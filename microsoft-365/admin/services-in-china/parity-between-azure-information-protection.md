---
title: Supporto di Azure Information Protection per Office 365 gestito da 21Vianet
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
description: Per ulteriori informazioni, vedere l'articolo relativo a Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988045"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="945cf-103">Supporto di Azure Information Protection per Office 365 gestito da 21Vianet</span><span class="sxs-lookup"><span data-stu-id="945cf-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="945cf-104">In questo articolo vengono illustrate le differenze tra il supporto di Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e le offerte commerciali, nonché istruzioni specifiche per la configurazione di AIP per i clienti in Cina, &mdash; tra cui l'installazione dello scanner di AIP in locale e la gestione dei processi di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="945cf-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="945cf-105">Differenze tra AIP per Office 365 gestito da 21Vianet e offerte commerciali</span><span class="sxs-lookup"><span data-stu-id="945cf-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="945cf-106">Anche se l'obiettivo è quello di fornire tutti i servizi e le funzionalità commerciali ai clienti in Cina con la nostra AIP per Office 365 gestito dall'offerta 21Vianet, ci sono alcune funzionalità mancanti che vorremmo evidenziare.</span><span class="sxs-lookup"><span data-stu-id="945cf-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="945cf-107">L'elenco seguente include gli spazi vuoti esistenti tra AIP per Office 365 gestito da 21Vianet e le offerte commerciali del gennaio 2021:</span><span class="sxs-lookup"><span data-stu-id="945cf-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="945cf-108">Information Rights Management (IRM) è supportato solo per le app Microsoft 365 per Enterprise (Build 11731,10000 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="945cf-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="945cf-109">Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="945cf-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="945cf-110">La migrazione da Active Directory Rights Management Services (AD RMS) a AIP non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="945cf-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="945cf-111">La condivisione dei messaggi di posta elettronica protetti con gli utenti nel cloud commerciale è supportata.</span><span class="sxs-lookup"><span data-stu-id="945cf-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="945cf-112">La condivisione dei documenti e degli allegati di posta elettronica con gli utenti nel cloud commerciale non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="945cf-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="945cf-113">Questo include Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale, non Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale e gli utenti con una licenza RMS per i singoli.</span><span class="sxs-lookup"><span data-stu-id="945cf-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="945cf-114">IRM con SharePoint (siti e raccolte protette con IRM) non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="945cf-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="945cf-115">L'estensione del dispositivo mobile per AD RMS non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="945cf-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="945cf-116">Il [Visualizzatore per dispositivi mobili](/azure/information-protection/rms-client/mobile-app-faq) non è supportato da Azure China 21ViaNet.</span><span class="sxs-lookup"><span data-stu-id="945cf-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="945cf-117">Configurare l'AIP per i clienti in Cina</span><span class="sxs-lookup"><span data-stu-id="945cf-117">Configure AIP for customers in China</span></span>

<span data-ttu-id="945cf-118">Per configurare l'AIP per i clienti in Cina:</span><span class="sxs-lookup"><span data-stu-id="945cf-118">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="945cf-119">[Abilitare Rights Management per il tenant](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="945cf-119">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="945cf-120">[Configurare la crittografia DNS](#step-2-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="945cf-120">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="945cf-121">[Installare e configurare il client di etichettatura di AIP Unified](#step-3-install-and-configure-the-aip-unified-labeling-client).</span><span class="sxs-lookup"><span data-stu-id="945cf-121">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="945cf-122">[Configurare le app AIP su Windows](#step-4-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="945cf-122">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="945cf-123">[Installare lo scanner locale di AIP e gestire i processi di analisi del contenuto](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span><span class="sxs-lookup"><span data-stu-id="945cf-123">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="945cf-124">Passaggio 1: abilitare Rights Management per il tenant</span><span class="sxs-lookup"><span data-stu-id="945cf-124">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="945cf-125">Affinché la crittografia funzioni correttamente, RMS deve essere abilitato per il tenant.</span><span class="sxs-lookup"><span data-stu-id="945cf-125">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="945cf-126">Controllare se RMS è abilitato:</span><span class="sxs-lookup"><span data-stu-id="945cf-126">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="945cf-127">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="945cf-127">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="945cf-128">Se il modulo di AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="945cf-128">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="945cf-129">Importare il modulo utilizzando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="945cf-129">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="945cf-130">Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="945cf-130">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="945cf-131">Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="945cf-131">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="945cf-132">Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="945cf-132">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="945cf-133">Passaggio 2: configurare la crittografia DNS</span><span class="sxs-lookup"><span data-stu-id="945cf-133">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="945cf-134">Affinché la crittografia funzioni correttamente, le applicazioni client di Office devono connettersi all'istanza di Cina del servizio e bootstrap da tale posizione.</span><span class="sxs-lookup"><span data-stu-id="945cf-134">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="945cf-135">Per reindirizzare le applicazioni client all'istanza del servizio appropriato, è necessario che l'amministratore del tenant configuri un record DNS SRV con informazioni sull'URL di Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="945cf-135">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="945cf-136">Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="945cf-136">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="945cf-137">Inoltre, si presuppone che gli utenti accedano con un nome utente basato sul dominio di proprietà del tenant (ad esempio, `joe@contoso.cn` ) e non sul `onmschina` nome utente (ad esempio, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="945cf-137">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="945cf-138">Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.</span><span class="sxs-lookup"><span data-stu-id="945cf-138">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="945cf-139">Configurare la crittografia DNS-Windows</span><span class="sxs-lookup"><span data-stu-id="945cf-139">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="945cf-140">Ottenere l'ID RMS:</span><span class="sxs-lookup"><span data-stu-id="945cf-140">Get the RMS ID:</span></span>

    1. <span data-ttu-id="945cf-141">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="945cf-141">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="945cf-142">Se il modulo di AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="945cf-142">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="945cf-143">Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="945cf-143">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="945cf-144">Esegui `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.</span><span class="sxs-lookup"><span data-stu-id="945cf-144">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="945cf-145">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="945cf-145">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="945cf-146">Servizio = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="945cf-146">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="945cf-147">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="945cf-147">Protocol = `_http`</span></span>
    - <span data-ttu-id="945cf-148">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="945cf-148">Name = `_tcp`</span></span>
    - <span data-ttu-id="945cf-149">Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)</span><span class="sxs-lookup"><span data-stu-id="945cf-149">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="945cf-150">Priorità, peso, secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="945cf-150">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="945cf-151">Associare il dominio personalizzato al tenant nel portale di [Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="945cf-151">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="945cf-152">In questo modo verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.</span><span class="sxs-lookup"><span data-stu-id="945cf-152">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="945cf-153">Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="945cf-153">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="945cf-154">Nel processo di verifica, potrebbero essere necessarie ulteriori modifiche DNS.</span><span class="sxs-lookup"><span data-stu-id="945cf-154">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="945cf-155">Dopo aver effettuato la verifica, è possibile creare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="945cf-155">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="945cf-156">Configurare la crittografia DNS-Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="945cf-156">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="945cf-157">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="945cf-157">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="945cf-158">Servizio = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="945cf-158">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="945cf-159">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="945cf-159">Protocol = `_http`</span></span>
- <span data-ttu-id="945cf-160">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="945cf-160">Name = `_tcp`</span></span>
- <span data-ttu-id="945cf-161">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="945cf-161">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="945cf-162">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="945cf-162">Port = `80`</span></span>
- <span data-ttu-id="945cf-163">Priorità, peso, secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="945cf-163">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="945cf-164">Passaggio 3: installare e configurare il client di etichettatura di AIP Unified</span><span class="sxs-lookup"><span data-stu-id="945cf-164">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="945cf-165">Scaricare il client di etichettatura AIP Unified dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="945cf-165">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="945cf-166">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="945cf-166">For more information, see:</span></span>

- [<span data-ttu-id="945cf-167">Documentazione su AIP</span><span class="sxs-lookup"><span data-stu-id="945cf-167">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="945cf-168">AIP cronologia delle versioni e criteri di supporto</span><span class="sxs-lookup"><span data-stu-id="945cf-168">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="945cf-169">Requisiti di sistema AIP</span><span class="sxs-lookup"><span data-stu-id="945cf-169">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="945cf-170">Guida introduttiva a AIP: distribuire il client AIP</span><span class="sxs-lookup"><span data-stu-id="945cf-170">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="945cf-171">Guida all'amministratore di AIP</span><span class="sxs-lookup"><span data-stu-id="945cf-171">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="945cf-172">Guida per l'utente AIP</span><span class="sxs-lookup"><span data-stu-id="945cf-172">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="945cf-173">Informazioni sulle etichette di riservatezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="945cf-173">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="945cf-174">Passaggio 4: configurare le app AIP su Windows</span><span class="sxs-lookup"><span data-stu-id="945cf-174">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="945cf-175">Le app AIP su Windows richiedono la seguente chiave del registro di sistema per indirizzarle al cloud sovrano corretto per Azure China:</span><span class="sxs-lookup"><span data-stu-id="945cf-175">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="945cf-176">Nodo del registro di sistema = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="945cf-176">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="945cf-177">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="945cf-177">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="945cf-178">Valore = `6` (impostazione predefinita = 0)</span><span class="sxs-lookup"><span data-stu-id="945cf-178">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="945cf-179">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="945cf-179">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="945cf-180">Assicurarsi di non eliminare la chiave del registro di sistema dopo una disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="945cf-180">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="945cf-181">Se la chiave è vuota, errata o inesistente, la funzionalità si comporterà come valore predefinito (valore predefinito = 0 per il cloud commerciale).</span><span class="sxs-lookup"><span data-stu-id="945cf-181">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="945cf-182">Se la chiave è vuota o non è corretta, al registro viene aggiunto anche un errore di stampa.</span><span class="sxs-lookup"><span data-stu-id="945cf-182">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="945cf-183">Passaggio 5: installare lo scanner locale di AIP e gestire i processi di analisi del contenuto</span><span class="sxs-lookup"><span data-stu-id="945cf-183">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="945cf-184">Installare lo scanner di AIP in locale per analizzare le condivisioni di rete e di contenuto per i dati sensibili e applicare etichette di classificazione e protezione configurate nei criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="945cf-184">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="945cf-185">Quando si installa lo scanner e si gestiscono i processi di analisi del contenuto, utilizzare i cmdlet seguenti anziché l'interfaccia del portale di Azure utilizzata dalle offerte commerciali:</span><span class="sxs-lookup"><span data-stu-id="945cf-185">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="945cf-186">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="945cf-186">Cmdlet</span></span> | <span data-ttu-id="945cf-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="945cf-187">Description</span></span> |
|--|--|
| [<span data-ttu-id="945cf-188">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="945cf-188">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="945cf-189">Aggiunge un nuovo repository al processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="945cf-189">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="945cf-190">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="945cf-190">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="945cf-191">Ottiene informazioni dettagliate sul processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="945cf-191">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="945cf-192">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="945cf-192">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="945cf-193">Ottiene informazioni dettagliate sui repository definiti per il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="945cf-193">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="945cf-194">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="945cf-194">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="945cf-195">Elimina il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="945cf-195">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="945cf-196">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="945cf-196">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="945cf-197">Rimuove un repository dal processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="945cf-197">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="945cf-198">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="945cf-198">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="945cf-199">Definisce le impostazioni per il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="945cf-199">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="945cf-200">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="945cf-200">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="945cf-201">Definisce le impostazioni per un archivio esistente nel processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="945cf-201">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="945cf-202">Per ulteriori informazioni, vedere [What is the Azure Information Protection Unified Labeling scanner?](/azure/information-protection/deploy-aip-scanner) e [gestire i processi di analisi del contenuto utilizzando solo PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="945cf-202">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>