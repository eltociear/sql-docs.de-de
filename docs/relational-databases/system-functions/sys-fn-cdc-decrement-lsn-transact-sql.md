---
description: sys.fn_cdc_decrement_lsn (Transact-SQL)
title: sys. fn_cdc_decrement_lsn (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_cdc_decrement_lsn
- sys.fn_cdc_decrement_lsn_TSQL
- sys.fn_cdc_decrement_lsn
- fn_cdc_decrement_lsn_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- fn_cdc_decrement_lsn
- sys.fn_cdc_decrement_lsn
ms.assetid: 83c182ad-4713-439b-8769-9b7408aec8b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 6402fabc4904ca8d9c9953d8dddc6f4626d949dc
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88321756"
---
# <a name="sysfn_cdc_decrement_lsn-transact-sql"></a>sys.fn_cdc_decrement_lsn (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Gibt die vorherige Protokollfolgenummer (Log Sequence Number, LSN) in der auf der angegebenen LSN basierenden Reihenfolge zurück.  
  
 ![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Symbol für Themenlink") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sys.fn_cdc_decrement_lsn ( lsn_value )  
```  
  
## <a name="arguments"></a>Argumente  
 *lsn_value*  
 LSN-Wert. *lsn_value* ist **binary(10)**  
  
## <a name="return-type"></a>Rückgabetyp  
 **binary(10)**  
  
## <a name="remarks"></a>Bemerkungen  
 Die von der Funktion zurückgegebene LSN ist immer kleiner als der angegebene Wert. Zwischen den beiden Werten können sich keine LSN-Werte befinden.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der **Public** -Daten Bank Rolle.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird mithilfe von `sys.fn_cdc_decrement_lsn` die LSN-Obergrenze in einer Abfrage festgelegt, bei der Änderungsdatenzeilen mit LSN-Werten zurückgegeben werden, die unter dem größten LSN-Wert liegen.  
  
```  
Use AdventureWorks2012;  
GO  
DECLARE @from_lsn binary(10), @to_lsn binary(10);  
SET @from_lsn = sys.fn_cdc_get_min_lsn('HumanResources_Employee');  
SET @to_lsn = sys.fn_cdc_decrement_lsn(sys.fn_cdc_get_max_lsn());  
SELECT * FROM cdc.fn_cdc_get_all_changes_HumanResources_Employee( @from_lsn, @to_lsn, 'all');   
GO  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [sys. fn_cdc_increment_lsn &#40;Transact-SQL-&#41;](../../relational-databases/system-functions/sys-fn-cdc-increment-lsn-transact-sql.md)   
 [sys. fn_cdc_get_min_lsn &#40;Transact-SQL-&#41;](../../relational-databases/system-functions/sys-fn-cdc-get-min-lsn-transact-sql.md)   
 [sys. fn_cdc_get_max_lsn &#40;Transact-SQL-&#41;](../../relational-databases/system-functions/sys-fn-cdc-get-max-lsn-transact-sql.md)   
 [Das Transaktionsprotokoll &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md)   
 [Über Change Data Capture &#40;SQL Server&#41;](../../relational-databases/track-changes/about-change-data-capture-sql-server.md)  
  
  
