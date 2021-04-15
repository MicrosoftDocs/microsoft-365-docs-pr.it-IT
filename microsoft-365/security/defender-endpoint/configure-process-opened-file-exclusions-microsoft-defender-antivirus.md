---
title: Configurare le esclusioni per i file aperti da processi specifici
description: È possibile escludere i file dalle analisi se sono stati aperti da un processo specifico.
keywords: Microsoft Defender Antivirus, processo, esclusione, file, analisi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 94375bc843c6512616d49345bcc9e7f63899a708
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765084"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="13e4f-104">Configurare le esclusioni per i file aperti dai processi</span><span class="sxs-lookup"><span data-stu-id="13e4f-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="13e4f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="13e4f-105">**Applies to:**</span></span>

- [<span data-ttu-id="13e4f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="13e4f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="13e4f-107">Puoi escludere i file aperti da processi specifici dalle analisi di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="13e4f-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="13e4f-108">Vedere [Suggerimenti per la definizione delle esclusioni](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) prima di definire gli elenchi di esclusione.</span><span class="sxs-lookup"><span data-stu-id="13e4f-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="13e4f-109">In questo articolo viene descritto come configurare gli elenchi di esclusione.</span><span class="sxs-lookup"><span data-stu-id="13e4f-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="13e4f-110">Esempi di esclusioni</span><span class="sxs-lookup"><span data-stu-id="13e4f-110">Examples of exclusions</span></span>

|<span data-ttu-id="13e4f-111">Esclusione</span><span class="sxs-lookup"><span data-stu-id="13e4f-111">Exclusion</span></span> | <span data-ttu-id="13e4f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="13e4f-112">Example</span></span> |
|---|---|
|<span data-ttu-id="13e4f-113">Qualsiasi file nel computer aperto da qualsiasi processo con un nome di file specifico</span><span class="sxs-lookup"><span data-stu-id="13e4f-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="13e4f-114">Specificando si `test.exe` escluderebbero i file aperti da:</span><span class="sxs-lookup"><span data-stu-id="13e4f-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="13e4f-115">Qualsiasi file nel computer aperto da qualsiasi processo in una cartella specifica</span><span class="sxs-lookup"><span data-stu-id="13e4f-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="13e4f-116">Specificando si `c:\test\sample\*` escluderebbero i file aperti da:</span><span class="sxs-lookup"><span data-stu-id="13e4f-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="13e4f-117">Qualsiasi file nel computer aperto da un processo specifico in una cartella specifica</span><span class="sxs-lookup"><span data-stu-id="13e4f-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="13e4f-118">Se si specifica `c:\test\process.exe` l'esclusione dei file aperti solo da `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="13e4f-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="13e4f-119">Quando aggiungi un processo all'elenco di esclusione dei processi, Microsoft Defender Antivirus non analizza i file aperti da tale processo, indipendentemente dalla posizione in cui si trovano i file.</span><span class="sxs-lookup"><span data-stu-id="13e4f-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="13e4f-120">Il processo stesso, tuttavia, verrà analizzato a meno che non sia stato aggiunto anche [all'elenco di esclusione file.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="13e4f-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="13e4f-121">Le esclusioni si applicano solo alla protezione e al monitoraggio sempre in tempo [reale.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="13e4f-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="13e4f-122">Non si applicano alle analisi pianificate o su richiesta.</span><span class="sxs-lookup"><span data-stu-id="13e4f-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="13e4f-123">Le modifiche apportate con Criteri di gruppo agli elenchi di **esclusione verranno** mostrate negli elenchi nell'app Sicurezza [di Windows.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="13e4f-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="13e4f-124">Tuttavia, le modifiche apportate nell'app Sicurezza di Windows **non verranno mostrate** negli elenchi di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="13e4f-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="13e4f-125">Puoi aggiungere, rimuovere ed esaminare gli elenchi per le esclusioni in Criteri di gruppo, Microsoft Endpoint Configuration Manager, Microsoft Intune e con l'app Sicurezza di Windows e puoi usare i caratteri jolly per personalizzare ulteriormente gli elenchi.</span><span class="sxs-lookup"><span data-stu-id="13e4f-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="13e4f-126">È inoltre possibile utilizzare i cmdlet di PowerShell e WMI per configurare gli elenchi di esclusione, inclusa la revisione degli elenchi.</span><span class="sxs-lookup"><span data-stu-id="13e4f-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="13e4f-127">Per impostazione predefinita, le modifiche locali apportate agli elenchi (dagli utenti con privilegi di amministratore, le modifiche apportate con PowerShell e WMI) verranno unite agli elenchi definiti (e distribuiti) da Criteri di gruppo, Configuration Manager o Intune.</span><span class="sxs-lookup"><span data-stu-id="13e4f-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="13e4f-128">Gli elenchi di Criteri di gruppo avranno la precedenza in caso di conflitti.</span><span class="sxs-lookup"><span data-stu-id="13e4f-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="13e4f-129">È possibile [configurare la modalità di unione degli](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) elenchi di esclusioni definite localmente e globalmente per consentire alle modifiche locali di ignorare le impostazioni di distribuzione gestite.</span><span class="sxs-lookup"><span data-stu-id="13e4f-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="13e4f-130">Configurare l'elenco di esclusioni per i file aperti da processi specificati</span><span class="sxs-lookup"><span data-stu-id="13e4f-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="13e4f-131">Usare Microsoft Intune per escludere i file aperti da processi specificati dalle analisi</span><span class="sxs-lookup"><span data-stu-id="13e4f-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="13e4f-132">Per [altri dettagli, vedi](/intune/device-restrictions-configure) Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune e Microsoft Defender Antivirus per [Windows 10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="13e4f-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="13e4f-133">Utilizzare Microsoft Endpoint Manager per escludere i file aperti da processi specificati dalle analisi</span><span class="sxs-lookup"><span data-stu-id="13e4f-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="13e4f-134">Vedi [Come creare e distribuire criteri antimalware: impostazioni](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) di esclusione per informazioni dettagliate sulla configurazione di Microsoft Endpoint Manager (current branch).</span><span class="sxs-lookup"><span data-stu-id="13e4f-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="13e4f-135">Utilizzare Criteri di gruppo per escludere i file aperti da processi specificati dalle analisi</span><span class="sxs-lookup"><span data-stu-id="13e4f-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="13e4f-136">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="13e4f-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="13e4f-137">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="13e4f-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="13e4f-138">Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus > Esclusioni**.</span><span class="sxs-lookup"><span data-stu-id="13e4f-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="13e4f-139">Fare doppio clic **su Elabora esclusioni** e aggiungere le esclusioni:</span><span class="sxs-lookup"><span data-stu-id="13e4f-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="13e4f-140">Impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="13e4f-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="13e4f-141">Nella sezione **Opzioni** fare clic su **Mostra...**.</span><span class="sxs-lookup"><span data-stu-id="13e4f-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="13e4f-142">Immettere ogni processo nella propria riga nella **colonna Nome** valore.</span><span class="sxs-lookup"><span data-stu-id="13e4f-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="13e4f-143">Vedere la tabella di esempio per i diversi tipi di esclusioni di processo.</span><span class="sxs-lookup"><span data-stu-id="13e4f-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="13e4f-144">Immettere **0** nella **colonna Valore** per tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="13e4f-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="13e4f-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="13e4f-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="13e4f-146">Utilizzare i cmdlet di PowerShell per escludere i file aperti da processi specificati dalle analisi</span><span class="sxs-lookup"><span data-stu-id="13e4f-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="13e4f-147">L'utilizzo di PowerShell per aggiungere o rimuovere esclusioni per i file aperti dai processi richiede l'utilizzo di una combinazione di tre cmdlet con il `-ExclusionProcess` parametro .</span><span class="sxs-lookup"><span data-stu-id="13e4f-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="13e4f-148">I cmdlet sono tutti nel [modulo Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="13e4f-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="13e4f-149">Il formato per i cmdlet è:</span><span class="sxs-lookup"><span data-stu-id="13e4f-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="13e4f-150">Gli elementi seguenti sono consentiti come \<cmdlet> :</span><span class="sxs-lookup"><span data-stu-id="13e4f-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="13e4f-151">Azione di configurazione</span><span class="sxs-lookup"><span data-stu-id="13e4f-151">Configuration action</span></span> | <span data-ttu-id="13e4f-152">Cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="13e4f-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="13e4f-153">Creare o sovrascrivere l'elenco</span><span class="sxs-lookup"><span data-stu-id="13e4f-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="13e4f-154">Aggiungi all'elenco</span><span class="sxs-lookup"><span data-stu-id="13e4f-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="13e4f-155">Rimuovere elementi dall'elenco</span><span class="sxs-lookup"><span data-stu-id="13e4f-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="13e4f-156">Se è stato creato un elenco con o , utilizzando di nuovo `Set-MpPreference` `Add-MpPreference` il cmdlet verrà `Set-MpPreference` sovrascritto l'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="13e4f-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="13e4f-157">Ad esempio, il frammento di codice seguente fa in modo che le analisi di Microsoft Defender AV escludono qualsiasi file aperto dal processo specificato:</span><span class="sxs-lookup"><span data-stu-id="13e4f-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="13e4f-158">Per ulteriori informazioni su come usare PowerShell con Microsoft Defender Antivirus, vedere Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="13e4f-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="13e4f-159">Utilizzare Windows Management Instruction (WMI) per escludere i file aperti da processi specificati dalle analisi</span><span class="sxs-lookup"><span data-stu-id="13e4f-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="13e4f-160">Utilizzare i [ **metodi Set**, **Add** e **Remove** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="13e4f-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="13e4f-161">**L'utilizzo di Set,** **Add** e **Remove** è analogo alle rispettive controparti in PowerShell: , `Set-MpPreference` e `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="13e4f-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="13e4f-162">Per altre informazioni e parametri consentiti, [vedi Windows Defender API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="13e4f-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="13e4f-163">Usare l'app Sicurezza di Windows per escludere i file aperti da processi specificati dalle analisi</span><span class="sxs-lookup"><span data-stu-id="13e4f-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="13e4f-164">Per istruzioni, vedi Aggiungere [esclusioni nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="13e4f-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="13e4f-165">Utilizzare caratteri jolly nell'elenco di esclusione dei processi</span><span class="sxs-lookup"><span data-stu-id="13e4f-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="13e4f-166">L'utilizzo dei caratteri jolly nell'elenco di esclusione dei processi è diverso dall'utilizzo in altri elenchi di esclusione.</span><span class="sxs-lookup"><span data-stu-id="13e4f-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="13e4f-167">In particolare, non è possibile utilizzare il carattere jolly punto interrogativo ( ) e il carattere jolly asterisco ( ) può essere utilizzato solo alla fine `?` `*` di un percorso completo.</span><span class="sxs-lookup"><span data-stu-id="13e4f-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="13e4f-168">È comunque possibile utilizzare variabili di ambiente (ad esempio ) come caratteri jolly per `%ALLUSERSPROFILE%` definire gli elementi nell'elenco di esclusione dei processi.</span><span class="sxs-lookup"><span data-stu-id="13e4f-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="13e4f-169">Nella tabella seguente viene descritto come utilizzare i caratteri jolly nell'elenco di esclusione dei processi:</span><span class="sxs-lookup"><span data-stu-id="13e4f-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="13e4f-170">Carattere jolly</span><span class="sxs-lookup"><span data-stu-id="13e4f-170">Wildcard</span></span> | <span data-ttu-id="13e4f-171">Esempio di utilizzo</span><span class="sxs-lookup"><span data-stu-id="13e4f-171">Example use</span></span> | <span data-ttu-id="13e4f-172">Corrispondenze di esempio</span><span class="sxs-lookup"><span data-stu-id="13e4f-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="13e4f-173">`*` (asterisco)</span><span class="sxs-lookup"><span data-stu-id="13e4f-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="13e4f-174">Sostituisce qualsiasi numero di caratteri</span><span class="sxs-lookup"><span data-stu-id="13e4f-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="13e4f-175">Qualsiasi file aperto da `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="13e4f-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="13e4f-176">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="13e4f-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="13e4f-177">La variabile definita viene popolata come percorso quando viene valutata l'esclusione</span><span class="sxs-lookup"><span data-stu-id="13e4f-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="13e4f-178">Qualsiasi file aperto da `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="13e4f-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="13e4f-179">Esaminare l'elenco delle esclusioni</span><span class="sxs-lookup"><span data-stu-id="13e4f-179">Review the list of exclusions</span></span>

<span data-ttu-id="13e4f-180">Puoi recuperare gli elementi nell'elenco di esclusione con MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)o l'app Di sicurezza [di Windows.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="13e4f-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="13e4f-181">Se si utilizza PowerShell, è possibile recuperare l'elenco in due modi:</span><span class="sxs-lookup"><span data-stu-id="13e4f-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="13e4f-182">Recuperare lo stato di tutte le preferenze di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="13e4f-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="13e4f-183">Ogni elenco verrà visualizzato su righe separate, ma gli elementi all'interno di ogni elenco verranno combinati nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="13e4f-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="13e4f-184">Scrivi lo stato di tutte le preferenze in una variabile e usa tale variabile solo per chiamare l'elenco specifico che ti interessa.</span><span class="sxs-lookup"><span data-stu-id="13e4f-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="13e4f-185">Ogni utilizzo di `Add-MpPreference` viene scritto in una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="13e4f-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="13e4f-186">Convalidare l'elenco di esclusione utilizzando MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="13e4f-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="13e4f-187">Per controllare le esclusioni con lo strumento da riga di comando dedicato [mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13e4f-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="13e4f-188">Il controllo delle esclusioni con MpCmdRun richiede Microsoft Defender Antivirus CAMP versione 4.18.1812.3 (rilasciata a dicembre 2018) o successiva.</span><span class="sxs-lookup"><span data-stu-id="13e4f-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="13e4f-189">Esaminare l'elenco delle esclusioni insieme a tutte le altre preferenze di Microsoft Defender Antivirus tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="13e4f-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="13e4f-190">Utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="13e4f-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="13e4f-191">Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="13e4f-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="13e4f-192">Recuperare un elenco di esclusioni specifico tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="13e4f-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="13e4f-193">Usa il frammento di codice seguente (immetti ogni riga come comando separato); sostituire **WDAVprefs** con qualsiasi etichetta che si desidera assegnare alla variabile:</span><span class="sxs-lookup"><span data-stu-id="13e4f-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="13e4f-194">Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="13e4f-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="13e4f-195">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="13e4f-195">Related articles</span></span>

- [<span data-ttu-id="13e4f-196">Configurare e convalidare le esclusioni nelle analisi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="13e4f-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="13e4f-197">Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella</span><span class="sxs-lookup"><span data-stu-id="13e4f-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="13e4f-198">Configurare le esclusioni di Microsoft Defender Antivirus in Windows Server</span><span class="sxs-lookup"><span data-stu-id="13e4f-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="13e4f-199">Errori comuni da evitare durante la definizione delle esclusioni</span><span class="sxs-lookup"><span data-stu-id="13e4f-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="13e4f-200">Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="13e4f-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="13e4f-201">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="13e4f-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)