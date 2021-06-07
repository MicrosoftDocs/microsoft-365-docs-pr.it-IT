---
title: Eseguire il pull dei rilevamenti di Microsoft Defender per endpoint con l'API REST
description: Scopri come chiamare un endpoint API di Microsoft Defender for Endpoint per eseguire il pull dei rilevamenti in formato JSON usando l'API REST SIEM.
keywords: rilevamenti, rilevamenti pull, api rest, richiesta, risposta
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
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6716b0eb029b49ec08cb52ebefc23e50b19036ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771670"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="25bf9-104">Eseguire il pull dei rilevamenti di Microsoft Defender per endpoint con l'API REST SIEM</span><span class="sxs-lookup"><span data-stu-id="25bf9-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25bf9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="25bf9-105">**Applies to:**</span></span>
- [<span data-ttu-id="25bf9-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="25bf9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="25bf9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25bf9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="25bf9-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="25bf9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25bf9-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="25bf9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="25bf9-110">[Microsoft Defender for Endpoint Alert](alerts.md) è composto da uno o più rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="25bf9-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="25bf9-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) è composto dall'evento sospetto che si è verificato nel dispositivo e dai relativi dettagli di avviso.</span><span class="sxs-lookup"><span data-stu-id="25bf9-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="25bf9-112">-L'API di Microsoft Defender for Endpoint Alert è l'API più recente per il consumo di avvisi e contiene un elenco dettagliato di prove correlate per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="25bf9-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="25bf9-113">Per ulteriori informazioni, vedere [Metodi e proprietà degli](alerts.md) avvisi e Avvisi [elenco.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="25bf9-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="25bf9-114">Microsoft Defender for Endpoint supporta il protocollo OAuth 2.0 per il pull dei rilevamenti dall'API.</span><span class="sxs-lookup"><span data-stu-id="25bf9-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="25bf9-115">In generale, il protocollo OAuth 2.0 supporta quattro tipi di flussi:</span><span class="sxs-lookup"><span data-stu-id="25bf9-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="25bf9-116">Flusso di concessione dell'autorizzazione</span><span class="sxs-lookup"><span data-stu-id="25bf9-116">Authorization grant flow</span></span>
- <span data-ttu-id="25bf9-117">Flusso implicito</span><span class="sxs-lookup"><span data-stu-id="25bf9-117">Implicit flow</span></span>
- <span data-ttu-id="25bf9-118">Flusso delle credenziali client</span><span class="sxs-lookup"><span data-stu-id="25bf9-118">Client credentials flow</span></span>
- <span data-ttu-id="25bf9-119">Flusso proprietario risorsa</span><span class="sxs-lookup"><span data-stu-id="25bf9-119">Resource owner flow</span></span>

<span data-ttu-id="25bf9-120">Per ulteriori informazioni sulle specifiche OAuth, vedere il sito Web [OAuth.](http://www.oauth.net)</span><span class="sxs-lookup"><span data-stu-id="25bf9-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="25bf9-121">Microsoft Defender for Endpoint  supporta il flusso di concessione dell'autorizzazione e il flusso delle credenziali _client_ per ottenere l'accesso ai rilevamenti pull, con Azure Active Directory (AAD) come server di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="25bf9-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="25bf9-122">Il _flusso di concessione dell'autorizzazione_ usa le credenziali utente per ottenere un codice di autorizzazione, che viene quindi usato per ottenere un token di accesso.</span><span class="sxs-lookup"><span data-stu-id="25bf9-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="25bf9-123">Il _flusso di credenziali client usa_ le credenziali client per eseguire l'autenticazione nell'URL dell'endpoint di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="25bf9-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="25bf9-124">Questo flusso è adatto agli scenari in cui un client OAuth crea richieste a un'API che non richiede credenziali utente.</span><span class="sxs-lookup"><span data-stu-id="25bf9-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="25bf9-125">Usa il metodo seguente nell'API di Microsoft Defender for Endpoint per estrarre i rilevamenti in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="25bf9-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="25bf9-126">Microsoft Defender Security Center unisce rilevamenti di avvisi simili in un singolo avviso.</span><span class="sxs-lookup"><span data-stu-id="25bf9-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="25bf9-127">Questa API esegue il pull dei rilevamenti degli avvisi nella forma non elaborata in base ai parametri di query impostati, consentendo di applicare il proprio raggruppamento e filtro.</span><span class="sxs-lookup"><span data-stu-id="25bf9-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="25bf9-128">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="25bf9-128">Before you begin</span></span>
- <span data-ttu-id="25bf9-129">Prima di chiamare l'endpoint di Microsoft Defender per Endpoint per il pull dei rilevamenti, devi abilitare l'applicazione di integrazione SIEM in Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="25bf9-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="25bf9-130">Per altre informazioni, vedi [Abilitare l'integrazione SIEM in Microsoft Defender per Endpoint.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="25bf9-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="25bf9-131">Prendere nota dei valori seguenti nella registrazione dell'applicazione Azure.</span><span class="sxs-lookup"><span data-stu-id="25bf9-131">Take note of the following values in your Azure application registration.</span></span> <span data-ttu-id="25bf9-132">Sono necessari questi valori per configurare il flusso OAuth nel servizio o nell'app daemon:</span><span class="sxs-lookup"><span data-stu-id="25bf9-132">You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="25bf9-133">ID applicazione (univoco per l'applicazione)</span><span class="sxs-lookup"><span data-stu-id="25bf9-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="25bf9-134">Chiave dell'app o segreto (univoco per l'applicazione)</span><span class="sxs-lookup"><span data-stu-id="25bf9-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="25bf9-135">Endpoint token OAuth 2.0 della tua app</span><span class="sxs-lookup"><span data-stu-id="25bf9-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="25bf9-136">Trova questo valore facendo **clic su Visualizza endpoint** nella parte inferiore del portale di gestione di Azure nella pagina dell'app.</span><span class="sxs-lookup"><span data-stu-id="25bf9-136">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page.</span></span> <span data-ttu-id="25bf9-137">L'endpoint sarà simile `https://login.microsoftonline.com/{tenantId}/oauth2/token` a .</span><span class="sxs-lookup"><span data-stu-id="25bf9-137">The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="25bf9-138">Ottenere un token di accesso</span><span class="sxs-lookup"><span data-stu-id="25bf9-138">Get an access token</span></span>
<span data-ttu-id="25bf9-139">Prima di creare chiamate all'endpoint, devi ottenere un token di accesso.</span><span class="sxs-lookup"><span data-stu-id="25bf9-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="25bf9-140">Userai il token di accesso per accedere alla risorsa protetta, ovvero i rilevamenti in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="25bf9-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="25bf9-141">Per ottenere un token di accesso, devi eseguire una richiesta POST all'endpoint di emissione del token.</span><span class="sxs-lookup"><span data-stu-id="25bf9-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="25bf9-142">Ecco una richiesta di esempio:</span><span class="sxs-lookup"><span data-stu-id="25bf9-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="25bf9-143">La risposta includerà un token di accesso e informazioni sulla scadenza.</span><span class="sxs-lookup"><span data-stu-id="25bf9-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="25bf9-144">Ora puoi usare il valore nel campo *access_token* in una richiesta all'API Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="25bf9-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="25bf9-145">Richiesta</span><span class="sxs-lookup"><span data-stu-id="25bf9-145">Request</span></span>
<span data-ttu-id="25bf9-146">Con un token di accesso, la tua app può effettuare richieste autenticate all'API di Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="25bf9-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="25bf9-147">L'app deve aggiungere il token di accesso all'intestazione Authorization di ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="25bf9-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="25bf9-148">Sintassi delle richieste</span><span class="sxs-lookup"><span data-stu-id="25bf9-148">Request syntax</span></span>
<span data-ttu-id="25bf9-149">Metodo</span><span class="sxs-lookup"><span data-stu-id="25bf9-149">Method</span></span> | <span data-ttu-id="25bf9-150">URI richiesta</span><span class="sxs-lookup"><span data-stu-id="25bf9-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="25bf9-151">GET</span><span class="sxs-lookup"><span data-stu-id="25bf9-151">GET</span></span>| <span data-ttu-id="25bf9-152">Usa l'URI applicabile per la tua area geografica.</span><span class="sxs-lookup"><span data-stu-id="25bf9-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="25bf9-153">**Per l'UE**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="25bf9-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="25bf9-154">**Per gli Stati Uniti**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="25bf9-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="25bf9-155">**Per il Regno Unito**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="25bf9-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="25bf9-156">Intestazione della richiesta</span><span class="sxs-lookup"><span data-stu-id="25bf9-156">Request header</span></span>
<span data-ttu-id="25bf9-157">Intestazione</span><span class="sxs-lookup"><span data-stu-id="25bf9-157">Header</span></span> | <span data-ttu-id="25bf9-158">Tipo</span><span class="sxs-lookup"><span data-stu-id="25bf9-158">Type</span></span> | <span data-ttu-id="25bf9-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25bf9-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="25bf9-160">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="25bf9-160">Authorization</span></span> | <span data-ttu-id="25bf9-161">stringa</span><span class="sxs-lookup"><span data-stu-id="25bf9-161">string</span></span> | <span data-ttu-id="25bf9-162">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="25bf9-162">Required.</span></span> <span data-ttu-id="25bf9-163">Token di accesso di Azure AD nel formato **Token Bearer** &lt;  &gt; .</span><span class="sxs-lookup"><span data-stu-id="25bf9-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="25bf9-164">Parametri di richiesta</span><span class="sxs-lookup"><span data-stu-id="25bf9-164">Request parameters</span></span>

<span data-ttu-id="25bf9-165">Utilizzare parametri di query facoltativi per specificare e controllare la quantità di dati restituiti in una risposta.</span><span class="sxs-lookup"><span data-stu-id="25bf9-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="25bf9-166">Se si chiama questo metodo senza parametri, la risposta contiene tutti gli avvisi nell'organizzazione nelle ultime 2 ore.</span><span class="sxs-lookup"><span data-stu-id="25bf9-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="25bf9-167">Name</span><span class="sxs-lookup"><span data-stu-id="25bf9-167">Name</span></span> | <span data-ttu-id="25bf9-168">Valore</span><span class="sxs-lookup"><span data-stu-id="25bf9-168">Value</span></span>| <span data-ttu-id="25bf9-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25bf9-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="25bf9-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="25bf9-170">sinceTimeUtc</span></span> | <span data-ttu-id="25bf9-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="25bf9-171">DateTime</span></span> | <span data-ttu-id="25bf9-172">Definisce gli avvisi di tempo inferiore da cui vengono recuperati gli avvisi in base al campo:</span><span class="sxs-lookup"><span data-stu-id="25bf9-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="25bf9-173">L'intervallo di tempo sarà: da sinceTimeUtc time a current time.</span><span class="sxs-lookup"><span data-stu-id="25bf9-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="25bf9-174">**NOTA:** se non specificato, vengono recuperati tutti gli avvisi generati nelle ultime due ore.</span><span class="sxs-lookup"><span data-stu-id="25bf9-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="25bf9-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="25bf9-175">untilTimeUtc</span></span> | <span data-ttu-id="25bf9-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="25bf9-176">DateTime</span></span> | <span data-ttu-id="25bf9-177">Definisce gli avvisi limite temporale superiore recuperati.</span><span class="sxs-lookup"><span data-stu-id="25bf9-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="25bf9-178">L'intervallo di tempo sarà: `sinceTimeUtc` di tanto in `untilTimeUtc` tanto.</span><span class="sxs-lookup"><span data-stu-id="25bf9-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="25bf9-179">**NOTA:** se non specificato, il valore predefinito sarà l'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="25bf9-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="25bf9-180">ago</span><span class="sxs-lookup"><span data-stu-id="25bf9-180">ago</span></span> | <span data-ttu-id="25bf9-181">stringa</span><span class="sxs-lookup"><span data-stu-id="25bf9-181">string</span></span> | <span data-ttu-id="25bf9-182">Estrae gli avvisi nel seguente intervallo di tempo: `(current_time - ago)` di tanto in `current_time` tanto.</span><span class="sxs-lookup"><span data-stu-id="25bf9-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="25bf9-183">Il valore deve essere impostato in base al formato di durata **ISO 8601**</span><span class="sxs-lookup"><span data-stu-id="25bf9-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="25bf9-184">Esempio: `ago=PT10M` verranno pull degli avvisi ricevuti negli ultimi 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="25bf9-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="25bf9-185">limite</span><span class="sxs-lookup"><span data-stu-id="25bf9-185">limit</span></span> | <span data-ttu-id="25bf9-186">int</span><span class="sxs-lookup"><span data-stu-id="25bf9-186">int</span></span> | <span data-ttu-id="25bf9-187">Definisce il numero di avvisi da recuperare.</span><span class="sxs-lookup"><span data-stu-id="25bf9-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="25bf9-188">Gli avvisi più recenti verranno recuperati in base al numero definito.</span><span class="sxs-lookup"><span data-stu-id="25bf9-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="25bf9-189">**NOTA:** se non specificato, verranno recuperati tutti gli avvisi disponibili nell'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="25bf9-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="25bf9-190">machinegroups</span><span class="sxs-lookup"><span data-stu-id="25bf9-190">machinegroups</span></span> | <span data-ttu-id="25bf9-191">stringa</span><span class="sxs-lookup"><span data-stu-id="25bf9-191">string</span></span> | <span data-ttu-id="25bf9-192">Specifica i gruppi di dispositivi da cui estrarre gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="25bf9-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="25bf9-193">**NOTA:** se non specificato, verranno recuperati gli avvisi di tutti i gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="25bf9-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="25bf9-194">Esempio:</span><span class="sxs-lookup"><span data-stu-id="25bf9-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="25bf9-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="25bf9-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="25bf9-196">stringa</span><span class="sxs-lookup"><span data-stu-id="25bf9-196">string</span></span> | <span data-ttu-id="25bf9-197">Tag dispositivo singolo dal Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="25bf9-197">Single device tag from the registry.</span></span>
<span data-ttu-id="25bf9-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="25bf9-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="25bf9-199">stringa</span><span class="sxs-lookup"><span data-stu-id="25bf9-199">string</span></span> | <span data-ttu-id="25bf9-200">Tag dispositivo creati in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="25bf9-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="25bf9-201">Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="25bf9-201">Request example</span></span>
<span data-ttu-id="25bf9-202">Nell'esempio seguente viene illustrato come recuperare tutti i rilevamenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25bf9-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="25bf9-203">L'esempio seguente illustra una richiesta per ottenere gli ultimi 20 rilevamenti dal 2016-09-12 alle 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="25bf9-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="25bf9-204">Risposta</span><span class="sxs-lookup"><span data-stu-id="25bf9-204">Response</span></span>
<span data-ttu-id="25bf9-205">Il valore restituito è una matrice di oggetti avviso in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="25bf9-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="25bf9-206">Ecco un valore restituito di esempio:</span><span class="sxs-lookup"><span data-stu-id="25bf9-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="25bf9-207">Esempi di codice</span><span class="sxs-lookup"><span data-stu-id="25bf9-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="25bf9-208">Ottenere il token di accesso</span><span class="sxs-lookup"><span data-stu-id="25bf9-208">Get access token</span></span>
<span data-ttu-id="25bf9-209">Gli esempi di codice seguenti illustrano come ottenere un token di accesso per chiamare l'API SIEM di Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="25bf9-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="25bf9-210">Usare il token per connettersi all'endpoint di rilevamento</span><span class="sxs-lookup"><span data-stu-id="25bf9-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="25bf9-211">Gli esempi di codice seguenti illustrano come usare un token di accesso per chiamare l'API Defender for Endpoint SIEM per ottenere avvisi.</span><span class="sxs-lookup"><span data-stu-id="25bf9-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="25bf9-212">Codici di errore</span><span class="sxs-lookup"><span data-stu-id="25bf9-212">Error codes</span></span>
<span data-ttu-id="25bf9-213">L'API REST di Microsoft Defender per endpoint restituisce i codici di errore seguenti causati da una richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="25bf9-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="25bf9-214">Codice di errore HTTP</span><span class="sxs-lookup"><span data-stu-id="25bf9-214">HTTP error code</span></span> | <span data-ttu-id="25bf9-215">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25bf9-215">Description</span></span>
:---|:---
<span data-ttu-id="25bf9-216">401</span><span class="sxs-lookup"><span data-stu-id="25bf9-216">401</span></span> | <span data-ttu-id="25bf9-217">Richiesta non valida o token non valido.</span><span class="sxs-lookup"><span data-stu-id="25bf9-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="25bf9-218">403</span><span class="sxs-lookup"><span data-stu-id="25bf9-218">403</span></span> | <span data-ttu-id="25bf9-219">Eccezione non autorizzata: uno dei domini non viene gestito dall'amministratore tenant o lo stato del tenant viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="25bf9-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="25bf9-220">500</span><span class="sxs-lookup"><span data-stu-id="25bf9-220">500</span></span> | <span data-ttu-id="25bf9-221">Errore nel servizio.</span><span class="sxs-lookup"><span data-stu-id="25bf9-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25bf9-222">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="25bf9-222">Related topics</span></span>
- [<span data-ttu-id="25bf9-223">Abilitare l'integrazione SIEM in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="25bf9-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="25bf9-224">Configurare ArcSight per eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint</span><span class="sxs-lookup"><span data-stu-id="25bf9-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="25bf9-225">Eseguire il pull dei rilevamenti agli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="25bf9-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="25bf9-226">Campi di Microsoft Defender per il rilevamento degli endpoint</span><span class="sxs-lookup"><span data-stu-id="25bf9-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="25bf9-227">Risolvere i problemi di integrazione degli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="25bf9-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
