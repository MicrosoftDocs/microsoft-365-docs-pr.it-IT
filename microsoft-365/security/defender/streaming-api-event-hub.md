---
title: Trasmettere Microsoft 365 eventi di Defender all'Hub eventi di Azure
description: Scopri come configurare Microsoft 365 Defender per trasmettere eventi di ricerca avanzata al tuo Hub eventi.
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
ms.openlocfilehash: 6f5d04d35c8c4fec18e1a689c51ecbc32d416adf
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903817"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a><span data-ttu-id="a05ac-104">Configurare Microsoft 365 Defender per trasmettere eventi di ricerca avanzata all'Hub eventi di Azure</span><span class="sxs-lookup"><span data-stu-id="a05ac-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a05ac-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a05ac-105">**Applies to:**</span></span>
- [<span data-ttu-id="a05ac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a05ac-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="a05ac-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a05ac-107">Before you begin</span></span>

1. <span data-ttu-id="a05ac-108">Creare un [hub eventi](/azure/event-hubs/) nel tenant.</span><span class="sxs-lookup"><span data-stu-id="a05ac-108">Create an [Event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="a05ac-109">Accedere al [tenant di Azure,](https://ms.portal.azure.com/)passare a Sottoscrizioni > La sottoscrizione > provider di risorse **> registrarsi a Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="a05ac-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="a05ac-110">Crea uno spazio dei nomi hub eventi, vai a Hub eventi **> Aggiungi** e seleziona il livello di prezzi, le unità di velocità effettiva e l'gonfiarsi automatico appropriato per il carico previsto.</span><span class="sxs-lookup"><span data-stu-id="a05ac-110">Create an Event Hub Namespace, go to **Event Hub > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="a05ac-111">Per ulteriori informazioni, vedere [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="a05ac-111">For more information, see [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

### <a name="add-contributor-permissions"></a><span data-ttu-id="a05ac-112">Aggiungere autorizzazioni di collaboratore</span><span class="sxs-lookup"><span data-stu-id="a05ac-112">Add contributor permissions</span></span> 
<span data-ttu-id="a05ac-113">Dopo aver creato lo spazio dei nomi Hub eventi, dovrai:</span><span class="sxs-lookup"><span data-stu-id="a05ac-113">Once the Event Hub namespace is created you will need to:</span></span>
1. <span data-ttu-id="a05ac-114">Definisci l'utente che accederà a Microsoft 365 Defender come Collaboratore.</span><span class="sxs-lookup"><span data-stu-id="a05ac-114">Define the user who will be logging into Microsoft 365 Defender as Contributor.</span></span>

2. <span data-ttu-id="a05ac-115">Se ci si connette a un'applicazione, aggiungere l'entità servizio di registrazione app come lettore, ricevitore di dati dell'hub eventi di Azure (questa operazione può essere eseguita anche a livello di gruppo di risorse o di sottoscrizione).</span><span class="sxs-lookup"><span data-stu-id="a05ac-115">If you are connecting to an application, add the App Registration Service Principal as Reader, Azure Event Hub Data Receiver (this can also be done at Resource Group or Subscription level).</span></span> 

    <span data-ttu-id="a05ac-116">Vai a Hub eventi spazio dei nomi > controllo di accesso **(IAM) > Aggiungi** e verifica in **Assegnazioni di ruolo**.</span><span class="sxs-lookup"><span data-stu-id="a05ac-116">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignments**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="a05ac-117">Abilitare lo streaming di dati non elaborati</span><span class="sxs-lookup"><span data-stu-id="a05ac-117">Enable raw data streaming</span></span>

1. <span data-ttu-id="a05ac-118">Accedere al Centro sicurezza [Microsoft 365 Defender](https://security.microsoft.com) come ***Amministratore** globale _ o _* Amministratore _della sicurezza_\*\*.</span><span class="sxs-lookup"><span data-stu-id="a05ac-118">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="a05ac-119">Vai alla pagina [Impostazioni API di streaming.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="a05ac-119">Go to the [Streaming API settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="a05ac-120">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a05ac-120">Click on **Add**.</span></span>

4. <span data-ttu-id="a05ac-121">Scegliere un nome per le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a05ac-121">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="a05ac-122">Scegliere **Inoltra eventi ad Hub eventi di Azure**.</span><span class="sxs-lookup"><span data-stu-id="a05ac-122">Choose **Forward events to Azure Event Hub**.</span></span>

6. <span data-ttu-id="a05ac-123">Puoi scegliere se esportare i dati dell'evento in un singolo hub eventi o per esportare ogni tabella di eventi in un hub eventi diverso nello spazio dei nomi Hub eventi.</span><span class="sxs-lookup"><span data-stu-id="a05ac-123">You can select if you want to export the event data to a single Event Hub, or to export each event table to a different event hub in your Event Hub namespace.</span></span> 

7. <span data-ttu-id="a05ac-124">Per esportare i dati dell'evento in un singolo hub eventi, immetti il nome **dell'hub eventi** e l'ID **risorsa Hub eventi.**</span><span class="sxs-lookup"><span data-stu-id="a05ac-124">To export the event data to a single Event Hub, enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="a05ac-125">Per ottenere **l'ID** risorsa Hub eventi, passare alla pagina dello spazio dei nomi hub eventi di [Azure](https://ms.portal.azure.com/)nella scheda Proprietà di Azure > copiare il testo in  >   ID **risorsa**:</span><span class="sxs-lookup"><span data-stu-id="a05ac-125">To get your **Event Hub resource ID**, go to your Azure Event Hub namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Immagine della risorsa Hub eventi ID1](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="a05ac-127">Scegli gli eventi che vuoi trasmettere e fai clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="a05ac-127">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hub"></a><span data-ttu-id="a05ac-128">Schema degli eventi nell'Hub eventi di Azure</span><span class="sxs-lookup"><span data-stu-id="a05ac-128">The schema of the events in Azure Event Hub</span></span>

```JSON
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="a05ac-129">Ogni messaggio dell'hub eventi in Hub eventi di Azure contiene un elenco di record.</span><span class="sxs-lookup"><span data-stu-id="a05ac-129">Each Event Hub message in Azure Event Hub contains list of records.</span></span>

- <span data-ttu-id="a05ac-130">Ogni record contiene il nome dell'evento, l'ora in cui Microsoft 365 Defender ha ricevuto l'evento, il tenant a cui appartiene (si otterrà solo gli eventi dal tenant) e l'evento in formato JSON in una proprietà denominata "**properties**".</span><span class="sxs-lookup"><span data-stu-id="a05ac-130">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="a05ac-131">Per altre informazioni sullo schema degli eventi Microsoft 365 Defender, vedi [Panoramica di Advanced Hunting.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a05ac-131">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="a05ac-132">In Ricerca avanzata, la **tabella DeviceInfo** contiene una colonna denominata **MachineGroup** che contiene il gruppo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a05ac-132">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="a05ac-133">Anche qui ogni evento verrà decorato con questa colonna.</span><span class="sxs-lookup"><span data-stu-id="a05ac-133">Here every event will be decorated with this column as well.</span></span> 




## <a name="data-types-mapping"></a><span data-ttu-id="a05ac-134">Mapping dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a05ac-134">Data types mapping</span></span>

<span data-ttu-id="a05ac-135">Per ottenere i tipi di dati per le proprietà dell'evento, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a05ac-135">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="a05ac-136">Accedi al centro [Microsoft 365 sicurezza](https://security.microsoft.com) e vai alla pagina [Ricerca avanzata.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="a05ac-136">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="a05ac-137">Eseguire la query seguente per ottenere il mapping dei tipi di dati per ogni evento:</span><span class="sxs-lookup"><span data-stu-id="a05ac-137">Run the following query to get the data types mapping for each event:</span></span>
 
   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="a05ac-138">Ecco un esempio di evento Info dispositivo:</span><span class="sxs-lookup"><span data-stu-id="a05ac-138">Here is an example for Device Info event:</span></span> 

  ![Immagine della risorsa Hub eventi Id2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="a05ac-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a05ac-140">Related topics</span></span>
- [<span data-ttu-id="a05ac-141">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="a05ac-141">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a05ac-142">Microsoft 365 Defender streaming API</span><span class="sxs-lookup"><span data-stu-id="a05ac-142">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="a05ac-143">Trasmettere Microsoft 365 eventi di Defender all'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="a05ac-143">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="a05ac-144">Documentazione dell'hub eventi di Azure</span><span class="sxs-lookup"><span data-stu-id="a05ac-144">Azure Event Hub documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="a05ac-145">Risolvere i problemi di connettività - Hub eventi di Azure</span><span class="sxs-lookup"><span data-stu-id="a05ac-145">Troubleshoot connectivity issues - Azure Event Hub</span></span>](/azure/event-hubs/troubleshooting-guide)
