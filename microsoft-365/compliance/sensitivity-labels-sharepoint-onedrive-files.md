---
title: Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Gli amministratori possono abilitare il supporto delle etichette di riservatezza per i file Word, Excel e PowerPoint in SharePoint e OneDrive.
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802829"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="6d544-103">Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive (anteprima pubblica)</span><span class="sxs-lookup"><span data-stu-id="6d544-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="6d544-104">In precedenza, quando sono state applicate etichette di riservatezza che includono la crittografia per i file di Office archiviati in SharePoint e OneDrive, il servizio non è in grado di elaborare il contenuto di tali file.</span><span class="sxs-lookup"><span data-stu-id="6d544-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="6d544-105">La CoAuthoring, la eDiscovery, la prevenzione della perdita di dati, la ricerca, l'approfondimento e altre funzionalità di collaborazione non hanno funzionato in queste circostanze.</span><span class="sxs-lookup"><span data-stu-id="6d544-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="6d544-106">Questa anteprima consente di abilitare queste caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="6d544-106">This preview enables these features:</span></span>

- <span data-ttu-id="6d544-107">SharePoint riconosce le etichette di riservatezza applicate ai file di Word, Excel e PowerPoint in SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6d544-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="6d544-108">SharePoint applica anche le impostazioni che corrispondono a ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="6d544-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="6d544-109">Quando si scarica un file da SharePoint o OneDrive, l'etichetta di riservatezza viaggia con il file e le impostazioni restano applicate.</span><span class="sxs-lookup"><span data-stu-id="6d544-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="6d544-110">Applicare le etichette di riservatezza ai file di Office e aprire e modificare i file con etichette di riservatezza applicate (se le autorizzazioni dell'etichetta lo consentono) utilizzando le versioni Web di Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="6d544-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="6d544-111">Con Word sul Web, è possibile utilizzare l'etichettatura automatica anche quando si modificano i documenti.</span><span class="sxs-lookup"><span data-stu-id="6d544-111">With Word on the web, you can also use Auto labeling when you edit documents.</span></span>

- <span data-ttu-id="6d544-112">Office 365 eDiscovery supporta la ricerca full-text nei file con etichette di riservatezza applicate.</span><span class="sxs-lookup"><span data-stu-id="6d544-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="6d544-113">I criteri di prevenzione della perdita di dati (DLP) riguardano i contenuti di questi file.</span><span class="sxs-lookup"><span data-stu-id="6d544-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="6d544-114">Sono disponibili tre nuovi eventi di controllo per il monitoraggio delle etichette di riservatezza:</span><span class="sxs-lookup"><span data-stu-id="6d544-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="6d544-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="6d544-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="6d544-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="6d544-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="6d544-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="6d544-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="6d544-118">È inoltre possibile applicare etichette di riservatezza a Microsoft teams, gruppi di Office 365 e siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6d544-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="6d544-119">[Altre informazioni](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="6d544-119">[Learn more](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="6d544-120">Se necessario, è possibile escludere l'anteprima in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="6d544-120">If necessary, you can opt out of the preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="6d544-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d544-121">Requirements</span></span>

<span data-ttu-id="6d544-122">Queste funzionalità funzionano solo con le [etichette di riservatezza](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="6d544-122">These features work only with [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="6d544-123">Se sono state utilizzate le etichette di Azure Information Protection, è possibile convertirle in etichette di riservatezza per abilitare queste funzionalità per i nuovi file caricati.</span><span class="sxs-lookup"><span data-stu-id="6d544-123">If you used Azure Information Protection labels, you can convert them to sensitivity labels to enable these features for new files that you upload.</span></span> [<span data-ttu-id="6d544-124">Informazioni su come</span><span class="sxs-lookup"><span data-stu-id="6d544-124">Learn how</span></span>](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

<span data-ttu-id="6d544-125">Per questa anteprima, utilizzare la versione di OneDrive Sync App 19.002.0121.0008 o versioni successive su Windows e la versione 19.002.0107.0008 o versioni successive su Mac.</span><span class="sxs-lookup"><span data-stu-id="6d544-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="6d544-126">Entrambe le versioni sono state rilasciate il 28 gennaio 2019 e sono attualmente rilasciate a tutti gli anelli.</span><span class="sxs-lookup"><span data-stu-id="6d544-126">Both of these versions were released on January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="6d544-127">[Vedere le note sulla versione di OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="6d544-127">[See the OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="6d544-128">Dopo aver abilitato l'anteprima, gli utenti che eseguono una versione precedente dell'app di sincronizzazione verranno invitati a aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="6d544-128">After you enable this preview, users who run an older version of the sync app will be prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="6d544-129">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="6d544-129">Limitations</span></span>

- <span data-ttu-id="6d544-130">Quando si abilita questa anteprima, gli utenti che applicano un'etichetta a un file utilizzando le app desktop o mobili di Office potrebbero non essere in grado di salvare le modifiche apportate al file.</span><span class="sxs-lookup"><span data-stu-id="6d544-130">When you enable this preview, users who apply a label to a file by using the Office desktop or mobile apps might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="6d544-131">In alternativa, l'app richiede agli utenti di salvare o ignorare le modifiche locali.</span><span class="sxs-lookup"><span data-stu-id="6d544-131">Instead, the app prompts users to Save As or Discard local changes.</span></span> <span data-ttu-id="6d544-132">Per evitare di perdere il lavoro, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d544-132">To avoid losing work, do one of these actions:</span></span>

  - <span data-ttu-id="6d544-133">Per applicare le etichette, utilizzare le versioni Web delle app di Office.</span><span class="sxs-lookup"><span data-stu-id="6d544-133">To apply labels, use the web versions of the Office apps.</span></span>

  - <span data-ttu-id="6d544-134">Chiudere un file dopo l'applicazione di un'etichetta e quindi riaprire il file per apportare altre modifiche.</span><span class="sxs-lookup"><span data-stu-id="6d544-134">Close a file after you apply a label and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="6d544-135">SharePoint non applica automaticamente le nuove etichette ai file esistenti già crittografati utilizzando le etichette di Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="6d544-135">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="6d544-136">Al contrario, per far funzionare le caratteristiche dopo aver abilitato l'anteprima, completare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="6d544-136">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>

  - <span data-ttu-id="6d544-137">Convertire le etichette di Azure Information Protection in etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="6d544-137">Convert the Azure Information Protection labels to sensitivity labels.</span></span>

  - <span data-ttu-id="6d544-138">Scaricare i file e caricarli in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6d544-138">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="6d544-139">SharePoint non è in grado di elaborare etichette con autorizzazioni e etichette personalizzate con date di scadenza.</span><span class="sxs-lookup"><span data-stu-id="6d544-139">SharePoint can't process labels with custom permissions and labels with expiration dates.</span></span>

- <span data-ttu-id="6d544-140">Quando gli utenti dispongono di autorizzazioni di modifica, le versioni Web delle app di Office consentono la copia indipendentemente dall'impostazione del criterio di copia nell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="6d544-140">When users have edit permissions, the web versions of the Office apps allow copying regardless of the copy policy setting in the label.</span></span>

- <span data-ttu-id="6d544-141">La revoca, la verifica e la segnalazione RMS non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="6d544-141">RMS revocation, tracking, and reporting are unsupported.</span></span>

- <span data-ttu-id="6d544-142">Le app desktop di Office e le app per dispositivi mobili non supportano la CoAuthoring.</span><span class="sxs-lookup"><span data-stu-id="6d544-142">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="6d544-143">Queste app continuano invece a aprire file in modalità di modifica esclusiva.</span><span class="sxs-lookup"><span data-stu-id="6d544-143">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="6d544-144">Se un'etichetta include la crittografia, Microsoft cloud app Security non è in grado di leggere le informazioni sull'etichetta per i file in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6d544-144">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="6d544-145">Preparare la shell di gestione di SharePoint Online per l'anteprima</span><span class="sxs-lookup"><span data-stu-id="6d544-145">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="6d544-146">Prima di abilitare l'anteprima, verificare che sia in esecuzione SharePoint Online Management Shell versione 16.0.19418.12000 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="6d544-146">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="6d544-147">Se si ha già la versione più recente, è possibile procedere e abilitare l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="6d544-147">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="6d544-148">Se è stata installata una versione precedente di SharePoint Online Management Shell dalla raccolta di PowerShell, è possibile aggiornare il modulo eseguendo il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="6d544-148">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="6d544-149">In alternativa, se è stata installata una versione precedente di SharePoint Online Management Shell dall'area download Microsoft, è anche possibile **aggiungere o rimuovere programmi** e disinstallare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6d544-149">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="6d544-150">In un Web browser passare alla pagina Centro download e [scaricare la versione più recente di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="6d544-150">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="6d544-151">Selezionare la lingua e quindi fare clic su **download**.</span><span class="sxs-lookup"><span data-stu-id="6d544-151">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="6d544-152">Scegliere tra il file x64 e x86. msi.</span><span class="sxs-lookup"><span data-stu-id="6d544-152">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="6d544-153">Scaricare il file x64 se si esegue la versione di Windows a 64 bit o il file x86 se si esegue la versione a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="6d544-153">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="6d544-154">Se non si conosce, vedere [la versione del sistema operativo Windows in esecuzione?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="6d544-154">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="6d544-155">Dopo aver scaricato il file, eseguire il file e seguire i passaggi illustrati nell'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="6d544-155">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="6d544-156">Abilitare l'anteprima tramite Microsoft PowerShell (opt-in)</span><span class="sxs-lookup"><span data-stu-id="6d544-156">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="6d544-157">Per abilitare l'anteprima, utilizzare il cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="6d544-157">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="6d544-158">Utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale o di amministrazione di SharePoint in Office 365, connettersi a SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6d544-158">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="6d544-159">Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="6d544-159">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="6d544-160">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6d544-160">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="6d544-161">Pianificare l'implementazione dopo la creazione o la modifica di un'etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="6d544-161">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="6d544-162">Dopo aver creato o modificato un'etichetta di riservatezza nel centro conformità di Microsoft 365, pubblicarla in fasi.</span><span class="sxs-lookup"><span data-stu-id="6d544-162">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="6d544-163">Se si pubblicano etichette che non sono state completamente sincronizzate, quando gli utenti applicano le etichette ai file e le caricano in SharePoint, i file non possono essere aperti nelle versioni Web delle app di Office.</span><span class="sxs-lookup"><span data-stu-id="6d544-163">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="6d544-164">Anche le funzioni di ricerca e eDiscovery non funzionano per i file.</span><span class="sxs-lookup"><span data-stu-id="6d544-164">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="6d544-165">È consigliabile attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="6d544-165">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="6d544-166">Pubblicare l'etichetta di riservatezza nuova o modificata solo su una o due persone.</span><span class="sxs-lookup"><span data-stu-id="6d544-166">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="6d544-167">Attendere almeno 24 ore dopo la pubblicazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="6d544-167">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="6d544-168">Verificare che l'etichetta sia stata completamente sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="6d544-168">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="6d544-169">Pubblicare l'etichetta in senso più generale.</span><span class="sxs-lookup"><span data-stu-id="6d544-169">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="6d544-170">Disabilitare l'anteprima tramite Microsoft PowerShell (opt-out)</span><span class="sxs-lookup"><span data-stu-id="6d544-170">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="6d544-171">Se si disattiva questa anteprima, i file caricati durante l'anteprima continueranno a essere protetti dall'etichetta.</span><span class="sxs-lookup"><span data-stu-id="6d544-171">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="6d544-172">Le impostazioni corrispondenti continuano a essere applicate.</span><span class="sxs-lookup"><span data-stu-id="6d544-172">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="6d544-173">Quando si applicano etichette ai nuovi file dopo aver disabilitato l'anteprima, la ricerca full-text, eDiscovery e la CoAuthoring non funzioneranno più.</span><span class="sxs-lookup"><span data-stu-id="6d544-173">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="6d544-174">Per disabilitare l'anteprima, utilizzare il cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="6d544-174">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="6d544-175">Utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale o di amministrazione di SharePoint in Office 365, connettersi a SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6d544-175">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="6d544-176">Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="6d544-176">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="6d544-177">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6d544-177">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
