---
title: Passaggi di migrazione AD FS per la migrazione da Microsoft Cloud Deutschland
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
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688666"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="a357d-103">Passaggi di migrazione AD FS per la migrazione da Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="a357d-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="a357d-104">Per eseguire la migrazione della farm di Active Directory Federation Services (AD FS) da Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="a357d-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="a357d-105">Eseguire il backup delle impostazioni di ADFS, incluse le informazioni sull'attendibilità FF con [questi passaggi](#backup).</span><span class="sxs-lookup"><span data-stu-id="a357d-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="a357d-106">Denominare il backup di **Microsoft cloud Deutschland_Only** per indicare che contiene solo le informazioni sul tenant di Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="a357d-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="a357d-107">Testare il ripristino utilizzando il backup di Microsoft Cloud Deutschland_Only, la farm ADFS dovrebbe continuare a funzionare solo con Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="a357d-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="a357d-108">Creare una nuova relazione di trust di relying party da **adfs > servizi di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="a357d-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="a357d-109">In **Relying Party Trusts** nella console di gestione ad FS, selezionare **Aggiungi attendibilità componente**.</span><span class="sxs-lookup"><span data-stu-id="a357d-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="a357d-110">Scegliere **Avanti** nella pagina **iniziale** dell'aggiunta guidata attendibilità componente.</span><span class="sxs-lookup"><span data-stu-id="a357d-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="a357d-111">Nella pagina **Selezione origine dati** selezionare **Importa dati relativi al componente pubblicato online o su una rete locale**.</span><span class="sxs-lookup"><span data-stu-id="a357d-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="a357d-112">Il valore dell' **indirizzo dei metadati di federazione (nome host o URL)** è impostato su `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="a357d-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="a357d-113">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a357d-113">Click **Next**.</span></span>
7. <span data-ttu-id="a357d-114">Nella pagina **Selezione origine dati** Digitare il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a357d-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="a357d-115">Microsoft consiglia Microsoft **Office 365 Identity Platform in tutto il mondo**.</span><span class="sxs-lookup"><span data-stu-id="a357d-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="a357d-116">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a357d-116">Click **Next**.</span></span>
8. <span data-ttu-id="a357d-117">Fare clic su **Avanti** per configurare l'autenticazione a più **fattori in questo momento**, **scegliere regole di autorizzazione di rilascio** e **pronto per l'aggiunta di pagine attendibili** .</span><span class="sxs-lookup"><span data-stu-id="a357d-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="a357d-118">Fare clic su **Chiudi** nella pagina **fine** .</span><span class="sxs-lookup"><span data-stu-id="a357d-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="a357d-119">Chiudendo la procedura guidata, viene stabilita la relazione di trust relying party ai servizi di Office 365 eSTS.</span><span class="sxs-lookup"><span data-stu-id="a357d-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="a357d-120">Tuttavia, non vengono stabilite regole di trasformazione dell'emissione.</span><span class="sxs-lookup"><span data-stu-id="a357d-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="a357d-121">È possibile utilizzare la [Guida di ADFS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) per generare le regole di trasformazione di rilascio corrette.</span><span class="sxs-lookup"><span data-stu-id="a357d-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="a357d-122">Le regole attestazione generate create con la Guida di ADFS possono essere aggiunte manualmente tramite la console di gestione di ADFS o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a357d-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="a357d-123">La Guida di ADFS genererà gli script di PowerShell necessari che devono essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="a357d-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="a357d-124">Eseguire **genera attestazioni** sulla guida di ADFS e copiare lo script di trasformazione delle attestazioni di PowerShell utilizzando l'opzione **copia** all'angolo superiore destro dello script.</span><span class="sxs-lookup"><span data-stu-id="a357d-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="a357d-125">Incollare la PowerShell generata nei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="a357d-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="a357d-126">Eseguire lo script completato.</span><span class="sxs-lookup"><span data-stu-id="a357d-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="a357d-127">Verificare che siano presenti due trust relying party. uno per tutto il mondo e uno per BF.</span><span class="sxs-lookup"><span data-stu-id="a357d-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="a357d-128">Eseguire il backup dei trust utilizzando [questi passaggi](#backup).</span><span class="sxs-lookup"><span data-stu-id="a357d-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="a357d-129">Salvarlo con il nome **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="a357d-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="a357d-130">Completare la migrazione di back-end e verificare che ADFS funzioni ancora durante il processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="a357d-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="a357d-131">Ripristino di emergenza ADFS (database WID)</span><span class="sxs-lookup"><span data-stu-id="a357d-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="a357d-132">Per ripristinare la farm ADFS in uno strumento di [ripristino rapido di emergenza ad FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) , è necessario utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="a357d-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="a357d-133">Pertanto, è necessario scaricare lo strumento e prima dell'inizio della migrazione è necessario creare un backup e archiviarlo in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="a357d-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="a357d-134">In questo esempio (ambienti TAT) sono stati eseguiti i comandi seguenti per eseguire il backup della farm:</span><span class="sxs-lookup"><span data-stu-id="a357d-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="a357d-135">Eseguire il backup di una farm AD FS</span><span class="sxs-lookup"><span data-stu-id="a357d-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="a357d-136">Installare lo strumento AD FS per il ripristino rapido sul server ADFS primario.</span><span class="sxs-lookup"><span data-stu-id="a357d-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="a357d-137">Importare il modulo in una sessione di PowerShell con questo comando.</span><span class="sxs-lookup"><span data-stu-id="a357d-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="a357d-138">Eseguire il comando backup:</span><span class="sxs-lookup"><span data-stu-id="a357d-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="a357d-139">Archiviare il backup in modo sicuro su una destinazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="a357d-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="a357d-140">Ripristinare una farm AD FS</span><span class="sxs-lookup"><span data-stu-id="a357d-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="a357d-141">Se la farm non è stata completata correttamente e non è possibile tornare alla farm precedente, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="a357d-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="a357d-142">Spostare il backup precedentemente generato e archiviato nel nuovo server ADFS primario.</span><span class="sxs-lookup"><span data-stu-id="a357d-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="a357d-143">Eseguire il seguente `Restore-ADFS` comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a357d-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="a357d-144">Se necessario, importare il certificato SSL ADFS in anticipo.</span><span class="sxs-lookup"><span data-stu-id="a357d-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="a357d-145">Indirizzare i nuovi record DNS o il bilanciamento del carico ai nuovi server AD FS.</span><span class="sxs-lookup"><span data-stu-id="a357d-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="a357d-146">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a357d-146">More information</span></span>

<span data-ttu-id="a357d-147">Guida introduttiva:</span><span class="sxs-lookup"><span data-stu-id="a357d-147">Getting started:</span></span>

- [<span data-ttu-id="a357d-148">Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco</span><span class="sxs-lookup"><span data-stu-id="a357d-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="a357d-149">Assistenza per la migrazione di Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="a357d-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="a357d-150">Come acconsentire esplicitamente a eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="a357d-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="a357d-151">Esperienza del cliente durante la migrazione</span><span class="sxs-lookup"><span data-stu-id="a357d-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="a357d-152">Spostamento attraverso la transizione:</span><span class="sxs-lookup"><span data-stu-id="a357d-152">Moving through the transition:</span></span>

- [<span data-ttu-id="a357d-153">Azioni ed impatti sulle fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="a357d-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="a357d-154">Ulteriore prelavoro</span><span class="sxs-lookup"><span data-stu-id="a357d-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="a357d-155">Ulteriori informazioni su [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="a357d-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="a357d-156">App Cloud:</span><span class="sxs-lookup"><span data-stu-id="a357d-156">Cloud apps:</span></span>

- [<span data-ttu-id="a357d-157">Informazioni sul programma di migrazione di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a357d-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="a357d-158">Informazioni sul programma di migrazione di Power BI</span><span class="sxs-lookup"><span data-stu-id="a357d-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="a357d-159">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a357d-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
