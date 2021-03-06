---
title: Entwurfsrichtlinien für Member
description: Lernen Sie die Entwurfs Richtlinien für Member in .net kennen. Zu den Membern zählen Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: a1f0c1d74e8bffa7cfef975c7dafb9fd01479470
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594490"
---
# <a name="member-design-guidelines"></a>Entwurfsrichtlinien für Member
Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder werden zusammen als Member bezeichnet. Member sind letztendlich die Mittel, mit denen Frameworkfunktionen den Endbenutzern eines Frameworks zur Verfügung gestellt werden.  
  
 Mitglieder können virtuell oder nicht virtuell, konkret oder abstrakt, statisch oder eine Instanz sein und mehrere verschiedene Bereiche der Barrierefreiheit haben. Diese ganze Zahl bietet eine unglaubliche Ausdruckskraft, aber gleichzeitig muss der Teil des frameworkdesigners berücksichtigt werden.  
  
 Dieses Kapitel enthält grundlegende Richtlinien, die beim Entwerfen von Membern eines beliebigen Typs befolgt werden sollten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Element Überladung](member-overloading.md)  
 [Eigenschafts Entwurf](property.md)  
 [Konstruktorentwurf](constructor.md)  
 [Ereignis Entwurf](event.md)  
 [Feld Entwurf](field.md)  
 [Erweiterungsmethoden](extension-methods.md)  
 [Operator Überladungen](operator-overloads.md)  
 [Parameter Entwurf](parameter-design.md)  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Weitere Informationen

- [Framework-Entwurfs Richtlinien](index.md)
