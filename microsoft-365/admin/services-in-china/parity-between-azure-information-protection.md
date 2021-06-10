---
title: Supporto di Azure Information Protection Office 365 gestito da 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Altre informazioni su Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e su come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535843"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="65d54-103">Supporto di Azure Information Protection Office 365 gestito da 21Vianet</span><span class="sxs-lookup"><span data-stu-id="65d54-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="65d54-104">In questo articolo vengono illustrate le differenze tra il supporto di Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e le offerte commerciali, nonché istruzioni specifiche per la configurazione di AIP per i clienti in Cina, tra cui come installare lo scanner AIP locale e gestire i processi di analisi del &mdash; contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="65d54-105">Differenze tra AIP per Office 365 gestito da 21Vianet e offerte commerciali</span><span class="sxs-lookup"><span data-stu-id="65d54-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="65d54-106">Anche se il nostro obiettivo è fornire tutte le funzionalità commerciali ai clienti in Cina con la nostra offerta AIP per Office 365 gestita da 21Vianet, alcune funzionalità mancanti sono da evidenziare.</span><span class="sxs-lookup"><span data-stu-id="65d54-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="65d54-107">L'elenco seguente include le lacune esistenti tra AIP per Office 365 gestito da 21Vianet e le offerte commerciali a partire da gennaio 2021:</span><span class="sxs-lookup"><span data-stu-id="65d54-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="65d54-108">Information Rights Management (IRM) è supportato solo per Microsoft 365 Apps for enterprise (build 11731.10000 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="65d54-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="65d54-109">Office 2010, Office 2013 e altre Office 2016 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="65d54-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="65d54-110">La migrazione da Active Directory Rights Management Services (AD RMS) ad AIP non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="65d54-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="65d54-111">È supportata la condivisione di messaggi di posta elettronica protetti con gli utenti nel cloud commerciale.</span><span class="sxs-lookup"><span data-stu-id="65d54-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="65d54-112">La condivisione di documenti e allegati di posta elettronica con gli utenti nel cloud commerciale non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="65d54-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="65d54-113">Sono inclusi Office 365 gestiti da 21 utentiVianet nel cloud commerciale, non Office 365 gestiti da 21 utentiVianet nel cloud commerciale e utenti con una licenza RMS per singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="65d54-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="65d54-114">IRM con SharePoint (siti e raccolte protetti da IRM) non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="65d54-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="65d54-115">L'estensione per dispositivi mobili per AD RMS non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="65d54-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="65d54-116">Il [visualizzatore per](/azure/information-protection/rms-client/mobile-app-faq) dispositivi mobili non è supportato da Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="65d54-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="65d54-117">L'area AIP del portale di Azure non è disponibile per i clienti in Cina.</span><span class="sxs-lookup"><span data-stu-id="65d54-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="65d54-118">Utilizzare [i comandi di PowerShell](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) invece di eseguire azioni nel portale, ad esempio la gestione e l'esecuzione dei processi di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="65d54-119">Configurare AIP per i clienti in Cina</span><span class="sxs-lookup"><span data-stu-id="65d54-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="65d54-120">Per configurare AIP per i clienti in Cina:</span><span class="sxs-lookup"><span data-stu-id="65d54-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="65d54-121">[Abilitare Rights Management per il tenant](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="65d54-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="65d54-122">[Aggiungere l'entità servizio di sincronizzazione](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)di Microsoft Information Protection .</span><span class="sxs-lookup"><span data-stu-id="65d54-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="65d54-123">[Configurare la crittografia DNS](#step-3-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="65d54-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="65d54-124">[Installare e configurare il client di etichettatura unificato AIP](#step-4-install-and-configure-the-aip-unified-labeling-client).</span><span class="sxs-lookup"><span data-stu-id="65d54-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="65d54-125">[Configurare le app AIP in Windows](#step-5-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="65d54-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="65d54-126">[Installare lo scanner AIP locale e gestire i processi di analisi del contenuto.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="65d54-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="65d54-127">Passaggio 1: Abilitare Rights Management per il tenant</span><span class="sxs-lookup"><span data-stu-id="65d54-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="65d54-128">Per il corretto funzionamento della crittografia, è necessario che RMS sia abilitato per il tenant.</span><span class="sxs-lookup"><span data-stu-id="65d54-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="65d54-129">Verificare se RMS è abilitato:</span><span class="sxs-lookup"><span data-stu-id="65d54-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="65d54-130">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="65d54-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="65d54-131">Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="65d54-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="65d54-132">Importare il modulo utilizzando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="65d54-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="65d54-133">Connessione al servizio tramite `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="65d54-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="65d54-134">Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="65d54-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="65d54-135">Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="65d54-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="65d54-136">Passaggio 2: Aggiungere l'entità servizio di sincronizzazione di Microsoft Information Protection</span><span class="sxs-lookup"><span data-stu-id="65d54-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="65d54-137">L'entità servizio di **sincronizzazione** di Microsoft Information Protection non è disponibile nei tenant di Azure Cina per impostazione predefinita ed è necessaria per Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="65d54-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="65d54-138">Creare manualmente questa entità servizio utilizzando il cmdlet [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) e `870c4f2e-85b6-4d43-bdda-6ed9a579b725` l'ID applicazione per il servizio di sincronizzazione di Microsoft Information Protection.</span><span class="sxs-lookup"><span data-stu-id="65d54-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="65d54-139">Dopo aver aggiunto l'entità servizio, aggiungere le autorizzazioni rilevanti necessarie al servizio.</span><span class="sxs-lookup"><span data-stu-id="65d54-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="65d54-140">Passaggio 3: Configurare la crittografia DNS</span><span class="sxs-lookup"><span data-stu-id="65d54-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="65d54-141">Per il corretto funzionamento della crittografia, Office applicazioni client devono connettersi all'istanza cina del servizio e avviare il bootstrap da lì.</span><span class="sxs-lookup"><span data-stu-id="65d54-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="65d54-142">Per reindirizzare le applicazioni client all'istanza del servizio giusta, l'amministratore tenant deve configurare un record DNS SRV con informazioni sull'URL di Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="65d54-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="65d54-143">Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="65d54-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="65d54-144">Inoltre, il presupposto è che gli utenti accederanno con un nome utente basato sul dominio di proprietà del tenant (ad esempio, ) e non con il nome `joe@contoso.cn` `onmschina` utente (ad esempio, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="65d54-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="65d54-145">Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.</span><span class="sxs-lookup"><span data-stu-id="65d54-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="65d54-146">Configurare la crittografia DNS - Windows</span><span class="sxs-lookup"><span data-stu-id="65d54-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="65d54-147">Ottenere l'ID RMS:</span><span class="sxs-lookup"><span data-stu-id="65d54-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="65d54-148">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="65d54-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="65d54-149">Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="65d54-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="65d54-150">Connessione al servizio tramite `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="65d54-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="65d54-151">Eseguire `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.</span><span class="sxs-lookup"><span data-stu-id="65d54-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="65d54-152">Accedere al provider DNS, accedere alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="65d54-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="65d54-153">Servizio = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="65d54-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="65d54-154">Protocollo = `_http`</span><span class="sxs-lookup"><span data-stu-id="65d54-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="65d54-155">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="65d54-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="65d54-156">Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)</span><span class="sxs-lookup"><span data-stu-id="65d54-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="65d54-157">Priorità, Peso, Secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="65d54-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="65d54-158">Associare il dominio personalizzato al tenant nel [portale di Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="65d54-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="65d54-159">Verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.</span><span class="sxs-lookup"><span data-stu-id="65d54-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="65d54-160">Accedere all'interfaccia Microsoft 365 di amministrazione con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="65d54-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="65d54-161">Nel processo di verifica potrebbero essere necessarie ulteriori modifiche al DNS.</span><span class="sxs-lookup"><span data-stu-id="65d54-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="65d54-162">Al termine della verifica, gli utenti possono essere creati.</span><span class="sxs-lookup"><span data-stu-id="65d54-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="65d54-163">Configurare la crittografia DNS - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="65d54-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="65d54-164">Accedere al provider DNS, accedere alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="65d54-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="65d54-165">Servizio = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="65d54-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="65d54-166">Protocollo = `_http`</span><span class="sxs-lookup"><span data-stu-id="65d54-166">Protocol = `_http`</span></span>
- <span data-ttu-id="65d54-167">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="65d54-167">Name = `_tcp`</span></span>
- <span data-ttu-id="65d54-168">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="65d54-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="65d54-169">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="65d54-169">Port = `80`</span></span>
- <span data-ttu-id="65d54-170">Priorità, Peso, Secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="65d54-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="65d54-171">Passaggio 4: Installare e configurare il client di etichettatura unificato AIP</span><span class="sxs-lookup"><span data-stu-id="65d54-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="65d54-172">Scaricare e installare il client di etichettatura unificato AIP [dall'Area download Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="65d54-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="65d54-173">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="65d54-173">For more information, see:</span></span>

- [<span data-ttu-id="65d54-174">Documentazione AIP</span><span class="sxs-lookup"><span data-stu-id="65d54-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="65d54-175">Cronologia delle versioni AIP e criteri di supporto</span><span class="sxs-lookup"><span data-stu-id="65d54-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="65d54-176">Requisiti di sistema AIP</span><span class="sxs-lookup"><span data-stu-id="65d54-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="65d54-177">Guida introduttiva AIP: Distribuire il client AIP</span><span class="sxs-lookup"><span data-stu-id="65d54-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="65d54-178">Guida all'amministratore AIP</span><span class="sxs-lookup"><span data-stu-id="65d54-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="65d54-179">Guida per l'utente AIP</span><span class="sxs-lookup"><span data-stu-id="65d54-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="65d54-180">Informazioni sulle Microsoft 365 di riservatezza</span><span class="sxs-lookup"><span data-stu-id="65d54-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="65d54-181">Passaggio 5: Configurare le app AIP Windows</span><span class="sxs-lookup"><span data-stu-id="65d54-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="65d54-182">Le app AIP Windows la chiave del Registro di sistema seguente per puntare al cloud sovrano corretto per Azure Cina:</span><span class="sxs-lookup"><span data-stu-id="65d54-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="65d54-183">Nodo del Registro di sistema = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="65d54-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="65d54-184">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="65d54-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="65d54-185">Value = `6` (valore predefinito = 0)</span><span class="sxs-lookup"><span data-stu-id="65d54-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="65d54-186">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="65d54-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65d54-187">Assicurarsi di non eliminare la chiave del Registro di sistema dopo una disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="65d54-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="65d54-188">Se la chiave è vuota, errata o inesistente, la funzionalità si comporterà come valore predefinito (valore predefinito = 0 per il cloud commerciale).</span><span class="sxs-lookup"><span data-stu-id="65d54-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="65d54-189">Se la chiave è vuota o errata, al registro viene aggiunto anche un errore di stampa.</span><span class="sxs-lookup"><span data-stu-id="65d54-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="65d54-190">Passaggio 6: Installare lo scanner AIP locale e gestire i processi di analisi del contenuto</span><span class="sxs-lookup"><span data-stu-id="65d54-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="65d54-191">Installare lo scanner AIP locale per analizzare la rete e le condivisioni di contenuto alla ricerca di dati sensibili e applicare etichette di classificazione e protezione come configurato nei criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65d54-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="65d54-192">Quando configuri e gestisci i processi di analisi del contenuto, usa la procedura seguente invece dell'interfaccia del portale di [Azure](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) usata dalle offerte commerciali.</span><span class="sxs-lookup"><span data-stu-id="65d54-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="65d54-193">Per ulteriori informazioni, vedere [Che cos'è lo scanner](/azure/information-protection/deploy-aip-scanner) di etichettatura unificato di Azure Information Protection? e Gestire i processi di analisi del contenuto solo tramite [PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="65d54-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="65d54-194">**Per installare e configurare lo scanner:**</span><span class="sxs-lookup"><span data-stu-id="65d54-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="65d54-195">Accedere al computer Windows Server che eseguirà lo scanner.</span><span class="sxs-lookup"><span data-stu-id="65d54-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="65d54-196">Utilizzare un account con diritti di amministratore locale e che dispone delle autorizzazioni per scrivere nel database master SQL Server database master.</span><span class="sxs-lookup"><span data-stu-id="65d54-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="65d54-197">Iniziare con PowerShell chiuso.</span><span class="sxs-lookup"><span data-stu-id="65d54-197">Start with PowerShell closed.</span></span> <span data-ttu-id="65d54-198">Se in precedenza sono stati installati il client AIP e lo scanner, assicurarsi che il **servizio AIPScanner** sia arrestato.</span><span class="sxs-lookup"><span data-stu-id="65d54-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="65d54-199">Aprire una Windows PowerShell sessione con **l'opzione Esegui come** amministratore.</span><span class="sxs-lookup"><span data-stu-id="65d54-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="65d54-200">Eseguire il cmdlet [Install-AIPScanner,](/powershell/module/azureinformationprotection/Install-AIPScanner) specificando l'istanza di SQL Server in cui creare un database per lo scanner di Azure Information Protection e un nome significativo per il cluster di scanner.</span><span class="sxs-lookup"><span data-stu-id="65d54-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="65d54-201">È possibile utilizzare lo stesso nome del cluster nel [comando Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) per associare più nodi scanner allo stesso cluster.</span><span class="sxs-lookup"><span data-stu-id="65d54-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="65d54-202">L'utilizzo dello stesso cluster per più nodi scanner consente a più scanner di lavorare insieme per eseguire le analisi.</span><span class="sxs-lookup"><span data-stu-id="65d54-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="65d54-203">Verificare che il servizio sia installato utilizzando Strumenti **di** amministrazione  >  .</span><span class="sxs-lookup"><span data-stu-id="65d54-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="65d54-204">Il servizio installato è denominato **Scanner di Azure Information Protection** ed è configurato per l'esecuzione utilizzando l'account di servizio dello scanner creato.</span><span class="sxs-lookup"><span data-stu-id="65d54-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="65d54-205">Ottenere un token di Azure da usare con lo scanner.</span><span class="sxs-lookup"><span data-stu-id="65d54-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="65d54-206">Un token Azure AD consente allo scanner di eseguire l'autenticazione nel servizio Azure Information Protection, consentendo l'esecuzione non interattiva dello scanner.</span><span class="sxs-lookup"><span data-stu-id="65d54-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="65d54-207">Aprire il portale di Azure e creare un'applicazione Azure AD per specificare un token di accesso per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="65d54-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="65d54-208">Per ulteriori informazioni, vedere [Come etichettare i file in modo non interattivo per Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)</span><span class="sxs-lookup"><span data-stu-id="65d54-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="65d54-209">Quando si creano e configurano le applicazioni di Azure AD per il  comando [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) nel riquadro Richiedi **autorizzazioni API** viene visualizzata la scheda API utilizzate dall'organizzazione anziché la scheda **API Microsoft.** Seleziona le **API utilizzate dall'organizzazione** per selezionare **Azure Rights Management Services.**</span><span class="sxs-lookup"><span data-stu-id="65d54-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="65d54-210">Dal computer Windows Server, se all'account del servizio  scanner è stato concesso il diritto Di accesso locale per l'installazione, accedere con questo account e avviare una sessione di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65d54-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="65d54-211">Se all'account del servizio  scanner non è possibile concedere il diritto di accesso locale per l'installazione, utilizzare il parametro *OnBehalfOf* con [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), come descritto in Come etichettare i file in modo non interattivo per [Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)</span><span class="sxs-lookup"><span data-stu-id="65d54-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="65d54-212">Eseguire [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specificando i valori copiati dall'applicazione Azure AD:</span><span class="sxs-lookup"><span data-stu-id="65d54-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="65d54-213">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="65d54-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="65d54-214">Lo scanner ora dispone di un token per l'autenticazione in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="65d54-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="65d54-215">Questo token è valido per un anno, due anni o mai, in base alla configurazione del segreto **client dell'app Web /API** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="65d54-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="65d54-216">Quando il token scade, è necessario ripetere questa procedura.</span><span class="sxs-lookup"><span data-stu-id="65d54-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="65d54-217">Eseguire il cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) per impostare lo scanner in modo che funzioni in modalità offline.</span><span class="sxs-lookup"><span data-stu-id="65d54-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="65d54-218">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="65d54-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="65d54-219">Eseguire il cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) per creare un processo di analisi del contenuto predefinito.</span><span class="sxs-lookup"><span data-stu-id="65d54-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="65d54-220">L'unico parametro obbligatorio nel cmdlet **Set-AIPScannerContentScanJob** è **Enforce**.</span><span class="sxs-lookup"><span data-stu-id="65d54-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="65d54-221">È tuttavia possibile definire altre impostazioni per il processo di analisi del contenuto in questo momento.</span><span class="sxs-lookup"><span data-stu-id="65d54-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="65d54-222">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="65d54-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="65d54-223">La sintassi precedente configura le impostazioni seguenti mentre si continua la configurazione:</span><span class="sxs-lookup"><span data-stu-id="65d54-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="65d54-224">Mantiene manuale la pianificazione dell'esecuzione dello *scanner*</span><span class="sxs-lookup"><span data-stu-id="65d54-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="65d54-225">Imposta i tipi di informazioni da individuare in base al criterio di etichettatura di riservatezza</span><span class="sxs-lookup"><span data-stu-id="65d54-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="65d54-226">Non *applica un* criterio di etichettatura di riservatezza</span><span class="sxs-lookup"><span data-stu-id="65d54-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="65d54-227">Etichetta automaticamente i file in base al contenuto, utilizzando l'etichetta predefinita definita per il criterio di etichettatura di riservatezza</span><span class="sxs-lookup"><span data-stu-id="65d54-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="65d54-228">Non *consente la* rietichettatura dei file</span><span class="sxs-lookup"><span data-stu-id="65d54-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="65d54-229">Mantiene i dettagli dei file durante l'analisi e l'etichettatura automatica, tra cui *data* di *modifica,* ultima modifica *e modifica in base ai* valori</span><span class="sxs-lookup"><span data-stu-id="65d54-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="65d54-230">Imposta lo scanner in modo da escludere i file con estensione msg e tmp durante l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="65d54-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="65d54-231">Imposta il proprietario predefinito sull'account che si desidera utilizzare quando si esegue lo scanner</span><span class="sxs-lookup"><span data-stu-id="65d54-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="65d54-232">Utilizzare il cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) per definire gli archivi che si desidera analizzare nel processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="65d54-233">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="65d54-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="65d54-234">Utilizzare una delle sintassi seguenti, a seconda del tipo di repository che si sta aggiungendo:</span><span class="sxs-lookup"><span data-stu-id="65d54-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="65d54-235">Per una condivisione di rete, utilizzare `\\Server\Folder` .</span><span class="sxs-lookup"><span data-stu-id="65d54-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="65d54-236">Per una SharePoint, utilizzare `http://sharepoint.contoso.com/Shared%20Documents/Folder` .</span><span class="sxs-lookup"><span data-stu-id="65d54-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="65d54-237">Per un percorso locale: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="65d54-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="65d54-238">Per un percorso UNC: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="65d54-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="65d54-239">I caratteri jolly non sono supportati e i percorsi WebDav non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="65d54-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="65d54-240">Per modificare l'archivio in un secondo momento, utilizzare invece il cmdlet [Set-AIPScannerRepository.](/powershell/module/azureinformationprotection/set-aipscannerrepository)</span><span class="sxs-lookup"><span data-stu-id="65d54-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="65d54-241">Continuare con i passaggi seguenti in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="65d54-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="65d54-242">Eseguire un ciclo di individuazione e visualizzare i report per lo scanner</span><span class="sxs-lookup"><span data-stu-id="65d54-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="65d54-243">Usare PowerShell per configurare lo scanner per applicare la classificazione e la protezione</span><span class="sxs-lookup"><span data-stu-id="65d54-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="65d54-244">Utilizzare PowerShell per configurare un criterio DLP con lo scanner</span><span class="sxs-lookup"><span data-stu-id="65d54-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="65d54-245">Nella tabella seguente sono elencati i cmdlet di PowerShell rilevanti per l'installazione dello scanner e la gestione dei processi di analisi del contenuto:</span><span class="sxs-lookup"><span data-stu-id="65d54-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="65d54-246">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="65d54-246">Cmdlet</span></span> | <span data-ttu-id="65d54-247">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65d54-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="65d54-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="65d54-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="65d54-249">Aggiunge un nuovo repository al processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="65d54-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="65d54-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="65d54-251">Restituisce i dettagli sul cluster.</span><span class="sxs-lookup"><span data-stu-id="65d54-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="65d54-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="65d54-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="65d54-253">Ottiene informazioni dettagliate sul processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="65d54-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="65d54-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="65d54-255">Ottiene i dettagli sugli archivi definiti per il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="65d54-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="65d54-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="65d54-257">Elimina il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="65d54-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="65d54-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="65d54-259">Rimuove un repository dal processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="65d54-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="65d54-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="65d54-261">Definisce le impostazioni per il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="65d54-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="65d54-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="65d54-263">Definisce le impostazioni per un archivio esistente nel processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="65d54-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="65d54-264">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="65d54-264">For more information, see:</span></span>

- [<span data-ttu-id="65d54-265">Che cos'è lo scanner di etichettatura unificato di Azure Information Protection?</span><span class="sxs-lookup"><span data-stu-id="65d54-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="65d54-266">Configurazione e installazione dello scanner di etichettatura unificato di Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="65d54-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="65d54-267">[Gestire i processi di analisi del contenuto solo tramite PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="65d54-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
