---
title: Usare le etichette di riservatezza per definire la priorità della risposta agli eventi imprevisti
description: Informazioni su come usare le etichette di riservatezza per definire la priorità e analizzare gli eventi imprevisti
keywords: informazioni, protezione, dati, perdita, prevenzione,etichette, dlp, incidente, indagare, indagine
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
ms.openlocfilehash: bff490edcc79bc8f96e65c8b27586ca8b54e5bce
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186126"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="87ee4-104">Usare le etichette di riservatezza per definire la priorità della risposta agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="87ee4-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="87ee4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="87ee4-105">**Applies to:**</span></span>
- [<span data-ttu-id="87ee4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="87ee4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="87ee4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87ee4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="87ee4-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="87ee4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="87ee4-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="87ee4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="87ee4-110">Un tipico ciclo di vita avanzato delle minacce persistenti implica l'esfiltrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="87ee4-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="87ee4-111">In un incidente di sicurezza, è importante avere la possibilità di assegnare priorità alle indagini in cui i file sensibili potrebbero essere a rischio in modo che i dati e le informazioni aziendali siano protetti.</span><span class="sxs-lookup"><span data-stu-id="87ee4-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="87ee4-112">Defender for Endpoint consente di semplificare la definizione della priorità degli incidenti di sicurezza con l'uso delle etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="87ee4-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="87ee4-113">Le etichette di riservatezza identificano rapidamente gli incidenti che possono coinvolgere i dispositivi con informazioni riservate, ad esempio informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="87ee4-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="87ee4-114">Analizzare gli eventi imprevisti che coinvolgono dati sensibili</span><span class="sxs-lookup"><span data-stu-id="87ee4-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="87ee4-115">Informazioni su come usare le etichette di riservatezza dei dati per definire la priorità dell'analisi degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="87ee4-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="87ee4-116">Vengono rilevate etichette per Windows 10 versione 1809 o successiva.</span><span class="sxs-lookup"><span data-stu-id="87ee4-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="87ee4-117">In Microsoft Defender Security Center seleziona **Eventi imprevisti.**</span><span class="sxs-lookup"><span data-stu-id="87ee4-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="87ee4-118">Scorrere verso destra per visualizzare la **colonna Riservatezza dati.**</span><span class="sxs-lookup"><span data-stu-id="87ee4-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="87ee4-119">Questa colonna riflette le etichette di riservatezza che sono state osservate nei dispositivi correlati agli eventi imprevisti, fornendo un'indicazione se i file sensibili potrebbero essere influenzati dall'incidente.</span><span class="sxs-lookup"><span data-stu-id="87ee4-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![Immagine della colonna di riservatezza dei dati](images/data-sensitivity-column.png)

    <span data-ttu-id="87ee4-121">È inoltre possibile filtrare in base **alla riservatezza dei dati**</span><span class="sxs-lookup"><span data-stu-id="87ee4-121">You can also filter based on **Data sensitivity**</span></span> 

    ![Immagine del filtro di riservatezza dei dati](images/data-sensitivity-filter.png)

3. <span data-ttu-id="87ee4-123">Apri la pagina dell'evento imprevisto per analizzare ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="87ee4-123">Open the incident page to further investigate.</span></span>

    ![Immagine dei dettagli della pagina dell'evento imprevisto](images/incident-page.png)

4. <span data-ttu-id="87ee4-125">Seleziona la **scheda Dispositivi** per identificare i dispositivi che archiviano file con etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="87ee4-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![Immagine della scheda del dispositivo](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="87ee4-127">Seleziona i dispositivi che archiviano dati sensibili ed eserciti una ricerca nella sequenza temporale per identificare i file che potrebbero essere influenzati e quindi eserciti le azioni appropriate per garantire che i dati siano protetti.</span><span class="sxs-lookup"><span data-stu-id="87ee4-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="87ee4-128">Puoi limitare gli eventi visualizzati nella sequenza temporale del dispositivo cercando le etichette di riservatezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="87ee4-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="87ee4-129">In questo modo verranno visualizzati solo gli eventi associati ai file con il nome dell'etichetta specificato.</span><span class="sxs-lookup"><span data-stu-id="87ee4-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![Immagine della sequenza temporale del dispositivo con risultati di ricerca ristretti in base all'etichetta](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="87ee4-131">Questi punti dati vengono esposti anche tramite "DeviceFileEvents" nella ricerca avanzata, consentendo alle query avanzate e al rilevamento della pianificazione di prendere in considerazione le etichette di riservatezza e lo stato di protezione dei file.</span><span class="sxs-lookup"><span data-stu-id="87ee4-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
