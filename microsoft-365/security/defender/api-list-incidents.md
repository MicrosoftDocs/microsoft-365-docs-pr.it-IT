---
title: API elenca eventi imprevisti in Microsoft 365 Defender
description: Scopri come elencare le API per gli eventi imprevisti in Microsoft 365 Defender
keywords: list, incident, incidents, api
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
ms.openlocfilehash: 833bc1d8284829323cc2f0c391e42f4e563a6948
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730883"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="6f6f1-104">API elenca eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f6f1-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f6f1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6f6f1-105">**Applies to:**</span></span>

- [<span data-ttu-id="6f6f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f6f1-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="6f6f1-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6f6f1-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="6f6f1-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="6f6f1-109">API description</span></span>

<span data-ttu-id="6f6f1-110">L'API elenca eventi imprevisti consente di ordinare gli eventi imprevisti per creare una risposta informata alla sicurezza informatica.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="6f6f1-111">Espone una raccolta di eventi imprevisti contrassegnati nella rete, entro l'intervallo di tempo specificato nei criteri di conservazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="6f6f1-112">Gli eventi imprevisti più recenti vengono visualizzati all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="6f6f1-113">Ogni evento imprevisto contiene una matrice di avvisi correlati e le relative entità.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="6f6f1-114">L'API supporta gli operatori **OData** seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f6f1-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="6f6f1-115">`$filter`nelle `lastUpdateTime` proprietà , `createdTime` , `status` e `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="6f6f1-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="6f6f1-116">`$top`, con un valore massimo **di 100**</span><span class="sxs-lookup"><span data-stu-id="6f6f1-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="6f6f1-117">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="6f6f1-117">Limitations</span></span>

1. <span data-ttu-id="6f6f1-118">La dimensione massima della pagina **è 100 eventi imprevisti.**</span><span class="sxs-lookup"><span data-stu-id="6f6f1-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="6f6f1-119">La velocità massima delle richieste **è di 50 chiamate al minuto** e **1500 chiamate all'ora.**</span><span class="sxs-lookup"><span data-stu-id="6f6f1-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="6f6f1-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6f6f1-120">Permissions</span></span>

<span data-ttu-id="6f6f1-121">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6f6f1-122">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedere [Access Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="6f6f1-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="6f6f1-123">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-123">Permission type</span></span> | <span data-ttu-id="6f6f1-124">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-124">Permission</span></span> | <span data-ttu-id="6f6f1-125">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="6f6f1-126">Applicazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-126">Application</span></span> | <span data-ttu-id="6f6f1-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="6f6f1-127">Incident.Read.All</span></span> | <span data-ttu-id="6f6f1-128">Leggere tutti gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="6f6f1-128">Read all incidents</span></span>
<span data-ttu-id="6f6f1-129">Applicazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-129">Application</span></span> | <span data-ttu-id="6f6f1-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6f6f1-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="6f6f1-131">Lettura e scrittura di tutti gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="6f6f1-131">Read and write all incidents</span></span>
<span data-ttu-id="6f6f1-132">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="6f6f1-132">Delegated (work or school account)</span></span> | <span data-ttu-id="6f6f1-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="6f6f1-133">Incident.Read</span></span> | <span data-ttu-id="6f6f1-134">Eventi imprevisti di lettura</span><span class="sxs-lookup"><span data-stu-id="6f6f1-134">Read incidents</span></span>
<span data-ttu-id="6f6f1-135">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="6f6f1-135">Delegated (work or school account)</span></span> | <span data-ttu-id="6f6f1-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6f6f1-136">Incident.ReadWrite</span></span> | <span data-ttu-id="6f6f1-137">Eventi imprevisti di lettura e scrittura</span><span class="sxs-lookup"><span data-stu-id="6f6f1-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="6f6f1-138">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="6f6f1-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="6f6f1-139">L'utente deve disporre dell'autorizzazione di visualizzazione per gli eventi imprevisti nel portale.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="6f6f1-140">La risposta includerà solo gli eventi imprevisti a cui l'utente è esposto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="6f6f1-141">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="6f6f1-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="6f6f1-142">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="6f6f1-142">Request headers</span></span>

<span data-ttu-id="6f6f1-143">Name</span><span class="sxs-lookup"><span data-stu-id="6f6f1-143">Name</span></span> | <span data-ttu-id="6f6f1-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-144">Type</span></span> | <span data-ttu-id="6f6f1-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-145">Description</span></span>
-|-|-
<span data-ttu-id="6f6f1-146">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-146">Authorization</span></span> | <span data-ttu-id="6f6f1-147">Stringa</span><span class="sxs-lookup"><span data-stu-id="6f6f1-147">String</span></span> | <span data-ttu-id="6f6f1-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-148">Bearer {token}.</span></span> <span data-ttu-id="6f6f1-149">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="6f6f1-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="6f6f1-150">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="6f6f1-150">Request body</span></span>

<span data-ttu-id="6f6f1-151">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="6f6f1-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="6f6f1-152">Response</span></span>

<span data-ttu-id="6f6f1-153">Se ha esito positivo, questo metodo restituisce `200 OK` e un elenco di eventi [imprevisti](api-incident.md) nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="6f6f1-154">Mapping dello schema</span><span class="sxs-lookup"><span data-stu-id="6f6f1-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="6f6f1-155">Metadati degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="6f6f1-155">Incident metadata</span></span>

<span data-ttu-id="6f6f1-156">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-156">Field name</span></span> | <span data-ttu-id="6f6f1-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-157">Description</span></span> | <span data-ttu-id="6f6f1-158">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="6f6f1-158">Example value</span></span>
-|-|-
<span data-ttu-id="6f6f1-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-159">incidentId</span></span> | <span data-ttu-id="6f6f1-160">Identificatore univoco per rappresentare l'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="6f6f1-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="6f6f1-161">924565</span><span class="sxs-lookup"><span data-stu-id="6f6f1-161">924565</span></span>
<span data-ttu-id="6f6f1-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-162">redirectIncidentId</span></span> | <span data-ttu-id="6f6f1-163">Popolato solo nel caso in cui un evento imprevisto venga raggruppato insieme a un altro evento imprevisto, come parte della logica di elaborazione degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="6f6f1-164">924569</span><span class="sxs-lookup"><span data-stu-id="6f6f1-164">924569</span></span>
<span data-ttu-id="6f6f1-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-165">incidentName</span></span> | <span data-ttu-id="6f6f1-166">Valore stringa disponibile per ogni evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-166">String value available for every incident.</span></span> | <span data-ttu-id="6f6f1-167">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="6f6f1-167">Ransomware activity</span></span>
<span data-ttu-id="6f6f1-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="6f6f1-168">createdTime</span></span> | <span data-ttu-id="6f6f1-169">Ora di creazione dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-169">Time when incident was first created.</span></span> | <span data-ttu-id="6f6f1-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="6f6f1-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="6f6f1-171">lastUpdateTime</span></span> | <span data-ttu-id="6f6f1-172">Ora dell'ultimo aggiornamento dell'evento imprevisto nel back-end.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="6f6f1-173">Questo campo può essere utilizzato quando si imposta il parametro request per l'intervallo di tempo in cui vengono recuperati gli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="6f6f1-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="6f6f1-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-175">assignedTo</span></span> | <span data-ttu-id="6f6f1-176">Proprietario dell'evento imprevisto oppure *null se* non è assegnato alcun proprietario.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="6f6f1-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6f6f1-177">secop2@contoso.com</span></span>
<span data-ttu-id="6f6f1-178">classificazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-178">classification</span></span> | <span data-ttu-id="6f6f1-179">Specifica per l'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-179">The specification for the incident.</span></span> <span data-ttu-id="6f6f1-180">I valori delle proprietà *sono: Unknown,* *FalsePositive,* *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="6f6f1-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="6f6f1-181">Unknown</span></span>
<span data-ttu-id="6f6f1-182">determinazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-182">determination</span></span> | <span data-ttu-id="6f6f1-183">Specifica la determinazione dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="6f6f1-184">I valori delle proprietà sono: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="6f6f1-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="6f6f1-185">NotAvailable</span></span>
<span data-ttu-id="6f6f1-186">status</span><span class="sxs-lookup"><span data-stu-id="6f6f1-186">status</span></span> | <span data-ttu-id="6f6f1-187">Categorizzare gli eventi imprevisti *(come Active* o *Resolved).*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="6f6f1-188">Può essere utile per organizzare e gestire la risposta agli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="6f6f1-189">Attivazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-189">Active</span></span>
<span data-ttu-id="6f6f1-190">gravità</span><span class="sxs-lookup"><span data-stu-id="6f6f1-190">severity</span></span> | <span data-ttu-id="6f6f1-191">Indica il possibile impatto sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="6f6f1-192">Maggiore è la gravità, maggiore sarà l'impatto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="6f6f1-193">In genere, gli elementi di gravità superiore richiedono l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="6f6f1-194">Uno dei valori seguenti: *Informational,* \*Low,\*\*Medium e *High.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="6f6f1-195">Medio</span><span class="sxs-lookup"><span data-stu-id="6f6f1-195">Medium</span></span>
<span data-ttu-id="6f6f1-196">tag</span><span class="sxs-lookup"><span data-stu-id="6f6f1-196">tags</span></span> | <span data-ttu-id="6f6f1-197">Matrice di tag personalizzati associati a un evento imprevisto, ad esempio per contrassegnare un gruppo di eventi imprevisti con una caratteristica comune.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="6f6f1-198">commenti</span><span class="sxs-lookup"><span data-stu-id="6f6f1-198">comments</span></span> | <span data-ttu-id="6f6f1-199">Matrice di commenti creati da secop durante la gestione dell'evento imprevisto, ad esempio informazioni aggiuntive sulla selezione della classificazione.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="6f6f1-200">avvisi</span><span class="sxs-lookup"><span data-stu-id="6f6f1-200">alerts</span></span> | <span data-ttu-id="6f6f1-201">Matrice contenente tutti gli avvisi correlati all'evento imprevisto, oltre ad altre informazioni, ad esempio la gravità, le entità coinvolte nell'avviso e l'origine degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="6f6f1-202">\[\] (vedi i dettagli sui campi degli avvisi di seguito)</span><span class="sxs-lookup"><span data-stu-id="6f6f1-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="6f6f1-203">Metadati degli avvisi</span><span class="sxs-lookup"><span data-stu-id="6f6f1-203">Alerts metadata</span></span>

<span data-ttu-id="6f6f1-204">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-204">Field name</span></span> | <span data-ttu-id="6f6f1-205">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-205">Description</span></span> | <span data-ttu-id="6f6f1-206">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="6f6f1-206">Example value</span></span>
-|-|-
<span data-ttu-id="6f6f1-207">alertId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-207">alertId</span></span> | <span data-ttu-id="6f6f1-208">Identificatore univoco per rappresentare l'avviso</span><span class="sxs-lookup"><span data-stu-id="6f6f1-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="6f6f1-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="6f6f1-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="6f6f1-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-210">incidentId</span></span> | <span data-ttu-id="6f6f1-211">Identificatore univoco per rappresentare l'evento imprevisto a cui è associato questo avviso</span><span class="sxs-lookup"><span data-stu-id="6f6f1-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="6f6f1-212">924565</span><span class="sxs-lookup"><span data-stu-id="6f6f1-212">924565</span></span>
<span data-ttu-id="6f6f1-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="6f6f1-213">serviceSource</span></span> | <span data-ttu-id="6f6f1-214">Servizio da cui proviene l'avviso, ad esempio Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity o Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="6f6f1-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="6f6f1-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="6f6f1-216">creationTime</span><span class="sxs-lookup"><span data-stu-id="6f6f1-216">creationTime</span></span> | <span data-ttu-id="6f6f1-217">Ora di creazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-217">Time when alert was first created.</span></span> | <span data-ttu-id="6f6f1-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="6f6f1-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="6f6f1-219">lastUpdatedTime</span></span> | <span data-ttu-id="6f6f1-220">Ora dell'ultimo aggiornamento dell'avviso nel back-end.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="6f6f1-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="6f6f1-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="6f6f1-222">resolvedTime</span></span> | <span data-ttu-id="6f6f1-223">Ora in cui l'avviso è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-223">Time when alert was resolved.</span></span> | <span data-ttu-id="6f6f1-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="6f6f1-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="6f6f1-225">firstActivity</span></span> | <span data-ttu-id="6f6f1-226">Ora in cui l'avviso ha segnalato per la prima volta che l'attività è stata aggiornata nel back-end.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="6f6f1-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="6f6f1-228">title</span><span class="sxs-lookup"><span data-stu-id="6f6f1-228">title</span></span> | <span data-ttu-id="6f6f1-229">Breve valore stringa di identificazione disponibile per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="6f6f1-230">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="6f6f1-230">Ransomware activity</span></span>
<span data-ttu-id="6f6f1-231">descrizione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-231">description</span></span> | <span data-ttu-id="6f6f1-232">Valore stringa che descrive ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-232">String value describing each alert.</span></span> | <span data-ttu-id="6f6f1-233">L'utente Test User2 (testUser2@contoso.com) ha modificato 99 file con più estensioni che terminano con l'estensione non comune *herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="6f6f1-234">Si tratta di un numero insolito di manipolazioni di file ed è indicativo di un potenziale attacco ransomware.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="6f6f1-235">category</span><span class="sxs-lookup"><span data-stu-id="6f6f1-235">category</span></span> | <span data-ttu-id="6f6f1-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="6f6f1-237">Allineato al framework [MITRE ATT&CK™](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="6f6f1-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="6f6f1-238">Impatto</span><span class="sxs-lookup"><span data-stu-id="6f6f1-238">Impact</span></span>
<span data-ttu-id="6f6f1-239">status</span><span class="sxs-lookup"><span data-stu-id="6f6f1-239">status</span></span> | <span data-ttu-id="6f6f1-240">Categorizzare gli avvisi *(come Nuovo,* *Attivo* o *Risolto).*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="6f6f1-241">Può essere utile per organizzare e gestire la risposta agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="6f6f1-242">New</span><span class="sxs-lookup"><span data-stu-id="6f6f1-242">New</span></span>
<span data-ttu-id="6f6f1-243">gravità</span><span class="sxs-lookup"><span data-stu-id="6f6f1-243">severity</span></span> | <span data-ttu-id="6f6f1-244">Indica il possibile impatto sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="6f6f1-245">Maggiore è la gravità, maggiore sarà l'impatto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="6f6f1-246">In genere, gli elementi di gravità superiore richiedono l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="6f6f1-247">Uno dei valori seguenti: *Informational,* \*Low,\*\*Medium e *High.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="6f6f1-248">Medio</span><span class="sxs-lookup"><span data-stu-id="6f6f1-248">Medium</span></span>
<span data-ttu-id="6f6f1-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-249">investigationId</span></span> | <span data-ttu-id="6f6f1-250">ID dell'indagine automatizzata attivato da questo avviso.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="6f6f1-251">1234</span><span class="sxs-lookup"><span data-stu-id="6f6f1-251">1234</span></span>
<span data-ttu-id="6f6f1-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="6f6f1-252">investigationState</span></span> | <span data-ttu-id="6f6f1-253">Informazioni sullo stato corrente dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-253">Information on the investigation's current status.</span></span> <span data-ttu-id="6f6f1-254">Uno dei valori seguenti: *Unknown,* *Terminated,* *SuccessfullyRemediated,* *Benign,* *Failed,* *PartiallyRemediated,* *Running,* *PendingApproval,* *PendingResource,* *PartiallyInvestigated,* *TerminatedByUser,* *TerminatedBySystem,* *Queued,* *InnerFailure,* *PreexistingAlert,* *UnsupportedOs,* *UnsupportedAlertType,* *SuppressedAlert.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="6f6f1-255">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="6f6f1-255">UnsupportedAlertType</span></span>
<span data-ttu-id="6f6f1-256">classificazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-256">classification</span></span> | <span data-ttu-id="6f6f1-257">Specifica per l'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-257">The specification for the incident.</span></span> <span data-ttu-id="6f6f1-258">I valori delle proprietà *sono: Unknown,* *FalsePositive,* *TruePositive* o *null*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="6f6f1-259">Unknown</span><span class="sxs-lookup"><span data-stu-id="6f6f1-259">Unknown</span></span>
<span data-ttu-id="6f6f1-260">determinazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-260">determination</span></span> | <span data-ttu-id="6f6f1-261">Specifica la determinazione dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="6f6f1-262">I valori delle proprietà sono: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* o  *null*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="6f6f1-263">Apt</span><span class="sxs-lookup"><span data-stu-id="6f6f1-263">Apt</span></span>
<span data-ttu-id="6f6f1-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-264">assignedTo</span></span> | <span data-ttu-id="6f6f1-265">Proprietario dell'evento imprevisto oppure *null se* non è assegnato alcun proprietario.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="6f6f1-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6f6f1-266">secop2@contoso.com</span></span>
<span data-ttu-id="6f6f1-267">actorName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-267">actorName</span></span> | <span data-ttu-id="6f6f1-268">Gruppo di attività, se presente, associato a questo avviso.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="6f6f1-269">BORON</span><span class="sxs-lookup"><span data-stu-id="6f6f1-269">BORON</span></span>
<span data-ttu-id="6f6f1-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-270">threatFamilyName</span></span> | <span data-ttu-id="6f6f1-271">Famiglia di minacce associata a questo avviso.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="6f6f1-272">null</span><span class="sxs-lookup"><span data-stu-id="6f6f1-272">null</span></span>
<span data-ttu-id="6f6f1-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="6f6f1-273">mitreTechniques</span></span> | <span data-ttu-id="6f6f1-274">Le tecniche di attacco, allineate al framework di&CK ™ [MITRE.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="6f6f1-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="6f6f1-275">dispositivi</span><span class="sxs-lookup"><span data-stu-id="6f6f1-275">devices</span></span> | <span data-ttu-id="6f6f1-276">Tutti i dispositivi in cui sono stati inviati avvisi relativi all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="6f6f1-277">\[\] (vedi i dettagli sui campi dell'entità di seguito)</span><span class="sxs-lookup"><span data-stu-id="6f6f1-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="6f6f1-278">Formato dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-278">Device format</span></span>

<span data-ttu-id="6f6f1-279">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-279">Field name</span></span> | <span data-ttu-id="6f6f1-280">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-280">Description</span></span> | <span data-ttu-id="6f6f1-281">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="6f6f1-281">Example value</span></span>
-|-|-
<span data-ttu-id="6f6f1-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-282">DeviceId</span></span> | <span data-ttu-id="6f6f1-283">ID dispositivo designato in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="6f6f1-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="6f6f1-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="6f6f1-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-285">aadDeviceId</span></span> |  <span data-ttu-id="6f6f1-286">ID dispositivo designato in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="6f6f1-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="6f6f1-287">Disponibile solo per i dispositivi aggiunti a un dominio.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="6f6f1-288">null</span><span class="sxs-lookup"><span data-stu-id="6f6f1-288">null</span></span>
<span data-ttu-id="6f6f1-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-289">deviceDnsName</span></span> | <span data-ttu-id="6f6f1-290">Nome di dominio completo per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="6f6f1-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6f6f1-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="6f6f1-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="6f6f1-292">osPlatform</span></span> | <span data-ttu-id="6f6f1-293">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-293">The OS platform the device is running.</span></span>| <span data-ttu-id="6f6f1-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="6f6f1-294">WindowsServer2016</span></span>
<span data-ttu-id="6f6f1-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="6f6f1-295">osBuild</span></span> | <span data-ttu-id="6f6f1-296">Versione della build per il sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="6f6f1-297">14393</span><span class="sxs-lookup"><span data-stu-id="6f6f1-297">14393</span></span>
<span data-ttu-id="6f6f1-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-298">rbacGroupName</span></span> | <span data-ttu-id="6f6f1-299">Gruppo [di controllo di accesso](/azure/role-based-access-control/overview) basato sui ruoli associato al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="6f6f1-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="6f6f1-300">WDATP-Ring0</span></span>
<span data-ttu-id="6f6f1-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="6f6f1-301">firstSeen</span></span> | <span data-ttu-id="6f6f1-302">Ora in cui il dispositivo è stato visualizzato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-302">Time when device was first seen.</span></span> | <span data-ttu-id="6f6f1-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="6f6f1-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="6f6f1-304">healthStatus</span></span> | <span data-ttu-id="6f6f1-305">Stato di integrità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-305">The health state of the device.</span></span> | <span data-ttu-id="6f6f1-306">Attivazione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-306">Active</span></span>
<span data-ttu-id="6f6f1-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="6f6f1-307">riskScore</span></span> | <span data-ttu-id="6f6f1-308">Punteggio di rischio per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-308">The risk score for the  device.</span></span> | <span data-ttu-id="6f6f1-309">Fortemente</span><span class="sxs-lookup"><span data-stu-id="6f6f1-309">High</span></span>
<span data-ttu-id="6f6f1-310">entità</span><span class="sxs-lookup"><span data-stu-id="6f6f1-310">entities</span></span> | <span data-ttu-id="6f6f1-311">Tutte le entità identificate come parte o correlate a un determinato avviso.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="6f6f1-312">\[\] (vedi i dettagli sui campi dell'entità di seguito)</span><span class="sxs-lookup"><span data-stu-id="6f6f1-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="6f6f1-313">Formato entità</span><span class="sxs-lookup"><span data-stu-id="6f6f1-313">Entity Format</span></span>

<span data-ttu-id="6f6f1-314">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-314">Field name</span></span> | <span data-ttu-id="6f6f1-315">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f6f1-315">Description</span></span> | <span data-ttu-id="6f6f1-316">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="6f6f1-316">Example value</span></span>
-|-|-
<span data-ttu-id="6f6f1-317">entityType</span><span class="sxs-lookup"><span data-stu-id="6f6f1-317">entityType</span></span> | <span data-ttu-id="6f6f1-318">Entità identificate come parte o correlate a un determinato avviso.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="6f6f1-319">I valori delle proprietà sono: *User,* *Ip,* *Url,* *File,* *Process,* *MailBox,* *MailMessage,* *MailCluster,* *Registry*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="6f6f1-320">Utente</span><span class="sxs-lookup"><span data-stu-id="6f6f1-320">User</span></span>
<span data-ttu-id="6f6f1-321">sha1</span><span class="sxs-lookup"><span data-stu-id="6f6f1-321">sha1</span></span> | <span data-ttu-id="6f6f1-322">Disponibile se entityType è *File*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="6f6f1-323">Hash del file per gli avvisi associati a un file o a un processo.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="6f6f1-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="6f6f1-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="6f6f1-325">sha256</span><span class="sxs-lookup"><span data-stu-id="6f6f1-325">sha256</span></span> | <span data-ttu-id="6f6f1-326">Disponibile se entityType è *File*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="6f6f1-327">Hash del file per gli avvisi associati a un file o a un processo.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="6f6f1-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="6f6f1-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="6f6f1-329">fileName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-329">fileName</span></span> | <span data-ttu-id="6f6f1-330">Disponibile se entityType è *File*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="6f6f1-331">Nome file per gli avvisi associati a un file o a un processo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="6f6f1-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="6f6f1-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="6f6f1-333">filePath</span><span class="sxs-lookup"><span data-stu-id="6f6f1-333">filePath</span></span> | <span data-ttu-id="6f6f1-334">Disponibile se entityType è *File*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="6f6f1-335">Percorso file per gli avvisi associati a un file o a un processo</span><span class="sxs-lookup"><span data-stu-id="6f6f1-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="6f6f1-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="6f6f1-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="6f6f1-337">processId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-337">processId</span></span> | <span data-ttu-id="6f6f1-338">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6f6f1-339">24348</span><span class="sxs-lookup"><span data-stu-id="6f6f1-339">24348</span></span>
<span data-ttu-id="6f6f1-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="6f6f1-340">processCommandLine</span></span> | <span data-ttu-id="6f6f1-341">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6f6f1-342">"Il file è pronto per il download \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="6f6f1-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="6f6f1-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="6f6f1-343">processCreationTime</span></span> | <span data-ttu-id="6f6f1-344">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6f6f1-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="6f6f1-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-346">parentProcessId</span></span> | <span data-ttu-id="6f6f1-347">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6f6f1-348">16840</span><span class="sxs-lookup"><span data-stu-id="6f6f1-348">16840</span></span>
<span data-ttu-id="6f6f1-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="6f6f1-349">parentProcessCreationTime</span></span> | <span data-ttu-id="6f6f1-350">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6f6f1-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="6f6f1-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="6f6f1-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="6f6f1-352">ipAddress</span></span> | <span data-ttu-id="6f6f1-353">Disponibile se entityType è *Ip*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="6f6f1-354">Indirizzo IP per gli avvisi associati a eventi di rete, ad esempio *Comunicazione con una destinazione di rete dannosa.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="6f6f1-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="6f6f1-355">62.216.203.204</span></span>
<span data-ttu-id="6f6f1-356">url</span><span class="sxs-lookup"><span data-stu-id="6f6f1-356">url</span></span> | <span data-ttu-id="6f6f1-357">Disponibile se entityType è *Url*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="6f6f1-358">URL per gli avvisi associati a eventi di rete, ad esempio Comunicazione *con una destinazione di rete dannosa.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="6f6f1-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="6f6f1-359">down.esales360.cn</span></span>
<span data-ttu-id="6f6f1-360">accountName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-360">accountName</span></span> | <span data-ttu-id="6f6f1-361">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="6f6f1-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="6f6f1-362">testUser2</span></span>
<span data-ttu-id="6f6f1-363">domainName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-363">domainName</span></span> | <span data-ttu-id="6f6f1-364">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="6f6f1-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="6f6f1-365">europe.corp.contoso</span></span>
<span data-ttu-id="6f6f1-366">userSid</span><span class="sxs-lookup"><span data-stu-id="6f6f1-366">userSid</span></span> | <span data-ttu-id="6f6f1-367">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="6f6f1-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="6f6f1-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="6f6f1-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-369">aadUserId</span></span> | <span data-ttu-id="6f6f1-370">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="6f6f1-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="6f6f1-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="6f6f1-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-372">userPrincipalName</span></span> | <span data-ttu-id="6f6f1-373">Disponibile se entityType è *User* / *MailBox* / *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6f6f1-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6f6f1-374">testUser2@contoso.com</span></span>
<span data-ttu-id="6f6f1-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-375">mailboxDisplayName</span></span> | <span data-ttu-id="6f6f1-376">Disponibile se entityType è *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="6f6f1-377">test User2</span><span class="sxs-lookup"><span data-stu-id="6f6f1-377">test User2</span></span>
<span data-ttu-id="6f6f1-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="6f6f1-378">mailboxAddress</span></span> | <span data-ttu-id="6f6f1-379">Disponibile se entityType è *User* / *MailBox* / *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6f6f1-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6f6f1-380">testUser2@contoso.com</span></span>
<span data-ttu-id="6f6f1-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="6f6f1-381">clusterBy</span></span> | <span data-ttu-id="6f6f1-382">Disponibile se entityType è  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="6f6f1-383">Subject; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="6f6f1-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="6f6f1-384">mittente</span><span class="sxs-lookup"><span data-stu-id="6f6f1-384">sender</span></span> | <span data-ttu-id="6f6f1-385">Disponibile se entityType è *User* / *MailBox* / *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6f6f1-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="6f6f1-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="6f6f1-387">destinatario</span><span class="sxs-lookup"><span data-stu-id="6f6f1-387">recipient</span></span> | <span data-ttu-id="6f6f1-388">Disponibile se entityType è *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6f6f1-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6f6f1-389">testUser2@contoso.com</span></span>
<span data-ttu-id="6f6f1-390">subject</span><span class="sxs-lookup"><span data-stu-id="6f6f1-390">subject</span></span> | <span data-ttu-id="6f6f1-391">Disponibile se entityType è *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6f6f1-392">\[Attenzione \] ESTERNA</span><span class="sxs-lookup"><span data-stu-id="6f6f1-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="6f6f1-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="6f6f1-393">deliveryAction</span></span> | <span data-ttu-id="6f6f1-394">Disponibile se entityType è *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6f6f1-395">Recapitati</span><span class="sxs-lookup"><span data-stu-id="6f6f1-395">Delivered</span></span>
<span data-ttu-id="6f6f1-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-396">securityGroupId</span></span> | <span data-ttu-id="6f6f1-397">Disponibile se entityType è *SecurityGroup.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="6f6f1-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="6f6f1-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="6f6f1-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="6f6f1-399">securityGroupName</span></span> | <span data-ttu-id="6f6f1-400">Disponibile se entityType è *SecurityGroup.*</span><span class="sxs-lookup"><span data-stu-id="6f6f1-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="6f6f1-401">Network Configuration Operators</span><span class="sxs-lookup"><span data-stu-id="6f6f1-401">Network Configuration Operators</span></span>
<span data-ttu-id="6f6f1-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="6f6f1-402">registryHive</span></span> | <span data-ttu-id="6f6f1-403">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6f6f1-404">HKEY \_ COMPUTER \_ LOCALE</span><span class="sxs-lookup"><span data-stu-id="6f6f1-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="6f6f1-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="6f6f1-405">registryKey</span></span> | <span data-ttu-id="6f6f1-406">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6f6f1-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="6f6f1-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="6f6f1-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="6f6f1-408">registryValueType</span></span> | <span data-ttu-id="6f6f1-409">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6f6f1-410">Stringa</span><span class="sxs-lookup"><span data-stu-id="6f6f1-410">String</span></span>
<span data-ttu-id="6f6f1-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="6f6f1-411">registryValue</span></span> | <span data-ttu-id="6f6f1-412">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6f6f1-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="6f6f1-413">31-00-00-00</span></span>
<span data-ttu-id="6f6f1-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="6f6f1-414">deviceId</span></span> | <span data-ttu-id="6f6f1-415">ID, se presente, del dispositivo correlato all'entità.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="6f6f1-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="6f6f1-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="6f6f1-417">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f6f1-417">Example</span></span>

<span data-ttu-id="6f6f1-418">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="6f6f1-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="6f6f1-419">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="6f6f1-419">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="6f6f1-420">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="6f6f1-420">Related articles</span></span>

- [<span data-ttu-id="6f6f1-421">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f6f1-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="6f6f1-422">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="6f6f1-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="6f6f1-423">Comprendere i codici di errore</span><span class="sxs-lookup"><span data-stu-id="6f6f1-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="6f6f1-424">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="6f6f1-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6f6f1-425">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="6f6f1-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="6f6f1-426">API per gli eventi imprevisti di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="6f6f1-426">Update incident API</span></span>](api-update-incidents.md)
