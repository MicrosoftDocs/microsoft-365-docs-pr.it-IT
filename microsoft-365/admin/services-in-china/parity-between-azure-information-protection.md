---
title: Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
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
description: Per ulteriori informazioni, vedere Azure Information Protection per Office 365 gestito da 21Vianet e come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: ca30811e77f686b92b8cdd13d624182eb0d3039e
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445580"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="12c75-103">Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali</span><span class="sxs-lookup"><span data-stu-id="12c75-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="12c75-104">Anche se l'obiettivo è quello di fornire tutti i servizi e le funzionalità commerciali ai clienti in Cina con la nostra Azure Information Protection per Office 365 gestito dall'offerta 21Vianet, vi sono alcune funzionalità mancanti che vorremmo evidenziare.</span><span class="sxs-lookup"><span data-stu-id="12c75-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="12c75-105">L'elenco seguente include gli spazi vuoti esistenti tra Azure Information Protection per Office 365 gestito da 21Vianet e le offerte commerciali del 2019 luglio:</span><span class="sxs-lookup"><span data-stu-id="12c75-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="12c75-106">Information Rights Management (IRM) è supportato solo per le app Microsoft 365 per Enterprise (Build 11731,10000 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="12c75-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="12c75-107">Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="12c75-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="12c75-108">La migrazione da Active Directory Rights Management Services (AD RMS) a Azure Information Protection non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="12c75-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="12c75-109">È supportata la condivisione di messaggi di posta elettronica protetti per gli utenti nel cloud commerciale.</span><span class="sxs-lookup"><span data-stu-id="12c75-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="12c75-110">La condivisione dei documenti e degli allegati di posta elettronica per gli utenti nel cloud commerciale non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="12c75-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="12c75-111">Questo include Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale, non Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale e gli utenti con una licenza RMS per i singoli.</span><span class="sxs-lookup"><span data-stu-id="12c75-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="12c75-112">IRM con SharePoint (siti e raccolte protette con IRM) non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="12c75-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="12c75-113">Il connettore Rights Management non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="12c75-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="12c75-114">L'estensione del dispositivo mobile per AD RMS non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="12c75-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="12c75-115">Configurazione di Azure Information Protection per i clienti in Cina</span><span class="sxs-lookup"><span data-stu-id="12c75-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="12c75-116">Abilitare Rights Management per il tenant</span><span class="sxs-lookup"><span data-stu-id="12c75-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="12c75-117">Affinché la crittografia funzioni correttamente, è necessario che il server RMS sia abilitato per il tenant.</span><span class="sxs-lookup"><span data-stu-id="12c75-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="12c75-118">Controllare se RMS è abilitato:</span><span class="sxs-lookup"><span data-stu-id="12c75-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="12c75-119">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="12c75-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="12c75-120">Se il modulo AIPService non è installato, eseguire  `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="12c75-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="12c75-121">Importare il modulo utilizzando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="12c75-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="12c75-122">Connettersi al servizio tramite  `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="12c75-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="12c75-123">Eseguire  `(Get-AipServiceConfiguration).FunctionalState`   e verificare se lo stato è  `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="12c75-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="12c75-124">Se lo stato funzionale è  `Disabled` , eseguire  `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="12c75-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="12c75-125">Configurazione DNS per la crittografia (Windows)</span><span class="sxs-lookup"><span data-stu-id="12c75-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="12c75-126">Affinché la crittografia funzioni correttamente, le applicazioni client di Office devono connettersi all'istanza di Cina del servizio e bootstrap da tale posizione.</span><span class="sxs-lookup"><span data-stu-id="12c75-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="12c75-127">Per reindirizzare le applicazioni client all'istanza del servizio appropriato, è necessario che l'amministratore del tenant configuri un record DNS SRV con informazioni sull'URL di Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="12c75-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="12c75-128">Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="12c75-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="12c75-129">Inoltre, si presuppone che gli utenti accedano con un nome utente basato sul dominio di proprietà del tenant (ad esempio, `joe@contoso.cn` ) e non sul `onmschina` nome utente (ad esempio, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="12c75-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="12c75-130">Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.</span><span class="sxs-lookup"><span data-stu-id="12c75-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="12c75-131">Ottenere l'ID RMS:</span><span class="sxs-lookup"><span data-stu-id="12c75-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="12c75-132">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="12c75-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="12c75-133">Se il modulo AIPService non è installato, eseguire  `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="12c75-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="12c75-134">Connettersi al servizio tramite  `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="12c75-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="12c75-135">Esegui  `(Get-AipServiceConfiguration).RightsManagementServiceId`   per ottenere l'ID RMS.</span><span class="sxs-lookup"><span data-stu-id="12c75-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="12c75-136">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="12c75-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="12c75-137">Servizio = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="12c75-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="12c75-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="12c75-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="12c75-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="12c75-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="12c75-140">Target =  `[GUID].rms.aadrm.cn`   (dove GUID è l'ID RMS)</span><span class="sxs-lookup"><span data-stu-id="12c75-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="12c75-141">Priorità, peso, secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="12c75-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="12c75-142">Associare il dominio personalizzato al tenant nel portale di [Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="12c75-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="12c75-143">In questo modo verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.</span><span class="sxs-lookup"><span data-stu-id="12c75-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="12c75-144">Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="12c75-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="12c75-145">Nel processo di verifica, potrebbero essere necessarie ulteriori modifiche DNS.</span><span class="sxs-lookup"><span data-stu-id="12c75-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="12c75-146">Dopo aver effettuato la verifica, è possibile creare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="12c75-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="12c75-147">Configurazione DNS per la crittografia (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="12c75-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="12c75-148">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="12c75-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="12c75-149">Servizio = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="12c75-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="12c75-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="12c75-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="12c75-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="12c75-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="12c75-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="12c75-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="12c75-153">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="12c75-153">Port = `80`</span></span>
  - <span data-ttu-id="12c75-154">Priorità, peso, secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="12c75-154">Priority, Weight, Seconds, TTL = default values</span></span>
