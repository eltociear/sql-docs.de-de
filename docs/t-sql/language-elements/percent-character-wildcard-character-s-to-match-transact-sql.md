---
description: Prozentzeichen (Platzhalterzeichen - zu suchende(s) Zeichen) (Transact-SQL)
title: Platzhaltersuche (%)
ms.custom: seo-lt-2019
ms.date: 12/06/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- '%'
- '%_TSQL'
- wildcard
dev_langs:
- TSQL
helpviewer_keywords:
- conditions [SQL Server], wildcards
- '% (wildcard - character(s) to match)'
- matching conditions [SQL Server]
- wildcard characters [SQL Server]
- characters [SQL Server], wildcard
ms.assetid: d4cbc1a9-37e1-4101-97fb-e6ac30c1223e
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a0c232b2849f2fcfc7bf7d0a946714b15f753fc
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88307550"
---
# <a name="percent-character-wildcard---characters-to-match-transact-sql"></a>Prozentzeichen (Platzhalterzeichen - zu suchende(s) Zeichen) (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Entspricht einer Zeichenfolge aus null oder mehr Zeichen. Dieser Platzhalter kann entweder als Präfix oder Suffix verwendet werden.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel werden alle Vornamen der Personen in der `Person`-Tabelle von `AdventureWorks2012` zurückgegeben, die mit `Dan` beginnen.  
  
```  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName  
FROM Person.Person  
WHERE FirstName LIKE 'Dan%';  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LIKE &#40;Transact-SQL&#41;](../../t-sql/language-elements/like-transact-sql.md)   
 [Operatoren &#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [Ausdrücke &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)  
 [&#91; &#93; (Wildcard - Character(s) to Match) ([ ] (Platzhalterzeichen – zu suchende[s] Zeichen))](../../t-sql/language-elements/wildcard-character-s-to-match-transact-sql.md)   
  [&#91;^&#93; (Wildcard - Character(s) Not to Match) ([^] (Platzhalterzeichen – nicht zu suchende[s] Zeichen))](../../t-sql/language-elements/wildcard-character-s-not-to-match-transact-sql.md)     
 [_ (Platzhalterzeichen – einzelnes zu suchendes Zeichen)](../../t-sql/language-elements/wildcard-match-one-character-transact-sql.md)  
    
  
