---
description: Parameter (ADO für Visual C++-Syntax)
title: Parameter (ADO für Visual C++-Syntax) | Microsoft-Dokumentation
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
dev_langs:
- C++
helpviewer_keywords:
- Parameter collection [ADO], ADO for Visual C++ syntax
ms.assetid: 74801dc1-cf0f-4a6e-960b-5990fe55e30d
author: rothja
ms.author: jroth
ms.openlocfilehash: b2d502f6071375f7d5a482b2db9753caa15fb086
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88990221"
---
# <a name="parameter-ado-for-visual-c-syntax"></a>Parameter (ADO für Visual C++-Syntax)
## <a name="methods"></a>Methoden  
  
```  
AppendChunk(VARIANT Val)  
```  
  
## <a name="properties"></a>Eigenschaften  
  
```  
get_Attributes(LONG *plParmAttribs)  
put_Attributes(LONG lParmAttribs)  
get_Direction(ParameterDirectionEnum *plParmDirection)  
put_Direction(ParameterDirectionEnum lParmDirection)  
get_Name(BSTR *pbstr)  
put_Name(BSTR bstr)  
get_NumericScale(BYTE *pbScale)  
put_NumericScale(BYTE bScale)  
get_Precision(BYTE *pbPrecision)  
put_Precision(BYTE bPrecision)  
get_Size(long *pl)  
put_Size(long l)  
get_Type(DataTypeEnum *psDataType)  
put_Type(DataTypeEnum sDataType)  
get_Value(VARIANT *pvar)  
put_Value(VARIANT val)  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Parameter-Objekt](./parameter-object.md)