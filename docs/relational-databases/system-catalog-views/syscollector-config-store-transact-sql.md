---
description: syscollector_config_store (Transact-SQL)
title: syscollector_config_store (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- syscollector_config_store_TSQL
- syscollector_config_store
dev_langs:
- TSQL
helpviewer_keywords:
- data collector view
- syscollector_config_store view
ms.assetid: f15f6b05-6808-4b76-b6a8-48dec844cf63
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 339bbba2335512c582251f960224baae15513618
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88399786"
---
# <a name="syscollector_config_store-transact-sql"></a>syscollector_config_store (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Gibt Eigenschaften zurück, die im Gegensatz zu einer Sammlungssatzinstanz für den gesamten Datensammler gelten. Jede Zeile in dieser Sicht beschreibt eine bestimmte Datensammlereigenschaft, wie den Namen des Verwaltungs-Data Warehouse und den Namen der Instanz, in der sich das Verwaltungs-Data Warehouse befindet.  
  
|Spaltenname|Datentyp|BESCHREIBUNG|  
|-----------------|---------------|-----------------|  
|parameter_name|**nvarchar(128)**|Den Namen der Eigenschaft. Lässt keine NULL-Werte zu.|  
|parameter_value|**sql_variant**|Der tatsächliche Wert der Eigenschaft. Lässt NULL-Werte zu.|  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die SELECT-Berechtigung für die Sicht oder die Mitgliedschaft in der festen Datenbankrolle dc_operator, dc_proxy oder dc_admin.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Liste der verfügbaren Eigenschaften ist festgelegt, und deren Werte können nur mithilfe der geeigneten gespeicherten Prozedur geändert werden. In der folgenden Tabelle werden die Eigenschaften beschrieben, die durch diese Sicht verfügbar gemacht werden.  
  
|Eigenschaftenname|Beschreibung|  
|-------------------|-----------------|  
|CacheDirectory|Der Name des Verzeichnisses im Dateisystem, in dem die Sammlertyppakete temporäre Informationen speichern.<br /><br /> NULL = das standardmäßige temporäre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verzeichnis wird verwendet.|  
|CacheWindow|Gibt die Datenbeibehaltungsrichtlinie des Cacheverzeichnisses für fehlgeschlagene Datenuploads an.<br /><br /> -1 = Daten aus allen fehlgeschlagenen Uploads beibehalten.<br /><br /> 0 - Keine Daten aus fehlgeschlagenen Uploads beibehalten.<br /><br /> *n* = Daten aus *n* früheren Uploadfehlern beibehalten, wobei *n* >= 1 ist.<br /><br /> Verwenden Sie die gespeicherte Prozedur sp_syscollector_set_cache_window, um diesen Wert zu ändern.|  
|CollectorEnabled|Gibt den Status des Datensammlers an.<br /><br /> 0 = deaktiviert<br /><br /> 1 = aktiviert<br /><br /> Verwenden Sie entweder die gespeicherte Prozedur sp_syscollector_enable_collector oder die gespeicherte Prozedur sp_syscollector_disable_collector, um diesen Wert zu ändern.|  
|MDWDatabase|Der Name des Verwaltungs-Data Warehouses. Verwenden Sie die gespeicherte Prozedur sp_syscollector_set_warehouse_database_name, um diesen Wert zu ändern.|  
|MDWInstance|Der Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz für das Verwaltungs-Data Warehouse. Verwenden Sie die gespeicherte Prozedur sp_syscollector_set_warehouse_instance_name, um diesen Wert zu ändern.|  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird die syscollector_config_store-Sicht abgefragt.  
  
```sql  
SELECT parameter_name, parameter_value  
FROM msdb.dbo.syscollector_config_store;  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Gespeicherte Prozeduren für den Datensammler &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [Datensammler Sichten &#40;Transact-SQL-&#41;](../../relational-databases/system-catalog-views/data-collector-views-transact-sql.md)   
 [Datensammlung](../../relational-databases/data-collection/data-collection.md)   
 [sp_syscollector_enable_collector &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql.md)   
 [sp_syscollector_disable_collector &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql.md)   
 [sp_syscollector_set_warehouse_database_name &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-syscollector-set-warehouse-database-name-transact-sql.md)   
 [sp_syscollector_set_warehouse_instance_name &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-syscollector-set-warehouse-instance-name-transact-sql.md)   
 [sp_syscollector_set_cache_window &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-syscollector-set-cache-window-transact-sql.md)  
  
  
