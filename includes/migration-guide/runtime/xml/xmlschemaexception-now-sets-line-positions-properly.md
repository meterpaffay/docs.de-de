---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379603"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>XmlSchemaException legt Zeilenpositionen jetzt ordnungsgemäß fest

|   |   |
|---|---|
|Details|Wenn der <xref:System.Xml.Linq.LoadOptions.SetLineInfo>-Wert an die Load-Methode übergeben wird und ein Validierungsfehler auftritt, enthalten die Eigenschaften <xref:System.Xml.Schema.XmlSchemaException.LineNumber> und <xref:System.Xml.Schema.XmlSchemaException.LinePosition> jetzt Zeileninformationen.|
|Vorschlag|Ausnahmebehandlungscode, der davon ausgeht, dass <xref:System.Xml.Schema.XmlSchemaException.LineNumber> und <xref:System.Xml.Schema.XmlSchemaException.LinePosition> nicht festgelegt werden, sollte aktualisiert werden, da diese Eigenschaften jetzt ordnungsgemäß festgelegt werden kann, wenn „SetLineInfo“ beim Laden von XML verwendet wird.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
