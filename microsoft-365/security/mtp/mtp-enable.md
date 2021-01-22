---
title: Attivare Microsoft 365 Defender nel Centro sicurezza Microsoft 365
description: Informazioni su come abilitare Microsoft 365 Defender e iniziare a integrare l'incidente di sicurezza e la risposta.
keywords: introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, posizione dei dati, autorizzazioni necessarie, idoneità alle licenze, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930223"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="b1a4f-104">Attivare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1a4f-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b1a4f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b1a4f-105">**Applies to:**</span></span>
- <span data-ttu-id="b1a4f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1a4f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b1a4f-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifica il processo di risposta agli incidenti integrando le principali funzionalità tra Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="b1a4f-108">Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="b1a4f-109">Microsoft 365 Defender si attiva automaticamente quando i clienti idonei con le autorizzazioni necessarie visitano il Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="b1a4f-110">Leggere questo articolo per comprendere i diversi prerequisiti e come viene eseguito il provisioning di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="b1a4f-111">Verificare l'idoneità delle licenze e le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="b1a4f-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="b1a4f-112">Una licenza per un prodotto di sicurezza di Microsoft 365 in genere consente di usare Microsoft 365 Defender nel Centro sicurezza Microsoft 365 senza costi di licenza aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="b1a4f-113">È consigliabile ottenere una licenza di Microsoft 365 E5, E5 Security, A5 o A5 Security o una combinazione valida di licenze che fornisce l'accesso a tutti i servizi supportati.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="b1a4f-114">Per informazioni dettagliate sulle licenze, [leggere i requisiti di licenza.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="b1a4f-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="b1a4f-115">Controllare il ruolo</span><span class="sxs-lookup"><span data-stu-id="b1a4f-115">Check your role</span></span>

<span data-ttu-id="b1a4f-116">Per attivare  Microsoft 365 Defender, è necessario essere un amministratore globale o un amministratore della sicurezza **in** Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="b1a4f-117">Visualizzare i ruoli in Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1a4f-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="b1a4f-118">Servizi supportati</span><span class="sxs-lookup"><span data-stu-id="b1a4f-118">Supported services</span></span>

<span data-ttu-id="b1a4f-119">Microsoft 365 Defender aggrega i dati dei vari servizi supportati già distribuiti.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="b1a4f-120">I dati verranno elaborati e archiviati centralmente per identificare nuove informazioni dettagliate e rendere possibili flussi di lavoro di risposta centralizzati.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="b1a4f-121">Questa operazione non influisce sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="b1a4f-122">Per ottenere la migliore protezione e ottimizzare Microsoft 365 Defender, è consigliabile distribuire tutti i servizi supportati applicabili nella rete.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="b1a4f-123">Per ulteriori informazioni, [vedere Distribuzione dei servizi supportati .](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="b1a4f-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="b1a4f-124">Prima di avviare il servizio</span><span class="sxs-lookup"><span data-stu-id="b1a4f-124">Before starting the service</span></span>

<span data-ttu-id="b1a4f-125">Prima di attivare il servizio, il Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)) mostra la pagina delle impostazioni di  Microsoft 365 Defender quando si seleziona Eventi imprevisti, Centro notifiche o Ricerca nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="b1a4f-126">Questi elementi di spostamento non vengono visualizzati se non si è idonei a usare Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="b1a4f-127">![Immagine della pagina delle impostazioni di Microsoft 365 Defender visualizzata se Microsoft 365 Defender non è stato attivato nelle impostazioni di ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender nel Centro sicurezza Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="b1a4f-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="b1a4f-128">Avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="b1a4f-128">Starting the service</span></span>

<span data-ttu-id="b1a4f-129">Per attivare Microsoft 365 Defender, è sufficiente selezionare **Attiva Microsoft 365 Defender** e applicare la modifica.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="b1a4f-130">È anche possibile accedere a questa opzione selezionando Impostazioni **(** [security.microsoft.com/settings](https://security.microsoft.com/settings)) nel riquadro di spostamento e quindi selezionando **Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="b1a4f-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="b1a4f-131">Se non vedi Impostazioni **nel** riquadro di spostamento o non hai potuto accedere alla pagina, controlla le autorizzazioni e le licenze.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="b1a4f-132">Posizione del data center</span><span class="sxs-lookup"><span data-stu-id="b1a4f-132">Data center location</span></span>

<span data-ttu-id="b1a4f-133">Microsoft 365 Defender archivierà ed eelaborare i dati nella stessa posizione usata [da Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="b1a4f-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="b1a4f-134">Se non si dispone di Microsoft Defender per Endpoint, viene selezionata automaticamente una nuova posizione del data center in base alla posizione dei servizi di sicurezza di Microsoft 365 attivi.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="b1a4f-135">La posizione del data center selezionato viene visualizzata sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="b1a4f-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="b1a4f-137">Microsoft Defender for Endpoint effettua automaticamente il provisioning nei data center dell'Unione Europea (UE) quando è attivato tramite Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="b1a4f-138">Microsoft 365 Defender eseguirà automaticamente il provisioning nello stesso data center dell'Unione Europea per i clienti che hanno effettuato il provisioning di Defender per Endpoint in questo modo.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="b1a4f-139">Verificare che il servizio sia attivo</span><span class="sxs-lookup"><span data-stu-id="b1a4f-139">Confirm that the service is on</span></span>

<span data-ttu-id="b1a4f-140">Dopo aver eseguito il provisioning il servizio aggiunge:</span><span class="sxs-lookup"><span data-stu-id="b1a4f-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="b1a4f-141">Gestione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="b1a4f-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="b1a4f-142">Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="b1a4f-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="b1a4f-143">[Funzionalità di ricerca](advanced-hunting-overview.md) avanzate</span><span class="sxs-lookup"><span data-stu-id="b1a4f-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="b1a4f-144">![Immagine del riquadro di spostamento del Centro sicurezza Microsoft 365 con il Centro sicurezza Microsoft 365 Defender con gestione degli eventi imprevisti e altre funzionalità di ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender*</span><span class="sxs-lookup"><span data-stu-id="b1a4f-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="b1a4f-145">Recupero dei dati di Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b1a4f-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="b1a4f-146">Per condividere i dati di Microsoft Defender for Identity con Microsoft 365 Defender, verificare che l'integrazione di Microsoft Cloud App Security e Microsoft Defender for Identity sia attivata.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="b1a4f-147">[Ulteriori informazioni su questa integrazione.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="b1a4f-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="b1a4f-148">Ottenere assistenza</span><span class="sxs-lookup"><span data-stu-id="b1a4f-148">Get assistance</span></span>

<span data-ttu-id="b1a4f-149">Per ottenere risposte alle domande più frequenti sull'attivazione di Microsoft 365 Defender, [leggere le domande frequenti.](mtp-enable-faq.md)</span><span class="sxs-lookup"><span data-stu-id="b1a4f-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="b1a4f-150">Il personale di supporto Microsoft può aiutare a eseguire il provisioning o il deprovisioning del servizio e delle risorse correlate nel tenant.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="b1a4f-151">Per assistenza, selezionare **Serve aiuto?** nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b1a4f-152">Quando si contatta il supporto tecnico, menzionare Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1a4f-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b1a4f-153">Related topics</span></span>

- [<span data-ttu-id="b1a4f-154">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="b1a4f-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="b1a4f-155">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b1a4f-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="b1a4f-156">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="b1a4f-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="b1a4f-157">Panoramica di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1a4f-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="b1a4f-158">Panoramica di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b1a4f-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="b1a4f-159">Panoramica di Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="b1a4f-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="b1a4f-160">Panoramica di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b1a4f-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="b1a4f-161">Panoramica di Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b1a4f-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="b1a4f-162">Microsoft Defender per l'archiviazione dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="b1a4f-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
