---
description: 'Lektion 3: Hinzufügen der Protokollierung mit SSIS'
title: 'Lektion 3: Hinzufügen der Protokollierung mit SSIS | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 01/04/2019
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: tutorial
ms.assetid: 64cd24cc-ba8e-4bd7-b10b-6b80d8b04af6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59065cf89a1b3f012e183eb062258bc20bbe6a1a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88422224"
---
# <a name="lesson-3-add-logging-with-ssis"></a>Lektion 3: Hinzufügen der Protokollierung mit SSIS

[!INCLUDE[sqlserver-ssis](../includes/applies-to-version/sqlserver-ssis.md)]



[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] umfasst Protokollierungsfunktionen für die Problembehandlung und Überwachung der Paketausführung mithilfe einer Reihe von Task- und Containerereignissen. Die Protokollierungsfeatures sind flexibel. Sie können die Protokollierung auf Paketebene oder für individuelle Tasks oder Container in dem Paket aktivieren. Wählen Sie aus, welche Ereignisse protokolliert werden sollen, und erstellen Sie mehrere Protokolle für ein einzelnes Paket.  
  
Die Protokolle werden von Protokollanbietern erstellt. Jeder Protokollanbieter ist in der Lage, Protokollierungsinformationen in verschiedenen Formaten und Zieltypen zu schreiben. [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] stellt die folgenden Protokollanbieter bereit:  
  
-   Textdatei  
  
-   [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]  
  
-   Windows-Ereignisprotokoll:  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
  
-   XML-Datei:  
  
In dieser Lektion erstellen Sie eine Kopie des Pakets, das Sie in [Lektion 2: Hinzufügen von Schleifen mit SSIS](../integration-services/lesson-2-adding-looping-with-ssis.md) erstellt haben. Dann fügen Sie beim Arbeiten mit diesem neuen Paket die Protokollierung hinzu und konfigurieren sie, um bestimmte Ereignisse während der Paketausführung zu überwachen. Wenn Sie keine der vorherigen Lektionen abgeschlossen haben, können Sie auch das abgeschlossene Paket aus Lektion 2 kopieren, das im Tutorial enthalten ist.  

> [!NOTE]
> Machen Sie sich, falls noch nicht geschehen, mit den [Anforderungen für Lektion 1](../integration-services/lesson-1-create-a-project-and-basic-package-with-ssis.md#prerequisites) vertraut.

## <a name="lesson-tasks"></a>Aufgaben der Lektion  
Diese Lektion enthält die folgenden Aufgaben:  
  
-   [Schritt 1: Kopieren des Pakets aus Lektion 2](../integration-services/lesson-3-1-copying-the-lesson-2-package.md)  
  
-   [Schritt 2: Hinzufügen und Konfigurieren der Protokollierung](../integration-services/lesson-3-2-adding-and-configuring-logging.md)  
  
-   [Schritt 3: Testen des Tutorialpakets aus Lektion 3](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
## <a name="start-the-lesson"></a>Lektion beginnen  
[Schritt 1: Kopieren des Pakets aus Lektion 2](../integration-services/lesson-3-1-copying-the-lesson-2-package.md)  
  
