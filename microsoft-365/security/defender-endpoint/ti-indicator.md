---
title: Tipo di risorsa indicatore
description: Specifica i dettagli dell'entità e definisci la scadenza dell'indicatore usando Microsoft Defender per Endpoint.
keywords: api, api supportate, get, TiIndicator, Indicatore, recente
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
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771382"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="50619-104">Tipo di risorsa indicatore</span><span class="sxs-lookup"><span data-stu-id="50619-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="50619-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="50619-105">**Applies to:**</span></span>
- [<span data-ttu-id="50619-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="50619-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="50619-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50619-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="50619-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="50619-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="50619-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="50619-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="50619-110">Vedere la [pagina Indicatori corrispondente](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) nel portale.</span><span class="sxs-lookup"><span data-stu-id="50619-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="50619-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="50619-111">Method</span></span>|<span data-ttu-id="50619-112">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="50619-112">Return Type</span></span> |<span data-ttu-id="50619-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50619-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="50619-114">Elenca indicatori</span><span class="sxs-lookup"><span data-stu-id="50619-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="50619-115">[Indicatore](ti-indicator.md) Raccolta</span><span class="sxs-lookup"><span data-stu-id="50619-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="50619-116">Entità [indicatore](ti-indicator.md) elenco.</span><span class="sxs-lookup"><span data-stu-id="50619-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="50619-117">Invia indicatore</span><span class="sxs-lookup"><span data-stu-id="50619-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="50619-118">Indicatore</span><span class="sxs-lookup"><span data-stu-id="50619-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="50619-119">Inviare o aggiornare [l'entità Indicatore.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="50619-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="50619-120">Indicatori di importazione</span><span class="sxs-lookup"><span data-stu-id="50619-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="50619-121">[Indicatore](ti-indicator.md) Raccolta</span><span class="sxs-lookup"><span data-stu-id="50619-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="50619-122">Inviare o aggiornare [entità](ti-indicator.md) Indicatori.</span><span class="sxs-lookup"><span data-stu-id="50619-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="50619-123">Elimina indicatore</span><span class="sxs-lookup"><span data-stu-id="50619-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="50619-124">Nessun contenuto</span><span class="sxs-lookup"><span data-stu-id="50619-124">No Content</span></span> | <span data-ttu-id="50619-125">Elimina [l'entità Indicatore.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="50619-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="50619-126">Proprietà</span><span class="sxs-lookup"><span data-stu-id="50619-126">Properties</span></span>
<span data-ttu-id="50619-127">Proprietà</span><span class="sxs-lookup"><span data-stu-id="50619-127">Property</span></span> |  <span data-ttu-id="50619-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="50619-128">Type</span></span>    |   <span data-ttu-id="50619-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50619-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="50619-130">id</span><span class="sxs-lookup"><span data-stu-id="50619-130">id</span></span> | <span data-ttu-id="50619-131">Stringa</span><span class="sxs-lookup"><span data-stu-id="50619-131">String</span></span> | <span data-ttu-id="50619-132">Identità [dell'entità Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="50619-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="50619-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="50619-133">indicatorValue</span></span> | <span data-ttu-id="50619-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="50619-134">String</span></span> | <span data-ttu-id="50619-135">Valore dell'oggetto [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="50619-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="50619-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="50619-136">indicatorType</span></span> | <span data-ttu-id="50619-137">Enum</span><span class="sxs-lookup"><span data-stu-id="50619-137">Enum</span></span> | <span data-ttu-id="50619-138">Tipo dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-138">Type of the indicator.</span></span> <span data-ttu-id="50619-139">I valori possibili sono: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".</span><span class="sxs-lookup"><span data-stu-id="50619-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="50619-140">application</span><span class="sxs-lookup"><span data-stu-id="50619-140">application</span></span> | <span data-ttu-id="50619-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="50619-141">String</span></span> | <span data-ttu-id="50619-142">Applicazione associata all'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="50619-143">action</span><span class="sxs-lookup"><span data-stu-id="50619-143">action</span></span> | <span data-ttu-id="50619-144">Enum</span><span class="sxs-lookup"><span data-stu-id="50619-144">Enum</span></span> | <span data-ttu-id="50619-145">Azione che verrà eseguita se l'indicatore verrà individuato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="50619-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="50619-146">I valori possibili sono: "Alert", "AlertAndBlock" e "Allowed".</span><span class="sxs-lookup"><span data-stu-id="50619-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="50619-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="50619-147">sourceType</span></span> | <span data-ttu-id="50619-148">Enum</span><span class="sxs-lookup"><span data-stu-id="50619-148">Enum</span></span> | <span data-ttu-id="50619-149">"Utente" nel caso in cui l'indicatore creato da un utente (ad esempio dal portale), "AadApp" nel caso in cui sia stato inviato utilizzando l'applicazione automatizzata tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="50619-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="50619-150">source</span><span class="sxs-lookup"><span data-stu-id="50619-150">source</span></span> | <span data-ttu-id="50619-151">stringa</span><span class="sxs-lookup"><span data-stu-id="50619-151">string</span></span> | <span data-ttu-id="50619-152">Nome dell'utente/applicazione che ha inviato l'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="50619-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="50619-153">createdBy</span></span> | <span data-ttu-id="50619-154">Stringa</span><span class="sxs-lookup"><span data-stu-id="50619-154">String</span></span> | <span data-ttu-id="50619-155">Identità univoca dell'utente/applicazione che ha inviato l'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="50619-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="50619-156">lastUpdatedBy</span></span> | <span data-ttu-id="50619-157">Stringa</span><span class="sxs-lookup"><span data-stu-id="50619-157">String</span></span> | <span data-ttu-id="50619-158">Identità dell'utente/applicazione che ha aggiornato l'indicatore per l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="50619-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="50619-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="50619-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="50619-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="50619-160">DateTimeOffset</span></span> | <span data-ttu-id="50619-161">Data e ora di creazione dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="50619-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="50619-162">expirationTime</span></span> | <span data-ttu-id="50619-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="50619-163">DateTimeOffset</span></span> | <span data-ttu-id="50619-164">Ora di scadenza dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="50619-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="50619-165">lastUpdateTime</span></span> | <span data-ttu-id="50619-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="50619-166">DateTimeOffset</span></span> | <span data-ttu-id="50619-167">L'ultima volta che l'indicatore è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="50619-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="50619-168">gravità</span><span class="sxs-lookup"><span data-stu-id="50619-168">severity</span></span> | <span data-ttu-id="50619-169">Enum</span><span class="sxs-lookup"><span data-stu-id="50619-169">Enum</span></span> | <span data-ttu-id="50619-170">Gravità dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-170">The severity of the indicator.</span></span> <span data-ttu-id="50619-171">i valori possibili sono: "Informational", "Low", "Medium" e "High".</span><span class="sxs-lookup"><span data-stu-id="50619-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="50619-172">title</span><span class="sxs-lookup"><span data-stu-id="50619-172">title</span></span> | <span data-ttu-id="50619-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="50619-173">String</span></span> | <span data-ttu-id="50619-174">Titolo indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-174">Indicator title.</span></span>
<span data-ttu-id="50619-175">descrizione</span><span class="sxs-lookup"><span data-stu-id="50619-175">description</span></span> | <span data-ttu-id="50619-176">Stringa</span><span class="sxs-lookup"><span data-stu-id="50619-176">String</span></span> | <span data-ttu-id="50619-177">Descrizione dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-177">Description of the indicator.</span></span>
<span data-ttu-id="50619-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="50619-178">recommendedActions</span></span> | <span data-ttu-id="50619-179">Stringa</span><span class="sxs-lookup"><span data-stu-id="50619-179">String</span></span> | <span data-ttu-id="50619-180">Azioni consigliate per l'indicatore.</span><span class="sxs-lookup"><span data-stu-id="50619-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="50619-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="50619-181">rbacGroupNames</span></span> | <span data-ttu-id="50619-182">Elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="50619-182">List of strings</span></span> | <span data-ttu-id="50619-183">Nomi dei gruppi di dispositivi RBAC in cui l'indicatore è esposto e attivo.</span><span class="sxs-lookup"><span data-stu-id="50619-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="50619-184">Elenco vuoto nel caso in cui sia esposto a tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="50619-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="50619-185">Rappresentazione Json</span><span class="sxs-lookup"><span data-stu-id="50619-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
