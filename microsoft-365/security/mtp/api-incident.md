---
title: Microsoft 365 Defender Incidents APIs e il tipo di risorsa Incident
description: Informazioni sui metodi e le proprietà del tipo di risorsa Incident in Microsoft 365 Defender
keywords: eventi incidentati, incidenti, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719335"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="937c5-104">API Microsoft 365 Defender Incidents e il tipo di risorsa Incident</span><span class="sxs-lookup"><span data-stu-id="937c5-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="937c5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="937c5-105">**Applies to:**</span></span>

- <span data-ttu-id="937c5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="937c5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="937c5-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="937c5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="937c5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="937c5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="937c5-109">Un [evento imprevisto](incidents-overview.md) è un insieme di avvisi correlati che consentono di descrivere un attacco.</span><span class="sxs-lookup"><span data-stu-id="937c5-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="937c5-110">Gli eventi provenienti da entità diverse nell'organizzazione vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="937c5-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="937c5-111">È possibile utilizzare l'API Incidents per programatically accedere agli eventi imprevisti dell'organizzazione e ai relativi avvisi.</span><span class="sxs-lookup"><span data-stu-id="937c5-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="937c5-112">Quote e allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="937c5-112">Quotas and resource allocation</span></span>

<span data-ttu-id="937c5-113">È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="937c5-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="937c5-114">Ogni metodo dispone anche di quote proprie.</span><span class="sxs-lookup"><span data-stu-id="937c5-114">Each method also has its own quotas.</span></span> <span data-ttu-id="937c5-115">Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="937c5-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="937c5-116">Un `429` codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo di esecuzione assegnato.</span><span class="sxs-lookup"><span data-stu-id="937c5-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="937c5-117">Il corpo di risposta includerà l'ora in cui la quota raggiunta verrà reimpostata.</span><span class="sxs-lookup"><span data-stu-id="937c5-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="937c5-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="937c5-118">Permissions</span></span>

<span data-ttu-id="937c5-119">L'API Incidents richiede diversi tipi di autorizzazioni per ognuno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="937c5-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="937c5-120">Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo relativo al metodo.</span><span class="sxs-lookup"><span data-stu-id="937c5-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="937c5-121">Metodi</span><span class="sxs-lookup"><span data-stu-id="937c5-121">Methods</span></span>

<span data-ttu-id="937c5-122">Metodo</span><span class="sxs-lookup"><span data-stu-id="937c5-122">Method</span></span> | <span data-ttu-id="937c5-123">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="937c5-123">Return Type</span></span> | <span data-ttu-id="937c5-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="937c5-124">Description</span></span>
-|-|-
[<span data-ttu-id="937c5-125">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="937c5-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="937c5-126">Elenco [eventi](api-incident.md) non consentiti</span><span class="sxs-lookup"><span data-stu-id="937c5-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="937c5-127">Ottenere un elenco di eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="937c5-127">Get a list of incidents.</span></span>
[<span data-ttu-id="937c5-128">Aggiornare incidente</span><span class="sxs-lookup"><span data-stu-id="937c5-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="937c5-129">Operazioni non consentite</span><span class="sxs-lookup"><span data-stu-id="937c5-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="937c5-130">Aggiornare un evento specifico.</span><span class="sxs-lookup"><span data-stu-id="937c5-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="937c5-131">Corpo della richiesta, risposta ed esempi</span><span class="sxs-lookup"><span data-stu-id="937c5-131">Request body, response, and examples</span></span>

<span data-ttu-id="937c5-132">Per ulteriori informazioni su come creare una richiesta o analizzare una risposta e per esempi pratici, vedere gli articoli relativi ai rispettivi metodi.</span><span class="sxs-lookup"><span data-stu-id="937c5-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="937c5-133">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="937c5-133">Common properties</span></span>

<span data-ttu-id="937c5-134">Proprietà</span><span class="sxs-lookup"><span data-stu-id="937c5-134">Property</span></span> | <span data-ttu-id="937c5-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="937c5-135">Type</span></span> | <span data-ttu-id="937c5-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="937c5-136">Description</span></span>
-|-|-
<span data-ttu-id="937c5-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="937c5-137">incidentId</span></span> | <span data-ttu-id="937c5-138">long</span><span class="sxs-lookup"><span data-stu-id="937c5-138">long</span></span> | <span data-ttu-id="937c5-139">ID univoco per gli incidenti.</span><span class="sxs-lookup"><span data-stu-id="937c5-139">Incident unique ID.</span></span>
<span data-ttu-id="937c5-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="937c5-140">redirectIncidentId</span></span> | <span data-ttu-id="937c5-141">Long Nullable</span><span class="sxs-lookup"><span data-stu-id="937c5-141">nullable long</span></span> | <span data-ttu-id="937c5-142">ID di incidente in cui è stato unito l'evento Incident corrente.</span><span class="sxs-lookup"><span data-stu-id="937c5-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="937c5-143">evento incidentname</span><span class="sxs-lookup"><span data-stu-id="937c5-143">incidentName</span></span> | <span data-ttu-id="937c5-144">stringa</span><span class="sxs-lookup"><span data-stu-id="937c5-144">string</span></span> | <span data-ttu-id="937c5-145">Nome dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="937c5-145">The name of the Incident.</span></span>
<span data-ttu-id="937c5-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="937c5-146">createdTime</span></span> | <span data-ttu-id="937c5-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="937c5-147">DateTimeOffset</span></span> | <span data-ttu-id="937c5-148">La data e l'ora (in formato UTC) dell'evento Incident è stato creato.</span><span class="sxs-lookup"><span data-stu-id="937c5-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="937c5-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="937c5-149">lastUpdateTime</span></span> | <span data-ttu-id="937c5-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="937c5-150">DateTimeOffset</span></span> | <span data-ttu-id="937c5-151">La data e l'ora (in formato UTC) dell'ultimo aggiornamento dell'evento.</span><span class="sxs-lookup"><span data-stu-id="937c5-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="937c5-152">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="937c5-152">assignedTo</span></span> | <span data-ttu-id="937c5-153">stringa</span><span class="sxs-lookup"><span data-stu-id="937c5-153">string</span></span> | <span data-ttu-id="937c5-154">Proprietario dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="937c5-154">Owner of the Incident.</span></span>
<span data-ttu-id="937c5-155">gravità</span><span class="sxs-lookup"><span data-stu-id="937c5-155">severity</span></span> | <span data-ttu-id="937c5-156">Enum</span><span class="sxs-lookup"><span data-stu-id="937c5-156">Enum</span></span> | <span data-ttu-id="937c5-157">Gravità dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="937c5-157">Severity of the Incident.</span></span> <span data-ttu-id="937c5-158">I valori possibili sono:,,, ```UnSpecified``` ```Informational``` ```Low``` ```Medium``` e ```High``` .</span><span class="sxs-lookup"><span data-stu-id="937c5-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="937c5-159">stato</span><span class="sxs-lookup"><span data-stu-id="937c5-159">status</span></span> | <span data-ttu-id="937c5-160">Enum</span><span class="sxs-lookup"><span data-stu-id="937c5-160">Enum</span></span> | <span data-ttu-id="937c5-161">Specifica lo stato corrente dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="937c5-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="937c5-162">I valori possibili sono: ```Active``` , ```Resolved``` e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="937c5-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="937c5-163">classificazione</span><span class="sxs-lookup"><span data-stu-id="937c5-163">classification</span></span> | <span data-ttu-id="937c5-164">Enum</span><span class="sxs-lookup"><span data-stu-id="937c5-164">Enum</span></span> | <span data-ttu-id="937c5-165">Specifica dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="937c5-165">Specification of the incident.</span></span> <span data-ttu-id="937c5-166">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="937c5-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="937c5-167">determinazione</span><span class="sxs-lookup"><span data-stu-id="937c5-167">determination</span></span> | <span data-ttu-id="937c5-168">Enum</span><span class="sxs-lookup"><span data-stu-id="937c5-168">Enum</span></span> | <span data-ttu-id="937c5-169">Specifica la determinazione dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="937c5-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="937c5-170">I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="937c5-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="937c5-171">Tag</span><span class="sxs-lookup"><span data-stu-id="937c5-171">tags</span></span> | <span data-ttu-id="937c5-172">Elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="937c5-172">string List</span></span> | <span data-ttu-id="937c5-173">Elenco dei tag Incident.</span><span class="sxs-lookup"><span data-stu-id="937c5-173">List of Incident tags.</span></span>
<span data-ttu-id="937c5-174">avvisi</span><span class="sxs-lookup"><span data-stu-id="937c5-174">alerts</span></span> | <span data-ttu-id="937c5-175">Elenco avvisi</span><span class="sxs-lookup"><span data-stu-id="937c5-175">Alert List</span></span> | <span data-ttu-id="937c5-176">Elenco di avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="937c5-176">List of related alerts.</span></span> <span data-ttu-id="937c5-177">Vedere esempi di documentazione sull'API degli [incidenti di elenco](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="937c5-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="937c5-178">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="937c5-178">Related articles</span></span>

- [<span data-ttu-id="937c5-179">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="937c5-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="937c5-180">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="937c5-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="937c5-181">API degli incidenti di elenco</span><span class="sxs-lookup"><span data-stu-id="937c5-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="937c5-182">Aggiornare l'API Incident</span><span class="sxs-lookup"><span data-stu-id="937c5-182">Update incident API</span></span>](api-update-incidents.md)
