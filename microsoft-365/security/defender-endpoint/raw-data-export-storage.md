---
title: Trasmettere gli eventi di Microsoft Defender for Endpoint al tuo account di archiviazione
description: Scopri come configurare Microsoft Defender ATP per trasmettere eventi di ricerca avanzata al tuo account di archiviazione.
keywords: esportazione di dati non elaborati, API di streaming, API, hub eventi, archiviazione di Azure, account di archiviazione, ricerca avanzata, condivisione di dati non elaborati
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
ms.openlocfilehash: 9f1eb79bbf617afad58b7e4d70e1f40e422f9046
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063850"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="d873a-104">Configurare Microsoft Defender per Endpoint per trasmettere eventi di ricerca avanzata al tuo account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="d873a-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d873a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d873a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d873a-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d873a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="d873a-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d873a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d873a-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d873a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="d873a-109">Informazioni preliminari:</span><span class="sxs-lookup"><span data-stu-id="d873a-109">Before you begin:</span></span>

1. <span data-ttu-id="d873a-110">Creare un [account di archiviazione](https://docs.microsoft.com/azure/storage/common/storage-account-overview) nel tenant.</span><span class="sxs-lookup"><span data-stu-id="d873a-110">Create a [Storage account](https://docs.microsoft.com/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="d873a-111">Accedere al [tenant di Azure,](https://ms.portal.azure.com/)passare a Sottoscrizioni > La sottoscrizione > provider di risorse **> registrarsi a Microsoft.insights**.</span><span class="sxs-lookup"><span data-stu-id="d873a-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="d873a-112">Abilita flusso di dati non elaborati:</span><span class="sxs-lookup"><span data-stu-id="d873a-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="d873a-113">Accedere a [Microsoft Defender for Endpoint Portal](https://securitycenter.windows.com) come amministratore globale _ o _\* Amministratore della _sicurezza_\*\*.</span><span class="sxs-lookup"><span data-stu-id="d873a-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="d873a-114">Vai alla [pagina Impostazioni esportazione dati](https://securitycenter.windows.com/interoperability/dataexport) in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="d873a-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="d873a-115">Fare clic **su Aggiungi impostazioni di esportazione dati**.</span><span class="sxs-lookup"><span data-stu-id="d873a-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="d873a-116">Scegliere un nome per le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d873a-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="d873a-117">Scegliere **Inoltra eventi a Archiviazione di Azure**.</span><span class="sxs-lookup"><span data-stu-id="d873a-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="d873a-118">Digitare **l'ID risorsa dell'account di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="d873a-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="d873a-119">Per ottenere l'ID risorsa **dell'account** di archiviazione, passare alla pagina Account di archiviazione nella scheda Proprietà > portale di [Azure](https://ms.portal.azure.com/) > copiare il testo in ID risorsa **account di archiviazione**:</span><span class="sxs-lookup"><span data-stu-id="d873a-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![Immagine della risorsa hub eventi ID1](images/storage-account-resource-id.png)

7. <span data-ttu-id="d873a-121">Scegli gli eventi che vuoi trasmettere e fai clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="d873a-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="d873a-122">Schema degli eventi nell'account di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="d873a-122">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="d873a-123">Verrà creato un contenitore BLOB per ogni tipo di evento:</span><span class="sxs-lookup"><span data-stu-id="d873a-123">A blob container will be created for each event type:</span></span> 

  ![Immagine della risorsa hub eventi ID2](images/storage-account-event-schema.png)

- <span data-ttu-id="d873a-125">Lo schema di ogni riga di un BLOB è il codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="d873a-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="d873a-126">Ogni BLOB contiene più righe.</span><span class="sxs-lookup"><span data-stu-id="d873a-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="d873a-127">Ogni riga contiene il nome dell'evento, l'ora in cui Defender per Endpoint ha ricevuto l'evento, il tenant a cui appartiene (si otterrà solo gli eventi dal tenant) e l'evento in formato JSON in una proprietà denominata "proprietà".</span><span class="sxs-lookup"><span data-stu-id="d873a-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="d873a-128">Per altre informazioni sullo schema degli eventi di Microsoft Defender for Endpoint, vedi [Panoramica di Advanced Hunting.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d873a-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="d873a-129">In Ricerca avanzata, la **tabella DeviceInfo** contiene una colonna denominata **MachineGroup** che contiene il gruppo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d873a-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="d873a-130">Anche qui ogni evento verrà decorato con questa colonna.</span><span class="sxs-lookup"><span data-stu-id="d873a-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="d873a-131">Per [altre informazioni, vedi Gruppi](machine-groups.md) di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d873a-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="d873a-132">Mapping dei tipi di dati:</span><span class="sxs-lookup"><span data-stu-id="d873a-132">Data types mapping:</span></span>

<span data-ttu-id="d873a-133">Per ottenere i tipi di dati per le proprietà degli eventi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d873a-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="d873a-134">Accedi a [Microsoft Defender Security Center](https://securitycenter.windows.com) e vai alla pagina Ricerca [avanzata.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="d873a-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="d873a-135">Eseguire la query seguente per ottenere il mapping dei tipi di dati per ogni evento:</span><span class="sxs-lookup"><span data-stu-id="d873a-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="d873a-136">Ecco un esempio di evento Info dispositivo:</span><span class="sxs-lookup"><span data-stu-id="d873a-136">Here is an example for Device Info event:</span></span> 

  ![Immagine della risorsa hub eventi ID3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="d873a-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d873a-138">Related topics</span></span>
- [<span data-ttu-id="d873a-139">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="d873a-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d873a-140">API di streaming di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d873a-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="d873a-141">Trasmettere gli eventi di Microsoft Defender for Endpoint al tuo account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="d873a-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="d873a-142">Documentazione relativa all'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="d873a-142">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
