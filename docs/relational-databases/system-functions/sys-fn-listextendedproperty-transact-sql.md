---
description: sys.fn_listextendedproperty (Transact-SQL)
title: sys. fn_listextendedproperty (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_listextendedproperty
- fn_listextendedproperty_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- fn_listextendedproperty function
- displaying extended properties
- database extended properties [SQL Server]
- viewing extended properties
- column extended properties [SQL Server]
- sys.fn_listextendedproperties function
- database objects [SQL Server], extended properties
- extended properties [SQL Server], columns
- table extended properties [SQL Server]
ms.assetid: 59bbb91f-a277-4a35-803e-dcb91e847a49
author: rothja
ms.author: jroth
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: dd891bcfdaddfb42e2b55e1b69e3f320563c1ba7
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88427822"
---
# <a name="sysfn_listextendedproperty-transact-sql"></a>sys.fn_listextendedproperty (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Gibt erweiterte Eigenschaftswerte von Datenbankobjekten zurück.  
 
 
 ![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Symbol für Themenlink") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
fn_listextendedproperty (   
    { default | 'property_name' | NULL }   
  , { default | 'level0_object_type' | NULL }   
  , { default | 'level0_object_name' | NULL }   
  , { default | 'level1_object_type' | NULL }   
  , { default | 'level1_object_name' | NULL }   
  , { default | 'level2_object_type' | NULL }   
  , { default | 'level2_object_name' | NULL }   
  )   
```  
  
## <a name="arguments"></a>Argumente  
 {Standard | '*property_name*' | Normal  
 Der Name der Eigenschaft. *property_name* ist vom **Datentyp vom Datentyp sysname**. Eine gültige Eingabe ist default, NULL oder ein Eigenschaftsname.  
  
 {Standard | '*level0_object_type*' | Normal  
 Der Benutzer oder benutzerdefinierte Typ. *level0_object_type* ist vom Datentyp **varchar (128)** und hat den Standardwert NULL. Gültige Eingaben sind ASSEMBLY, CONTRACT, EVENT NOTIFICATION, FILEGROUP, MESSAGE TYPE, PARTITION FUNCTION, PARTITION SCHEME, REMOTE SERVICE BINDING, ROUTE, SCHEMA, SERVICE, TRIGGER, TYPE, USER und NULL.  
  
> [!IMPORTANT]  
>  USER und TYPE als Typen der Ebene 0 werden in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht mehr unterstützt. Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktionen zurzeit verwenden. Verwenden Sie SCHEMA anstelle von USER als Typ der Ebene 0. Verwenden Sie für TYPE als Typ der Ebene 0 SCHEMA und TYPE als Typ der Ebene 1.  
  
 {Standard | '*level0_object_name*' | Normal  
 Der Name des angegebenen Objekttyps der Ebene 0. *level0_object_name* ist vom **Datentyp vom Datentyp sysname** und hat den Standardwert NULL. Eine gültige Eingabe ist default, NULL oder ein Objektname.  
  
 {Standard | '*level1_object_type*' | Normal  
 Der Typ des Objekts der Ebene 1. *level1_object_type* ist vom Datentyp **varchar (128)** und hat den Standardwert NULL. Gültige Eingabewerte sind AGGREGATE, DEFAULT, FUNCTION, LOGICAL FILE NAME, PROCEDURE, QUEUE, RULE, SYNONYM, TABLE, TYPE, VIEW, XML SCHEMA COLLECTION und NULL.  
  
> [!NOTE]  
>  default ergibt NULL, und 'default' ergibt den Objekttyp DEFAULT.  
  
 {Standard | '*level1_object_name*' | Normal  
 Der Name des angegebenen Objekttyps der Ebene 1. *level1_object_name* ist vom **Datentyp vom Datentyp sysname** und hat den Standardwert NULL. Eine gültige Eingabe ist default, NULL oder ein Objektname.  
  
 {Standard | '*level2_object_type*' | Normal  
 Der Typ des Objekts der Ebene 2. *level2_object_type* ist vom Datentyp **varchar (128)** und hat den Standardwert NULL. Gültige Eingaben sind DEFAULT, default (ergibt NULL) und NULL. Gültige Eingaben für *level2_object_type* sind Column, Einschränkung, Event Notification, Index, Parameter, Triggern und NULL.  
  
 {Standard | '*level2_object_name*' | Normal  
 Der Name des angegebenen Objekttyps der Ebene 2. *level2_object_name* ist vom **Datentyp vom Datentyp sysname** und hat den Standardwert NULL. Eine gültige Eingabe ist default, NULL oder ein Objektname.  
  
## <a name="tables-returned"></a>Zurückgegebene Tabellen  
 Dies ist das Format der von fn_listextendedproperty zurückgegebenen Tabellen.  
  
|Spaltenname|Datentyp|  
|-----------------|---------------|  
|objtype|**sysname**|  
|objname|**sysname**|  
|name|**sysname**|  
|value|**sql_variant**|  
  
 Wenn die zurückgegebene Tabelle leer ist, besitzt das Objekt keine erweiterten Eigenschaften oder der Benutzer hat keine Berechtigungen zum Auflisten der erweiterten Eigenschaften des Objekts. Beim Zurückgeben erweiterter Eigenschaften für die Datenbank selbst weisen die Spalten objtype und objname den Wert NULL auf.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn der Wert für *property_name* NULL oder default ist, gibt fn_listextendedproperty alle Eigenschaften für das angegebene Objekt zurück.  
  
 Wenn der Objekttyp angegeben ist und der Wert des entsprechenden Objektnamens NULL oder default ist, gibt fn_listextendedproperty alle erweiterten Eigenschaften für alle Objekte des angegebenen Typs zurück.  
  
 Die Objekte werden nach Ebenen unterschieden, wobei Ebene 0 die höchste und Ebene 2 die niedrigste ist. Wenn ein Objekttyp und -name einer niedrigen Ebene (Ebene 1 oder 2) angegeben sind, sollten die Werte für den Objekttyp und -namen des übergeordneten Objekts nicht NULL oder default sein. Andernfalls gibt die Funktion ein leeres Resultset zurück.  
  
 **objname** ist als Latin1_General_CI_AI korrigiert. Sie können dies umgehen, indem Sie die Sortierung im Vergleich überschreiben.  
  
```  
SELECT o.[object_id] AS 'table_id', o.[name] 'table_name',  
0 AS 'column_order', NULL AS 'column_name', NULL AS 'column_datatype',  
NULL AS 'column_length', Cast(e.value AS varchar(500)) AS 'column_description'  
FROM AdventureWorks.sys.objects AS o  
LEFT JOIN sys.fn_listextendedproperty(N'MS_Description', N'user',N'HumanResources',N'table', N'Employee', null, default) AS e  
    ON o.name = e.objname COLLATE SQL_Latin1_General_CP1_CI_AS  
WHERE o.name = 'Employee';  
```  
  
## <a name="permissions"></a>Berechtigungen  
 Die Berechtigungen zum Auflisten der erweiterten Eigenschaften von Objekten hängen vom Objekttyp ab.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-displaying-extended-properties-on-a-database"></a>A. Anzeigen erweiterter Eigenschaften für eine Datenbank  
 Im folgenden Beispiel werden alle erweiterten Eigenschaften angezeigt, die für das Datenbankobjekt selbst festgelegt wurden.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT objtype, objname, name, value  
FROM fn_listextendedproperty(default, default, default, default, default, default, default);  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `objtype    objname     name            value`  
  
 `---------  ---------   -----------     ----------------------------`  
  
 `NULL       NULL        MS_Description  AdventureWorks2008 Sample OLTP Database`  
  
 `(1 row(s) affected)`  
  
### <a name="b-displaying-extended-properties-on-all-columns-in-a-table"></a>B. Anzeigen erweiterter Eigenschaften für alle Spalten in einer Tabelle  
 Im folgenden Beispiel werden erweiterte Eigenschaften für Spalten in der- `ScrapReason` Tabelle aufgelistet. Diese ist im `Production`-Schema enthalten.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT objtype, objname, name, value  
FROM fn_listextendedproperty (NULL, 'schema', 'Production', 'table', 'ScrapReason', 'column', default);  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `objtype objname      name            value`  
  
 `------- -----------  -------------   ------------------------`  
  
 `COLUMN ScrapReasonID MS_Description  Primary key for ScrapReason records.`  
  
 `COLUMN Name          MS_Description  Failure description.`  
  
 `COLUMN ModifiedDate  MS_Description  Date the record was last updated.`  
  
 `(3 row(s) affected)`  
  
### <a name="c-displaying-extended-properties-on-all-tables-in-a-schema"></a>C. Anzeigen erweiterter Eigenschaften für alle Tabellen in einem Schema  
 Im folgenden Beispiel werden die erweiterten Eigenschaften für alle Tabellen aufgelistet, die im Schema enthalten sind `Sales` .  
  
```  
USE AdventureWorks2012;  
GO  
SELECT objtype, objname, name, value  
FROM fn_listextendedproperty (NULL, 'schema', 'Sales', 'table', default, NULL, NULL);  
GO  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [sp_addextendedproperty &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql.md)   
 [sp_dropextendedproperty &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-dropextendedproperty-transact-sql.md)   
 [sp_updateextendedproperty &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-updateextendedproperty-transact-sql.md)   
 [sys.extended_properties &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/extended-properties-catalog-views-sys-extended-properties.md)  
  
  
