---
title: Microsoft 365 API degli incidenti di Defender e tipo di risorsa incidente
description: Informazioni sui metodi e le proprietà del tipo di risorsa Incidente in Microsoft 365 Defender
keywords: incidente, incidenti, api
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572586"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="1d1cb-104">Microsoft 365 API degli incidenti di Defender e tipo di risorsa incidente</span><span class="sxs-lookup"><span data-stu-id="1d1cb-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1d1cb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1d1cb-105">**Applies to:**</span></span>

- <span data-ttu-id="1d1cb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d1cb-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d1cb-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1d1cb-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1d1cb-109">Un [incidente](incidents-overview.md) è una raccolta di avvisi correlati che aiutano a descrivere un attacco.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="1d1cb-110">Gli eventi di entità diverse nell'organizzazione vengono aggregati automaticamente Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="1d1cb-111">È possibile utilizzare l'API degli incidenti per accedere programmaticamente agli incidenti e agli avvisi correlati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="1d1cb-112">Quote e allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="1d1cb-112">Quotas and resource allocation</span></span>

<span data-ttu-id="1d1cb-113">È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="1d1cb-114">Ogni metodo ha anche le proprie quote.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-114">Each method also has its own quotas.</span></span> <span data-ttu-id="1d1cb-115">Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="1d1cb-116">Un `429` codice di risposta HTTP indica che hai raggiunto una quota, in base al numero di richieste inviate o al tempo di esecuzione assegnato.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="1d1cb-117">Il corpo di risposta includerà il tempo fino a quando la quota raggiunta non verrà reimpostata.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="1d1cb-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1d1cb-118">Permissions</span></span>

<span data-ttu-id="1d1cb-119">L'API degli incidenti richiede diversi tipi di autorizzazioni per ciascuno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="1d1cb-120">Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo del rispettivo metodo.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="1d1cb-121">Metodi</span><span class="sxs-lookup"><span data-stu-id="1d1cb-121">Methods</span></span>

<span data-ttu-id="1d1cb-122">Metodo</span><span class="sxs-lookup"><span data-stu-id="1d1cb-122">Method</span></span> | <span data-ttu-id="1d1cb-123">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="1d1cb-123">Return Type</span></span> | <span data-ttu-id="1d1cb-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d1cb-124">Description</span></span>
-|-|-
[<span data-ttu-id="1d1cb-125">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="1d1cb-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="1d1cb-126">[Elenco](api-incident.md) incidenti</span><span class="sxs-lookup"><span data-stu-id="1d1cb-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="1d1cb-127">Ottieni un elenco di incidenti.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-127">Get a list of incidents.</span></span>
[<span data-ttu-id="1d1cb-128">Aggiornare incidente</span><span class="sxs-lookup"><span data-stu-id="1d1cb-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="1d1cb-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="1d1cb-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="1d1cb-130">Aggiornare un incidente specifico.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="1d1cb-131">Corpo della richiesta, risposta ed esempi</span><span class="sxs-lookup"><span data-stu-id="1d1cb-131">Request body, response, and examples</span></span>

<span data-ttu-id="1d1cb-132">Fare riferimento ai rispettivi articoli del metodo per ulteriori dettagli su come costruire una richiesta o analizzare una risposta e per esempi pratici.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="1d1cb-133">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="1d1cb-133">Common properties</span></span>

<span data-ttu-id="1d1cb-134">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1d1cb-134">Property</span></span> | <span data-ttu-id="1d1cb-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d1cb-135">Type</span></span> | <span data-ttu-id="1d1cb-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d1cb-136">Description</span></span>
-|-|-
<span data-ttu-id="1d1cb-137">id incidente</span><span class="sxs-lookup"><span data-stu-id="1d1cb-137">incidentId</span></span> | <span data-ttu-id="1d1cb-138">long</span><span class="sxs-lookup"><span data-stu-id="1d1cb-138">long</span></span> | <span data-ttu-id="1d1cb-139">ID univoco incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-139">Incident unique ID.</span></span>
<span data-ttu-id="1d1cb-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="1d1cb-140">redirectIncidentId</span></span> | <span data-ttu-id="1d1cb-141">nullable lungo</span><span class="sxs-lookup"><span data-stu-id="1d1cb-141">nullable long</span></span> | <span data-ttu-id="1d1cb-142">ID incidente a cui è stato unito l'incidente corrente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="1d1cb-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="1d1cb-143">incidentName</span></span> | <span data-ttu-id="1d1cb-144">stringa</span><span class="sxs-lookup"><span data-stu-id="1d1cb-144">string</span></span> | <span data-ttu-id="1d1cb-145">Nome dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-145">The name of the Incident.</span></span>
<span data-ttu-id="1d1cb-146">tempo creato</span><span class="sxs-lookup"><span data-stu-id="1d1cb-146">createdTime</span></span> | <span data-ttu-id="1d1cb-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1d1cb-147">DateTimeOffset</span></span> | <span data-ttu-id="1d1cb-148">Data e ora (in UTC) in cui è stato creato l'incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="1d1cb-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="1d1cb-149">lastUpdateTime</span></span> | <span data-ttu-id="1d1cb-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1d1cb-150">DateTimeOffset</span></span> | <span data-ttu-id="1d1cb-151">Data e ora (in UTC) dell'ultimo aggiornamento dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="1d1cb-152">assegnatoA</span><span class="sxs-lookup"><span data-stu-id="1d1cb-152">assignedTo</span></span> | <span data-ttu-id="1d1cb-153">stringa</span><span class="sxs-lookup"><span data-stu-id="1d1cb-153">string</span></span> | <span data-ttu-id="1d1cb-154">Proprietario dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-154">Owner of the Incident.</span></span>
<span data-ttu-id="1d1cb-155">severità</span><span class="sxs-lookup"><span data-stu-id="1d1cb-155">severity</span></span> | <span data-ttu-id="1d1cb-156">Enum</span><span class="sxs-lookup"><span data-stu-id="1d1cb-156">Enum</span></span> | <span data-ttu-id="1d1cb-157">Gravità dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-157">Severity of the Incident.</span></span> <span data-ttu-id="1d1cb-158">I valori possibili sono: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="1d1cb-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="1d1cb-159">stato</span><span class="sxs-lookup"><span data-stu-id="1d1cb-159">status</span></span> | <span data-ttu-id="1d1cb-160">Enum</span><span class="sxs-lookup"><span data-stu-id="1d1cb-160">Enum</span></span> | <span data-ttu-id="1d1cb-161">Specifica lo stato corrente dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="1d1cb-162">I valori possibili sono: ```Active``` ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="1d1cb-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="1d1cb-163">classificazione</span><span class="sxs-lookup"><span data-stu-id="1d1cb-163">classification</span></span> | <span data-ttu-id="1d1cb-164">Enum</span><span class="sxs-lookup"><span data-stu-id="1d1cb-164">Enum</span></span> | <span data-ttu-id="1d1cb-165">Specifica dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-165">Specification of the incident.</span></span> <span data-ttu-id="1d1cb-166">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="1d1cb-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="1d1cb-167">determinazione</span><span class="sxs-lookup"><span data-stu-id="1d1cb-167">determination</span></span> | <span data-ttu-id="1d1cb-168">Enum</span><span class="sxs-lookup"><span data-stu-id="1d1cb-168">Enum</span></span> | <span data-ttu-id="1d1cb-169">Specifica la determinazione dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="1d1cb-170">I valori possibili sono: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="1d1cb-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="1d1cb-171">Tag</span><span class="sxs-lookup"><span data-stu-id="1d1cb-171">tags</span></span> | <span data-ttu-id="1d1cb-172">elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="1d1cb-172">string List</span></span> | <span data-ttu-id="1d1cb-173">Elenco di tag Incidente.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-173">List of Incident tags.</span></span>
<span data-ttu-id="1d1cb-174">Commenti</span><span class="sxs-lookup"><span data-stu-id="1d1cb-174">comments</span></span> | <span data-ttu-id="1d1cb-175">Elenco dei commenti sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="1d1cb-175">List of incident comments</span></span> | <span data-ttu-id="1d1cb-176">L'oggetto Incident Comment contiene: stringa di commento, stringa createdBy e ora di data createTime.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="1d1cb-177">Avvisi</span><span class="sxs-lookup"><span data-stu-id="1d1cb-177">alerts</span></span> | <span data-ttu-id="1d1cb-178">Elenco avvisi</span><span class="sxs-lookup"><span data-stu-id="1d1cb-178">Alert List</span></span> | <span data-ttu-id="1d1cb-179">Elenco degli avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-179">List of related alerts.</span></span> <span data-ttu-id="1d1cb-180">Vedere esempi nella [documentazione dell'API degli](api-list-incidents.md) incidenti elenco.</span><span class="sxs-lookup"><span data-stu-id="1d1cb-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1d1cb-181">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="1d1cb-181">Related articles</span></span>

- [<span data-ttu-id="1d1cb-182">Microsoft 365 Panoramica delle API defender</span><span class="sxs-lookup"><span data-stu-id="1d1cb-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="1d1cb-183">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="1d1cb-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1d1cb-184">API elenco incidenti</span><span class="sxs-lookup"><span data-stu-id="1d1cb-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="1d1cb-185">Aggiornare l'API degli incidenti</span><span class="sxs-lookup"><span data-stu-id="1d1cb-185">Update incident API</span></span>](api-update-incidents.md)
