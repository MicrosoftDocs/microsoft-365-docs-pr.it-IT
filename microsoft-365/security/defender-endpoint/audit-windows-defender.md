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
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 06/02/2021
ms.topic: article
ms.openlocfilehash: 10351d97ba72945f929e042dc72a37724a1df291
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769606"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="abd69-104">Testare la riduzione della superficie di attacco in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="abd69-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="abd69-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="abd69-105">**Applies to:**</span></span>
- [<span data-ttu-id="abd69-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="abd69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="abd69-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abd69-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="abd69-108">Se si fa parte del team di sicurezza dell'organizzazione, è possibile configurare le funzionalità di riduzione della superficie di attacco per l'esecuzione in modalità di controllo per vedere come funzionano nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abd69-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="abd69-109">In particolare, è possibile abilitare le regole di riduzione della superficie di attacco, la protezione degli exploit, la protezione di rete e l'accesso controllato alle cartelle in modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="abd69-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="abd69-110">La modalità di controllo consente di visualizzare un record di ciò *che* sarebbe successo se fosse stata abilitata la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="abd69-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="abd69-111">È possibile abilitare la modalità di controllo durante il test del funzionamento delle funzionalità nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abd69-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="abd69-112">In questo modo puoi assicurarti che le app line-of-business non siano interessate.</span><span class="sxs-lookup"><span data-stu-id="abd69-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="abd69-113">Puoi anche avere un'idea del numero di tentativi sospetti di modifica dei file in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="abd69-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="abd69-114">Le funzionalità non bloccano o impediscono la modifica di app, script o file.</span><span class="sxs-lookup"><span data-stu-id="abd69-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="abd69-115">Tuttavia, il Windows eventi registra gli eventi come se le funzionalità fossero completamente abilitate.</span><span class="sxs-lookup"><span data-stu-id="abd69-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="abd69-116">Con la modalità di controllo, è possibile esaminare il registro eventi per verificare l'impatto che la funzionalità avrebbe avuto se fosse stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="abd69-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="abd69-117">Per trovare le voci verificate, passare a **Applicazioni** e servizi  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="abd69-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="abd69-118">Puoi usare Defender for Endpoint per ottenere maggiori dettagli per ogni evento, in particolare per analizzare le regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="abd69-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="abd69-119">L'uso della console defender per endpoint consente di analizzare i problemi nell'ambito della sequenza temporale degli avvisi e [degli scenari di indagine.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="abd69-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="abd69-120">È possibile usare Criteri di gruppo, PowerShell e provider di servizi di configurazione (CSP) per abilitare la modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="abd69-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="abd69-121">È inoltre possibile visitare il sito Windows Defender Testground all'indirizzo [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) verificare che le funzionalità funzionino e vedere come funzionano.</span><span class="sxs-lookup"><span data-stu-id="abd69-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="abd69-122">**Opzioni di controllo**</span><span class="sxs-lookup"><span data-stu-id="abd69-122">**Audit options**</span></span> | <span data-ttu-id="abd69-123">**Come abilitare la modalità di controllo**</span><span class="sxs-lookup"><span data-stu-id="abd69-123">**How to enable audit mode**</span></span> | <span data-ttu-id="abd69-124">**Come visualizzare gli eventi**</span><span class="sxs-lookup"><span data-stu-id="abd69-124">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="abd69-125">Il controllo si applica a tutti gli eventi</span><span class="sxs-lookup"><span data-stu-id="abd69-125">Audit applies to all events</span></span> | [<span data-ttu-id="abd69-126">Abilitare l’accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="abd69-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="abd69-127">Eventi di accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="abd69-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="abd69-128">Il controllo si applica a singole regole</span><span class="sxs-lookup"><span data-stu-id="abd69-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="abd69-129">Abilitare regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="abd69-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="abd69-130">Eventi delle regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="abd69-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="abd69-131">Il controllo si applica a tutti gli eventi</span><span class="sxs-lookup"><span data-stu-id="abd69-131">Audit applies to all events</span></span> | [<span data-ttu-id="abd69-132">Abilitare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="abd69-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="abd69-133">Eventi di protezione di rete</span><span class="sxs-lookup"><span data-stu-id="abd69-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="abd69-134">Il controllo si applica alle singole mitigazioni</span><span class="sxs-lookup"><span data-stu-id="abd69-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="abd69-135">Abilitare la protezione dagli exploit</span><span class="sxs-lookup"><span data-stu-id="abd69-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="abd69-136">Eventi di protezione da exploit</span><span class="sxs-lookup"><span data-stu-id="abd69-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


