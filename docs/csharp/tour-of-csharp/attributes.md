---
title: C#-Attribute – Überblick über C#
description: Informationen zur deklarativen Programmierung mithilfe von Attributen in C#
ms.date: 02/27/2020
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: dc5b194c22fc2746ff8b0ab3e550e560a3666bbe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159207"
---
# <a name="attributes"></a>Attribute

Typen, Member und andere Entitäten in einem C#-Programm unterstützen Modifizierer, die bestimmte Aspekte ihres Verhaltens steuern. Der Zugriff auf eine Methode wird beispielsweise mithilfe der Modifizierer `public`, `protected`, `internal` und `private` kontrolliert. C# generalisiert diese Funktionalität, indem benutzerdefinierte Typen deklarativer Informationen an eine Programmentität angefügt und zur Laufzeit abgerufen werden können. Programm geben diese zusätzlichen deklarativen Informationen durch das Definieren und Verwenden von ***Attributen*** an.

Im folgenden Beispiel wird ein `HelpAttribute`-Attribut deklariert, das in Programmentitäten platziert werden kann, um Links zur zugehörigen Dokumentation bereitzustellen.

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

Alle Attributklassen werden von der <xref:System.Attribute> Basisklasse abgeleitet, die von der Standardbibliothek bereitgestellt wird. Attribute können durch Angabe ihres Namens angewendet werden, zusammen mit beliebigen Argumenten. Diese müssen in eckigen Klammern genau vor der zugehörigen Deklaration eingefügt werden. Wenn ein Attributname auf `Attribute` endet, kann dieser Teil des Namens beim Verweis auf das Attribut weggelassen werden. Beispielsweise kann `HelpAttribute` wie folgt verwendet werden.

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

In diesem Beispiel wird `HelpAttribute` an die `Widget`-Klasse angefügt. Darüber hinaus wird der `Display`-Methode in der Klasse ein weiteres `HelpAttribute` hinzugefügt. Die öffentlichen Konstruktoren einer Attributklasse steuern die Informationen, die beim Anfügen des Attributs an eine Programmentität angegeben werden müssen. Zusätzliche Informationen können angegeben werden, indem auf öffentliche Eigenschaften mit Lese-/Schreibzugriff der Attributklasse verwiesen wird (z.B. wie der obige Verweis auf die `Topic`-Eigenschaft).

Die durch Attribute definierten Metadaten können zur Laufzeit mittels Reflektion gelesen und bearbeitet werden. Wenn mithilfe dieser Technik ein bestimmtes Attribut angefordert wird, wird der Konstruktor für die Attributklasse mit den in der Programmquelle angegebenen Informationen aufgerufen, und die resultierende Attributinstanz wird zurückgegeben. Wenn zusätzliche Informationen über Eigenschaften bereitgestellt wurden, werden diese Eigenschaften auf die vorgegebenen Werte festgelegt, bevor die Attributinstanz zurückgegeben wird.

Das folgende Codebeispiel zeigt, wie die der `Widget`-Klasse zugeordneten `HelpAttribute`-Instanzen und die dazugehörige `Display`-Methode abgerufen wird.

[!code-csharp[AttributeRead](../../../samples/snippets/csharp/tour/attributes/Program.cs#ReadAttributes)]

>[!div class="step-by-step"]
>[Zurück](delegates.md)
