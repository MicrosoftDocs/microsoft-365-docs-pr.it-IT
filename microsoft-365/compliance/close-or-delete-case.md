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
ms.openlocfilehash: be8d133a8215fc40c6d33025f9f4d1dee0f3b609
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412785"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="faf83-103">Chiudere o eliminare un caso avanzato di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="faf83-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="faf83-104">Quando la causa legale o l'indagine supportata da un caso avanzato di eDiscovery è stata completata, è possibile chiudere o eliminare un caso.</span><span class="sxs-lookup"><span data-stu-id="faf83-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="faf83-105">È inoltre possibile riaprire un caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="faf83-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="faf83-106">Chiudere un caso</span><span class="sxs-lookup"><span data-stu-id="faf83-106">Close a case</span></span>

<span data-ttu-id="faf83-107">Ecco cosa succede quando si chiude un caso avanzato di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="faf83-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="faf83-108">Se il caso contiene eventuali posizioni di contenuto in attesa, tali esenzioni saranno disattivate.</span><span class="sxs-lookup"><span data-stu-id="faf83-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="faf83-109">Dopo che l'esenzione è stata disattivata, viene applicato un periodo di tolleranza di 30 giorni (denominato *blocco di ritardo*) ai percorsi di contenuto in attesa.</span><span class="sxs-lookup"><span data-stu-id="faf83-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="faf83-110">Ciò consente di evitare che il contenuto venga eliminato immediatamente e fornisce agli amministratori la possibilità di cercare o recuperare il contenuto che verrà eliminato definitivamente dopo la scadenza del periodo di attesa.</span><span class="sxs-lookup"><span data-stu-id="faf83-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="faf83-111">Per ulteriori informazioni, vedere [rimozione di percorsi di contenuto da un'esenzione di eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="faf83-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="faf83-112">La chiusura di un caso disattiva solo le esenzioni associate a quel caso.</span><span class="sxs-lookup"><span data-stu-id="faf83-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="faf83-113">Se altre esenzioni sono posizionate in una posizione di contenuto, ad esempio una conservazione per controversia legale, un blocco di eDiscovery di base o un'esenzione da un caso eDiscovery avanzato diverso, tali esenzioni verranno mantenute.</span><span class="sxs-lookup"><span data-stu-id="faf83-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="faf83-114">Il caso è ancora elencato nella pagina eDiscovery nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="faf83-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="faf83-115">Vengono mantenuti i dettagli, le esenzioni, le ricerche e i membri di un caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="faf83-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="faf83-116">È possibile modificare un caso dopo che è stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="faf83-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="faf83-117">Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare i risultati della ricerca e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="faf83-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="faf83-118">La differenza principale tra casi attivi e chiusi consiste nel fatto che le esenzioni sono disattivate quando un caso viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="faf83-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="faf83-119">Per chiudere un caso:</span><span class="sxs-lookup"><span data-stu-id="faf83-119">To close a case:</span></span>

1. <span data-ttu-id="faf83-120">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera chiudere.</span><span class="sxs-lookup"><span data-stu-id="faf83-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="faf83-121">Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="faf83-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="faf83-122">Fare clic su **Chiudi caso**.</span><span class="sxs-lookup"><span data-stu-id="faf83-122">Click **Close case**.</span></span>

   <span data-ttu-id="faf83-123">Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="faf83-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="faf83-124">Riaprire un caso chiuso</span><span class="sxs-lookup"><span data-stu-id="faf83-124">Reopen a closed case</span></span>

<span data-ttu-id="faf83-125">Quando si riapre un caso di eDiscovery avanzato, tutte le esenzioni sul posto quando il caso è stato chiuso non verranno ripristinate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="faf83-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="faf83-126">Dopo la riapertura del caso, è necessario passare alla scheda **esenzioni** e abilitare le esenzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="faf83-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="faf83-127">Per attivare un'esenzione, selezionarla per visualizzare la pagina del riquadro a comparsa e quindi impostare l'interruttore di **stato** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="faf83-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="faf83-128">Per riaprire un caso chiuso:</span><span class="sxs-lookup"><span data-stu-id="faf83-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="faf83-129">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="faf83-129">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="faf83-130">Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="faf83-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="faf83-131">Fare clic su **riapri caso**.</span><span class="sxs-lookup"><span data-stu-id="faf83-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="faf83-132">Per il completamento del processo di riapertura, potrebbero essere necessari fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="faf83-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="faf83-133">Eliminazione di un caso</span><span class="sxs-lookup"><span data-stu-id="faf83-133">Delete a case</span></span>

<span data-ttu-id="faf83-134">È possibile eliminare i casi di eDiscovery avanzati sia attivi che chiusi.</span><span class="sxs-lookup"><span data-stu-id="faf83-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="faf83-135">Quando si elimina un caso, vengono eliminati tutti i componenti associati al caso, ad esempio l'elenco dei depositari, le comunicazioni, le ricerche, i set di revisione e il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="faf83-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="faf83-136">La distinzione tra maiuscole e minuscole viene rimossa dall'elenco dei casi della pagina **Advanced eDiscovery** nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="faf83-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="faf83-137">Non è possibile ripristinare o riaprire un caso eliminato.</span><span class="sxs-lookup"><span data-stu-id="faf83-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="faf83-138">Negli scenari di perdita dei dati, l'unico modo per rimuovere gli elementi in un set di revisione consiste nell'eliminare il caso Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="faf83-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="faf83-139">Gli altri metodi "Search and Purge" non rimuovono gli elementi da un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="faf83-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="faf83-140">Prima di poter eliminare un caso (che sia attivo o chiuso), è necessario prima eliminare *tutti* gli appigli associati al caso.</span><span class="sxs-lookup"><span data-stu-id="faf83-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="faf83-141">Che include l'eliminazione di esenzioni con stato **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="faf83-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="faf83-142">Per eliminare le esenzioni associate a un caso:</span><span class="sxs-lookup"><span data-stu-id="faf83-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="faf83-143">Passare alla scheda **esenzioni** nel caso Advanced eDiscovery che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="faf83-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="faf83-144">Fare clic sul blocco che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="faf83-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="faf83-145">Nella pagina a comparsa fare clic su **Elimina blocco**.</span><span class="sxs-lookup"><span data-stu-id="faf83-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="faf83-146">Per eliminare un caso:</span><span class="sxs-lookup"><span data-stu-id="faf83-146">To delete a case:</span></span>

1. <span data-ttu-id="faf83-147">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="faf83-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="faf83-148">Nella scheda **Impostazioni** , in **informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="faf83-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="faf83-149">Fare clic su **Delete case**.</span><span class="sxs-lookup"><span data-stu-id="faf83-149">Click **Delete case**.</span></span>
