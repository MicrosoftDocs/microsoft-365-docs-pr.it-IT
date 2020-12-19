---
title: Elenco delle API incidentate in Microsoft 365 Defender
description: Informazioni su come elencare le API degli incidenti in Microsoft 365 Defender
keywords: elenco, incidenti, incidenti, API
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
ms.openlocfilehash: 13508d3ad9d61797517ccb55a27152883947843a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719429"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="e6671-104">Elenco delle API incidentate in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6671-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e6671-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e6671-105">**Applies to:**</span></span>

- <span data-ttu-id="e6671-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6671-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6671-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="e6671-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e6671-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e6671-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="e6671-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="e6671-109">API description</span></span>

<span data-ttu-id="e6671-110">L'API degli eventi imprevisti dell'elenco consente di ordinare gli eventi non consentiti per creare una risposta Cybersecurity informata.</span><span class="sxs-lookup"><span data-stu-id="e6671-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="e6671-111">Espone una raccolta di operazioni non consentite che sono state contrassegnate nella rete, all'interno dell'intervallo di tempo specificato nel criterio di conservazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6671-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="e6671-112">Gli incidenti più recenti vengono visualizzati all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e6671-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="e6671-113">Ogni evento Incident contiene una matrice di avvisi correlati e le entità correlate.</span><span class="sxs-lookup"><span data-stu-id="e6671-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="e6671-114">L'API supporta gli operatori **OData** seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6671-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="e6671-115">`$filter`nelle `lastUpdateTime` proprietà, `createdTime` , `status` e `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="e6671-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="e6671-116">`$top`, con un valore massimo di **100**</span><span class="sxs-lookup"><span data-stu-id="e6671-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="e6671-117">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="e6671-117">Limitations</span></span>

1. <span data-ttu-id="e6671-118">La dimensione massima della pagina è di **100 incidenti**.</span><span class="sxs-lookup"><span data-stu-id="e6671-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="e6671-119">La frequenza massima delle richieste è di **50 chiamate al minuto** e **1500 chiamate all'ora**.</span><span class="sxs-lookup"><span data-stu-id="e6671-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="e6671-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e6671-120">Permissions</span></span>

<span data-ttu-id="e6671-121">Per chiamare l'API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e6671-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e6671-122">Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access Microsoft 365 Defender Apis](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="e6671-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="e6671-123">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e6671-123">Permission type</span></span> | <span data-ttu-id="e6671-124">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e6671-124">Permission</span></span> | <span data-ttu-id="e6671-125">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e6671-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="e6671-126">Applicazione</span><span class="sxs-lookup"><span data-stu-id="e6671-126">Application</span></span> | <span data-ttu-id="e6671-127">Incident. Read. All</span><span class="sxs-lookup"><span data-stu-id="e6671-127">Incident.Read.All</span></span> | <span data-ttu-id="e6671-128">Leggere tutti gli eventi non consentiti</span><span class="sxs-lookup"><span data-stu-id="e6671-128">Read all incidents</span></span>
<span data-ttu-id="e6671-129">Applicazione</span><span class="sxs-lookup"><span data-stu-id="e6671-129">Application</span></span> | <span data-ttu-id="e6671-130">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="e6671-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="e6671-131">Leggere e scrivere tutti gli eventi non consentiti</span><span class="sxs-lookup"><span data-stu-id="e6671-131">Read and write all incidents</span></span>
<span data-ttu-id="e6671-132">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="e6671-132">Delegated (work or school account)</span></span> | <span data-ttu-id="e6671-133">Evento Incident. Read</span><span class="sxs-lookup"><span data-stu-id="e6671-133">Incident.Read</span></span> | <span data-ttu-id="e6671-134">Leggere gli incidenti</span><span class="sxs-lookup"><span data-stu-id="e6671-134">Read incidents</span></span>
<span data-ttu-id="e6671-135">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="e6671-135">Delegated (work or school account)</span></span> | <span data-ttu-id="e6671-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e6671-136">Incident.ReadWrite</span></span> | <span data-ttu-id="e6671-137">Operazioni di lettura e scrittura degli incidenti</span><span class="sxs-lookup"><span data-stu-id="e6671-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="e6671-138">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="e6671-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="e6671-139">L'utente deve disporre dell'autorizzazione di visualizzazione per gli eventi non consentiti nel portale.</span><span class="sxs-lookup"><span data-stu-id="e6671-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="e6671-140">La risposta includerà solo gli incidenti a cui l'utente è esposto.</span><span class="sxs-lookup"><span data-stu-id="e6671-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="e6671-141">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="e6671-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="e6671-142">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="e6671-142">Request headers</span></span>

<span data-ttu-id="e6671-143">Name</span><span class="sxs-lookup"><span data-stu-id="e6671-143">Name</span></span> | <span data-ttu-id="e6671-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6671-144">Type</span></span> | <span data-ttu-id="e6671-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6671-145">Description</span></span>
-|-|-
<span data-ttu-id="e6671-146">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e6671-146">Authorization</span></span> | <span data-ttu-id="e6671-147">Stringa</span><span class="sxs-lookup"><span data-stu-id="e6671-147">String</span></span> | <span data-ttu-id="e6671-148">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="e6671-148">Bearer {token}.</span></span> <span data-ttu-id="e6671-149">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="e6671-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="e6671-150">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="e6671-150">Request body</span></span>

<span data-ttu-id="e6671-151">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="e6671-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="e6671-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="e6671-152">Response</span></span>

<span data-ttu-id="e6671-153">In caso di esito positivo, questo metodo restituisce `200 OK` un elenco di [eventi](api-incident.md) non consentiti nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="e6671-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="e6671-154">Mapping dello schema</span><span class="sxs-lookup"><span data-stu-id="e6671-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="e6671-155">Metadati degli incidenti</span><span class="sxs-lookup"><span data-stu-id="e6671-155">Incident metadata</span></span>

<span data-ttu-id="e6671-156">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="e6671-156">Field name</span></span> | <span data-ttu-id="e6671-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6671-157">Description</span></span> | <span data-ttu-id="e6671-158">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="e6671-158">Example value</span></span>
-|-|-
<span data-ttu-id="e6671-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="e6671-159">incidentId</span></span> | <span data-ttu-id="e6671-160">Identificatore univoco per rappresentare l'evento non consentita</span><span class="sxs-lookup"><span data-stu-id="e6671-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="e6671-161">924565</span><span class="sxs-lookup"><span data-stu-id="e6671-161">924565</span></span>
<span data-ttu-id="e6671-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="e6671-162">redirectIncidentId</span></span> | <span data-ttu-id="e6671-163">Viene popolato solo nel caso in cui un evento Incident venga raggruppato insieme a un altro incidente, come parte della logica di elaborazione degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="e6671-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="e6671-164">924569</span><span class="sxs-lookup"><span data-stu-id="e6671-164">924569</span></span>
<span data-ttu-id="e6671-165">evento incidentname</span><span class="sxs-lookup"><span data-stu-id="e6671-165">incidentName</span></span> | <span data-ttu-id="e6671-166">Valore stringa disponibile per ogni evento Incident.</span><span class="sxs-lookup"><span data-stu-id="e6671-166">String value available for every incident.</span></span> | <span data-ttu-id="e6671-167">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="e6671-167">Ransomware activity</span></span>
<span data-ttu-id="e6671-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="e6671-168">createdTime</span></span> | <span data-ttu-id="e6671-169">Ora in cui è stato creato l'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="e6671-169">Time when incident was first created.</span></span> | <span data-ttu-id="e6671-170">2020-09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="e6671-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="e6671-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="e6671-171">lastUpdateTime</span></span> | <span data-ttu-id="e6671-172">Ora dell'ultimo aggiornamento dell'incidente sul backend.</span><span class="sxs-lookup"><span data-stu-id="e6671-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="e6671-173">Questo campo può essere utilizzato quando si imposta il parametro request per l'intervallo di tempo in cui vengono recuperati gli eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="e6671-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="e6671-174">2020-09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="e6671-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="e6671-175">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="e6671-175">assignedTo</span></span> | <span data-ttu-id="e6671-176">Proprietario dell'evento Incident oppure *null* se non è stato assegnato alcun proprietario.</span><span class="sxs-lookup"><span data-stu-id="e6671-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="e6671-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e6671-177">secop2@contoso.com</span></span>
<span data-ttu-id="e6671-178">classificazione</span><span class="sxs-lookup"><span data-stu-id="e6671-178">classification</span></span> | <span data-ttu-id="e6671-179">Specifica per l'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="e6671-179">The specification for the incident.</span></span> <span data-ttu-id="e6671-180">I valori delle proprietà sono: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="e6671-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="e6671-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="e6671-181">Unknown</span></span>
<span data-ttu-id="e6671-182">determinazione</span><span class="sxs-lookup"><span data-stu-id="e6671-182">determination</span></span> | <span data-ttu-id="e6671-183">Specifica la determinazione dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="e6671-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="e6671-184">I valori delle proprietà sono: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other*</span><span class="sxs-lookup"><span data-stu-id="e6671-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="e6671-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="e6671-185">NotAvailable</span></span>
<span data-ttu-id="e6671-186">stato</span><span class="sxs-lookup"><span data-stu-id="e6671-186">status</span></span> | <span data-ttu-id="e6671-187">Categorizzare gli incidenti (come *attivi* o *risolti*).</span><span class="sxs-lookup"><span data-stu-id="e6671-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="e6671-188">Può essere utile per organizzare e gestire la risposta a eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="e6671-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="e6671-189">Attivazione</span><span class="sxs-lookup"><span data-stu-id="e6671-189">Active</span></span>
<span data-ttu-id="e6671-190">gravità</span><span class="sxs-lookup"><span data-stu-id="e6671-190">severity</span></span> | <span data-ttu-id="e6671-191">Indica il possibile impatto sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="e6671-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="e6671-192">Maggiore è la gravità più grande è l'impatto.</span><span class="sxs-lookup"><span data-stu-id="e6671-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="e6671-193">Gli elementi di gravità generalmente superiori richiedono l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="e6671-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="e6671-194">Uno dei valori seguenti: *informativo*, *basso*, \* medio e *alto*.</span><span class="sxs-lookup"><span data-stu-id="e6671-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="e6671-195">Medio</span><span class="sxs-lookup"><span data-stu-id="e6671-195">Medium</span></span>
<span data-ttu-id="e6671-196">Tag</span><span class="sxs-lookup"><span data-stu-id="e6671-196">tags</span></span> | <span data-ttu-id="e6671-197">Matrice di tag personalizzati associati a un evento imprevisto, ad esempio per contrassegnare un gruppo di incidenti con una caratteristica comune.</span><span class="sxs-lookup"><span data-stu-id="e6671-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="e6671-198">avvisi</span><span class="sxs-lookup"><span data-stu-id="e6671-198">alerts</span></span> | <span data-ttu-id="e6671-199">Matrice contenente tutti gli avvisi relativi all'incidente, oltre ad altre informazioni, ad esempio la gravità, le entità coinvolte nell'avviso e l'origine degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="e6671-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="e6671-200">\[\] (vedere i dettagli sui campi di avviso riportati di seguito)</span><span class="sxs-lookup"><span data-stu-id="e6671-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="e6671-201">Avvisi dei metadati</span><span class="sxs-lookup"><span data-stu-id="e6671-201">Alerts metadata</span></span>

<span data-ttu-id="e6671-202">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="e6671-202">Field name</span></span> | <span data-ttu-id="e6671-203">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6671-203">Description</span></span> | <span data-ttu-id="e6671-204">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="e6671-204">Example value</span></span>
-|-|-
<span data-ttu-id="e6671-205">alertId</span><span class="sxs-lookup"><span data-stu-id="e6671-205">alertId</span></span> | <span data-ttu-id="e6671-206">Identificatore univoco per rappresentare l'avviso</span><span class="sxs-lookup"><span data-stu-id="e6671-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="e6671-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="e6671-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="e6671-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="e6671-208">incidentId</span></span> | <span data-ttu-id="e6671-209">Identificatore univoco per rappresentare l'evento anomalo a cui è associato questo avviso</span><span class="sxs-lookup"><span data-stu-id="e6671-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="e6671-210">924565</span><span class="sxs-lookup"><span data-stu-id="e6671-210">924565</span></span>
<span data-ttu-id="e6671-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="e6671-211">serviceSource</span></span> | <span data-ttu-id="e6671-212">Servizio da cui proviene l'avviso, ad esempio Microsoft Defender per endpoint, Microsoft cloud app Security, Microsoft Defender per Identity o Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6671-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="e6671-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="e6671-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="e6671-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="e6671-214">creationTime</span></span> | <span data-ttu-id="e6671-215">Ora in cui è stato creato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="e6671-215">Time when alert was first created.</span></span> | <span data-ttu-id="e6671-216">2020-09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="e6671-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="e6671-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="e6671-217">lastUpdatedTime</span></span> | <span data-ttu-id="e6671-218">Ora dell'ultimo aggiornamento dell'avviso nel backend.</span><span class="sxs-lookup"><span data-stu-id="e6671-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="e6671-219">2020-09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="e6671-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="e6671-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="e6671-220">resolvedTime</span></span> | <span data-ttu-id="e6671-221">Ora in cui l'avviso è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="e6671-221">Time when alert was resolved.</span></span> | <span data-ttu-id="e6671-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="e6671-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="e6671-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="e6671-223">firstActivity</span></span> | <span data-ttu-id="e6671-224">Ora in cui il primo avviso ha riferito che l'attività è stata aggiornata nel backend.</span><span class="sxs-lookup"><span data-stu-id="e6671-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="e6671-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="e6671-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="e6671-226">title</span><span class="sxs-lookup"><span data-stu-id="e6671-226">title</span></span> | <span data-ttu-id="e6671-227">Breve valore stringa di identificazione disponibile per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="e6671-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="e6671-228">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="e6671-228">Ransomware activity</span></span>
<span data-ttu-id="e6671-229">descrizione</span><span class="sxs-lookup"><span data-stu-id="e6671-229">description</span></span> | <span data-ttu-id="e6671-230">Valore stringa che descrive ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="e6671-230">String value describing each alert.</span></span> | <span data-ttu-id="e6671-231">La User2 (testUser2@contoso.com) ha modificato i file di 99 con più estensioni che terminano con la *scaricare* di estensione non comune.</span><span class="sxs-lookup"><span data-stu-id="e6671-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="e6671-232">Si tratta di un numero insolito di manipolazioni dei file ed è indicativo di un potenziale attacco ransomware.</span><span class="sxs-lookup"><span data-stu-id="e6671-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="e6671-233">Categoria</span><span class="sxs-lookup"><span data-stu-id="e6671-233">category</span></span> | <span data-ttu-id="e6671-234">Visualizzazione e visualizzazione numerica di quanto l'attacco è progredito lungo la catena di Kill.</span><span class="sxs-lookup"><span data-stu-id="e6671-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="e6671-235">Allineato al [quadro di&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="e6671-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="e6671-236">Impatto</span><span class="sxs-lookup"><span data-stu-id="e6671-236">Impact</span></span>
<span data-ttu-id="e6671-237">stato</span><span class="sxs-lookup"><span data-stu-id="e6671-237">status</span></span> | <span data-ttu-id="e6671-238">Categorizzare gli avvisi (come *nuovi*, *attivi* o *risolti*).</span><span class="sxs-lookup"><span data-stu-id="e6671-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="e6671-239">Può essere utile per organizzare e gestire la risposta agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="e6671-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="e6671-240">Nuova</span><span class="sxs-lookup"><span data-stu-id="e6671-240">New</span></span>
<span data-ttu-id="e6671-241">gravità</span><span class="sxs-lookup"><span data-stu-id="e6671-241">severity</span></span> | <span data-ttu-id="e6671-242">Indica il possibile impatto sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="e6671-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="e6671-243">Maggiore è la gravità più grande è l'impatto.</span><span class="sxs-lookup"><span data-stu-id="e6671-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="e6671-244">Gli elementi di gravità generalmente superiori richiedono l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="e6671-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="e6671-245">Uno dei valori seguenti: *informativo*, *basso*, \* medio e *alto*.</span><span class="sxs-lookup"><span data-stu-id="e6671-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="e6671-246">Medio</span><span class="sxs-lookup"><span data-stu-id="e6671-246">Medium</span></span>
<span data-ttu-id="e6671-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="e6671-247">investigationId</span></span> | <span data-ttu-id="e6671-248">ID analisi automatizzato attivato da questo avviso.</span><span class="sxs-lookup"><span data-stu-id="e6671-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="e6671-249">1234</span><span class="sxs-lookup"><span data-stu-id="e6671-249">1234</span></span>
<span data-ttu-id="e6671-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="e6671-250">investigationState</span></span> | <span data-ttu-id="e6671-251">Informazioni sullo stato corrente dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="e6671-251">Information on the investigation's current status.</span></span> <span data-ttu-id="e6671-252">Uno dei valori seguenti: *Unknown*, *terminated*, *SuccessfullyRemediated*, *benigne*, *failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, PartiallyInvestigated *, TerminatedByUser*, *TerminatedBySystem*, *queued*, *InnerFailure*, *PreexistingAlert*, *unsupportos*, *UnsupportedAlertType*, *SuppressedAlert*. </span><span class="sxs-lookup"><span data-stu-id="e6671-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="e6671-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="e6671-253">UnsupportedAlertType</span></span>
<span data-ttu-id="e6671-254">classificazione</span><span class="sxs-lookup"><span data-stu-id="e6671-254">classification</span></span> | <span data-ttu-id="e6671-255">Specifica per l'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="e6671-255">The specification for the incident.</span></span> <span data-ttu-id="e6671-256">I valori delle proprietà sono: *Unknown*, *FalsePositive*, *TruePositive* o *null*</span><span class="sxs-lookup"><span data-stu-id="e6671-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="e6671-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="e6671-257">Unknown</span></span>
<span data-ttu-id="e6671-258">determinazione</span><span class="sxs-lookup"><span data-stu-id="e6671-258">determination</span></span> | <span data-ttu-id="e6671-259">Specifica la determinazione dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="e6671-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="e6671-260">I valori delle proprietà sono: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* o  *null*</span><span class="sxs-lookup"><span data-stu-id="e6671-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="e6671-261">APT</span><span class="sxs-lookup"><span data-stu-id="e6671-261">Apt</span></span>
<span data-ttu-id="e6671-262">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="e6671-262">assignedTo</span></span> | <span data-ttu-id="e6671-263">Proprietario dell'evento Incident oppure *null* se non è stato assegnato alcun proprietario.</span><span class="sxs-lookup"><span data-stu-id="e6671-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="e6671-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e6671-264">secop2@contoso.com</span></span>
<span data-ttu-id="e6671-265">actorname</span><span class="sxs-lookup"><span data-stu-id="e6671-265">actorName</span></span> | <span data-ttu-id="e6671-266">Il gruppo di attività, se presente, associato all'avviso.</span><span class="sxs-lookup"><span data-stu-id="e6671-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="e6671-267">BORO</span><span class="sxs-lookup"><span data-stu-id="e6671-267">BORON</span></span>
<span data-ttu-id="e6671-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="e6671-268">threatFamilyName</span></span> | <span data-ttu-id="e6671-269">Famiglia di minacce associata all'avviso.</span><span class="sxs-lookup"><span data-stu-id="e6671-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="e6671-270">null</span><span class="sxs-lookup"><span data-stu-id="e6671-270">null</span></span>
<span data-ttu-id="e6671-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="e6671-271">mitreTechniques</span></span> | <span data-ttu-id="e6671-272">Le tecniche di attacco, allineate al [mitra&CK](https://attack.mitre.org/)™ Framework.</span><span class="sxs-lookup"><span data-stu-id="e6671-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="e6671-273">dispositivi</span><span class="sxs-lookup"><span data-stu-id="e6671-273">devices</span></span> | <span data-ttu-id="e6671-274">Tutti i dispositivi in cui sono stati inviati avvisi relativi all'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="e6671-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="e6671-275">\[\] (vedere dettagli sui campi entità seguenti)</span><span class="sxs-lookup"><span data-stu-id="e6671-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="e6671-276">Formato dispositivo</span><span class="sxs-lookup"><span data-stu-id="e6671-276">Device format</span></span>

<span data-ttu-id="e6671-277">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="e6671-277">Field name</span></span> | <span data-ttu-id="e6671-278">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6671-278">Description</span></span> | <span data-ttu-id="e6671-279">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="e6671-279">Example value</span></span>
-|-|-
<span data-ttu-id="e6671-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="e6671-280">DeviceId</span></span> | <span data-ttu-id="e6671-281">ID del dispositivo come indicato in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="e6671-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="e6671-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="e6671-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="e6671-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="e6671-283">aadDeviceId</span></span> |  <span data-ttu-id="e6671-284">ID del dispositivo come indicato in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="e6671-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="e6671-285">Disponibile solo per i dispositivi appartenenti al dominio.</span><span class="sxs-lookup"><span data-stu-id="e6671-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="e6671-286">null</span><span class="sxs-lookup"><span data-stu-id="e6671-286">null</span></span>
<span data-ttu-id="e6671-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="e6671-287">deviceDnsName</span></span> | <span data-ttu-id="e6671-288">Il nome di dominio completo per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6671-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="e6671-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e6671-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="e6671-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="e6671-290">osPlatform</span></span> | <span data-ttu-id="e6671-291">Piattaforma del sistema operativo in cui è in esecuzione il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6671-291">The OS platform the device is running.</span></span>| <span data-ttu-id="e6671-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="e6671-292">WindowsServer2016</span></span>
<span data-ttu-id="e6671-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="e6671-293">osBuild</span></span> | <span data-ttu-id="e6671-294">La versione di compilazione per il sistema operativo in cui è in esecuzione il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6671-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="e6671-295">14393</span><span class="sxs-lookup"><span data-stu-id="e6671-295">14393</span></span>
<span data-ttu-id="e6671-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="e6671-296">rbacGroupName</span></span> | <span data-ttu-id="e6671-297">Il gruppo di [controllo di accesso basato sui ruoli](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) associato al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6671-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="e6671-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="e6671-298">WDATP-Ring0</span></span>
<span data-ttu-id="e6671-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="e6671-299">firstSeen</span></span> | <span data-ttu-id="e6671-300">Ora in cui è stato visualizzato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6671-300">Time when device was first seen.</span></span> | <span data-ttu-id="e6671-301">2020-02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="e6671-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="e6671-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="e6671-302">healthStatus</span></span> | <span data-ttu-id="e6671-303">Lo stato di integrità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6671-303">The health state of the device.</span></span> | <span data-ttu-id="e6671-304">Attivazione</span><span class="sxs-lookup"><span data-stu-id="e6671-304">Active</span></span>
<span data-ttu-id="e6671-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="e6671-305">riskScore</span></span> | <span data-ttu-id="e6671-306">Il Punteggio di rischio per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6671-306">The risk score for the  device.</span></span> | <span data-ttu-id="e6671-307">Alto</span><span class="sxs-lookup"><span data-stu-id="e6671-307">High</span></span>
<span data-ttu-id="e6671-308">entità</span><span class="sxs-lookup"><span data-stu-id="e6671-308">entities</span></span> | <span data-ttu-id="e6671-309">Tutte le entità che sono state identificate come parte di un determinato avviso o che sono correlate a.</span><span class="sxs-lookup"><span data-stu-id="e6671-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="e6671-310">\[\] (vedere dettagli sui campi entità seguenti)</span><span class="sxs-lookup"><span data-stu-id="e6671-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="e6671-311">Formato entità</span><span class="sxs-lookup"><span data-stu-id="e6671-311">Entity Format</span></span>

<span data-ttu-id="e6671-312">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="e6671-312">Field name</span></span> | <span data-ttu-id="e6671-313">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6671-313">Description</span></span> | <span data-ttu-id="e6671-314">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="e6671-314">Example value</span></span>
-|-|-
<span data-ttu-id="e6671-315">entityType</span><span class="sxs-lookup"><span data-stu-id="e6671-315">entityType</span></span> | <span data-ttu-id="e6671-316">Entità che sono state identificate come parte di un determinato avviso o che sono correlate.</span><span class="sxs-lookup"><span data-stu-id="e6671-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="e6671-317">I valori delle proprietà sono: *User*, *IP*, *URL*, *file*, *Process*, *Mailbox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="e6671-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="e6671-318">Utente</span><span class="sxs-lookup"><span data-stu-id="e6671-318">User</span></span>
<span data-ttu-id="e6671-319">SHA1</span><span class="sxs-lookup"><span data-stu-id="e6671-319">sha1</span></span> | <span data-ttu-id="e6671-320">Disponibile se entityType è *file*.</span><span class="sxs-lookup"><span data-stu-id="e6671-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="e6671-321">Hash del file per gli avvisi associati a un file o a un processo.</span><span class="sxs-lookup"><span data-stu-id="e6671-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="e6671-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="e6671-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="e6671-323">SHA256</span><span class="sxs-lookup"><span data-stu-id="e6671-323">sha256</span></span> | <span data-ttu-id="e6671-324">Disponibile se entityType è *file*.</span><span class="sxs-lookup"><span data-stu-id="e6671-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="e6671-325">Hash del file per gli avvisi associati a un file o a un processo.</span><span class="sxs-lookup"><span data-stu-id="e6671-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="e6671-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="e6671-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="e6671-327">fileName</span><span class="sxs-lookup"><span data-stu-id="e6671-327">fileName</span></span> | <span data-ttu-id="e6671-328">Disponibile se entityType è *file*.</span><span class="sxs-lookup"><span data-stu-id="e6671-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="e6671-329">Nome del file per gli avvisi associati a un file o a un processo</span><span class="sxs-lookup"><span data-stu-id="e6671-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="e6671-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="e6671-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="e6671-331">filePath</span><span class="sxs-lookup"><span data-stu-id="e6671-331">filePath</span></span> | <span data-ttu-id="e6671-332">Disponibile se entityType è *file*.</span><span class="sxs-lookup"><span data-stu-id="e6671-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="e6671-333">Percorso del file per gli avvisi associati a un file o a un processo</span><span class="sxs-lookup"><span data-stu-id="e6671-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="e6671-334">C: \\ \ agent_work_temp \deploy\system\2020-09-06 12_14_54 \ out</span><span class="sxs-lookup"><span data-stu-id="e6671-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="e6671-335">processId</span><span class="sxs-lookup"><span data-stu-id="e6671-335">processId</span></span> | <span data-ttu-id="e6671-336">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="e6671-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e6671-337">24348</span><span class="sxs-lookup"><span data-stu-id="e6671-337">24348</span></span>
<span data-ttu-id="e6671-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="e6671-338">processCommandLine</span></span> | <span data-ttu-id="e6671-339">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="e6671-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e6671-340">"Il file è pronto per il download \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="e6671-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="e6671-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="e6671-341">processCreationTime</span></span> | <span data-ttu-id="e6671-342">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="e6671-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e6671-343">2020-07-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="e6671-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="e6671-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="e6671-344">parentProcessId</span></span> | <span data-ttu-id="e6671-345">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="e6671-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e6671-346">16840</span><span class="sxs-lookup"><span data-stu-id="e6671-346">16840</span></span>
<span data-ttu-id="e6671-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="e6671-347">parentProcessCreationTime</span></span> | <span data-ttu-id="e6671-348">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="e6671-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="e6671-349">2020-07-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="e6671-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="e6671-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="e6671-350">ipAddress</span></span> | <span data-ttu-id="e6671-351">Disponibile se entityType è *IP*.</span><span class="sxs-lookup"><span data-stu-id="e6671-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="e6671-352">Indirizzo IP per gli avvisi associati agli eventi di rete, ad esempio *la comunicazione a una destinazione di rete dannosa*.</span><span class="sxs-lookup"><span data-stu-id="e6671-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="e6671-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="e6671-353">62.216.203.204</span></span>
<span data-ttu-id="e6671-354">URL</span><span class="sxs-lookup"><span data-stu-id="e6671-354">url</span></span> | <span data-ttu-id="e6671-355">Disponibile se entityType è l' *URL*.</span><span class="sxs-lookup"><span data-stu-id="e6671-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="e6671-356">URL per gli avvisi associati a eventi di rete, ad esempio *la comunicazione a una destinazione di rete dannosa*.</span><span class="sxs-lookup"><span data-stu-id="e6671-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="e6671-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="e6671-357">down.esales360.cn</span></span>
<span data-ttu-id="e6671-358">accountName</span><span class="sxs-lookup"><span data-stu-id="e6671-358">accountName</span></span> | <span data-ttu-id="e6671-359">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="e6671-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="e6671-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="e6671-360">testUser2</span></span>
<span data-ttu-id="e6671-361">domainName</span><span class="sxs-lookup"><span data-stu-id="e6671-361">domainName</span></span> | <span data-ttu-id="e6671-362">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="e6671-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="e6671-363">Europe. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="e6671-363">europe.corp.contoso</span></span>
<span data-ttu-id="e6671-364">userSid</span><span class="sxs-lookup"><span data-stu-id="e6671-364">userSid</span></span> | <span data-ttu-id="e6671-365">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="e6671-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="e6671-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="e6671-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="e6671-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="e6671-367">aadUserId</span></span> | <span data-ttu-id="e6671-368">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="e6671-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="e6671-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="e6671-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="e6671-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="e6671-370">userPrincipalName</span></span> | <span data-ttu-id="e6671-371">Disponibile se EntityType è la cassetta postale *dell'utente* /  / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="e6671-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="e6671-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e6671-372">testUser2@contoso.com</span></span>
<span data-ttu-id="e6671-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="e6671-373">mailboxDisplayName</span></span> | <span data-ttu-id="e6671-374">Disponibile se entityType è una *cassetta postale*.</span><span class="sxs-lookup"><span data-stu-id="e6671-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="e6671-375">test User2</span><span class="sxs-lookup"><span data-stu-id="e6671-375">test User2</span></span>
<span data-ttu-id="e6671-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="e6671-376">mailboxAddress</span></span> | <span data-ttu-id="e6671-377">Disponibile se EntityType è la cassetta postale *dell'utente* /  / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="e6671-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="e6671-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e6671-378">testUser2@contoso.com</span></span>
<span data-ttu-id="e6671-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="e6671-379">clusterBy</span></span> | <span data-ttu-id="e6671-380">Disponibile se entityType è  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="e6671-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="e6671-381">Soggetto P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="e6671-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="e6671-382">mittente</span><span class="sxs-lookup"><span data-stu-id="e6671-382">sender</span></span> | <span data-ttu-id="e6671-383">Disponibile se EntityType è la cassetta postale *dell'utente* /  / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="e6671-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="e6671-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="e6671-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="e6671-385">destinatario</span><span class="sxs-lookup"><span data-stu-id="e6671-385">recipient</span></span> | <span data-ttu-id="e6671-386">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="e6671-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="e6671-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e6671-387">testUser2@contoso.com</span></span>
<span data-ttu-id="e6671-388">subject</span><span class="sxs-lookup"><span data-stu-id="e6671-388">subject</span></span> | <span data-ttu-id="e6671-389">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="e6671-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="e6671-390">\[\]Attenzione esterna</span><span class="sxs-lookup"><span data-stu-id="e6671-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="e6671-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="e6671-391">deliveryAction</span></span> | <span data-ttu-id="e6671-392">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="e6671-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="e6671-393">Consegnato</span><span class="sxs-lookup"><span data-stu-id="e6671-393">Delivered</span></span>
<span data-ttu-id="e6671-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="e6671-394">securityGroupId</span></span> | <span data-ttu-id="e6671-395">Disponibile se entityType è  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="e6671-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="e6671-396">301c47c8-e15f-4059-AB09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="e6671-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="e6671-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="e6671-397">securityGroupName</span></span> | <span data-ttu-id="e6671-398">Disponibile se entityType è  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="e6671-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="e6671-399">Operatori di configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="e6671-399">Network Configuration Operators</span></span>
<span data-ttu-id="e6671-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="e6671-400">registryHive</span></span> | <span data-ttu-id="e6671-401">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="e6671-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="e6671-402">\_computer locale di HKEY \_</span><span class="sxs-lookup"><span data-stu-id="e6671-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="e6671-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="e6671-403">registryKey</span></span> | <span data-ttu-id="e6671-404">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="e6671-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="e6671-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="e6671-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="e6671-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="e6671-406">registryValueType</span></span> | <span data-ttu-id="e6671-407">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="e6671-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="e6671-408">Stringa</span><span class="sxs-lookup"><span data-stu-id="e6671-408">String</span></span>
<span data-ttu-id="e6671-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="e6671-409">registryValue</span></span> | <span data-ttu-id="e6671-410">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="e6671-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="e6671-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="e6671-411">31-00-00-00</span></span>
<span data-ttu-id="e6671-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="e6671-412">deviceId</span></span> | <span data-ttu-id="e6671-413">L'ID, se presente, del dispositivo relativo all'entità.</span><span class="sxs-lookup"><span data-stu-id="e6671-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="e6671-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="e6671-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="e6671-415">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6671-415">Example</span></span>

<span data-ttu-id="e6671-416">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="e6671-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="e6671-417">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="e6671-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="e6671-418">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="e6671-418">Related articles</span></span>

- [<span data-ttu-id="e6671-419">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6671-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e6671-420">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="e6671-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="e6671-421">Informazioni sui codici di errore</span><span class="sxs-lookup"><span data-stu-id="e6671-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="e6671-422">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="e6671-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e6671-423">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="e6671-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="e6671-424">Aggiornare l'API Incident</span><span class="sxs-lookup"><span data-stu-id="e6671-424">Update incident API</span></span>](api-update-incidents.md)
