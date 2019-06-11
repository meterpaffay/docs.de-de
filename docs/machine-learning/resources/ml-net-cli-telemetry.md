---
title: Erfassen von Telemetriedaten durch die ML.NET-CLI
description: Erfahren Sie mehr über die die Telemetriefeatures der ML.NET-CLI, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Erfahren Sie auch, wie Sie diese Features deaktivieren können. Außerdem finden Sie hier Links zur .NET-Lizenzvereinbarung und Informationen zur Einhaltung der DSGVO durch Microsoft.
ms.topic: conceptual
ms.date: 05/05/2019
ms.custom: ''
ms.openlocfilehash: 94c66267dfeec4b70ba4dd1fc47518eb0e01509a
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053574"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a>Erfassen von Telemetriedaten durch die ML.NET-CLI

Die [ML.NET-CLI](http://aka.ms/mlnet-cli) beinhaltet ein Telemetriefeature, das anonyme Nutzungsdaten sammelt, die für die Verwendung durch Microsoft zusammengefasst werden.

## <a name="how-microsoft-uses-the-data"></a>So verwendet Microsoft die Daten

Das Produktteam verwendet die Telemetriedaten der ML.NET-CLI, um zu verstehen, wie die Tools verbessert werden können. Wenn Kunden beispielsweise eine bestimmte Machine Learning-Aufgabe selten nutzen, untersucht das Produktteam, warum dies der Fall ist, und verwendet die Ergebnisse, um die Entwicklung von Features zu priorisieren. Telemetriedaten der ML.NET-CLI unterstützen auch das Debugging von Problemen wie Abstürze und Codeanomalien. 

Das Produktteam schätzt diese Erkenntnis, aber wir wissen auch, dass nicht jeder diese Daten weitergeben möchte. [Erfahren Sie, wie Sie die Telemetriedaten deaktivieren können.](#opt-out-of-data-collection)

## <a name="scope"></a>Bereich

Der Befehl `mlnet` startet die ML.NET-CLI, aber die Befehl selbst sammelt noch keine Telemetriedaten.

Die Telemetrie wird durch die Ausführung des Befehls `mlnet` *nicht aktiviert*, wenn kein Befehl angefügt ist. Beispiel:

- `mlnet`
- `mlnet --help`

Die Telemetrie *wird aktiviert*, wenn Sie einen [ML.NET-CLI-Befehl](../reference/ml-net-cli-reference.md) ausführen, wie `mlnet auto-train`.

## <a name="opt-out-of-data-collection"></a>Ablehnen der Datensammlung

Die Telemetriefeature der ML.NET-CLI ist standardmäßig aktiviert.

Deaktivieren Sie die Telemetriefeature, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen. Diese Umgebungsvariable gilt global für das .NET CLI-Tool.

## <a name="data-points-collected"></a>Gesammelte Datenpunkte

Die Funktion sammelt die folgenden Daten:

- Welcher Befehl aufgerufen wurde, z.B. `auto-train`
- Verwendete Befehlszeilen-Parameternamen (z.B. „dataset-name“, „label-column-name“, „ml-task“, „output-path“, „max-exploration-time“, „verbosity“)
- MAC-Adresse mit Hash: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer
- Zeitstempel eines Aufrufs
- Die aus drei Oktetten bestehende IP-Adresse (nicht die vollständige IP-Adresse), die nur zur Bestimmung des geografischen Standorts verwendet wird
- Die Namen aller verwendeter Argumente/Parameter Nicht die Kundenwerte, z.B. Zeichenfolgen
- Hash-Datasetdateiname
- Datasetdateigrößen-Bucket
- Betriebssystem und Version
- Wert des --Taskparameters: Kategoriewerte, z. B. `regression`, `binary-classification` und `multiclass-classification`
- ML.NET-CLI-Version (d.h. 0.3.27703.4)

Die Daten werden mithilfe der Technologie [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) verwendet.

### <a name="data-points-not-collected"></a>Nicht gesammelte Datenpunkte
Das Telemetriefeature sammelt *nicht*:
- persönliche Daten, z.B. Benutzernamen
- Namen der Datasetdateien
- Daten aus den Datasetdateien

Wenn Sie vermuten, dass durch die ML.NET-CLI-Telemetrie vertrauliche Daten gesammelt oder die Daten nicht sicher oder ordnungsgemäß behandelt werden, melden Sie ein Problem mit dem [ML.NET](https://github.com/dotnet/machinelearning)-Repository, damit dieses untersucht wird.

## <a name="license"></a>Lizenz

Die Microsoft-Verteilung der ML.NET-CLI ist gemäß den [Microsoft-Softwarelizenzbedingungen: Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula) lizenziert. Ausführlichere Informationen zur Datensammlung und -verarbeitung finden Sie im Abschnitt „Daten“.

## <a name="disclosure"></a>Offenlegung

Wenn Sie zum ersten Mal einen [ML.NET-CLI-Befehl](../reference/ml-net-cli-reference.md) wie `mlnet auto-train` ausführen, zeigt das ML.NET-CLI-Tool einen Text an, der Ihnen erklärt, wie Sie die Telemetrie deaktivieren können. Der Text kann abhängig von der von Ihnen ausgeführten Version der CLI leicht variieren.

## <a name="see-also"></a>Siehe auch
- [ML.NET-CLI-Referenz](../reference/ml-net-cli-reference.md)
- [Microsoft-Software-Lizenzbedingungen: Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula)
- [Datenschutz bei Microsoft](https://www.microsoft.com/trustcenter/privacy/)
- [Datenschutzerklärung von Microsoft](https://privacy.microsoft.com/privacystatement)