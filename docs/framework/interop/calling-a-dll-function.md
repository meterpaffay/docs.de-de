---
title: Aufrufen einer DLL-Funktion
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 14589544e05f6c59f4f58f7723fef40e75af9823
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123721"
---
# <a name="calling-a-dll-function"></a>Aufrufen einer DLL-Funktion
Obwohl Aufrufe nicht verwalteter DLL-Funktionen nahezu identisch mit anderen Aufrufen von verwaltetem Code sind, bestehen Unterschiede, die DLL-Funktionen zuerst verwirrend erscheinen lassen. Dieser Abschnitt enthält Themen, in denen einige ungewöhnliche aufrufbezogene Probleme beschrieben werden.  
  
 Strukturen, die von Plattforminvokeaufrufen zurückgegeben werden, müssen Datentypen sein, die die gleiche Darstellung in verwaltetem und nicht verwaltetem Code haben. Solche Typen werden *blitfähige Typen* genannt, da keine Konvertierung erforderlich ist (siehe [Blitfähige und nicht blitfähige Typen](blittable-and-non-blittable-types.md)). Um eine Funktion aufzurufen, die über eine nicht blitfähige Struktur als Rückgabetyp verfügt, können Sie einen blitfähigen Hilfstyp mit derselben Größe wie der nicht blitfähige Typ definieren, und nach der Rückgabe der Funktion Daten konvertieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übergeben von Strukturen](passing-structures.md)  
 Identifiziert die Probleme der Übergabe von Datenstrukturen mit einem vordefinierten Layout.  
  
 [Rückruffunktionen](callback-functions.md)  
 Enthält grundlegende Informationen über Rückruffunktionen.  
  
 [How to: Implementieren von Rückruffunktionen](how-to-implement-callback-functions.md)  
 Beschreibt das Implementieren von Rückruffunktionen in verwaltetem Code.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verwenden nicht verwalteter DLL-Funktionen](consuming-unmanaged-dll-functions.md)  
 Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf  
  
 [Marshallen von Daten mit Plattformaufruf](marshaling-data-with-platform-invoke.md)  
 Beschreibt, wie Sie Methodenparameter deklarieren und Argumente an Funktionen übergeben, die aus nicht verwalteten Bibliotheken exportiert wurden.
