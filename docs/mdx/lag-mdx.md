---
description: Lag (MDX)
title: Verzögerung (MDX) | Microsoft-Dokumentation
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: bc9beb8215d8d690f2d4ccdf43c3aaf03096b9d8
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88477042"
---
# <a name="lag-mdx"></a>Lag (MDX)


  Gibt das Element zurück, das eine angegebene Anzahl von Positionen vor einem angegebenen Element auf der Ebene des Elements liegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Member_Expression.Lag(Index)   
```  
  
## <a name="arguments"></a>Argumente  
 *Member_Expression*  
 Ein gültiger MDX-Ausdruck (Multidimensional Expressions), der ein Element zurückgibt.  
  
 *Index*  
 Ein gültiger numerischer Ausdruck, der die Anzahl der Elementpositionen angibt, die vor dem Element liegen sollen.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Elementpositionen auf einer Ebene werden über die natürliche Reihenfolge der Attributhierarchie bestimmt. Die Nummerierung der Positionen basiert auf Null.  
  
 Wenn die angegebene Verzögerung 0 (null) ist, gibt die **lag** -Funktion den angegebenen Member selbst zurück.  
  
 Wenn die angegebene Verzögerung negativ ist, gibt die **lag** -Funktion einen nachfolgenden Member zurück.  
  
 `Lag(1)` entspricht der [PrevMember](../mdx/prevmember-mdx.md) -Funktion. `Lag(-1)` entspricht der [NextMember](../mdx/nextmember-mdx.md) -Funktion.  
  
 Die **lag** -Funktion ähnelt der [Lead](../mdx/lead-mdx.md) -Funktion, mit der Ausnahme, dass die **Lead** -Funktion in umgekehrter Richtung zur **lag** -Funktion sucht. Somit ist `Lag(n)` äquivalent zu `Lead(-n)`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Wert December 2001 zurückgegeben:  
  
```  
SELECT [Date].[Fiscal].[Month].[February 2002].Lag(2) ON 0  
FROM [Adventure Works]  
  
```  
  
 Im folgenden Beispiel wird der Wert March 2002 zurückgegeben:  
  
```  
SELECT [Date].[Fiscal].[Month].[February 2002].Lag(-1) ON 0  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [MDX-Funktionsreferenz &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
