---
description: Adress Book-Datenbindungsobjekt
title: Adressbuch-Daten Bindungs Objekt | Microsoft-Dokumentation
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS scenarios [ADO], data-binding object
- address book application scenario [ADO], data-binding object
ms.assetid: 080c1925-d453-4b89-92ac-c93591490518
author: rothja
ms.author: jroth
ms.openlocfilehash: d6b6bb99ea218268a7ccb988acb2f49fb4898f32
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88978441"
---
# <a name="address-book-data-binding-object"></a>Adress Book-Datenbindungsobjekt
Die Adressbuch Anwendung verwendet [RDS. DataControl](../../reference/rds-api/datacontrol-object-rds.md) -Objekt zum Binden von Daten aus der SQL Server Datenbank an ein visuelles Objekt (in diesem Fall eine DHTML-Tabelle) auf der Client-HTML-Seite der Anwendung. Die ereignisgesteuerte VBScript-Programmlogik verwendet [RDS. DataControl](../../reference/rds-api/datacontrol-object-rds.md) in:  
  
> [!IMPORTANT]
>  Ab Windows 8 und Windows Server 2012 sind RDS-Server Komponenten nicht mehr im Windows-Betriebssystem enthalten (weitere Details finden Sie unter Windows 8 und [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) ). RDS-Client Komponenten werden in einer zukünftigen Version von Windows entfernt. Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden. Anwendungen, die RDS verwenden, sollten zu [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)migriert werden.  
  
-   Fragen Sie die Datenbank ab, senden Sie Aktualisierungen an die Datenbank, und aktualisieren Sie das Datenraster.  
  
-   Ermöglicht Benutzern das Wechseln zum ersten, nächsten, vorherigen oder letzten Datensatz im Datenraster.  
  
 Im folgenden Code wird der RDS-Code definiert **. DataControl** -Komponente:  
  
```vb
<OBJECT classid="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33"  
   ID=DC1 Width=1 Height=1>  
   <PARAM NAME="SERVER" VALUE="https://<%=Request.ServerVariables("SERVER_NAME")%>">  
   <PARAM NAME="CONNECT" VALUE="Provider=sqloledb;  
Initial Catalog=AddrBookDb;Integrated Security=SSPI;">  
</OBJECT>  
```  
  
 Das Objekttag definiert das **RDS. Die Komponente "DataControl** " im Programm. Das-Tag enthält zwei Arten von Parametern:  
  
-   Die dem generischen Objekttag zugeordneten.  
  
-   Die für das **RDS spezifischen. DataControl** -Objekt.  
  
## <a name="generic-object-tag-parameters"></a>Generische Objekttagparameter  
 In der folgenden Tabelle werden die Parameter beschrieben, die dem Objekttag zugeordnet sind.  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|***ClassID***|Eine eindeutige 128-Bit-Zahl, die den Typ des eingebetteten Objekts für das System identifiziert. Dieser Bezeichner wird in der Systemregistrierung des lokalen Computers verwaltet. (Für die Klassen-IDs der **RDS. DataControl** -Objekt finden Sie unter [RDS. DataControl-Objekt](../../reference/rds-api/datacontrol-object-rds.md).)|  
|***ID***|Definiert einen Dokument weiten Bezeichner für das eingebettete Objekt, das zur Identifizierung im Code verwendet wird.|  
  
## <a name="rdsdatacontrol-tag-parameters"></a>RDS. DataControl-Tagparameter  
 In der folgenden Tabelle werden die für RDS spezifischen Parameter beschrieben **. DataControl** -Objekt. (Eine komplette Liste der **RDS. DataControl** -Objekt Parameter und wann diese implementiert werden sollten, finden Sie unter [RDS. DataControl-Objekt](../../reference/rds-api/datacontrol-object-rds.md).)  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[Servers](../../reference/rds-api/server-property-rds.md)|Wenn Sie http verwenden, ist der Wert der Name des Server Computers, dem vorangestellt ist `https://` .|  
|[CONNECT](../../reference/rds-api/connect-property-rds.md)|Stellt die erforderlichen Verbindungsinformationen für **RDS bereit. DataControl** zum Herstellen einer Verbindung mit SQL Server.|  
|[SQL](../../reference/rds-api/sql-property.md)|Legt die zum Abrufen des [Recordsets verwendete Abfrage Zeichenfolge](../../reference/ado-api/recordset-object-ado.md)fest oder gibt diese zurück.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Adress Book-Befehlsschaltflächen](./address-book-command-buttons.md)