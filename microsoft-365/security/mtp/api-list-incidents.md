---
title: API degli incidenti di elenco in Microsoft Threat Protection
description: Informazioni su come elencare le API degli incidenti in Microsoft Threat Protection
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
ms.openlocfilehash: 9defc9c0f8fa04e019c0108ca0f4111de54edb5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195391"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="bd80f-104">API degli incidenti di elenco in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bd80f-104">List incidents API in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bd80f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bd80f-105">**Applies to:**</span></span>

- <span data-ttu-id="bd80f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bd80f-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd80f-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="bd80f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bd80f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="bd80f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="bd80f-109">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="bd80f-109">API description</span></span>

<span data-ttu-id="bd80f-110">L'API Incident consente di ordinare gli eventi non consentiti per definire la priorità e creare una risposta Cybersecurity informata.</span><span class="sxs-lookup"><span data-stu-id="bd80f-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="bd80f-111">Espone una raccolta di operazioni non consentite che sono state contrassegnate da dispositivi, account di posta elettronica e utenti della rete, all'interno dell'intervallo di tempo specificato nel criterio di conservazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="bd80f-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="bd80f-112">Gli incidenti più recenti vengono visualizzati all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd80f-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="bd80f-113">Ogni evento Incident contiene una matrice di avvisi correlati e le entità correlate.</span><span class="sxs-lookup"><span data-stu-id="bd80f-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="bd80f-114">L'API supporta gli operatori **OData** seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd80f-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="bd80f-115">```$filter``` on: ```lastUpdateTime``` , ```createdTime``` ```status``` e ```assignedTo``` Properties.</span><span class="sxs-lookup"><span data-stu-id="bd80f-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="bd80f-116">```$top``` con valore massimo di **100**</span><span class="sxs-lookup"><span data-stu-id="bd80f-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="bd80f-117">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="bd80f-117">Limitations</span></span>

1. <span data-ttu-id="bd80f-118">La dimensione massima della pagina è di **100 incidenti**.</span><span class="sxs-lookup"><span data-stu-id="bd80f-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="bd80f-119">La frequenza massima delle richieste è di **50 chiamate al minuto** e **1500 chiamate all'ora**.</span><span class="sxs-lookup"><span data-stu-id="bd80f-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="bd80f-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bd80f-120">Permissions</span></span>

<span data-ttu-id="bd80f-121">Per chiamare l'API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="bd80f-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bd80f-122">Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access Microsoft Threat Protection Apis](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="bd80f-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="bd80f-123">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-123">Permission type</span></span> |   <span data-ttu-id="bd80f-124">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-124">Permission</span></span>  |   <span data-ttu-id="bd80f-125">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bd80f-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bd80f-126">Applicazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-126">Application</span></span> |   <span data-ttu-id="bd80f-127">Incident. Read. All</span><span class="sxs-lookup"><span data-stu-id="bd80f-127">Incident.Read.All</span></span> | <span data-ttu-id="bd80f-128">' Leggi tutti gli eventi non consentiti '</span><span class="sxs-lookup"><span data-stu-id="bd80f-128">'Read all incidents'</span></span>
<span data-ttu-id="bd80f-129">Applicazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-129">Application</span></span> |   <span data-ttu-id="bd80f-130">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="bd80f-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="bd80f-131">' Leggi e Scrivi tutti gli incidenti '</span><span class="sxs-lookup"><span data-stu-id="bd80f-131">'Read and write all incidents'</span></span>
<span data-ttu-id="bd80f-132">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="bd80f-132">Delegated (work or school account)</span></span> | <span data-ttu-id="bd80f-133">Evento Incident. Read</span><span class="sxs-lookup"><span data-stu-id="bd80f-133">Incident.Read</span></span> | <span data-ttu-id="bd80f-134">' Leggi gli incidenti '</span><span class="sxs-lookup"><span data-stu-id="bd80f-134">'Read incidents'</span></span>
<span data-ttu-id="bd80f-135">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="bd80f-135">Delegated (work or school account)</span></span> | <span data-ttu-id="bd80f-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="bd80f-136">Incident.ReadWrite</span></span> | <span data-ttu-id="bd80f-137">' Operazioni di lettura e scrittura degli incidenti '</span><span class="sxs-lookup"><span data-stu-id="bd80f-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="bd80f-138">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="bd80f-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="bd80f-139">L'utente deve disporre dell'autorizzazione di visualizzazione per gli eventi non consentiti nel portale.</span><span class="sxs-lookup"><span data-stu-id="bd80f-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="bd80f-140">La risposta includerà solo gli incidenti a cui l'utente è esposto.</span><span class="sxs-lookup"><span data-stu-id="bd80f-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="bd80f-141">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="bd80f-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="bd80f-142">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="bd80f-142">Request headers</span></span>

<span data-ttu-id="bd80f-143">Name</span><span class="sxs-lookup"><span data-stu-id="bd80f-143">Name</span></span> | <span data-ttu-id="bd80f-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="bd80f-144">Type</span></span> | <span data-ttu-id="bd80f-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd80f-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="bd80f-146">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-146">Authorization</span></span> | <span data-ttu-id="bd80f-147">Stringa</span><span class="sxs-lookup"><span data-stu-id="bd80f-147">String</span></span> | <span data-ttu-id="bd80f-148">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="bd80f-148">Bearer {token}.</span></span> <span data-ttu-id="bd80f-149">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="bd80f-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="bd80f-150">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="bd80f-150">Request body</span></span>
<span data-ttu-id="bd80f-151">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="bd80f-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="bd80f-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="bd80f-152">Response</span></span>
<span data-ttu-id="bd80f-153">Se l'operazione ha esito positivo, questo metodo restituisce 200 OK e un elenco di [operazioni](api-incident.md) non consentite nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="bd80f-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="bd80f-154">Mapping dello schema</span><span class="sxs-lookup"><span data-stu-id="bd80f-154">Schema mapping</span></span>

| <span data-ttu-id="bd80f-155">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="bd80f-155">Field name</span></span>                                | <span data-ttu-id="bd80f-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd80f-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="bd80f-157">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="bd80f-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="bd80f-158">**Metadati degli incidenti**</span><span class="sxs-lookup"><span data-stu-id="bd80f-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="bd80f-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="bd80f-159">incidentId</span></span>                                | <span data-ttu-id="bd80f-160">Identificatore univoco che rappresenta l'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="bd80f-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="bd80f-161">924565</span><span class="sxs-lookup"><span data-stu-id="bd80f-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="bd80f-162">redirectIncidentId</span></span>                        | <span data-ttu-id="bd80f-163">Viene popolato solo nel caso in cui un evento Incident venga raggruppato insieme a un altro incidente, come parte della logica di elaborazione degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="bd80f-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="bd80f-164">924569</span><span class="sxs-lookup"><span data-stu-id="bd80f-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-165">evento incidentname</span><span class="sxs-lookup"><span data-stu-id="bd80f-165">incidentName</span></span>                              | <span data-ttu-id="bd80f-166">Valore stringa disponibile per ogni evento Incident.</span><span class="sxs-lookup"><span data-stu-id="bd80f-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="bd80f-167">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="bd80f-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="bd80f-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="bd80f-168">createdTime</span></span>                               | <span data-ttu-id="bd80f-169">Ora in cui è stato creato l'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="bd80f-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="bd80f-170">2020-09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="bd80f-171">lastUpdateTime</span></span>                            | <span data-ttu-id="bd80f-172">Data e ora dell'ultimo aggiornamento dell'evento in back-end.</span><span class="sxs-lookup"><span data-stu-id="bd80f-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="bd80f-173">Questo campo può essere utilizzato quando si imposta il parametro request per l'intervallo di tempo in cui vengono recuperati gli eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="bd80f-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="bd80f-174">2020-09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="bd80f-175">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="bd80f-175">assignedTo</span></span>                                | <span data-ttu-id="bd80f-176">Proprietario dell'evento Incident oppure *null* se non è stato assegnato alcun proprietario.</span><span class="sxs-lookup"><span data-stu-id="bd80f-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="bd80f-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd80f-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="bd80f-178">classificazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-178">classification</span></span>                            | <span data-ttu-id="bd80f-179">Specifica per l'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="bd80f-179">The specification for the incident.</span></span> <span data-ttu-id="bd80f-180">I valori delle proprietà sono: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="bd80f-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="bd80f-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="bd80f-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="bd80f-182">determinazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-182">determination</span></span>                             | <span data-ttu-id="bd80f-183">Specifica la determinazione dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="bd80f-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="bd80f-184">I valori delle proprietà sono: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other*</span><span class="sxs-lookup"><span data-stu-id="bd80f-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="bd80f-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="bd80f-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-186">stato</span><span class="sxs-lookup"><span data-stu-id="bd80f-186">status</span></span>                                    | <span data-ttu-id="bd80f-187">Categorizzare gli incidenti (come *attivi*o *risolti*).</span><span class="sxs-lookup"><span data-stu-id="bd80f-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="bd80f-188">In questo modo è possibile organizzare e gestire la risposta a eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="bd80f-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="bd80f-189">Attivazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-190">gravità</span><span class="sxs-lookup"><span data-stu-id="bd80f-190">severity</span></span>                                  | <span data-ttu-id="bd80f-191">Indica il possibile impatto sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="bd80f-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="bd80f-192">Maggiore è la gravità più grande è l'impatto.</span><span class="sxs-lookup"><span data-stu-id="bd80f-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="bd80f-193">Gli elementi di gravità generalmente superiori richiedono l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="bd80f-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="bd80f-194">Uno dei valori seguenti: *informativo*, *basso*, \* medio e *alto*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="bd80f-195">Media</span><span class="sxs-lookup"><span data-stu-id="bd80f-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-196">Tag</span><span class="sxs-lookup"><span data-stu-id="bd80f-196">tags</span></span>                                      | <span data-ttu-id="bd80f-197">Matrice di tag personalizzati associati a un evento imprevisto, ad esempio per contrassegnare un gruppo di incidenti con una caratteristica comune.</span><span class="sxs-lookup"><span data-stu-id="bd80f-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-198">avvisi</span><span class="sxs-lookup"><span data-stu-id="bd80f-198">alerts</span></span>                                    | <span data-ttu-id="bd80f-199">Matrice di tutti gli avvisi relativi all'incidente e ad altre informazioni, ad esempio la gravità, le entità che sono state coinvolte nell'avviso, l'origine degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="bd80f-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-200">\[\] (vedere i dettagli sui campi di avviso riportati di seguito)</span><span class="sxs-lookup"><span data-stu-id="bd80f-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="bd80f-201">**Avvisi dei metadati**</span><span class="sxs-lookup"><span data-stu-id="bd80f-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="bd80f-202">alertId</span><span class="sxs-lookup"><span data-stu-id="bd80f-202">alertId</span></span>                                   | <span data-ttu-id="bd80f-203">Identificatore univoco per rappresentare l'avviso</span><span class="sxs-lookup"><span data-stu-id="bd80f-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="bd80f-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="bd80f-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-205">incidentId</span><span class="sxs-lookup"><span data-stu-id="bd80f-205">incidentId</span></span>                                | <span data-ttu-id="bd80f-206">Identificatore univoco per rappresentare l'evento anomalo a cui è associato questo avviso</span><span class="sxs-lookup"><span data-stu-id="bd80f-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="bd80f-207">924565</span><span class="sxs-lookup"><span data-stu-id="bd80f-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-208">serviceSource</span><span class="sxs-lookup"><span data-stu-id="bd80f-208">serviceSource</span></span>                             | <span data-ttu-id="bd80f-209">Servizio da cui proviene l'avviso, ad esempio Microsoft Defender ATP, Microsoft cloud app Security, Azure ATP o Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="bd80f-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="bd80f-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="bd80f-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="bd80f-211">creationTime</span></span>                              | <span data-ttu-id="bd80f-212">Ora in cui è stato creato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="bd80f-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="bd80f-213">2020-09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="bd80f-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="bd80f-215">Ora dell'ultimo aggiornamento dell'avviso nel backend.</span><span class="sxs-lookup"><span data-stu-id="bd80f-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="bd80f-216">2020-09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-217">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="bd80f-217">resolvedTime</span></span>                              | <span data-ttu-id="bd80f-218">Ora in cui l'avviso è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="bd80f-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="bd80f-219">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="bd80f-220">firstActivity</span></span>                             | <span data-ttu-id="bd80f-221">Ora in cui il primo avviso ha riferito che l'attività è stata aggiornata nel backend.</span><span class="sxs-lookup"><span data-stu-id="bd80f-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="bd80f-222">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-223">title</span><span class="sxs-lookup"><span data-stu-id="bd80f-223">title</span></span>                                     | <span data-ttu-id="bd80f-224">Breve valore stringa di identificazione disponibile per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="bd80f-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-225">Attività ransomware</span><span class="sxs-lookup"><span data-stu-id="bd80f-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="bd80f-226">descrizione</span><span class="sxs-lookup"><span data-stu-id="bd80f-226">description</span></span>                               | <span data-ttu-id="bd80f-227">Valore stringa che descrive ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="bd80f-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="bd80f-228">La User2 (testUser2@contoso.com) ha modificato i file di 99 con più estensioni che terminano con la *scaricare*di estensione non comune.</span><span class="sxs-lookup"><span data-stu-id="bd80f-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="bd80f-229">Si tratta di un numero insolito di manipolazioni dei file ed è indicativo di un potenziale attacco ransomware.</span><span class="sxs-lookup"><span data-stu-id="bd80f-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="bd80f-230">Categoria</span><span class="sxs-lookup"><span data-stu-id="bd80f-230">category</span></span>                                  | <span data-ttu-id="bd80f-231">Visualizzazione e visualizzazione numerica di quanto l'attacco è progredito lungo la catena di Kill.</span><span class="sxs-lookup"><span data-stu-id="bd80f-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="bd80f-232">Allineato al [quadro di&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="bd80f-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="bd80f-233">Impatto</span><span class="sxs-lookup"><span data-stu-id="bd80f-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-234">stato</span><span class="sxs-lookup"><span data-stu-id="bd80f-234">status</span></span>                                    | <span data-ttu-id="bd80f-235">Categorizzare gli avvisi (come *nuovi*, *attivi*o *risolti*).</span><span class="sxs-lookup"><span data-stu-id="bd80f-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="bd80f-236">In questo modo è possibile organizzare e gestire la risposta agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="bd80f-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="bd80f-237">Nuova</span><span class="sxs-lookup"><span data-stu-id="bd80f-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="bd80f-238">gravità</span><span class="sxs-lookup"><span data-stu-id="bd80f-238">severity</span></span>                                  | <span data-ttu-id="bd80f-239">Indica il possibile impatto sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="bd80f-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="bd80f-240">Maggiore è la gravità più grande è l'impatto.</span><span class="sxs-lookup"><span data-stu-id="bd80f-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="bd80f-241">Gli elementi di gravità generalmente superiori richiedono l'attenzione più immediata.</span><span class="sxs-lookup"><span data-stu-id="bd80f-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="bd80f-242">Uno dei valori seguenti: *informativo*, *basso*, \* medio e *alto*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="bd80f-243">Media</span><span class="sxs-lookup"><span data-stu-id="bd80f-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-244">investigationId</span><span class="sxs-lookup"><span data-stu-id="bd80f-244">investigationId</span></span>                           | <span data-ttu-id="bd80f-245">ID analisi automatizzato attivato da questo avviso.</span><span class="sxs-lookup"><span data-stu-id="bd80f-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="bd80f-246">1234</span><span class="sxs-lookup"><span data-stu-id="bd80f-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="bd80f-247">investigationState</span></span>                        | <span data-ttu-id="bd80f-248">Informazioni sullo stato corrente dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="bd80f-248">Information on the investigation's current status.</span></span> <span data-ttu-id="bd80f-249">Uno dei seguenti: *Unknown*, *terminated*, *SuccessfullyRemediated*, *benigne*, *failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, PartiallyInvestigated *, TerminatedByUser*, *TerminatedBySystem*, *queued*, *InnerFailure*, *PreexistingAlert*, *unsupportos*, *UnsupportedAlertType*, *SuppressedAlert*. *PartiallyInvestigated*</span><span class="sxs-lookup"><span data-stu-id="bd80f-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="bd80f-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="bd80f-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-251">classificazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-251">classification</span></span>                            | <span data-ttu-id="bd80f-252">Specifica per l'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="bd80f-252">The specification for the incident.</span></span> <span data-ttu-id="bd80f-253">I valori delle proprietà sono: *Unknown*, *FalsePositive*, *TruePositive* o *null*</span><span class="sxs-lookup"><span data-stu-id="bd80f-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="bd80f-254">Unknown</span><span class="sxs-lookup"><span data-stu-id="bd80f-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="bd80f-255">determinazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-255">determination</span></span>                             | <span data-ttu-id="bd80f-256">Specifica la determinazione dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="bd80f-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="bd80f-257">I valori delle proprietà sono: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* o  *null*</span><span class="sxs-lookup"><span data-stu-id="bd80f-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="bd80f-258">APT</span><span class="sxs-lookup"><span data-stu-id="bd80f-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="bd80f-259">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="bd80f-259">assignedTo</span></span>                                | <span data-ttu-id="bd80f-260">Proprietario dell'evento Incident oppure *null* se non è stato assegnato alcun proprietario.</span><span class="sxs-lookup"><span data-stu-id="bd80f-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="bd80f-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd80f-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="bd80f-262">actorname</span><span class="sxs-lookup"><span data-stu-id="bd80f-262">actorName</span></span>                                 | <span data-ttu-id="bd80f-263">Il gruppo di attività, se presente, associato all'avviso.</span><span class="sxs-lookup"><span data-stu-id="bd80f-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="bd80f-264">BORO</span><span class="sxs-lookup"><span data-stu-id="bd80f-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="bd80f-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="bd80f-265">threatFamilyName</span></span>                          | <span data-ttu-id="bd80f-266">Famiglia di minacce associata all'avviso.</span><span class="sxs-lookup"><span data-stu-id="bd80f-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="bd80f-267">null</span><span class="sxs-lookup"><span data-stu-id="bd80f-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="bd80f-268">mitreTechniques</span></span>                           | <span data-ttu-id="bd80f-269">Le tecniche di attacco, allineate al [mitra&CK](https://attack.mitre.org/)™ Framework.</span><span class="sxs-lookup"><span data-stu-id="bd80f-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-270">dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd80f-270">devices</span></span>                                   | <span data-ttu-id="bd80f-271">Tutti i dispositivi in cui sono stati inviati avvisi relativi all'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="bd80f-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-272">\[\] (vedere dettagli sui campi entità seguenti)</span><span class="sxs-lookup"><span data-stu-id="bd80f-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="bd80f-273">**Formato dispositivo**</span><span class="sxs-lookup"><span data-stu-id="bd80f-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="bd80f-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="bd80f-274">DeviceId</span></span>                                  | <span data-ttu-id="bd80f-275">ID del dispositivo come indicato in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="bd80f-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="bd80f-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="bd80f-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="bd80f-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="bd80f-277">aadDeviceId</span></span>                               |  <span data-ttu-id="bd80f-278">ID del dispositivo come indicato in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span><span class="sxs-lookup"><span data-stu-id="bd80f-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="bd80f-279">Disponibile solo per i dispositivi appartenenti al dominio.</span><span class="sxs-lookup"><span data-stu-id="bd80f-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="bd80f-280">null</span><span class="sxs-lookup"><span data-stu-id="bd80f-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="bd80f-281">deviceDnsName</span></span>                             | <span data-ttu-id="bd80f-282">Il nome di dominio completo per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="bd80f-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd80f-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="bd80f-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="bd80f-284">osPlatform</span></span>                                | <span data-ttu-id="bd80f-285">Piattaforma del sistema operativo in cui è in esecuzione il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="bd80f-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="bd80f-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="bd80f-287">osBuild</span></span>                                   | <span data-ttu-id="bd80f-288">La versione di compilazione per il sistema operativo in cui è in esecuzione il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="bd80f-289">14393</span><span class="sxs-lookup"><span data-stu-id="bd80f-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="bd80f-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="bd80f-290">rbacGroupName</span></span>                             | <span data-ttu-id="bd80f-291">Il gruppo di [controllo di accesso basato sui ruoli](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) associato al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="bd80f-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="bd80f-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="bd80f-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="bd80f-293">firstSeen</span></span>                                 | <span data-ttu-id="bd80f-294">Ora in cui è stato visualizzato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="bd80f-295">2020-02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="bd80f-296">healthStatus</span></span>                              | <span data-ttu-id="bd80f-297">Lo stato di integrità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="bd80f-298">Attivazione</span><span class="sxs-lookup"><span data-stu-id="bd80f-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="bd80f-299">riskScore</span></span>                                 | <span data-ttu-id="bd80f-300">Il Punteggio di rischio per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="bd80f-301">Fortemente</span><span class="sxs-lookup"><span data-stu-id="bd80f-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-302">entità</span><span class="sxs-lookup"><span data-stu-id="bd80f-302">entities</span></span>                                  | <span data-ttu-id="bd80f-303">Tutte le entità che sono state identificate come parte di un determinato avviso o che sono correlate a.</span><span class="sxs-lookup"><span data-stu-id="bd80f-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="bd80f-304">\[\] (vedere dettagli sui campi entità seguenti)</span><span class="sxs-lookup"><span data-stu-id="bd80f-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="bd80f-305">**Formato entità**</span><span class="sxs-lookup"><span data-stu-id="bd80f-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="bd80f-306">entityType</span><span class="sxs-lookup"><span data-stu-id="bd80f-306">entityType</span></span>                                | <span data-ttu-id="bd80f-307">Entità che sono state identificate come parte di un determinato avviso o che sono correlate.</span><span class="sxs-lookup"><span data-stu-id="bd80f-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="bd80f-308">I valori delle proprietà sono: *User*, *IP*, *URL*, *file*, *Process*, *Mailbox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="bd80f-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="bd80f-309">Utente</span><span class="sxs-lookup"><span data-stu-id="bd80f-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-310">SHA1</span><span class="sxs-lookup"><span data-stu-id="bd80f-310">sha1</span></span>                                      | <span data-ttu-id="bd80f-311">Disponibile se entityType è *file*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="bd80f-312">Hash del file per gli avvisi associati a un file o a un processo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="bd80f-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="bd80f-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="bd80f-314">SHA256</span><span class="sxs-lookup"><span data-stu-id="bd80f-314">sha256</span></span>                                    | <span data-ttu-id="bd80f-315">Disponibile se entityType è *file*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="bd80f-316">Hash del file per gli avvisi associati a un file o a un processo.</span><span class="sxs-lookup"><span data-stu-id="bd80f-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="bd80f-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="bd80f-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="bd80f-318">fileName</span><span class="sxs-lookup"><span data-stu-id="bd80f-318">fileName</span></span>                                  | <span data-ttu-id="bd80f-319">Disponibile se entityType è *file*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="bd80f-320">Nome del file per gli avvisi associati a un file o a un processo</span><span class="sxs-lookup"><span data-stu-id="bd80f-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="bd80f-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="bd80f-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-322">filePath</span><span class="sxs-lookup"><span data-stu-id="bd80f-322">filePath</span></span>                                  | <span data-ttu-id="bd80f-323">Disponibile se entityType è *file*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="bd80f-324">Percorso del file per gli avvisi associati a un file o a un processo</span><span class="sxs-lookup"><span data-stu-id="bd80f-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="bd80f-325">C: \\ \\ Agent \\ \\ \_ Work \\ \\ \_ temp \\ \\ deploy \_ System 2020-09-06 12 \_ 14 \_ 54 \\ \\ out</span><span class="sxs-lookup"><span data-stu-id="bd80f-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="bd80f-326">processId</span><span class="sxs-lookup"><span data-stu-id="bd80f-326">processId</span></span>                                 | <span data-ttu-id="bd80f-327">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-328">24348</span><span class="sxs-lookup"><span data-stu-id="bd80f-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="bd80f-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="bd80f-329">processCommandLine</span></span>                        | <span data-ttu-id="bd80f-330">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-331">"" \\ Il file è pronto per il Download \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="bd80f-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="bd80f-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="bd80f-332">processCreationTime</span></span>                       | <span data-ttu-id="bd80f-333">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-334">2020-07-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="bd80f-335">parentProcessId</span></span>                           | <span data-ttu-id="bd80f-336">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="bd80f-337">16840</span><span class="sxs-lookup"><span data-stu-id="bd80f-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="bd80f-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="bd80f-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="bd80f-339">Disponibile se entityType è *Process*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-340">2020-07-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="bd80f-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-341">ipAddress</span><span class="sxs-lookup"><span data-stu-id="bd80f-341">ipAddress</span></span>                                 | <span data-ttu-id="bd80f-342">Disponibile se entityType è *IP*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="bd80f-343">Indirizzo IP per gli avvisi associati agli eventi di rete, ad esempio *la comunicazione a una destinazione di rete dannosa*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="bd80f-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="bd80f-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="bd80f-345">URL</span><span class="sxs-lookup"><span data-stu-id="bd80f-345">url</span></span>                                       | <span data-ttu-id="bd80f-346">Disponibile se entityType è l' *URL*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="bd80f-347">URL per gli avvisi associati a eventi di rete, ad esempio *la comunicazione a una destinazione di rete dannosa*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="bd80f-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="bd80f-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="bd80f-349">accountName</span><span class="sxs-lookup"><span data-stu-id="bd80f-349">accountName</span></span>                               | <span data-ttu-id="bd80f-350">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="bd80f-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="bd80f-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="bd80f-352">domainName</span><span class="sxs-lookup"><span data-stu-id="bd80f-352">domainName</span></span>                                | <span data-ttu-id="bd80f-353">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="bd80f-354">Europe. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="bd80f-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-355">userSid</span><span class="sxs-lookup"><span data-stu-id="bd80f-355">userSid</span></span>                                   | <span data-ttu-id="bd80f-356">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="bd80f-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="bd80f-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="bd80f-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="bd80f-358">aadUserId</span></span>                                 | <span data-ttu-id="bd80f-359">Disponibile se entityType è *User*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="bd80f-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="bd80f-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="bd80f-361">userPrincipalName</span></span>                         | <span data-ttu-id="bd80f-362">Disponibile se EntityType è la cassetta postale *dell'utente* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="bd80f-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd80f-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="bd80f-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="bd80f-365">Disponibile se entityType è una *cassetta postale*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-366">test User2</span><span class="sxs-lookup"><span data-stu-id="bd80f-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="bd80f-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="bd80f-367">mailboxAddress</span></span>                            | <span data-ttu-id="bd80f-368">Disponibile se EntityType è la cassetta postale *dell'utente* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="bd80f-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd80f-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="bd80f-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="bd80f-370">clusterBy</span></span>                                 | <span data-ttu-id="bd80f-371">Disponibile se entityType è  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="bd80f-372">Soggetto P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="bd80f-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="bd80f-373">mittente</span><span class="sxs-lookup"><span data-stu-id="bd80f-373">sender</span></span>                                    | <span data-ttu-id="bd80f-374">Disponibile se EntityType è la cassetta postale *dell'utente* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="bd80f-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="bd80f-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="bd80f-376">destinatario</span><span class="sxs-lookup"><span data-stu-id="bd80f-376">recipient</span></span>                                 | <span data-ttu-id="bd80f-377">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="bd80f-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bd80f-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="bd80f-379">subject</span><span class="sxs-lookup"><span data-stu-id="bd80f-379">subject</span></span>                                   | <span data-ttu-id="bd80f-380">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="bd80f-381">\[\]Attenzione esterna</span><span class="sxs-lookup"><span data-stu-id="bd80f-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-382">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="bd80f-382">deliveryAction</span></span>                            | <span data-ttu-id="bd80f-383">Disponibile se entityType è *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="bd80f-384">Consegnato</span><span class="sxs-lookup"><span data-stu-id="bd80f-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="bd80f-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="bd80f-385">securityGroupId</span></span>                           | <span data-ttu-id="bd80f-386">Disponibile se entityType è  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="bd80f-387">301c47c8-e15f-4059-AB09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="bd80f-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="bd80f-388">securityGroupName</span></span>                         | <span data-ttu-id="bd80f-389">Disponibile se entityType è  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="bd80f-390">Operatori di configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="bd80f-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="bd80f-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="bd80f-391">registryHive</span></span>                              | <span data-ttu-id="bd80f-392">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="bd80f-393">\_computer locale di HKEY \_</span><span class="sxs-lookup"><span data-stu-id="bd80f-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="bd80f-394">registryKey</span><span class="sxs-lookup"><span data-stu-id="bd80f-394">registryKey</span></span>                               | <span data-ttu-id="bd80f-395">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="bd80f-396">SOFTWARE \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="bd80f-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="bd80f-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="bd80f-397">registryValueType</span></span>                         | <span data-ttu-id="bd80f-398">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="bd80f-399">Stringa</span><span class="sxs-lookup"><span data-stu-id="bd80f-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="bd80f-400">registryValue</span><span class="sxs-lookup"><span data-stu-id="bd80f-400">registryValue</span></span>                             | <span data-ttu-id="bd80f-401">Disponibile se entityType è  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="bd80f-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="bd80f-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="bd80f-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="bd80f-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="bd80f-403">deviceId</span></span>                                  | <span data-ttu-id="bd80f-404">L'ID, se presente, del dispositivo relativo all'entità.</span><span class="sxs-lookup"><span data-stu-id="bd80f-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="bd80f-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="bd80f-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="bd80f-406">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd80f-406">Example</span></span>

<span data-ttu-id="bd80f-407">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="bd80f-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="bd80f-408">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="bd80f-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="bd80f-409">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="bd80f-409">Related topic</span></span>
- [<span data-ttu-id="bd80f-410">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="bd80f-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="bd80f-411">Aggiornare incidente</span><span class="sxs-lookup"><span data-stu-id="bd80f-411">Update incident</span></span>](api-update-incidents.md)
