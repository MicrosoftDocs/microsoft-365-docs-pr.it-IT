---
title: Passaggi di migrazione di AD FS per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: passaggi di migrazione di Active Directory Federation Services (AD FS) per la migrazione da Microsoft Cloud Deutschland.'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727468"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="6ed12-103">Passaggi di migrazione di AD FS per la migrazione da Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="6ed12-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="6ed12-104">Questa modifica alla configurazione può essere applicata in qualsiasi momento prima dell'avvio della fase 4.</span><span class="sxs-lookup"><span data-stu-id="6ed12-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="6ed12-105">Al termine della fase 2, la modifica della configurazione funzionerà e sarà possibile accedere agli endpoint globali di Office 365, ad esempio `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="6ed12-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="6ed12-106">Se si implementa la modifica alla configurazione prima della fase 2,  gli endpoint globali di Office 365 non funzionano ancora, ma la nuova relazione di trust della relying party fa ancora parte della configurazione di Active Directory Federation Services (AD FS).</span><span class="sxs-lookup"><span data-stu-id="6ed12-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="6ed12-107">Per eseguire la migrazione della farm AD FS da Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="6ed12-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="6ed12-108">Eseguire il backup delle impostazioni di AD FS, incluse le info sull'attendibilità FF con [questi passaggi.](#backup)</span><span class="sxs-lookup"><span data-stu-id="6ed12-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="6ed12-109">Denoti il nome **Microsoft Cloud Deutschland_Only** per indicare che contiene solo le informazioni del tenant di Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="6ed12-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="6ed12-110">Testare il ripristino usando il backup di Microsoft Cloud Deutschland_Only, la farm AD FS deve continuare a funzionare solo come Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="6ed12-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="6ed12-111">Dopo aver completato e testato il backup di AD FS, eseguire la procedura seguente per aggiungere un nuovo trust relying party alla configurazione di ADFS:</span><span class="sxs-lookup"><span data-stu-id="6ed12-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="6ed12-112">Aprire la console di gestione di AD FS</span><span class="sxs-lookup"><span data-stu-id="6ed12-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="6ed12-113">Nel riquadro sinistro della console di gestione ADFS espandere **ADFS**, quindi **Relazioni di** trust , quindi **Trust relying party**</span><span class="sxs-lookup"><span data-stu-id="6ed12-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="6ed12-114">Nel riquadro destro seleziona **Aggiungi attendibilità componente...**</span><span class="sxs-lookup"><span data-stu-id="6ed12-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="6ed12-115">Selezionare **Avanti** nella pagina **iniziale** della procedura guidata Aggiungi attendibilità componente.</span><span class="sxs-lookup"><span data-stu-id="6ed12-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="6ed12-116">Nella pagina **Seleziona origine dati** selezionare Importa dati sulla **relying party pubblicata online o in una rete locale.**</span><span class="sxs-lookup"><span data-stu-id="6ed12-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="6ed12-117">Il **valore dell'indirizzo dei metadati federativi (nome host o URL)** deve essere impostato su `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="6ed12-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="6ed12-118">Fare quindi clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6ed12-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="6ed12-119">Nella pagina **Seleziona origine dati** digitare il nome visualizzato, ad esempio Microsoft Office **365 Identity Platform WorldWide.**</span><span class="sxs-lookup"><span data-stu-id="6ed12-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="6ed12-120">Fare quindi clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6ed12-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="6ed12-121">Nella pagina della procedura guidata **Configure Multi-factor Authentication Now?** selezionare la scelta appropriata in base ai requisiti di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="6ed12-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="6ed12-122">Se si è ancorati all'impostazione predefinita, selezionare Non si desidera configurare le impostazioni di autenticazione a più fattori per questa attendibilità **relying party in questo momento.**</span><span class="sxs-lookup"><span data-stu-id="6ed12-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="6ed12-123">Se lo si desidera, è possibile modificare questa impostazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="6ed12-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="6ed12-124">Nella pagina **Scegli regole di autorizzazione rilascio** mantenere Selezionata l'opzione Consenti a tutti gli utenti di accedere a questa **relying party** fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="6ed12-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="6ed12-125">Fare **clic su** Avanti nella pagina Pronto per **aggiungere** attendibilità per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="6ed12-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="6ed12-126">Fare **clic su** Chiudi nella **pagina** Fine.</span><span class="sxs-lookup"><span data-stu-id="6ed12-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="6ed12-127">Chiudendo la procedura guidata, viene stabilita l'attendibilità del componente con i servizi globali di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6ed12-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="6ed12-128">Tuttavia, non sono ancora configurate regole di trasformazione rilascio.</span><span class="sxs-lookup"><span data-stu-id="6ed12-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="6ed12-129">È possibile utilizzare [la Guida di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) per generare le regole corrette di trasformazione rilascio.</span><span class="sxs-lookup"><span data-stu-id="6ed12-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="6ed12-130">Le regole attestazione generate create con la Guida di AD FS possono essere aggiunte manualmente tramite la console di gestione di AD FS o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ed12-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="6ed12-131">La Guida di AD FS genererà gli script di PowerShell necessari che devono essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="6ed12-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="6ed12-132">Eseguire **la guida Genera** attestazioni in ADFS e copiare lo script di trasformazione delle attestazioni di PowerShell utilizzando l'opzione **Copia** nell'angolo superiore destro dello script.</span><span class="sxs-lookup"><span data-stu-id="6ed12-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="6ed12-133">Apri l'editor di testo preferito e incolla lo script di PowerShell in una nuova finestra di testo.</span><span class="sxs-lookup"><span data-stu-id="6ed12-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="6ed12-134">Aggiungere le righe di PowerShell seguenti alla fine dello script incollato dal passaggio 2</span><span class="sxs-lookup"><span data-stu-id="6ed12-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="6ed12-135">Safe and execute the PowerShell script.</span><span class="sxs-lookup"><span data-stu-id="6ed12-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="6ed12-136">Verificare che siano presenti due trust relying party. uno per Microsoft Cloud Deutschland e uno per il servizio Office 365 Global.</span><span class="sxs-lookup"><span data-stu-id="6ed12-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="6ed12-137">Eseguire il backup dei trust utilizzando [questa procedura.](#backup)</span><span class="sxs-lookup"><span data-stu-id="6ed12-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="6ed12-138">Salvarlo con il nome **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="6ed12-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="6ed12-139">Completare la migrazione back-end e verificare che ADFS funzioni ancora durante il processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="6ed12-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="6ed12-140">Ripristino di emergenza AD FS (database WID)</span><span class="sxs-lookup"><span data-stu-id="6ed12-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="6ed12-141">Per ripristinare la farm AD FS in uno strumento di ripristino rapido [di ADFS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) di emergenza deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6ed12-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="6ed12-142">Pertanto, lo strumento deve essere scaricato e prima dell'inizio della migrazione deve essere creato e archiviato in modo sicuro un backup.</span><span class="sxs-lookup"><span data-stu-id="6ed12-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="6ed12-143">In questo esempio (ambienti TAT) sono stati eseguiti i comandi seguenti per eseguire il backup della farm:</span><span class="sxs-lookup"><span data-stu-id="6ed12-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="6ed12-144">Eseguire il backup di una farm AD FS</span><span class="sxs-lookup"><span data-stu-id="6ed12-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="6ed12-145">Installare lo strumento di ripristino rapido AD FS nel server AD FS primario.</span><span class="sxs-lookup"><span data-stu-id="6ed12-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="6ed12-146">Importare il modulo in una sessione di PowerShell con questo comando.</span><span class="sxs-lookup"><span data-stu-id="6ed12-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="6ed12-147">Eseguire il comando di backup:</span><span class="sxs-lookup"><span data-stu-id="6ed12-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="6ed12-148">Archiviare il backup in modo sicuro in una destinazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="6ed12-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="6ed12-149">Ripristinare una farm AD FS</span><span class="sxs-lookup"><span data-stu-id="6ed12-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="6ed12-150">Se la farm ha avuto completamente esito negativo e non è possibile tornare alla farm precedente, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6ed12-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="6ed12-151">Spostare il backup generato e archiviato in precedenza nel nuovo server ADFS primario.</span><span class="sxs-lookup"><span data-stu-id="6ed12-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="6ed12-152">Eseguire il seguente `Restore-ADFS` comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ed12-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="6ed12-153">Se necessario, importare il certificato SSL di AD FS in anticipo.</span><span class="sxs-lookup"><span data-stu-id="6ed12-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="6ed12-154">Puntare i nuovi record DNS o il servizio di bilanciamento del carico ai nuovi server AD FS.</span><span class="sxs-lookup"><span data-stu-id="6ed12-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="6ed12-155">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="6ed12-155">More information</span></span>

<span data-ttu-id="6ed12-156">Guida introduttiva:</span><span class="sxs-lookup"><span data-stu-id="6ed12-156">Getting started:</span></span>

- [<span data-ttu-id="6ed12-157">Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche</span><span class="sxs-lookup"><span data-stu-id="6ed12-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="6ed12-158">Assistenza per la migrazione di Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="6ed12-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="6ed12-159">Come acconsentire esplicitamente a eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="6ed12-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="6ed12-160">Esperienza del cliente durante la migrazione</span><span class="sxs-lookup"><span data-stu-id="6ed12-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="6ed12-161">Passaggio attraverso la transizione:</span><span class="sxs-lookup"><span data-stu-id="6ed12-161">Moving through the transition:</span></span>

- [<span data-ttu-id="6ed12-162">Azioni ed impatti sulle fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="6ed12-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="6ed12-163">Pre-lavoro aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="6ed12-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="6ed12-164">Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="6ed12-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="6ed12-165">App cloud:</span><span class="sxs-lookup"><span data-stu-id="6ed12-165">Cloud apps:</span></span>

- [<span data-ttu-id="6ed12-166">Informazioni sul programma di migrazione di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6ed12-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="6ed12-167">Informazioni sul programma di migrazione di Power BI</span><span class="sxs-lookup"><span data-stu-id="6ed12-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="6ed12-168">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ed12-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
