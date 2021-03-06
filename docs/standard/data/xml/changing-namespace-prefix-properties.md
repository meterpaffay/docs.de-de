---
title: Ändern der Eigenschaften von Namespacepräfixen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
ms.openlocfilehash: b817a68ff9789be414118ff4c1a3d88ca3ea9f01
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290914"
---
# <a name="changing-namespace-prefix-properties"></a>Ändern der Eigenschaften von Namespacepräfixen
Mit der **XmlNode**-Klasse können Sie das Namespacepräfix ändern, das mit einem bestimmten Knoten verknüpft ist. Im folgenden Code wird beispielsweise die Änderung des Präfixes eines Elements dargestellt.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Ausgabe**  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 Wenn Sie das Präfix eines Knotens ändern, ändert sich dessen Namespace dadurch nicht. Der Namespace kann nur bei der Erstellung des Knotens festgelegt werden. Wenn die Struktur erhalten bleiben soll, können neue Namespaceattribute nicht mit übernommen werden, damit die Anforderungen für das festgelegte Präfix erfüllt werden. Wenn der neue Namespace nicht erstellt werden kann, wird das Präfix geändert, sodass der Knoten seinen lokalen Namen und Namespace beibehält. Im folgenden Beispiel wird dargestellt, wie ein Namespaceattribut hinzugefügt wird.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Ausgabe**  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 Wenn die Struktur als Folge des Aufrufs von **doc.InnerXml** in Form einer Zeichenfolge erhalten blieb, wurde das `xmlns:a='123'`-Attribut hinzugefügt, damit der Namespace des `test`-Elements beibehalten wird. Er war `'123'` und bleibt `'123'`.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
