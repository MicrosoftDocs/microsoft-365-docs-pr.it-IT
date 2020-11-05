---
title: Attiva Microsoft 365 Defender in Microsoft 365 Security Center
description: Informazioni su come abilitare Microsoft 365 Defender e avviare l'integrazione degli incidenti di sicurezza e della risposta.
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
ms.openlocfilehash: c5b8cae9e4eabcb2b3c6a7eb76971784193a221d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920503"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="41fa5-104">Attiva Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41fa5-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="41fa5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="41fa5-105">**Applies to:**</span></span>
- <span data-ttu-id="41fa5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41fa5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="41fa5-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifica il processo di risposta agli incidenti mediante l'integrazione delle funzionalità chiave in Microsoft Defender per endpoint, Microsoft Defender per Office 365, Microsoft cloud app Security e Microsoft Defender per Identity.</span><span class="sxs-lookup"><span data-stu-id="41fa5-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="41fa5-108">Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41fa5-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="41fa5-109">Microsoft 365 Defender si attiva automaticamente quando i clienti idonei con le autorizzazioni necessarie visitano il Centro sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41fa5-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="41fa5-110">Leggere questo articolo per comprendere i vari prerequisiti e il provisioning di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="41fa5-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="41fa5-111">Verificare l'idoneità delle licenze e le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="41fa5-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="41fa5-112">Una licenza per un prodotto di sicurezza di Microsoft 365 generalmente autorizza l'utilizzo di Microsoft 365 Defender in Microsoft 365 Security Center senza ulteriori costi di licenza.</span><span class="sxs-lookup"><span data-stu-id="41fa5-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="41fa5-113">Si consiglia di ottenere una licenza di sicurezza Microsoft 365 E5, E5 Security, a5 o a5 o una combinazione valida di licenze che fornisce l'accesso a tutti i servizi supportati.</span><span class="sxs-lookup"><span data-stu-id="41fa5-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="41fa5-114">Per informazioni dettagliate sulla licenza, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="41fa5-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="41fa5-115">Controllare il ruolo</span><span class="sxs-lookup"><span data-stu-id="41fa5-115">Check your role</span></span>
<span data-ttu-id="41fa5-116">È necessario essere un **amministratore globale** o un **amministratore della sicurezza** in Azure Active Directory per abilitare Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="41fa5-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="41fa5-117">Visualizzare i ruoli in Azure AD</span><span class="sxs-lookup"><span data-stu-id="41fa5-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="41fa5-118">Servizi supportati</span><span class="sxs-lookup"><span data-stu-id="41fa5-118">Supported services</span></span>
<span data-ttu-id="41fa5-119">Microsoft 365 Defender aggrega i dati provenienti dai vari servizi supportati già distribuiti.</span><span class="sxs-lookup"><span data-stu-id="41fa5-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="41fa5-120">I dati verranno elaborati e archiviati in modo centralizzato per identificare nuove informazioni e rendere possibili flussi di lavoro di risposta centralizzati.</span><span class="sxs-lookup"><span data-stu-id="41fa5-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="41fa5-121">In questo caso, senza influire sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="41fa5-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="41fa5-122">Per ottenere la migliore protezione e ottimizzare Microsoft 365 Defender, è consigliabile distribuire tutti i servizi supportati applicabili sulla rete.</span><span class="sxs-lookup"><span data-stu-id="41fa5-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="41fa5-123">Per ulteriori informazioni, [vedere informazioni sulla distribuzione di servizi supportati](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="41fa5-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="41fa5-124">Prima di avviare il servizio</span><span class="sxs-lookup"><span data-stu-id="41fa5-124">Before starting the service</span></span>
<span data-ttu-id="41fa5-125">Prima di abilitare il servizio, Microsoft 365 Security Center ( [Security.Microsoft.com](https://security.microsoft.com)) Visualizza la pagina delle impostazioni di Microsoft 365 Defender quando si seleziona **incidenti** , **Centro azioni** o **ricerca** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="41fa5-125">Before you turn on the service, the Microsoft 365 security center ( [security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents** , **Action center** , or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="41fa5-126">Questi elementi di spostamento non vengono visualizzati se non si è idonei per l'utilizzo di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="41fa5-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="41fa5-127">![Immagine della pagina Microsoft 365 Defender Settings visualizzata se Microsoft 365 Defender non è stato attivato ](../../media/mtp-enable/mtp-settings.png)
 *nelle impostazioni di Microsoft 365 Defender in Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="41fa5-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="41fa5-128">Avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="41fa5-128">Starting the service</span></span>
<span data-ttu-id="41fa5-129">Per abilitare Microsoft 365 Defender, è sufficiente selezionare **attiva microsoft 365 Defender** e applicare la modifica.</span><span class="sxs-lookup"><span data-stu-id="41fa5-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="41fa5-130">È inoltre possibile accedere a questa opzione selezionando **Impostazioni** ( [Security.Microsoft.com/settings](https://security.microsoft.com/settings)) nel riquadro di spostamento e quindi selezionando **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="41fa5-130">You can also access this option by selecting **Settings** ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="41fa5-131">Se non si visualizzano le **Impostazioni** nel riquadro di spostamento o non è stato possibile accedere alla pagina, controllare autorizzazioni e licenze.</span><span class="sxs-lookup"><span data-stu-id="41fa5-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="41fa5-132">Percorso Data Center</span><span class="sxs-lookup"><span data-stu-id="41fa5-132">Data center location</span></span>
<span data-ttu-id="41fa5-133">Microsoft 365 Defender archivierà e elaborerà i dati nello [stesso percorso utilizzato da Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="41fa5-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="41fa5-134">Se non si dispone di Microsoft Defender per endpoint, viene selezionata automaticamente una nuova posizione del Data Center in base alla posizione dei servizi di sicurezza Microsoft 365 attivi.</span><span class="sxs-lookup"><span data-stu-id="41fa5-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="41fa5-135">La posizione del Data Center selezionato viene visualizzata nella schermata.</span><span class="sxs-lookup"><span data-stu-id="41fa5-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="41fa5-136">Selezionare **serve assistenza?** nel centro sicurezza Microsoft 365 contattare il supporto tecnico Microsoft per il provisioning di Microsoft 365 Defender in una posizione data center diversa.</span><span class="sxs-lookup"><span data-stu-id="41fa5-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="41fa5-137">Microsoft Defender per endpoint si riattiva automaticamente nei data center dell'Unione europea (EU) quando viene attivato tramite Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="41fa5-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="41fa5-138">Microsoft 365 Defender provvederà alla provisioning automatico nello stesso data center EU per i clienti che hanno eseguito il preprovisioning di Defender per endpoint in questo modo.</span><span class="sxs-lookup"><span data-stu-id="41fa5-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="41fa5-139">Verificare che il servizio sia attivo</span><span class="sxs-lookup"><span data-stu-id="41fa5-139">Confirm that the service is on</span></span>
<span data-ttu-id="41fa5-140">Dopo aver eseguito il provisioning il servizio aggiunge:</span><span class="sxs-lookup"><span data-stu-id="41fa5-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="41fa5-141">Gestione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="41fa5-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="41fa5-142">Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="41fa5-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="41fa5-143">Funzionalità di [ricerca avanzata](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="41fa5-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="41fa5-144">![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza con Microsoft 365 Defender caratteristiche ](../../media/mtp-enable/mtp-on.png)
 *Centro sicurezza Microsoft 365 con gestione eventi non consentiti e altre funzionalità di Microsoft 365 Defender*</span><span class="sxs-lookup"><span data-stu-id="41fa5-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="41fa5-145">Ottenere Microsoft Defender per i dati dell'identità</span><span class="sxs-lookup"><span data-stu-id="41fa5-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="41fa5-146">Per condividere Microsoft Defender per i dati di identità con Microsoft 365 Defender, verificare che Microsoft cloud app Security e Microsoft Defender per l'integrazione delle identità sia attivata.</span><span class="sxs-lookup"><span data-stu-id="41fa5-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> [<span data-ttu-id="41fa5-147">Altre informazioni sull'integrazione</span><span class="sxs-lookup"><span data-stu-id="41fa5-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a><span data-ttu-id="41fa5-148">Disattiva Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41fa5-148">Turn off Microsoft 365 Defender</span></span>
<span data-ttu-id="41fa5-149">Per interrompere l'utilizzo di Microsoft 365 Defender, accedere a **Settings**  >  **Microsoft 365 Defender**  >  **opt-in/opt-out** nel centro protezione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41fa5-149">To stop using Microsoft 365 Defender, go to **Settings** > **Microsoft 365 Defender** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="41fa5-150">Deseleziona **attiva Microsoft 365 Defender** e applica le modifiche.</span><span class="sxs-lookup"><span data-stu-id="41fa5-150">Unselect **Turn on Microsoft 365 Defender** and apply the changes.</span></span>

<span data-ttu-id="41fa5-151">Le funzionalità corrispondenti verranno rimosse dal centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41fa5-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="41fa5-152">Ottenere assistenza</span><span class="sxs-lookup"><span data-stu-id="41fa5-152">Get assistance</span></span>

<span data-ttu-id="41fa5-153">Per ottenere le risposte alle domande più frequenti sull'attivazione di Microsoft 365 Defender, [Leggi le domande frequenti](mtp-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="41fa5-153">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="41fa5-154">Il personale del supporto tecnico Microsoft può contribuire a provisionare o deprovisionare il servizio e le risorse correlate sul tenant.</span><span class="sxs-lookup"><span data-stu-id="41fa5-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="41fa5-155">Per assistenza, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41fa5-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="41fa5-156">Quando si contatta il supporto tecnico, fare riferimento a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="41fa5-156">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="41fa5-157">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="41fa5-157">Related topics</span></span>

- [<span data-ttu-id="41fa5-158">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="41fa5-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="41fa5-159">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="41fa5-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="41fa5-160">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="41fa5-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="41fa5-161">Panoramica di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41fa5-161">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="41fa5-162">Panoramica di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="41fa5-162">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="41fa5-163">Panoramica del difensore per Office 365</span><span class="sxs-lookup"><span data-stu-id="41fa5-163">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="41fa5-164">Panoramica di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="41fa5-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="41fa5-165">Panoramica di Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="41fa5-165">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="41fa5-166">Microsoft Defender per l'archiviazione dei dati di endpoint</span><span class="sxs-lookup"><span data-stu-id="41fa5-166">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
