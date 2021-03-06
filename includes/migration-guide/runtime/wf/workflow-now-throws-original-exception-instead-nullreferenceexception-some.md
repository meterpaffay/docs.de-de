---
ms.openlocfilehash: 470fc2ddcfbb29a677cadb6e7e1d2e55784d7ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802509"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>Der Workflow löst jetzt anstelle einer NullReferenceException teilweise eine ursprüngliche Ausnahme aus

|   |   |
|---|---|
|Details|In .NET Framework 4.6.2 und früheren Versionen löst die System.Activities-Workflowruntime eine <code>null</code> aus, wenn die Execute-Methode einer Workflowaktivität eine Ausnahme mit einem <xref:System.Exception.Message>-Wert für die <xref:System.NullReferenceException?displayProperty=name>-Eigenschaft auslöst, wodurch die ursprüngliche Ausnahme maskiert wird. In .NET Framework 4.7 wird die zuvor maskierte Ausnahme ausgelöst.|
|Vorschlag|Wenn Ihr Code von der Verarbeitung von <xref:System.NullReferenceException?displayProperty=name> abhängig ist, ändern Sie diesen, um die Ausnahmen zu erfassen, die Ihre benutzerdefinierten Aktivitäten auslösen könnten.|
|`Scope`|Nebenversion|
|Version|4.7|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
