---
title: Erteilen einer Berechtigung für einen Prinzipal | Microsoft-Dokumentation
description: Hier erfahren Sie, wie Sie einem Prinzipal in SQL Server mithilfe von SQL Server Management Studio oder Transact-SQL Berechtigungen gewähren. Außerdem werden bewährte Methoden vorgestellt.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Grant permission to a principal
ms.assetid: 4107389d-05b6-4aa3-9fa8-95b40cdf05dc
author: VanMSFT
ms.author: vanto
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 1d9522bf78d3c3d0a36047283d8b0ab9e3073b6d
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "86005629"
---
# <a name="grant-a-permission-to-a-principal"></a>Erteilen einer Berechtigung für einen Prinzipal
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
  In diesem Thema wird beschrieben, wie Sie mit [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Berechtigungen für einen Prinzipal in [!INCLUDE[tsql](../../../includes/tsql-md.md)]gewähren können.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   **So erteilen Sie eine Berechtigung für einen Prinzipal mit**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> Einschränkungen  
 Mit den folgenden Best Practices wird die Verwaltung von Berechtigungen erleichtert.  
  
-   Erteilen von Berechtigungen für Rollen statt einzelner Anmeldenamen oder Benutzer. Wenn eine Einzelperson durch eine andere ersetzt wird, kann fortgehende Einzelperson aus der Rolle entfernt und die neue Person der Rolle hinzugefügt werden. Die vielen Berechtigungen, die der Rolle möglicherweise zugeordnet sind, sind für die neue Einzelperson automatisch verfügbar. Wenn mehrere Personen in einer Organisation die gleichen Berechtigungen benötigen, können Sie diese der Rolle hinzufügen und ihnen so die gleichen Berechtigungen gewähren.  
  
-   Konfigurieren Sie ähnliche sicherungsfähige Elemente (Tabellen, Sichten und Prozeduren) als im Besitz eines Schemas befindlich, und gewähren Sie dem Schema anschließend Berechtigungen. Beispielsweise kann das Lohnlistenschema mehrere Tabellen, Sichten und gespeicherte Prozeduren besitzen. Durch Gewähren des Zugriffs für das Schema können alle zum Ausführen der Lohnlistenfunktion erforderlichen Berechtigungen gleichzeitig erteilt werden. Weitere Informationen zu den sicherungsfähigen Elementen, denen Berechtigungen gewährt werden können, finden Sie unter [Securables](../../../relational-databases/security/securables.md).  
  
###  <a name="security"></a><a name="Security"></a> Sicherheit  
  
####  <a name="permissions"></a><a name="Permissions"></a> Berechtigungen  
 Der Berechtigende (oder der mit der AS-Option angegebene Prinzipal) muss entweder über die Berechtigung selbst mit GRANT OPTION oder über eine höhere Berechtigung verfügen, in der die erteilte Berechtigung impliziert ist. Mitglieder der festen Serverrolle **sysadmin** können beliebige Berechtigungen erteilen.  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-grant-permission-to-a-principal"></a>So erteilen Sie eine Berechtigung für einen Prinzipal  
  
1.  Erweitern Sie im Objekt-Explorer die Datenbank, die das Objekt enthält, dem Sie Berechtigungen gewähren möchten.  
  
    > [!NOTE]  
    >  In diesen Schritten geht es ausdrücklich um das Gewähren von Berechtigungen für eine gespeicherte Prozedur. Sie können jedoch auch ähnliche Schritte vollziehen, um Tabellen, Sichten, Funktionen, Assemblys sowie anderen sicherungsfähigen Elementen Berechtigungen hinzuzufügen. Weitere Informationen finden Sie unter [GRANT &#40;Transact-SQL&#41;](../../../t-sql/statements/grant-transact-sql.md).  
  
2.  Erweitern Sie den Ordner **Programmierbarkeit** .  
  
3.  Erweitern Sie den Ordner **Gespeicherte Prozeduren** .  
  
4.  Klicken Sie mit der rechten Maustaste auf eine gespeicherte Prozedur, und wählen Sie **Eigenschaften**aus.  
  
5.  Klicken Sie im Dialogfeld **Eigenschaften der gespeicherten Prozedur -** _Name\_der\_gespeicherten_Prozedur_ unter „Seite auswählen“ auf die Option **Berechtigungen**. Verwenden Sie diese Seite, um der gespeicherten Prozedur Benutzer oder Rollen hinzuzufügen und um die Berechtigungen anzugeben, die diese Benutzer oder Rollen haben.  
  
6.  Wenn Sie fertig sind, klicken Sie auf **OK**.  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
  
#### <a name="to-grant-permission-to-a-principal"></a>So erteilen Sie eine Berechtigung für einen Prinzipal  
  
1.  Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.  
  
    ```  
    -- Grants EXECUTE permission on stored procedure HumanResources.uspUpdateEmployeeHireInfo to an application role called Recruiting11.   
    USE AdventureWorks2012;  
    GO  
    GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
        TO Recruiting11;  
    GO  
    ```  
  
 Weitere Informationen finden Sie unter [GRANT &#40;Transact-SQL&#41;](../../../t-sql/statements/grant-transact-sql.md) und [GRANT (Objektberechtigungen)&#40;Transact-SQL&#41;](../../../t-sql/statements/grant-object-permissions-transact-sql.md).  
  
## <a name="see-also"></a>Weitere Informationen  
 [Prinzipale &#40;Datenbank-Engine&#41;](../../../relational-databases/security/authentication-access/principals-database-engine.md)  
  
  
