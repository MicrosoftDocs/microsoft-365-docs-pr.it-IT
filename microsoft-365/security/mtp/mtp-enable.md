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
ms.openlocfilehash: 0bb91f226a29fe6b175cf1ca4866316d1457291e
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011864"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="997cc-104">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="997cc-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="997cc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="997cc-105">**Applies to:**</span></span>
- <span data-ttu-id="997cc-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="997cc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="997cc-107">Microsoft Threat Protection unifica il processo di risposta agli eventi imprevisti integrando le funzionalità principali in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="997cc-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="997cc-108">Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="997cc-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="997cc-109">Per ottenere la migliore protezione e ottimizzare Microsoft Threat Protection, è consigliabile distribuire tutti i servizi supportati in rete.</span><span class="sxs-lookup"><span data-stu-id="997cc-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="997cc-110">Per ulteriori informazioni, [vedere informazioni sulla distribuzione di servizi supportati](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="997cc-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="997cc-111">Verificare l'idoneità delle licenze e le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="997cc-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="997cc-112">Una licenza di sicurezza Microsoft 365 E5, E5, a5 o a5 o una combinazione valida di licenze fornisce l'accesso ai servizi supportati e autorizza l'utilizzo di Microsoft Threat Protection in Microsoft 365 Security Center senza ulteriori costi di licenza.</span><span class="sxs-lookup"><span data-stu-id="997cc-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span>

<span data-ttu-id="997cc-113">Per informazioni dettagliate sulla licenza, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="997cc-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="997cc-114">Controllare il ruolo</span><span class="sxs-lookup"><span data-stu-id="997cc-114">Check your role</span></span>
<span data-ttu-id="997cc-115">Per abilitare Microsoft Threat Protection, è necessario essere un amministratore **globale** o un **amministratore della sicurezza** in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="997cc-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="997cc-116">Visualizzare i ruoli in Azure AD</span><span class="sxs-lookup"><span data-stu-id="997cc-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="997cc-117">Iniziare a usare il servizio</span><span class="sxs-lookup"><span data-stu-id="997cc-117">Start using the service</span></span>

>[!IMPORTANT]
><span data-ttu-id="997cc-118">A partire dal 3 maggio 2020, Microsoft eseguirà gradualmente nuove esperienze ottimizzate in merito [ai requisiti di licenza](prerequisites.md#licensing-requirements) e all'attivazione di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="997cc-118">Starting May 3, 2020, Microsoft will gradually roll out new, optimized experiences around [licensing requirements](prerequisites.md#licensing-requirements) and turning on Microsoft Threat Protection.</span></span> <span data-ttu-id="997cc-119">Per alcune settimane durante questo periodo, alcuni clienti inizieranno a visualizzare le modifiche apportate alle esperienze del portale.</span><span class="sxs-lookup"><span data-stu-id="997cc-119">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="997cc-120">Le informazioni sulle nuove esperienze sono state contrassegnate come **nuova esperienza** in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="997cc-120">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="997cc-121">Microsoft Threat Protection aggrega i dati provenienti dai vari servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="997cc-121">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="997cc-122">I dati verranno elaborati e archiviati in modo centralizzato per identificare nuove informazioni e rendere possibili flussi di lavoro di risposta centralizzati.</span><span class="sxs-lookup"><span data-stu-id="997cc-122">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="997cc-123">In questo caso, senza influire sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="997cc-123">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="997cc-124">Prima di abilitare il servizio, Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) Visualizza la pagina di benvenuto di Microsoft Threat Protection quando si seleziona **incidenti**, **Centro azioni**o **ricerca** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="997cc-124">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="997cc-125">Queste opzioni di spostamento non vengono visualizzate se non si è idonei per l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="997cc-125">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="997cc-126">![Immagine della pagina di benvenuto di Microsoft Threat Protection visualizzata se Microsoft Threat Protection non è stato attivato](../../media/mtp-welcome.png)
*nella pagina di benvenuto Microsoft Threat Protection in Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="997cc-126">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="997cc-127">Per abilitare Microsoft Threat Protection, è sufficiente completare il processo dalla pagina di benvenuto.</span><span class="sxs-lookup"><span data-stu-id="997cc-127">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="997cc-128">È inoltre possibile abilitare Microsoft Threat Protection accedendo alle **Impostazioni** ([Security.Microsoft.com/settings](https://security.microsoft.com/settings)) nel riquadro di spostamento e selezionando **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="997cc-128">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="997cc-129">Se non si visualizzano le **Impostazioni** nel riquadro di spostamento o non è stato possibile accedere alla pagina, controllare autorizzazioni e licenze.</span><span class="sxs-lookup"><span data-stu-id="997cc-129">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>       

### <a name="select-data-center-location"></a><span data-ttu-id="997cc-130">Selezionare percorso Data Center</span><span class="sxs-lookup"><span data-stu-id="997cc-130">Select data center location</span></span>
<span data-ttu-id="997cc-131">Se è stato eseguito il provisioning di Microsoft Defender ATP per l'organizzazione, i dati verranno archiviati ed elaborati nella stessa area data center selezionata per i [dati di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="997cc-131">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="997cc-132">Se non si dispone di Microsoft Defender ATP, verrà chiesto di scegliere una nuova area data center specifica per Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="997cc-132">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 
 
<span data-ttu-id="997cc-133">È necessario fornire il consenso prima che i dati vengano condivisi tra i servizi e aggregati.</span><span class="sxs-lookup"><span data-stu-id="997cc-133">You need to provide consent before data is shared between services and aggregated.</span></span>

<span data-ttu-id="997cc-134">**Nuova esperienza:** A partire dal 3 maggio 2020, i clienti riceveranno gradualmente le modifiche apportate a questa esperienza.</span><span class="sxs-lookup"><span data-stu-id="997cc-134">**New experience:** Starting May 3, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="997cc-135">Per gli utenti con la nuova esperienza, il servizio seleziona automaticamente la posizione ottimale del centro dati per i dati aggregati in base ai servizi di sicurezza esistenti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="997cc-135">For those with the new experience, the service automatically selects the optimal data center location for your aggregated data based on your existing Microsoft 365 security services.</span></span> <span data-ttu-id="997cc-136">La posizione del Data Center selezionato viene visualizzata nella schermata.</span><span class="sxs-lookup"><span data-stu-id="997cc-136">The selected data center location is shown in the screen.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="997cc-137">Verificare che il servizio sia attivo</span><span class="sxs-lookup"><span data-stu-id="997cc-137">Confirm that the service is on</span></span>
<span data-ttu-id="997cc-138">Dopo aver eseguito il provisioning il servizio aggiunge:</span><span class="sxs-lookup"><span data-stu-id="997cc-138">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="997cc-139">Gestione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="997cc-139">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="997cc-140">Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="997cc-140">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="997cc-141">Funzionalità di [ricerca avanzata](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="997cc-141">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="997cc-142">![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza con Microsoft Threat Protection](../../media/mtp-on.png)
caratteristiche*Microsoft 365 Security Center con gestione degli incidenti e altre funzionalità di Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="997cc-142">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="997cc-143">Ottenere i dati di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="997cc-143">Getting Azure ATP data</span></span>
<span data-ttu-id="997cc-144">Per condividere i dati di Azure ATP con Microsoft Threat Protection, accertarsi che l'integrazione di Microsoft Cloud App Security e Azure ATP sia attivata.</span><span class="sxs-lookup"><span data-stu-id="997cc-144">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="997cc-145">Altre informazioni sull'integrazione</span><span class="sxs-lookup"><span data-stu-id="997cc-145">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="997cc-146">Disattivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="997cc-146">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="997cc-147">Per interrompere l'uso del servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > \*\* Consenso esplicito/rifiuto esplicito\*\* nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="997cc-147">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="997cc-148">Deselezionare **Attiva Microsoft Threat Protection** e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="997cc-148">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="997cc-149">Le funzionalità corrispondenti verranno rimosse dal centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="997cc-149">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="997cc-150">Ottenere assistenza</span><span class="sxs-lookup"><span data-stu-id="997cc-150">Get assistance</span></span>

<span data-ttu-id="997cc-151">Il personale del supporto tecnico Microsoft può contribuire a provisionare o deprovisionare il servizio e le risorse correlate sul tenant.</span><span class="sxs-lookup"><span data-stu-id="997cc-151">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="997cc-152">Per assistenza, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="997cc-152">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="997cc-153">Per contattare il supporto tecnico, fare riferimento a Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="997cc-153">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="997cc-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="997cc-154">Related topics</span></span>

- [<span data-ttu-id="997cc-155">Panoramica di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="997cc-155">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="997cc-156">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="997cc-156">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="997cc-157">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="997cc-157">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="997cc-158">Panoramica di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="997cc-158">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="997cc-159">Panoramica di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="997cc-159">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="997cc-160">Panoramica di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="997cc-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="997cc-161">Panoramica di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="997cc-161">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="997cc-162">Archiviazione dei dati di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="997cc-162">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
