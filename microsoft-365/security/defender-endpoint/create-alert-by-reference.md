---
title: Creare un avviso dall'API dell'evento
description: Scopri come usare l'API Crea avviso per creare un nuovo avviso sopra Evento in Microsoft Defender per endpoint.
keywords: api, api del grafico, api supportate, ottenere, avviso, informazioni, id
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
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289464"
---
# <a name="create-alert-api"></a><span data-ttu-id="4e1ed-104">API per la creazione di avvisi</span><span class="sxs-lookup"><span data-stu-id="4e1ed-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4e1ed-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4e1ed-105">**Applies to:**</span></span>
- [<span data-ttu-id="4e1ed-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="4e1ed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4e1ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e1ed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="4e1ed-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4e1ed-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4e1ed-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4e1ed-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="4e1ed-110">API description</span></span>

<span data-ttu-id="4e1ed-111">Crea un [nuovo avviso](alerts.md) sopra **l'evento**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>

- <span data-ttu-id="4e1ed-112">**Microsoft Defender for Endpoint Event** è necessario per la creazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
- <span data-ttu-id="4e1ed-113">Dovrai fornire 3 parametri dall'evento nella richiesta: **Event Time,** **Machine ID** e **Report ID.**</span><span class="sxs-lookup"><span data-stu-id="4e1ed-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="4e1ed-114">Vedere l'esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-114">See example below.</span></span>
- <span data-ttu-id="4e1ed-115">Puoi usare un evento disponibile in Advanced Hunting API o Portal.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
- <span data-ttu-id="4e1ed-116">Se nello stesso dispositivo è presente un avviso aperto con lo stesso titolo, il nuovo avviso creato verrà unito ad esso.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
- <span data-ttu-id="4e1ed-117">Un'indagine automatica viene avviata automaticamente sugli avvisi creati tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-117">An automatic investigation starts automatically on alerts created via the API.</span></span>

## <a name="limitations"></a><span data-ttu-id="4e1ed-118">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="4e1ed-118">Limitations</span></span>

1. <span data-ttu-id="4e1ed-119">I limiti di frequenza per questa API sono 15 chiamate al minuto.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-119">Rate limitations for this API are 15 calls per minute.</span></span>

## <a name="permissions"></a><span data-ttu-id="4e1ed-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4e1ed-120">Permissions</span></span>

<span data-ttu-id="4e1ed-121">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4e1ed-122">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4e1ed-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4e1ed-123">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4e1ed-123">Permission type</span></span> | <span data-ttu-id="4e1ed-124">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4e1ed-124">Permission</span></span> | <span data-ttu-id="4e1ed-125">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4e1ed-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4e1ed-126">Applicazione</span><span class="sxs-lookup"><span data-stu-id="4e1ed-126">Application</span></span> | <span data-ttu-id="4e1ed-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4e1ed-127">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="4e1ed-128">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="4e1ed-128">'Read and write all alerts'</span></span>
<span data-ttu-id="4e1ed-129">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="4e1ed-129">Delegated (work or school account)</span></span> | <span data-ttu-id="4e1ed-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4e1ed-130">Alert.ReadWrite</span></span> | <span data-ttu-id="4e1ed-131">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="4e1ed-131">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="4e1ed-132">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="4e1ed-132">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="4e1ed-133">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Analisi degli avvisi" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="4e1ed-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="4e1ed-134">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="4e1ed-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4e1ed-135">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="4e1ed-135">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="4e1ed-136">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="4e1ed-136">Request headers</span></span>

<span data-ttu-id="4e1ed-137">Nome</span><span class="sxs-lookup"><span data-stu-id="4e1ed-137">Name</span></span> | <span data-ttu-id="4e1ed-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="4e1ed-138">Type</span></span> | <span data-ttu-id="4e1ed-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e1ed-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="4e1ed-140">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4e1ed-140">Authorization</span></span> | <span data-ttu-id="4e1ed-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-141">String</span></span> | <span data-ttu-id="4e1ed-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-142">Bearer {token}.</span></span> <span data-ttu-id="4e1ed-143">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-143">**Required**.</span></span>
<span data-ttu-id="4e1ed-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4e1ed-144">Content-Type</span></span> | <span data-ttu-id="4e1ed-145">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-145">String</span></span> | <span data-ttu-id="4e1ed-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-146">application/json.</span></span> <span data-ttu-id="4e1ed-147">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4e1ed-148">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="4e1ed-148">Request body</span></span>

<span data-ttu-id="4e1ed-149">Nel corpo della richiesta specificare i valori seguenti (sono necessari tutti):</span><span class="sxs-lookup"><span data-stu-id="4e1ed-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="4e1ed-150">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4e1ed-150">Property</span></span> | <span data-ttu-id="4e1ed-151">Tipo</span><span class="sxs-lookup"><span data-stu-id="4e1ed-151">Type</span></span> | <span data-ttu-id="4e1ed-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e1ed-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="4e1ed-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="4e1ed-153">eventTime</span></span> | <span data-ttu-id="4e1ed-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="4e1ed-154">DateTime(UTC)</span></span> | <span data-ttu-id="4e1ed-155">Ora precisa dell'evento come stringa, ottenuta dalla ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="4e1ed-156">Ad esempio, ```2018-08-03T16:45:21.7115183Z``` **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="4e1ed-157">reportId</span><span class="sxs-lookup"><span data-stu-id="4e1ed-157">reportId</span></span> | <span data-ttu-id="4e1ed-158">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-158">String</span></span> | <span data-ttu-id="4e1ed-159">ReportId dell'evento, ottenuto dalla ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="4e1ed-160">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-160">**Required**.</span></span>
<span data-ttu-id="4e1ed-161">machineId</span><span class="sxs-lookup"><span data-stu-id="4e1ed-161">machineId</span></span> | <span data-ttu-id="4e1ed-162">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-162">String</span></span> | <span data-ttu-id="4e1ed-163">ID del dispositivo in cui è stato identificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="4e1ed-164">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-164">**Required**.</span></span>
<span data-ttu-id="4e1ed-165">gravità</span><span class="sxs-lookup"><span data-stu-id="4e1ed-165">severity</span></span> | <span data-ttu-id="4e1ed-166">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-166">String</span></span> | <span data-ttu-id="4e1ed-167">Gravità dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-167">Severity of the alert.</span></span> <span data-ttu-id="4e1ed-168">I valori della proprietà sono: 'Low', 'Medium' e 'High'.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="4e1ed-169">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-169">**Required**.</span></span>
<span data-ttu-id="4e1ed-170">title</span><span class="sxs-lookup"><span data-stu-id="4e1ed-170">title</span></span> | <span data-ttu-id="4e1ed-171">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-171">String</span></span> | <span data-ttu-id="4e1ed-172">Titolo dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-172">Title for the alert.</span></span> <span data-ttu-id="4e1ed-173">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-173">**Required**.</span></span>
<span data-ttu-id="4e1ed-174">descrizione</span><span class="sxs-lookup"><span data-stu-id="4e1ed-174">description</span></span> | <span data-ttu-id="4e1ed-175">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-175">String</span></span> | <span data-ttu-id="4e1ed-176">Descrizione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-176">Description of the alert.</span></span> <span data-ttu-id="4e1ed-177">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-177">**Required**.</span></span>
<span data-ttu-id="4e1ed-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="4e1ed-178">recommendedAction</span></span>| <span data-ttu-id="4e1ed-179">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-179">String</span></span> | <span data-ttu-id="4e1ed-180">Azione consigliata da parte del responsabile della sicurezza durante l'analisi dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="4e1ed-181">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-181">**Required**.</span></span>
<span data-ttu-id="4e1ed-182">category</span><span class="sxs-lookup"><span data-stu-id="4e1ed-182">category</span></span>| <span data-ttu-id="4e1ed-183">Stringa</span><span class="sxs-lookup"><span data-stu-id="4e1ed-183">String</span></span> | <span data-ttu-id="4e1ed-184">Categoria dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-184">Category of the alert.</span></span> <span data-ttu-id="4e1ed-185">I valori delle proprietà sono: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="4e1ed-186">Risposta</span><span class="sxs-lookup"><span data-stu-id="4e1ed-186">Response</span></span>

<span data-ttu-id="4e1ed-187">Se ha esito positivo, questo metodo restituisce 200 OK e un nuovo oggetto [avviso](alerts.md) nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="4e1ed-188">Se l'evento con le proprietà specificate (_reportId_, _eventTime_ e _machineId_) non è stato trovato - 404 Not Found.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="4e1ed-189">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e1ed-189">Example</span></span>

### <a name="request"></a><span data-ttu-id="4e1ed-190">Richiesta</span><span class="sxs-lookup"><span data-stu-id="4e1ed-190">Request</span></span>

<span data-ttu-id="4e1ed-191">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4e1ed-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
