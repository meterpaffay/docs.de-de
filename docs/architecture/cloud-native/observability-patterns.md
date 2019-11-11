---
title: Beobachtbarkeitsmuster
description: Observability-Muster für Native Cloud-Anwendungen
ms.date: 09/23/2019
ms.openlocfilehash: 23320144c03278d631b8a1fcc1d1c0954e907296
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841066"
---
# <a name="observability-patterns"></a><span data-ttu-id="07b38-103">Beobachtbarkeitsmuster</span><span class="sxs-lookup"><span data-stu-id="07b38-103">Observability patterns</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="07b38-104">Ebenso wie Muster entwickelt wurden, um das Layout von Code in Anwendungen zu unterstützen, gibt es auf zuverlässige Weise Muster für Betriebs Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="07b38-104">Just as patterns have been developed to aid in the layout of code in applications, there are patterns for operating applications in a reliable way.</span></span> <span data-ttu-id="07b38-105">Bei der Verwaltung von Anwendungen sind drei nützliche Muster aufgetreten: Protokollierung, Überwachung und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="07b38-105">Three useful patterns in maintaining applications have emerged: logging, monitoring, and alerts.</span></span>

## <a name="when-to-use-logging"></a><span data-ttu-id="07b38-106">Verwendungszwecke der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="07b38-106">When to use logging</span></span>

<span data-ttu-id="07b38-107">Unabhängig davon, wie sorgfältig wir sind, Verhalten sich Anwendungen fast immer auf unerwartete Weise in der Produktionsumgebung.</span><span class="sxs-lookup"><span data-stu-id="07b38-107">No matter how careful we are, applications almost always behave in unexpected ways in production.</span></span> <span data-ttu-id="07b38-108">Wenn Benutzer Probleme mit einer Anwendung melden, ist es äußerst nützlich, wenn Sie sehen können, was mit der APP passiert ist, als das Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="07b38-108">When users report problems with an application, it's extremely useful to be able to see what was going on with the app when the problem occurred.</span></span> <span data-ttu-id="07b38-109">Eine der bewährten Methoden zum Erfassen von Informationen darüber, was eine Anwendung während der Ausführung tut, besteht darin, die Anwendung zu schreiben, was Sie tut.</span><span class="sxs-lookup"><span data-stu-id="07b38-109">One of the most tried and true ways of capturing information about what an application is doing while it's running is to have the application write down what it's doing.</span></span> <span data-ttu-id="07b38-110">Dieser Prozess wird als Protokollierung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="07b38-110">This process is known as logging.</span></span> <span data-ttu-id="07b38-111">Immer wenn Ausfälle oder Probleme in der Produktion auftreten, sollte das Ziel darin bestehen, die Bedingungen, unter denen die Ausfälle aufgetreten sind, in einer nicht-Produktionsumgebung zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="07b38-111">Anytime failures or problems occur in production, the goal should be to reproduce the conditions under which the failures occurred, in a non-production environment.</span></span> <span data-ttu-id="07b38-112">Eine gute Protokollierung ist eine Roadmap für Entwickler, die Sie befolgen können, um Probleme in einer Umgebung zu duplizieren, die Sie testen und experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="07b38-112">Having good logging in place provides a roadmap for developers to follow in order to duplicate problems in an environment that can be tested and experimented with.</span></span>

### <a name="logging-in-cloud-native-applications"></a><span data-ttu-id="07b38-113">Protokollierung in Cloud-native Anwendungen</span><span class="sxs-lookup"><span data-stu-id="07b38-113">Logging in cloud-native applications</span></span>

<span data-ttu-id="07b38-114">Jede Programmiersprache verfügt über Tools, die das Schreiben von Protokollen erlauben, und in der Regel ist der Aufwand für das Schreiben dieser Protokolle gering.</span><span class="sxs-lookup"><span data-stu-id="07b38-114">Every programming language has tooling that permits writing logs, and typically the overhead for writing these logs is low.</span></span> <span data-ttu-id="07b38-115">Viele der Protokollierungs Bibliotheken ermöglichen das Protokollieren verschiedener Arten von criticalities, die zur Laufzeit optimiert werden können.</span><span class="sxs-lookup"><span data-stu-id="07b38-115">Many of the logging libraries provide logging different kinds of criticalities, which can be tuned at run time.</span></span> <span data-ttu-id="07b38-116">Die Bibliothek "serilog" ist beispielsweise eine beliebte strukturierte Protokollierungs Bibliothek für .net, die die folgenden Protokolliergrade bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="07b38-116">For instance, the Serilog library is a popular structured logging library for .NET that provides the following logging levels</span></span>

* <span data-ttu-id="07b38-117">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="07b38-117">Verbose</span></span>
* <span data-ttu-id="07b38-118">Debug</span><span class="sxs-lookup"><span data-stu-id="07b38-118">Debug</span></span>
* <span data-ttu-id="07b38-119">Information</span><span class="sxs-lookup"><span data-stu-id="07b38-119">Information</span></span>
* <span data-ttu-id="07b38-120">Warnung</span><span class="sxs-lookup"><span data-stu-id="07b38-120">Warning</span></span>
* <span data-ttu-id="07b38-121">Fehler</span><span class="sxs-lookup"><span data-stu-id="07b38-121">Error</span></span>
* <span data-ttu-id="07b38-122">FAT</span><span class="sxs-lookup"><span data-stu-id="07b38-122">Fatal</span></span>

<span data-ttu-id="07b38-123">Diese verschiedenen Protokoll Ebenen bieten Granularität bei der Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="07b38-123">These different log levels provide granularity in logging.</span></span> <span data-ttu-id="07b38-124">Wenn die Anwendung in der Produktionsumgebung ordnungsgemäß funktioniert, kann Sie so konfiguriert werden, dass nur wichtige Nachrichten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="07b38-124">When the application is functioning properly in production, it may be configured to only log important messages.</span></span> <span data-ttu-id="07b38-125">Wenn sich die Anwendung nicht verhält, kann die Protokollebene erweitert werden, sodass ausführlichere Protokolle gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="07b38-125">When the application is misbehaving, then the log level can be increased so more verbose logs are gathered.</span></span> <span data-ttu-id="07b38-126">Dadurch wird die Leistung gegenüber dem einfachen Debuggen ausgeglichen.</span><span class="sxs-lookup"><span data-stu-id="07b38-126">This balances performance against ease of debugging.</span></span>

<span data-ttu-id="07b38-127">Dank der hohen Leistung der Protokollierungs Tools und der Anpassbarkeit der Ausführlichkeit sollten Entwickler sich häufig anmelden.</span><span class="sxs-lookup"><span data-stu-id="07b38-127">The high performance of logging tools and the tunability of verbosity should encourage developers to log frequently.</span></span> <span data-ttu-id="07b38-128">Viele bevorzugen ein Muster für das Protokollieren des Eintrags und Beendigungs der einzelnen Methoden.</span><span class="sxs-lookup"><span data-stu-id="07b38-128">Many favor a pattern of logging the entry and exit of each method.</span></span> <span data-ttu-id="07b38-129">Diese Vorgehensweise mag wie bei Overkill klingen, aber es ist selten, dass Entwickler weniger protokollieren möchten.</span><span class="sxs-lookup"><span data-stu-id="07b38-129">This approach may sound like overkill, but it's infrequent that developers will wish for less logging.</span></span> <span data-ttu-id="07b38-130">Tatsächlich ist es nicht ungewöhnlich, bereit Stellungen ausschließlich für das Hinzufügen von Protokollierung um eine problematische Methode auszuführen.</span><span class="sxs-lookup"><span data-stu-id="07b38-130">In fact, it's not uncommon to perform deployments for the sole purpose of adding logging around a problematic method.</span></span> <span data-ttu-id="07b38-131">Irren Sie sich auf der Seite der zu großen Protokollierung, nicht auf zu wenig.</span><span class="sxs-lookup"><span data-stu-id="07b38-131">Err on the side of too much logging and not on too little.</span></span> <span data-ttu-id="07b38-132">Beachten Sie, dass einige Tools verwendet werden können, um diese Art der Protokollierung automatisch bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="07b38-132">Note that some tools can be used to automatically provide this kind of logging.</span></span>

<span data-ttu-id="07b38-133">In herkömmlichen Anwendungen wurden Protokolldateien in der Regel auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="07b38-133">In traditional applications, log files were typically stored on the local machine.</span></span> <span data-ttu-id="07b38-134">Tatsächlich gibt es auf Unix-ähnlichen Betriebssystemen eine Ordnerstruktur, die für alle Protokolle definiert ist, in der Regel unter `/var/log`.</span><span class="sxs-lookup"><span data-stu-id="07b38-134">In fact, on Unix-like operating systems, there's a folder structure defined to hold any logs, typically under `/var/log`.</span></span> <span data-ttu-id="07b38-135">Die Nützlichkeit der Protokollierung in einer Flatfile auf einem einzelnen Computer wird in einer cloudumgebung erheblich reduziert.</span><span class="sxs-lookup"><span data-stu-id="07b38-135">The usefulness of logging to a flat file on a single machine is vastly reduced in a cloud environment.</span></span> <span data-ttu-id="07b38-136">Anwendungen, die Protokolle erstellen, haben möglicherweise keinen Zugriff auf den lokalen Datenträger, oder der lokale Datenträger ist möglicherweise sehr vorübergehend, da Container durch physische Computer gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="07b38-136">Applications producing logs may not have access to the local disk or the local disk may be highly transient as containers are shuffled around physical machines.</span></span>

<span data-ttu-id="07b38-137">Cloud native-Anwendungen, die mit einer microservicearchitektur entwickelt wurden, stellen auch einige Herausforderungen bei dateibasierten Protokollierungen dar.</span><span class="sxs-lookup"><span data-stu-id="07b38-137">Cloud-native applications developed using a microservices architecture also pose some challenges for file-based loggers.</span></span> <span data-ttu-id="07b38-138">Benutzer Anforderungen können sich nun über mehrere Dienste erstrecken, die auf unterschiedlichen Computern ausgeführt werden und Server lose Funktionen enthalten, die keinen Zugriff auf ein lokales Dateisystem haben.</span><span class="sxs-lookup"><span data-stu-id="07b38-138">User requests may now span multiple services that are run on different machines, and may include serverless functions with no access to a local file system at all.</span></span> <span data-ttu-id="07b38-139">Es wäre sehr schwierig, die Protokolle von einem Benutzer oder einer Sitzung über diese vielen Dienste und Computer hinweg zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="07b38-139">It would be very challenging to correlate the logs from a user or a session across these many services and machines.</span></span>

<span data-ttu-id="07b38-140">Zum Schluss ist die Anzahl der Benutzer in einigen cloudbasierten Anwendungen hoch.</span><span class="sxs-lookup"><span data-stu-id="07b38-140">Finally, the number of users in some cloud-native applications is high.</span></span> <span data-ttu-id="07b38-141">Stellen Sie sich vor, dass jeder Benutzer bei der Anmeldung bei einer Anwendung hundert Zeilen mit Protokollnachrichten generiert.</span><span class="sxs-lookup"><span data-stu-id="07b38-141">Imagine that each user generates a hundred lines of log messages when they log into an application.</span></span> <span data-ttu-id="07b38-142">In der Isolation ist das zwar verwaltbar, aber es werden mehr als 100.000 Benutzer multipliziert, und die Menge der Protokolle wird zu groß.</span><span class="sxs-lookup"><span data-stu-id="07b38-142">In isolation, that is manageable, but multiply that over 100,000 users and the volume of logs becomes large.</span></span>

<span data-ttu-id="07b38-143">Glücklicherweise gibt es einige fantastische Alternativen zur Verwendung der Dateisystem basierten Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="07b38-143">Fortunately, there are some fantastic alternatives to using file system-based logging.</span></span> <span data-ttu-id="07b38-144">Ein zentralisierter Protokollserver, an den alle Protokolle gesendet werden, behebt alle diese Probleme.</span><span class="sxs-lookup"><span data-stu-id="07b38-144">A centralized log server to which all logs are sent, fixes all these problems.</span></span> <span data-ttu-id="07b38-145">Protokolle werden von den Anwendungen gesammelt und an eine zentrale Protokollierungs Anwendung geliefert, die die Protokolle indiziert und speichert.</span><span class="sxs-lookup"><span data-stu-id="07b38-145">Logs are collected by the applications and shipped to a central logging application which indexes and stores the logs.</span></span> <span data-ttu-id="07b38-146">Diese System Klasse kann täglich zehn Gigabyte an Protokollen erfassen.</span><span class="sxs-lookup"><span data-stu-id="07b38-146">This class of system can ingest tens of gigabytes of logs every day.</span></span>

<span data-ttu-id="07b38-147">Es ist auch hilfreich, einige Standardverfahren zu befolgen, wenn Sie die Protokollierung entwickeln, die viele Dienste umfasst.</span><span class="sxs-lookup"><span data-stu-id="07b38-147">It's also helpful to follow some standard practices when building logging that spans many services.</span></span> <span data-ttu-id="07b38-148">Wenn Sie beispielsweise eine [Korrelations-ID](https://blog.rapid7.com/2016/12/23/the-value-of-correlation-ids/) zu Beginn einer langen Interaktion erstellen und diese dann in jeder Nachricht protokollieren, die mit dieser Interaktion verknüpft ist, ist es einfacher, nach allen zugehörigen Nachrichten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="07b38-148">For instance, generating a [correlation ID](https://blog.rapid7.com/2016/12/23/the-value-of-correlation-ids/) at the start of a lengthy interaction, and then logging it in each message that is related to that interaction, makes it easier to search for all related messages.</span></span> <span data-ttu-id="07b38-149">Sie müssen nur eine einzelne Nachricht suchen und die Korrelations-ID extrahieren, um alle zugehörigen Nachrichten zu finden.</span><span class="sxs-lookup"><span data-stu-id="07b38-149">One need only find a single message and extract the correlation ID to find all the related messages.</span></span> <span data-ttu-id="07b38-150">Ein weiteres Beispiel ist die Sicherstellung, dass das Protokoll Format für jeden Dienst identisch ist, und zwar ungeachtet der verwendeten Sprache oder Protokollierungs Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="07b38-150">Another example is ensuring that the log format is the same for every service, whatever the language or logging library it uses.</span></span> <span data-ttu-id="07b38-151">Diese Standardisierung erleichtert das Lesen von Protokollen.</span><span class="sxs-lookup"><span data-stu-id="07b38-151">This standardization makes reading logs much easier.</span></span> <span data-ttu-id="07b38-152">In Abbildung 7-1 wird veranschaulicht, wie eine microservicesarchitektur die zentralisierte Protokollierung als Teil des Workflows nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="07b38-152">Figure 7-1 demonstrates how a microservices architecture can leverage centralized logging as part of its workflow.</span></span>

<span data-ttu-id="07b38-153">![Protokolle aus verschiedenen Quellen werden in einen zentralisierten Protokoll Speicher aufgenommen.](./media/centralized-logging.png)
**Abbildung 7-1**.</span><span class="sxs-lookup"><span data-stu-id="07b38-153">![Logs from various sources are ingested into a centralized log store.](./media/centralized-logging.png)
**Figure 7-1**.</span></span> <span data-ttu-id="07b38-154">Protokolle aus verschiedenen Quellen werden in einen zentralisierten Protokoll Speicher aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="07b38-154">Logs from various sources are ingested into a centralized log store.</span></span>

## <a name="when-to-use-monitoring"></a><span data-ttu-id="07b38-155">Verwendungszwecke der Überwachung</span><span class="sxs-lookup"><span data-stu-id="07b38-155">When to use monitoring</span></span>

<span data-ttu-id="07b38-156">Einige Anwendungen sind nicht Unternehmens kritisch.</span><span class="sxs-lookup"><span data-stu-id="07b38-156">Some applications aren't mission-critical.</span></span> <span data-ttu-id="07b38-157">Vielleicht werden Sie nur intern verwendet, und wenn ein Problem auftritt, kann der Benutzer das verantwortliche Team kontaktieren, und die Anwendung kann neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="07b38-157">Maybe they're only used internally, and when a problem occurs, the user can contact the team responsible and the application can be restarted.</span></span> <span data-ttu-id="07b38-158">Kunden haben jedoch häufig höhere Erwartungen an die Anwendungen, die Sie nutzen.</span><span class="sxs-lookup"><span data-stu-id="07b38-158">However, customers often have higher expectations for the applications they consume.</span></span> <span data-ttu-id="07b38-159">Wenn Sie wissen müssen, wann Probleme mit Ihrer Anwendung auftreten, *bevor* Benutzer dies tun, oder bevor Sie von Benutzern benachrichtigt werden, müssen Sie den aktuellen Status überwachen.</span><span class="sxs-lookup"><span data-stu-id="07b38-159">If you need to know when problems occur with your application *before* users do, or before users notify you, you need to monitor its current state.</span></span> <span data-ttu-id="07b38-160">Wenn Sie ordnungsgemäß implementiert haben, können Sie über die Überwachung über Bedingungen informiert werden, die zu Problemen führen, sodass Sie die zugrunde liegenden Bedingungen lösen können, bevor Sie zu Benutzer Auswirkungen führen.</span><span class="sxs-lookup"><span data-stu-id="07b38-160">Implemented properly, monitoring can let you know about conditions that will lead to problems, letting you address underlying conditions before they result in any user impact.</span></span>

## <a name="monitoring-considerations"></a><span data-ttu-id="07b38-161">Überlegungen zur Überwachung</span><span class="sxs-lookup"><span data-stu-id="07b38-161">Monitoring considerations</span></span>

<span data-ttu-id="07b38-162">Einige zentralisierte Protokollierungs Systeme erfordern eine zusätzliche Rolle beim Sammeln von Telemetriedaten außerhalb von reinen Protokollen.</span><span class="sxs-lookup"><span data-stu-id="07b38-162">Some centralized logging systems take on an additional role of collecting telemetry outside of pure logs.</span></span> <span data-ttu-id="07b38-163">Sie können Metriken erfassen, wie z. b. Zeit zum Ausführen einer Datenbankabfrage, durchschnittliche Reaktionszeit eines Webservers und sogar CPU-Auslastung durch Mittelwerte und Arbeitsspeicher Auslastung, wie vom Betriebssystem gemeldet.</span><span class="sxs-lookup"><span data-stu-id="07b38-163">They can collect metrics, such as time to run a database query, average response time from a web server, and even CPU load averages and memory pressure as reported by the operating system.</span></span> <span data-ttu-id="07b38-164">In Verbindung mit den Protokollen können diese Systeme eine ganzheitliche Ansicht der Integrität der Knoten im System und der Anwendung als Ganzes bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="07b38-164">In conjunction with the logs, these systems can provide a holistic view of the health of nodes in the system and the application as a whole.</span></span>

<span data-ttu-id="07b38-165">Die metriksammungsfunktionen der Überwachungstools können auch manuell in der Anwendung erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="07b38-165">The metric gathering capabilities of the monitoring tools can also be fed manually from within the application.</span></span> <span data-ttu-id="07b38-166">Geschäftliche Abläufe, die von besonderem Interesse sind, wie z. b. neue Benutzer, die sich registrieren oder Aufträge platzieren, können so instrumentiert werden, dass Sie einen Gegenstand im zentralen Überwachungssystem erhöhen.</span><span class="sxs-lookup"><span data-stu-id="07b38-166">Business flows that are of particular interest such as new users signing up or orders being placed, may be instrumented such that they increment a counter in the central monitoring system.</span></span> <span data-ttu-id="07b38-167">Dadurch werden die Überwachungstools entsperrt, um nicht nur die Integrität der Anwendung, sondern die Integrität des Unternehmens zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="07b38-167">This unlocks the monitoring tools to not only monitor the health of the application but the health of the business.</span></span>

<span data-ttu-id="07b38-168">Abfragen können in den Protokoll Aggregations Tools erstellt werden, um nach bestimmten Statistiken oder Mustern zu suchen, die dann in grafischer Form auf benutzerdefinierten Dashboards angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="07b38-168">Queries can be constructed in the log aggregation tools to look for certain statistics or patterns, which can then be displayed in graphical form, on custom dashboards.</span></span> <span data-ttu-id="07b38-169">Häufig investieren Teams in große, an der Wand eingebundene anzeigen, die sich durch die Statistiken für eine Anwendung drehen.</span><span class="sxs-lookup"><span data-stu-id="07b38-169">Frequently, teams will invest in large, wall-mounted displays that rotate through the statistics related to an application.</span></span> <span data-ttu-id="07b38-170">Auf diese Weise ist es einfach, die Probleme zu erkennen, sobald sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="07b38-170">This way, it's simple to see the problems as they occur.</span></span>

## <a name="when-to-use-alerts"></a><span data-ttu-id="07b38-171">Verwendungszwecke von Warnungen</span><span class="sxs-lookup"><span data-stu-id="07b38-171">When to use alerts</span></span>

<span data-ttu-id="07b38-172">Wenn Sie auf Probleme mit Ihrer Anwendung reagieren müssen, benötigen Sie eine Möglichkeit, die richtigen Mitarbeiter zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="07b38-172">If you need to react to problems with your application, you need some way to alert the right personnel.</span></span> <span data-ttu-id="07b38-173">Dies ist das dritte in der Cloud Native Anwendungs Wahrnehmbarkeit-Muster, das von der Protokollierung und Überwachung abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="07b38-173">This is the third cloud-native application observability pattern, and depends on logging and monitoring.</span></span> <span data-ttu-id="07b38-174">Die Anwendung muss über eine Protokollierung verfügen, damit Probleme diagnostiziert werden können, und in einigen Fällen müssen Sie in die Überwachungstools einfließen.</span><span class="sxs-lookup"><span data-stu-id="07b38-174">Your application needs to have logging in place to allow problems to be diagnosed, and in some cases to feed into monitoring tools.</span></span> <span data-ttu-id="07b38-175">Es muss überwacht werden, um anwendungsmetriken und Integritäts Daten an einem Ort zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="07b38-175">It needs monitoring to aggregate application metrics and health data in one place.</span></span> <span data-ttu-id="07b38-176">Nachdem dies festgelegt wurde, können Regeln erstellt werden, mit denen Warnungen ausgelöst werden, wenn bestimmte Metriken außerhalb der zulässigen Werte liegen.</span><span class="sxs-lookup"><span data-stu-id="07b38-176">Once this has been established, rules can be created that will trigger alerts when certain metrics fall outside of acceptable levels.</span></span>

## <a name="alerts"></a><span data-ttu-id="07b38-177">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="07b38-177">Alerts</span></span>

<span data-ttu-id="07b38-178">Sie können Abfragen für die Überwachungstools erstellen, um nach bekannten Fehlerbedingungen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="07b38-178">You can craft queries against the monitoring tools to look for known failure conditions.</span></span> <span data-ttu-id="07b38-179">Abfragen können beispielsweise die eingehenden Protokolle nach Hinweisen zum HTTP-Statuscode 500 durchsuchen, was auf ein Problem auf einem Webserver hinweist.</span><span class="sxs-lookup"><span data-stu-id="07b38-179">For instance, queries could search through the incoming logs for indications of HTTP status code 500, which indicates a problem on a web server.</span></span> <span data-ttu-id="07b38-180">Sobald eine dieser Informationen erkannt wird, könnte eine e-Mail oder eine SMS an den Besitzer des Ursprungs dienstanders gesendet werden, der mit der Untersuchung beginnen kann.</span><span class="sxs-lookup"><span data-stu-id="07b38-180">As soon as one of these is detected, then an e-mail or an SMS could be sent to the owner of the originating service who can begin to investigate.</span></span>

<span data-ttu-id="07b38-181">In der Regel reicht ein einzelner 500-Fehler nicht aus, um zu ermitteln, dass ein Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="07b38-181">Typically though, a single 500 error isn't sufficient to determine that a problem has occurred.</span></span> <span data-ttu-id="07b38-182">Dies könnte bedeuten, dass ein Benutzer sein Kennwort falsch eingegeben oder falsch formatierte Daten eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="07b38-182">It could mean that a user mistyped their password or entered some malformed data.</span></span> <span data-ttu-id="07b38-183">Die Warnungs Abfragen können so gestaltet werden, dass Sie nur ausgelöst werden, wenn eine höhere Anzahl von 500 Fehlern erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="07b38-183">The alert queries can be crafted to only fire when a larger than average number of 500 errors are detected.</span></span>

<span data-ttu-id="07b38-184">Eines der schädlichsten Muster bei der Warnung ist, dass zu viele Warnungen ausgelöst werden, damit die Menschen untersucht werden können.</span><span class="sxs-lookup"><span data-stu-id="07b38-184">One of the most damaging patterns in alerting is to fire too many alerts for humans to investigate.</span></span> <span data-ttu-id="07b38-185">Dienst Besitzer werden schnell zu Fehlern, die Sie zuvor untersucht haben und als harmlos eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="07b38-185">Service owners will rapidly become desensitized to errors that they've previously investigated and found to be benign.</span></span> <span data-ttu-id="07b38-186">Wenn echte Fehler auftreten, gehen Sie beim Rauschen von Hunderten falsch positiven Ergebnissen verloren.</span><span class="sxs-lookup"><span data-stu-id="07b38-186">When true errors occur then they'll be lost in the noise of hundreds of false positives.</span></span> <span data-ttu-id="07b38-187">Das Gleichnis der Person [, die Wolf ausgerufen](https://en.wikipedia.org/wiki/The_Boy_Who_Cried_Wolf) hat, wird häufig untergeordneten Elementen mitgeteilt, dass Sie von dieser großen Gefahr gewarnt werden.</span><span class="sxs-lookup"><span data-stu-id="07b38-187">The parable of the [Boy Who Cried Wolf](https://en.wikipedia.org/wiki/The_Boy_Who_Cried_Wolf) is frequently told to children to warn them of this very danger.</span></span> <span data-ttu-id="07b38-188">Es ist wichtig sicherzustellen, dass die Warnungen, die ausgelöst werden, auf ein echtes Problem hindeuten.</span><span class="sxs-lookup"><span data-stu-id="07b38-188">It's important to ensure that the alerts that do fire are indicative of a real problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="07b38-189">[Zurück](monitoring-health.md)
>[Weiter](logging-with-elastic-stack.md)</span><span class="sxs-lookup"><span data-stu-id="07b38-189">[Previous](monitoring-health.md)
[Next](logging-with-elastic-stack.md)</span></span>