---
description: SQLSetEnvAttr
title: Sqltenvattr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLSetEnvAttr function
ms.assetid: d4114571-feca-4330-b2e4-7bfd1050b812
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 4b6bcc13a62a052e31777b1fa4044a9c5ba56c96
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88420794"
---
# <a name="sqlsetenvattr"></a>SQLSetEnvAttr
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Die [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250) definiert, wie ODBC-Treiber die **SQLSetEnvAttr** -Attributspezifikationen aus Anwendungen interpretieren sollen, die in die ODBC 2.*x* - oder ODBC 3.*x* -API geschrieben wurden. Der ODBC-Treiber von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Native Client entspricht diesen Regeln.  
  
 Eines der Attribute ist, das von **SQLSetEnvAttr** gesteuert wird, bestimmt, ob Verbindungspooling verwendet werden soll. Wenn Verbindungspooling mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber verwendet wird, muss für den *DriverCompletion* -Parameter SQL_DRIVER_NOPROMPT festgelegt werden, wenn eine Verbindung mit [SQLDriverConnect](../../relational-databases/native-client-odbc-api/sqldriverconnect.md) oder **SQLConnect**hergestellt wird.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Sqlsettenvattr-Funktion](https://go.microsoft.com/fwlink/?LinkId=59369)   
 [ODBC API Implementation Details](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
