---
description: CopyRecord-Methode (ADO)
title: CopyRecord-Methode (ADO) | Microsoft-Dokumentation
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Record::raw_CopyRecord
- _Record::CopyRecord
helpviewer_keywords:
- CopyRecord method [ADO]
ms.assetid: b9bcf272-3c74-479f-95dd-0229a32e98fc
author: rothja
ms.author: jroth
ms.openlocfilehash: 0056d33f1ad07ed48002bb7638acd84a963fb566
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88974581"
---
# <a name="copyrecord-method-ado"></a>CopyRecord-Methode (ADO)
Kopiert eine durch einen [Datensatz](./record-object-ado.md) dargestellte Entität in einen anderen Speicherort.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Record.CopyRecord (Source, Destination, UserName, Password, Options, Async)  
```  
  
#### <a name="parameters"></a>Parameter  
 *Quelle*  
 Optional. Ein **Zeichen** folgen Wert, der eine URL enthält, die die zu kopierende Entität angibt (z. b. eine Datei oder ein Verzeichnis). Wenn die *Quelle* weggelassen wird oder eine leere Zeichenfolge angibt, wird die Datei oder das Verzeichnis kopiert, die durch den aktuellen [Datensatz](./record-object-ado.md) dargestellt werden.  
  
 *Ziel*  
 Optional. Ein **Zeichen** folgen Wert, der eine URL enthält, die den Speicherort angibt, an den die *Quelle* kopiert wird.  
  
 *UserName*  
 Optional. Ein **Zeichen** folgen Wert, der die Benutzer-ID enthält, die bei Bedarf den Zugriff auf das *Ziel*autorisiert.  
  
 *Kennwort*  
 Optional. Ein **Zeichen** folgen Wert, der das Kennwort enthält, das bei Bedarf den *Benutzernamen*überprüft.  
  
 *Optionen*  
 Optional. Ein [copyrecordoptionsenum](./copyrecordoptionsenum.md) -Wert, der den Standardwert **adcopyunspezifiziert**hat. Gibt das Verhalten dieser Methode an.  
  
 *Asynchron*  
 Optional. Ein **boolescher** Wert, der, wenn **true**, angibt, dass dieser Vorgang asynchron sein soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein **Zeichen** folgen Wert, der in der Regel den Wert von *Destination*zurückgibt. Der genaue zurückgegebene Wert ist jedoch vom Anbieter abhängig.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Werte von *Quelle* und *Ziel* dürfen nicht identisch sein. Andernfalls tritt ein Laufzeitfehler auf. Mindestens einer der Server-, Pfad-oder Ressourcennamen muss abweichen.  
  
 Alle untergeordneten Elemente (z. b. Unterverzeichnisse) der *Quelle* werden rekursiv kopiert, es sei denn, **adCopyNonRecursive** ist angegeben. Bei einem rekursiven Vorgang darf das *Ziel* kein Unterverzeichnis der *Quelle*sein. Andernfalls wird der Vorgang nicht beendet.  
  
 Diese Methode schlägt fehl, wenn das *Ziel* eine vorhandene Entität (z. b. eine Datei oder ein Verzeichnis) identifiziert, es sei denn, **AdCopyOverwrite** ist angegeben.  
  
> [!IMPORTANT]
>  Verwenden Sie die Option **AdCopyOverwrite** mit Bedacht. Wenn Sie diese Option beispielsweise beim Kopieren einer Datei in ein Verzeichnis angeben, wird das Verzeichnis *gelöscht* und durch die Datei ersetzt.  
  
> [!NOTE]
>  URLs, die das http-Schema verwenden, rufen automatisch den [Microsoft OLE DB-Anbieter für die Internet Veröffentlichung auf](../../guide/appendixes/microsoft-ole-db-provider-for-internet-publishing.md). Weitere Informationen finden Sie unter [absolute und relative URLs](../../guide/data/absolute-and-relative-urls.md).  
  
## <a name="applies-to"></a>Gilt für  
 [Record-Objekt (ADO)](./record-object-ado.md)