---
title: Attivare Microsoft Threat Protection nel Centro sicurezza Microsoft 365
description: Informazioni su come abilitare Microsoft Threat Protection e iniziare a integrare i problemi di sicurezza e le relative risposte.
keywords: Introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, percorso dati, autorizzazioni necessarie, idoneità licenza
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b1832e2080c3178837f43cbfd45366fc4d48322d
ms.sourcegitcommit: c9332016f61b26f63c9145c9169ea5330e91a243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "41173822"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="b6723-104">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b6723-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="b6723-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b6723-105">**Applies to:**</span></span>
- <span data-ttu-id="b6723-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b6723-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b6723-107">Microsoft Threat Protection unifica il processo di risposta agli eventi imprevisti integrando le funzionalità principali in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="b6723-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="b6723-108">Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6723-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="b6723-109">Verificare l'idoneità delle licenze e le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="b6723-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="b6723-110">I clienti che dispongono di Microsoft 365 E5 o di una licenza equivalente possono usare Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b6723-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="b6723-111">Per altre informazioni [consultare i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="b6723-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

 <span data-ttu-id="b6723-112">Per poter abilitare Microsoft Threat Protection, è necessario essere un **amministratore globale** o un **amministratore della sicurezza** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span><span class="sxs-lookup"><span data-stu-id="b6723-112">To be able to turn on Microsoft Threat Protection, you need to be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="b6723-113">Iniziare a usare il servizio</span><span class="sxs-lookup"><span data-stu-id="b6723-113">Start using the service</span></span>
<span data-ttu-id="b6723-114">L'attivazione del servizio Microsoft Threat Protection aggrega i dati dai vari servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="b6723-114">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="b6723-115">I dati vengono elaborati e archiviati in modo centralizzato per identificare nuovi approfondimenti e consentire flussi di lavoro di risposte centralizzate.</span><span class="sxs-lookup"><span data-stu-id="b6723-115">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="b6723-116">Prima di abilitare il servizio, Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) non Visualizza le opzioni relative a **operazioni** non consentite e al **Centro azioni** del menu.</span><span class="sxs-lookup"><span data-stu-id="b6723-116">Before you turn the service on, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="b6723-117">![Immagine del menu del Centro sicurezza Microsoft 365 senza funzionalità di Microsoft Threat Protection](../images/mtp-off.png)
*Centro sicurezza Microsoft 365 con Microsoft Threat Protection disattivato*</span><span class="sxs-lookup"><span data-stu-id="b6723-117">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="b6723-118">Per attivare il servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > \*\* Consenso esplicito/rifiuto esplicito\*\* nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6723-118">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span>

<span data-ttu-id="b6723-119">Se è stato eseguito il provisioning di Microsoft Defender ATP per l'organizzazione, i dati verranno archiviati ed elaborati nella stessa area data center selezionata per i [dati di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="b6723-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="b6723-120">Se non si dispone di Microsoft Defender ATP, verrà chiesto di scegliere una nuova area data center specifica per Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b6723-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="b6723-121">Sarà necessario fornire il consenso prima che i dati vengano condivisi tra i servizi e gli aggregati.</span><span class="sxs-lookup"><span data-stu-id="b6723-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="b6723-122">Verificare che il servizio sia attivo</span><span class="sxs-lookup"><span data-stu-id="b6723-122">Confirm that the service is on</span></span>
<span data-ttu-id="b6723-123">Dopo aver eseguito il provisioning il servizio aggiunge:</span><span class="sxs-lookup"><span data-stu-id="b6723-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="b6723-124">Gestione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="b6723-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="b6723-125">Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="b6723-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="b6723-126">Funzionalità di [ricerca avanzata](advanced-hunting-overview.md) alla pagina **Ricerca** esistente</span><span class="sxs-lookup"><span data-stu-id="b6723-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="b6723-127">![Immagine del menu del Centro sicurezza Microsoft 365 con funzionalità di Microsoft Threat Protection](../images/mtp-on.png)
*Centro sicurezza Microsoft 365 con gestione degli eventi imprevisti e altre funzionalità di Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="b6723-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="b6723-128">Ottenere i dati di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="b6723-128">Getting Azure ATP data</span></span>
<span data-ttu-id="b6723-129">Per condividere i dati di Azure ATP con Microsoft Threat Protection, accertarsi che l'integrazione di Microsoft Cloud App Security e Azure ATP sia attivata.</span><span class="sxs-lookup"><span data-stu-id="b6723-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="b6723-130">Altre informazioni sull'integrazione</span><span class="sxs-lookup"><span data-stu-id="b6723-130">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="b6723-131">Disattivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b6723-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="b6723-132">Per interrompere l'uso del servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > \*\* Consenso esplicito/rifiuto esplicito\*\* nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6723-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b6723-133">Deselezionare **Attiva Microsoft Threat Protection** e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b6723-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="b6723-134">I dati verranno eliminati in modo definitivo e le funzionalità corrispondenti verranno rimosse dal centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6723-134">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="b6723-135">Ottenere assistenza</span><span class="sxs-lookup"><span data-stu-id="b6723-135">Get assistance</span></span>

<span data-ttu-id="b6723-136">Il personale Microsoft può fornire assistenza per eseguire il provisioning o deprovisioning del servizio e delle risorse correlate nel tenant.</span><span class="sxs-lookup"><span data-stu-id="b6723-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="b6723-137">Per assistenza, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6723-137">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b6723-138">Quando si descrivono le proprie preoccupazioni, menzione "Microsoft Threat Protection".</span><span class="sxs-lookup"><span data-stu-id="b6723-138">When describing your concerns, mention "Microsoft Threat Protection".</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6723-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b6723-139">Related topics</span></span>

- [<span data-ttu-id="b6723-140">Panoramica di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b6723-140">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="b6723-141">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b6723-141">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="b6723-142">Panoramica di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b6723-142">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="b6723-143">Panoramica di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b6723-143">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="b6723-144">Panoramica di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b6723-144">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="b6723-145">Panoramica di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="b6723-145">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="b6723-146">Archiviazione dei dati di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b6723-146">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
