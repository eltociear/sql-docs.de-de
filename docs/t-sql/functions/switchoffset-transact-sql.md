---
description: SWITCHOFFSET (Transact-SQL)
title: SWITCHOFFSET (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/02/2015
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- SWITCHTZ
- SWITCHTZ_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- dates [SQL Server], functions
- functions [SQL Server], time
- functions [SQL Server], date and time
- SWITCHOFFSET function [SQL Server]
- time [SQL Server], functions
- date and time [SQL Server], SWITCHOFFSET
- time zones [SQL Server]
ms.assetid: 32a48e36-0aa4-4260-9fe9-cae9197d16c5
author: julieMSFT
ms.author: jrasnick
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: f8cffc510ca7d089be5326abf3d3823807b416e6
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88417196"
---
# <a name="switchoffset-transact-sql"></a>SWITCHOFFSET (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Gibt einen **datetimeoffset**-Wert zurück, der von einem gespeicherten Zeitzonenoffset in einen angegebenen neuen Zeitzonenoffset geändert wurde.  
  
 Eine Übersicht über alle Datums- und Uhrzeitdatentypen und zugehörige Funktionen für [!INCLUDE[tsql](../../includes/tsql-md.md)] finden Sie unter [Date and Time Data Types and Functions &#40;Transact-SQL&#41; (Datums- und Uhrzeitdatentypen und zugehörige Funktionen)](../../t-sql/functions/date-and-time-data-types-and-functions-transact-sql.md).  
  
 ![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Symbol für Themenlink") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
SWITCHOFFSET ( DATETIMEOFFSET, time_zone )   
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Argumente
 *DATETIMEOFFSET*  
 Ein Ausdruck, der in einen **datetimeoffset(n)**-Wert aufgelöst werden kann.  
  
 *time_zone*  
 Eine Zeichenfolge im Format [+|-]TZH:TZM oder eine ganze Zahl mit Vorzeichen (Minuten), die den Zeitzonenoffset darstellt und von der vorausgesetzt wird, dass sie die Sommerzeit berücksichtigt und entsprechend angepasst ist.  
  
## <a name="return-type"></a>Rückgabetyp  
 **datetimeoffset** mit der Genauigkeit von Bruchteilen des *DATETIMEOFFSET*-Arguments.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie SWITCHOFFSET, um einen **datetimeoffset**-Wert in einem Zeitzonenoffset auszuwählen, der sich vom ursprünglich gespeicherten Zeitzonenoffset unterscheidet. Der gespeicherte *time_zone*-Wert wird nicht von SWITCHOFFSET aktualisiert.  
  
 SWITCHOFFSET kann verwendet werden, um eine **datetimeoffset**-Spalte zu aktualisieren.  
  
 Bei Verwendung von SWITCHOFFSET mit der GETDATE()-Funktion wird die Abfrage u. U. langsam ausgeführt. Das liegt daran, dass der Abfrageoptimierer keine genauen Kardinalitätsschätzungen für den datetime-Wert abrufen kann. Um dieses Problem zu beheben, verwenden Sie den OPTION (RECOMPILE)-Abfragehinweis, um zu erzwingen, dass der Abfrageoptimierer einen Abfrageplan erneut kompiliert, sobald dieselbe Abfrage das nächste Mal ausgeführt wird. Auf diese Weise erhält der Optimierer exakte Kardinalitätsschätzungen und kann einen effizienteren Abfrageplan erzeugen. Weitere Informationen zum RECOMPILE-Abfragehinweis finden Sie unter [Query Hints &#40;Transact-SQL&#41; (Abfragehinweise (Transact-SQL))](../../t-sql/queries/hints-transact-sql-query.md).  
  
```  
DECLARE @dt datetimeoffset = switchoffset (CONVERT(datetimeoffset, GETDATE()), '-04:00');   
SELECT * FROM t    
WHERE c1 > @dt OPTION (RECOMPILE);  
  
```  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird `SWITCHOFFSET` verwendet, um einen anderen als den in der Datenbank gespeicherten Zeitzonenoffset-Wert anzuzeigen.  
  
```  
CREATE TABLE dbo.test   
    (  
    ColDatetimeoffset datetimeoffset  
    );  
GO  
INSERT INTO dbo.test   
VALUES ('1998-09-20 7:45:50.71345 -5:00');  
GO  
SELECT SWITCHOFFSET (ColDatetimeoffset, '-08:00')   
FROM dbo.test;  
GO  
--Returns: 1998-09-20 04:45:50.7134500 -08:00  
SELECT ColDatetimeoffset  
FROM dbo.test;  
--Returns: 1998-09-20 07:45:50.7134500 -05:00  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [CAST und CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)   
 [AT TIME ZONE &#40;Transact-SQL&#41;](../../t-sql/queries/at-time-zone-transact-sql.md)  
  
  


