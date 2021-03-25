---
title: Valutare le regole di riduzione della superficie di attacco
description: Scopri come la riduzione della superficie di attacco potrebbe bloccare e impedire gli attacchi con lo strumento demo personalizzato.
keywords: Riduzione della superficie di attacco, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, valutare, testare, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 13b1ac5f71f2bc24ad6f52af6722e12fab935270
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067794"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="62d7d-104">Valutare le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="62d7d-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="62d7d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="62d7d-105">**Applies to:**</span></span>
- [<span data-ttu-id="62d7d-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="62d7d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="62d7d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62d7d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="62d7d-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="62d7d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="62d7d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="62d7d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="62d7d-110">Le regole di riduzione della superficie di attacco consentono di impedire le azioni in genere utilizzate dal malware per compromettere dispositivi o reti.</span><span class="sxs-lookup"><span data-stu-id="62d7d-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="62d7d-111">Imposta le regole di riduzione della superficie di attacco per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="62d7d-111">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="62d7d-112">Windows 10 Pro, [versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o successiva</span><span class="sxs-lookup"><span data-stu-id="62d7d-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="62d7d-113">Windows 10 Enterprise, [versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o successiva</span><span class="sxs-lookup"><span data-stu-id="62d7d-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="62d7d-114">Windows Server, [versione 1803 (Canale semestraale)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="62d7d-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="62d7d-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="62d7d-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="62d7d-116">Scopri come valutare le regole di riduzione della superficie di attacco abilitando la modalità di controllo per testare la funzionalità direttamente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="62d7d-116">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="62d7d-117">Puoi anche visitare il sito Web dello scenario demo di Microsoft Defender per Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che la funzionalità funzioni e vedere come funziona.</span><span class="sxs-lookup"><span data-stu-id="62d7d-117">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="62d7d-118">Usare la modalità di controllo per misurare l'impatto</span><span class="sxs-lookup"><span data-stu-id="62d7d-118">Use audit mode to measure impact</span></span>

<span data-ttu-id="62d7d-119">Abilita le regole di riduzione della superficie di attacco in modalità di controllo per visualizzare un record di app che sarebbero state bloccate se la funzionalità fosse stata completamente abilitata.</span><span class="sxs-lookup"><span data-stu-id="62d7d-119">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="62d7d-120">Testare il funzionamento della funzionalità nell'organizzazione per assicurarsi che non influisca sulle app line-of-business.</span><span class="sxs-lookup"><span data-stu-id="62d7d-120">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="62d7d-121">È inoltre possibile avere un'idea della frequenza di esecuzione delle regole durante il normale utilizzo.</span><span class="sxs-lookup"><span data-stu-id="62d7d-121">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="62d7d-122">Per abilitare una regola di riduzione della superficie di attacco in modalità di controllo, utilizzare il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="62d7d-122">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="62d7d-123">Dove è un valore GUID della regola di riduzione della superficie `<rule ID>` [di attacco.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="62d7d-123">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="62d7d-124">Per abilitare tutte le regole di riduzione della superficie di attacco aggiunte in modalità di controllo, utilizzare il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="62d7d-124">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="62d7d-125">Se si desidera controllare completamente il funzionamento delle regole di riduzione della superficie di attacco nell'organizzazione, è necessario utilizzare uno strumento di gestione per distribuire questa impostazione nei dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="62d7d-125">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="62d7d-126">Puoi anche usare Criteri di gruppo, Intune o provider di servizi di configurazione (CSP) per la gestione dei dispositivi mobili (MDM) per configurare e distribuire l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="62d7d-126">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="62d7d-127">Per ulteriori informazioni, vedere [l'articolo principale Sulle regole di riduzione della superficie di](attack-surface-reduction.md) attacco.</span><span class="sxs-lookup"><span data-stu-id="62d7d-127">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="62d7d-128">Esaminare gli eventi di riduzione della superficie di attacco nel Visualizzatore eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="62d7d-128">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="62d7d-129">Per esaminare le app che sarebbero state bloccate, aprire il Visualizzatore eventi e filtrare l'ID evento 1121 nel registro microsoft-Windows-Windows Defender/operativo.</span><span class="sxs-lookup"><span data-stu-id="62d7d-129">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="62d7d-130">Nella tabella seguente sono elencati tutti gli eventi di protezione di rete.</span><span class="sxs-lookup"><span data-stu-id="62d7d-130">The following table lists all network protection events.</span></span>

<span data-ttu-id="62d7d-131">ID evento</span><span class="sxs-lookup"><span data-stu-id="62d7d-131">Event ID</span></span> | <span data-ttu-id="62d7d-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62d7d-132">Description</span></span>
-|-
 <span data-ttu-id="62d7d-133">5007</span><span class="sxs-lookup"><span data-stu-id="62d7d-133">5007</span></span> | <span data-ttu-id="62d7d-134">Evento quando vengono modificate le impostazioni</span><span class="sxs-lookup"><span data-stu-id="62d7d-134">Event when settings are changed</span></span>
 <span data-ttu-id="62d7d-135">1121</span><span class="sxs-lookup"><span data-stu-id="62d7d-135">1121</span></span> | <span data-ttu-id="62d7d-136">Evento quando viene attivata una regola di riduzione della superficie di attacco in modalità blocco</span><span class="sxs-lookup"><span data-stu-id="62d7d-136">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="62d7d-137">1122</span><span class="sxs-lookup"><span data-stu-id="62d7d-137">1122</span></span> | <span data-ttu-id="62d7d-138">Evento quando una regola di riduzione della superficie di attacco viene attivata in modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="62d7d-138">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="62d7d-139">Personalizzare le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="62d7d-139">Customize attack surface reduction rules</span></span>

<span data-ttu-id="62d7d-140">Durante la valutazione, è possibile configurare ogni regola singolarmente o escludere determinati file e processi dalla valutazione da parte della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="62d7d-140">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="62d7d-141">Vedi [Personalizzare le regole di riduzione della superficie](customize-attack-surface-reduction.md) di attacco per informazioni sulla configurazione della funzionalità con strumenti di gestione, inclusi Criteri di gruppo e criteri CSP MDM.</span><span class="sxs-lookup"><span data-stu-id="62d7d-141">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="62d7d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62d7d-142">See also</span></span>

* [<span data-ttu-id="62d7d-143">Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="62d7d-143">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="62d7d-144">Usare la modalità di controllo per valutare Windows Defender</span><span class="sxs-lookup"><span data-stu-id="62d7d-144">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="62d7d-145">Domande frequenti sulla riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="62d7d-145">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
