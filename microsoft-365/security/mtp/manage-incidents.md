---
title: Gestire gli eventi imprevisti in Microsoft Threat Protection
description: Informazioni su come assegnare, aggiornare lo stato,
keywords: evento imprevisto, eventi imprevisti, avvisi, avvisi correlati, assegnare, aggiornare, stato, gestire, classificazione, microsoft, 365, M365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f711cc2ff38f15dfd22097e37a1dec42719eb5aa
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148115"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="c4d96-104">Gestire gli eventi imprevisti in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c4d96-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="c4d96-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c4d96-105">**Applies to:**</span></span>
- <span data-ttu-id="c4d96-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c4d96-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c4d96-107">La gestione degli eventi è fondamentale per garantire il controllo e la soluzione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="c4d96-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="c4d96-108">In Microsoft Threat Protection si dispone dell'accesso alla gestione degli eventi imprevisti su dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="c4d96-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="c4d96-109">È possibile gestire gli eventi selezionandone uno dalla **Coda degli eventi imprevisti**.</span><span class="sxs-lookup"><span data-stu-id="c4d96-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="c4d96-110">È possibile modificare il nome di un evento, risolverlo, impostarne la classificazione e la determinazione.</span><span class="sxs-lookup"><span data-stu-id="c4d96-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="c4d96-111">Inoltre, è possibile assegnare l'evento a se stessi, aggiungere tag e commenti.</span><span class="sxs-lookup"><span data-stu-id="c4d96-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="c4d96-112">Se durante l'analisi si vogliono spostare gli avvisi da un evento all'altro è possibile eseguire l'operazione anche dalla scheda Avvisi, creando così un evento più grande oppure più piccolo che includa tutti gli avvisi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="c4d96-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="c4d96-113">Modificare il nome di un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="c4d96-113">Edit incident name</span></span>
<span data-ttu-id="c4d96-114">Per impostazione predefinita, a un evento viene assegnato un numero.</span><span class="sxs-lookup"><span data-stu-id="c4d96-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="c4d96-115">È possibile modificare il nome dell'evento per allinearlo alla convenzione di denominazione preferita.</span><span class="sxs-lookup"><span data-stu-id="c4d96-115">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!TIP]
> <span data-ttu-id="c4d96-116">Per una maggiore visibilità a colpo d'occhio, la denominazione degli incidenti automatici, attualmente in anteprima pubblica, genera nomi di incidenti basati su attributi di avviso, ad esempio il numero di endpoint coinvolti, gli utenti coinvolti, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="c4d96-116">For additional visibility at-a-glance, automatic incident naming, currently in public preview, generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="c4d96-117">In questo modo è possibile comprendere rapidamente l'ambito dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="c4d96-117">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="c4d96-118">Ad esempio: *eventi a più fasi su più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="c4d96-118">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="c4d96-119">Gli incidenti che sono stati precedenti all'implementazione della denominazione degli incidenti automatici non avranno il nome modificato.</span><span class="sxs-lookup"><span data-stu-id="c4d96-119">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>
>
> <span data-ttu-id="c4d96-120">Ulteriori informazioni su come [attivare le funzionalità di anteprima](preview.md#turn-on-preview-features).</span><span class="sxs-lookup"><span data-stu-id="c4d96-120">Learn more about [turning on preview features](preview.md#turn-on-preview-features).</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="c4d96-121">Assegnare gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="c4d96-121">Assign incidents</span></span>
<span data-ttu-id="c4d96-122">Se un evento non è stato ancora assegnato, è possibile selezionare **Assegna a me** per assegnare l'evento a se stessi.</span><span class="sxs-lookup"><span data-stu-id="c4d96-122">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="c4d96-123">In questo modo si assume la proprietà non solo dell'evento, ma anche di tutti gli avvisi associati.</span><span class="sxs-lookup"><span data-stu-id="c4d96-123">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="c4d96-124">Impostare lo stato e la classificazione</span><span class="sxs-lookup"><span data-stu-id="c4d96-124">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="c4d96-125">Stato di un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="c4d96-125">Incident status</span></span>
<span data-ttu-id="c4d96-126">È possibile categorizzare gli eventi imprevisti, ad esempio **Attivo** oppure **Risolto**, modificando lo stato durante il corso dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="c4d96-126">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="c4d96-127">Questo consente di organizzare e gestire il modo in cui il team può rispondere agli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="c4d96-127">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="c4d96-128">Ad esempio, l'analista SOC può esaminare gli eventi **Attivi** e urgenti del giorno e decidere di assegnarli a se stesso per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="c4d96-128">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="c4d96-129">In alternativa, può impostare l'evento come **Risolto** se l'evento è stato corretto.</span><span class="sxs-lookup"><span data-stu-id="c4d96-129">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="c4d96-130">La risoluzione di un evento imprevisto chiude automaticamente tutti gli avvisi ancora aperti che fanno parte dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c4d96-130">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="c4d96-131">Classificazione e determinazione</span><span class="sxs-lookup"><span data-stu-id="c4d96-131">Classification and determination</span></span>
<span data-ttu-id="c4d96-132">È possibile scegliere di non impostare una classificazione oppure decidere di specificare se un evento è vero o falso.</span><span class="sxs-lookup"><span data-stu-id="c4d96-132">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="c4d96-133">Così facendo, il team può visualizzare i criteri e imparare a usarli.</span><span class="sxs-lookup"><span data-stu-id="c4d96-133">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="c4d96-134">Aggiungere commenti</span><span class="sxs-lookup"><span data-stu-id="c4d96-134">Add comments</span></span>
<span data-ttu-id="c4d96-135">È possibile aggiungere commenti e visualizzare gli eventi cronologici relativi a un imprevisto per visualizzare le precedenti modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="c4d96-135">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="c4d96-136">Ogni volta che viene apportata una modifica o aggiunto un commento a un avviso, l'evento viene registrato nella sezione Commenti e cronologia.</span><span class="sxs-lookup"><span data-stu-id="c4d96-136">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="c4d96-137">I commenti aggiunti vengono visualizzati istantaneamente nel pannello.</span><span class="sxs-lookup"><span data-stu-id="c4d96-137">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="c4d96-138">Aggiungere tag agli eventi</span><span class="sxs-lookup"><span data-stu-id="c4d96-138">Add incident tags</span></span>
<span data-ttu-id="c4d96-139">È possibile aggiungere tag personalizzati a un evento, ad esempio per contrassegnare un insieme di eventi imprevisti con caratteristiche comuni.</span><span class="sxs-lookup"><span data-stu-id="c4d96-139">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="c4d96-140">In seguito è possibile filtrare la coda di tutti gli eventi imprevisti che contengono un tag specifico.</span><span class="sxs-lookup"><span data-stu-id="c4d96-140">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>