---
description: sys.sp_xtp_unbind_db_resource_pool (Transact-SQL)
title: sys. sp_xtp_unbind_db_resource_pool (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_xtp_unbind_db_resource_pool_TSQL
- sp_xtp_unbind_db_resource_pool
- sys.sp_xtp_unbind_db_resource_pool_TSQL
- sys.sp_xtp_unbind_db_resource_pool
dev_langs:
- TSQL
helpviewer_keywords:
- sp_xtp_unbind_db_resource_pool
- sys.sp_xtp_unbind_db_resource_pool
ms.assetid: 695a796d-087e-4bc8-99d0-ddc342604c75
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4dda2f6da0ee65b7bfa927739ac945407f28cbc7
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88463930"
---
# <a name="syssp_xtp_unbind_db_resource_pool-transact-sql"></a>sys.sp_xtp_unbind_db_resource_pool (Transact-SQL)
[!INCLUDE[sqlserver](../../includes/applies-to-version/sqlserver.md)]

  Durch diese Systemprozedur wird eine vorhandene Bindung zwischen einer Datenbank und einem Ressourcenpool entfernt, um die [!INCLUDE[hek_2](../../includes/hek-2-md.md)] -Speicherauslastung nachzuverfolgen.  Wenn derzeit kein Pool an die angegebene Datenbank gebunden ist, war die Ausführung erfolgreich. Wenn die Datenbankbindung aufgehoben wird, bleibt der zuvor zugeordnete Arbeitsspeicher für speicheroptimierte Objekte dem vorherigen Ressourcenpool zugeordnet. Sie müssen die Datenbank neu starten, um den zugeordneten Arbeitsspeicher freizugeben. Sobald die Bindung einer Datenbank an den Ressourcenpool aufgehoben wird, fällt sie an den DEFAULT-Ressourcenpool zurück.  
  
 ![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Symbol für Themenlink") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```sql  
sys.sp_xtp_unbind_db_resource_pool 'database_name'  
```  
  
## <a name="arguments"></a>Argumente  
 database_name  
 Der Name einer vorhandenen [!INCLUDE[hek_2](../../includes/hek-2-md.md)] -aktivierten Datenbank.  
  
#### <a name="parameters"></a>Parameter  
  
## <a name="messages"></a>Meldungen  
 Wenn die Datenbank an einen benannten Ressourcenpool gebunden wurde, wurde die Prozedur erfolgreich ausgeführt. Sie müssen die Datenbank jedoch neu starten, damit die aufgehobene Bindung wirksam wird.  
 Wenn für die angegebene Datenbank keine Bindung besteht, wird `sp_xtp_unbind_db_resource_pool` zwar erfolgreich ausgeführt, gibt aber folgende Informationsmeldung aus:  
  
```  
Msg 41374, Level 16, State 1, Procedure sp_xtp_unbind_db_resource_pool_internal, Line 140.  
Database 'Hekaton_DB' does not have a binding to a resource pool.  
  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird die Bindung der Hekaton_DB-Datenbank an den [!INCLUDE[hek_2](../../includes/hek-2-md.md)] -Ressourcenpool aufgehoben.  Wenn Hekaton_DB derzeit nicht an einen [!INCLUDE[hek_2](../../includes/hek-2-md.md)] -Ressourcenpool gebunden ist, wird eine Meldung ausgegeben. Die Datenbank muss neu gestartet werden, damit die aufgehobene Bindung wirksam wird.  
  
```sql  
sys.sp_xtp_unbind_db_resource_pool 'Hekaton_DB'  
```  
  
## <a name="requirements"></a>Anforderungen  
  
-   Die durch `database_name` angegebene Datenbank muss an einen [!INCLUDE[hek_2](../../includes/hek-2-md.md)] -Ressourcenpool gebunden sein.  
  
-   Erfordert die CONTROL SERVER-Berechtigung.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Binden einer Datenbank mit speicheroptimierten Tabellen an einen Ressourcenpool](../../relational-databases/in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)   
 [sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql.md)  
  
  
