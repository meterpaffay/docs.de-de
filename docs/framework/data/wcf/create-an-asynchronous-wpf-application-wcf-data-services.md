---
title: 'Gewusst wie: Erstellen einer asynchronen Windows Presentation Framework-Anwendung (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: 9bc1cef1f76e6e55e9cd5ed318741f8913abbaab
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569278"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Gewusst wie: Erstellen einer asynchronen Windows Presentation Framework-Anwendung (WCF Data Services)
Mit WCF Data Services können Sie Daten, die von einem Datendienst abgerufen wurden, an ein Benutzeroberflächen Element einer Windows Presentation Framework (WPF)-Anwendung binden. Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente](binding-data-to-controls-wcf-data-services.md). Sie können auch Vorgänge für den Datendienst asynchron ausführen, sodass die Anwendung während des Wartens auf eine Antwort auf eine Daten Service Request weiterhin antwortet. Anwendungen für Silverlight sind erforderlich, um asynchron auf den Datendienst zuzugreifen. Weitere Informationen finden Sie unter [asynchrone Vorgänge](asynchronous-operations-wcf-data-services.md).  
  
 In diesem Thema wird gezeigt, wie asynchron auf einen Datendienst zugegriffen wird und die Ergebnisse an Elemente einer WPF-Anwendung gebunden werden. In den Beispielen in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Clientdatendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code definiert das Fenster der WPF-Anwendung.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Beispiel  
 Die folgende Code-Behind-Seite für die XAML-Datei führt mit dem Datendienst eine asynchrone Abfrage aus und bindet die Ergebnisse an Elemente im WPF-Fenster.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
