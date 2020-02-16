---
title: Attivare Microsoft Threat Protection nel Centro sicurezza Microsoft 365
description: Informazioni su come abilitare Microsoft Threat Protection e iniziare a integrare i problemi di sicurezza e le relative risposte.
keywords: Introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, percorso dati, autorizzazioni necessarie, idoneità licenza, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 8f966060ebc9a30166647b397b93f2b45356df74
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083727"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="411bf-104">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="411bf-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="411bf-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="411bf-105">**Applies to:**</span></span>
- <span data-ttu-id="411bf-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="411bf-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="411bf-107">Microsoft Threat Protection unifica il processo di risposta agli eventi imprevisti integrando le funzionalità principali in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="411bf-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="411bf-108">Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="411bf-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="411bf-109">Verificare l'idoneità delle licenze e le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="411bf-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="411bf-110">I clienti con Microsoft 365 E5, Microsoft 365 E5 Security o una combinazione equivalente di licenze possono utilizzare Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="411bf-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="411bf-111">Per altre informazioni [consultare i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="411bf-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="411bf-112">Per abilitare Microsoft Threat Protection, è necessario essere un amministratore **globale** o un **amministratore della sicurezza** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="411bf-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="411bf-113">Iniziare a usare il servizio</span><span class="sxs-lookup"><span data-stu-id="411bf-113">Start using the service</span></span>
<span data-ttu-id="411bf-114">Microsoft Threat Protection aggrega i dati provenienti dai vari servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="411bf-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="411bf-115">I dati verranno elaborati e archiviati in modo centralizzato per identificare nuove informazioni e rendere possibili flussi di lavoro di risposta centralizzati.</span><span class="sxs-lookup"><span data-stu-id="411bf-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="411bf-116">Prima di abilitare il servizio, Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) non Visualizza gli **eventi** non consentiti e le opzioni del **Centro azioni** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="411bf-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="411bf-117">![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza senza Microsoft Threat Protection](../../media/mtp-off.png)
caratteristiche*Microsoft 365 Security Center con Microsoft Threat Protection disattivata*</span><span class="sxs-lookup"><span data-stu-id="411bf-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../../media/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="411bf-118">Per abilitare Microsoft Threat Protection, selezionare **Impostazioni** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="411bf-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="411bf-119">Nella **[pagina Impostazioni](https://security.microsoft.com/settings)**, accedere a **Microsoft Threat Protection** > **opt-in/opt-out**.</span><span class="sxs-lookup"><span data-stu-id="411bf-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="411bf-120">Se non si visualizzano le **Impostazioni** nel riquadro di spostamento o non è stato possibile accedere alla pagina, controllare autorizzazioni e licenze.</span><span class="sxs-lookup"><span data-stu-id="411bf-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="411bf-121">Selezionare percorso Data Center</span><span class="sxs-lookup"><span data-stu-id="411bf-121">Select data center location</span></span>
<span data-ttu-id="411bf-122">Se è stato eseguito il provisioning di Microsoft Defender ATP per l'organizzazione, i dati verranno archiviati ed elaborati nella stessa area data center selezionata per i [dati di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="411bf-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="411bf-123">Se non si dispone di Microsoft Defender ATP, verrà chiesto di scegliere una nuova area data center specifica per Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="411bf-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="411bf-124">È necessario fornire il consenso prima che i dati vengano condivisi tra i servizi e aggregati.</span><span class="sxs-lookup"><span data-stu-id="411bf-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="411bf-125">Verificare che il servizio sia attivo</span><span class="sxs-lookup"><span data-stu-id="411bf-125">Confirm that the service is on</span></span>
<span data-ttu-id="411bf-126">Dopo aver eseguito il provisioning il servizio aggiunge:</span><span class="sxs-lookup"><span data-stu-id="411bf-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="411bf-127">Gestione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="411bf-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="411bf-128">Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="411bf-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="411bf-129">Funzionalità di [ricerca avanzata](advanced-hunting-overview.md) alla pagina **Ricerca** esistente</span><span class="sxs-lookup"><span data-stu-id="411bf-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="411bf-130">![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza con Microsoft Threat Protection](../../media/mtp-on.png)
caratteristiche*Microsoft 365 Security Center con gestione degli incidenti e altre funzionalità di Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="411bf-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="411bf-131">Ottenere i dati di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="411bf-131">Getting Azure ATP data</span></span>
<span data-ttu-id="411bf-132">Per condividere i dati di Azure ATP con Microsoft Threat Protection, accertarsi che l'integrazione di Microsoft Cloud App Security e Azure ATP sia attivata.</span><span class="sxs-lookup"><span data-stu-id="411bf-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="411bf-133">Altre informazioni sull'integrazione</span><span class="sxs-lookup"><span data-stu-id="411bf-133">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="411bf-134">Disattivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="411bf-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="411bf-135">Per interrompere l'uso del servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > \*\* Consenso esplicito/rifiuto esplicito\*\* nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="411bf-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="411bf-136">Deselezionare **Attiva Microsoft Threat Protection** e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="411bf-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="411bf-137">I dati verranno eliminati in modo definitivo e le funzionalità corrispondenti verranno rimosse dal centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="411bf-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="411bf-138">Ottenere assistenza</span><span class="sxs-lookup"><span data-stu-id="411bf-138">Get assistance</span></span>

<span data-ttu-id="411bf-139">Il personale del supporto tecnico Microsoft può contribuire a provisionare o deprovisionare il servizio e le risorse correlate sul tenant.</span><span class="sxs-lookup"><span data-stu-id="411bf-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="411bf-140">Per assistenza, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="411bf-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="411bf-141">Per contattare il supporto tecnico, fare riferimento a Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="411bf-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="411bf-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="411bf-142">Related topics</span></span>

- [<span data-ttu-id="411bf-143">Panoramica di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="411bf-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="411bf-144">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="411bf-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="411bf-145">Panoramica di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="411bf-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="411bf-146">Panoramica di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="411bf-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="411bf-147">Panoramica di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="411bf-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="411bf-148">Panoramica di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="411bf-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="411bf-149">Archiviazione dei dati di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="411bf-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
