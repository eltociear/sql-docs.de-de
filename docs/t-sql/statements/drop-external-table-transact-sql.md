---
description: DROP EXTERNAL TABLE (Transact-SQL)
title: DROP EXTERNAL TABLE (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: sql-data-warehouse, pdw, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 02a6a236-0756-4570-abfa-6f677a7df042
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 75ad3c1c1de4d12a1efa2267c63a2f22e5f2cb2e
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88415626"
---
# <a name="drop-external-table-transact-sql"></a>DROP EXTERNAL TABLE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  Entfernt eine externe PolyBase-Tabelle aus einer Datenbank, löscht aber nicht die externen Daten.  
  
 ![Artikellinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Artikellinksymbol") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```syntaxsql
DROP EXTERNAL TABLE { database_name.schema_name.table_name | schema_name.table_name | table_name }
[;]  
```  
  

## <a name="arguments"></a>Argumente  
 `[ database_name . [schema_name] . | schema_name . ] table_name`  
 Der ein- bis dreiteilige Name der externen Tabelle, die entfernt werden soll. Der Tabellenname kann optional das Schema oder die Datenbank und das Schema enthalten.  
  
## <a name="permissions"></a>Berechtigungen  
  
-   Erfordert die Berechtigung **ALTER** für das Schema, zu dem die Tabelle gehört.  
  
## <a name="general-remarks"></a>Allgemeine Hinweise  
 Das Löschen einer externen Tabelle entfernt alle Metadaten, die mit der Tabelle verknüpft sind. Externe Daten werden nicht gelöscht.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-using-basic-syntax"></a>A. Verwenden einer grundlegenden Syntax  
  
```sql  
DROP EXTERNAL TABLE SalesPerson;  
DROP EXTERNAL TABLE dbo.SalesPerson;  
DROP EXTERNAL TABLE EasternDivision.dbo.SalesPerson;  
```  
  
### <a name="b-dropping-an-external-table-from-the-current-database"></a>B. Löschen einer externen Tabelle aus der aktuellen Datenbank  
 Im folgenden Beispiel werden die `ProductVendor1`-Tabelle, ihre Daten, ihre Indizes und alle davon abhängigen Sichten aus der aktuellen Datenbank entfernt.  
  
```sql  
DROP EXTERNAL TABLE ProductVendor1;  
```  
  
### <a name="c-dropping-a-table-from-another-database"></a>C. Löschen einer Tabelle aus einer anderen Datenbank  
 Im folgenden Beispiel wird die `SalesPerson`-Tabelle in der `EasternDivision`-Datenbank gelöscht.  
  
```sql  
DROP EXTERNAL TABLE EasternDivision.dbo.SalesPerson;  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [CREATE EXTERNAL TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-external-table-transact-sql.md)  
  
