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
ms.openlocfilehash: b6ac30f7e32bbec80952ad4f2104032886b11503
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016344"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="34e1e-104">Attivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="34e1e-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="34e1e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="34e1e-105">**Applies to:**</span></span>
- <span data-ttu-id="34e1e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="34e1e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="34e1e-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifica il processo di risposta agli incidenti mediante l'integrazione di funzionalità chiave in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft cloud app Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="34e1e-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="34e1e-108">Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34e1e-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="34e1e-109">Microsoft Threat Protection si attiva automaticamente quando i clienti idonei con le autorizzazioni necessarie visitano Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="34e1e-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="34e1e-110">Leggere questo articolo per comprendere i vari prerequisiti e il provisioning di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="34e1e-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="34e1e-111">Verificare l'idoneità delle licenze e le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="34e1e-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="34e1e-112">Una licenza per un prodotto di sicurezza Microsoft 365 in genere consente di utilizzare Microsoft Threat Protection in Microsoft 365 Security Center senza ulteriori costi di licenza.</span><span class="sxs-lookup"><span data-stu-id="34e1e-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="34e1e-113">Si consiglia di ottenere una licenza di sicurezza Microsoft 365 E5, E5 Security, a5 o a5 o una combinazione valida di licenze che fornisce l'accesso a tutti i servizi supportati.</span><span class="sxs-lookup"><span data-stu-id="34e1e-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="34e1e-114">Per informazioni dettagliate sulla licenza, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="34e1e-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="34e1e-115">Controllare il ruolo</span><span class="sxs-lookup"><span data-stu-id="34e1e-115">Check your role</span></span>
<span data-ttu-id="34e1e-116">Per abilitare Microsoft Threat Protection, è necessario essere un amministratore **globale** o un **amministratore della sicurezza** in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34e1e-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="34e1e-117">Visualizzare i ruoli in Azure AD</span><span class="sxs-lookup"><span data-stu-id="34e1e-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="34e1e-118">Servizi supportati</span><span class="sxs-lookup"><span data-stu-id="34e1e-118">Supported services</span></span>
<span data-ttu-id="34e1e-119">Microsoft Threat Protection aggrega i dati provenienti dai vari servizi supportati già distribuiti.</span><span class="sxs-lookup"><span data-stu-id="34e1e-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="34e1e-120">I dati verranno elaborati e archiviati in modo centralizzato per identificare nuove informazioni e rendere possibili flussi di lavoro di risposta centralizzati.</span><span class="sxs-lookup"><span data-stu-id="34e1e-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="34e1e-121">In questo caso, senza influire sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="34e1e-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="34e1e-122">Per ottenere la migliore protezione e ottimizzare Microsoft Threat Protection, è consigliabile distribuire tutti i servizi supportati in rete.</span><span class="sxs-lookup"><span data-stu-id="34e1e-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="34e1e-123">Per ulteriori informazioni, [vedere informazioni sulla distribuzione di servizi supportati](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="34e1e-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="34e1e-124">Prima di avviare il servizio</span><span class="sxs-lookup"><span data-stu-id="34e1e-124">Before starting the service</span></span>
<span data-ttu-id="34e1e-125">Prima di abilitare il servizio, Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) consente di visualizzare la pagina delle impostazioni di protezione delle minacce di Microsoft quando si seleziona **incidenti**, **Centro azioni**o **ricerca** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="34e1e-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="34e1e-126">Questi elementi di spostamento non vengono visualizzati se non si è idonei per l'utilizzo di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="34e1e-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="34e1e-127">![Immagine della pagina delle impostazioni di protezione dalle minacce di Microsoft visualizzata se Microsoft Threat Protection non è stato attivato ](../../media/mtp-enable/mtp-settings.png)
 *nelle impostazioni di Microsoft Threat Protection in Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="34e1e-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="34e1e-128">Avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="34e1e-128">Starting the service</span></span>
<span data-ttu-id="34e1e-129">Per abilitare Microsoft Threat Protection, è sufficiente selezionare **attiva Microsoft Threat Protection** e applicare la modifica.</span><span class="sxs-lookup"><span data-stu-id="34e1e-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="34e1e-130">È inoltre possibile accedere a questa opzione selezionando **Impostazioni** ([Security.Microsoft.com/settings](https://security.microsoft.com/settings)) nel riquadro di spostamento e quindi selezionando **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="34e1e-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="34e1e-131">Se non si visualizzano le **Impostazioni** nel riquadro di spostamento o non è stato possibile accedere alla pagina, controllare autorizzazioni e licenze.</span><span class="sxs-lookup"><span data-stu-id="34e1e-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="34e1e-132">Percorso Data Center</span><span class="sxs-lookup"><span data-stu-id="34e1e-132">Data center location</span></span>
<span data-ttu-id="34e1e-133">Microsoft Threat Protection archivierà ed elaborerà i dati nello [stesso percorso utilizzato da Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="34e1e-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="34e1e-134">Se non si dispone di Microsoft Defender ATP, viene selezionata automaticamente una nuova posizione del Data Center in base alla posizione dei servizi di sicurezza Microsoft 365 attivi.</span><span class="sxs-lookup"><span data-stu-id="34e1e-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="34e1e-135">La posizione del Data Center selezionato viene visualizzata nella schermata.</span><span class="sxs-lookup"><span data-stu-id="34e1e-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="34e1e-136">Selezionare **serve assistenza?** nel centro sicurezza Microsoft 365 contattare il supporto tecnico Microsoft per il provisioning di Microsoft Threat Protection in una posizione data center diversa.</span><span class="sxs-lookup"><span data-stu-id="34e1e-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft Threat Protection in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="34e1e-137">Microsoft Defender ATP accantona automaticamente i data center dell'Unione europea (EU) quando viene attivato tramite il Centro sicurezza di Azure.</span><span class="sxs-lookup"><span data-stu-id="34e1e-137">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="34e1e-138">Microsoft Threat Protection provisionerà automaticamente nello stesso data center dell'Unione europea per i clienti che hanno eseguito il provisioning di Microsoft Defender ATP in questo modo.</span><span class="sxs-lookup"><span data-stu-id="34e1e-138">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="34e1e-139">Verificare che il servizio sia attivo</span><span class="sxs-lookup"><span data-stu-id="34e1e-139">Confirm that the service is on</span></span>
<span data-ttu-id="34e1e-140">Dopo aver eseguito il provisioning il servizio aggiunge:</span><span class="sxs-lookup"><span data-stu-id="34e1e-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="34e1e-141">Gestione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="34e1e-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="34e1e-142">Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="34e1e-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="34e1e-143">Funzionalità di [ricerca avanzata](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="34e1e-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="34e1e-144">![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza con Microsoft Threat Protection caratteristiche ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Security Center con gestione degli incidenti e altre funzionalità di Microsoft Threat Protection*</span><span class="sxs-lookup"><span data-stu-id="34e1e-144">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="34e1e-145">Ottenere i dati di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="34e1e-145">Getting Azure ATP data</span></span>
<span data-ttu-id="34e1e-146">Per condividere i dati di Azure ATP con Microsoft Threat Protection, accertarsi che l'integrazione di Microsoft Cloud App Security e Azure ATP sia attivata.</span><span class="sxs-lookup"><span data-stu-id="34e1e-146">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="34e1e-147">Altre informazioni sull'integrazione</span><span class="sxs-lookup"><span data-stu-id="34e1e-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="34e1e-148">Disattivare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="34e1e-148">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="34e1e-149">Per interrompere l'uso del servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > \*\* Consenso esplicito/rifiuto esplicito\*\* nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34e1e-149">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="34e1e-150">Deselezionare **attiva Microsoft Threat Protection** e applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="34e1e-150">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="34e1e-151">Le funzionalità corrispondenti verranno rimosse dal centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34e1e-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="34e1e-152">Ottenere assistenza</span><span class="sxs-lookup"><span data-stu-id="34e1e-152">Get assistance</span></span>

<span data-ttu-id="34e1e-153">Per ottenere le risposte alle domande più frequenti relative all'attivazione di Microsoft Threat Protection, [leggere le FAQ](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="34e1e-153">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="34e1e-154">Il personale del supporto tecnico Microsoft può contribuire a provisionare o deprovisionare il servizio e le risorse correlate sul tenant.</span><span class="sxs-lookup"><span data-stu-id="34e1e-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="34e1e-155">Per assistenza, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34e1e-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="34e1e-156">Per contattare il supporto tecnico, fare riferimento a Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="34e1e-156">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="34e1e-157">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="34e1e-157">Related topics</span></span>

- [<span data-ttu-id="34e1e-158">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="34e1e-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="34e1e-159">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="34e1e-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="34e1e-160">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="34e1e-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="34e1e-161">Panoramica di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="34e1e-161">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="34e1e-162">Panoramica di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="34e1e-162">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="34e1e-163">Panoramica di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="34e1e-163">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="34e1e-164">Panoramica di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="34e1e-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="34e1e-165">Panoramica di Azure ATP</span><span class="sxs-lookup"><span data-stu-id="34e1e-165">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="34e1e-166">Archiviazione dei dati di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="34e1e-166">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)