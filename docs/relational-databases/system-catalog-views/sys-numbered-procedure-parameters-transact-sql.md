---
description: sys.numbered_procedure_parameters (Transact-SQL)
title: sys. numbered_procedure_parameters (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- numbered_procedure_parameters_TSQL
- sys.numbered_procedure_parameters_TSQL
- numbered_procedure_parameters
- sys.numbered_procedure_parameters
dev_langs:
- TSQL
helpviewer_keywords:
- sys.numbered_procedure_parameters catalog view
ms.assetid: a441d46d-1f30-41c2-8d94-e9442f59786e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2edff92d0cac8a45bfc895e77f5d113701b903f9
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88455208"
---
# <a name="sysnumbered_procedure_parameters-transact-sql"></a>sys.numbered_procedure_parameters (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Enthält eine Zeile für jeden Parameter einer nummerierten Prozedur. Beim Erstellen einer nummerierten gespeicherten Prozedur erhält die Basisprozedur die Nummer 1. Nachfolgende Prozeduren erhalten die Nummern 2, 3 usw. **sys.numbered_procedure_parameters** enthält die Parameterdefinitionen für alle nachfolgenden Prozeduren ab der Nummer 2 aufwärts. Diese Sicht zeigt keine Parameter für die gespeicherte Basisprozedur (Nummer 1). Die gespeicherte Basisprozedur ist mit einer nicht nummerierten gespeicherten Prozedur vergleichbar. Ihre Parameter werden daher in [sys.parameters (Transact-SQL)](../../relational-databases/system-catalog-views/sys-parameters-transact-sql.md)dargestellt.  
  
> [!IMPORTANT]  
>  Nummerierte Prozeduren sind als veraltet markiert. Von der Verwendung nummerierter Prozeduren wird abgeraten. Ein DEPRECATION_ANNOUNCEMENT-Ereignis wird ausgelöst, wenn eine Abfrage kompiliert wird, die diese Katalogsicht verwendet.  
  
> [!NOTE]  
>  XML- und CLR-Parameter werden für nummerierte Prozeduren nicht unterstützt.  
  
|Spaltenname|Datentyp|BESCHREIBUNG|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|Die ID des Objekts, zu dem dieser Parameter gehört.|  
|**procedure_number**|**smallint**|Die Nummer dieser Prozedur innerhalb des Objekts, d. h. 2 oder größer.|  
|**name**|**sysname**|Der Name des Parameters. Ist innerhalb von **procedure_number**eindeutig.|  
|**parameter_id**|**int**|ID des Parameters. Ist innerhalb von **procedure_number**eindeutig.|  
|**system_type_id**|**tinyint**|Die Systemtyp-ID des Parameters.|  
|**user_type_id**|**int**|Die ID des Parametertyps gemäß der Definition seitens des Benutzers.|  
|**max_length**|**smallint**|Die maximale Länge des Parameters in Byte.<br /><br /> -1 = Spaltendaten sind vom Datentyp varchar(max), nvarchar(max) oder varbinary(max).|  
|**precision**|**tinyint**|Genauigkeit des Parameters, wenn dieser numerisch ist. Andernfalls ist der Wert 0.|  
|**scale**|**tinyint**|Dezimalstellen des Parameters, wenn dieser numerisch ist. Andernfalls ist der Wert 0.|  
|**is_output**|**bit**|1 = Der Parameter ist ein Ausgabe- oder Rückgabewert; andernfalls 0.|  
|**is_cursor_ref**|**bit**|1 = Der Parameter ist ein Cursorverweis.|  
  
> [!NOTE]  
>  XML- und CLR-Parameter werden für nummerierte Prozeduren nicht unterstützt.  
  
## <a name="permissions"></a>Berechtigungen  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Weitere Informationen  
 [Katalogsichten für Objekte &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Katalogsichten &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
