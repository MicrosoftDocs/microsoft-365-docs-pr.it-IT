---
title: API per gli eventi imprevisti di Microsoft 365 Defender e tipo di risorsa evento imprevisto
description: Informazioni sui metodi e le proprietà del tipo di risorsa Evento imprevisto in Microsoft 365 Defender
keywords: evento imprevisto, eventi imprevisti, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928355"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="bd1f3-104">API per gli eventi imprevisti di Microsoft 365 Defender e tipo di risorsa evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="bd1f3-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bd1f3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bd1f3-105">**Applies to:**</span></span>

- <span data-ttu-id="bd1f3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd1f3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd1f3-107">Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bd1f3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="bd1f3-109">Un [evento](incidents-overview.md) imprevisto è una raccolta di avvisi correlati che consentono di descrivere un attacco.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="bd1f3-110">Gli eventi di entità diverse nell'organizzazione vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="bd1f3-111">Puoi usare l'API per gli eventi imprevisti per accedere a livello di codice agli eventi imprevisti e agli avvisi correlati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="bd1f3-112">Quote e allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="bd1f3-112">Quotas and resource allocation</span></span>

<span data-ttu-id="bd1f3-113">È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="bd1f3-114">Ogni metodo dispone inoltre di quote proprie.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-114">Each method also has its own quotas.</span></span> <span data-ttu-id="bd1f3-115">Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="bd1f3-116">Un codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo di `429` esecuzione assegnato.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="bd1f3-117">Il corpo della risposta includerà il tempo fino al ripristino della quota raggiunta.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="bd1f3-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bd1f3-118">Permissions</span></span>

<span data-ttu-id="bd1f3-119">L'API degli eventi imprevisti richiede diversi tipi di autorizzazioni per ognuno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="bd1f3-120">Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo relativo al rispettivo metodo.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="bd1f3-121">Metodi</span><span class="sxs-lookup"><span data-stu-id="bd1f3-121">Methods</span></span>

<span data-ttu-id="bd1f3-122">Metodo</span><span class="sxs-lookup"><span data-stu-id="bd1f3-122">Method</span></span> | <span data-ttu-id="bd1f3-123">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="bd1f3-123">Return Type</span></span> | <span data-ttu-id="bd1f3-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd1f3-124">Description</span></span>
-|-|-
[<span data-ttu-id="bd1f3-125">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="bd1f3-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="bd1f3-126">[Elenco operazioni non](api-incident.md) consentite</span><span class="sxs-lookup"><span data-stu-id="bd1f3-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="bd1f3-127">Ottenere un elenco di eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-127">Get a list of incidents.</span></span>
[<span data-ttu-id="bd1f3-128">Aggiornare incidente</span><span class="sxs-lookup"><span data-stu-id="bd1f3-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="bd1f3-129">Evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="bd1f3-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="bd1f3-130">Aggiornare un evento imprevisto specifico.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="bd1f3-131">Corpo della richiesta, risposta ed esempi</span><span class="sxs-lookup"><span data-stu-id="bd1f3-131">Request body, response, and examples</span></span>

<span data-ttu-id="bd1f3-132">Fare riferimento ai rispettivi articoli relativi al metodo per ulteriori dettagli su come creare una richiesta o analizzare una risposta e per esempi pratici.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="bd1f3-133">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="bd1f3-133">Common properties</span></span>

<span data-ttu-id="bd1f3-134">Proprietà</span><span class="sxs-lookup"><span data-stu-id="bd1f3-134">Property</span></span> | <span data-ttu-id="bd1f3-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="bd1f3-135">Type</span></span> | <span data-ttu-id="bd1f3-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd1f3-136">Description</span></span>
-|-|-
<span data-ttu-id="bd1f3-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="bd1f3-137">incidentId</span></span> | <span data-ttu-id="bd1f3-138">long</span><span class="sxs-lookup"><span data-stu-id="bd1f3-138">long</span></span> | <span data-ttu-id="bd1f3-139">ID univoco dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-139">Incident unique ID.</span></span>
<span data-ttu-id="bd1f3-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="bd1f3-140">redirectIncidentId</span></span> | <span data-ttu-id="bd1f3-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="bd1f3-141">nullable long</span></span> | <span data-ttu-id="bd1f3-142">ID evento imprevisto a cui è stato unito l'evento imprevisto corrente.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="bd1f3-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="bd1f3-143">incidentName</span></span> | <span data-ttu-id="bd1f3-144">stringa</span><span class="sxs-lookup"><span data-stu-id="bd1f3-144">string</span></span> | <span data-ttu-id="bd1f3-145">Nome dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-145">The name of the Incident.</span></span>
<span data-ttu-id="bd1f3-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="bd1f3-146">createdTime</span></span> | <span data-ttu-id="bd1f3-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="bd1f3-147">DateTimeOffset</span></span> | <span data-ttu-id="bd1f3-148">Data e ora (in FORMATO UTC) in cui è stato creato l'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="bd1f3-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="bd1f3-149">lastUpdateTime</span></span> | <span data-ttu-id="bd1f3-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="bd1f3-150">DateTimeOffset</span></span> | <span data-ttu-id="bd1f3-151">Data e ora (in FORMATO UTC) dell'ultimo aggiornamento dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="bd1f3-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="bd1f3-152">assignedTo</span></span> | <span data-ttu-id="bd1f3-153">stringa</span><span class="sxs-lookup"><span data-stu-id="bd1f3-153">string</span></span> | <span data-ttu-id="bd1f3-154">Proprietario dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-154">Owner of the Incident.</span></span>
<span data-ttu-id="bd1f3-155">gravità</span><span class="sxs-lookup"><span data-stu-id="bd1f3-155">severity</span></span> | <span data-ttu-id="bd1f3-156">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bd1f3-156">Enum</span></span> | <span data-ttu-id="bd1f3-157">Gravità dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-157">Severity of the Incident.</span></span> <span data-ttu-id="bd1f3-158">I valori possibili sono: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="bd1f3-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="bd1f3-159">status</span><span class="sxs-lookup"><span data-stu-id="bd1f3-159">status</span></span> | <span data-ttu-id="bd1f3-160">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bd1f3-160">Enum</span></span> | <span data-ttu-id="bd1f3-161">Specifica lo stato corrente dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="bd1f3-162">I valori possibili sono: ```Active``` , ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="bd1f3-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="bd1f3-163">classificazione</span><span class="sxs-lookup"><span data-stu-id="bd1f3-163">classification</span></span> | <span data-ttu-id="bd1f3-164">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bd1f3-164">Enum</span></span> | <span data-ttu-id="bd1f3-165">Specifica dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-165">Specification of the incident.</span></span> <span data-ttu-id="bd1f3-166">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="bd1f3-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="bd1f3-167">determinazione</span><span class="sxs-lookup"><span data-stu-id="bd1f3-167">determination</span></span> | <span data-ttu-id="bd1f3-168">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="bd1f3-168">Enum</span></span> | <span data-ttu-id="bd1f3-169">Specifica la determinazione dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="bd1f3-170">I valori possibili sono: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="bd1f3-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="bd1f3-171">tag</span><span class="sxs-lookup"><span data-stu-id="bd1f3-171">tags</span></span> | <span data-ttu-id="bd1f3-172">string List</span><span class="sxs-lookup"><span data-stu-id="bd1f3-172">string List</span></span> | <span data-ttu-id="bd1f3-173">Elenco di tag Evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-173">List of Incident tags.</span></span>
<span data-ttu-id="bd1f3-174">avvisi</span><span class="sxs-lookup"><span data-stu-id="bd1f3-174">alerts</span></span> | <span data-ttu-id="bd1f3-175">Elenco avvisi</span><span class="sxs-lookup"><span data-stu-id="bd1f3-175">Alert List</span></span> | <span data-ttu-id="bd1f3-176">Elenco di avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-176">List of related alerts.</span></span> <span data-ttu-id="bd1f3-177">Vedi gli esempi nella [documentazione dell'API per gli eventi](api-list-incidents.md) imprevisti dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd1f3-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bd1f3-178">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="bd1f3-178">Related articles</span></span>

- [<span data-ttu-id="bd1f3-179">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd1f3-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="bd1f3-180">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="bd1f3-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="bd1f3-181">API per gli eventi imprevisti dell'elenco</span><span class="sxs-lookup"><span data-stu-id="bd1f3-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="bd1f3-182">API per gli eventi imprevisti di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="bd1f3-182">Update incident API</span></span>](api-update-incidents.md)
