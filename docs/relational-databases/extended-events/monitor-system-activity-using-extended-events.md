---
title: Überwachen der Systemaktivität mit erweiterten Ereignisses
description: Hier erfahren Sie, wie Sie anhand von erweiterten Ereignissen mit der Ereignisablaufverfolgung für Windows die Systemaktivität überwachen. Hier erhalten Sie weitere Informationen zu den CREATE EVENT SESSION-, ALTER EVENT SESSION- und DROP EVENT SESSION-Anweisungen.
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: xevents
ms.topic: tutorial
helpviewer_keywords:
- xe
- extended events [SQL Server], monitoring system activity
ms.assetid: d83ad88f-818c-49fe-a9a9-299f704fca53
author: MightyPen
ms.author: genemi
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: d80d0e1deee504d4dd5a2d8ce49303a799f66fb8
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85790847"
---
# <a name="monitor-system-activity-using-extended-events"></a>Überwachen der Systemaktivität mit erweiterten Ereignisses

[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Das folgende Verfahren veranschaulicht, wie Extended Events mit der Ereignisablaufverfolgung für Windows (ETW) zum Überwachen der Systemaktivität verwendet werden kann. Außerdem wird gezeigt, wie die Anweisungen CREATE EVENT SESSION, ALTER EVENT SESSION und DROP EVENT SESSION verwendet werden.  
  
 Das Ausführen dieser Tasks umfasst die Verwendung des Abfrage-Editors in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , um den folgenden Vorgang durchzuführen. Das Verfahren erfordert außerdem, mithilfe der Eingabeaufforderung ETW-Befehle auszuführen.  
  
### <a name="to-monitor-system-activity-using-extended-events"></a>So überwachen Sie die Systemaktivität mit erweiterten Ereignissen  
  
1.  Geben Sie im Abfrage-Editor die folgenden Anweisungen aus, um eine Ereignissitzung zu erstellen und zwei Ereignisse hinzuzufügen. Diese Ereignisse, checkpoint_begin und checkpoint_end, werden am Anfang und am Ende eines Datenbankprüfpunkts ausgelöst.  
  
    ```  
    CREATE EVENT SESSION test0  
    ON SERVER  
    ADD EVENT sqlserver.checkpoint_begin,  
    ADD EVENT sqlserver.checkpoint_end  
    WITH (MAX_DISPATCH_LATENCY = 1 SECONDS)  
    go  
    ```  
  
2.  Fügen Sie das Ziel mit 32 Buckets hinzu, um die Anzahl der Prüfpunkte basierend auf der Datenbank-ID zu zählen.  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.histogram  
    (  
          SET slots = 32, filtering_event_name = 'sqlserver.checkpoint_end', source_type = 0, source = 'database_id'  
    )  
    go  
    ```  
  
3.  Geben Sie die folgenden Anweisungen aus, um das ETW-Ziel hinzuzufügen. So können Sie die Anfangs- und Endereignisse anzeigen, mit denen die Dauer des Prüfpunkts bestimmt wird.  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.etw_classic_sync_target  
    go  
    ```  
  
4.  Geben Sie die folgenden Anweisungen aus, um die Sitzung und die Ereignisauflistung zu starten.  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = start  
    go  
    ```  
  
5.  Geben Sie die folgenden Anweisungen aus, um drei Ereignisse auszulösen.  
  
    ```  
    USE tempdb  
          checkpoint  
    go  
    USE master  
          checkpoint  
          checkpoint  
    go  
    ```  
  
6.  Geben Sie die folgenden Anweisungen aus, um die Ereigniszähler anzuzeigen.  
  
    ```  
    SELECT CAST(xest.target_data AS xml) Bucketizer_Target_Data_in_XML  
    FROM sys.dm_xe_session_targets xest  
    JOIN sys.dm_xe_sessions xes ON xes.address = xest.event_session_address  
    JOIN sys.server_event_sessions ses ON xes.name = ses.name  
    WHERE xest.target_name = 'histogram' AND xes.name = 'test0'  
    go  
    ```  
  
7.  Geben Sie die folgenden Befehle an der Eingabeaufforderung aus, um die ETW-Daten anzuzeigen.  
  
    > [!NOTE]  
    >  Um Hilfe für den **tracerpt** -Befehl aufzurufen, geben Sie an der Eingabeaufforderung `tracerpt /?`ein.  
  
    ```  
    logman query -ets --- List the ETW sessions. This is optional.  
    logman update XE_DEFAULT_ETW_SESSION -fd -ets --- Flush the ETW log.  
    tracerpt %temp%\xeetw.etl -o xeetw.txt --- Dump the events so they can be seen.  
    ```  
  
8.  Geben Sie die folgenden Anweisungen aus, um die Ereignissitzung zu beenden und vom Server zu entfernen.  

    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = STOP  
    go  
  
    DROP EVENT SESSION test0  
    ON SERVER  
    go  
    ```  
  
## <a name="see-also"></a>Weitere Informationen  
 [CREATE EVENT SESSION &#40;Transact-SQL&#41;](../../t-sql/statements/create-event-session-transact-sql.md)   
 [ALTER EVENT SESSION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-event-session-transact-sql.md)   
 [DROP EVENT SESSION &#40;Transact-SQL&#41;](../../t-sql/statements/drop-event-session-transact-sql.md)   
 [Katalogsichten für erweiterte Ereignisse &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql.md)   
 [Dynamische Verwaltungssichten für erweiterte Ereignisse](../../relational-databases/system-dynamic-management-views/extended-events-dynamic-management-views.md)   
 [Ziele für erweiterte Ereignisse von SQL Server](https://msdn.microsoft.com/library/e281684c-40d1-4cf9-a0d4-7ea1ecffa384)  
  
  
