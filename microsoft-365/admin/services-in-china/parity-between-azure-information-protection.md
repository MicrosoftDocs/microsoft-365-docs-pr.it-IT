---
title: Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali
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
description: Per ulteriori informazioni, vedere Azure Information Protection per Office 365 gestito da 21Vianet e come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: 7be40466c43a49cf51a2a2c1c273cef035bee831
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519342"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="8fefa-103">Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali</span><span class="sxs-lookup"><span data-stu-id="8fefa-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="8fefa-104">Anche se l'obiettivo è quello di fornire tutti i servizi e le funzionalità commerciali ai clienti in Cina con la nostra Azure Information Protection per Office 365 gestito dall'offerta 21Vianet, vi sono alcune funzionalità mancanti che vorremmo evidenziare.</span><span class="sxs-lookup"><span data-stu-id="8fefa-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="8fefa-105">L'elenco seguente include gli spazi vuoti esistenti tra Azure Information Protection per Office 365 gestito da 21Vianet e le offerte commerciali del 2019 luglio:</span><span class="sxs-lookup"><span data-stu-id="8fefa-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="8fefa-106">Information Rights Management (IRM) è supportato solo per le app Microsoft 365 per Enterprise (Build 11731,10000 o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="8fefa-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="8fefa-107">Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="8fefa-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="8fefa-108">La migrazione da Active Directory Rights Management Services (AD RMS) a Azure Information Protection non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="8fefa-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="8fefa-109">È supportata la condivisione di messaggi di posta elettronica protetti per gli utenti nel cloud commerciale.</span><span class="sxs-lookup"><span data-stu-id="8fefa-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="8fefa-110">La condivisione dei documenti e degli allegati di posta elettronica per gli utenti nel cloud commerciale non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="8fefa-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="8fefa-111">Questo include Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale, non Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale e gli utenti con una licenza RMS per i singoli.</span><span class="sxs-lookup"><span data-stu-id="8fefa-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="8fefa-112">IRM con SharePoint (siti e raccolte protette con IRM) non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="8fefa-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="8fefa-113">L'estensione del dispositivo mobile per AD RMS non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="8fefa-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="8fefa-114">Configurazione di Azure Information Protection per i clienti in Cina</span><span class="sxs-lookup"><span data-stu-id="8fefa-114">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="8fefa-115">Abilitare Rights Management per il tenant</span><span class="sxs-lookup"><span data-stu-id="8fefa-115">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="8fefa-116">Affinché la crittografia funzioni correttamente, è necessario che il server RMS sia abilitato per il tenant.</span><span class="sxs-lookup"><span data-stu-id="8fefa-116">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="8fefa-117">Controllare se RMS è abilitato:</span><span class="sxs-lookup"><span data-stu-id="8fefa-117">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="8fefa-118">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="8fefa-118">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="8fefa-119">Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="8fefa-119">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="8fefa-120">Importare il modulo utilizzando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="8fefa-120">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="8fefa-121">Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="8fefa-121">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="8fefa-122">Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="8fefa-122">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="8fefa-123">Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="8fefa-123">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="8fefa-124">Configurazione DNS per la crittografia (Windows)</span><span class="sxs-lookup"><span data-stu-id="8fefa-124">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="8fefa-125">Affinché la crittografia funzioni correttamente, le applicazioni client di Office devono connettersi all'istanza di Cina del servizio e bootstrap da tale posizione.</span><span class="sxs-lookup"><span data-stu-id="8fefa-125">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="8fefa-126">Per reindirizzare le applicazioni client all'istanza del servizio appropriato, è necessario che l'amministratore del tenant configuri un record DNS SRV con informazioni sull'URL di Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="8fefa-126">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="8fefa-127">Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8fefa-127">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="8fefa-128">Inoltre, si presuppone che gli utenti accedano con un nome utente basato sul dominio di proprietà del tenant (ad esempio, `joe@contoso.cn` ) e non sul `onmschina` nome utente (ad esempio, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="8fefa-128">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="8fefa-129">Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.</span><span class="sxs-lookup"><span data-stu-id="8fefa-129">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="8fefa-130">Ottenere l'ID RMS:</span><span class="sxs-lookup"><span data-stu-id="8fefa-130">Get the RMS ID:</span></span>
  1. <span data-ttu-id="8fefa-131">Avviare PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="8fefa-131">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="8fefa-132">Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="8fefa-132">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="8fefa-133">Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="8fefa-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="8fefa-134">Esegui `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.</span><span class="sxs-lookup"><span data-stu-id="8fefa-134">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="8fefa-135">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="8fefa-135">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="8fefa-136">Servizio = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="8fefa-136">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="8fefa-137">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="8fefa-137">Protocol = `_http`</span></span>
  - <span data-ttu-id="8fefa-138">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="8fefa-138">Name = `_tcp`</span></span>
  - <span data-ttu-id="8fefa-139">Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)</span><span class="sxs-lookup"><span data-stu-id="8fefa-139">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="8fefa-140">Priorità, peso, secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="8fefa-140">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="8fefa-141">Associare il dominio personalizzato al tenant nel portale di [Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="8fefa-141">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="8fefa-142">In questo modo verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.</span><span class="sxs-lookup"><span data-stu-id="8fefa-142">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="8fefa-143">Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8fefa-143">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="8fefa-144">Nel processo di verifica, potrebbero essere necessarie ulteriori modifiche DNS.</span><span class="sxs-lookup"><span data-stu-id="8fefa-144">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="8fefa-145">Dopo aver effettuato la verifica, è possibile creare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8fefa-145">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="8fefa-146">Configurazione DNS per la crittografia (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="8fefa-146">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="8fefa-147">Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.</span><span class="sxs-lookup"><span data-stu-id="8fefa-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="8fefa-148">Servizio = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="8fefa-148">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="8fefa-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="8fefa-149">Protocol = `_http`</span></span>
  - <span data-ttu-id="8fefa-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="8fefa-150">Name = `_tcp`</span></span>
  - <span data-ttu-id="8fefa-151">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="8fefa-151">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="8fefa-152">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="8fefa-152">Port = `80`</span></span>
  - <span data-ttu-id="8fefa-153">Priorità, peso, secondi, TTL = valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="8fefa-153">Priority, Weight, Seconds, TTL = default values</span></span>
