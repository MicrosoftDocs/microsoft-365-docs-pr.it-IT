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
ms.technology: mde
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187256"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="aafe8-104">API per l'invio o l'aggiornamento degli indicatori</span><span class="sxs-lookup"><span data-stu-id="aafe8-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aafe8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="aafe8-105">**Applies to:**</span></span>
- [<span data-ttu-id="aafe8-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="aafe8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aafe8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aafe8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aafe8-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aafe8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aafe8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="aafe8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="aafe8-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="aafe8-110">API description</span></span>
<span data-ttu-id="aafe8-111">Invia o aggiorna la nuova [entità Indicatore.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="aafe8-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="aafe8-112">La notazione CIDR per gli IP non è supportata.</span><span class="sxs-lookup"><span data-stu-id="aafe8-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="aafe8-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="aafe8-113">Limitations</span></span>
1. <span data-ttu-id="aafe8-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="aafe8-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="aafe8-115">Esiste un limite di 15.000 indicatori attivi per tenant.</span><span class="sxs-lookup"><span data-stu-id="aafe8-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="aafe8-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="aafe8-116">Permissions</span></span>
<span data-ttu-id="aafe8-117">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="aafe8-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="aafe8-118">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="aafe8-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="aafe8-119">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aafe8-119">Permission type</span></span> |   <span data-ttu-id="aafe8-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aafe8-120">Permission</span></span>  |   <span data-ttu-id="aafe8-121">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aafe8-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="aafe8-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="aafe8-122">Application</span></span> |   <span data-ttu-id="aafe8-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="aafe8-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="aafe8-124">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="aafe8-124">'Read and write Indicators'</span></span>
<span data-ttu-id="aafe8-125">Applicazione</span><span class="sxs-lookup"><span data-stu-id="aafe8-125">Application</span></span> |   <span data-ttu-id="aafe8-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="aafe8-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="aafe8-127">"Lettura e scrittura di tutti gli indicatori"</span><span class="sxs-lookup"><span data-stu-id="aafe8-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="aafe8-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="aafe8-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="aafe8-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="aafe8-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="aafe8-130">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="aafe8-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="aafe8-131">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="aafe8-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="aafe8-132">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="aafe8-132">Request headers</span></span>

<span data-ttu-id="aafe8-133">Name</span><span class="sxs-lookup"><span data-stu-id="aafe8-133">Name</span></span> | <span data-ttu-id="aafe8-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="aafe8-134">Type</span></span> | <span data-ttu-id="aafe8-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aafe8-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="aafe8-136">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aafe8-136">Authorization</span></span> | <span data-ttu-id="aafe8-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="aafe8-137">String</span></span> | <span data-ttu-id="aafe8-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="aafe8-138">Bearer {token}.</span></span> <span data-ttu-id="aafe8-139">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="aafe8-139">**Required**.</span></span>
<span data-ttu-id="aafe8-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="aafe8-140">Content-Type</span></span> | <span data-ttu-id="aafe8-141">stringa</span><span class="sxs-lookup"><span data-stu-id="aafe8-141">string</span></span> | <span data-ttu-id="aafe8-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="aafe8-142">application/json.</span></span> <span data-ttu-id="aafe8-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="aafe8-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="aafe8-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="aafe8-144">Request body</span></span>
<span data-ttu-id="aafe8-145">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="aafe8-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="aafe8-146">Parametro</span><span class="sxs-lookup"><span data-stu-id="aafe8-146">Parameter</span></span> | <span data-ttu-id="aafe8-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="aafe8-147">Type</span></span>    | <span data-ttu-id="aafe8-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aafe8-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="aafe8-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="aafe8-149">indicatorValue</span></span> | <span data-ttu-id="aafe8-150">Stringa</span><span class="sxs-lookup"><span data-stu-id="aafe8-150">String</span></span> | <span data-ttu-id="aafe8-151">Identità [dell'entità Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="aafe8-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="aafe8-152">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="aafe8-152">**Required**</span></span>
<span data-ttu-id="aafe8-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="aafe8-153">indicatorType</span></span> | <span data-ttu-id="aafe8-154">Enum</span><span class="sxs-lookup"><span data-stu-id="aafe8-154">Enum</span></span> | <span data-ttu-id="aafe8-155">Tipo dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="aafe8-155">Type of the indicator.</span></span> <span data-ttu-id="aafe8-156">I valori possibili sono: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".</span><span class="sxs-lookup"><span data-stu-id="aafe8-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="aafe8-157">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="aafe8-157">**Required**</span></span>
<span data-ttu-id="aafe8-158">action</span><span class="sxs-lookup"><span data-stu-id="aafe8-158">action</span></span> | <span data-ttu-id="aafe8-159">Enum</span><span class="sxs-lookup"><span data-stu-id="aafe8-159">Enum</span></span> | <span data-ttu-id="aafe8-160">Azione che verrà eseguita se l'indicatore verrà individuato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aafe8-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="aafe8-161">I valori possibili sono: "Alert", "AlertAndBlock" e "Allowed".</span><span class="sxs-lookup"><span data-stu-id="aafe8-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="aafe8-162">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="aafe8-162">**Required**</span></span>
<span data-ttu-id="aafe8-163">application</span><span class="sxs-lookup"><span data-stu-id="aafe8-163">application</span></span> | <span data-ttu-id="aafe8-164">Stringa</span><span class="sxs-lookup"><span data-stu-id="aafe8-164">String</span></span> | <span data-ttu-id="aafe8-165">Applicazione associata all'indicatore.</span><span class="sxs-lookup"><span data-stu-id="aafe8-165">The application associated with the indicator.</span></span> <span data-ttu-id="aafe8-166">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="aafe8-166">**Optional**</span></span>
<span data-ttu-id="aafe8-167">title</span><span class="sxs-lookup"><span data-stu-id="aafe8-167">title</span></span> | <span data-ttu-id="aafe8-168">Stringa</span><span class="sxs-lookup"><span data-stu-id="aafe8-168">String</span></span> | <span data-ttu-id="aafe8-169">Titolo dell'avviso indicatore.</span><span class="sxs-lookup"><span data-stu-id="aafe8-169">Indicator alert title.</span></span> <span data-ttu-id="aafe8-170">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="aafe8-170">**Required**</span></span>
<span data-ttu-id="aafe8-171">descrizione</span><span class="sxs-lookup"><span data-stu-id="aafe8-171">description</span></span> | <span data-ttu-id="aafe8-172">Stringa</span><span class="sxs-lookup"><span data-stu-id="aafe8-172">String</span></span> | <span data-ttu-id="aafe8-173">Descrizione dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="aafe8-173">Description of the indicator.</span></span> <span data-ttu-id="aafe8-174">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="aafe8-174">**Required**</span></span>
<span data-ttu-id="aafe8-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="aafe8-175">expirationTime</span></span> | <span data-ttu-id="aafe8-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="aafe8-176">DateTimeOffset</span></span> | <span data-ttu-id="aafe8-177">Ora di scadenza dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="aafe8-177">The expiration time of the indicator.</span></span> <span data-ttu-id="aafe8-178">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="aafe8-178">**Optional**</span></span>
<span data-ttu-id="aafe8-179">gravità</span><span class="sxs-lookup"><span data-stu-id="aafe8-179">severity</span></span> | <span data-ttu-id="aafe8-180">Enum</span><span class="sxs-lookup"><span data-stu-id="aafe8-180">Enum</span></span> | <span data-ttu-id="aafe8-181">Gravità dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="aafe8-181">The severity of the indicator.</span></span> <span data-ttu-id="aafe8-182">i valori possibili sono: "Informational", "Low", "Medium" e "High".</span><span class="sxs-lookup"><span data-stu-id="aafe8-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="aafe8-183">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="aafe8-183">**Optional**</span></span>
<span data-ttu-id="aafe8-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="aafe8-184">recommendedActions</span></span> | <span data-ttu-id="aafe8-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="aafe8-185">String</span></span> | <span data-ttu-id="aafe8-186">Azioni consigliate per l'avviso dell'indicatore TI.</span><span class="sxs-lookup"><span data-stu-id="aafe8-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="aafe8-187">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="aafe8-187">**Optional**</span></span>
<span data-ttu-id="aafe8-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="aafe8-188">rbacGroupNames</span></span> | <span data-ttu-id="aafe8-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="aafe8-189">String</span></span> | <span data-ttu-id="aafe8-190">Elenco delimitato da virgole di nomi di gruppi RBAC a cui verrà applicato l'indicatore.</span><span class="sxs-lookup"><span data-stu-id="aafe8-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="aafe8-191">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="aafe8-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="aafe8-192">Risposta</span><span class="sxs-lookup"><span data-stu-id="aafe8-192">Response</span></span>
- <span data-ttu-id="aafe8-193">Se ha esito positivo, questo metodo restituisce 200 - OK codice di risposta e l'entità [Indicator](ti-indicator.md) creata/aggiornata nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="aafe8-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="aafe8-194">In caso di esito negativo: questo metodo restituisce 400 - Richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="aafe8-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="aafe8-195">La richiesta non valida in genere indica un corpo errato.</span><span class="sxs-lookup"><span data-stu-id="aafe8-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="aafe8-196">Esempio</span><span class="sxs-lookup"><span data-stu-id="aafe8-196">Example</span></span>

<span data-ttu-id="aafe8-197">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="aafe8-197">**Request**</span></span>

<span data-ttu-id="aafe8-198">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="aafe8-198">Here is an example of the request.</span></span>

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

## <a name="related-topic"></a><span data-ttu-id="aafe8-199">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="aafe8-199">Related topic</span></span>
- [<span data-ttu-id="aafe8-200">Gestire gli indicatori</span><span class="sxs-lookup"><span data-stu-id="aafe8-200">Manage indicators</span></span>](manage-indicators.md)
