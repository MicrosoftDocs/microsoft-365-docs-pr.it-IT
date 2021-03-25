---
title: Risolvere i problemi relativi alle regole di riduzione della superficie di attacco
description: Risorse e codice di esempio per la risoluzione dei problemi relativi alle regole di riduzione della superficie di attacco in Microsoft Defender per Endpoint.
keywords: risoluzione dei problemi, errore, correzione, windows defender ad esempio, asr, regole, hips, risoluzione dei problemi, controllo, esclusione, falso positivo, interrotto, blocco, microsoft defender per endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: cc8c66665740449e499c11e1db4403caef20cf9c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183766"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="8d0dc-104">Risolvere i problemi relativi alle regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8d0dc-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8d0dc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8d0dc-105">**Applies to:**</span></span>
- [<span data-ttu-id="8d0dc-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8d0dc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8d0dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d0dc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8d0dc-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8d0dc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8d0dc-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="8d0dc-110">Quando usi regole [di riduzione della superficie di](attack-surface-reduction.md) attacco potresti insoddirti in problemi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8d0dc-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="8d0dc-111">Una regola blocca un file, un processo o esegue un'altra azione che non dovrebbe essere eseguita (falso positivo)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="8d0dc-112">Una regola non funziona come descritto o non blocca un file o un processo che dovrebbe essere (falso negativo)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="8d0dc-113">Per risolvere questi problemi, è necessario eseguire quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="8d0dc-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="8d0dc-114">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8d0dc-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="8d0dc-115">Usare la modalità di controllo per testare la regola</span><span class="sxs-lookup"><span data-stu-id="8d0dc-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="8d0dc-116">[Aggiungere esclusioni per la regola specificata](#add-exclusions-for-a-false-positive) (per falsi positivi)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="8d0dc-117">Inviare i log di supporto</span><span class="sxs-lookup"><span data-stu-id="8d0dc-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="8d0dc-118">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8d0dc-118">Confirm prerequisites</span></span>

<span data-ttu-id="8d0dc-119">Le regole di riduzione della superficie di attacco funzionano solo nei dispositivi con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d0dc-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="8d0dc-120">Gli endpoint eseguono Windows 10 Enterprise versione 1709 (noto anche come Fall Creators Update).</span><span class="sxs-lookup"><span data-stu-id="8d0dc-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="8d0dc-121">Gli endpoint usano Microsoft Defender Antivirus come unica app di protezione antivirus.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="8d0dc-122">[L'uso di qualsiasi altra app antivirus causerà la disabilitazione](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)di Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="8d0dc-123">[La protezione in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="8d0dc-124">La modalità di controllo non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="8d0dc-125">Utilizzare Criteri di gruppo per impostare la regola su **Disabilitato** (valore: **0**) come descritto in Abilitare le regole di riduzione della superficie [di attacco.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="8d0dc-126">Se tutti questi prerequisiti sono stati soddisfatti, andare al passaggio successivo per testare la regola in modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="8d0dc-127">Usare la modalità di controllo per testare la regola</span><span class="sxs-lookup"><span data-stu-id="8d0dc-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="8d0dc-128">Puoi visitare il sito Web di base di Windows Defender Test all'indirizzo demo.wd.microsoft.com per verificare che le regole di riduzione della superficie di attacco funzionino [in](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) genere per scenari e processi preconfigurati in un dispositivo oppure puoi usare la modalità di controllo, che abilita le regole solo per la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="8d0dc-129">Segui queste istruzioni in [Usare lo](evaluate-attack-surface-reduction.md) strumento demo per vedere come funzionano le regole di riduzione della superficie di attacco per testare la regola specifica con cui si verificano problemi.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="8d0dc-130">Abilitare la modalità di controllo per la regola specifica che si desidera testare.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="8d0dc-131">Utilizzare Criteri di gruppo per impostare la regola sulla **modalità di** controllo (valore: **2**) come descritto in [Abilitare le regole di riduzione della superficie di attacco.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="8d0dc-132">La modalità di controllo consente alla regola di segnalare il file o il processo, ma ne consentirà comunque l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="8d0dc-133">Eseguire l'attività che causa un problema, ad esempio aprire o eseguire il file o il processo che deve essere bloccato ma che è consentito.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="8d0dc-134">[Esaminare i registri eventi della](attack-surface-reduction.md) regola di riduzione della superficie di attacco per verificare se la regola avrebbe bloccato il file o il processo se la regola fosse stata impostata su **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="8d0dc-135">Se una regola non blocca un file o un processo previsto che dovrebbe bloccarsi, controlla innanzitutto se la modalità di controllo è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="8d0dc-136">La modalità di controllo potrebbe essere stata abilitata per il test di un'altra funzionalità o da uno script di PowerShell automatizzato e potrebbe non essere stata disabilitata al termine dei test.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="8d0dc-137">Se hai testato la regola con lo strumento demo e con la modalità di controllo e le regole di riduzione della superficie di attacco funzionano su scenari preconfigurati, ma la regola non funziona come previsto, passa a una delle sezioni seguenti in base alla situazione:</span><span class="sxs-lookup"><span data-stu-id="8d0dc-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="8d0dc-138">Se la regola di riduzione della superficie di attacco blocca qualcosa che non dovrebbe bloccare (noto anche come falso positivo), puoi innanzitutto aggiungere un'esclusione della regola di riduzione della superficie [di attacco.](#add-exclusions-for-a-false-positive)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="8d0dc-139">Se la regola di riduzione della superficie di attacco non blocca un elemento che dovrebbe bloccare (noto anche come falso negativo), puoi procedere immediatamente all'ultimo passaggio, raccogliendo dati di diagnostica e inviando il problema a [Microsoft.](#collect-diagnostic-data-for-file-submissions)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="8d0dc-140">Aggiungere esclusioni per un falso positivo</span><span class="sxs-lookup"><span data-stu-id="8d0dc-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="8d0dc-141">Se la regola di riduzione della superficie di attacco blocca qualcosa che non dovrebbe bloccare (noto anche come falso positivo), puoi aggiungere esclusioni per impedire alle regole di riduzione della superficie di attacco di valutare i file o le cartelle esclusi.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="8d0dc-142">Per aggiungere un'esclusione, vedi [Personalizzare la riduzione della superficie di attacco.](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="8d0dc-143">È possibile specificare singoli file e cartelle da escludere, ma non è possibile specificare singole regole.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="8d0dc-144">Ciò significa che tutti i file o le cartelle esclusi verranno esclusi da tutte le regole asr.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="8d0dc-145">Segnalare un falso positivo o falso negativo</span><span class="sxs-lookup"><span data-stu-id="8d0dc-145">Report a false positive or false negative</span></span>

<span data-ttu-id="8d0dc-146">Utilizzare il Windows Defender di invio basato sul Web di [Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) per segnalare un falso negativo o un falso positivo per la protezione della rete.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="8d0dc-147">Con un abbonamento a Windows E5, puoi anche [fornire un collegamento a qualsiasi avviso associato.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="8d0dc-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="8d0dc-148">Raccogliere dati di diagnostica per gli invii di file</span><span class="sxs-lookup"><span data-stu-id="8d0dc-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="8d0dc-149">Quando si segnala un problema con le regole di riduzione della superficie di attacco, viene richiesto di raccogliere e inviare dati di diagnostica che possono essere utilizzati dai team di supporto e progettazione Microsoft per risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="8d0dc-150">Aprire un prompt dei comandi con privilegi elevati e passare alla directory Windows Defender:</span><span class="sxs-lookup"><span data-stu-id="8d0dc-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="8d0dc-151">Eseguire questo comando per generare i log di diagnostica:</span><span class="sxs-lookup"><span data-stu-id="8d0dc-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="8d0dc-152">Per impostazione predefinita, vengono salvati in `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="8d0dc-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="8d0dc-153">Allegare il file al modulo di invio.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8d0dc-154">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="8d0dc-154">Related articles</span></span>

- [<span data-ttu-id="8d0dc-155">Regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8d0dc-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="8d0dc-156">Abilitare le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8d0dc-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="8d0dc-157">Valutare le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8d0dc-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
