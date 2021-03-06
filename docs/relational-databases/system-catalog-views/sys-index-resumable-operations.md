---
description: sys. index_resumable_operations (Transact-SQL)
title: sys. index_resumable_operations (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/12/2019
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.index_resumable_operations_TSQL
- sys.indexes_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.indexes
- sys.index_resumable_operations
ms.assetid: ''
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2017||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: fa2ae5221dbd360c5bad7279d27dbaedc7ae7f16
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88490308"
---
# <a name="sysindex_resumable_operations-transact-sql"></a>sys. index_resumable_operations (Transact-SQL)

[!INCLUDE[sqlserver2017-asdb](../../includes/applies-to-version/sqlserver2017-asdb.md)]
**sys. index_resumable_operations** ist eine Systemsicht, die den aktuellen Ausführungs Status für die fort Setz Bare indexneu Erstellung oder-Erstellung überwacht und überprüft.  
**Gilt für**: SQL Server (2017 und höher) und Azure SQL-Datenbank
  
|Spaltenname|Datentyp|BESCHREIBUNG|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|ID des Objekts, zu dem dieser Index gehört (lässt keine NULL-Werte zu).|  
|**index_id**|**int**|ID des Indexes (lässt keine NULL-Werte zu). **index_id** ist nur innerhalb des-Objekts eindeutig.|
|**name**|**sysname**|Name des Indexes. der **Name** ist nur innerhalb des Objekts eindeutig.|  
|**sql_text**|**nvarchar(max)**|DDL-T-SQL-Anweisungs Text|
|**last_max_dop**|**smallint**|Letztes MAX_DOP verwendet (Standardwert = 0)|
|**partition_number**|**int**|Die Partitionsnummer im besitzenden Index oder Heap. Für nicht partitionierte Tabellen und Indizes oder für den Fall, dass alle Partitionen neu erstellt werden, ist der Wert dieser Spalte NULL.|
|**Status**|**tinyint**|Betriebsstatus für fort Setz baren Index:<br /><br />0 = wird ausgeführt<br /><br />1 = anhalten|
|**state_desc**|**nvarchar(60)**|Beschreibung des Betriebsstatus für einen fort Setz baren Index (wird ausgeführt oder angehalten)|  
|**start_time**|**datetime**|Startzeit des Index Vorgangs (lässt keine NULL-Werte zu)|
|**last_pause_time**|**DataTime**| Zeit für Index Vorgang: letzte Pause (Nullable). NULL, wenn der Vorgang ausgeführt wird und nie angehalten wird.|
|**total_execution_time**|**int**|Gesamt Ausführungszeit der Startzeit in Minuten (lässt keine NULL-Werte zu)|
|**percent_complete**|**real**|Der Fortschritt des Index Vorgangs in% (lässt keine NULL-Werte zu).|
|**page_count**|**bigint**|Die Gesamtanzahl der Indexseiten, die vom indexbuildvorgang für die neuen Indizes und Zuordnungs Indizes zugeordnet werden (keine NULL-Werte zulassen).

## <a name="permissions"></a>Berechtigungen

[!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  

## <a name="example"></a>Beispiel

 Listet alle fort Setz baren Index Erstellungs-oder Neuerstellungs Vorgänge auf, die sich im anhaltezustand befinden.

```sql
SELECT * FROM  sys.index_resumable_operations WHERE STATE = 1;  
```

## <a name="see-also"></a>Weitere Informationen

- [ALTER INDEX](../../t-sql/statements/alter-index-transact-sql.md)
- [CREATE INDEX](../../t-sql/statements/create-index-transact-sql.md)
- [Katalogansichten](catalog-views-transact-sql.md)
- [Objektkatalog Sichten](object-catalog-views-transact-sql.md)
- [sys.indexes](sys-xml-indexes-transact-sql.md)
- [sys.index_columns](sys-index-columns-transact-sql.md)
- [sys.xml_indexes](sys-xml-indexes-transact-sql.md)
- [sys.objects](sys-index-columns-transact-sql.md)
- [sys.key_constraints](sys-key-constraints-transact-sql.md)
- [sys.filegroups](sys-filegroups-transact-sql.md)
- [sys.partition_schemes](sys-partition-schemes-transact-sql.md)
- [FAQ: Abfragen des SQL Server-Systemkatalogs](querying-the-sql-server-system-catalog-faq.md)
