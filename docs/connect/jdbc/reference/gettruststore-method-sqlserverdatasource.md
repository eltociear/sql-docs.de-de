---
title: getTrustStore-Methode (SQLServerDataSource) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- getTrustStore Method (SQLServerDataSource)
apilocation:
- getTrustStore Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: 8f5850e4-8627-49a8-ba0e-b1f4014322a5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 43b537a20cf39d64e06baf6f0cae78ed46526915
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "80911158"
---
# <a name="gettruststore-method-sqlserverdatasource"></a>getTrustStore-Methode (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Gibt den Pfad (einschließlich Dateiname) zur trustStore-Zertifikatsdatei zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public java.lang.String getTrustStore()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Eine **Zeichenfolge** mit dem Pfad (einschließlich Dateiname) zur trustStore-Zertifikatsdatei, oder NULL, wenn kein Wert festgelegt wurde.  
  
## <a name="remarks"></a>Bemerkungen  
 Ist die trustStore-Eigenschaft nicht festgelegt, wird von der [getTrustStore](../../../connect/jdbc/reference/gettruststore-method-sqlserverdatasource.md)-Methode NULL zurückgegeben.  
  
## <a name="see-also"></a>Weitere Informationen  
 [SQLServerDataSource-Elemente](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource-Klasse](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
