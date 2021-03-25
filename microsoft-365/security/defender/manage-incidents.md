---
title: Gestire gli eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come assegnare, aggiornare lo stato,
keywords: evento imprevisto, eventi imprevisti, avvisi, avvisi correlati, assegnare, aggiornare, stato, gestire, classificazione, microsoft, 365, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4e216f841c8728b1cabd98a931e7326f53344a74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064677"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="90430-104">Gestire gli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90430-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="90430-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="90430-105">**Applies to:**</span></span>
- <span data-ttu-id="90430-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90430-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="90430-107">La gestione degli eventi è fondamentale per garantire il controllo e la soluzione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="90430-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="90430-108">In Microsoft 365 Defender hai accesso alla gestione degli eventi imprevisti su dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="90430-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="90430-109">È possibile gestire gli eventi selezionandone uno dalla **Coda degli eventi imprevisti**.</span><span class="sxs-lookup"><span data-stu-id="90430-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="90430-110">È possibile modificare il nome di un evento, risolverlo, impostarne la classificazione e la determinazione.</span><span class="sxs-lookup"><span data-stu-id="90430-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="90430-111">Inoltre, è possibile assegnare l'evento a se stessi, aggiungere tag e commenti.</span><span class="sxs-lookup"><span data-stu-id="90430-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="90430-112">Se durante l'analisi si vogliono spostare gli avvisi da un evento all'altro è possibile eseguire l'operazione anche dalla scheda Avvisi, creando così un evento più grande oppure più piccolo che includa tutti gli avvisi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="90430-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="90430-113">Modificare il nome di un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="90430-113">Edit incident name</span></span>
<span data-ttu-id="90430-114">Agli eventi imprevisti viene assegnato automaticamente un nome in base agli attributi degli avvisi, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="90430-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="90430-115">In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="90430-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="90430-116">Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="90430-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="90430-117">È possibile modificare il nome dell'evento per allinearlo alla convenzione di denominazione preferita.</span><span class="sxs-lookup"><span data-stu-id="90430-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="90430-118">Gli eventi imprevisti che si verificavano prima dell'implementazione della funzionalità di denominazione automatica degli eventi imprevisti manterranno il nome.</span><span class="sxs-lookup"><span data-stu-id="90430-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="90430-119">Assegnare gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="90430-119">Assign incidents</span></span>
<span data-ttu-id="90430-120">Se un evento non è stato ancora assegnato, è possibile selezionare **Assegna a me** per assegnare l'evento a se stessi.</span><span class="sxs-lookup"><span data-stu-id="90430-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="90430-121">In questo modo si assume la proprietà non solo dell'evento, ma anche di tutti gli avvisi associati.</span><span class="sxs-lookup"><span data-stu-id="90430-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="90430-122">Impostare lo stato e la classificazione</span><span class="sxs-lookup"><span data-stu-id="90430-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="90430-123">Stato di un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="90430-123">Incident status</span></span>
<span data-ttu-id="90430-124">È possibile categorizzare gli eventi imprevisti, ad esempio **Attivo** oppure **Risolto**, modificando lo stato durante il corso dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="90430-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="90430-125">Questo consente di organizzare e gestire il modo in cui il team può rispondere agli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="90430-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="90430-126">Ad esempio, l'analista SOC può esaminare gli eventi **Attivi** e urgenti del giorno e decidere di assegnarli a se stesso per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="90430-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="90430-127">In alternativa, può impostare l'evento come **Risolto** se l'evento è stato corretto.</span><span class="sxs-lookup"><span data-stu-id="90430-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="90430-128">La risoluzione di un evento imprevisto chiude automaticamente tutti gli avvisi ancora aperti che fanno parte dell'evento.</span><span class="sxs-lookup"><span data-stu-id="90430-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="90430-129">Classificazione e determinazione</span><span class="sxs-lookup"><span data-stu-id="90430-129">Classification and determination</span></span>
<span data-ttu-id="90430-130">È possibile scegliere di non impostare una classificazione oppure decidere di specificare se un evento è vero o falso.</span><span class="sxs-lookup"><span data-stu-id="90430-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="90430-131">Così facendo, il team può visualizzare i criteri e imparare a usarli.</span><span class="sxs-lookup"><span data-stu-id="90430-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="90430-132">Aggiungere commenti</span><span class="sxs-lookup"><span data-stu-id="90430-132">Add comments</span></span>
<span data-ttu-id="90430-133">È possibile aggiungere commenti e visualizzare gli eventi cronologici relativi a un imprevisto per visualizzare le precedenti modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="90430-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="90430-134">Ogni volta che viene apportata una modifica o aggiunto un commento a un avviso, l'evento viene registrato nella sezione Commenti e cronologia.</span><span class="sxs-lookup"><span data-stu-id="90430-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="90430-135">I commenti aggiunti vengono visualizzati istantaneamente nel pannello.</span><span class="sxs-lookup"><span data-stu-id="90430-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="90430-136">Aggiungere tag agli eventi</span><span class="sxs-lookup"><span data-stu-id="90430-136">Add incident tags</span></span>
<span data-ttu-id="90430-137">È possibile aggiungere tag personalizzati a un evento, ad esempio per contrassegnare un insieme di eventi imprevisti con caratteristiche comuni.</span><span class="sxs-lookup"><span data-stu-id="90430-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="90430-138">In seguito è possibile filtrare la coda di tutti gli eventi imprevisti che contengono un tag specifico.</span><span class="sxs-lookup"><span data-stu-id="90430-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
