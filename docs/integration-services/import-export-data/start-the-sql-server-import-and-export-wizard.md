---
description: Starten des SQL Server-Import/Export-Assistenten
title: Starten des SQL Server-Import/Export-Assistenten
titleSuffix: Integration Services (SSIS)
ms.prod: sql
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Import and Export Wizard
- starting SQL Server Import and Export Wizard
- Import and Export Wizard
- starting Import and Export Wizard
ms.assetid: 5fc4f6d1-1f6f-444e-9aeb-827f85e1c405
author: chugugrace
ms.author: chugu
ms.reviewer: ''
ms.custom: ''
ms.date: 11/18/2019
ms.openlocfilehash: adbb8eee477e9f021c011b91e586492e64747851
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88346576"
---
# <a name="start-the-sql-server-import-and-export-wizard"></a>Starten des SQL Server-Import/Export-Assistenten

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]

Starten Sie den Import- und Export-Assistenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit einer der in diesem Artikel beschriebenen Methoden zum Importieren von Daten aus und Exportieren von Daten in unterstützte Datenquellen.

> [!IMPORTANT]
> In diesem Thema wird nur beschrieben, wie Sie den Assistenten **starten** . Wenn Sie andere Themen interessieren, lesen Sie die Seite [Verwandte Tasks und Inhalte](#related-tasks-and-content).

So starten Sie den Assistenten

- Von [Startmenü](#start-menu).
- Von [Befehlszeile](#command-prompt).
- Von [SQL Server Management Studio (SSMS)](#sql-server-management-studio-ssms).
- Von [Visual Studio mit SQL Server Data Tools (SSDT)](#visual-studio).

## <a name="prerequisite---is-the-wizard-installed-on-your-computer"></a>Voraussetzung: Installation des Assistenten auf dem Computer

Wenn Sie den Assistenten ausführen möchten, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aber nicht auf Ihrem Computer installiert ist, können Sie den Import- und Export-Assistenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit SQL Server Data Tools (SSDT) installieren. Weitere Informationen finden Sie unter [Herunterladen von SQL Server Data Tools (SSDT)](https://msdn.microsoft.com/library/mt204009.aspx).

> [!NOTE]
> Sie müssen SQL Server installieren, um die 64-Bit-Version des SQL Server-Import/Export-Assistenten verwenden zu können. SQL Server Data Tools (SSDT) und SQL Server Management Studio (SSMS) sind 32-Bit-Anwendungen und installieren daher auch nur 32-Bit-Dateien, einschließlich der 32-Bit-Version des Assistenten.

## <a name="start-menu"></a>Startmenü

### <a name="start-the-sql-server-import-and-export-wizard-from-the-start-menu"></a>Starten des SQL Server-Import/Export-Assistenten über das Menü „Start“

1. Suchen und erweitern Sie **Microsoft SQL Server 20xx** im Menü **Start**.
2. Klicken Sie auf eine der folgenden Optionen:
    - **SQL Server 20xx-Datenimport und -export (64 Bit)**
    - **SQL Server 20xx-Datenimport und -export (32 Bit)**

    Führen Sie die 64-Bit-Version des Assistenten aus, sofern für die Datenquelle kein 32-Bit-Datenanbieter erforderlich ist.

    ![Starten des Assistenten über das Startmenü](../../integration-services/import-export-data/media/start-wizard-start-64.png)

## <a name="command-prompt"></a>Eingabeaufforderung

### <a name="start-the-sql-server-import-and-export-wizard-from-the-command-prompt"></a>Starten des SQL Server-Import/Export-Assistenten über die Eingabeaufforderung

Führen Sie in einem Eingabeaufforderungsfenster **DTSWizard.exe** von einem der folgenden Speicherorte aus.

- **C:\Programme\Microsoft SQL Server\140\DTS\Binn** bei einer 64-Bit-Version.
  - *140* = SQL Server 2017.  Dieser Wert hängt von der Version von SQL Server ab, die Sie besitzen.

- **C:\Programme (x86)\Microsoft SQL Server\140\DTS\Binn** bei einer 32-Bit-Version.
  - *140* = SQL Server 2017.  Dieser Wert hängt von der Version von SQL Server ab, die Sie besitzen.

Führen Sie die 64-Bit-Version des Assistenten aus, sofern für die Datenquelle kein 32-Bit-Datenanbieter erforderlich ist.

![Starten des Assistenten über cmd](../../integration-services/import-export-data/media/start-wizard-cmd.png)
  
## <a name="sql-server-management-studio-ssms"></a>SQL Server Management Studio (SSMS)

### <a name="start-the-sql-server-import-and-export-wizard-from-sql-server-management-studio-ssms"></a>Starten des SQL Server-Import/Export-Assistenten in SQL Server Management Studio (SSMS)

1. Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.

2. Erweitern Sie **Datenbanken**.

3. Klicken Sie mit der rechten Maustaste auf eine Datenbank.

4. Zeigen Sie auf **Aufgaben**.

5. Klicken Sie auf eine der folgenden Optionen:

   - **Daten importieren**

   - **Daten exportieren**  

   ![Starten des Assistenten in SSMS](../../integration-services/import-export-data/media/start-wizard-ssms.jpg) 

Wenn Sie SQL Server nicht installiert haben, bzw. SQL Server installiert haben, jedoch nicht SQL Server Management Studio, lesen Sie [Herunterladen von SQL Server Management Studio (SSMS)](../../ssms/download-sql-server-management-studio-ssms.md).

## <a name="visual-studio"></a>Visual Studio

### <a name="start-the-sql-server-import-and-export-wizard-from-visual-studio-with-sql-server-data-tools-ssdt"></a>Starten des SQL Server-Import/Export-Assistenten aus Visual Studio mit SQL Server Data Tools (SSDT)

 Führen Sie in Visual Studio mit [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]mit einem geöffneten Integration Services-Projekt eine der folgenden Aktionen aus.

- Klicken Sie im Menü **Projekt** auf **SSIS-Import/Export-Assistent**.

   ![Starten des Assistenten aus einem Projekt](../../integration-services/import-export-data/media/start-wizard-project.png)

   \- oder –

- Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Ordner **SSIS-Pakete** , und klicken Sie dann auf **SSIS-Import/Export-Assistent**.

    ![Starten des Assistenten aus Paketen](../../integration-services/import-export-data/media/start-wizard-packages.png)

Wenn Sie Visual Studio nicht installiert haben, bzw. Visual Studio installiert haben, jedoch nicht SQL Server Data Tools, lesen Sie [Herunterladen von SQL Server Data Tools (SSDT)](../../ssdt/download-sql-server-data-tools-ssdt.md).

## <a name="get-the-wizard"></a>Installieren des Assistenten

Wenn Sie den Assistenten ausführen möchten, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aber nicht auf Ihrem Computer installiert ist, können Sie den Import- und Export-Assistenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit SQL Server Data Tools (SSDT) installieren. Weitere Informationen finden Sie unter [Herunterladen von SQL Server Data Tools (SSDT)](https://msdn.microsoft.com/library/mt204009.aspx).

## <a name="get-help-while-the-wizard-is-running"></a>Aufrufen der Hilfe während der Ausführung des Assistent

> [!TIP]
> Drücken Sie auf einer beliebigen Seite oder in einem beliebigen Dialogfeld des Assistenten F1, um die Dokumentation für die aktuelle Seite anzuzeigen.   

## <a name="whats-next"></a>Nächste Schritte

Beim Starten des Assistenten ist die erste Seite **Willkommen beim SQL Server-Import/Export-Assistenten**. Sie müssen auf dieser Seite keine Aktionen durchführen. Weitere Informationen finden Sie unter [Willkommen beim SQL Server-Import/Export-Assistenten](../../integration-services/import-export-data/welcome-to-sql-server-import-and-export-wizard.md).  
  
## <a name="related-tasks-and-content"></a>Verwandte Tasks und Inhalte

Im Folgenden werden einige weitere grundlegenden Tasks aufgelistet.

- **Sehen Sie sich ein kurzes Beispiel zur Funktionsweise des Assistenten an.**

  - **Wenn Sie lieber mit Screenshots arbeiten:** Sehen Sie sich dieses einfache Beispiel auf der Seite [Erste Schritte mit diesem einfachen Beispiel für den Import-/Export-Assistenten](../../integration-services/import-export-data/get-started-with-this-simple-example-of-the-import-and-export-wizard.md) an.

  - **Wenn Sie sich lieber ein Video ansehen möchten:** Sehen Sie sich dieses vierminütige YouTube-Video an, in dem der Assistent vorgestellt wird und klar und deutlich erklärt wird, wie Daten nach Excel exportiert werden können: [Using the SQL Server Import and Export Wizard to Export to Excel](https://go.microsoft.com/fwlink/?linkid=829049) (Verwenden des SQL Server-Import/Export-Assistenten zum Exportieren nach Excel).

  - **Weitere Informationen zur Funktionsweise des Assistenten:**

  - **Weitere Informationen zum Assistenten.** Wenn Sie eine Übersicht über den Assistenten suchen, lesen Sie [Importieren und Exportieren von für SQL Server unterstützten Datenquellen](../../integration-services/import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).

  - **Weitere Informationen zu den Schritten des Assistenten:** Weitere Informationen zu den einzelnen Schritten des Assistenten finden Sie auf der Seite [Steps in the SQL Server Import and Export Wizard](../../integration-services/import-export-data/steps-in-the-sql-server-import-and-export-wizard.md) (Schritte im SQL Server-Import/Export-Assistenten). Es ist außerdem eine eigene Dokumentationsseite für jede Seite des Assistenten verfügbar.

  - **Weitere Informationen zum Herstellen einer Verbindung zwischen Datenquellen und -zielen:** Wählen Sie für weitere Informationen zum Herstellen einer Verbindung mit Ihren Daten die Seite aus der Liste aus, die Sie besonders interessiert: [Connect to data sources with the SQL Server Import and Export Wizard (Herstellen einer Verbindung mit Datenquellen mit dem SQL Server Import/Export-Assistenten)](../../integration-services/import-export-data/connect-to-data-sources-with-the-sql-server-import-and-export-wizard.md). Es sind separate Dokumentationsseiten für verschiedene, häufig verwendete Datenquellen verfügbar.
