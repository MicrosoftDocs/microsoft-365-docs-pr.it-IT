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
description: Informazioni su cosa accade quando un'indagine o un caso legale supportato da un Advanced eDiscovery caso viene chiuso o eliminato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657652"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="91718-103">Chiudere o eliminare un Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="91718-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="91718-104">Una volta completata la causa legale o l'indagine supportata da un Advanced eDiscovery, è possibile chiudere o eliminare un caso.</span><span class="sxs-lookup"><span data-stu-id="91718-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="91718-105">È anche possibile riaprire un caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="91718-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="91718-106">Chiudere un caso</span><span class="sxs-lookup"><span data-stu-id="91718-106">Close a case</span></span>

<span data-ttu-id="91718-107">Ecco cosa accade quando si chiude un Advanced eDiscovery caso:</span><span class="sxs-lookup"><span data-stu-id="91718-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="91718-108">Se il caso contiene posizioni di contenuti bloccate, i blocchi vengono disattivati.</span><span class="sxs-lookup"><span data-stu-id="91718-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="91718-109">Dopo che il blocco è stato disattivato, un periodo di tolleranza di 30 giorni (denominato blocco di *ritardo)* viene applicato alle posizioni di contenuto che erano in attesa.</span><span class="sxs-lookup"><span data-stu-id="91718-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="91718-110">Ciò consente di impedire l'eliminazione immediata del contenuto e offre agli amministratori la possibilità di cercare o ripristinare il contenuto che verrà eliminato definitivamente dopo la scadenza del periodo di attesa di ritardo.</span><span class="sxs-lookup"><span data-stu-id="91718-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="91718-111">Per ulteriori informazioni, vedere [Rimozione di percorsi di contenuto da un blocco di eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="91718-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="91718-112">Con la chiusura di un caso vengono disattivati solo i blocchi specifici associati.</span><span class="sxs-lookup"><span data-stu-id="91718-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="91718-113">Se altre esenzioni vengono posizionate in un percorso di contenuto (ad esempio un blocco per controversia legale, un blocco eDiscovery di base o un blocco di un caso Advanced eDiscovery diverso), tali blocchi verranno comunque mantenuti.</span><span class="sxs-lookup"><span data-stu-id="91718-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="91718-114">Il caso è ancora elencato nella pagina eDiscovery nel Centro Microsoft 365 conformità.</span><span class="sxs-lookup"><span data-stu-id="91718-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="91718-115">I dettagli, i blocchi, le ricerche e i membri di un caso chiuso vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="91718-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="91718-116">È possibile modificare un caso dopo che è stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="91718-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="91718-117">Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche, esportare risultati di ricerca e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="91718-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="91718-118">La differenza principale tra casi attivi e chiusi è che con la chiusura di un caso vengono disattivati i blocchi.</span><span class="sxs-lookup"><span data-stu-id="91718-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="91718-119">Per chiudere un caso:</span><span class="sxs-lookup"><span data-stu-id="91718-119">To close a case:</span></span>

1. <span data-ttu-id="91718-120">Nella pagina **Advanced eDiscovery**, selezionare il caso che si desidera chiudere.</span><span class="sxs-lookup"><span data-stu-id="91718-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="91718-121">Nella scheda **Impostazioni** in **Informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="91718-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="91718-122">Nella parte inferiore della **pagina del** riquadro a comparsa Informazioni caso fare clic su (**...**) **Altre opzioni** e quindi fare clic su **Chiudi caso.**</span><span class="sxs-lookup"><span data-stu-id="91718-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![Opzione nel menu Altre opzioni per chiudere un'Advanced eDiscovery caso](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="91718-124">Per il completamento del processo di chiusura possono essere necessari fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="91718-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="91718-125">Riaprire un caso chiuso</span><span class="sxs-lookup"><span data-stu-id="91718-125">Reopen a closed case</span></span>

<span data-ttu-id="91718-126">Quando si riapre un Advanced eDiscovery caso, le eventuali esenzioni in essere al momento della chiusura del caso non verranno ripristinate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="91718-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="91718-127">Dopo la riapertura del caso, è  necessario passare alla scheda Esenzioni e attivare le esenzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="91718-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="91718-128">Per attivare un blocco, selezionarlo per visualizzare la pagina a comparsa, quindi impostare l'interruttore dello **Stato** su **On**.</span><span class="sxs-lookup"><span data-stu-id="91718-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="91718-129">Per riaprire un caso chiuso:</span><span class="sxs-lookup"><span data-stu-id="91718-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="91718-130">Nella pagina **Advanced eDiscovery**, selezionare il caso che si desidera riaprire.</span><span class="sxs-lookup"><span data-stu-id="91718-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="91718-131">Nella scheda **Impostazioni** in **Informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="91718-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="91718-132">Nella parte inferiore della **pagina del** riquadro a comparsa Informazioni caso fare clic su (**...**) **Altre opzioni** e quindi fare clic su **Riapri caso.**</span><span class="sxs-lookup"><span data-stu-id="91718-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![Opzione nel menu Altre opzioni per riaprire un Advanced eDiscovery caso](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="91718-134">Il completamento del processo di riapertura potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="91718-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="91718-135">Eliminare un caso</span><span class="sxs-lookup"><span data-stu-id="91718-135">Delete a case</span></span>

<span data-ttu-id="91718-136">È possibile eliminare sia i casi attivi che Advanced eDiscovery chiusi.</span><span class="sxs-lookup"><span data-stu-id="91718-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="91718-137">Quando si elimina un caso, tutti i componenti associati al caso, come l'elenco di responsabili, comunicazioni, ricerche, insiemi da rivedere e processi esportati vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="91718-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="91718-138">Il caso viene rimosso dall'elenco dei casi nella pagina **Advanced eDiscovery** nel Centro Microsoft 365 conformità.</span><span class="sxs-lookup"><span data-stu-id="91718-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="91718-139">Non è possibile ripristinare o riaprire un caso eliminato.</span><span class="sxs-lookup"><span data-stu-id="91718-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="91718-140">Negli scenari di fuoriuscita di dati, l'unico modo per rimuovere gli elementi in un set di revisione è eliminare il Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="91718-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="91718-141">Altri metodi di "ricerca ed eliminazione" non rimuovono elementi da un set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="91718-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="91718-142">Prima di poter eliminare un caso( attivo o chiuso),  è necessario eliminare tutte le esenzioni associate al caso.</span><span class="sxs-lookup"><span data-stu-id="91718-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="91718-143">Ciò include l'eliminazione delle esenzioni con stato **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="91718-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="91718-144">Per eliminare i blocchi associati a un caso:</span><span class="sxs-lookup"><span data-stu-id="91718-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="91718-145">Passare alla **scheda** Esenzioni Advanced eDiscovery caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="91718-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="91718-146">Fare clic sull'esenzione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="91718-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="91718-147">Nella pagina a comparsa fare clic su **Elimina blocco.**</span><span class="sxs-lookup"><span data-stu-id="91718-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="91718-148">Per eliminare un caso:</span><span class="sxs-lookup"><span data-stu-id="91718-148">To delete a case:</span></span>

1. <span data-ttu-id="91718-149">Nella pagina **Advanced eDiscovery**, selezionare il caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="91718-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="91718-150">Nella scheda **Impostazioni** in **Informazioni sul caso**, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="91718-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="91718-151">Nella parte inferiore della **pagina del** riquadro a comparsa Informazioni caso fare clic su (**...**) **Altre opzioni** e quindi fare clic **su Elimina caso.**</span><span class="sxs-lookup"><span data-stu-id="91718-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![Opzione nel menu Altre opzioni per eliminare una Advanced eDiscovery caso](..\Media\DeleteAdvancedeDiscoveryCase.png)
