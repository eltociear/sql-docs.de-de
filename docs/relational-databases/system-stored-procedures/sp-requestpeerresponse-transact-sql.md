---
description: sp_requestpeerresponse (Transact-SQL)
title: sp_requestpeerresponse (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_requestpeerresponse_TSQL
- sp_requestpeerresponse
helpviewer_keywords:
- sp_requestpeerresponse
ms.assetid: cbe13c22-4d7d-4a36-b194-7a13ce68ef27
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b2114460ca878b45bb0b850c066e1fd9356504a8
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88489198"
---
# <a name="sp_requestpeerresponse-transact-sql"></a>sp_requestpeerresponse (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Wenn diese Prozedur auf einem Knoten in einer Peer-zu-Peer-Topologie ausgeführt wird, fordert sie von jedem anderen Knoten in der Topologie eine Antwort an. Durch Ausführen dieser Prozedur und Überprüfen der entsprechenden Antworten können Sie sicherstellen, dass alle früheren Befehle an die antwortenden Knoten übermittelt wurden. Diese gespeicherte Prozedur wird auf dem anfordernden Knoten auf jeder Datenbank ausgeführt.  
  
 ![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Symbol für Themenlink") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_requestpeerresponse [ @publication = ] 'publication'  
    [ , [ @description = ] 'description'  
    [ , [ @request_id = ] request_id OUTPUT ]  
```  
  
## <a name="arguments"></a>Argumente  
`[ @publication = ] 'publication'` Der Name der Veröffentlichung in einer Peer-zu-Peer-Topologie, für die der Status überprüft wird. *Publication* ist vom **Datentyp vom Datentyp sysname**und hat keinen Standardwert.  
  
`[ @description = ] 'description'` Benutzerdefinierte Informationen, die zum Identifizieren einzelner Status Anforderungen verwendet werden können. die *Beschreibung* ist vom Datentyp **nvarchar (4000)** und hat den Standardwert NULL.  
  
`[ @request_id = ] request_id` Gibt die ID der neuen Anforderung zurück. *request_id* ist vom Datentyp **int** und ein Output-Parameter. Dieser Wert kann beim Ausführen [sp_helppeerresponses &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql.md) verwendet werden, um alle Antworten auf eine Status Anforderung anzuzeigen.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 **0** (Erfolg) oder **1** (Fehler)  
  
## <a name="remarks"></a>Bemerkungen  
 **sp_requestpeerresponse** wird in der Peer-zu-Peer-Transaktions Replikation verwendet.  
  
 **sp_requestpeerresponse** wird verwendet, um sicherzustellen, dass alle anderen Knoten alle Befehle empfangen haben, bevor eine in einer Peer-zu-Peer-Topologie veröffentlichte Datenbank wieder hergestellt wird. Die Prozedur wird außerdem beim Replizieren von DDL-Änderungen (Data Definition Language) verwendet, die vorgenommen wurden, während ein Knoten offline war. Damit kann abgeschätzt werden, wann diese Änderungen bei den anderen Knoten ankommen.  
  
 **sp_requestpeerresponse** kann nicht innerhalb einer benutzerdefinierten Transaktion ausgeführt werden.  
  
## <a name="permissions"></a>Berechtigungen  
 Nur Mitglieder der festen Server Rolle **sysadmin** oder der festen Daten Bank Rolle **db_owner** können **sp_requestpeerresponse**ausführen.  
  
## <a name="see-also"></a>Siehe auch  
 [sp_deletepeerrequesthistory &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-deletepeerrequesthistory-transact-sql.md)   
 [sp_helppeerrequests &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-helppeerrequests-transact-sql.md)  
  
  
