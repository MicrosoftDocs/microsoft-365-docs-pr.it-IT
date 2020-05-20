---
title: Chiudere o eliminare un caso
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su cosa accade quando un'indagine o un caso legale supportato da un caso avanzato di eDiscovery è chiuso o eliminato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292412"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="a1188-103">Chiudere o eliminare un caso avanzato di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a1188-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="a1188-104">Quando la causa legale o l'indagine supportata da un caso avanzato di eDiscovery è stata completata, è possibile chiudere o eliminare un caso.</span><span class="sxs-lookup"><span data-stu-id="a1188-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="a1188-105">È inoltre possibile riaprire un caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="a1188-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="a1188-106">Chiudere un caso</span><span class="sxs-lookup"><span data-stu-id="a1188-106">Close a case</span></span>

<span data-ttu-id="a1188-107">Ecco cosa succede quando si chiude un caso avanzato di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="a1188-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="a1188-108">Se il caso contiene eventuali posizioni di contenuto in attesa, tali esenzioni saranno disattivate.</span><span class="sxs-lookup"><span data-stu-id="a1188-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="a1188-109">Potrebbe risultare che il contenuto venga eliminato o rimosso definitivamente, dall'utente o da un processo automatizzato, ad esempio un criterio di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="a1188-109">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="a1188-110">La chiusura di un caso disattiva solo le esenzioni associate a quel caso.</span><span class="sxs-lookup"><span data-stu-id="a1188-110">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="a1188-111">Se altre esenzioni sono posizionate in una posizione di contenuto, ad esempio una conservazione per controversia legale, un blocco di eDiscovery di base o un'esenzione da un caso eDiscovery avanzato diverso, tali esenzioni verranno mantenute.</span><span class="sxs-lookup"><span data-stu-id="a1188-111">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="a1188-112">Il caso è ancora elencato nella pagina eDiscovery nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1188-112">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a1188-113">Vengono mantenuti i dettagli, le esenzioni, le ricerche e i membri di un caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="a1188-113">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="a1188-114">È possibile modificare un caso dopo che è stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="a1188-114">You can edit a case after it's closed.</span></span> <span data-ttu-id="a1188-115">Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare i risultati della ricerca e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a1188-115">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="a1188-116">La differenza principale tra casi attivi e chiusi consiste nel fatto che le esenzioni sono disattivate quando un caso viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="a1188-116">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="a1188-117">Per chiudere un caso:</span><span class="sxs-lookup"><span data-stu-id="a1188-117">To close a case:</span></span>

1. <span data-ttu-id="a1188-118">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera chiudere.</span><span class="sxs-lookup"><span data-stu-id="a1188-118">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="a1188-119">Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="a1188-119">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="a1188-120">Fare clic su **Chiudi caso**.</span><span class="sxs-lookup"><span data-stu-id="a1188-120">Click **Close case**.</span></span>

   <span data-ttu-id="a1188-121">Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="a1188-121">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="a1188-122">Riaprire un caso chiuso</span><span class="sxs-lookup"><span data-stu-id="a1188-122">Reopen a closed case</span></span>

<span data-ttu-id="a1188-123">Quando si riapre un caso di eDiscovery avanzato, tutte le esenzioni sul posto quando il caso è stato chiuso non verranno ripristinate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a1188-123">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="a1188-124">Dopo la riapertura del caso, è necessario passare alla scheda **esenzioni** e abilitare le esenzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a1188-124">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="a1188-125">Per attivare un'esenzione, selezionarla per visualizzare la pagina del riquadro a comparsa e quindi impostare l'interruttore di **stato** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="a1188-125">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="a1188-126">Per riaprire un caso chiuso:</span><span class="sxs-lookup"><span data-stu-id="a1188-126">To reopen a closed case:</span></span>

1. <span data-ttu-id="a1188-127">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="a1188-127">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="a1188-128">Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="a1188-128">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="a1188-129">Fare clic su **riapri caso**.</span><span class="sxs-lookup"><span data-stu-id="a1188-129">Click **Reopen case**.</span></span>

   <span data-ttu-id="a1188-130">Per il completamento del processo di riapertura, potrebbero essere necessari fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="a1188-130">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="a1188-131">Eliminazione di un caso</span><span class="sxs-lookup"><span data-stu-id="a1188-131">Delete a case</span></span>

<span data-ttu-id="a1188-132">È possibile eliminare i casi di eDiscovery avanzati sia attivi che chiusi.</span><span class="sxs-lookup"><span data-stu-id="a1188-132">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="a1188-133">Quando si elimina un caso, vengono eliminati tutti i componenti associati al caso, ad esempio l'elenco dei depositari, le comunicazioni, le ricerche, i set di revisione e il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="a1188-133">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="a1188-134">La distinzione tra maiuscole e minuscole viene rimossa dall'elenco dei casi della pagina **Advanced eDiscovery** nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1188-134">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a1188-135">Non è possibile ripristinare o riaprire un caso eliminato.</span><span class="sxs-lookup"><span data-stu-id="a1188-135">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="a1188-136">Negli scenari di perdita dei dati, l'unico modo per rimuovere gli elementi in un set di revisione consiste nell'eliminare il caso Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a1188-136">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="a1188-137">Gli altri metodi "Search and Purge" non rimuovono gli elementi da un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="a1188-137">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="a1188-138">Prima di poter eliminare un caso (che sia attivo o chiuso), è necessario prima eliminare *tutti* gli appigli associati al caso.</span><span class="sxs-lookup"><span data-stu-id="a1188-138">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="a1188-139">Che include l'eliminazione di esenzioni con stato **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="a1188-139">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="a1188-140">Per eliminare le esenzioni associate a un caso:</span><span class="sxs-lookup"><span data-stu-id="a1188-140">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="a1188-141">Passare alla scheda **esenzioni** nel caso Advanced eDiscovery che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="a1188-141">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="a1188-142">Fare clic sul blocco che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="a1188-142">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="a1188-143">Nella pagina a comparsa fare clic su **Elimina blocco**.</span><span class="sxs-lookup"><span data-stu-id="a1188-143">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="a1188-144">Per eliminare un caso:</span><span class="sxs-lookup"><span data-stu-id="a1188-144">To delete a case:</span></span>

1. <span data-ttu-id="a1188-145">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="a1188-145">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="a1188-146">Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="a1188-146">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="a1188-147">Fare clic su **Delete case**.</span><span class="sxs-lookup"><span data-stu-id="a1188-147">Click **Delete case**.</span></span>
