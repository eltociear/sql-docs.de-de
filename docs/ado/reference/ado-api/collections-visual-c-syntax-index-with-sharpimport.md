---
description: 'Auflistungen (Visual C++ Syntax Index mit #Import)'
title: 'Auflistungen (Visual C++ Syntax Index mit #Import) | Microsoft-Dokumentation'
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
- 'syntax indexes [ADO], ADO for Visual C++ syntax with #import'
- 'collections [ADO], ADO for Visual C++ syntax with #import'
- 'ADO for Visual C++ syntax with #import [ADO]'
- '#import [ADO]'
ms.assetid: 36fbca8e-1884-44b5-806b-d15e30f42fe6
author: rothja
ms.author: jroth
ms.openlocfilehash: cba9fa93b2f23388b11dc764a95b78d94df4874c
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88975261"
---
# <a name="collections-visual-c-syntax-index-with-import"></a>Auflistungen (Visual C++ Syntax Index mit #Import)
Es ist hilfreich zu wissen, dass Auflistungen bestimmte allgemeine Methoden und Eigenschaften erben.  
  
 Alle Auflistungen erben die **count** -Eigenschaft und die **Aktualisierungs** Methode, und alle Sammlungen fügen die **Item** -Eigenschaft hinzu. Die **Errors** -Auflistung fügt die **Clear** -Methode hinzu. Die **Parameters** -Auflistung erbt die Methoden zum **Anfügen** und **Löschen** , während die **Fields** -Auflistung die Methoden zum **Anfügen**, **Löschen**und **Aktualisieren** hinzufügt.  
  
## <a name="properties-collection"></a>'Properties'-Sammlung  
  
### <a name="methods"></a>Methoden  
  
```  
HRESULT Refresh( );  
```  
  
### <a name="properties"></a>Eigenschaften  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## <a name="errors-collection"></a>Fehlersammlung  
  
### <a name="methods"></a>Methoden  
  
```  
HRESULT Clear( );  
HRESULT Refresh( );  
```  
  
### <a name="properties"></a>Eigenschaften  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## <a name="parameters-collection"></a>Parameters-Auflistung  
  
### <a name="methods"></a>Methoden  
  
```  
HRESULT Append( IDispatch * Object );  
HRESULT Delete( const _variant_t & Index );  
HRESULT Refresh( );  
```  
  
### <a name="properties"></a>Eigenschaften  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## <a name="fields-collection"></a>Fields-Auflistung  
  
### <a name="methods"></a>Methoden  
  
```  
HRESULT Append( _bstr_t Name, enum DataTypeEnum Type, long DefinedSize, enum FieldAttributeEnum Attrib, const _variant_t & FieldValue = vtMissing );  
HRESULT Delete( const _variant_t & Index );  
HRESULT Refresh( );  
HRESULT Update( );  
```  
  
### <a name="properties"></a>Eigenschaften  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Fehlersammlung (ADO)](./errors-collection-ado.md)   
 [Fields-Auflistung (ADO)](./fields-collection-ado.md)   
 [Parameter Auflistung (ADO)](./parameters-collection-ado.md)   
 [Properties-Collection (ADO)](./properties-collection-ado.md)