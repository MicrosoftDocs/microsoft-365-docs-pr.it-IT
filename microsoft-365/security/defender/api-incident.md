---
title: Microsoft 365 API defender incidents e il tipo di risorsa eventi imprevisti
description: Informazioni sui metodi e le proprietà del tipo di risorsa Eventi imprevisti in Microsoft 365 Defender
keywords: eventi imprevisti, eventi imprevisti, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 587d6107b0c09b2178311d8da6606968e7fda083
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730931"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="931bf-104">Microsoft 365 API eventi imprevisti defender e tipo di risorsa eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="931bf-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="931bf-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="931bf-105">**Applies to:**</span></span>

- [<span data-ttu-id="931bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="931bf-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="931bf-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="931bf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="931bf-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="931bf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="931bf-109">Un [evento imprevisto](incidents-overview.md) è una raccolta di avvisi correlati che consentono di descrivere un attacco.</span><span class="sxs-lookup"><span data-stu-id="931bf-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="931bf-110">Gli eventi di entità diverse nell'organizzazione vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="931bf-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="931bf-111">Puoi usare l'API eventi imprevisti per accedere a livello di programmazione agli eventi imprevisti e agli avvisi correlati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="931bf-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="931bf-112">Quote e allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="931bf-112">Quotas and resource allocation</span></span>

<span data-ttu-id="931bf-113">È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="931bf-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="931bf-114">Ogni metodo ha anche le proprie quote.</span><span class="sxs-lookup"><span data-stu-id="931bf-114">Each method also has its own quotas.</span></span> <span data-ttu-id="931bf-115">Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="931bf-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="931bf-116">Un codice di risposta HTTP indica che hai raggiunto una quota, in base al numero di richieste inviate o al tempo `429` di esecuzione assegnato.</span><span class="sxs-lookup"><span data-stu-id="931bf-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="931bf-117">Il corpo della risposta includerà il tempo fino a quando la quota raggiunta non verrà reimpostata.</span><span class="sxs-lookup"><span data-stu-id="931bf-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="931bf-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="931bf-118">Permissions</span></span>

<span data-ttu-id="931bf-119">L'API eventi imprevisti richiede diversi tipi di autorizzazioni per ognuno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="931bf-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="931bf-120">Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo relativo al rispettivo metodo.</span><span class="sxs-lookup"><span data-stu-id="931bf-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="931bf-121">Metodi</span><span class="sxs-lookup"><span data-stu-id="931bf-121">Methods</span></span>

<span data-ttu-id="931bf-122">Metodo</span><span class="sxs-lookup"><span data-stu-id="931bf-122">Method</span></span> | <span data-ttu-id="931bf-123">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="931bf-123">Return Type</span></span> | <span data-ttu-id="931bf-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="931bf-124">Description</span></span>
-|-|-
[<span data-ttu-id="931bf-125">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="931bf-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="931bf-126">[Elenco operazioni](api-incident.md) non consentite</span><span class="sxs-lookup"><span data-stu-id="931bf-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="931bf-127">Ottenere un elenco di eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="931bf-127">Get a list of incidents.</span></span>
[<span data-ttu-id="931bf-128">Aggiornare incidente</span><span class="sxs-lookup"><span data-stu-id="931bf-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="931bf-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="931bf-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="931bf-130">Aggiornare un evento imprevisto specifico.</span><span class="sxs-lookup"><span data-stu-id="931bf-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="931bf-131">Corpo, risposta ed esempi della richiesta</span><span class="sxs-lookup"><span data-stu-id="931bf-131">Request body, response, and examples</span></span>

<span data-ttu-id="931bf-132">Per ulteriori dettagli su come creare una richiesta o analizzare una risposta, vedere gli articoli relativi ai rispettivi metodi e per esempi pratici.</span><span class="sxs-lookup"><span data-stu-id="931bf-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="931bf-133">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="931bf-133">Common properties</span></span>

<span data-ttu-id="931bf-134">Proprietà</span><span class="sxs-lookup"><span data-stu-id="931bf-134">Property</span></span> | <span data-ttu-id="931bf-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="931bf-135">Type</span></span> | <span data-ttu-id="931bf-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="931bf-136">Description</span></span>
-|-|-
<span data-ttu-id="931bf-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="931bf-137">incidentId</span></span> | <span data-ttu-id="931bf-138">long</span><span class="sxs-lookup"><span data-stu-id="931bf-138">long</span></span> | <span data-ttu-id="931bf-139">ID univoco dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-139">Incident unique ID.</span></span>
<span data-ttu-id="931bf-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="931bf-140">redirectIncidentId</span></span> | <span data-ttu-id="931bf-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="931bf-141">nullable long</span></span> | <span data-ttu-id="931bf-142">ID evento imprevisto a cui è stato unito l'evento imprevisto corrente.</span><span class="sxs-lookup"><span data-stu-id="931bf-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="931bf-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="931bf-143">incidentName</span></span> | <span data-ttu-id="931bf-144">stringa</span><span class="sxs-lookup"><span data-stu-id="931bf-144">string</span></span> | <span data-ttu-id="931bf-145">Nome dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-145">The name of the Incident.</span></span>
<span data-ttu-id="931bf-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="931bf-146">createdTime</span></span> | <span data-ttu-id="931bf-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="931bf-147">DateTimeOffset</span></span> | <span data-ttu-id="931bf-148">Data e ora (in UTC) in cui è stato creato l'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="931bf-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="931bf-149">lastUpdateTime</span></span> | <span data-ttu-id="931bf-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="931bf-150">DateTimeOffset</span></span> | <span data-ttu-id="931bf-151">Data e ora (in UTC) dell'ultimo aggiornamento dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="931bf-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="931bf-152">assignedTo</span></span> | <span data-ttu-id="931bf-153">stringa</span><span class="sxs-lookup"><span data-stu-id="931bf-153">string</span></span> | <span data-ttu-id="931bf-154">Proprietario dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-154">Owner of the Incident.</span></span>
<span data-ttu-id="931bf-155">gravità</span><span class="sxs-lookup"><span data-stu-id="931bf-155">severity</span></span> | <span data-ttu-id="931bf-156">Enum</span><span class="sxs-lookup"><span data-stu-id="931bf-156">Enum</span></span> | <span data-ttu-id="931bf-157">Gravità dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-157">Severity of the Incident.</span></span> <span data-ttu-id="931bf-158">I valori possibili sono: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="931bf-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="931bf-159">status</span><span class="sxs-lookup"><span data-stu-id="931bf-159">status</span></span> | <span data-ttu-id="931bf-160">Enum</span><span class="sxs-lookup"><span data-stu-id="931bf-160">Enum</span></span> | <span data-ttu-id="931bf-161">Specifica lo stato corrente dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="931bf-162">I valori possibili sono: ```Active``` ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="931bf-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="931bf-163">classificazione</span><span class="sxs-lookup"><span data-stu-id="931bf-163">classification</span></span> | <span data-ttu-id="931bf-164">Enum</span><span class="sxs-lookup"><span data-stu-id="931bf-164">Enum</span></span> | <span data-ttu-id="931bf-165">Specifica dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-165">Specification of the incident.</span></span> <span data-ttu-id="931bf-166">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="931bf-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="931bf-167">determinazione</span><span class="sxs-lookup"><span data-stu-id="931bf-167">determination</span></span> | <span data-ttu-id="931bf-168">Enum</span><span class="sxs-lookup"><span data-stu-id="931bf-168">Enum</span></span> | <span data-ttu-id="931bf-169">Specifica la determinazione dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="931bf-170">I valori possibili sono: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="931bf-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="931bf-171">tag</span><span class="sxs-lookup"><span data-stu-id="931bf-171">tags</span></span> | <span data-ttu-id="931bf-172">string List</span><span class="sxs-lookup"><span data-stu-id="931bf-172">string List</span></span> | <span data-ttu-id="931bf-173">Elenco di tag Evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="931bf-173">List of Incident tags.</span></span>
<span data-ttu-id="931bf-174">commenti</span><span class="sxs-lookup"><span data-stu-id="931bf-174">comments</span></span> | <span data-ttu-id="931bf-175">Elenco dei commenti degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="931bf-175">List of incident comments</span></span> | <span data-ttu-id="931bf-176">L'oggetto Incident Comment contiene: stringa di commento, stringa createdBy e data/ora createTime.</span><span class="sxs-lookup"><span data-stu-id="931bf-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="931bf-177">avvisi</span><span class="sxs-lookup"><span data-stu-id="931bf-177">alerts</span></span> | <span data-ttu-id="931bf-178">Elenco avvisi</span><span class="sxs-lookup"><span data-stu-id="931bf-178">Alert List</span></span> | <span data-ttu-id="931bf-179">Elenco di avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="931bf-179">List of related alerts.</span></span> <span data-ttu-id="931bf-180">Vedi gli esempi nella [documentazione dell'API list incidents.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="931bf-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="931bf-181">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="931bf-181">Related articles</span></span>

- [<span data-ttu-id="931bf-182">Microsoft 365 Panoramica delle API defender</span><span class="sxs-lookup"><span data-stu-id="931bf-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="931bf-183">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="931bf-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="931bf-184">API elenca eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="931bf-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="931bf-185">API per gli eventi imprevisti di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="931bf-185">Update incident API</span></span>](api-update-incidents.md)
