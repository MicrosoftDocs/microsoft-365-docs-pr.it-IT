---
title: Trasmettere Microsoft 365 eventi defender al tuo account Archiviazione
description: Scopri come configurare Microsoft 365 Defender per trasmettere eventi di ricerca avanzata al Archiviazione account.
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
ms.openlocfilehash: 1a1d6b63bcdf21535f36b23d4a30e5ea01833c36
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729993"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="96386-104">Configurare Microsoft 365 Defender per trasmettere eventi di ricerca avanzata al Archiviazione account</span><span class="sxs-lookup"><span data-stu-id="96386-104">Configure  Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="96386-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="96386-105">**Applies to:**</span></span>
- [<span data-ttu-id="96386-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96386-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="96386-107">Informazioni preliminari:</span><span class="sxs-lookup"><span data-stu-id="96386-107">Before you begin:</span></span>

1. <span data-ttu-id="96386-108">Creare un [Archiviazione nel](/azure/storage/common/storage-account-overview) tenant.</span><span class="sxs-lookup"><span data-stu-id="96386-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="96386-109">Accedere al [tenant di Azure,](https://ms.portal.azure.com/)passare a Sottoscrizioni > La sottoscrizione > provider di risorse **> registrarsi a Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="96386-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="96386-110">Abilita flusso di dati non elaborati:</span><span class="sxs-lookup"><span data-stu-id="96386-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="96386-111">Accedere a Microsoft 365 [Centro sicurezza Defender](https://security.microsoft.com) come ***Amministratore** globale _ o _* Amministratore _della sicurezza_\*\*.</span><span class="sxs-lookup"><span data-stu-id="96386-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="96386-112">Vai alla [pagina Impostazioni esportazione dati](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="96386-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="96386-113">Fare clic **su Aggiungi impostazioni di esportazione dati**.</span><span class="sxs-lookup"><span data-stu-id="96386-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="96386-114">Scegliere un nome per le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="96386-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="96386-115">Scegliere **Inoltra eventi da Archiviazione di Azure**.</span><span class="sxs-lookup"><span data-stu-id="96386-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="96386-116">Digitare **l'ID Archiviazione account utente**.</span><span class="sxs-lookup"><span data-stu-id="96386-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="96386-117">Per ottenere **l'ID** risorsa account Archiviazione , passare alla pagina dell'account Archiviazione nella scheda Delle proprietà del portale di [Azure](https://ms.portal.azure.com/) > > copiare il testo in ID risorsa **account** Archiviazione :</span><span class="sxs-lookup"><span data-stu-id="96386-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![Immagine della risorsa hub eventi ID1](images/storage-account-resource-id.png)

7. <span data-ttu-id="96386-119">Scegli gli eventi che vuoi trasmettere e fai clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="96386-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="96386-120">Schema degli eventi nell'account Archiviazione:</span><span class="sxs-lookup"><span data-stu-id="96386-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="96386-121">Verrà creato un contenitore BLOB per ogni tipo di evento:</span><span class="sxs-lookup"><span data-stu-id="96386-121">A blob container will be created for each event type:</span></span> 

  ![Immagine della risorsa hub eventi ID2](images/storage-account-event-schema.png)

- <span data-ttu-id="96386-123">Lo schema di ogni riga di un BLOB è il codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="96386-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="96386-124">Ogni BLOB contiene più righe.</span><span class="sxs-lookup"><span data-stu-id="96386-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="96386-125">Ogni riga contiene il nome dell'evento, l'ora in cui Defender per Endpoint ha ricevuto l'evento, il tenant a cui appartiene (si otterrà solo gli eventi dal tenant) e l'evento in formato JSON in una proprietà denominata "proprietà".</span><span class="sxs-lookup"><span data-stu-id="96386-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="96386-126">Per altre informazioni sullo schema degli eventi Microsoft 365 Defender, vedi [Panoramica di Advanced Hunting.](../defender/advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="96386-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="96386-127">Mapping dei tipi di dati:</span><span class="sxs-lookup"><span data-stu-id="96386-127">Data types mapping:</span></span>

<span data-ttu-id="96386-128">Per ottenere i tipi di dati per le proprietà degli eventi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="96386-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="96386-129">Accedi al centro [Microsoft 365 sicurezza](https://security.microsoft.com) e vai alla pagina [Ricerca avanzata.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="96386-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="96386-130">Eseguire la query seguente per ottenere il mapping dei tipi di dati per ogni evento:</span><span class="sxs-lookup"><span data-stu-id="96386-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="96386-131">Ecco un esempio di evento Info dispositivo:</span><span class="sxs-lookup"><span data-stu-id="96386-131">Here is an example for Device Info event:</span></span> 

  ![Immagine della risorsa hub eventi ID3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="96386-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="96386-133">Related topics</span></span>
- [<span data-ttu-id="96386-134">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="96386-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="96386-135">Microsoft 365 Defender Streaming API</span><span class="sxs-lookup"><span data-stu-id="96386-135">Microsoft 365 Defender Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="96386-136">Trasmettere Microsoft 365 eventi di Defender all'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="96386-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="96386-137">Archiviazione di Azure Documentazione dell'account</span><span class="sxs-lookup"><span data-stu-id="96386-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
