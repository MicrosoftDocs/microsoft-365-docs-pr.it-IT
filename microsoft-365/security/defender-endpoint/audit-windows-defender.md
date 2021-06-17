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
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985097"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f15ac-104">Testare la riduzione della superficie di attacco in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f15ac-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f15ac-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f15ac-105">**Applies to:**</span></span>

- [<span data-ttu-id="f15ac-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f15ac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f15ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f15ac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f15ac-108">Come parte del team di sicurezza dell'organizzazione, puoi configurare le funzionalità di riduzione della superficie di attacco per l'esecuzione in modalità di controllo per vedere come funzionano.</span><span class="sxs-lookup"><span data-stu-id="f15ac-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="f15ac-109">In modalità di controllo puoi abilitare:</span><span class="sxs-lookup"><span data-stu-id="f15ac-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="f15ac-110">Regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="f15ac-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="f15ac-111">Protezione dagli exploit</span><span class="sxs-lookup"><span data-stu-id="f15ac-111">Exploit protection</span></span>
- <span data-ttu-id="f15ac-112">Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="f15ac-112">Network protection</span></span>
- <span data-ttu-id="f15ac-113">E l'accesso controllato alle cartelle in modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="f15ac-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="f15ac-114">La modalità di controllo consente di visualizzare un record di ciò *che* sarebbe successo se fosse stata abilitata la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f15ac-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="f15ac-115">Puoi abilitare la modalità di controllo durante il test del funzionamento delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f15ac-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="f15ac-116">In questo modo puoi assicurarti che le app line-of-business non siano interessate.</span><span class="sxs-lookup"><span data-stu-id="f15ac-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="f15ac-117">Puoi anche avere un'idea del numero di tentativi sospetti di modifica dei file in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="f15ac-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="f15ac-118">Le funzionalità non bloccano o impediscono la modifica di app, script o file.</span><span class="sxs-lookup"><span data-stu-id="f15ac-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="f15ac-119">Tuttavia, il Windows eventi registra gli eventi come se le funzionalità fossero completamente abilitate.</span><span class="sxs-lookup"><span data-stu-id="f15ac-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="f15ac-120">Con la modalità di controllo, è possibile esaminare il registro eventi per vedere quali effetti avrebbe avuto la funzionalità se fosse stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="f15ac-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="f15ac-121">Per trovare le voci verificate, passare a **Applicazioni** e servizi  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="f15ac-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="f15ac-122">Usa Defender for Endpoint per ottenere maggiori dettagli per ogni evento, in particolare per analizzare le regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="f15ac-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="f15ac-123">L'uso della console defender per endpoint consente di analizzare i problemi nell'ambito della sequenza temporale degli avvisi e [degli scenari di indagine.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f15ac-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="f15ac-124">Puoi abilitare la modalità di controllo usando Criteri di gruppo, PowerShell e provider di servizi di configurazione (CSP).</span><span class="sxs-lookup"><span data-stu-id="f15ac-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="f15ac-125">È inoltre possibile visitare il sito Windows Defender Testground all'indirizzo [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) verificare che le funzionalità funzionino e vedere come funzionano.</span><span class="sxs-lookup"><span data-stu-id="f15ac-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="f15ac-126">Opzioni di controllo</span><span class="sxs-lookup"><span data-stu-id="f15ac-126">Audit options</span></span> | <span data-ttu-id="f15ac-127">Come abilitare la modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="f15ac-127">How to enable audit mode</span></span> | <span data-ttu-id="f15ac-128">Come visualizzare gli eventi</span><span class="sxs-lookup"><span data-stu-id="f15ac-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="f15ac-129">Il controllo si applica a tutti gli eventi</span><span class="sxs-lookup"><span data-stu-id="f15ac-129">Audit applies to all events</span></span> | [<span data-ttu-id="f15ac-130">Abilitare l’accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="f15ac-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="f15ac-131">Eventi di accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="f15ac-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="f15ac-132">Il controllo si applica a singole regole</span><span class="sxs-lookup"><span data-stu-id="f15ac-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="f15ac-133">Abilitare regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="f15ac-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="f15ac-134">Eventi delle regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="f15ac-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="f15ac-135">Il controllo si applica a tutti gli eventi</span><span class="sxs-lookup"><span data-stu-id="f15ac-135">Audit applies to all events</span></span> | [<span data-ttu-id="f15ac-136">Abilitare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="f15ac-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="f15ac-137">Eventi di protezione di rete</span><span class="sxs-lookup"><span data-stu-id="f15ac-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="f15ac-138">Il controllo si applica alle singole mitigazioni</span><span class="sxs-lookup"><span data-stu-id="f15ac-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="f15ac-139">Abilitare la protezione dagli exploit</span><span class="sxs-lookup"><span data-stu-id="f15ac-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="f15ac-140">Eventi di protezione da exploit</span><span class="sxs-lookup"><span data-stu-id="f15ac-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
