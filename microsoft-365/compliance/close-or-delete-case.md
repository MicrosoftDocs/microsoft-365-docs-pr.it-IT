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
description: Informazioni su cosa accade quando un'indagine o un caso legale supportato da un caso di Advanced eDiscovery viene chiuso o eliminato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419062"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="51c45-103">Chiudere o eliminare un caso di Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="51c45-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="51c45-104">Una volta completata la causa legale o l'indagine supportata da un caso di Advanced eDiscovery, è possibile chiudere o eliminare un caso.</span><span class="sxs-lookup"><span data-stu-id="51c45-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="51c45-105">È inoltre possibile riaprire un caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="51c45-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="51c45-106">Chiudere un caso</span><span class="sxs-lookup"><span data-stu-id="51c45-106">Close a case</span></span>

<span data-ttu-id="51c45-107">Ecco cosa accade quando si chiude un caso di Advanced eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="51c45-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="51c45-108">Se il caso contiene percorsi di contenuto in attesa, tali esenzioni verranno disattivate.</span><span class="sxs-lookup"><span data-stu-id="51c45-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="51c45-109">Dopo che l'esenzione è stata disattivata, un periodo di tolleranza di 30 giorni (denominato blocco di *ritardo)* viene applicato ai percorsi di contenuto che erano in attesa.</span><span class="sxs-lookup"><span data-stu-id="51c45-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="51c45-110">Ciò consente di evitare che il contenuto venga eliminato immediatamente e offre agli amministratori l'opportunità di cercare o recuperare contenuti che verranno eliminati definitivamente dopo la scadenza del periodo di attesa.</span><span class="sxs-lookup"><span data-stu-id="51c45-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="51c45-111">Per ulteriori informazioni, vedere [Rimozione di percorsi di contenuto da un blocco di eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="51c45-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="51c45-112">La chiusura di un caso disattiva solo le esenzioni associate a tale caso.</span><span class="sxs-lookup"><span data-stu-id="51c45-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="51c45-113">Se in un percorso di contenuto sono presenti altri blocchi , ad esempio un blocco per controversia legale, un blocco di eDiscovery di base o un blocco di un altro caso di Advanced eDiscovery, tali blocchi verranno mantenuti.</span><span class="sxs-lookup"><span data-stu-id="51c45-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="51c45-114">Il caso è ancora elencato nella pagina eDiscovery nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51c45-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="51c45-115">I dettagli, le esenzioni, le ricerche e i membri di un caso chiuso vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="51c45-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="51c45-116">È possibile modificare un caso dopo che è stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="51c45-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="51c45-117">Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare i risultati della ricerca e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="51c45-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="51c45-118">La differenza principale tra casi attivi e chiusi consiste nel fatto che i blocchi vengono disattivati quando un caso viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="51c45-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="51c45-119">Per chiudere un caso:</span><span class="sxs-lookup"><span data-stu-id="51c45-119">To close a case:</span></span>

1. <span data-ttu-id="51c45-120">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera chiudere.</span><span class="sxs-lookup"><span data-stu-id="51c45-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="51c45-121">Nella scheda **Impostazioni,** in **Informazioni caso,** fare clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="51c45-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="51c45-122">Fare **clic su Chiudi caso.**</span><span class="sxs-lookup"><span data-stu-id="51c45-122">Click **Close case**.</span></span>

   <span data-ttu-id="51c45-123">Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="51c45-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="51c45-124">Riaprire un caso chiuso</span><span class="sxs-lookup"><span data-stu-id="51c45-124">Reopen a closed case</span></span>

<span data-ttu-id="51c45-125">Quando si riapre un caso di Advanced eDiscovery, tutti i blocchi che erano presenti al momento della chiusura del caso non verranno ripristinati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="51c45-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="51c45-126">Dopo la riapertura del caso, è  necessario passare alla scheda Esenzioni e attivare le esenzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="51c45-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="51c45-127">Per attivare un'esenzione, selezionarla per visualizzare la pagina a comparsa e quindi impostare l'interruttore **Stato** su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="51c45-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="51c45-128">Per riaprire un caso chiuso:</span><span class="sxs-lookup"><span data-stu-id="51c45-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="51c45-129">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera riaprire.</span><span class="sxs-lookup"><span data-stu-id="51c45-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="51c45-130">Nella scheda **Impostazioni,** in **Informazioni caso,** fare clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="51c45-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="51c45-131">Fare clic **su Riapri caso.**</span><span class="sxs-lookup"><span data-stu-id="51c45-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="51c45-132">Il completamento del processo di riapertura potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="51c45-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="51c45-133">Eliminare un caso</span><span class="sxs-lookup"><span data-stu-id="51c45-133">Delete a case</span></span>

<span data-ttu-id="51c45-134">È possibile eliminare sia i casi di Advanced eDiscovery attivi che chiusi.</span><span class="sxs-lookup"><span data-stu-id="51c45-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="51c45-135">Quando si elimina un caso, vengono eliminati tutti i componenti associati al caso, ad esempio l'elenco dei responsabile, le comunicazioni, le ricerche, i set di revisioni e il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="51c45-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="51c45-136">Il caso viene rimosso dall'elenco dei casi nella pagina **Advanced eDiscovery** nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51c45-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="51c45-137">Non è possibile recuperare o riaprire un caso eliminato.</span><span class="sxs-lookup"><span data-stu-id="51c45-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="51c45-138">Negli scenari di perdita di dati, l'unico modo per rimuovere gli elementi in un insieme da rivedere è eliminare il caso di Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="51c45-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="51c45-139">Altri metodi di "ricerca ed eliminazione" non rimuovono elementi da un insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="51c45-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="51c45-140">Prima di poter eliminare un caso (attivo o chiuso),  è necessario eliminare tutte le esenzioni associate al caso.</span><span class="sxs-lookup"><span data-stu-id="51c45-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="51c45-141">Ciò include l'eliminazione delle esenzioni con stato **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="51c45-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="51c45-142">Per eliminare i blocchi associati a un caso:</span><span class="sxs-lookup"><span data-stu-id="51c45-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="51c45-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span><span class="sxs-lookup"><span data-stu-id="51c45-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="51c45-144">Fare clic sull'esenzione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="51c45-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="51c45-145">Nella pagina a comparsa fare clic su **Elimina blocco.**</span><span class="sxs-lookup"><span data-stu-id="51c45-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="51c45-146">Per eliminare un caso:</span><span class="sxs-lookup"><span data-stu-id="51c45-146">To delete a case:</span></span>

1. <span data-ttu-id="51c45-147">Nella pagina **Advanced eDiscovery** selezionare il caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="51c45-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="51c45-148">Nella scheda **Impostazioni,** in **Informazioni caso,** fare clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="51c45-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="51c45-149">Fare clic **su Elimina caso.**</span><span class="sxs-lookup"><span data-stu-id="51c45-149">Click **Delete case**.</span></span>
