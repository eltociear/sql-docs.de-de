---
title: 'rsInternalError: Reporting Services-Fehler | Microsoft-Dokumentation'
description: 'Auf dieser Fehlerreferenzseite erfahren Sie mehr über die Ereignis-ID „rsInternalError“: Interner Fehler beim Berichtsserver. Weitere Informationen finden Sie im Fehlerprotokoll.'
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: troubleshooting
ms.topic: conceptual
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3f134f1c071b62c1c32f48855f76f62d5a1b0a69
ms.sourcegitcommit: b2cc3f213042813af803ced37901c5c9d8016c24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81487240"
---
# <a name="rsinternalerror---reporting-services-error"></a>rsInternalError – Reporting Services-Fehler
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Ereignis-ID|rsInternalError|  
|Ereignisquelle|Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings|  
|Komponente|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|Meldungstext|Interner Fehler beim Berichtsserver. Weitere Informationen finden Sie im Fehlerprotokoll.|  
  
## <a name="explanation"></a>Erklärung  
 Dies ist eine generische Fehlermeldung, auf die häufig ein Fehler mit ausführlicher Beschreibung folgt, die weitere Informationen enthält.  
  
 Interne Fehler treten nicht häufig auf. Wenn dieser Fehler ausgegeben wird, finden Sie weitere Informationen in den Ablaufverfolgungsprotokollen des Berichtsservers. Wenn Sie an demselben Computer als lokaler Administrator angemeldet sind, können Sie zusätzlich die Aufrufliste anzeigen, um weitere Informationen zu erhalten.  
  
## <a name="user-action"></a>Benutzeraktion  
 Überprüfen Sie die Berichtsserver-Protokolldateien, um die genaue Ursache dieser Meldung zu bestimmen. Sie finden diese Dateien unter \Microsoft SQL Server\MSRS12.\<Instanzname>\Reporting Services\LogFiles. Weitere Informationen finden Sie unter [Reporting Services-Protokolldateien und Quellen](../../reporting-services/report-server/reporting-services-log-files-and-sources.md).  
  
 Um die Aufrufliste anzuzeigen, klicken Sie mit der rechten Maustaste auf die Seite, auf der der Fehler auftritt, und zeigen Sie auf **Quelle anzeigen**. Um die Aufrufliste anzuzeigen, sind Administratorberechtigungen für den gleichen Computer erforderlich, auf dem der Fehler aufgetreten ist.  
  
 Wenn keine weiteren Informationen verfügbar sind, versuchen Sie erneut, die Anforderung durchzuführen.  
  
## <a name="internal-only"></a>Nur intern  
  
## <a name="see-also"></a>Weitere Informationen  
 [Start and Stop the Report Server Service (Starten und Beenden des Berichtsserverdiensts)](../../reporting-services/report-server/start-and-stop-the-report-server-service.md)  
  
  
