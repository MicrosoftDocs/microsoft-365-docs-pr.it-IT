---
title: Gestire gli eventi imprevisti di Microsoft Defender ATP
description: Gestire gli eventi imprevisti assegnandolo, aggiornandone lo stato o impostandone la classificazione.
keywords: incidenti, gestire, assegnare, stato, classificazione, avviso vero, falso avviso
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b8b5e806d09f08a12c090a1055f2c165f25b7ea1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185812"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="1d3a9-104">Gestire gli eventi imprevisti di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d3a9-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1d3a9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1d3a9-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d3a9-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1d3a9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d3a9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d3a9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1d3a9-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1d3a9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d3a9-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1d3a9-110">La gestione degli incidenti è una parte importante di ogni operazione di cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="1d3a9-111">È possibile gestire gli eventi imprevisti selezionando un evento imprevisto nella coda Eventi imprevisti **o** nel **riquadro Gestione eventi imprevisti.**</span><span class="sxs-lookup"><span data-stu-id="1d3a9-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="1d3a9-112">Se si seleziona un evento imprevisto dalla **coda** Eventi imprevisti, viene visualizzato il **riquadro Gestione** eventi imprevisti in cui è possibile aprire la pagina dell'evento imprevisto per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Immagine del riquadro di gestione degli eventi imprevisti](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="1d3a9-114">È possibile assegnare eventi imprevisti a se stessi, modificare lo stato e la classificazione, rinominare o commentarli per tenere traccia dello stato.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="1d3a9-115">Per un'ulteriore visibilità a colpo d'occhio, i nomi degli eventi imprevisti vengono generati automaticamente in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="1d3a9-116">In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="1d3a9-117">Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="1d3a9-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="1d3a9-118">Gli eventi imprevisti esistenti prima dell'implementazione della denominazione automatica degli eventi imprevisti manterranno i nomi.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Immagine della pagina dei dettagli dell'evento imprevisto](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="1d3a9-120">Assegnare gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="1d3a9-120">Assign incidents</span></span>
<span data-ttu-id="1d3a9-121">Se non è stato ancora assegnato un evento imprevisto, è possibile selezionare Assegna a **me** per assegnare l'evento a se stessi.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="1d3a9-122">In questo modo si assume la proprietà non solo dell'evento, ma anche di tutti gli avvisi associati.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="1d3a9-123">Impostare lo stato e la classificazione</span><span class="sxs-lookup"><span data-stu-id="1d3a9-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="1d3a9-124">Stato di un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="1d3a9-124">Incident status</span></span>
<span data-ttu-id="1d3a9-125">È possibile categorizzare gli eventi imprevisti, ad esempio **Attivo** oppure **Risolto**, modificando lo stato durante il corso dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="1d3a9-126">Questo consente di organizzare e gestire il modo in cui il team può rispondere agli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="1d3a9-127">Ad esempio, l'analista  SoC può esaminare gli incidenti attivi urgenti del giorno e decidere di assegnarli a se stesso per le indagini.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="1d3a9-128">In alternativa, l'analista SoC potrebbe impostare l'evento come **Risolto** se l'evento è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="1d3a9-129">Classificazione</span><span class="sxs-lookup"><span data-stu-id="1d3a9-129">Classification</span></span>
<span data-ttu-id="1d3a9-130">È possibile scegliere di non impostare una classificazione oppure decidere di specificare se un evento è vero o falso.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="1d3a9-131">Così facendo, il team può visualizzare i criteri e imparare a usarli.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="1d3a9-132">Aggiungere commenti</span><span class="sxs-lookup"><span data-stu-id="1d3a9-132">Add comments</span></span>
<span data-ttu-id="1d3a9-133">È possibile aggiungere commenti e visualizzare gli eventi cronologici relativi a un imprevisto per visualizzare le precedenti modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="1d3a9-134">Ogni volta che viene apportata una modifica o aggiunto un commento a un avviso, l'evento viene registrato nella sezione Commenti e cronologia.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="1d3a9-135">I commenti aggiunti vengono visualizzati istantaneamente nel pannello.</span><span class="sxs-lookup"><span data-stu-id="1d3a9-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="1d3a9-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1d3a9-136">Related topics</span></span>
- [<span data-ttu-id="1d3a9-137">Coda eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="1d3a9-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="1d3a9-138">Visualizzare e organizzare la coda eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="1d3a9-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="1d3a9-139">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="1d3a9-139">Investigate incidents</span></span>](investigate-incidents.md)
