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
ms.openlocfilehash: f1c616a3d752324b8db5fdd5069904989a25eade
ms.sourcegitcommit: b57d597edbff5ab6cff8c2b04d27c15b0024776f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "43997515"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="1edcc-104">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1edcc-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="1edcc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1edcc-105">**Applies to:**</span></span>
- <span data-ttu-id="1edcc-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1edcc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1edcc-107">Microsoft Threat Protection unifica il processo di risposta agli eventi imprevisti integrando le funzionalità principali in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="1edcc-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="1edcc-108">Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1edcc-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="1edcc-109">Per ottenere la migliore protezione e ottimizzare Microsoft Threat Protection, è consigliabile distribuire tutti i servizi supportati in rete.</span><span class="sxs-lookup"><span data-stu-id="1edcc-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="1edcc-110">Per ulteriori informazioni, [vedere informazioni sulla distribuzione di servizi supportati](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="1edcc-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="1edcc-111">Verificare l'idoneità delle licenze e le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="1edcc-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="1edcc-112">Una licenza di sicurezza Microsoft 365 E5, E5 Security, a5 o a5 o una combinazione valida di licenze fornisce l'accesso ai servizi supportati e autorizza l'utilizzo di Microsoft Threat Protection in Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="1edcc-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="1edcc-113">Per informazioni dettagliate sulla licenza, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="1edcc-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="1edcc-114">Controllare il ruolo</span><span class="sxs-lookup"><span data-stu-id="1edcc-114">Check your role</span></span>
<span data-ttu-id="1edcc-115">Per abilitare Microsoft Threat Protection, è necessario essere un amministratore **globale** o un **amministratore della sicurezza** in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1edcc-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="1edcc-116">Visualizzare i ruoli in Azure AD</span><span class="sxs-lookup"><span data-stu-id="1edcc-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="1edcc-117">Iniziare a usare il servizio</span><span class="sxs-lookup"><span data-stu-id="1edcc-117">Start using the service</span></span>
<span data-ttu-id="1edcc-118">Microsoft Threat Protection aggrega i dati provenienti dai vari servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="1edcc-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="1edcc-119">I dati verranno elaborati e archiviati in modo centralizzato per identificare nuove informazioni e rendere possibili flussi di lavoro di risposta centralizzati.</span><span class="sxs-lookup"><span data-stu-id="1edcc-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="1edcc-120">Prima di abilitare il servizio, Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) Visualizza la pagina di benvenuto di Microsoft Threat Protection quando si seleziona **incidenti**, **Centro azioni**o **ricerca** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="1edcc-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="1edcc-121">Queste opzioni di spostamento non vengono visualizzate se non si è idonei per l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="1edcc-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="1edcc-122">![Immagine della pagina di benvenuto di Microsoft Threat Protection visualizzata se Microsoft Threat Protection non è stato attivato](../../media/mtp-welcome.png)
*nella pagina di benvenuto Microsoft Threat Protection in Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="1edcc-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="1edcc-123">Per abilitare Microsoft Threat Protection, è sufficiente completare il processo dalla pagina di benvenuto.</span><span class="sxs-lookup"><span data-stu-id="1edcc-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="1edcc-124">È inoltre possibile abilitare Microsoft Threat Protection accedendo alle **Impostazioni** ([Security.Microsoft.com/settings](https://security.microsoft.com/settings)) nel riquadro di spostamento e selezionando **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="1edcc-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span> <span data-ttu-id="1edcc-125">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1edcc-125">Click **Save**.</span></span>

>[!NOTE]
><span data-ttu-id="1edcc-126">Se non si visualizzano le **Impostazioni** nel riquadro di spostamento o non è stato possibile accedere alla pagina, controllare autorizzazioni e licenze.</span><span class="sxs-lookup"><span data-stu-id="1edcc-126">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="1edcc-127">Selezionare percorso Data Center</span><span class="sxs-lookup"><span data-stu-id="1edcc-127">Select data center location</span></span>
<span data-ttu-id="1edcc-128">Se è stato eseguito il provisioning di Microsoft Defender ATP per l'organizzazione, i dati verranno archiviati ed elaborati nella stessa area data center selezionata per i [dati di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="1edcc-128">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="1edcc-129">Se non si dispone di Microsoft Defender ATP, verrà chiesto di scegliere una nuova area data center specifica per Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="1edcc-129">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="1edcc-130">È necessario fornire il consenso prima che i dati vengano condivisi tra i servizi e aggregati.</span><span class="sxs-lookup"><span data-stu-id="1edcc-130">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="1edcc-131">Verificare che il servizio sia attivo</span><span class="sxs-lookup"><span data-stu-id="1edcc-131">Confirm that the service is on</span></span>
<span data-ttu-id="1edcc-132">Dopo aver eseguito il provisioning il servizio aggiunge:</span><span class="sxs-lookup"><span data-stu-id="1edcc-132">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="1edcc-133">Gestione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="1edcc-133">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="1edcc-134">Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="1edcc-134">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="1edcc-135">Funzionalità di [ricerca avanzata](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1edcc-135">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="1edcc-136">![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza con Microsoft Threat Protection](../../media/mtp-on.png)
caratteristiche*Microsoft 365 Security Center con gestione degli incidenti e altre funzionalità di Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="1edcc-136">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="1edcc-137">Ottenere i dati di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="1edcc-137">Getting Azure ATP data</span></span>
<span data-ttu-id="1edcc-138">Per condividere i dati di Azure ATP con Microsoft Threat Protection, accertarsi che l'integrazione di Microsoft Cloud App Security e Azure ATP sia attivata.</span><span class="sxs-lookup"><span data-stu-id="1edcc-138">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="1edcc-139">Altre informazioni sull'integrazione</span><span class="sxs-lookup"><span data-stu-id="1edcc-139">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="1edcc-140">Disattivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1edcc-140">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="1edcc-141">Per interrompere l'uso del servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > \*\* Consenso esplicito/rifiuto esplicito\*\* nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1edcc-141">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="1edcc-142">Deselezionare **Attiva Microsoft Threat Protection** e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1edcc-142">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="1edcc-143">Le funzionalità corrispondenti verranno rimosse dal centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1edcc-143">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="1edcc-144">Ottenere assistenza</span><span class="sxs-lookup"><span data-stu-id="1edcc-144">Get assistance</span></span>

<span data-ttu-id="1edcc-145">Il personale del supporto tecnico Microsoft può contribuire a provisionare o deprovisionare il servizio e le risorse correlate sul tenant.</span><span class="sxs-lookup"><span data-stu-id="1edcc-145">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="1edcc-146">Per assistenza, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1edcc-146">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="1edcc-147">Per contattare il supporto tecnico, fare riferimento a Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="1edcc-147">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1edcc-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1edcc-148">Related topics</span></span>

- [<span data-ttu-id="1edcc-149">Panoramica di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1edcc-149">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1edcc-150">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1edcc-150">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="1edcc-151">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="1edcc-151">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="1edcc-152">Panoramica di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1edcc-152">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="1edcc-153">Panoramica di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1edcc-153">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="1edcc-154">Panoramica di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1edcc-154">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="1edcc-155">Panoramica di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="1edcc-155">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="1edcc-156">Archiviazione dei dati di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1edcc-156">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
