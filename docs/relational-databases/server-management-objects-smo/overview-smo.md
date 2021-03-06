---
description: Übersicht (SMO)
title: Übersicht (SMO) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e988f9e8-6801-41d1-8069-726f487244d5
author: markingmyname
ms.author: maghan
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: f567277dd128095222633c0694412fd477bc623b
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88455533"
---
# <a name="overview-smo"></a>Übersicht (SMO)
[!INCLUDE [SQL Server ASDB, ASDBMI, ASDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Management Objects (SMO) sind Objekte, die für die programmgesteuerte Verwaltung von entwickelt wurden [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Sie können SMO verwenden, um benutzerdefinierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verwaltungsanwendungen zu erstellen. Wenngleich [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine leistungsstarke und umfassende Anwendung zur Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist, sind Sie in manchen Fällen mit einer SMO-Anwendung möglicherweise besser beraten.  
  
 Beispielsweise müssen die Benutzeranwendungen zur Steuerung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verwaltungsaufgaben eventuell vereinfacht werden, um den Anforderungen neuer Benutzer zu entsprechen und um die Schulungskosten zu senken. Oder Sie müssen benutzerdefinierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbanken bzw. eine Anwendung zum Erstellen und Überwachen der Indexeffizienz erstellen. Eine SMO-Anwendung kann auch verwendet werden, um Hard- oder Software anderer Hersteller nahtlos in die Anwendung zur Datenbankverwaltung einzubinden.  
  
 Da SMO mit [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen kompatibel ist, können Sie mühelos eine Multiversionsumgebung verwalten.  
  
 Zu den Funktionen in SMO zählen die folgenden:  
  
-   Zwischengespeichertes Objektmodell und optimierte Objektinstanzerstellung. Objekte werden nur geladen, wenn auf sie ausdrücklich verwiesen wird. Objekteigenschaften werden beim Erstellen der Objekte nur teilweise geladen. Die übrigen Objekte und Eigenschaften werden geladen, wenn direkt auf sie verwiesen wird.  
  
-   Ausführung von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen im Batchmodus. Anweisungen werden im Batchmodus ausgeführt, um die Netzwerkleistung zu verbessern.  
  
-   Aufzeichnen von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen. Ermöglicht die Erfassung eines beliebigen Vorgangs in einem Skript. [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] verwendet diese Fähigkeit, um einen Vorgang in ein Skript aufzunehmen, anstatt ihn sofort auszuführen.  
  
-   Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Diensten mit dem WMI-Anbieter. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste können programmgesteuert gestartet, gestoppt und angehalten werden.  
  
-   Erweiterte Skripterstellung. [!INCLUDE[tsql](../../includes/tsql-md.md)]-Skripts können generiert werden, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Objekte neu zu erstellen, die Beziehungen zu anderen Objekten auf der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beschreiben.  
  
-   Verwenden eindeutiger Ressourcennamen (URNs). Ein URN ermöglicht es Ihnen, Instanzen von SMO-Objekten zu erstellen und darauf zu verweisen.  
  
 SMO stellt auch viele Funktionen und Komponenten, die in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] eingeführt wurden, als neue Objekte oder Eigenschaften dar. Zu diesen neuen Funktionen und Komponenten gehören:  
  
-   Tabellen- und Indexpartitionierung zur Speicherung der Daten über ein Partitionsschema. Weitere Informationen finden Sie unter [partitionierte Tabellen und Indizes](../../relational-databases/partitions/partitioned-tables-and-indexes.md).  
  
-   HTTP-Endpunkte zur Verwaltung von SOAP-Anforderungen. Weitere Informationen finden Sie unter [Implementieren von Endpunkten](../../relational-databases/server-management-objects-smo/tasks/implementing-endpoints.md).  
  
-   Momentaufnahmeisolation und Versionsverwaltung auf Zeilenebene für erhöhte Parallelität. Weitere Informationen finden Sie unter [Arbeiten mit der Momentaufnahmeisolation](../../relational-databases/native-client/features/working-with-snapshot-isolation.md).  
  
-   XML-Schemaauflistung, XML-Indizes und XML-Datentyp zur Überprüfung und Speicherung von XML-Daten. Weitere Informationen finden Sie unter XML-Schema Auflistungen [&#40;SQL Server&#41;](../../relational-databases/xml/xml-schema-collections-sql-server.md) und [Verwenden von XML-Schemas](../../relational-databases/server-management-objects-smo/tasks/using-xml-schemas.md).  
  
-   Momentaufnahmedatenbanken zur Erstellung schreibgeschützter Datenbankkopien.  
  
-   [!INCLUDE[ssSB](../../includes/sssb-md.md)]-Unterstützung für nachrichtenbasierte Kommunikation. Weitere Informationen finden Sie unter [SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md).  
  
-   Synonymunterstützung für mehrere Namen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbankobjekten. Weitere Informationen finden Sie unter [Synonyme &#40;Datenbank-Engine&#41;](../../relational-databases/synonyms/synonyms-database-engine.md).  
  
-   Verwaltung von Datenbank-E-Mail zur Erstellung von E-Mail-Servern, E-Mail-Profilen und E-Mail-Konten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Weitere Informationen finden Sie unter [Datenbank-E-Mail](../../relational-databases/database-mail/database-mail.md).  
  
-   Unterstützung registrierter Server zum Registrieren von Verbindungsinformationen. Weitere Informationen finden Sie unter [Registrieren von Servern](../../tools/sql-server-management-studio/register-servers.md).  
  
-   Ablaufverfolgung und Wiederholung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ereignissen. Weitere Informationen finden Sie unter [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md), [SQL](../../relational-databases/sql-trace/sql-trace.md)-Ablauf Verfolgung, [SQL Server Distributed Replay](../../tools/distributed-replay/sql-server-distributed-replay.md)und [Erweiterte Ereignisse](../../relational-databases/extended-events/extended-events.md).  
  
-   Unterstützung von Zertifikaten und Schlüsseln für die Sicherheitssteuerung. Weitere Informationen finden Sie unter [Verschlüsselungs Hierarchie](../../relational-databases/security/encryption/encryption-hierarchy.md).  
  
-   DDL-Trigger für zusätzliche Funktionalität beim Auftreten von DDL-Ereignissen. Weitere Informationen finden Sie unter [DDL Triggers](../../relational-databases/triggers/ddl-triggers.md).  
  
 Der SMO-Namespace lautet <xref:Microsoft.SqlServer.Management.Smo>. SMO wird als [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Assembly implementiert. Das bedeutet, dass die CLR (Common Language Runtime) von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], Version 2.0, installiert werden muss, bevor die SMO-Objekte verwendet werden. Die SMO-Assemblys werden standardmäßig mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-SDK-Option im globalen Assemblycache (GAC) installiert. Die Assemblys befinden sich unter "c:\Programme\Microsoft SQL server\130\sdk\assemblies\". Weitere Informationen finden Sie in der Dokumentation zu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].  
  
## <a name="smo-classes"></a>SMO-Klassen  
 SMO-Klassen umfassen zwei Kategorien: Instanzklassen und Hilfsprogrammklassen.  
  
 **Instanzklassen**  
  
 Die Instanzklassen stellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Objekte dar, z.&nbsp;B. Server, Datenbanken, Tabellen, Trigger und gespeicherte Prozeduren. Um eine Verbindung zur Instanz von <xref:Microsoft.SqlServer.Management.Common.ServerConnection> herzustellen und den Aufzeichnungsmodus für an die Instanz gesendete Befehle zu steuern, wird die Klasse [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet.  
  
 Die SMO-Instanzobjekte bilden eine Hierarchie, die die Hierarchie eines Datenbankservers darstellt. Ganz oben sind die Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], gefolgt von den Datenbanken, gefolgt von den Tabellen, Spalten, Triggern usw. Ist eine 1:n-Beziehung zwischen den über- und untergeordneten Elementen logisch, etwa im Fall einer Tabelle mit mehreren Spalten, wird das untergeordnete Element durch eine Objektauflistung dargestellt. Andernfalls wird das untergeordnete Element nur durch ein Objekt dargestellt.  
  
 **Hilfsprogrammklassen**  
  
 Hilfsprogrammklassen sind eine Gruppe von Objekten, die explizit erstellt wurden, um bestimmte Tasks auszuführen. Sie werden auf Grundlage ihrer Funktion in unterschiedliche Objekthierarchien unterteilt:  
  
-   Übertragungsklasse. Diese wird verwendet, um Schema und Daten in eine andere Datenbank zu übertragen.  
  
-   Klassen zur Sicherung und Wiederherstellung. Diese werden zum Sichern und Wiederherstellen von Datenbanken verwendet.  
  
-   Scripter-Klasse. Diese wird zum Erstellen von Skriptdateien für die erneute Generierung von Objekten und ihren Abhängigkeiten verwendet.  
  
## <a name="smo-features"></a>SMO-Features  
 **Optimierte Leistung**  
  
 Die SMO-Architektur ist im Hinblick auf den Speicher effizient, da Objekte zunächst nur teilweise instanziiert werden und vom Server nur minimale Eigenschaften Informationen angefordert werden. Die vollständige Instanziierung der Objekte wird verzögert, bis auf das Objekt explizit verwiesen wird. Ein Objekt wird vollständig instanziiert, wenn eine Eigenschaft angefordert wird, die nicht Bestandteil der zunächst abgerufenen Eigenschaftengruppe ist, oder wenn eine Methode aufgerufen wird, die eine solche Eigenschaft erfordert. Der Übergang zwischen teilweise und vollständig instanziierten Objekten erfolgt für den Benutzer transparent. Darüber hinaus werden einige Eigenschaften, die viel Arbeitsspeicher belegen, nur dann abgerufen, wenn explizit auf die Eigenschaft verwiesen wird. Ein Beispiel hierfür ist die <xref:Microsoft.SqlServer.Management.Smo.Database.Size%2A>-Eigenschaft der <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekteigenschaft. Die teilweise Instanziierung erfordert jedoch mehr Netzwerkroundtrips und stellt möglicherweise nicht die leistungseffizienteste Option für Ihre Anwendung dar.  
  
 Sie können die Instanziierung entsprechend der Systemumgebung steuern. Durch die verzögerte Instanziierung wird der von der Anwendung benötigte Arbeitsspeicher minimiert, wenngleich dadurch möglicherweise zahlreiche Serveranforderungen ausgelöst werden, wenn auf Eigenschaften verwiesen wird.  
  
 Für Instanzklassen (Objekte, die wirkliche Datenbankobjekte darstellen) sind drei Ebenen der Instanziierung möglich: minimal instanziiert (nur die erforderlichen Mindesteigenschaften werden in einem Block gelesen), teilweise instanziiert (alle Eigenschaften, die relativ viel Speicher in Anspruch nehmen, werden in einem Block gelesen) und vollständig instanziiert. Nicht instanziiert und vollständig instanziiert sind die herkömmlichen Instanziierungsstatuswerte. Die teilweise Instanziierung steigert die Effizienz, da ein teilweise instanziiertes Objekt nicht Werte für alle Objekteigenschaften enthält. Die teilweise Instanziierung ist der Standardstatus für ein Objekt, auf das nicht direkt verwiesen wird. Wird auf eine dieser Eigenschaften verwiesen, tritt ein Fehler auf, der zur vollständigen Instanziierung des Objekts auffordert.  
  
 **Aufzeichnen der Ausführung**  
  
 Die direkte Ausführung ist die übliche Methode der Ausführung. Anweisungen werden direkt an eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gesendet. Eine Alternative stellt die Aufzeichnung der Ausführung dar.  
  
 Dabei können Sie [!INCLUDE[tsql](../../includes/tsql-md.md)]-Batches aufzeichnen, die in der Regel ausgeführt würden. Auf diese Weise kann der SMO-Programmierer das Skript aufschieben, zur späteren Ausführung speichern oder dem Endbenutzer eine Vorschau bereitstellen. Beispielsweise können eine **Create Database**-, **CREATE TABLE**-und **Create Index** -Anweisung in einem Batch gesendet und dann als drei sequenzielle Schritte ausgeführt werden. Diese Funktionalität wird vom Benutzer mit dem <xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A>-Objekt gesteuert.  
  
 **WMI-Anbieter**  
  
 Die WMI-Anbieterobjekte werden von SMO umschlossen. Damit steht dem SMO-Programmierer ein einfaches Objektmodell zur Verfügung, das SMO-Klassen stark ähnelt, ohne dass dafür Kenntnisse des durch den Namespace und die Details des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI-Anbieters dargestellten Programmiermodells erforderlich sind. Mithilfe des WMI-Anbieters können Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste, Aliase und Client- und Servernetzwerkbibliotheken konfigurieren.  
  
 **Skripterstellung**  
  
 In SMO wurde die Skripterstellung verbessert und in die **Scripter** -Klasse verschoben. Die **Scripter** -Klasse kann Abhängigkeiten ermitteln, die Beziehungen zwischen Objekten verstehen und die Bearbeitung der Abhängigkeits Hierarchie ermöglichen. Das Hauptskript Objekt ist das **scripterobjekt** . Daneben gibt es mehrere unterstützende Objekte, die Abhängigkeiten behandeln und auf Fortschritts- oder Fehlerereignisse antworten.  
  
 Das **Scripter** -Objekt unterstützt die folgenden erweiterten Skript Erstellungs Optionen:  
  
-   Einfache einphasige Skripterstellung (erstellt das Skript in einem Schritt)  
  
-   Erweiterte 3-Phasen-Skripterstellung (erstellt das Skript in drei Schritten: Abhängigkeits Ermittlung, Listen Generierung, Skript Generierung)  
  
-   Bidirektionale Abhängigkeitsermittlung (ermöglicht die Ermittlung von Abhängigkeiten oder abhängigen Elementen)  
  
-   Antwort auf Fortschrittsereignisse  
  
-   Antwort auf Fehlerereignisse  
  
 **Eindeutige Ressourcennamen**  
  
 Ein Schlüsselkonzept bei der Verwendung der SMO-Objektbibliothek ist der eindeutige Ressourcenname (Unique Resource Name, URN). Die URN-Syntax ähnelt der XPath-Syntax. Die XPath-Syntax stellt einen Hierarchiepfad zur Angabe eines Objekts dar, bei dem jede Ebene Qualifizierer und Funktionen aufweist. In SMO verfügt der URN über zwei Elemente, den Pfad und die Attributbenennung mit eingeschränkter Funktionalität. Über den Pfad wird der Speicherort des Objekts angegeben, während die Attributbenennung eine gewisse Filterung erlaubt.  
  
 Ein URN-Beispiel für eine Datenbank ist  
  
```  
/Server/Database[@Name='Adventureworks2012']  
```  
  
 Der URN eines Objekts kann abgerufen werden, indem auf seine URN-Eigenschaft verwiesen wird. Das Scripter-Objekt verwendet auch URNs als Parameter, die Objekt Verweise an die-Methode des **Scripter** -Objekts übergeben. Außerdem kann ein URN für die **gezmuobject** -Methode des **Server** Objekts angegeben werden. Damit wird eine Instanz des SMO-Objekts erstellt.  
  
## <a name="sql-server-features-represented-in-smo"></a>SQL Server in SMO dargestellte Features  
 **Tabellen-und Index Partitionierung**  
  
 Mithilfe der Indextabellenpartitionierung können Sie die Spannweite von Daten in Tabellen und Indizes dateigruppenübergreifend verwalten. Diese neue Funktion wird durch SMO-Objekte dargestellt.  
  
 **Endpunkte**  
  
 SOAP- und Datenbankspiegelungs-Anforderungen werden von Endpunkten verarbeitet, die das <xref:Microsoft.SqlServer.Management.Smo.Endpoint>-Objekt verwenden.  
  
 **Momentaufnahmeisolation/Versionsverwaltung auf Zeilenebene**  
  
 Die Momentaufnahmeisolation (Zeilenebenen-Versionsverwaltung) wird durch neue <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekteigenschaften dargestellt.  
  
 **XML-Schemanamespace, XML-Indizes und XML-Datentyp**  
  
 XML-Schemanamespaces werden in SMO durch eine Auflistung von Objekten dargestellt. XML-Indizes werden in SMO durch eine **Index** Objekt Eigenschaft dargestellt.  
  
 **Erweiterte Volltextsuche**  
  
 In SMO werden neue Objekte bereitgestellt, die eine erweiterte Volltextsuche ermöglichen.  
  
 **Seitenüberprüfung**  
  
 Das <xref:Microsoft.SqlServer.Management.Smo.DatabaseOptions.PageVerify%2A>-Objekt stellt Optionen zur Überprüfung von Datenbankseiten dar.  
  
 **Momentaufnahmen**  
  
 Eine Momentaufnahmedatenbank ist eine schreibgeschützte Kopie einer bestimmten Datenbank zu einem gegebenen Zeitpunkt. Eine Momentaufnahmedatenbank kann mit der <xref:Microsoft.SqlServer.Management.Smo.Database.IsDatabaseSnapshot%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekts angegeben werden.  
  
 **Service Broker**  
  
 [!INCLUDE[ssSB](../../includes/sssb-md.md)] und seine Funktionalität werden durch eine Gruppe von Objekten dargestellt.  
  
 **Indexerweiterungen**  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Indexerweiterungen werden durch neue Eigenschaften im <xref:Microsoft.SqlServer.Management.Smo.Index>-Objekt dargestellt.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Replication Management Objects Concepts](../../relational-databases/replication/concepts/replication-management-objects-concepts.md)  
  
  
