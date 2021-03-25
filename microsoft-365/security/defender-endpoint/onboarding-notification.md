---
title: Creare una regola di notifica onboarding o offboarding
description: Ricevere una notifica quando viene utilizzato uno script di onboarding o offboarding locale.
keywords: onboarding, offboarding, locale, script, notifica, regola
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
ms.openlocfilehash: 5dfdfc6d14add33154ed4c2370bca458e752125d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187232"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a><span data-ttu-id="7c810-104">Creare una regola di notifica quando viene utilizzato uno script di onboarding o offboarding locale</span><span class="sxs-lookup"><span data-stu-id="7c810-104">Create a notification rule when a local onboarding or offboarding script is used</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7c810-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7c810-105">**Applies to:**</span></span>
- [<span data-ttu-id="7c810-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="7c810-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7c810-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c810-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="7c810-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7c810-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7c810-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7c810-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="7c810-110">Creare una regola di notifica in modo che quando viene utilizzato uno script di onboarding o offboarding locale, verrà inviata una notifica.</span><span class="sxs-lookup"><span data-stu-id="7c810-110">Create a notification rule so that when a local onboarding or offboarding script is used, you'll be notified.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="7c810-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7c810-111">Before you begin</span></span>
<span data-ttu-id="7c810-112">Dovrai avere accesso a:</span><span class="sxs-lookup"><span data-stu-id="7c810-112">You'll need to have access to:</span></span>
 - <span data-ttu-id="7c810-113">Microsoft Flow (piano di flusso 1 come minimo).</span><span class="sxs-lookup"><span data-stu-id="7c810-113">Microsoft Flow (Flow Plan 1 at a minimum).</span></span> <span data-ttu-id="7c810-114">Per ulteriori informazioni, vedere [Flow pricing page.](https://flow.microsoft.com/pricing/)</span><span class="sxs-lookup"><span data-stu-id="7c810-114">For more information, see [Flow pricing page](https://flow.microsoft.com/pricing/).</span></span>
 - <span data-ttu-id="7c810-115">Tabella di Azure o elenco o raccolta di SharePoint/SQL database</span><span class="sxs-lookup"><span data-stu-id="7c810-115">Azure Table or SharePoint List or Library / SQL DB</span></span>

## <a name="create-the-notification-flow"></a><span data-ttu-id="7c810-116">Creare il flusso di notifica</span><span class="sxs-lookup"><span data-stu-id="7c810-116">Create the notification flow</span></span>

1. <span data-ttu-id="7c810-117">In [flow.microsoft.com](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="7c810-117">In [flow.microsoft.com](https://flow.microsoft.com/).</span></span>

2. <span data-ttu-id="7c810-118">Passare a **Flussi > nuovo > programmato - da vuoto**.</span><span class="sxs-lookup"><span data-stu-id="7c810-118">Navigate to **My flows > New > Scheduled - from blank**.</span></span> 

    ![Immagine del flusso](images/new-flow.png)


3. <span data-ttu-id="7c810-120">Creare un flusso pianificato.</span><span class="sxs-lookup"><span data-stu-id="7c810-120">Build a scheduled flow.</span></span>
   1. <span data-ttu-id="7c810-121">Immettere un nome di flusso.</span><span class="sxs-lookup"><span data-stu-id="7c810-121">Enter a flow name.</span></span>
   2. <span data-ttu-id="7c810-122">Specificare l'inizio e l'ora.</span><span class="sxs-lookup"><span data-stu-id="7c810-122">Specify the start and time.</span></span>
   3. <span data-ttu-id="7c810-123">Specificare la frequenza.</span><span class="sxs-lookup"><span data-stu-id="7c810-123">Specify the frequency.</span></span> <span data-ttu-id="7c810-124">Ad esempio, ogni 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="7c810-124">For example, every 5 minutes.</span></span>

    ![Immagine del flusso di notifica](images/build-flow.png)

4. <span data-ttu-id="7c810-126">Seleziona il pulsante + per aggiungere una nuova azione.</span><span class="sxs-lookup"><span data-stu-id="7c810-126">Select the + button to add a new action.</span></span> <span data-ttu-id="7c810-127">La nuova azione sarà una richiesta HTTP all'API del Centro sicurezza Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="7c810-127">The new action will be an HTTP request to the Defender for Endpoint security center device(s) API.</span></span> <span data-ttu-id="7c810-128">Puoi anche sostituirlo con il "connettore WDATP" (azione: "Machines - Get list of machines").</span><span class="sxs-lookup"><span data-stu-id="7c810-128">You can also replace it with the out-of-the-box "WDATP Connector" (action: "Machines - Get list of machines").</span></span> 

    ![Immagine della ricorrenza e dell'azione di aggiunta](images/recurrence-add.png)


5. <span data-ttu-id="7c810-130">Immettere i campi HTTP seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c810-130">Enter the following HTTP fields:</span></span>

   - <span data-ttu-id="7c810-131">Metodo: "GET" come valore per ottenere l'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7c810-131">Method: "GET" as a value to get the list of devices.</span></span>
   - <span data-ttu-id="7c810-132">URI: immettere `https://api.securitycenter.microsoft.com/api/machines` .</span><span class="sxs-lookup"><span data-stu-id="7c810-132">URI: Enter `https://api.securitycenter.microsoft.com/api/machines`.</span></span>
   - <span data-ttu-id="7c810-133">Autenticazione: selezionare "Active Directory OAuth".</span><span class="sxs-lookup"><span data-stu-id="7c810-133">Authentication: Select "Active Directory OAuth".</span></span>
   - <span data-ttu-id="7c810-134">Tenant: accedi ad Azure Active Directory e passa ad https://portal.azure.com Azure Active Directory > **registrazioni delle app** e ottieni il valore dell'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="7c810-134">Tenant: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>
   - <span data-ttu-id="7c810-135">Gruppo di destinatari: `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span><span class="sxs-lookup"><span data-stu-id="7c810-135">Audience: `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span></span>
   - <span data-ttu-id="7c810-136">ID client: accedere ad Azure Active Directory > app e ottenere il https://portal.azure.com valore ID client. </span><span class="sxs-lookup"><span data-stu-id="7c810-136">Client ID: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and  get the Client ID value.</span></span>
   - <span data-ttu-id="7c810-137">Tipo di credenziale: selezionare "Segreto".</span><span class="sxs-lookup"><span data-stu-id="7c810-137">Credential Type: Select "Secret".</span></span>
   - <span data-ttu-id="7c810-138">Segreto: accedi ad Azure Active Directory e https://portal.azure.com passa ad Azure Active Directory > **registrazioni delle app** e ottieni il valore dell'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="7c810-138">Secret: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>

    ![Immagine delle condizioni HTTP](images/http-conditions.png)


6. <span data-ttu-id="7c810-140">Aggiungi un nuovo passaggio selezionando **Aggiungi nuova azione,** quindi cerca **Operazioni dati** e seleziona **Analizza JSON.**</span><span class="sxs-lookup"><span data-stu-id="7c810-140">Add a new step by selecting **Add new action** then search for **Data Operations** and select **Parse JSON**.</span></span>

    ![Immagine delle operazioni sui dati](images/data-operations.png)

7. <span data-ttu-id="7c810-142">Aggiungere Corpo nel **campo** Contenuto.</span><span class="sxs-lookup"><span data-stu-id="7c810-142">Add Body in the **Content** field.</span></span>

    ![Immagine dell'analisi JSON](images/parse-json.png)

8. <span data-ttu-id="7c810-144">Selezionare il **collegamento Usa payload di esempio per generare lo schema.**</span><span class="sxs-lookup"><span data-stu-id="7c810-144">Select the **Use sample payload to generate schema** link.</span></span>

    ![Immagine di json di analisi con payload](images/parse-json-schema.png)

9. <span data-ttu-id="7c810-146">Copiare e incollare il frammento JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="7c810-146">Copy and paste the following JSON snippet:</span></span>

    ```
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10.  <span data-ttu-id="7c810-147">Estrarre i valori dalla chiamata JSON e verificare se i dispositivi onboarded sono già registrati nell'elenco di SharePoint come esempio:</span><span class="sxs-lookup"><span data-stu-id="7c810-147">Extract the values from the JSON call and check if the onboarded device(s) is / are already registered at the SharePoint list as an example:</span></span>
- <span data-ttu-id="7c810-148">In caso affermativa, non verrà attivata alcuna notifica</span><span class="sxs-lookup"><span data-stu-id="7c810-148">If yes, no notification will be triggered</span></span>
- <span data-ttu-id="7c810-149">Se no, registrerà i nuovi dispositivi onboarded nell'elenco di SharePoint e verrà inviata una notifica al Defender per l'amministratore dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="7c810-149">If no, will register the new onboarded device(s) in the SharePoint list and a notification will be sent to the Defender for Endpoint admin</span></span>

    ![Immagine di applica a ogni](images/flow-apply.png)

    ![Immagine dell'applicazione a ognuno con gli elementi get](images/apply-to-each.png)

11. <span data-ttu-id="7c810-152">In **Condizione** aggiungere l'espressione seguente: "length(body('Get_items')?[' value'])" e impostare la condizione su uguale a 0.</span><span class="sxs-lookup"><span data-stu-id="7c810-152">Under **Condition**, add the following expression: "length(body('Get_items')?['value'])" and set the condition to equal to 0.</span></span>

    <span data-ttu-id="7c810-153">![Immagine dell'applicazione a ogni condizione](images/apply-to-each-value.png)</span><span class="sxs-lookup"><span data-stu-id="7c810-153">![Image of apply to each condition](images/apply-to-each-value.png)</span></span>  
    <span data-ttu-id="7c810-154">![Immagine di condition1 ](images/conditions-2.png) 
     ![ Immagine di condition2](images/condition3.png)</span><span class="sxs-lookup"><span data-stu-id="7c810-154">![Image of condition1](images/conditions-2.png) 
    ![Image of condition2](images/condition3.png)</span></span>  
<span data-ttu-id="7c810-155">![Immagine dell'invio di posta elettronica](images/send-email.png)</span><span class="sxs-lookup"><span data-stu-id="7c810-155">![Image of send email](images/send-email.png)</span></span>

## <a name="alert-notification"></a><span data-ttu-id="7c810-156">Notifica di avviso</span><span class="sxs-lookup"><span data-stu-id="7c810-156">Alert notification</span></span>
<span data-ttu-id="7c810-157">L'immagine seguente è un esempio di notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="7c810-157">The following image is an example of an email notification.</span></span>

![Immagine della notifica tramite posta elettronica](images/alert-notification.png)


## <a name="tips"></a><span data-ttu-id="7c810-159">Suggerimenti </span><span class="sxs-lookup"><span data-stu-id="7c810-159">Tips</span></span>

- <span data-ttu-id="7c810-160">Puoi filtrare qui usando solo lastSeen:</span><span class="sxs-lookup"><span data-stu-id="7c810-160">You can filter here using lastSeen only:</span></span>
    - <span data-ttu-id="7c810-161">Ogni 60 minuti:</span><span class="sxs-lookup"><span data-stu-id="7c810-161">Every 60 min:</span></span>
      - <span data-ttu-id="7c810-162">Prendere tutti i dispositivi visti per l'ultima volta negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="7c810-162">Take all devices last seen in the past 7 days.</span></span> 

- <span data-ttu-id="7c810-163">Per ogni dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7c810-163">For each device:</span></span> 
    - <span data-ttu-id="7c810-164">Se l'ultima proprietà vista si trova nell'intervallo di un'ora di [-7 giorni, -7 giorni + 60 minuti ] -> Avviso per la possibilità di offboarding.</span><span class="sxs-lookup"><span data-stu-id="7c810-164">If last seen property is on the one hour interval of [-7 days, -7days + 60 minutes ] -> Alert for offboarding possibility.</span></span>
    - <span data-ttu-id="7c810-165">Se viene visualizzato per la prima volta nell'ultima > avviso per l'onboarding.</span><span class="sxs-lookup"><span data-stu-id="7c810-165">If first seen is on the past hour -> Alert for onboarding.</span></span>

<span data-ttu-id="7c810-166">In questa soluzione non saranno presenti avvisi duplicati: esistono tenant con numerosi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7c810-166">In this solution you will not have duplicate alerts: There are tenants that have numerous devices.</span></span> <span data-ttu-id="7c810-167">Ottenere tutti questi dispositivi potrebbe essere molto costoso e potrebbe richiedere il paging.</span><span class="sxs-lookup"><span data-stu-id="7c810-167">Getting all those devices might be very expensive and might require paging.</span></span>

<span data-ttu-id="7c810-168">È possibile suddividerlo in due query:</span><span class="sxs-lookup"><span data-stu-id="7c810-168">You can split it to two queries:</span></span> 
1.  <span data-ttu-id="7c810-169">Per l'offboarding prendere solo questo intervallo utilizzando il $filter OData e notificare solo se le condizioni sono soddisfatte.</span><span class="sxs-lookup"><span data-stu-id="7c810-169">For offboarding take only this interval using the OData $filter and only notify if the conditions are met.</span></span>
2.  <span data-ttu-id="7c810-170">Prendi tutti i dispositivi visti per l'ultima volta nell'ultima ora e controlla la proprietà first seen per loro (se la prima proprietà vista è nell'ultima ora, deve essere presente anche l'ultima proprietà vista).</span><span class="sxs-lookup"><span data-stu-id="7c810-170">Take all devices last seen in the past hour and check first seen property for them (if the first seen property is on the past hour, the last seen must be there too).</span></span> 

