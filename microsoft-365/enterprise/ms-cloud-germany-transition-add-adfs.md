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
ms.openlocfilehash: c8e784c8e582185b4bdebc0cb359cc4c19503d1a
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339611"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="1c3ba-103">Passaggi di migrazione di AD FS per la migrazione da Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="1c3ba-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="1c3ba-104">Questa modifica alla configurazione deve essere applicata ogni volta prima dell'avvio della fase 2.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="1c3ba-105">Una volta completata la fase 2, la modifica della configurazione funzionerà e sarà possibile accedere tramite Office 365 endpoint globali, ad esempio `https://admin.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="1c3ba-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://admin.microsoft.com`.</span></span> <span data-ttu-id="1c3ba-106">Se si implementa la modifica della configurazione prima della fase 2, gli endpoint globali di Office 365 non funzionano ancora, ma la nuova relazione di trust della relying party fa ancora parte della configurazione di Active Directory Federation Services (AD FS). </span><span class="sxs-lookup"><span data-stu-id="1c3ba-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="1c3ba-107">I clienti che utilizzano l'autenticazione federata con Active Directory Federation Services (ADFS) non devono apportare modifiche agli URI dell'autorità emittente utilizzati per tutte le autenticazioni con Servizi di dominio Active Directory locale durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="1c3ba-108">La modifica degli URI dell'autorità emittente causa errori di autenticazione per gli utenti nel dominio.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="1c3ba-109">Gli URI dell'autorità emittente possono essere modificati direttamente  in AD FS o quando un dominio viene convertito da gestito a _federato_ e viceversa.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="1c3ba-110">È consigliabile non aggiungere, rimuovere o convertire un dominio federato nel tenant di Azure AD di cui è stata eseguita la migrazione.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="1c3ba-111">Gli URI dell'autorità emittente possono essere modificati al termine della migrazione.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="1c3ba-112">Per preparare la farm AD FS per la migrazione da Microsoft Cloud Deutschland, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="1c3ba-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="1c3ba-113">Eseguire il backup delle impostazioni di AD FS, inclusa l'attendibilità del relying party Microsoft Cloud Deutschland esistente, con [questi passaggi.](#backup)</span><span class="sxs-lookup"><span data-stu-id="1c3ba-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="1c3ba-114">Assegnare al backup **il nome MicrosoftCloudDeutschlandOnly** per indicare che contiene solo le informazioni sul tenant di Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1c3ba-115">Il backup conterrà non solo l'Office 365 Relying Party Trust per Microsoft Cloud Deutschland, ma anche tutti gli altri trust relying party presenti nella rispettiva farm AD FS.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="1c3ba-116">Testare il ripristino utilizzando il backup MicrosoftCloudDeutschlandOnly, la farm AD FS deve continuare a funzionare solo come Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="1c3ba-117">Dopo aver completato e testato il backup di AD FS, eseguire la procedura seguente per aggiungere un nuovo trust relying party alla configurazione di ADFS:</span><span class="sxs-lookup"><span data-stu-id="1c3ba-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="1c3ba-118">Aprire la console di gestione AD FS.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="1c3ba-119">Nel riquadro sinistro della console di gestione ADFS passare al menu **Relying Party Trusts.**</span><span class="sxs-lookup"><span data-stu-id="1c3ba-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="1c3ba-120">Nel riquadro destro seleziona **Aggiungi attendibilità componente...**</span><span class="sxs-lookup"><span data-stu-id="1c3ba-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="1c3ba-121">Selezionare **Avvia** nella pagina **iniziale** della procedura guidata Aggiungi attendibilità componente.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="1c3ba-122">Nella pagina **Seleziona origine dati** selezionare Importa dati sulla **relying party pubblicata online o in una rete locale.**</span><span class="sxs-lookup"><span data-stu-id="1c3ba-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="1c3ba-123">Il **valore dell'indirizzo dei metadati federativi (nome host o URL)** deve essere impostato su `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="1c3ba-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="1c3ba-124">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-124">Click **Next**.</span></span>

6. <span data-ttu-id="1c3ba-125">Nella pagina **Specifica nome visualizzato** digitare il nome visualizzato, ad esempio Microsoft Office 365 Identity Platform **WorldWide.**</span><span class="sxs-lookup"><span data-stu-id="1c3ba-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="1c3ba-126">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-126">Click **Next**.</span></span>

7. <span data-ttu-id="1c3ba-127">Se si utilizza ADFS in Windows Server 2012, nella pagina della procedura guidata Configurare l'autenticazione a più fattori **ora?** selezionare la scelta appropriata in base ai requisiti di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="1c3ba-128">Se si è ancorati all'impostazione predefinita, selezionare Non si desidera configurare le impostazioni di autenticazione a più fattori per questa attendibilità **relying party in questo momento.**</span><span class="sxs-lookup"><span data-stu-id="1c3ba-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="1c3ba-129">Se lo si desidera, è possibile modificare questa impostazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="1c3ba-130">Per AD FS 2012: nella pagina **Scegli** regole di autorizzazione rilascio mantenere Selezionata l'opzione Consenti a tutti gli utenti di accedere a questa **relying party** e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="1c3ba-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

9. <span data-ttu-id="1c3ba-131">Per AD FS 2016 e AD FS 2019: nella pagina **Scegli** criteri di controllo di accesso selezionare il criterio di controllo di accesso appropriato e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="1c3ba-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="1c3ba-132">Se non si sceglie nessuno, l'attendibilità del componente **NON funzionerà.**</span><span class="sxs-lookup"><span data-stu-id="1c3ba-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

10. <span data-ttu-id="1c3ba-133">Fare **clic su** Avanti nella pagina Pronto per **aggiungere** attendibilità per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

11. <span data-ttu-id="1c3ba-134">Fare **clic su** Chiudi nella **pagina** Fine.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="1c3ba-135">Chiudendo la procedura guidata, viene stabilita l'attendibilità relying party Office 365 servizio globale.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="1c3ba-136">Tuttavia, non sono ancora configurate regole di trasformazione rilascio.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="1c3ba-137">È possibile utilizzare [la Guida di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) per generare le regole corrette di trasformazione rilascio.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="1c3ba-138">Le regole attestazione generate create con la Guida di AD FS possono essere aggiunte manualmente tramite la console di gestione di AD FS o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="1c3ba-139">La Guida di AD FS genererà gli script di PowerShell necessari che devono essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c3ba-140">[La Guida di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) genererà le regole di trasformazione di rilascio standard che vengono forniti con il prodotto.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="1c3ba-141">Tuttavia, se le regole di trasformazione di rilascio personalizzate sono presenti in Microsoft Cloud Deutschland Relying Party Trust (ad esempio, URI dell'autorità emittente personalizzata, ID non standard non modificabili o altre personalizzazioni), le regole generate dalla Guida di AD FS devono essere modificate in modo che si adattino alla logica personalizzata attualmente in uso per l'attendibilità del componente Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="1c3ba-142">Se queste personalizzazioni non sono integrate nelle regole generate tramite la Guida di [ADFS,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)l'autenticazione **Microsoft Office 365 Identity Platform WorldWide** probabilmente non funzionerà per le identità federate. </span><span class="sxs-lookup"><span data-stu-id="1c3ba-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="1c3ba-143">Eseguire **Generate Claims** on AD FS [Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) e copiare lo script di PowerShell usando l'opzione **Copy** nell'angolo superiore destro dello script.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="1c3ba-144">Seguire i passaggi descritti nella Guida [di AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) su come eseguire lo script di PowerShell nella farm AD FS per generare il trust relying party globale.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span> <span data-ttu-id="1c3ba-145">Prima di eseguire lo script, sostituire le righe di codice seguenti nello script generato come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="1c3ba-145">Before you run the script, replace the following code lines in the generated script as outlined below:</span></span>

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. <span data-ttu-id="1c3ba-146">Verificare che siano presenti due relying partyTtrust; uno per Microsoft Cloud Deutschland e uno per il Office 365 Global.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-146">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="1c3ba-147">Il comando seguente può essere utilizzato per il controllo.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-147">The following command can be leveraged for the check.</span></span> <span data-ttu-id="1c3ba-148">Deve restituire due righe e i rispettivi nomi e identificatori.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-148">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="1c3ba-149">Eseguire il backup della configurazione di migrazione completa, inclusi entrambi i trust relying party, utilizzando [questi passaggi.](#backup)</span><span class="sxs-lookup"><span data-stu-id="1c3ba-149">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="1c3ba-150">Salvarlo con il nome **MicrosoftCloudDeutschlandAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-150">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="1c3ba-151">Durante la migrazione del tenant, verificare regolarmente che l'autenticazione AD FS funzioni con Microsoft Cloud Deutschland e microsoft global cloud nei vari passaggi di migrazione supportati.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-151">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="1c3ba-152">Ripristino di emergenza AD FS (database WID)</span><span class="sxs-lookup"><span data-stu-id="1c3ba-152">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="1c3ba-153">Per ripristinare la farm AD FS in uno strumento di ripristino rapido [di ADFS](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) di emergenza deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-153">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="1c3ba-154">Pertanto, lo strumento deve essere scaricato e prima dell'inizio della migrazione deve essere creato e archiviato in modo sicuro un backup.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-154">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="1c3ba-155">In questo esempio sono stati eseguiti i comandi seguenti per eseguire il backup di una farm in esecuzione in un database WID:</span><span class="sxs-lookup"><span data-stu-id="1c3ba-155">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="1c3ba-156">Eseguire il backup di una farm AD FS</span><span class="sxs-lookup"><span data-stu-id="1c3ba-156">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="1c3ba-157">Installare lo strumento di ripristino rapido AD FS nel server AD FS primario.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-157">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="1c3ba-158">Importare il modulo in una sessione di PowerShell con questo comando.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-158">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="1c3ba-159">Eseguire il comando di backup:</span><span class="sxs-lookup"><span data-stu-id="1c3ba-159">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="1c3ba-160">Archiviare il backup in modo sicuro in una destinazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-160">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="1c3ba-161">Ripristinare una farm AD FS</span><span class="sxs-lookup"><span data-stu-id="1c3ba-161">Restore an AD FS Farm</span></span>

<span data-ttu-id="1c3ba-162">Se la farm ha avuto completamente esito negativo e non è possibile tornare alla farm precedente, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-162">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="1c3ba-163">Spostare il backup generato e archiviato in precedenza nel nuovo server ADFS primario.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-163">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="1c3ba-164">Eseguire il seguente `Restore-ADFS` comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-164">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="1c3ba-165">Se necessario, importare il certificato SSL di AD FS in anticipo.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-165">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="1c3ba-166">Puntare i nuovi record DNS o il servizio di bilanciamento del carico ai nuovi server AD FS.</span><span class="sxs-lookup"><span data-stu-id="1c3ba-166">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="1c3ba-167">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="1c3ba-167">More information</span></span>

<span data-ttu-id="1c3ba-168">Guida introduttiva:</span><span class="sxs-lookup"><span data-stu-id="1c3ba-168">Getting started:</span></span>

- [<span data-ttu-id="1c3ba-169">Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche</span><span class="sxs-lookup"><span data-stu-id="1c3ba-169">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="1c3ba-170">Assistenza per la migrazione di Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="1c3ba-170">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="1c3ba-171">Come acconsentire esplicitamente a eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="1c3ba-171">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="1c3ba-172">Esperienza del cliente durante la migrazione</span><span class="sxs-lookup"><span data-stu-id="1c3ba-172">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="1c3ba-173">Passaggio attraverso la transizione:</span><span class="sxs-lookup"><span data-stu-id="1c3ba-173">Moving through the transition:</span></span>

- [<span data-ttu-id="1c3ba-174">Azioni ed impatti sulle fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="1c3ba-174">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="1c3ba-175">Pre-lavoro aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="1c3ba-175">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="1c3ba-176">Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="1c3ba-176">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="1c3ba-177">App cloud:</span><span class="sxs-lookup"><span data-stu-id="1c3ba-177">Cloud apps:</span></span>

- [<span data-ttu-id="1c3ba-178">Informazioni sul programma di migrazione di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1c3ba-178">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="1c3ba-179">Informazioni sul programma di migrazione di Power BI</span><span class="sxs-lookup"><span data-stu-id="1c3ba-179">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="1c3ba-180">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c3ba-180">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
