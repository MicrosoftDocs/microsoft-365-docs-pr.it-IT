---
title: Chiudere, riaprire ed eliminare i casi di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come gestire i casi di eDiscovery di base. Ciò include la chiusura di un caso, la riapertura di un caso chiuso e l'eliminazione di un caso.
ms.openlocfilehash: d729c91d4e81ad12d0b4b16574aa4edad8e239a3
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684100"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="b0fff-104">Chiudere, riaprire ed eliminare un caso di Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b0fff-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="b0fff-105">In questo articolo viene descritto come chiudere, riaprire ed eliminare i casi di eDiscovery di base in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0fff-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="b0fff-106">Chiudere un caso</span><span class="sxs-lookup"><span data-stu-id="b0fff-106">Close a case</span></span>

<span data-ttu-id="b0fff-107">Una volta completata la causa legale o l'indagine supportata da un caso di Core eDiscovery, è possibile chiudere il caso.</span><span class="sxs-lookup"><span data-stu-id="b0fff-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="b0fff-108">Ecco cosa accade quando si chiude un caso:</span><span class="sxs-lookup"><span data-stu-id="b0fff-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="b0fff-109">Se il caso contiene blocchi di eDiscovery, verranno disattivati.</span><span class="sxs-lookup"><span data-stu-id="b0fff-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="b0fff-110">Dopo che il blocco è stato disattivato, un periodo di tolleranza di 30 giorni (denominato blocco di *ritardo)* viene applicato alle posizioni di contenuto che erano in attesa.</span><span class="sxs-lookup"><span data-stu-id="b0fff-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="b0fff-111">Ciò consente di evitare che il contenuto venga eliminato immediatamente e offre agli amministratori la possibilità di cercare e ripristinare il contenuto prima che venga eliminato definitivamente dopo la scadenza del periodo di attesa.</span><span class="sxs-lookup"><span data-stu-id="b0fff-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="b0fff-112">Per ulteriori informazioni, vedere [Rimozione di percorsi di contenuto da un blocco di eDiscovery.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)</span><span class="sxs-lookup"><span data-stu-id="b0fff-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="b0fff-113">Con la chiusura di un caso vengono disattivati solo i blocchi specifici associati.</span><span class="sxs-lookup"><span data-stu-id="b0fff-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="b0fff-114">Se altre esenzioni vengono collocate in un percorso di contenuto (ad esempio un blocco per controversia legale, un criterio di conservazione o un blocco di un altro caso di eDiscovery di base), tali blocchi verranno comunque mantenuti.</span><span class="sxs-lookup"><span data-stu-id="b0fff-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="b0fff-115">Il caso è ancora elencato nella pagina Core eDiscovery nel Centro Microsoft 365 conformità.</span><span class="sxs-lookup"><span data-stu-id="b0fff-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b0fff-116">I dettagli, i blocchi, le ricerche e i membri di un caso chiuso vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="b0fff-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="b0fff-117">È possibile modificare un caso dopo che è stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="b0fff-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="b0fff-118">Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche ed esportare risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b0fff-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="b0fff-119">La differenza principale tra i casi attivi e chiusi è che i blocchi di eDiscovery vengono disattivati quando un caso viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="b0fff-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="b0fff-120">Per chiudere un caso:</span><span class="sxs-lookup"><span data-stu-id="b0fff-120">To close a case:</span></span>
  
1. <span data-ttu-id="b0fff-121">Nel Centro Microsoft 365 conformità fare clic su **eDiscovery** Core per visualizzare l'elenco dei casi di eDiscovery di base  >   nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0fff-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="b0fff-122">Fare clic sul nome del caso che si desidera chiudere.</span><span class="sxs-lookup"><span data-stu-id="b0fff-122">Click the name of the case that you want to close.</span></span>

   ![Chiudere il caso nella home page del caso](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="b0fff-124">Nella home page, in **Stato,** fare clic **su Chiudi caso.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="b0fff-125">Viene visualizzato un avviso che indica che le esenzioni associate al caso verranno disattivate.</span><span class="sxs-lookup"><span data-stu-id="b0fff-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="b0fff-126">Fare **clic su Sì** per chiudere il caso.</span><span class="sxs-lookup"><span data-stu-id="b0fff-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="b0fff-127">Lo stato nella home page del caso viene modificato da **Attivo** a **Chiuso.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="b0fff-128">Nella pagina **Core eDiscovery** fare clic su **Aggiorna** per aggiornare lo stato del caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="b0fff-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="b0fff-129">Per il completamento del processo di chiusura possono essere necessari fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="b0fff-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="b0fff-130">Al termine del processo, lo stato del caso viene modificato in **Chiuso** nella **pagina Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="b0fff-131">Riaprire un caso chiuso</span><span class="sxs-lookup"><span data-stu-id="b0fff-131">Reopen a closed case</span></span>

<span data-ttu-id="b0fff-132">Quando si riapre un caso, le eventuali eDiscovery conservate al momento della chiusura del caso non verranno ripristinate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b0fff-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="b0fff-133">Dopo la riapertura del caso, è necessario passare alla pagina **Esenzioni** e attivare le esenzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="b0fff-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="b0fff-134">Per attivare un blocco, selezionarlo per visualizzare la pagina a comparsa, quindi impostare l'interruttore dello **Stato** su **On**.</span><span class="sxs-lookup"><span data-stu-id="b0fff-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="b0fff-135">Nel Centro Microsoft 365 conformità fare clic su **eDiscovery** Core per visualizzare l'elenco dei casi di eDiscovery di base  >   nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0fff-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="b0fff-136">Fare clic sul nome del caso che si desidera riaprire.</span><span class="sxs-lookup"><span data-stu-id="b0fff-136">Click the name of the case that you want to reopen.</span></span>

   ![Riaprire un caso chiuso](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="b0fff-138">Nella home page, in **Stato, fare** clic su **Riapri caso.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="b0fff-139">Viene visualizzato un avviso che indica che le esenzioni associate al caso al momento della chiusura non verranno attivate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b0fff-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="b0fff-140">Fare **clic su Sì** per riaprire il caso.</span><span class="sxs-lookup"><span data-stu-id="b0fff-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="b0fff-141">Lo stato nella pagina a comparsa della home page del caso viene modificato da **Chiuso** ad **Attivo.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="b0fff-142">Nella pagina **Core eDiscovery** fare clic su **Aggiorna** per aggiornare lo stato del caso riaperto.</span><span class="sxs-lookup"><span data-stu-id="b0fff-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="b0fff-143">Il completamento del processo di riapertura potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="b0fff-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="b0fff-144">Al termine del processo, lo stato del caso viene modificato in **Attivo** nella **pagina Core eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="b0fff-145">(Facoltativo) Per attivare eventuali esenzioni associate al  caso riaperto, passare alla scheda Esenzioni, selezionare un'esenzione e quindi selezionare la casella di controllo in **Stato** nella pagina del riquadro a comparsa di blocco.</span><span class="sxs-lookup"><span data-stu-id="b0fff-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="b0fff-146">Eliminare un caso</span><span class="sxs-lookup"><span data-stu-id="b0fff-146">Delete a case</span></span>

<span data-ttu-id="b0fff-147">È inoltre possibile eliminare i casi di eDiscovery core attivi e chiusi.</span><span class="sxs-lookup"><span data-stu-id="b0fff-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="b0fff-148">Quando si elimina un caso, tutte le ricerche e le esportazioni nel caso vengono eliminate e il caso viene rimosso dall'elenco dei casi nella pagina **eDiscovery** di base nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0fff-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b0fff-149">Non è possibile riaprire un caso eliminato.</span><span class="sxs-lookup"><span data-stu-id="b0fff-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="b0fff-150">Prima di poter eliminare un caso ,sia esso attivo  o chiuso, è necessario eliminare tutte le eDiscovery associate al caso.</span><span class="sxs-lookup"><span data-stu-id="b0fff-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="b0fff-151">Ciò include l'eliminazione delle esenzioni con stato **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="b0fff-152">Per eliminare un blocco di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="b0fff-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="b0fff-153">Passare alla **scheda Esenzioni** nel caso in cui si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="b0fff-153">Go to the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="b0fff-154">Selezionare l'esenzione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="b0fff-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="b0fff-155">Nella pagina a comparsa fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-155">On the flyout page, click **Delete**.</span></span>

      ![Eliminare un blocco di eDiscovery](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="b0fff-157">Per eliminare un caso:</span><span class="sxs-lookup"><span data-stu-id="b0fff-157">To delete a case:</span></span>

1. <span data-ttu-id="b0fff-158">Nel Centro Microsoft 365 conformità fare clic su **eDiscovery** Core per visualizzare l'elenco dei casi di eDiscovery di base  >   nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0fff-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="b0fff-159">Fare clic sul nome del caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="b0fff-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="b0fff-160">Nella home page del caso, in **Stato,** fare clic **su Elimina caso.**</span><span class="sxs-lookup"><span data-stu-id="b0fff-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![Eliminare un caso](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="b0fff-162">Se il caso che si sta tentando di eliminare contiene ancora blocchi di eDiscovery, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="b0fff-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="b0fff-163">Sarà necessario eliminare tutte le esenzioni associate al caso e quindi riprovare a eliminare il caso.</span><span class="sxs-lookup"><span data-stu-id="b0fff-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
