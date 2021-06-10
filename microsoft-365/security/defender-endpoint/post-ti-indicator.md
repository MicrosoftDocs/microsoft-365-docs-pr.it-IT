---
title: API per l'invio o l'aggiornamento degli indicatori
description: Scopri come usare l'API Invia o Aggiorna indicatore per inviare o aggiornare una nuova entità Indicatore in Microsoft Defender per endpoint.
keywords: api, api del grafico, api supportate, inviare, ti, indicatore, aggiornamento
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771706"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="b9235-104">API per l'invio o l'aggiornamento degli indicatori</span><span class="sxs-lookup"><span data-stu-id="b9235-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9235-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b9235-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9235-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b9235-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9235-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9235-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9235-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b9235-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9235-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b9235-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b9235-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="b9235-110">API description</span></span>
<span data-ttu-id="b9235-111">Invia o aggiorna la nuova [entità Indicatore.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="b9235-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="b9235-112">La notazione CIDR per gli IP non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b9235-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="b9235-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="b9235-113">Limitations</span></span>
1. <span data-ttu-id="b9235-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="b9235-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="b9235-115">Esiste un limite di 15.000 indicatori attivi per tenant.</span><span class="sxs-lookup"><span data-stu-id="b9235-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="b9235-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b9235-116">Permissions</span></span>
<span data-ttu-id="b9235-117">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b9235-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b9235-118">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b9235-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="b9235-119">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b9235-119">Permission type</span></span> |   <span data-ttu-id="b9235-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b9235-120">Permission</span></span>  |   <span data-ttu-id="b9235-121">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b9235-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b9235-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="b9235-122">Application</span></span> |   <span data-ttu-id="b9235-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b9235-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="b9235-124">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="b9235-124">'Read and write Indicators'</span></span>
<span data-ttu-id="b9235-125">Applicazione</span><span class="sxs-lookup"><span data-stu-id="b9235-125">Application</span></span> |   <span data-ttu-id="b9235-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b9235-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="b9235-127">"Lettura e scrittura di tutti gli indicatori"</span><span class="sxs-lookup"><span data-stu-id="b9235-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="b9235-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="b9235-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="b9235-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b9235-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="b9235-130">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="b9235-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="b9235-131">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="b9235-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="b9235-132">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="b9235-132">Request headers</span></span>

<span data-ttu-id="b9235-133">Name</span><span class="sxs-lookup"><span data-stu-id="b9235-133">Name</span></span> | <span data-ttu-id="b9235-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="b9235-134">Type</span></span> | <span data-ttu-id="b9235-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9235-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="b9235-136">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b9235-136">Authorization</span></span> | <span data-ttu-id="b9235-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="b9235-137">String</span></span> | <span data-ttu-id="b9235-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b9235-138">Bearer {token}.</span></span> <span data-ttu-id="b9235-139">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="b9235-139">**Required**.</span></span>
<span data-ttu-id="b9235-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b9235-140">Content-Type</span></span> | <span data-ttu-id="b9235-141">stringa</span><span class="sxs-lookup"><span data-stu-id="b9235-141">string</span></span> | <span data-ttu-id="b9235-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="b9235-142">application/json.</span></span> <span data-ttu-id="b9235-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="b9235-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b9235-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="b9235-144">Request body</span></span>
<span data-ttu-id="b9235-145">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9235-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="b9235-146">Parametro</span><span class="sxs-lookup"><span data-stu-id="b9235-146">Parameter</span></span> | <span data-ttu-id="b9235-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="b9235-147">Type</span></span>    | <span data-ttu-id="b9235-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9235-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="b9235-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="b9235-149">indicatorValue</span></span> | <span data-ttu-id="b9235-150">Stringa</span><span class="sxs-lookup"><span data-stu-id="b9235-150">String</span></span> | <span data-ttu-id="b9235-151">Identità [dell'entità Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="b9235-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="b9235-152">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="b9235-152">**Required**</span></span>
<span data-ttu-id="b9235-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="b9235-153">indicatorType</span></span> | <span data-ttu-id="b9235-154">Enum</span><span class="sxs-lookup"><span data-stu-id="b9235-154">Enum</span></span> | <span data-ttu-id="b9235-155">Tipo dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="b9235-155">Type of the indicator.</span></span> <span data-ttu-id="b9235-156">I valori possibili sono: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".</span><span class="sxs-lookup"><span data-stu-id="b9235-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="b9235-157">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="b9235-157">**Required**</span></span>
<span data-ttu-id="b9235-158">action</span><span class="sxs-lookup"><span data-stu-id="b9235-158">action</span></span> | <span data-ttu-id="b9235-159">Enum</span><span class="sxs-lookup"><span data-stu-id="b9235-159">Enum</span></span> | <span data-ttu-id="b9235-160">Azione che verrà eseguita se l'indicatore verrà individuato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b9235-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="b9235-161">I valori possibili sono: "Alert", "AlertAndBlock" e "Allowed".</span><span class="sxs-lookup"><span data-stu-id="b9235-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="b9235-162">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="b9235-162">**Required**</span></span>
<span data-ttu-id="b9235-163">application</span><span class="sxs-lookup"><span data-stu-id="b9235-163">application</span></span> | <span data-ttu-id="b9235-164">Stringa</span><span class="sxs-lookup"><span data-stu-id="b9235-164">String</span></span> | <span data-ttu-id="b9235-165">Applicazione associata all'indicatore.</span><span class="sxs-lookup"><span data-stu-id="b9235-165">The application associated with the indicator.</span></span> <span data-ttu-id="b9235-166">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="b9235-166">**Optional**</span></span>
<span data-ttu-id="b9235-167">title</span><span class="sxs-lookup"><span data-stu-id="b9235-167">title</span></span> | <span data-ttu-id="b9235-168">Stringa</span><span class="sxs-lookup"><span data-stu-id="b9235-168">String</span></span> | <span data-ttu-id="b9235-169">Titolo dell'avviso indicatore.</span><span class="sxs-lookup"><span data-stu-id="b9235-169">Indicator alert title.</span></span> <span data-ttu-id="b9235-170">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="b9235-170">**Required**</span></span>
<span data-ttu-id="b9235-171">descrizione</span><span class="sxs-lookup"><span data-stu-id="b9235-171">description</span></span> | <span data-ttu-id="b9235-172">Stringa</span><span class="sxs-lookup"><span data-stu-id="b9235-172">String</span></span> | <span data-ttu-id="b9235-173">Descrizione dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="b9235-173">Description of the indicator.</span></span> <span data-ttu-id="b9235-174">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="b9235-174">**Required**</span></span>
<span data-ttu-id="b9235-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="b9235-175">expirationTime</span></span> | <span data-ttu-id="b9235-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b9235-176">DateTimeOffset</span></span> | <span data-ttu-id="b9235-177">Ora di scadenza dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="b9235-177">The expiration time of the indicator.</span></span> <span data-ttu-id="b9235-178">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="b9235-178">**Optional**</span></span>
<span data-ttu-id="b9235-179">gravità</span><span class="sxs-lookup"><span data-stu-id="b9235-179">severity</span></span> | <span data-ttu-id="b9235-180">Enum</span><span class="sxs-lookup"><span data-stu-id="b9235-180">Enum</span></span> | <span data-ttu-id="b9235-181">Gravità dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="b9235-181">The severity of the indicator.</span></span> <span data-ttu-id="b9235-182">i valori possibili sono: "Informational", "Low", "Medium" e "High".</span><span class="sxs-lookup"><span data-stu-id="b9235-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="b9235-183">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="b9235-183">**Optional**</span></span>
<span data-ttu-id="b9235-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="b9235-184">recommendedActions</span></span> | <span data-ttu-id="b9235-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="b9235-185">String</span></span> | <span data-ttu-id="b9235-186">Azioni consigliate per l'avviso dell'indicatore TI.</span><span class="sxs-lookup"><span data-stu-id="b9235-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="b9235-187">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="b9235-187">**Optional**</span></span>
<span data-ttu-id="b9235-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="b9235-188">rbacGroupNames</span></span> | <span data-ttu-id="b9235-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="b9235-189">String</span></span> | <span data-ttu-id="b9235-190">Elenco delimitato da virgole di nomi di gruppi RBAC a cui verrà applicato l'indicatore.</span><span class="sxs-lookup"><span data-stu-id="b9235-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="b9235-191">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="b9235-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="b9235-192">Risposta</span><span class="sxs-lookup"><span data-stu-id="b9235-192">Response</span></span>
- <span data-ttu-id="b9235-193">Se ha esito positivo, questo metodo restituisce 200 - OK codice di risposta e l'entità [Indicator](ti-indicator.md) creata/aggiornata nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="b9235-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="b9235-194">In caso di esito negativo: questo metodo restituisce 400 - Richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="b9235-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="b9235-195">La richiesta non valida in genere indica un corpo errato.</span><span class="sxs-lookup"><span data-stu-id="b9235-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="b9235-196">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9235-196">Example</span></span>

<span data-ttu-id="b9235-197">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b9235-197">**Request**</span></span>

<span data-ttu-id="b9235-198">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b9235-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="b9235-199">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="b9235-199">Related topic</span></span>
- [<span data-ttu-id="b9235-200">Gestire indicatori</span><span class="sxs-lookup"><span data-stu-id="b9235-200">Manage indicators</span></span>](manage-indicators.md)
