---
title: Attivare Microsoft 365 Defender nel centro sicurezza Microsoft 365 sicurezza
description: Scopri come abilitare Microsoft 365 Defender e iniziare a integrare l'incidente di sicurezza e la risposta.
keywords: introduzione, abilitare Microsoft 365 Defender, Microsoft 365 Defender, M365, sicurezza, posizione dei dati, autorizzazioni necessarie, idoneità alla licenza, pagina delle impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3f05cc8c9b2509f8c95b802f56905e2859221cd2
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861600"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="39241-104">Attivare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39241-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="39241-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="39241-105">**Applies to:**</span></span>
- <span data-ttu-id="39241-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39241-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="39241-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifica il processo di risposta agli eventi imprevisti integrando le funzionalità chiave in Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="39241-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="39241-108">Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39241-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="39241-109">Microsoft 365 Defender si attiva automaticamente quando i clienti idonei con le autorizzazioni necessarie visitano Microsoft 365 centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="39241-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="39241-110">Leggere questo articolo per comprendere diversi prerequisiti e come viene eseguito il provisioning Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="39241-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="39241-111">Verificare l'idoneità della licenza e le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="39241-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="39241-112">Una licenza per un prodotto Microsoft 365 sicurezza in genere ti autorizza a usare Microsoft 365 Defender nel centro sicurezza Microsoft 365 senza costi aggiuntivi per le licenze.</span><span class="sxs-lookup"><span data-stu-id="39241-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="39241-113">Ti consigliamo di ottenere una licenza Microsoft 365 E5, E5 Security, A5 o A5 Security o una combinazione valida di licenze che fornisce l'accesso a tutti i servizi supportati.</span><span class="sxs-lookup"><span data-stu-id="39241-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="39241-114">Per informazioni dettagliate sulle licenze, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="39241-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="39241-115">Controllare il ruolo</span><span class="sxs-lookup"><span data-stu-id="39241-115">Check your role</span></span>

<span data-ttu-id="39241-116">Devi essere un **amministratore globale o** un amministratore della sicurezza in Azure Active Directory per attivare Microsoft 365 Defender. </span><span class="sxs-lookup"><span data-stu-id="39241-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="39241-117">Visualizzare i ruoli in Azure AD</span><span class="sxs-lookup"><span data-stu-id="39241-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="39241-118">Servizi supportati</span><span class="sxs-lookup"><span data-stu-id="39241-118">Supported services</span></span>

<span data-ttu-id="39241-119">Microsoft 365 Defender aggrega i dati dei vari servizi supportati che hai già distribuito.</span><span class="sxs-lookup"><span data-stu-id="39241-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="39241-120">I dati verranno processati e archiviati centralmente per identificare nuove informazioni dettagliate e rendere possibili flussi di lavoro di risposta centralizzati.</span><span class="sxs-lookup"><span data-stu-id="39241-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="39241-121">Questa operazione non influisce sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="39241-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="39241-122">Per ottenere la migliore protezione e ottimizzare Microsoft 365 Defender, ti consigliamo di distribuire tutti i servizi supportati applicabili nella rete.</span><span class="sxs-lookup"><span data-stu-id="39241-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="39241-123">Per ulteriori informazioni, [vedere distribuzione di servizi supportati.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="39241-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="39241-124">Onboard al servizio</span><span class="sxs-lookup"><span data-stu-id="39241-124">Onboard to the service</span></span>
<span data-ttu-id="39241-125">L'onboarding Microsoft 365 Defender è semplice.</span><span class="sxs-lookup"><span data-stu-id="39241-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="39241-126">Dal menu di spostamento seleziona qualsiasi Microsoft 365 Defender, ad esempio Eventi imprevisti, Ricerca, Centro notifiche o Analisi delle minacce per avviare il processo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="39241-126">From the navigation menu, select any Microsoft 365 Defender items, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="39241-127">Posizione del data center</span><span class="sxs-lookup"><span data-stu-id="39241-127">Data center location</span></span>

<span data-ttu-id="39241-128">Microsoft 365 Defender archivierà ed eelaborare i dati nella [stessa posizione usata da Microsoft Defender per Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="39241-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="39241-129">Se non si dispone di Microsoft Defender for Endpoint, viene selezionata automaticamente una nuova posizione del data center in base alla posizione dei servizi di sicurezza Microsoft 365 attivi.</span><span class="sxs-lookup"><span data-stu-id="39241-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="39241-130">La posizione del data center selezionata viene visualizzata sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="39241-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="39241-131">Selezionare **Serve assistenza?** nel centro sicurezza Microsoft 365 per contattare il supporto Tecnico Microsoft per il provisioning di Microsoft 365 Defender in un'altra posizione del data center.</span><span class="sxs-lookup"><span data-stu-id="39241-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="39241-132">In passato, Microsoft Defender for Endpoint eseguiva automaticamente il provisioning nei data center dell'Unione Europea (UE) quando è attivato tramite Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="39241-132">In the past, Microsoft Defender for Endpoint automatically provisioned in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="39241-133">Microsoft 365 Defender eseguirà automaticamente il provisioning nello stesso data center dell'UE per i clienti che hanno effettuato il provisioning di Defender per Endpoint in questo modo in passato.</span><span class="sxs-lookup"><span data-stu-id="39241-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner in the past.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="39241-134">Verificare che il servizio sia attivo</span><span class="sxs-lookup"><span data-stu-id="39241-134">Confirm that the service is on</span></span>

<span data-ttu-id="39241-135">Dopo aver eseguito il provisioning il servizio aggiunge:</span><span class="sxs-lookup"><span data-stu-id="39241-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="39241-136">Gestione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="39241-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="39241-137">Coda di avvisi</span><span class="sxs-lookup"><span data-stu-id="39241-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="39241-138">Un centro operativo per la gestione delle [analisi e risposte automatiche](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="39241-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="39241-139">[Funzionalità di ricerca](advanced-hunting-overview.md) avanzate</span><span class="sxs-lookup"><span data-stu-id="39241-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="39241-140">Analisi delle minacce</span><span class="sxs-lookup"><span data-stu-id="39241-140">Threat analytics</span></span>

<span data-ttu-id="39241-141">![Immagine del riquadro Microsoft 365 di spostamento del centro sicurezza con Microsoft 365 Defender Microsoft 365 centro sicurezza con gestione degli eventi imprevisti e altre ](../../media/overview-incident.png)
 *funzionalità Microsoft 365 Defender*</span><span class="sxs-lookup"><span data-stu-id="39241-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="39241-142">Recupero dei dati di Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="39241-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="39241-143">Per abilitare l'integrazione con Microsoft Cloud App Security, devi accedere al Microsoft Cloud App Security almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="39241-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="39241-144">Ottenere assistenza</span><span class="sxs-lookup"><span data-stu-id="39241-144">Get assistance</span></span>

<span data-ttu-id="39241-145">Per ottenere risposte alle domande più frequenti sull'attivazione di Microsoft 365 Defender, leggere [le domande frequenti](m365d-enable-faq.md).</span><span class="sxs-lookup"><span data-stu-id="39241-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="39241-146">Il personale di supporto Microsoft può aiutare a eseguire il provisioning o il deprovisioning del servizio e delle risorse correlate nel tenant.</span><span class="sxs-lookup"><span data-stu-id="39241-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="39241-147">Per assistenza, selezionare **Serve assistenza?** nel centro Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="39241-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="39241-148">Quando si contatta il supporto, menzionare Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="39241-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="39241-149">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="39241-149">Related topics</span></span>

- [<span data-ttu-id="39241-150">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="39241-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="39241-151">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="39241-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="39241-152">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="39241-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="39241-153">Microsoft 365 Panoramica di Defender</span><span class="sxs-lookup"><span data-stu-id="39241-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="39241-154">Panoramica di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39241-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="39241-155">Panoramica di Defender Office 365</span><span class="sxs-lookup"><span data-stu-id="39241-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="39241-156">Panoramica di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="39241-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="39241-157">Panoramica di Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="39241-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="39241-158">Archiviazione dei dati di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39241-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
