---
description: semanticsimilaritytable (Transact-SQL)
title: semanticsimilaritytable (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- semanticsimilaritytable
- semanticsimilaritytable_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- semanticsimilaritytable function
ms.assetid: b49d40ab-7552-438b-ad67-6237dcccb75b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4866c5002fce3540014b9ad0c94ccd7b20a0e235
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88397276"
---
# <a name="semanticsimilaritytable-transact-sql"></a>semanticsimilaritytable (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Gibt eine Tabelle mit keiner, einer oder mehreren Zeilen für Dokumente zurück, deren Inhalt  in den angegebenen Spalten einem angegebenen Dokument semantisch ähnlich ist.  
  
 Auf diese Rowsetfunktion kann in der FROM-Klausel einer SELECT-Anweisung wie auf einen regulären Tabellennamen verwiesen werden.  

 ![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Symbol für Themenlink") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```sql  
SEMANTICSIMILARITYTABLE  
    (  
    table,  
    { column | (column_list) | * },  
    source_key  
    )  
```  
  
##  <a name="arguments"></a><a name="Arguments"></a>Argumente  
 **Tabelle**  
 Ist der Name einer Tabelle, für die die Volltext- und die semantische Indizierung aktiviert ist.  
  
 Dieser Name kann einteilig sein oder aus bis zu vier Teilen bestehen, aber ein Remoteservername ist nicht zugelassen.  
  
 **column**  
 Name der indizierten Spalte, für die Ergebnisse zurückgegeben werden sollen. Für die Spalte muss die semantische Indizierung aktiviert sein.  
  
 **column_list**  
 Gibt mehrere durch Trennzeichen getrennte Spalten an, die in Klammern eingeschlossen sind. Für alle Spalten muss die semantische Indizierung aktiviert sein.  
  
 **\***  
 Gibt an, dass alle Spalten eingeschlossen werden, für die die semantische Indizierung aktiviert ist.  
  
 **source_key**  
 Eindeutiger Schlüssel für die Zeile, um Ergebnisse für eine bestimmte Zeile anzufordern.  
  
 Der Schlüssel wird nach Möglichkeit implizit in den Typ des eindeutigen voll Text Schlüssels in der Quell Tabelle konvertiert. Der Schlüssel kann als Konstante oder Variable angegeben werden. Er kann jedoch kein Ausdruck oder das Ergebnis einer skalaren Unterabfrage sein.  
  
## <a name="table-returned"></a>Zurückgegebene Tabelle  
 Die folgende Tabelle enthält Informationen zu ähnlichen oder verwandten Dokumenten, die diese Rowsetfunktion zurückgibt.  
  
 Passende Dokumente werden auf der Basis einzelner Spalten zurückgegeben, wenn Ergebnisse aus mehr als einer Spalte angefordert werden.  
  
|Column_name|type|Beschreibung|  
|------------------|----------|-----------------|  
|**source_column_id**|**int**|ID der Spalte, aus der ein Quelldokument zum Suchen von ähnlichen Dokumenten verwendet wurde.<br /><br /> Im Abschnitt über die COL_NAME-Funktion und COLUMNPROPERTY-Funktion finden Sie ausführliche Informationen zum Abrufen des Spaltennamens aus "column_id" und umgekehrt.|  
|**matched_column_id**|**int**|ID der Spalte, in der ein ähnliches Dokument gefunden wurde.<br /><br /> Im Abschnitt über die COL_NAME-Funktion und COLUMNPROPERTY-Funktion finden Sie ausführliche Informationen zum Abrufen des Spaltennamens aus "column_id" und umgekehrt.|  
|**matched_document_key**|**\***<br /><br /> Dieser Schlüssel stimmt mit dem Typ des eindeutigen Schlüssels in der Quelltabelle überein.|Eindeutiger Schlüsselwert für die Volltext- und semantische Extraktion des Dokuments oder der Zeile, das bzw. die Ähnlichkeit mit dem angegebenen Dokument in der Abfrage aufweist.|  
|**Endergebnis**|**Wirkliche**|Ein relativer Ähnlichkeitswert für dieses Dokument bezogen auf alle anderen ähnlichen Dokumente.<br /><br /> Der Wert ist eine Dezimalzahl im Bereich [0,0; 1,0], wobei ein höheres Ergebnis eine höhere Übereinstimmung und 1,0 ein perfektes Ergebnis darstellt.|  
  
## <a name="general-remarks"></a>Allgemeine Hinweise  
 Weitere Informationen finden Sie untersuchen von [ähnlichen und verwandten Dokumenten mit der semantischen Suche](../../relational-databases/search/find-similar-and-related-documents-with-semantic-search.md).  
  
## <a name="limitations-and-restrictions"></a>Einschränkungen  
 Ähnliche Dokumente können nicht über Spalten hinweg abgefragt werden. Die **semanticsimilaritytable** -Funktion ruft nur ähnliche Dokumente aus derselben Spalte wie die Quell Spalte ab, die durch das **source_key** -Argument identifiziert wird.  
  
## <a name="metadata"></a>Metadaten  
 Führen Sie eine Abfrage der folgenden dynamischen Verwaltungssichten durch, um Informationen, einschließlich Statusinformationen, zur semantischen Ähnlichkeitsextraktion und Auffüllung zu erhalten:  
  
-   [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql.md)  
  
-   [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql.md)  
  
## <a name="security"></a>Sicherheit  
  
### <a name="permissions"></a>Berechtigungen  
 Erfordert SELECT-Berechtigungen für die Basistabelle, für die der Volltextindex und der semantische Index erstellt wurden.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel werden die ersten 10 Kandidaten abgerufen, die einem angegebenen Kandidaten aus der HumanResources.JobCandidate-Tabelle in der AdventureWorks2012-Beispieldatenbank ähneln.  
  
```scr  
SELECT TOP(10) KEY_TBL.matched_document_key AS Candidate_ID  
FROMSEMANTICSIMILARITYTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume,  
    @CandidateID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
  
```  
  
  
