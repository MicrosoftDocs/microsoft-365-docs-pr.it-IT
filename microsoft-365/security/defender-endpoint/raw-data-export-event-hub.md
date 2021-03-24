---
title: Trasmettere gli eventi di Microsoft Defender for Endpoint agli hub eventi di Azure
description: Scopri come configurare Microsoft Defender ATP per trasmettere eventi di ricerca avanzata all'hub eventi.
keywords: esportazione di dati non elaborati, API di streaming, API, Hub eventi di Azure, archiviazione di Azure, account di archiviazione, Ricerca avanzata, condivisione di dati non elaborati
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
ms.openlocfilehash: 231ba79e1d66eee263b6c1a4335f0a7b54eeb75d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063869"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="503c3-104">Configurare Microsoft Defender per Endpoint per trasmettere gli eventi di ricerca avanzata agli hub eventi di Azure</span><span class="sxs-lookup"><span data-stu-id="503c3-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="503c3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="503c3-105">**Applies to:**</span></span>

- [<span data-ttu-id="503c3-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="503c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="503c3-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="503c3-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="503c3-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="503c3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="503c3-109">Informazioni preliminari:</span><span class="sxs-lookup"><span data-stu-id="503c3-109">Before you begin:</span></span>

1. <span data-ttu-id="503c3-110">Creare un [hub eventi](https://docs.microsoft.com/azure/event-hubs/) nel tenant.</span><span class="sxs-lookup"><span data-stu-id="503c3-110">Create an [event hub](https://docs.microsoft.com/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="503c3-111">Accedere al [tenant di Azure,](https://ms.portal.azure.com/)passare a \*\*Sottoscrizioni > La sottoscrizione > provider di risorse > registrarsi a **Microsoft.insights**.</span><span class="sxs-lookup"><span data-stu-id="503c3-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to **Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="503c3-112">Abilita flusso di dati non elaborati:</span><span class="sxs-lookup"><span data-stu-id="503c3-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="503c3-113">Accedere a [Microsoft Defender Security Center](https://securitycenter.windows.com) come ***Amministratore** globale _ o _* Amministratore _della sicurezza_\*\*.</span><span class="sxs-lookup"><span data-stu-id="503c3-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="503c3-114">Vai alla pagina [Impostazioni esportazione dati](https://securitycenter.windows.com/interoperability/dataexport) in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="503c3-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="503c3-115">Fare clic **su Aggiungi impostazioni di esportazione dati**.</span><span class="sxs-lookup"><span data-stu-id="503c3-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="503c3-116">Scegliere un nome per le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="503c3-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="503c3-117">Scegliere **Inoltra eventi a Hub eventi di Azure**.</span><span class="sxs-lookup"><span data-stu-id="503c3-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="503c3-118">Digitare il **nome degli hub eventi e** l'ID risorsa Hub **eventi**.</span><span class="sxs-lookup"><span data-stu-id="503c3-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="503c3-119">Per ottenere **l'ID** risorsa Hub eventi, passare alla pagina dello spazio dei nomi Hub eventi di Azure nella scheda Proprietà di [Azure](https://ms.portal.azure.com/) > > copiare il testo in **ID risorsa**:</span><span class="sxs-lookup"><span data-stu-id="503c3-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![Immagine della risorsa hub eventi ID1](images/event-hub-resource-id.png)

7. <span data-ttu-id="503c3-121">Scegli gli eventi che vuoi trasmettere e fai clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="503c3-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="503c3-122">Schema degli eventi negli hub eventi di Azure:</span><span class="sxs-lookup"><span data-stu-id="503c3-122">The schema of the events in Azure Event Hubs:</span></span>

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="503c3-123">Ogni messaggio dell'hub eventi in Hub eventi di Azure contiene un elenco di record.</span><span class="sxs-lookup"><span data-stu-id="503c3-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="503c3-124">Ogni record contiene il nome dell'evento, l'ora in cui Microsoft Defender for Endpoint ha ricevuto l'evento, il tenant a cui appartiene (si otterrà solo gli eventi dal tenant) e l'evento in formato JSON in una proprietà denominata "**properties**".</span><span class="sxs-lookup"><span data-stu-id="503c3-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="503c3-125">Per altre informazioni sullo schema degli eventi di Microsoft Defender for Endpoint, vedi [Panoramica di Advanced Hunting.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="503c3-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="503c3-126">In Ricerca avanzata, la **tabella DeviceInfo** contiene una colonna denominata **MachineGroup** che contiene il gruppo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="503c3-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="503c3-127">Anche qui ogni evento verrà decorato con questa colonna.</span><span class="sxs-lookup"><span data-stu-id="503c3-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="503c3-128">Per [altre informazioni, vedi Gruppi](machine-groups.md) di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="503c3-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="503c3-129">Mapping dei tipi di dati:</span><span class="sxs-lookup"><span data-stu-id="503c3-129">Data types mapping:</span></span>

<span data-ttu-id="503c3-130">Per ottenere i tipi di dati per le proprietà dell'evento, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="503c3-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="503c3-131">Accedi a [Microsoft Defender Security Center](https://securitycenter.windows.com) e vai alla pagina Ricerca [avanzata.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="503c3-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="503c3-132">Eseguire la query seguente per ottenere il mapping dei tipi di dati per ogni evento:</span><span class="sxs-lookup"><span data-stu-id="503c3-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="503c3-133">Ecco un esempio di evento Info dispositivo:</span><span class="sxs-lookup"><span data-stu-id="503c3-133">Here is an example for Device Info event:</span></span> 

  ![Immagine della risorsa hub eventi ID2](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="503c3-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="503c3-135">Related topics</span></span>
- [<span data-ttu-id="503c3-136">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="503c3-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="503c3-137">Microsoft Defender for Endpoint streaming API</span><span class="sxs-lookup"><span data-stu-id="503c3-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="503c3-138">Trasmettere gli eventi di Microsoft Defender for Endpoint al tuo account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="503c3-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="503c3-139">Documentazione di Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="503c3-139">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="503c3-140">Risolvere i problemi di connettività - Hub eventi di Azure</span><span class="sxs-lookup"><span data-stu-id="503c3-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
