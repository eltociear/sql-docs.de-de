---
title: getBytes-Methode (SQLServerCallableStatement) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerCallableStatement.getBytes
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b6e88cea-54b3-4d18-a9af-db54abf19f45
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 67b52629e0996eb5c162fbea8ef3d5920b7db19c
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "80921578"
---
# <a name="getbytes-method-sqlservercallablestatement"></a>getBytes-Methode (SQLServerCallableStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Ruft den Wert des angegebenen Parameters als Bytearray ab.  
  
## <a name="overload-list"></a>Überladungsliste  
  
|Name|BESCHREIBUNG|  
|----------|-----------------|  
|[getBytes (int)](../../../connect/jdbc/reference/getbytes-method-int.md)|Ruft den Wert des angegebenen Parameters unter Berücksichtigung des Parameterindexes als ein Array von Bytewerten ab.|  
|[getBytes (java.lang.String)](../../../connect/jdbc/reference/getbytes-method-java-lang-string.md)|Ruft den Wert des angegebenen Parameters unter Berücksichtigung des Parameternamens als ein Array von Bytewerten ab.|  
  
## <a name="remarks"></a>Bemerkungen  
 In einer früheren Version von [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] konnten Sie mithilfe von „SQLServerCallableStatement.getBytes“ Werte zwischen Bytearrays und den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datentypen **date**, **time**, **datetime2** oder **datetimeoffset** konvertieren. Nun wird durch Verwendung der Methode mit diesen Datentypen eine Ausnahme ausgelöst, die angibt, dass die Konvertierung nicht unterstützt wird.  
  
## <a name="see-also"></a>Weitere Informationen  
 [SQLServerCallableStatement-Elemente](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement-Klasse](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
