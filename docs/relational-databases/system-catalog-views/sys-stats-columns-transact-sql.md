---
description: sys.stats_columns (Transact-SQL)
title: sys. stats_columns (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/18/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- stats_columns_TSQL
- stats_columns
- sys.stats_columns
- sys.stats_columns_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.stats_columns catalog view
ms.assetid: 93414d07-97e9-4501-8577-f35b8d68fbe9
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 818a96ab6d867e7aee0ec2e6485e88c8434cdc51
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88490139"
---
# <a name="sysstats_columns-transact-sql"></a>sys.stats_columns (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Enthält eine Zeile für jede Spalte, die Teil einer **sys.stats** -Statistik ist.  
  
|Spaltenname|Datentyp|BESCHREIBUNG|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|ID des Objekts, von dem diese Spalte ein Bestandteil ist|  
|**stats_id**|**int**|ID der Statistik, von der diese Spalte ein Bestandteil ist<br /><br />Wenn Statistiken einem Index entsprechen, ist der *stats_id* Wert mit dem *index_id* Wert in der [sys. Indexes](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md) -Katalog Sicht identisch.|  
|**stats_column_id**|**int**|1-basierte Ordnungszahl innerhalb der Gruppe von stats_columns-Spalten|  
|**column_id**|**int**|ID der Spalte in **sys.columns**|  
  
## <a name="permissions"></a>Berechtigungen  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Weitere Informationen  
 [Katalogsichten für Objekte &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Katalogsichten &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [FAQ: Abfragen des SQL Server-Systemkatalogs](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
 [Statistiken](../../relational-databases/statistics/statistics.md)    
 [sys.dm_db_stats_properties (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-properties-transact-sql.md)   
 [sys. dm_db_stats_histogram &#40;Transact-SQL-&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-histogram-transact-sql.md)   
 [sys.stats &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-stats-transact-sql.md)  
  
  
