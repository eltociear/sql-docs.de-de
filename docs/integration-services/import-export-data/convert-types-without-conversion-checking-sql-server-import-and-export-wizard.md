---
description: Konvertieren von Typen ohne Konvertierungsprüfung (SQL Server-Import/Export-Assistent)
title: Konvertieren von Typen ohne Konvertierungsprüfung (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/11/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.impexpwizard.nomappingfile.f1
ms.assetid: 87d9d3e5-477f-4117-a37f-bff53ea3e14d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d7c53d4117d7634b6651069260c289657f82315
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88391466"
---
# <a name="convert-types-without-conversion-checking-sql-server-import-and-export-wizard"></a>Konvertieren von Typen ohne Konvertierungsprüfung (SQL Server-Import/Export-Assistent)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Nachdem Sie die vorhandenen Tabellen und Ansichten ausgewählt haben, um die von Ihnen angegebene Abfrage zu kopieren oder zu überprüfen, wird im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Import/Export-Assistent ggf. **Typen ohne Konvertierungsprüfung konvertieren**angezeigt. Der Assistent zeigt diese Seite an, wenn er mindestens eine der Datentypkonvertierungs- und Zuordnungsdateien nicht finden kann, die er benötigt, um Datentypen zwischen Ihrer Quelle und dem Ziel zuzuordnen. Die Seite enthält Informationen, die Ihnen hilft zu verstehen, was fehlt.
  
 Klicken Sie auf **Weiter** , um den Vorgang fortzusetzen, ohne zu wissen, ob Datentypkonvertierungen erfolgreich sein werden. Klicken Sie andernfalls auf **Zurück** , um Ihre Auswahl zu ändern, oder auf **Abbrechen** , um den Assistenten zu beenden.

## <a name="screen-shot-of-the-convert-types-page"></a>Screenshot der Seite „Konvertieren von Typen“  
  
Die folgende Abbildung zeigt ein Beispiel der Seite **Typen ohne Konvertierungsprüfung konvertieren** des Assistenten.

![Konvertieren von Typen](../../integration-services/import-export-data/media/convert-types.png)

Das Problem hier ist, dass der Assistent keine Zuordnungsdatei finden kann, die Datentypen für das von Ihnen ausgewählte Ziel zuordnet.

Die Informationen auf dieser Seite enthalten nicht den Namen der fehlenden Zuordnungsdatei. Da der Assistent nicht weiß, ob eine Datei für den angegebenen Datenanbieter vorhanden ist, kann er keinen Namen für die fehlende Datei bereitstellen.

## <a name="whats-next"></a>Nächste Schritte  
 Nachdem Sie auf **Weiter** geklickt haben, um dem Fortsetzen des Vorgangs zuzustimmen, ohne zu wissen, ob Datentypkonvertierungen erfolgreich sind, lautet die nächste Seite **Paket speichern und ausführen**. Auf dieser Seite geben Sie an, ob der Kopiervorgang sofort ausgeführt werden soll. Abhängig von Ihrer Konfiguration können Sie möglicherweise auch das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket speichern, das der Assistent erstellt hat, um es anzupassen und später wiederzuverwenden. Weitere Informationen finden Sie unter [Paket speichern und ausführen](../../integration-services/import-export-data/save-and-run-package-sql-server-import-and-export-wizard.md).  

## <a name="see-also"></a>Siehe auch
[Zuordnung von Datentypen mit dem SQL Server-Import/Export-Assistenten](../../integration-services/import-export-data/data-type-mapping-in-the-sql-server-import-and-export-wizard.md)
