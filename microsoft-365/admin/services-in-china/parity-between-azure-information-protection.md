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
description: Ulteriori informazioni su Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e su come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099679"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="0e89d-103">Supporto di Azure Information Protection per Office 365 gestito da 21Vianet</span><span class="sxs-lookup"><span data-stu-id="0e89d-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="0e89d-104">Questo articolo illustra le differenze tra il supporto di Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e le offerte commerciali, nonché istruzioni specifiche per la configurazione di AIP per i clienti in Cina, tra cui come installare lo scanner AIP locale e gestire i processi di analisi del &mdash; contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="0e89d-105">Differenze tra AIP per Office 365 gestito da 21Vianet e offerte commerciali</span><span class="sxs-lookup"><span data-stu-id="0e89d-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="0e89d-106">Anche se l'obiettivo è fornire tutte le funzionalità commerciali ai clienti in Cina con l'offerta AIP per Office 365 gestito da 21Vianet, alcune funzionalità mancanti sono da evidenziare.</span><span class="sxs-lookup"><span data-stu-id="0e89d-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="0e89d-107">L'elenco seguente include le lacune esistenti tra AIP per Office 365 gestito da 21Vianet e le offerte commerciali a partire da gennaio 2021:</span><span class="sxs-lookup"><span data-stu-id="0e89d-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="0e89d-108">Information Rights Management (IRM) è supportato solo per Microsoft 365 Apps for enterprise (build 11731.10000 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="0e89d-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="0e89d-109">Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0e89d-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="0e89d-110">La migrazione da Active Directory Rights Management Services (AD RMS) ad AIP non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="0e89d-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="0e89d-111">La condivisione di messaggi di posta elettronica protetti con gli utenti nel cloud commerciale è supportata.</span><span class="sxs-lookup"><span data-stu-id="0e89d-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="0e89d-112">La condivisione di documenti e allegati di posta elettronica con gli utenti nel cloud commerciale non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="0e89d-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="0e89d-113">Sono inclusi Office 365 gestito da utenti di 21Vianet nel cloud commerciale, utenti non di Office 365 gestiti da 21Vianet nel cloud commerciale e utenti con licenza RMS per singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="0e89d-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="0e89d-114">IRM con SharePoint (siti e raccolte protetti tramite IRM) non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="0e89d-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="0e89d-115">L'estensione per dispositivi mobili per AD RMS non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="0e89d-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="0e89d-116">Il [visualizzatore per](/azure/information-protection/rms-client/mobile-app-faq) dispositivi mobili non è supportato da Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="0e89d-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="0e89d-117">L'area AIP del portale di Azure non è disponibile per i clienti in Cina.</span><span class="sxs-lookup"><span data-stu-id="0e89d-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="0e89d-118">Utilizzare [i comandi di PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) invece di eseguire azioni nel portale, ad esempio l'installazione dello scanner locale e la gestione dei processi di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="0e89d-119">Configurare AIP per i clienti in Cina</span><span class="sxs-lookup"><span data-stu-id="0e89d-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="0e89d-120">Per configurare AIP per i clienti in Cina:</span><span class="sxs-lookup"><span data-stu-id="0e89d-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="0e89d-121">[Abilitare Rights Management per il tenant.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="0e89d-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="0e89d-122">[Configurare la crittografia DNS.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="0e89d-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="0e89d-123">[Installare e configurare il client di etichettatura unificato AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="0e89d-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="0e89d-124">[Configurare le app AIP in Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="0e89d-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="0e89d-125">[Installare lo scanner AIP locale e gestire i](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)processi di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="0e89d-126">Passaggio 1: abilitare Rights Management per il tenant</span><span class="sxs-lookup"><span data-stu-id="0e89d-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="0e89d-127">Per il corretto funzionamento della crittografia, è necessario che RMS sia abilitato per il tenant.</span><span class="sxs-lookup"><span data-stu-id="0e89d-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="0e89d-128">Verificare se RMS è abilitato:</span><span class="sxs-lookup"><span data-stu-id="0e89d-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="0e89d-129">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="0e89d-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="0e89d-130">Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="0e89d-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="0e89d-131">Importare il modulo utilizzando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="0e89d-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="0e89d-132">Connettersi al servizio utilizzando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="0e89d-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="0e89d-133">Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="0e89d-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="0e89d-134">Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="0e89d-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="0e89d-135">Passaggio 2: Configurare la crittografia DNS</span><span class="sxs-lookup"><span data-stu-id="0e89d-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="0e89d-136">Per il corretto funzionamento della crittografia, le applicazioni client di Office devono connettersi all'istanza cina del servizio e avviare il bootstrap da qui.</span><span class="sxs-lookup"><span data-stu-id="0e89d-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="0e89d-137">Per reindirizzare le applicazioni client all'istanza del servizio corretto, l'amministratore tenant deve configurare un record DNS SRV con informazioni sull'URL di Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="0e89d-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="0e89d-138">Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0e89d-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="0e89d-139">Inoltre, si presuppone che gli utenti accederanno con un nome utente basato sul dominio di proprietà del tenant (ad esempio, ) e non con il nome `joe@contoso.cn` `onmschina` utente (ad esempio, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="0e89d-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="0e89d-140">Il nome di dominio del nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.</span><span class="sxs-lookup"><span data-stu-id="0e89d-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="0e89d-141">Configurare la crittografia DNS - Windows</span><span class="sxs-lookup"><span data-stu-id="0e89d-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="0e89d-142">Ottenere l'ID RMS:</span><span class="sxs-lookup"><span data-stu-id="0e89d-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="0e89d-143">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="0e89d-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="0e89d-144">Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="0e89d-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="0e89d-145">Connettersi al servizio utilizzando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="0e89d-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="0e89d-146">Eseguire `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.</span><span class="sxs-lookup"><span data-stu-id="0e89d-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="0e89d-147">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="0e89d-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="0e89d-148">Servizio = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="0e89d-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="0e89d-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="0e89d-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="0e89d-150">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="0e89d-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="0e89d-151">Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)</span><span class="sxs-lookup"><span data-stu-id="0e89d-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="0e89d-152">Priorità, Peso, Secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="0e89d-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="0e89d-153">Associare il dominio personalizzato al tenant nel [portale di Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="0e89d-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="0e89d-154">Verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo l'aggiunta del valore alle impostazioni DNS.</span><span class="sxs-lookup"><span data-stu-id="0e89d-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="0e89d-155">Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="0e89d-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="0e89d-156">Nel processo di verifica potrebbero essere necessarie ulteriori modifiche al DNS.</span><span class="sxs-lookup"><span data-stu-id="0e89d-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="0e89d-157">Dopo aver eseguito la verifica, gli utenti possono essere creati.</span><span class="sxs-lookup"><span data-stu-id="0e89d-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="0e89d-158">Configurare la crittografia DNS - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="0e89d-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="0e89d-159">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="0e89d-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="0e89d-160">Servizio = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="0e89d-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="0e89d-161">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="0e89d-161">Protocol = `_http`</span></span>
- <span data-ttu-id="0e89d-162">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="0e89d-162">Name = `_tcp`</span></span>
- <span data-ttu-id="0e89d-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="0e89d-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="0e89d-164">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="0e89d-164">Port = `80`</span></span>
- <span data-ttu-id="0e89d-165">Priorità, Peso, Secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="0e89d-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="0e89d-166">Passaggio 3: Installare e configurare il client di etichettatura unificato AIP</span><span class="sxs-lookup"><span data-stu-id="0e89d-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="0e89d-167">Scaricare il client di etichettatura unificato AIP [dall'Area download Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="0e89d-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="0e89d-168">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="0e89d-168">For more information, see:</span></span>

- [<span data-ttu-id="0e89d-169">Documentazione AIP</span><span class="sxs-lookup"><span data-stu-id="0e89d-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="0e89d-170">Cronologia delle versioni AIP e criteri di supporto</span><span class="sxs-lookup"><span data-stu-id="0e89d-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="0e89d-171">Requisiti di sistema AIP</span><span class="sxs-lookup"><span data-stu-id="0e89d-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="0e89d-172">Guida introduttiva AIP: Distribuire il client AIP</span><span class="sxs-lookup"><span data-stu-id="0e89d-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="0e89d-173">Guida all'amministratore AIP</span><span class="sxs-lookup"><span data-stu-id="0e89d-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="0e89d-174">Manuale dell'utente AIP</span><span class="sxs-lookup"><span data-stu-id="0e89d-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="0e89d-175">Informazioni sulle etichette di riservatezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e89d-175">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="0e89d-176">Passaggio 4: Configurare le app AIP in Windows</span><span class="sxs-lookup"><span data-stu-id="0e89d-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="0e89d-177">Le app AIP in Windows necessitano della chiave del Registro di sistema seguente per puntare al cloud sovrano corretto per Azure Cina:</span><span class="sxs-lookup"><span data-stu-id="0e89d-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="0e89d-178">Nodo del Registro di sistema = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="0e89d-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="0e89d-179">Nome = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="0e89d-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="0e89d-180">Valore = `6` (valore predefinito = 0)</span><span class="sxs-lookup"><span data-stu-id="0e89d-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="0e89d-181">Tipo = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="0e89d-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e89d-182">Assicurati di non eliminare la chiave del Registro di sistema dopo una disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="0e89d-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="0e89d-183">Se la chiave è vuota, errata o inesistente, la funzionalità verrà utilizzata come valore predefinito (valore predefinito = 0 per il cloud commerciale).</span><span class="sxs-lookup"><span data-stu-id="0e89d-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="0e89d-184">Se la chiave è vuota o errata, al registro viene aggiunto anche un errore di stampa.</span><span class="sxs-lookup"><span data-stu-id="0e89d-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="0e89d-185">Passaggio 5: installare lo scanner AIP locale e gestire i processi di analisi del contenuto</span><span class="sxs-lookup"><span data-stu-id="0e89d-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="0e89d-186">Installare lo scanner AIP locale per analizzare la rete e le condivisioni di contenuto per i dati sensibili e applicare le etichette di classificazione e protezione in base alla configurazione nei criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0e89d-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="0e89d-187">Quando si installa lo scanner e si gestiscono i processi di analisi del contenuto, utilizzare i cmdlet seguenti anziché l'interfaccia del portale di Azure utilizzata dalle offerte commerciali:</span><span class="sxs-lookup"><span data-stu-id="0e89d-187">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="0e89d-188">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e89d-188">Cmdlet</span></span> | <span data-ttu-id="0e89d-189">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e89d-189">Description</span></span> |
|--|--|
| [<span data-ttu-id="0e89d-190">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="0e89d-190">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="0e89d-191">Aggiunge un nuovo archivio al processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-191">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="0e89d-192">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="0e89d-192">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="0e89d-193">Ottiene informazioni dettagliate sul processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-193">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="0e89d-194">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="0e89d-194">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="0e89d-195">Ottiene informazioni dettagliate sugli archivi definiti per il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-195">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="0e89d-196">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="0e89d-196">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="0e89d-197">Elimina il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-197">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="0e89d-198">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="0e89d-198">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="0e89d-199">Rimuove un archivio dal processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-199">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="0e89d-200">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="0e89d-200">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="0e89d-201">Definisce le impostazioni per il processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-201">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="0e89d-202">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="0e89d-202">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="0e89d-203">Definisce le impostazioni per un archivio esistente nel processo di analisi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0e89d-203">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="0e89d-204">Per altre informazioni, vedere [Che cos'è lo scanner](/azure/information-protection/deploy-aip-scanner) di etichettatura unificata di Azure Information Protection? e Gestire i processi di analisi del contenuto solo tramite [PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="0e89d-204">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
