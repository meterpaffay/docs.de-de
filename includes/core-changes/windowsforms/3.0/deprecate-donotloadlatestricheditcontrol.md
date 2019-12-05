---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643874"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="02e55-101">Kompatibilitätsswitch „Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl“ wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="02e55-101">Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="02e55-102">Der mit .NET Framework 4.7.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02e55-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="02e55-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="02e55-103">Change description</span></span>

<span data-ttu-id="02e55-104">In .NET Framework 4.6.2 und früheren Versionen wurde mit dem <xref:System.Windows.Forms.RichTextBox>-Steuerelement das Win32 RichEdit-Steuerelement v3.0 instanziiert, und bei Anwendungen für .NET Framework 4.7.1 wurde mit dem <xref:System.Windows.Forms.RichTextBox>-Steuerelement RichEdit v4.1 (in *msftedit.dll*) instanziiert.</span><span class="sxs-lookup"><span data-stu-id="02e55-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="02e55-105">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` wurde eingeführt, damit Anwendungen für .NET Framework 4.7.1 und höhere Versionen das neue RichEdit v4.1-Steuerelement abstellen und stattdessen das alte RichEdit v3-Steuerelement verwenden können.</span><span class="sxs-lookup"><span data-stu-id="02e55-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="02e55-106">In .NET Core wird der Switch `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02e55-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="02e55-107">Es werden nur neue Versionen des <xref:System.Windows.Forms.RichTextBox>-Steuerelements unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02e55-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="02e55-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="02e55-108">Version introduced</span></span>

<span data-ttu-id="02e55-109">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="02e55-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="02e55-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="02e55-110">Recommended action</span></span>

<span data-ttu-id="02e55-111">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="02e55-111">Remove the switch.</span></span> <span data-ttu-id="02e55-112">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="02e55-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="02e55-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="02e55-113">Category</span></span>

<span data-ttu-id="02e55-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02e55-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="02e55-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="02e55-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->