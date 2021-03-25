---
title: Panoramica della gestione e delle API
ms.reviewer: ''
description: Informazioni sugli strumenti di gestione e sulle categorie di API in Microsoft Defender ATP
keywords: onboarding, api, siem, rbac, accesso, portale, integrazione, indagine, risposta, entità, entità, contesto utente, contesto dell'applicazione, streaming
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 94cfe1cc053be896c137e0c0b9ee02ea53dd2717
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187554"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="f3f89-104">Panoramica della gestione e delle API</span><span class="sxs-lookup"><span data-stu-id="f3f89-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3f89-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f3f89-105">**Applies to:**</span></span>
- [<span data-ttu-id="f3f89-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f3f89-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3f89-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3f89-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f3f89-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f3f89-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f3f89-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f3f89-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="f3f89-110">Defender for Endpoint supporta un'ampia gamma di opzioni per garantire che i clienti possano adottare facilmente la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="f3f89-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="f3f89-111">Riconoscendo che gli ambienti e le strutture dei clienti possono variare, Defender for Endpoint è stato creato con flessibilità e controllo granulare per soddisfare le diverse esigenze dei clienti.</span><span class="sxs-lookup"><span data-stu-id="f3f89-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="f3f89-112">Onboarding degli endpoint e accesso al portale</span><span class="sxs-lookup"><span data-stu-id="f3f89-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="f3f89-113">L'onboarding dei dispositivi è completamente integrato in Microsoft Endpoint Manager e Microsoft Intune per i dispositivi client e nel Centro sicurezza Di Azure per i dispositivi server, offrendo un'esperienza end-to-end completa di configurazione, distribuzione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="f3f89-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Security Center for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="f3f89-114">Inoltre, Microsoft Defender for Endpoint supporta Criteri di gruppo e altri strumenti di terze parti usati per la gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f3f89-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="f3f89-115">Defender for Endpoint offre un controllo specifico su ciò che gli utenti con accesso al portale possono vedere e fare attraverso la flessibilità del controllo degli accessi in base ai ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="f3f89-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="f3f89-116">Il modello RBAC supporta tutte le funzionalità della struttura dei team di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="f3f89-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="f3f89-117">Organizzazioni e team di sicurezza distribuiti a livello globale</span><span class="sxs-lookup"><span data-stu-id="f3f89-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="f3f89-118">Team per le operazioni di sicurezza dei modelli a più livelli</span><span class="sxs-lookup"><span data-stu-id="f3f89-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="f3f89-119">Divisioni completamente segregate con singoli team di gestione centralizzata della sicurezza globale</span><span class="sxs-lookup"><span data-stu-id="f3f89-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="f3f89-120">API disponibili</span><span class="sxs-lookup"><span data-stu-id="f3f89-120">Available APIs</span></span>
<span data-ttu-id="f3f89-121">La soluzione Microsoft Defender for Endpoint si basa su una piattaforma pronta per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="f3f89-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="f3f89-122">Defender for Endpoint espone gran parte dei dati e delle azioni tramite un set di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="f3f89-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f3f89-123">Queste API ti consentiranno di automatizzare i flussi di lavoro e innovare in base alle funzionalità di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3f89-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Immagine dell'API e dell'integrazione disponibili in Microsoft Defender for Endpoint](images/mdatp-apis.png)  

<span data-ttu-id="f3f89-125">Le API defender per endpoint possono essere raggruppate in tre:</span><span class="sxs-lookup"><span data-stu-id="f3f89-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="f3f89-126">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f3f89-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="f3f89-127">API di streaming di dati non elaborati</span><span class="sxs-lookup"><span data-stu-id="f3f89-127">Raw data streaming API</span></span>
- <span data-ttu-id="f3f89-128">Integrazione SIEM</span><span class="sxs-lookup"><span data-stu-id="f3f89-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="f3f89-129">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f3f89-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="f3f89-130">Defender for Endpoint offre un modello API a più livelli che espone dati e funzionalità in un modello strutturato, chiaro e facile da usare, esposto tramite un modello di autenticazione e autorizzazione standard basato su Azure AD che consente l'accesso nel contesto di utenti o applicazioni SaaS.</span><span class="sxs-lookup"><span data-stu-id="f3f89-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="f3f89-131">Il modello API è stato progettato per esporre entità e funzionalità in un formato coerente.</span><span class="sxs-lookup"><span data-stu-id="f3f89-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="f3f89-132">Guarda questo video per una breve panoramica delle API di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3f89-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="f3f89-133">**L'API** investigation espone la ricchezza di Defender per Endpoint, ovvero l'esposizione di entità calcolate o "profilate" (ad esempio, dispositivo, utente e file) ed eventi discreti (ad esempio, la creazione di processi e la creazione di file) che in genere descrivono un comportamento correlato a un'entità, consentendo l'accesso ai dati tramite interfacce di indagine che consentono l'accesso basato su query ai dati.</span><span class="sxs-lookup"><span data-stu-id="f3f89-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="f3f89-134">Per altre informazioni, vedi [API supportate.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="f3f89-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="f3f89-135">**L'API** di risposta espone la possibilità di eseguire azioni nel servizio e nei dispositivi, consentendo ai clienti di inserire indicatori, gestire le impostazioni, lo stato degli avvisi, nonché eseguire azioni di risposta su dispositivi a livello di programmazione, ad esempio isolare i dispositivi dalla rete, i file di quarantena e altri.</span><span class="sxs-lookup"><span data-stu-id="f3f89-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="raw-data-streaming-api"></a><span data-ttu-id="f3f89-136">API di streaming di dati non elaborati</span><span class="sxs-lookup"><span data-stu-id="f3f89-136">Raw data streaming API</span></span> 
<span data-ttu-id="f3f89-137">Defender for Endpoint raw data streaming API offre ai clienti la possibilità di spedire eventi e avvisi in tempo reale dalle loro istanze quando si verificano all'interno di un singolo flusso di dati, fornendo un meccanismo di recapito a bassa latenza e velocità effettiva elevata.</span><span class="sxs-lookup"><span data-stu-id="f3f89-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="f3f89-138">Le informazioni sull'evento Defender for Endpoint vengono spinte direttamente nell'archiviazione di Azure per la conservazione dei dati a lungo termine o in Hub eventi di Azure per l'utilizzo da parte di servizi di visualizzazione o motori di elaborazione dati aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f3f89-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

<span data-ttu-id="f3f89-139">Per altre informazioni, vedi [API di streaming di dati non elaborati.](raw-data-export.md)</span><span class="sxs-lookup"><span data-stu-id="f3f89-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="f3f89-140">SIEM API</span><span class="sxs-lookup"><span data-stu-id="f3f89-140">SIEM API</span></span>
<span data-ttu-id="f3f89-141">Quando abiliti l'integrazione delle informazioni di sicurezza e della gestione degli eventi (SIEM), ti consente di estrarre i rilevamenti da Microsoft Defender Security Center usando la soluzione SIEM o connettendoti direttamente all'API REST dei rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="f3f89-141">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="f3f89-142">In questo modo viene attivata la sezione dei dettagli di accesso del connettore SIEM con valori precompilato e viene creata un'applicazione nel tenant di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f3f89-142">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="f3f89-143">Per ulteriori informazioni, vedere [Integrazione SIEM.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="f3f89-143">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3f89-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f3f89-144">Related topics</span></span>
- [<span data-ttu-id="f3f89-145">Accedere alle API di Microsoft Defender for Endpoint </span><span class="sxs-lookup"><span data-stu-id="f3f89-145">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="f3f89-146">API supportate</span><span class="sxs-lookup"><span data-stu-id="f3f89-146">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="f3f89-147">Opportunità per i partner tecnici</span><span class="sxs-lookup"><span data-stu-id="f3f89-147">Technical partner opportunities</span></span>](partner-integration.md)

