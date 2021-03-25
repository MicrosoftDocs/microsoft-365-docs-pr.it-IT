---
title: Risolvere i problemi relativi a Protezione di rete
description: Risorse e codice di esempio per la risoluzione dei problemi relativi a Protezione di rete in Microsoft Defender per Endpoint.
keywords: risoluzione dei problemi, errore, correzione, windows defender ad esempio, asr, regole, hips, risoluzione dei problemi, controllo, esclusione, falso positivo, interrotto, blocco, microsoft defender per endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 165c17bc820403ebfbbe5cdfe3ca856e8416c593
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066042"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="3e694-104">Risolvere i problemi di protezione di rete</span><span class="sxs-lookup"><span data-stu-id="3e694-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3e694-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3e694-105">**Applies to:**</span></span>
- [<span data-ttu-id="3e694-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3e694-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3e694-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e694-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3e694-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3e694-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3e694-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3e694-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="3e694-110">Quando si utilizza [Protezione di rete,](network-protection.md) è possibile che si verifichino problemi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3e694-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="3e694-111">Protezione di rete blocca un sito Web sicuro (falso positivo)</span><span class="sxs-lookup"><span data-stu-id="3e694-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="3e694-112">La protezione di rete non riesce a bloccare un sito Web dannoso sospetto o noto (falso negativo)</span><span class="sxs-lookup"><span data-stu-id="3e694-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="3e694-113">Per risolvere questi problemi, è necessario eseguire quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="3e694-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="3e694-114">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3e694-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="3e694-115">Usare la modalità di controllo per testare la regola</span><span class="sxs-lookup"><span data-stu-id="3e694-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="3e694-116">Aggiungere esclusioni per la regola specificata (per falsi positivi)</span><span class="sxs-lookup"><span data-stu-id="3e694-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="3e694-117">Inviare i log di supporto</span><span class="sxs-lookup"><span data-stu-id="3e694-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="3e694-118">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3e694-118">Confirm prerequisites</span></span>

<span data-ttu-id="3e694-119">La protezione di rete funzionerà solo nei dispositivi con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e694-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="3e694-120">Gli endpoint eseguono Windows 10 Pro o Enterprise Edition, versione 1709 o successiva.</span><span class="sxs-lookup"><span data-stu-id="3e694-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="3e694-121">Gli endpoint usano Microsoft Defender Antivirus come unica app di protezione antivirus.</span><span class="sxs-lookup"><span data-stu-id="3e694-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="3e694-122">[Vedere cosa succede quando si utilizza una soluzione antivirus non Microsoft.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="3e694-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="3e694-123">[La protezione in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="3e694-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="3e694-124">[La protezione consegnata dal cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="3e694-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="3e694-125">La modalità di controllo non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="3e694-125">Audit mode is not enabled.</span></span> <span data-ttu-id="3e694-126">Utilizzare [Criteri di gruppo](enable-network-protection.md#group-policy) per impostare la regola su **Disabilitato** (valore: **0**).</span><span class="sxs-lookup"><span data-stu-id="3e694-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="3e694-127">Usare la modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="3e694-127">Use audit mode</span></span>

<span data-ttu-id="3e694-128">È possibile abilitare la protezione di rete in modalità di controllo e quindi visitare un sito Web creato per la dimostrazione della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3e694-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="3e694-129">Tutte le connessioni al sito Web saranno consentite dalla protezione di rete, ma verrà registrato un evento per indicare qualsiasi connessione che sarebbe stata bloccata se la protezione di rete fosse stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="3e694-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="3e694-130">Impostare protezione di rete su **Modalità di controllo**.</span><span class="sxs-lookup"><span data-stu-id="3e694-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="3e694-131">Eseguire l'attività di connessione che causa un problema( ad esempio, tentare di visitare il sito o connettersi all'indirizzo IP che si esegue o non si desidera bloccare).</span><span class="sxs-lookup"><span data-stu-id="3e694-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="3e694-132">[Esaminare i registri eventi di protezione](network-protection.md#review-network-protection-events-in-windows-event-viewer) di rete per verificare se la funzionalità avrebbe bloccato la connessione se fosse stata impostata su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="3e694-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="3e694-133">Se la protezione di rete non blocca una connessione che si prevede che dovrebbe bloccare, abilitare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3e694-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="3e694-134">Segnalare un falso positivo o falso negativo</span><span class="sxs-lookup"><span data-stu-id="3e694-134">Report a false positive or false negative</span></span>

<span data-ttu-id="3e694-135">Se la funzionalità è stata testata con il sito demo e con la modalità di controllo e la protezione di rete funziona su scenari preconfigurati, ma non funziona come previsto per una connessione specifica, utilizzare il modulo di invio basato sul Web di [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) per segnalare un falso negativo o un falso positivo per la protezione di rete.</span><span class="sxs-lookup"><span data-stu-id="3e694-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="3e694-136">Con una sottoscrizione E5 puoi anche [fornire un collegamento a qualsiasi avviso associato.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="3e694-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="3e694-137">Vedi [Indirizzo falsi positivi/negativi in Microsoft Defender per Endpoint.](defender-endpoint-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="3e694-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="3e694-138">Escludere il sito Web dall'ambito di protezione di rete</span><span class="sxs-lookup"><span data-stu-id="3e694-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="3e694-139">Per consentire il sito Web bloccato (falso positivo), aggiungere il relativo URL [all'elenco dei siti attendibili.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)</span><span class="sxs-lookup"><span data-stu-id="3e694-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="3e694-140">Le risorse Web di questo elenco ignorano il controllo della protezione di rete.</span><span class="sxs-lookup"><span data-stu-id="3e694-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="3e694-141">Raccogliere dati di diagnostica per gli invii di file</span><span class="sxs-lookup"><span data-stu-id="3e694-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="3e694-142">Quando si segnala un problema con la protezione di rete, viene richiesto di raccogliere e inviare dati di diagnostica che possono essere utilizzati dai team di supporto e progettazione Microsoft per risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="3e694-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="3e694-143">Aprire un prompt dei comandi con privilegi elevati e passare alla directory Windows Defender:</span><span class="sxs-lookup"><span data-stu-id="3e694-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="3e694-144">Eseguire questo comando per generare i log di diagnostica:</span><span class="sxs-lookup"><span data-stu-id="3e694-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="3e694-145">Per impostazione predefinita, vengono salvati in C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span><span class="sxs-lookup"><span data-stu-id="3e694-145">By default, they are saved to C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span></span> <span data-ttu-id="3e694-146">Allegare il file al modulo di invio.</span><span class="sxs-lookup"><span data-stu-id="3e694-146">Attach the file to the submission form.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3e694-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3e694-147">Related topics</span></span>

- [<span data-ttu-id="3e694-148">Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="3e694-148">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="3e694-149">Valutare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="3e694-149">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="3e694-150">Abilitare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="3e694-150">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="3e694-151">Risolvere i falsi positivi/negativi in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3e694-151">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
