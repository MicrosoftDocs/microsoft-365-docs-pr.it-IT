---
title: Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Per ulteriori informazioni, vedere l'articolo relativo a Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840302"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="d1916-103">Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali</span><span class="sxs-lookup"><span data-stu-id="d1916-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="d1916-104">Anche se l'obiettivo è quello di fornire tutte le caratteristiche e le funzionalità commerciali ai clienti in Cina con la nostra Azure Information Protection (AIP) per Office 365 gestito dall'offerta di 21Vianet, ci sono alcune funzionalità mancanti che vorremmo evidenziare.</span><span class="sxs-lookup"><span data-stu-id="d1916-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="d1916-105">L'elenco seguente include gli spazi vuoti esistenti tra Azure Information Protection per Office 365 gestito da 21Vianet e le offerte commerciali del gennaio 2021:</span><span class="sxs-lookup"><span data-stu-id="d1916-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="d1916-106">Information Rights Management (IRM) è supportato solo per le app Microsoft 365 per Enterprise (Build 11731,10000 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="d1916-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="d1916-107">Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="d1916-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="d1916-108">La migrazione da Active Directory Rights Management Services (AD RMS) a Azure Information Protection non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="d1916-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="d1916-109">È supportata la condivisione di messaggi di posta elettronica protetti per gli utenti nel cloud commerciale.</span><span class="sxs-lookup"><span data-stu-id="d1916-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="d1916-110">La condivisione dei documenti e degli allegati di posta elettronica per gli utenti nel cloud commerciale non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="d1916-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="d1916-111">Questo include Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale, non Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale e gli utenti con una licenza RMS per i singoli.</span><span class="sxs-lookup"><span data-stu-id="d1916-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="d1916-112">IRM con SharePoint (siti e raccolte protette con IRM) non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="d1916-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="d1916-113">L'estensione del dispositivo mobile per AD RMS non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="d1916-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="d1916-114">Il [Visualizzatore per dispositivi mobili](/azure/information-protection/rms-client/mobile-app-faq) non è supportato da Azure China 21ViaNet.</span><span class="sxs-lookup"><span data-stu-id="d1916-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="d1916-115">Configurazione di Azure Information Protection per i clienti in Cina</span><span class="sxs-lookup"><span data-stu-id="d1916-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="d1916-116">Abilitare Rights Management per il tenant</span><span class="sxs-lookup"><span data-stu-id="d1916-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="d1916-117">Affinché la crittografia funzioni correttamente, è necessario che il server RMS sia abilitato per il tenant.</span><span class="sxs-lookup"><span data-stu-id="d1916-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="d1916-118">Controllare se RMS è abilitato:</span><span class="sxs-lookup"><span data-stu-id="d1916-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="d1916-119">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="d1916-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="d1916-120">Se il modulo di AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="d1916-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="d1916-121">Importare il modulo utilizzando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="d1916-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="d1916-122">Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="d1916-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="d1916-123">Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="d1916-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="d1916-124">Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="d1916-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="d1916-125">Configurazione DNS per la crittografia (Windows)</span><span class="sxs-lookup"><span data-stu-id="d1916-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="d1916-126">Affinché la crittografia funzioni correttamente, le applicazioni client di Office devono connettersi all'istanza di Cina del servizio e bootstrap da tale posizione.</span><span class="sxs-lookup"><span data-stu-id="d1916-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="d1916-127">Per reindirizzare le applicazioni client all'istanza del servizio appropriato, è necessario che l'amministratore del tenant configuri un record DNS SRV con informazioni sull'URL di Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="d1916-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="d1916-128">Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d1916-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="d1916-129">Inoltre, si presuppone che gli utenti accedano con un nome utente basato sul dominio di proprietà del tenant (ad esempio, `joe@contoso.cn` ) e non sul `onmschina` nome utente (ad esempio, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="d1916-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="d1916-130">Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.</span><span class="sxs-lookup"><span data-stu-id="d1916-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="d1916-131">Ottenere l'ID RMS:</span><span class="sxs-lookup"><span data-stu-id="d1916-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="d1916-132">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="d1916-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="d1916-133">Se il modulo di AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="d1916-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="d1916-134">Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="d1916-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="d1916-135">Esegui `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.</span><span class="sxs-lookup"><span data-stu-id="d1916-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="d1916-136">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="d1916-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="d1916-137">Servizio = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="d1916-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="d1916-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="d1916-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="d1916-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="d1916-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="d1916-140">Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)</span><span class="sxs-lookup"><span data-stu-id="d1916-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="d1916-141">Priorità, peso, secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="d1916-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="d1916-142">Associare il dominio personalizzato al tenant nel portale di [Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="d1916-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="d1916-143">In questo modo verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.</span><span class="sxs-lookup"><span data-stu-id="d1916-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="d1916-144">Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d1916-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="d1916-145">Nel processo di verifica, potrebbero essere necessarie ulteriori modifiche DNS.</span><span class="sxs-lookup"><span data-stu-id="d1916-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="d1916-146">Dopo aver effettuato la verifica, è possibile creare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1916-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="d1916-147">Configurazione DNS per la crittografia (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="d1916-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="d1916-148">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="d1916-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="d1916-149">Servizio = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="d1916-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="d1916-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="d1916-150">Protocol = `_http`</span></span>
- <span data-ttu-id="d1916-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="d1916-151">Name = `_tcp`</span></span>
- <span data-ttu-id="d1916-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="d1916-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="d1916-153">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="d1916-153">Port = `80`</span></span>
- <span data-ttu-id="d1916-154">Priorità, peso, secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="d1916-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="d1916-155">Configurazione client AIP</span><span class="sxs-lookup"><span data-stu-id="d1916-155">AIP client configuration</span></span>

<span data-ttu-id="d1916-156">Il client AIP unificato può essere scaricato dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="d1916-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="d1916-157">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="d1916-157">For more information, see:</span></span>

- [<span data-ttu-id="d1916-158">Documentazione relativa alla protezione delle informazioni di Azure</span><span class="sxs-lookup"><span data-stu-id="d1916-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="d1916-159">AIP cronologia delle versioni e criteri di supporto</span><span class="sxs-lookup"><span data-stu-id="d1916-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="d1916-160">Requisiti di sistema AIP</span><span class="sxs-lookup"><span data-stu-id="d1916-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="d1916-161">Guida introduttiva a AIP: distribuire il client AIP</span><span class="sxs-lookup"><span data-stu-id="d1916-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="d1916-162">Guida all'amministratore di AIP</span><span class="sxs-lookup"><span data-stu-id="d1916-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="d1916-163">Guida per l'utente AIP</span><span class="sxs-lookup"><span data-stu-id="d1916-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="d1916-164">Informazioni sulle etichette di riservatezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1916-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="d1916-165">Configurazione delle app AIP (solo client di etichette unificate)</span><span class="sxs-lookup"><span data-stu-id="d1916-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="d1916-166">Per la soluzione di etichettatura unificata, le app AIP su Windows richiedono la seguente chiave del registro di sistema per indirizzarle al cloud Sovereign appropriato per Azure China:</span><span class="sxs-lookup"><span data-stu-id="d1916-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="d1916-167">Nodo del registro di sistema = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="d1916-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="d1916-168">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="d1916-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="d1916-169">Valore = `6` (impostazione predefinita = 0)</span><span class="sxs-lookup"><span data-stu-id="d1916-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="d1916-170">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="d1916-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1916-171">Assicurarsi di non eliminare la chiave del registro di sistema dopo una disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="d1916-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="d1916-172">Se la chiave è vuota, errata o inesistente, la funzionalità si comporterà come valore predefinito (valore predefinito = 0 per il cloud commerciale).</span><span class="sxs-lookup"><span data-stu-id="d1916-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="d1916-173">Se la chiave è vuota o non è corretta, al registro viene aggiunto anche un errore di stampa.</span><span class="sxs-lookup"><span data-stu-id="d1916-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="d1916-174">Gestire i processi di analisi del contenuto di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="d1916-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="d1916-175">Per gestire i processi di analisi del contenuto di Azure Information Protection con un server di Azure China scanner, utilizzare i cmdlet seguenti anziché il portale di Azure:</span><span class="sxs-lookup"><span data-stu-id="d1916-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="d1916-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d1916-176">Cmdlet</span></span> | <span data-ttu-id="d1916-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1916-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="d1916-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="d1916-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="d1916-179">Aggiunge un nuovo repository al processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1916-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="d1916-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="d1916-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="d1916-181">Ottiene informazioni dettagliate sul processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1916-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="d1916-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="d1916-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="d1916-183">Ottiene informazioni dettagliate sui repository definiti per il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1916-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="d1916-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="d1916-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="d1916-185">Elimina il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1916-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="d1916-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="d1916-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="d1916-187">Rimuove un repository dal processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1916-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="d1916-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="d1916-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="d1916-189">Definisce le impostazioni per il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1916-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="d1916-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="d1916-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="d1916-191">Definisce le impostazioni per un archivio esistente nel processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1916-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="d1916-192">Per ulteriori informazioni, vedere [gestire i processi di analisi del contenuto utilizzando solo PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="d1916-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>