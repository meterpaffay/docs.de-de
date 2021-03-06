---
title: 'Vorgehensweise: Verwenden der ChannelFactory'
description: Erfahren Sie, wie Sie eine Kanalfactory erstellen, um mehr als einen Kanal zum Zugreifen auf Dienste mit einem WCF-Client zu erstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7c87026ca4cf7c739f4615da9bc7f0272a382392
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246661"
---
# <a name="how-to-use-the-channelfactory"></a>Vorgehensweise: Verwenden der ChannelFactory
Die generische <xref:System.ServiceModel.ChannelFactory%601>-Klasse wird in komplexen Szenarien verwendet, in denen eine Kanalfactory erstellt werden muss, die zum Erstellen mehrerer Kanäle eingesetzt werden kann.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>So erstellen und verwenden Sie die ChannelFactory-Klasse  
  
1. Erstellen und Ausführen eines Windows Communication Foundation (WCF)-Dienstanbieter. Weitere Informationen finden Sie unter [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md), [Konfigurieren von Diensten](../configuring-services.md)und [Hostingdiensten](../hosting-services.md).  
  
2. Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um den Vertrag (Schnittstelle) für den Client zu generieren.  
  
3. Verwenden Sie im Clientcode die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um mehrere Endpunktlistener zu erstellen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
