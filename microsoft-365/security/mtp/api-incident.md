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
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="ee88b-104">API per gli eventi imprevisti di Microsoft 365 Defender e tipo di risorsa evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="ee88b-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ee88b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ee88b-105">**Applies to:**</span></span>

- <span data-ttu-id="ee88b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee88b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee88b-107">Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato.</span><span class="sxs-lookup"><span data-stu-id="ee88b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ee88b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="ee88b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ee88b-109">Un [evento](incidents-overview.md) imprevisto è una raccolta di avvisi correlati che consentono di descrivere un attacco.</span><span class="sxs-lookup"><span data-stu-id="ee88b-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="ee88b-110">Gli eventi di entità diverse nell'organizzazione vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ee88b-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="ee88b-111">Puoi usare l'API per gli eventi imprevisti per accedere a livello di codice agli eventi imprevisti e agli avvisi correlati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ee88b-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="ee88b-112">Quote e allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="ee88b-112">Quotas and resource allocation</span></span>

<span data-ttu-id="ee88b-113">È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="ee88b-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="ee88b-114">Ogni metodo dispone inoltre di quote proprie.</span><span class="sxs-lookup"><span data-stu-id="ee88b-114">Each method also has its own quotas.</span></span> <span data-ttu-id="ee88b-115">Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ee88b-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="ee88b-116">Un codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo `429` di esecuzione assegnato.</span><span class="sxs-lookup"><span data-stu-id="ee88b-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="ee88b-117">Il corpo della risposta includerà il tempo fino al ripristino della quota raggiunta.</span><span class="sxs-lookup"><span data-stu-id="ee88b-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="ee88b-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ee88b-118">Permissions</span></span>

<span data-ttu-id="ee88b-119">L'API degli eventi imprevisti richiede diversi tipi di autorizzazioni per ognuno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="ee88b-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="ee88b-120">Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo relativo al rispettivo metodo.</span><span class="sxs-lookup"><span data-stu-id="ee88b-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="ee88b-121">Metodi</span><span class="sxs-lookup"><span data-stu-id="ee88b-121">Methods</span></span>

<span data-ttu-id="ee88b-122">Metodo</span><span class="sxs-lookup"><span data-stu-id="ee88b-122">Method</span></span> | <span data-ttu-id="ee88b-123">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="ee88b-123">Return Type</span></span> | <span data-ttu-id="ee88b-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee88b-124">Description</span></span>
-|-|-
[<span data-ttu-id="ee88b-125">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="ee88b-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="ee88b-126">[Elenco operazioni non](api-incident.md) consentite</span><span class="sxs-lookup"><span data-stu-id="ee88b-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="ee88b-127">Ottenere un elenco di eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="ee88b-127">Get a list of incidents.</span></span>
[<span data-ttu-id="ee88b-128">Aggiornare incidente</span><span class="sxs-lookup"><span data-stu-id="ee88b-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="ee88b-129">Evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="ee88b-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="ee88b-130">Aggiornare un evento imprevisto specifico.</span><span class="sxs-lookup"><span data-stu-id="ee88b-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="ee88b-131">Corpo della richiesta, risposta ed esempi</span><span class="sxs-lookup"><span data-stu-id="ee88b-131">Request body, response, and examples</span></span>

<span data-ttu-id="ee88b-132">Fare riferimento ai rispettivi articoli relativi al metodo per ulteriori dettagli su come creare una richiesta o analizzare una risposta e per esempi pratici.</span><span class="sxs-lookup"><span data-stu-id="ee88b-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="ee88b-133">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="ee88b-133">Common properties</span></span>

<span data-ttu-id="ee88b-134">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ee88b-134">Property</span></span> | <span data-ttu-id="ee88b-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee88b-135">Type</span></span> | <span data-ttu-id="ee88b-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee88b-136">Description</span></span>
-|-|-
<span data-ttu-id="ee88b-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="ee88b-137">incidentId</span></span> | <span data-ttu-id="ee88b-138">long</span><span class="sxs-lookup"><span data-stu-id="ee88b-138">long</span></span> | <span data-ttu-id="ee88b-139">ID univoco dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="ee88b-139">Incident unique ID.</span></span>
<span data-ttu-id="ee88b-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="ee88b-140">redirectIncidentId</span></span> | <span data-ttu-id="ee88b-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="ee88b-141">nullable long</span></span> | <span data-ttu-id="ee88b-142">ID evento imprevisto a cui è stato unito l'evento imprevisto corrente.</span><span class="sxs-lookup"><span data-stu-id="ee88b-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="ee88b-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="ee88b-143">incidentName</span></span> | <span data-ttu-id="ee88b-144">stringa</span><span class="sxs-lookup"><span data-stu-id="ee88b-144">string</span></span> | <span data-ttu-id="ee88b-145">Nome dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="ee88b-145">The name of the Incident.</span></span>
<span data-ttu-id="ee88b-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="ee88b-146">createdTime</span></span> | <span data-ttu-id="ee88b-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ee88b-147">DateTimeOffset</span></span> | <span data-ttu-id="ee88b-148">Data e ora (in FORMATO UTC) in cui è stato creato l'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="ee88b-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="ee88b-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="ee88b-149">lastUpdateTime</span></span> | <span data-ttu-id="ee88b-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ee88b-150">DateTimeOffset</span></span> | <span data-ttu-id="ee88b-151">Data e ora (in FORMATO UTC) dell'ultimo aggiornamento dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="ee88b-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="ee88b-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="ee88b-152">assignedTo</span></span> | <span data-ttu-id="ee88b-153">stringa</span><span class="sxs-lookup"><span data-stu-id="ee88b-153">string</span></span> | <span data-ttu-id="ee88b-154">Proprietario dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="ee88b-154">Owner of the Incident.</span></span>
<span data-ttu-id="ee88b-155">gravità</span><span class="sxs-lookup"><span data-stu-id="ee88b-155">severity</span></span> | <span data-ttu-id="ee88b-156">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="ee88b-156">Enum</span></span> | <span data-ttu-id="ee88b-157">Gravità dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="ee88b-157">Severity of the Incident.</span></span> <span data-ttu-id="ee88b-158">I valori possibili sono: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="ee88b-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="ee88b-159">status</span><span class="sxs-lookup"><span data-stu-id="ee88b-159">status</span></span> | <span data-ttu-id="ee88b-160">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="ee88b-160">Enum</span></span> | <span data-ttu-id="ee88b-161">Specifica lo stato corrente dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="ee88b-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="ee88b-162">I valori possibili sono: ```Active``` , ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="ee88b-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="ee88b-163">classificazione</span><span class="sxs-lookup"><span data-stu-id="ee88b-163">classification</span></span> | <span data-ttu-id="ee88b-164">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="ee88b-164">Enum</span></span> | <span data-ttu-id="ee88b-165">Specifica dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="ee88b-165">Specification of the incident.</span></span> <span data-ttu-id="ee88b-166">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="ee88b-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="ee88b-167">determinazione</span><span class="sxs-lookup"><span data-stu-id="ee88b-167">determination</span></span> | <span data-ttu-id="ee88b-168">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="ee88b-168">Enum</span></span> | <span data-ttu-id="ee88b-169">Specifica la determinazione dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="ee88b-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="ee88b-170">I valori possibili sono: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="ee88b-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="ee88b-171">tag</span><span class="sxs-lookup"><span data-stu-id="ee88b-171">tags</span></span> | <span data-ttu-id="ee88b-172">string List</span><span class="sxs-lookup"><span data-stu-id="ee88b-172">string List</span></span> | <span data-ttu-id="ee88b-173">Elenco di tag Evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="ee88b-173">List of Incident tags.</span></span>
<span data-ttu-id="ee88b-174">avvisi</span><span class="sxs-lookup"><span data-stu-id="ee88b-174">alerts</span></span> | <span data-ttu-id="ee88b-175">Elenco avvisi</span><span class="sxs-lookup"><span data-stu-id="ee88b-175">Alert List</span></span> | <span data-ttu-id="ee88b-176">Elenco di avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="ee88b-176">List of related alerts.</span></span> <span data-ttu-id="ee88b-177">Vedi esempi nella [documentazione dell'API per gli eventi imprevisti](api-list-incidents.md) dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee88b-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ee88b-178">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="ee88b-178">Related articles</span></span>

- [<span data-ttu-id="ee88b-179">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee88b-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="ee88b-180">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="ee88b-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ee88b-181">API per gli eventi imprevisti dell'elenco</span><span class="sxs-lookup"><span data-stu-id="ee88b-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="ee88b-182">API per gli eventi imprevisti di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ee88b-182">Update incident API</span></span>](api-update-incidents.md)
