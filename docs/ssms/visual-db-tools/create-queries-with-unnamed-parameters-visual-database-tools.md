---
title: Erstellen von Abfragen mit unbenannten Parametern
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.openlocfilehash: 263788197ce8beda6c25287155544b40d0edb824
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "86000051"
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a>Erstellen von Abfragen mit unbenannten Parametern (Visual Database Tools)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
Sie können eine Abfrage mit einem unbenannten Parameter erstellen, indem Sie ein Fragezeichen (?) als Platzhalter für den Literalwert angeben. Der Abfrage- und Sicht-Designer weist dann einen temporären Namen zu. In der Abfrage können beliebig viele unbenannte Parameter festgelegt werden.  
  
Wenn Sie die Abfrage im Abfrage- und Sicht-Designer ausführen, wird das Dialogfeld Abfrageparameter mit dem temporären Namen angezeigt.  
  
### <a name="to-specify-an-unnamed-parameter"></a>So geben Sie einen unbenannten Parameter an  
  
1.  Fügen Sie dem [Kriterienbereich](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md)die Spalten oder Ausdrücke hinzu, nach denen gesucht werden soll. Wenn in den Abfrageergebnissen keine Suchspalten bzw. Suchausdrücke angezeigt werden sollen, entfernen Sie die entsprechenden Ausgabespalten.  
  
2.  Wechseln Sie zu der Zeile, die die Datenspalte oder den Ausdruck für die Suche enthält, und geben Sie in der Datenblattspalte **Filter** ein Fragezeichen (?) ein.  
  
    Der Abfrage- und Sicht-Designer fügt standardmäßig den Operator "=" hinzu. Sie können die Zelle jedoch so bearbeiten, dass dafür ">", "<" oder ein beliebiger anderer SQL-Vergleichsoperator eingesetzt wird.  
  
## <a name="see-also"></a>Weitere Informationen  
[Erstellen von Abfragen mit Parametern &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/query-with-parameters-visual-database-tools.md)  
  
