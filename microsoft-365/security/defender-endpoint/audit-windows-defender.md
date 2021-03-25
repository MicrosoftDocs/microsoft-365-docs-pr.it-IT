---
title: Verificare il funzionamento delle funzionalità di Microsoft Defender for Endpoint in modalità di controllo
description: La modalità di controllo ti aiuta a vedere in che modo Microsoft Defender for Endpoint proteggerebbe i dispositivi se fosse abilitato.
keywords: exploit guard, controllo, controllo, modalità, abilitato, disabilitato, test, demo, valutare, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067354"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="8fe9b-104">Verificare il funzionamento delle funzionalità di Microsoft Defender for Endpoint in modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="8fe9b-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8fe9b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8fe9b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8fe9b-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8fe9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8fe9b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fe9b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="8fe9b-108">Puoi abilitare le regole di riduzione della superficie di attacco, la protezione degli exploit, la protezione di rete e l'accesso controllato alle cartelle in modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="8fe9b-109">La modalità di controllo consente di visualizzare un record di ciò *che* sarebbe successo se fosse stata abilitata la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="8fe9b-110">È possibile abilitare la modalità di controllo durante il test del funzionamento delle funzionalità nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="8fe9b-111">In questo modo puoi assicurarti che le app line-of-business non siano interessate.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="8fe9b-112">Puoi anche avere un'idea del numero di tentativi sospetti di modifica dei file in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="8fe9b-113">Le funzionalità non bloccano o impediscono la modifica di app, script o file.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="8fe9b-114">Tuttavia, il registro eventi di Windows registrerà gli eventi come se le funzionalità fossero completamente abilitate.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="8fe9b-115">Con la modalità di controllo, è possibile esaminare il registro eventi per verificare l'impatto che la funzionalità avrebbe avuto se fosse stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="8fe9b-116">Per trovare le voci controllate, passare a **Applicazioni e** servizi  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="8fe9b-117">Puoi usare Defender for Endpoint per ottenere maggiori dettagli per ogni evento, in particolare per analizzare le regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="8fe9b-118">L'uso della console defender per endpoint consente di analizzare i problemi nell'ambito della sequenza temporale degli avvisi e [degli scenari di indagine.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="8fe9b-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="8fe9b-119">È possibile usare Criteri di gruppo, PowerShell e provider di servizi di configurazione (CSP) per abilitare la modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="8fe9b-120">Puoi anche visitare il sito Web Windows Defender Testground all'indirizzo [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) verificare che le funzionalità funzionino e vedere come funzionano.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="8fe9b-121">**Opzioni di controllo**</span><span class="sxs-lookup"><span data-stu-id="8fe9b-121">**Audit options**</span></span> | <span data-ttu-id="8fe9b-122">**Come abilitare la modalità di controllo**</span><span class="sxs-lookup"><span data-stu-id="8fe9b-122">**How to enable audit mode**</span></span> | <span data-ttu-id="8fe9b-123">**Come visualizzare gli eventi**</span><span class="sxs-lookup"><span data-stu-id="8fe9b-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="8fe9b-124">Il controllo si applica a tutti gli eventi</span><span class="sxs-lookup"><span data-stu-id="8fe9b-124">Audit applies to all events</span></span> | [<span data-ttu-id="8fe9b-125">Abilitare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="8fe9b-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="8fe9b-126">Eventi di accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="8fe9b-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="8fe9b-127">Il controllo si applica a singole regole</span><span class="sxs-lookup"><span data-stu-id="8fe9b-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="8fe9b-128">Abilitare le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8fe9b-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="8fe9b-129">Eventi delle regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8fe9b-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="8fe9b-130">Il controllo si applica a tutti gli eventi</span><span class="sxs-lookup"><span data-stu-id="8fe9b-130">Audit applies to all events</span></span> | [<span data-ttu-id="8fe9b-131">Abilitare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="8fe9b-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="8fe9b-132">Eventi di protezione di rete</span><span class="sxs-lookup"><span data-stu-id="8fe9b-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="8fe9b-133">Il controllo si applica alle singole mitigazioni</span><span class="sxs-lookup"><span data-stu-id="8fe9b-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="8fe9b-134">Abilitare la protezione da exploit</span><span class="sxs-lookup"><span data-stu-id="8fe9b-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="8fe9b-135">Eventi di protezione da exploit</span><span class="sxs-lookup"><span data-stu-id="8fe9b-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="8fe9b-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8fe9b-136">Related topics</span></span>

* [<span data-ttu-id="8fe9b-137">Proteggere i dispositivi dagli exploit</span><span class="sxs-lookup"><span data-stu-id="8fe9b-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="8fe9b-138">Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8fe9b-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="8fe9b-139">Proteggere la rete</span><span class="sxs-lookup"><span data-stu-id="8fe9b-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="8fe9b-140">Proteggere le cartelle importanti</span><span class="sxs-lookup"><span data-stu-id="8fe9b-140">Protect important folders</span></span>](controlled-folders.md)