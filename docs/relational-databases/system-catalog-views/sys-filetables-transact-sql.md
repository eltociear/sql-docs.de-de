---
description: sys.filetables (Transact-SQL)
title: sys. filetables (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- filetables
- filetables_TSQL
- sys.filetables
- sys.filetables_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.filetables catalog view
ms.assetid: a740be59-cd52-4707-9ad2-5203669a63ac
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7ac470d0cdc64860721f045a3108c0221d20e219
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88482185"
---
# <a name="sysfiletables-transact-sql"></a>sys.filetables (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Gibt eine Zeile für jede FileTable in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]zurück. Weitere Informationen zu FileTables finden Sie unter [FileTables &#40;SQL Server&#41;](../../relational-databases/blob/filetables-sql-server.md).    
  
|Spaltenname|Datentyp|BESCHREIBUNG|  
|-----------------|---------------|-----------------|  
|**object_id**||Objekt-ID. Ist innerhalb einer Datenbank eindeutig.<br /><br /> Weitere Informationen finden Sie unter [sys. Objects &#40;Transact-SQL-&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).|  
|**is_enabled**|**bit**|1 = FileTable weist den Status "aktiviert" auf.|  
|**directory_name**|**varchar (255)**|Der Name des Stammverzeichnisses für eine FileTable.|  
|**filename_collation_id**||Die für die FileTable definierte Sortierungs-ID|  
|**filename_collation_name**||Der für die FileTable definierte Sortierungsname|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Verwalten von filetables](../../relational-databases/blob/manage-filetables.md)   
 [FileTables &#40;SQL Server&#41;](../../relational-databases/blob/filetables-sql-server.md)  
  
  
