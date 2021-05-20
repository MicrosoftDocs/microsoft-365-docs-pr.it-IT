---
title: Api elenco incidenti in Microsoft 365 Defender
description: Informazioni su come elencare l'API degli incidenti in Microsoft 365 Defender
keywords: elenco, incidente, incidenti, api
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
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572154"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="dc289-104">Api elenco incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc289-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dc289-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="dc289-105">**Applies to:**</span></span>

- <span data-ttu-id="dc289-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc289-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc289-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="dc289-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dc289-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="dc289-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="dc289-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="dc289-109">API description</span></span>

<span data-ttu-id="dc289-110">L'API degli incidenti dell'elenco consente di ordinare gli incidenti per creare una risposta informata alla sicurezza informatica.</span><span class="sxs-lookup"><span data-stu-id="dc289-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="dc289-111">Espone una raccolta di incidenti contrassegnati nella rete, entro l'intervallo di tempo specificato nei criteri di conservazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="dc289-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="dc289-112">Gli incidenti più recenti vengono visualizzati nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dc289-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="dc289-113">Ogni incidente contiene una serie di avvisi correlati e le relative entità.</span><span class="sxs-lookup"><span data-stu-id="dc289-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="dc289-114">L'API supporta i seguenti **operatori OData:**</span><span class="sxs-lookup"><span data-stu-id="dc289-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="dc289-115">`$filter`sulle `lastUpdateTime` proprietà `createdTime` , , `status` e `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="dc289-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="dc289-116">`$top`, con un valore massimo di **100**</span><span class="sxs-lookup"><span data-stu-id="dc289-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="dc289-117">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="dc289-117">Limitations</span></span>

1. <span data-ttu-id="dc289-118">La dimensione massima della pagina **è di 100 incidenti**.</span><span class="sxs-lookup"><span data-stu-id="dc289-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="dc289-119">La frequenza massima delle richieste è **di 50 chiamate al minuto** e **1500 chiamate all'ora.**</span><span class="sxs-lookup"><span data-stu-id="dc289-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="dc289-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="dc289-120">Permissions</span></span>

<span data-ttu-id="dc289-121">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dc289-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dc289-122">Per altre informazioni, incluso come scegliere le autorizzazioni, vedere [Access Microsoft 365 Defender API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="dc289-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="dc289-123">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dc289-123">Permission type</span></span> | <span data-ttu-id="dc289-124">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dc289-124">Permission</span></span> | <span data-ttu-id="dc289-125">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dc289-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="dc289-126">Applicazione</span><span class="sxs-lookup"><span data-stu-id="dc289-126">Application</span></span> | <span data-ttu-id="dc289-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="dc289-127">Incident.Read.All</span></span> | <span data-ttu-id="dc289-128">Leggi tutti gli incidenti</span><span class="sxs-lookup"><span data-stu-id="dc289-128">Read all incidents</span></span>
<span data-ttu-id="dc289-129">Applicazione</span><span class="sxs-lookup"><span data-stu-id="dc289-129">Application</span></span> | <span data-ttu-id="dc289-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="dc289-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="dc289-131">Leggere e scrivere tutti gli incidenti</span><span class="sxs-lookup"><span data-stu-id="dc289-131">Read and write all incidents</span></span>
<span data-ttu-id="dc289-132">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="dc289-132">Delegated (work or school account)</span></span> | <span data-ttu-id="dc289-133">Incidente.Lettura</span><span class="sxs-lookup"><span data-stu-id="dc289-133">Incident.Read</span></span> | <span data-ttu-id="dc289-134">Leggi gli incidenti</span><span class="sxs-lookup"><span data-stu-id="dc289-134">Read incidents</span></span>
<span data-ttu-id="dc289-135">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="dc289-135">Delegated (work or school account)</span></span> | <span data-ttu-id="dc289-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="dc289-136">Incident.ReadWrite</span></span> | <span data-ttu-id="dc289-137">Leggere e scrivere incidenti</span><span class="sxs-lookup"><span data-stu-id="dc289-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="dc289-138">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="dc289-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="dc289-139">L'utente deve avere l'autorizzazione di visualizzazione per gli incidenti nel portale.</span><span class="sxs-lookup"><span data-stu-id="dc289-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="dc289-140">La risposta includerà solo gli incidenti a cui l'utente è esposto.</span><span class="sxs-lookup"><span data-stu-id="dc289-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="dc289-141">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="dc289-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="dc289-142">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="dc289-142">Request headers</span></span>

<span data-ttu-id="dc289-143">Name</span><span class="sxs-lookup"><span data-stu-id="dc289-143">Name</span></span> | <span data-ttu-id="dc289-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="dc289-144">Type</span></span> | <span data-ttu-id="dc289-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc289-145">Description</span></span>
-|-|-
<span data-ttu-id="dc289-146">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dc289-146">Authorization</span></span> | <span data-ttu-id="dc289-147">Stringa</span><span class="sxs-lookup"><span data-stu-id="dc289-147">String</span></span> | <span data-ttu-id="dc289-148">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="dc289-148">Bearer {token}.</span></span> <span data-ttu-id="dc289-149">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="dc289-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="dc289-150">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="dc289-150">Request body</span></span>

<span data-ttu-id="dc289-151">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="dc289-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="dc289-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="dc289-152">Response</span></span>

<span data-ttu-id="dc289-153">In caso di esito positivo, questo `200 OK` metodo restituisce e un elenco [di](api-incident.md) incidenti nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="dc289-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="dc289-154">Mapping dello schema</span><span class="sxs-lookup"><span data-stu-id="dc289-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="dc289-155">Metadati dell'incidente</span><span class="sxs-lookup"><span data-stu-id="dc289-155">Incident metadata</span></span>

<span data-ttu-id="dc289-156">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="dc289-156">Field name</span></span> | <span data-ttu-id="dc289-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc289-157">Description</span></span> | <span data-ttu-id="dc289-158">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="dc289-158">Example value</span></span>
-|-|-
<span data-ttu-id="dc289-159">id incidente</span><span class="sxs-lookup"><span data-stu-id="dc289-159">incidentId</span></span> | <span data-ttu-id="dc289-160">Identificatore univoco per rappresentare l'incidente</span><span class="sxs-lookup"><span data-stu-id="dc289-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="dc289-161">924565</span><span class="sxs-lookup"><span data-stu-id="dc289-161">924565</span></span>
<span data-ttu-id="dc289-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="dc289-162">redirectIncidentId</span></span> | <span data-ttu-id="dc289-163">Popolato solo nel caso in cui un incidente venga raggruppato insieme a un altro incidente, come parte della logica di elaborazione degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="dc289-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="dc289-164">924569</span><span class="sxs-lookup"><span data-stu-id="dc289-164">924569</span></span>
<span data-ttu-id="dc289-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="dc289-165">incidentName</span></span> | <span data-ttu-id="dc289-166">Valore stringa disponibile per ogni incidente.</span><span class="sxs-lookup"><span data-stu-id="dc289-166">String value available for every incident.</span></span> | <span data-ttu-id="dc289-167">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="dc289-167">Ransomware activity</span></span>
<span data-ttu-id="dc289-168">tempo creato</span><span class="sxs-lookup"><span data-stu-id="dc289-168">createdTime</span></span> | <span data-ttu-id="dc289-169">Ora in cui l'incidente è stato creato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="dc289-169">Time when incident was first created.</span></span> | <span data-ttu-id="dc289-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="dc289-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="dc289-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="dc289-171">lastUpdateTime</span></span> | <span data-ttu-id="dc289-172">Ora dell'ultimo aggiornamento dell'incidente nel back-end.</span><span class="sxs-lookup"><span data-stu-id="dc289-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="dc289-173">Questo campo può essere utilizzato quando si imposta il parametro request per l'intervallo di tempo in cui vengono recuperati gli incidenti.</span><span class="sxs-lookup"><span data-stu-id="dc289-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="dc289-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="dc289-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="dc289-175">assegnatoA</span><span class="sxs-lookup"><span data-stu-id="dc289-175">assignedTo</span></span> | <span data-ttu-id="dc289-176">Proprietario dell'incidente o *null se* non è assegnato alcun proprietario.</span><span class="sxs-lookup"><span data-stu-id="dc289-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="dc289-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc289-177">secop2@contoso.com</span></span>
<span data-ttu-id="dc289-178">classificazione</span><span class="sxs-lookup"><span data-stu-id="dc289-178">classification</span></span> | <span data-ttu-id="dc289-179">Specifica dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="dc289-179">The specification for the incident.</span></span> <span data-ttu-id="dc289-180">I valori delle proprietà *sono: Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="dc289-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="dc289-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="dc289-181">Unknown</span></span>
<span data-ttu-id="dc289-182">determinazione</span><span class="sxs-lookup"><span data-stu-id="dc289-182">determination</span></span> | <span data-ttu-id="dc289-183">Specifica la determinazione dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="dc289-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="dc289-184">I valori delle proprietà sono: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="dc289-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="dc289-185">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="dc289-185">NotAvailable</span></span>
<span data-ttu-id="dc289-186">stato</span><span class="sxs-lookup"><span data-stu-id="dc289-186">status</span></span> | <span data-ttu-id="dc289-187">Categorizzare gli incidenti *(come* attivi o *risolti).*</span><span class="sxs-lookup"><span data-stu-id="dc289-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="dc289-188">Può aiutarti a organizzare e gestire la tua risposta agli incidenti.</span><span class="sxs-lookup"><span data-stu-id="dc289-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="dc289-189">Attivo</span><span class="sxs-lookup"><span data-stu-id="dc289-189">Active</span></span>
<span data-ttu-id="dc289-190">severità</span><span class="sxs-lookup"><span data-stu-id="dc289-190">severity</span></span> | <span data-ttu-id="dc289-191">Indica il possibile impatto sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="dc289-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="dc289-192">Maggiore è la gravità, maggiore è l'impatto.</span><span class="sxs-lookup"><span data-stu-id="dc289-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="dc289-193">In genere gli elementi di gravità più elevata richiedono l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="dc289-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="dc289-194">Uno dei valori seguenti: *Informational*, *Low*, \*Medium e *High*.</span><span class="sxs-lookup"><span data-stu-id="dc289-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="dc289-195">Medio</span><span class="sxs-lookup"><span data-stu-id="dc289-195">Medium</span></span>
<span data-ttu-id="dc289-196">Tag</span><span class="sxs-lookup"><span data-stu-id="dc289-196">tags</span></span> | <span data-ttu-id="dc289-197">Matrice di tag personalizzati associati a un incidente, ad esempio per contrassegnare un gruppo di incidenti con una caratteristica comune.</span><span class="sxs-lookup"><span data-stu-id="dc289-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="dc289-198">Commenti</span><span class="sxs-lookup"><span data-stu-id="dc289-198">comments</span></span> | <span data-ttu-id="dc289-199">Matrice di commenti creati dai secop durante la gestione dell'incidente, ad esempio informazioni aggiuntive sulla selezione della classificazione.</span><span class="sxs-lookup"><span data-stu-id="dc289-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="dc289-200">Avvisi</span><span class="sxs-lookup"><span data-stu-id="dc289-200">alerts</span></span> | <span data-ttu-id="dc289-201">Matrice contenente tutti gli avvisi relativi all'incidente, oltre ad altre informazioni, ad esempio la gravità, le entità coinvolte nell'avviso e l'origine degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="dc289-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="dc289-202">\[\] (vedere i dettagli sui campi degli avvisi di seguito)</span><span class="sxs-lookup"><span data-stu-id="dc289-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="dc289-203">Avvisi metadati</span><span class="sxs-lookup"><span data-stu-id="dc289-203">Alerts metadata</span></span>

<span data-ttu-id="dc289-204">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="dc289-204">Field name</span></span> | <span data-ttu-id="dc289-205">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc289-205">Description</span></span> | <span data-ttu-id="dc289-206">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="dc289-206">Example value</span></span>
-|-|-
<span data-ttu-id="dc289-207">ID avviso</span><span class="sxs-lookup"><span data-stu-id="dc289-207">alertId</span></span> | <span data-ttu-id="dc289-208">Identificatore univoco per rappresentare l'avviso</span><span class="sxs-lookup"><span data-stu-id="dc289-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="dc289-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="dc289-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="dc289-210">id incidente</span><span class="sxs-lookup"><span data-stu-id="dc289-210">incidentId</span></span> | <span data-ttu-id="dc289-211">Identificatore univoco per rappresentare l'incidente a cui è associato questo avviso</span><span class="sxs-lookup"><span data-stu-id="dc289-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="dc289-212">924565</span><span class="sxs-lookup"><span data-stu-id="dc289-212">924565</span></span>
<span data-ttu-id="dc289-213">origine servizio</span><span class="sxs-lookup"><span data-stu-id="dc289-213">serviceSource</span></span> | <span data-ttu-id="dc289-214">Servizio da cui proviene l'avviso, ad esempio Microsoft Defender per Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity o Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc289-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="dc289-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="dc289-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="dc289-216">tempo di creazione</span><span class="sxs-lookup"><span data-stu-id="dc289-216">creationTime</span></span> | <span data-ttu-id="dc289-217">Ora di creazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="dc289-217">Time when alert was first created.</span></span> | <span data-ttu-id="dc289-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="dc289-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="dc289-219">LastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="dc289-219">lastUpdatedTime</span></span> | <span data-ttu-id="dc289-220">Ora dell'ultimo aggiornamento dell'avviso nel back-end.</span><span class="sxs-lookup"><span data-stu-id="dc289-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="dc289-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="dc289-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="dc289-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="dc289-222">resolvedTime</span></span> | <span data-ttu-id="dc289-223">Ora in cui l'avviso è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="dc289-223">Time when alert was resolved.</span></span> | <span data-ttu-id="dc289-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="dc289-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="dc289-225">prima Attività</span><span class="sxs-lookup"><span data-stu-id="dc289-225">firstActivity</span></span> | <span data-ttu-id="dc289-226">Ora in cui l'avviso ha segnalato per la prima volta che l'attività è stata aggiornata al back-end.</span><span class="sxs-lookup"><span data-stu-id="dc289-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="dc289-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="dc289-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="dc289-228">title</span><span class="sxs-lookup"><span data-stu-id="dc289-228">title</span></span> | <span data-ttu-id="dc289-229">Breve identificazione del valore stringa disponibile per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="dc289-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="dc289-230">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="dc289-230">Ransomware activity</span></span>
<span data-ttu-id="dc289-231">descrizione</span><span class="sxs-lookup"><span data-stu-id="dc289-231">description</span></span> | <span data-ttu-id="dc289-232">Valore stringa che descrive ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="dc289-232">String value describing each alert.</span></span> | <span data-ttu-id="dc289-233">L'utente Test User2 (testUser2@contoso.com) ha manipolato 99 file con più estensioni che terminano con l'estensione non *comune herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="dc289-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="dc289-234">Questo è un numero insolito di manipolazioni di file ed è indicativo di un potenziale attacco ransomware.</span><span class="sxs-lookup"><span data-stu-id="dc289-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="dc289-235">categoria</span><span class="sxs-lookup"><span data-stu-id="dc289-235">category</span></span> | <span data-ttu-id="dc289-236">Visualizzazione visiva e numerica di quanto l'attacco è progredito lungo la catena di uccisioni.</span><span class="sxs-lookup"><span data-stu-id="dc289-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="dc289-237">Allineato al [framework CK&CK™&MITRE](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="dc289-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="dc289-238">Impatto</span><span class="sxs-lookup"><span data-stu-id="dc289-238">Impact</span></span>
<span data-ttu-id="dc289-239">stato</span><span class="sxs-lookup"><span data-stu-id="dc289-239">status</span></span> | <span data-ttu-id="dc289-240">Categorizzare gli avvisi *(come* Nuovi *, Attivi* o *Risolti*).</span><span class="sxs-lookup"><span data-stu-id="dc289-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="dc289-241">Può aiutarti a organizzare e gestire la tua risposta agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="dc289-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="dc289-242">Nuovo</span><span class="sxs-lookup"><span data-stu-id="dc289-242">New</span></span>
<span data-ttu-id="dc289-243">severità</span><span class="sxs-lookup"><span data-stu-id="dc289-243">severity</span></span> | <span data-ttu-id="dc289-244">Indica il possibile impatto sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="dc289-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="dc289-245">Maggiore è la gravità, maggiore è l'impatto.</span><span class="sxs-lookup"><span data-stu-id="dc289-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="dc289-246">In genere gli elementi di gravità più elevata richiedono l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="dc289-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="dc289-247">Uno dei valori seguenti: *Informational*, *Low*, \*Medium e *High*.</span><span class="sxs-lookup"><span data-stu-id="dc289-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="dc289-248">Medio</span><span class="sxs-lookup"><span data-stu-id="dc289-248">Medium</span></span>
<span data-ttu-id="dc289-249">ID indagine</span><span class="sxs-lookup"><span data-stu-id="dc289-249">investigationId</span></span> | <span data-ttu-id="dc289-250">ID dell'indagine automatizzato attivato da questo avviso.</span><span class="sxs-lookup"><span data-stu-id="dc289-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="dc289-251">1234</span><span class="sxs-lookup"><span data-stu-id="dc289-251">1234</span></span>
<span data-ttu-id="dc289-252">studioStato</span><span class="sxs-lookup"><span data-stu-id="dc289-252">investigationState</span></span> | <span data-ttu-id="dc289-253">Informazioni sullo stato attuale dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="dc289-253">Information on the investigation's current status.</span></span> <span data-ttu-id="dc289-254">Uno dei valori seguenti: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="dc289-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="dc289-255">Tipo non supportato</span><span class="sxs-lookup"><span data-stu-id="dc289-255">UnsupportedAlertType</span></span>
<span data-ttu-id="dc289-256">classificazione</span><span class="sxs-lookup"><span data-stu-id="dc289-256">classification</span></span> | <span data-ttu-id="dc289-257">Specifica dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="dc289-257">The specification for the incident.</span></span> <span data-ttu-id="dc289-258">I valori delle proprietà *sono: Unknown*, *FalsePositive*, *TruePositive* o *null*</span><span class="sxs-lookup"><span data-stu-id="dc289-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="dc289-259">Unknown</span><span class="sxs-lookup"><span data-stu-id="dc289-259">Unknown</span></span>
<span data-ttu-id="dc289-260">determinazione</span><span class="sxs-lookup"><span data-stu-id="dc289-260">determination</span></span> | <span data-ttu-id="dc289-261">Specifica la determinazione dell'incidente.</span><span class="sxs-lookup"><span data-stu-id="dc289-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="dc289-262">I valori delle proprietà sono: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* o  *null*</span><span class="sxs-lookup"><span data-stu-id="dc289-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="dc289-263">Appartamento</span><span class="sxs-lookup"><span data-stu-id="dc289-263">Apt</span></span>
<span data-ttu-id="dc289-264">assegnatoA</span><span class="sxs-lookup"><span data-stu-id="dc289-264">assignedTo</span></span> | <span data-ttu-id="dc289-265">Proprietario dell'incidente o *null se* non è assegnato alcun proprietario.</span><span class="sxs-lookup"><span data-stu-id="dc289-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="dc289-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc289-266">secop2@contoso.com</span></span>
<span data-ttu-id="dc289-267">nome attore</span><span class="sxs-lookup"><span data-stu-id="dc289-267">actorName</span></span> | <span data-ttu-id="dc289-268">Il gruppo di attività, se presente, l'oggetto associato a questo avviso.</span><span class="sxs-lookup"><span data-stu-id="dc289-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="dc289-269">boro</span><span class="sxs-lookup"><span data-stu-id="dc289-269">BORON</span></span>
<span data-ttu-id="dc289-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="dc289-270">threatFamilyName</span></span> | <span data-ttu-id="dc289-271">Famiglia di minacce associata a questo avviso.</span><span class="sxs-lookup"><span data-stu-id="dc289-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="dc289-272">null</span><span class="sxs-lookup"><span data-stu-id="dc289-272">null</span></span>
<span data-ttu-id="dc289-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="dc289-273">mitreTechniques</span></span> | <span data-ttu-id="dc289-274">Le tecniche di attacco, allineate con [la MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span><span class="sxs-lookup"><span data-stu-id="dc289-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="dc289-275">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="dc289-275">devices</span></span> | <span data-ttu-id="dc289-276">Tutti i dispositivi in cui sono stati inviati avvisi relativi all'incidente.</span><span class="sxs-lookup"><span data-stu-id="dc289-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="dc289-277">\[\] (vedere i dettagli sui campi delle entità di seguito)</span><span class="sxs-lookup"><span data-stu-id="dc289-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="dc289-278">Formato dispositivo</span><span class="sxs-lookup"><span data-stu-id="dc289-278">Device format</span></span>

<span data-ttu-id="dc289-279">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="dc289-279">Field name</span></span> | <span data-ttu-id="dc289-280">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc289-280">Description</span></span> | <span data-ttu-id="dc289-281">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="dc289-281">Example value</span></span>
-|-|-
<span data-ttu-id="dc289-282">Id dispositivo</span><span class="sxs-lookup"><span data-stu-id="dc289-282">DeviceId</span></span> | <span data-ttu-id="dc289-283">ID dispositivo come indicato in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc289-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="dc289-284">24c222B0B60FE148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="dc289-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="dc289-285">AadDeviceId</span><span class="sxs-lookup"><span data-stu-id="dc289-285">aadDeviceId</span></span> |  <span data-ttu-id="dc289-286">ID dispositivo come indicato in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="dc289-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="dc289-287">Disponibile solo per i dispositivi aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="dc289-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="dc289-288">null</span><span class="sxs-lookup"><span data-stu-id="dc289-288">null</span></span>
<span data-ttu-id="dc289-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="dc289-289">deviceDnsName</span></span> | <span data-ttu-id="dc289-290">Nome di dominio completo per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc289-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="dc289-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc289-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="dc289-292">piattaforma os</span><span class="sxs-lookup"><span data-stu-id="dc289-292">osPlatform</span></span> | <span data-ttu-id="dc289-293">La piattaforma del sistema operativo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dc289-293">The OS platform the device is running.</span></span>| <span data-ttu-id="dc289-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="dc289-294">WindowsServer2016</span></span>
<span data-ttu-id="dc289-295">edificio del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="dc289-295">osBuild</span></span> | <span data-ttu-id="dc289-296">Versione di compilazione per il sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc289-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="dc289-297">14393</span><span class="sxs-lookup"><span data-stu-id="dc289-297">14393</span></span>
<span data-ttu-id="dc289-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="dc289-298">rbacGroupName</span></span> | <span data-ttu-id="dc289-299">Gruppo [di controllo degli accessi](/azure/role-based-access-control/overview) basato sui ruoli (RBAC) associato al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc289-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="dc289-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="dc289-300">WDATP-Ring0</span></span>
<span data-ttu-id="dc289-301">primaSeen</span><span class="sxs-lookup"><span data-stu-id="dc289-301">firstSeen</span></span> | <span data-ttu-id="dc289-302">Ora in cui il dispositivo è stato visto per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="dc289-302">Time when device was first seen.</span></span> | <span data-ttu-id="dc289-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="dc289-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="dc289-304">stato integrità</span><span class="sxs-lookup"><span data-stu-id="dc289-304">healthStatus</span></span> | <span data-ttu-id="dc289-305">Stato di integrità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc289-305">The health state of the device.</span></span> | <span data-ttu-id="dc289-306">Attivo</span><span class="sxs-lookup"><span data-stu-id="dc289-306">Active</span></span>
<span data-ttu-id="dc289-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="dc289-307">riskScore</span></span> | <span data-ttu-id="dc289-308">Punteggio di rischio per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc289-308">The risk score for the  device.</span></span> | <span data-ttu-id="dc289-309">Alta</span><span class="sxs-lookup"><span data-stu-id="dc289-309">High</span></span>
<span data-ttu-id="dc289-310">Entità</span><span class="sxs-lookup"><span data-stu-id="dc289-310">entities</span></span> | <span data-ttu-id="dc289-311">Tutte le entità identificate come parte o correlate a un determinato avviso.</span><span class="sxs-lookup"><span data-stu-id="dc289-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="dc289-312">\[\] (vedere i dettagli sui campi delle entità di seguito)</span><span class="sxs-lookup"><span data-stu-id="dc289-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="dc289-313">Formato entità</span><span class="sxs-lookup"><span data-stu-id="dc289-313">Entity Format</span></span>

<span data-ttu-id="dc289-314">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="dc289-314">Field name</span></span> | <span data-ttu-id="dc289-315">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc289-315">Description</span></span> | <span data-ttu-id="dc289-316">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="dc289-316">Example value</span></span>
-|-|-
<span data-ttu-id="dc289-317">tipo entità</span><span class="sxs-lookup"><span data-stu-id="dc289-317">entityType</span></span> | <span data-ttu-id="dc289-318">Entità che sono state identificate come parte o correlate a un determinato avviso.</span><span class="sxs-lookup"><span data-stu-id="dc289-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="dc289-319">I valori delle proprietà sono: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster* *,* Registry</span><span class="sxs-lookup"><span data-stu-id="dc289-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="dc289-320">Utente</span><span class="sxs-lookup"><span data-stu-id="dc289-320">User</span></span>
<span data-ttu-id="dc289-321">sha1</span><span class="sxs-lookup"><span data-stu-id="dc289-321">sha1</span></span> | <span data-ttu-id="dc289-322">Disponibile se entityType è *File*.</span><span class="sxs-lookup"><span data-stu-id="dc289-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="dc289-323">Hash del file per gli avvisi associati a un file o a un processo.</span><span class="sxs-lookup"><span data-stu-id="dc289-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="dc289-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="dc289-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="dc289-325">sha256</span><span class="sxs-lookup"><span data-stu-id="dc289-325">sha256</span></span> | <span data-ttu-id="dc289-326">Disponibile se entityType è *File*.</span><span class="sxs-lookup"><span data-stu-id="dc289-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="dc289-327">Hash del file per gli avvisi associati a un file o a un processo.</span><span class="sxs-lookup"><span data-stu-id="dc289-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="dc289-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="dc289-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="dc289-329">Filename</span><span class="sxs-lookup"><span data-stu-id="dc289-329">fileName</span></span> | <span data-ttu-id="dc289-330">Disponibile se entityType è *File*.</span><span class="sxs-lookup"><span data-stu-id="dc289-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="dc289-331">Nome file per gli avvisi associati a un file o a un processo</span><span class="sxs-lookup"><span data-stu-id="dc289-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="dc289-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="dc289-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="dc289-333">percorsofile</span><span class="sxs-lookup"><span data-stu-id="dc289-333">filePath</span></span> | <span data-ttu-id="dc289-334">Disponibile se entityType è *File*.</span><span class="sxs-lookup"><span data-stu-id="dc289-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="dc289-335">Percorso del file per gli avvisi associati a un file o a un processo</span><span class="sxs-lookup"><span data-stu-id="dc289-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="dc289-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="dc289-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="dc289-337">ID processo</span><span class="sxs-lookup"><span data-stu-id="dc289-337">processId</span></span> | <span data-ttu-id="dc289-338">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="dc289-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="dc289-339">24348</span><span class="sxs-lookup"><span data-stu-id="dc289-339">24348</span></span>
<span data-ttu-id="dc289-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="dc289-340">processCommandLine</span></span> | <span data-ttu-id="dc289-341">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="dc289-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="dc289-342">"Il file è pronto per il \_ download1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="dc289-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="dc289-343">ProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="dc289-343">processCreationTime</span></span> | <span data-ttu-id="dc289-344">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="dc289-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="dc289-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="dc289-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="dc289-346">IdProcesso padre</span><span class="sxs-lookup"><span data-stu-id="dc289-346">parentProcessId</span></span> | <span data-ttu-id="dc289-347">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="dc289-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="dc289-348">16840</span><span class="sxs-lookup"><span data-stu-id="dc289-348">16840</span></span>
<span data-ttu-id="dc289-349">ParentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="dc289-349">parentProcessCreationTime</span></span> | <span data-ttu-id="dc289-350">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="dc289-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="dc289-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="dc289-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="dc289-352">Indirizzoip</span><span class="sxs-lookup"><span data-stu-id="dc289-352">ipAddress</span></span> | <span data-ttu-id="dc289-353">Disponibile se entityType è *Ip*.</span><span class="sxs-lookup"><span data-stu-id="dc289-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="dc289-354">Indirizzo IP per gli avvisi associati a eventi di rete, ad esempio *Comunicazione a una destinazione di rete dannosa*.</span><span class="sxs-lookup"><span data-stu-id="dc289-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="dc289-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="dc289-355">62.216.203.204</span></span>
<span data-ttu-id="dc289-356">URL</span><span class="sxs-lookup"><span data-stu-id="dc289-356">url</span></span> | <span data-ttu-id="dc289-357">Disponibile se entityType è *URL*.</span><span class="sxs-lookup"><span data-stu-id="dc289-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="dc289-358">URL degli avvisi associati agli eventi di rete, ad esempio *Comunicazione a una destinazione di rete dannosa*.</span><span class="sxs-lookup"><span data-stu-id="dc289-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="dc289-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="dc289-359">down.esales360.cn</span></span>
<span data-ttu-id="dc289-360">nome account</span><span class="sxs-lookup"><span data-stu-id="dc289-360">accountName</span></span> | <span data-ttu-id="dc289-361">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="dc289-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="dc289-362">Utentetest2</span><span class="sxs-lookup"><span data-stu-id="dc289-362">testUser2</span></span>
<span data-ttu-id="dc289-363">nomedominio</span><span class="sxs-lookup"><span data-stu-id="dc289-363">domainName</span></span> | <span data-ttu-id="dc289-364">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="dc289-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="dc289-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="dc289-365">europe.corp.contoso</span></span>
<span data-ttu-id="dc289-366">IDutenti</span><span class="sxs-lookup"><span data-stu-id="dc289-366">userSid</span></span> | <span data-ttu-id="dc289-367">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="dc289-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="dc289-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="dc289-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="dc289-369">id utenteaad</span><span class="sxs-lookup"><span data-stu-id="dc289-369">aadUserId</span></span> | <span data-ttu-id="dc289-370">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="dc289-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="dc289-371">FC8F7484-F813-4DB2-AFAB-BC1507913FB6</span><span class="sxs-lookup"><span data-stu-id="dc289-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="dc289-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="dc289-372">userPrincipalName</span></span> | <span data-ttu-id="dc289-373">Disponibile se entityType è *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="dc289-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="dc289-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc289-374">testUser2@contoso.com</span></span>
<span data-ttu-id="dc289-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="dc289-375">mailboxDisplayName</span></span> | <span data-ttu-id="dc289-376">Disponibile se entityType è *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="dc289-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="dc289-377">testare l'utente2</span><span class="sxs-lookup"><span data-stu-id="dc289-377">test User2</span></span>
<span data-ttu-id="dc289-378">indirizzo cassetta postale</span><span class="sxs-lookup"><span data-stu-id="dc289-378">mailboxAddress</span></span> | <span data-ttu-id="dc289-379">Disponibile se entityType è *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="dc289-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="dc289-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc289-380">testUser2@contoso.com</span></span>
<span data-ttu-id="dc289-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="dc289-381">clusterBy</span></span> | <span data-ttu-id="dc289-382">Disponibile se entityType è  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="dc289-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="dc289-383">Oggetto; P2SenderDomain; Tipo di contenuto</span><span class="sxs-lookup"><span data-stu-id="dc289-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="dc289-384">mittente</span><span class="sxs-lookup"><span data-stu-id="dc289-384">sender</span></span> | <span data-ttu-id="dc289-385">Disponibile se entityType è *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="dc289-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="dc289-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="dc289-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="dc289-387">destinatario</span><span class="sxs-lookup"><span data-stu-id="dc289-387">recipient</span></span> | <span data-ttu-id="dc289-388">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="dc289-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="dc289-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc289-389">testUser2@contoso.com</span></span>
<span data-ttu-id="dc289-390">subject</span><span class="sxs-lookup"><span data-stu-id="dc289-390">subject</span></span> | <span data-ttu-id="dc289-391">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="dc289-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="dc289-392">\[ATTENZIONE \] ESTERNA</span><span class="sxs-lookup"><span data-stu-id="dc289-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="dc289-393">deliveryAzione</span><span class="sxs-lookup"><span data-stu-id="dc289-393">deliveryAction</span></span> | <span data-ttu-id="dc289-394">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="dc289-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="dc289-395">consegnato</span><span class="sxs-lookup"><span data-stu-id="dc289-395">Delivered</span></span>
<span data-ttu-id="dc289-396">SecurityGroupId</span><span class="sxs-lookup"><span data-stu-id="dc289-396">securityGroupId</span></span> | <span data-ttu-id="dc289-397">Disponibile se entityType è  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="dc289-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="dc289-398">301C47C8-E15F-4059-AB09-E2BA9FFD372B</span><span class="sxs-lookup"><span data-stu-id="dc289-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="dc289-399">nomegruppodi protezione</span><span class="sxs-lookup"><span data-stu-id="dc289-399">securityGroupName</span></span> | <span data-ttu-id="dc289-400">Disponibile se entityType è  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="dc289-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="dc289-401">Operatori di configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="dc289-401">Network Configuration Operators</span></span>
<span data-ttu-id="dc289-402">registroHive</span><span class="sxs-lookup"><span data-stu-id="dc289-402">registryHive</span></span> | <span data-ttu-id="dc289-403">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="dc289-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="dc289-404">HKEY \_ LOCAL \_ MACHINE</span><span class="sxs-lookup"><span data-stu-id="dc289-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="dc289-405">Chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="dc289-405">registryKey</span></span> | <span data-ttu-id="dc289-406">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="dc289-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="dc289-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="dc289-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="dc289-408">RegistryValueType</span><span class="sxs-lookup"><span data-stu-id="dc289-408">registryValueType</span></span> | <span data-ttu-id="dc289-409">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="dc289-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="dc289-410">Stringa</span><span class="sxs-lookup"><span data-stu-id="dc289-410">String</span></span>
<span data-ttu-id="dc289-411">valore del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="dc289-411">registryValue</span></span> | <span data-ttu-id="dc289-412">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="dc289-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="dc289-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="dc289-413">31-00-00-00</span></span>
<span data-ttu-id="dc289-414">ID dispositivo</span><span class="sxs-lookup"><span data-stu-id="dc289-414">deviceId</span></span> | <span data-ttu-id="dc289-415">ID, se del caso, del dispositivo relativo all'entità.</span><span class="sxs-lookup"><span data-stu-id="dc289-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="dc289-416">986E5DF8B73DACD43C8917D17E523E76B13C75CD</span><span class="sxs-lookup"><span data-stu-id="dc289-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="dc289-417">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc289-417">Example</span></span>

<span data-ttu-id="dc289-418">**richiesta**</span><span class="sxs-lookup"><span data-stu-id="dc289-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="dc289-419">**risposta**</span><span class="sxs-lookup"><span data-stu-id="dc289-419">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="dc289-420">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="dc289-420">Related articles</span></span>

- [<span data-ttu-id="dc289-421">Accedere alle API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc289-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="dc289-422">Informazioni sui limiti e le licenze delle API</span><span class="sxs-lookup"><span data-stu-id="dc289-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="dc289-423">Informazioni i codici di errore</span><span class="sxs-lookup"><span data-stu-id="dc289-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="dc289-424">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="dc289-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="dc289-425">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="dc289-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="dc289-426">Aggiornare l'API degli incidenti</span><span class="sxs-lookup"><span data-stu-id="dc289-426">Update incident API</span></span>](api-update-incidents.md)
