---
title: Unterstützte SQL Server und SSIS-Datentypen für DQS-Domänen
description: Beschreibt die vier Datentypen für Data Quality Services (DQS)-Domänen (Data, Decimal, Integer und String) in SQL Server.
ms.custom: seo-lt-2019
ms.date: 11/08/2011
ms.prod: sql
ms.prod_service: data-quality-services
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 4931143a-b84d-478b-9b45-174128d36ed3
author: swinarko
ms.author: sawinark
ms.openlocfilehash: 6c90a3119e3377af2e850c973e8ee4cfa80422a7
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85883310"
---
# <a name="supported-sql-server-and-ssis-data-types-for-dqs-domains"></a>Unterstützte SQL Server und SSIS-Datentypen für DQS-Domänen

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sqlserver.md)]

  In SQL Server und SQL Server Integration Services (SSIS) sind zahlreiche Datentypen vorhanden, darunter jedoch nur vier für DQS-Domänen: Date, Decimal, Integer und String. Nicht alle SQL Server- und SSIS-Datentypen werden in DQS unterstützt. Sie können die Quelldaten zum Durchführen der Datenbereinigung einer DQS-Domäne nur zuordnen, wenn der Quelldatentyp in DQS unterstützt wird und mit dem DQS-Domänendatentyp übereinstimmt. Dieses Thema enthält Informationen zu den SQL Server- und SSIS-Datentypen, die unterstützt werden und jedem der vier Domänendatentypen in DQS zugeordnet werden können.  
  
> [!NOTE]  
>  Der Datentyp der Quellspalte wird in XLSX- und XLS-Dateien vom häufigsten Datentyp in den ersten acht Zeilen bestimmt. Wenn eine Zelle diesem Datentyp nicht entspricht, erhält sie einen NULL-Wert. Entsprechend wird auch in CSV-Dateien der Datentyp der Quellspalte vom häufigsten Datentyp in den ersten acht Zeilen bestimmt.  
  
##  <a name="supported-sql-server-data-types"></a><a name="SQLServer"></a>Unterstützte SQL Server-Datentypen 
 Die folgende Tabelle enthält Informationen zu den für jeden DQS-Domänendatentyp unterstützten SQL Server-Datentypen:  
  
|DQS-Domänendatentyp|Unterstützte SQL Server-Datentypen|  
|--------------------------|------------------------------------|  
|Datum|Datum|  
|Decimal|Decimal<br /><br /> float<br /><br /> money<br /><br /> NUMERIC<br /><br /> real<br /><br /> SMALLMONEY|  
|Ganze Zahl|BIGINT<br /><br /> INT<br /><br /> SMALLINT<br /><br /> TINYINT|  
|Zeichenfolge|char<br /><br /> NCHAR<br /><br /> NVARCHAR<br /><br /> varchar|  
  
 Die restlichen SQL Server-Datentypen werden in DQS nicht unterstützt. Informationen zu allen unterstützten SQL Server-Datentypen finden Sie unter[Data Types &#40;Transact-SQL&#41; (Datentypen &#40;Transact-SQL&#41;)](../t-sql/data-types/data-types-transact-sql.md).  
  
##  <a name="supported-ssis-data-types"></a><a name="SSIS"></a>Unterstützte SSIS-Datentypen  
 Die folgende Tabelle enthält Informationen zu den für jeden DQS-Domänendatentyp unterstützten SSIS-Datentypen:  
  
|DQS-Domänendatentyp|Unterstützter SSIS-Datentyp|  
|--------------------------|------------------------------|  
|Date|DT_DATE|  
|Decimal|DT_DECIMAL<br /><br /> DT_NUMERIC<br /><br /> DT_R4<br /><br /> DT_R8|  
|Ganze Zahl|DT_I1<br /><br /> DT_I2<br /><br /> DT_I4<br /><br /> DT_I8<br /><br /> DT_U1<br /><br /> DT_U2<br /><br /> DT_U4<br /><br /> DT_U8|  
|Zeichenfolge|DT_STR<br /><br /> DT_WSTR|  
  
 Die restlichen SSIS-Datentypen werden in DQS nicht unterstützt. Informationen zu allen SSIS-Datentypen finden Sie unter [Integration Services Data Types](../integration-services/data-flow/integration-services-data-types.md).  
  
## <a name="see-also"></a>Weitere Informationen  
 [Verwalten einer Domäne](../data-quality-services/managing-a-domain.md)  
  
  
