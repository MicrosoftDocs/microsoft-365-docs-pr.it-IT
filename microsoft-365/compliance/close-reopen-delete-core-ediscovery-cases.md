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
description: In questo articolo viene descritto come gestire i casi di eDiscovery di base. Questo include la chiusura di un caso, la riapertura di un caso chiuso e l'eliminazione di un caso.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412795"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="ac110-104">Chiudere, riaprire ed eliminare un caso di eDiscovery di base</span><span class="sxs-lookup"><span data-stu-id="ac110-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="ac110-105">In questo articolo viene descritto come chiudere, riaprire ed eliminare i casi di eDiscovery di base in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac110-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="ac110-106">Chiudere un caso</span><span class="sxs-lookup"><span data-stu-id="ac110-106">Close a case</span></span>

<span data-ttu-id="ac110-107">Quando la causa legale o l'indagine supportata da un caso di eDiscovery di base è stata completata, è possibile chiudere il caso.</span><span class="sxs-lookup"><span data-stu-id="ac110-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="ac110-108">Ecco cosa succede quando si chiude un caso:</span><span class="sxs-lookup"><span data-stu-id="ac110-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="ac110-109">Se il caso contiene posizioni di contenuto in eDiscovery Hold, tali esenzioni verranno disattivate.</span><span class="sxs-lookup"><span data-stu-id="ac110-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="ac110-110">Dopo che l'esenzione è stata disattivata, viene applicato un periodo di tolleranza di 30 giorni (denominato *blocco di ritardo*) ai percorsi di contenuto in attesa.</span><span class="sxs-lookup"><span data-stu-id="ac110-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="ac110-111">Ciò consente di evitare che il contenuto venga eliminato immediatamente e fornisce agli amministratori la possibilità di cercare e ripristinare il contenuto prima che venga eliminato definitivamente dopo la scadenza del periodo di attesa.</span><span class="sxs-lookup"><span data-stu-id="ac110-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="ac110-112">Per ulteriori informazioni, vedere [rimozione di percorsi di contenuto da un'esenzione di eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="ac110-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="ac110-113">La chiusura di un caso disattiva solo le esenzioni associate a quel caso.</span><span class="sxs-lookup"><span data-stu-id="ac110-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="ac110-114">Se altre esenzioni vengono inserite in una posizione di contenuto, ad esempio un blocco per controversia legale, un criterio di conservazione o un'esenzione da un caso di eDiscovery di base diverso, tali esenzioni verranno comunque mantenute.</span><span class="sxs-lookup"><span data-stu-id="ac110-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="ac110-115">Il caso è ancora elencato nella pagina principale di eDiscovery nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac110-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ac110-116">Vengono mantenuti i dettagli, le esenzioni, le ricerche e i membri di un caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="ac110-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="ac110-117">È possibile modificare un caso dopo che è stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="ac110-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="ac110-118">Ad esempio, è possibile aggiungere o rimuovere membri, creare ricerche ed esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac110-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="ac110-119">La differenza principale tra casi attivi e chiusi è che le esenzioni di eDiscovery sono disattivate quando un caso è chiuso.</span><span class="sxs-lookup"><span data-stu-id="ac110-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="ac110-120">Per chiudere un caso:</span><span class="sxs-lookup"><span data-stu-id="ac110-120">To close a case:</span></span>
  
1. <span data-ttu-id="ac110-121">Nel centro conformità di Microsoft 365, fare clic su **eDiscovery**  >  **Core** per visualizzare l'elenco dei casi di eDiscovery di base nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac110-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="ac110-122">Fare clic sul nome del caso che si desidera chiudere.</span><span class="sxs-lookup"><span data-stu-id="ac110-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="ac110-123">Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** .</span><span class="sxs-lookup"><span data-stu-id="ac110-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="ac110-124">In **Manage case status**fare clic su **Chiudi caso**.</span><span class="sxs-lookup"><span data-stu-id="ac110-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="ac110-125">Viene visualizzato un messaggio di avviso in cui viene indicato che le esenzioni associate al caso saranno disattivate.</span><span class="sxs-lookup"><span data-stu-id="ac110-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="ac110-126">Fare clic su **Sì** per chiudere il caso.</span><span class="sxs-lookup"><span data-stu-id="ac110-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="ac110-127">Lo stato della pagina **Gestisci** il riquadro a comparsa di questo caso è stato modificato da **attivo** a **chiusura**.</span><span class="sxs-lookup"><span data-stu-id="ac110-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="ac110-128">Chiudere la pagina **Gestisci questo caso** .</span><span class="sxs-lookup"><span data-stu-id="ac110-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="ac110-129">Nella pagina **Core eDiscovery** , fare clic su **Aggiorna** per aggiornare lo stato del caso chiuso.</span><span class="sxs-lookup"><span data-stu-id="ac110-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="ac110-130">Il completamento del processo di chiusura potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="ac110-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="ac110-131">Al termine del processo, lo stato della distinzione tra maiuscole e minuscole viene cambiato in **Closed** nella pagina di **eDiscovery di base** .</span><span class="sxs-lookup"><span data-stu-id="ac110-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="ac110-132">Fare di nuovo clic sul nome del caso per visualizzare la pagina Gestisci il riquadro a comparsa di **questo caso** , che contiene informazioni su quando il caso è stato chiuso e chi l'ha chiusa.</span><span class="sxs-lookup"><span data-stu-id="ac110-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="ac110-133">Riaprire un caso chiuso</span><span class="sxs-lookup"><span data-stu-id="ac110-133">Reopen a closed case</span></span>

<span data-ttu-id="ac110-134">Quando si riapre un caso, tutte le esenzioni di eDiscovery che erano sul posto quando il caso è stato chiuso non verranno ripristinate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ac110-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="ac110-135">Dopo la riapertura del caso, è necessario andare alla pagina **esenzioni** e abilitare le esenzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="ac110-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="ac110-136">Per attivare un'esenzione, selezionarla per visualizzare la pagina del riquadro a comparsa e quindi impostare l'interruttore di **stato** **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="ac110-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="ac110-137">Nel centro conformità di Microsoft 365, fare clic su **eDiscovery**  >  **Core** per visualizzare l'elenco dei casi di eDiscovery di base nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac110-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="ac110-138">Fare clic sul nome del caso che si desidera riaprire.</span><span class="sxs-lookup"><span data-stu-id="ac110-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="ac110-139">Viene visualizzata la pagina Gestisci il riquadro a comparsa di **questo caso** .</span><span class="sxs-lookup"><span data-stu-id="ac110-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="ac110-140">In **Manage case status**fare clic su **riapri caso**.</span><span class="sxs-lookup"><span data-stu-id="ac110-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="ac110-141">Viene visualizzato un messaggio di avviso in cui viene indicato che le esenzioni associate al caso in cui è stata chiusa non verranno attivate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ac110-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="ac110-142">Fare clic su **Sì** per riaprire il caso.</span><span class="sxs-lookup"><span data-stu-id="ac110-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="ac110-143">Lo stato della pagina **Gestisci** il riquadro a comparsa di questo caso è stato modificato da **chiuso** a **attivo**.</span><span class="sxs-lookup"><span data-stu-id="ac110-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="ac110-144">Chiudere la pagina **Gestisci questo caso** .</span><span class="sxs-lookup"><span data-stu-id="ac110-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="ac110-145">Nella pagina **eDiscovery di base** fare clic su **Aggiorna** per aggiornare lo stato del caso riaperto.</span><span class="sxs-lookup"><span data-stu-id="ac110-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="ac110-146">Per il completamento del processo di riapertura, potrebbero essere necessari fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="ac110-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="ac110-147">Al termine del processo, lo stato del caso viene modificato in **attivo** nella pagina di **eDiscovery di base** .</span><span class="sxs-lookup"><span data-stu-id="ac110-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="ac110-148">Eliminazione di un caso</span><span class="sxs-lookup"><span data-stu-id="ac110-148">Delete a case</span></span>

<span data-ttu-id="ac110-149">È inoltre possibile eliminare i casi di eDiscovery core attivi e chiusi.</span><span class="sxs-lookup"><span data-stu-id="ac110-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="ac110-150">Quando si elimina un caso, tutte le ricerche e le esportazioni nel caso vengono eliminate e il caso viene rimosso dall'elenco dei casi nella pagina di **eDiscovery di base** nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac110-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ac110-151">Non è possibile riaprire un caso eliminato.</span><span class="sxs-lookup"><span data-stu-id="ac110-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="ac110-152">Prima di eliminare un caso (che sia attivo o chiuso), è necessario innanzitutto eliminare *tutte le* esenzioni di eDiscovery associate al caso.</span><span class="sxs-lookup"><span data-stu-id="ac110-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="ac110-153">Che include l'eliminazione di esenzioni con stato **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="ac110-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="ac110-154">Per eliminare un blocco di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="ac110-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="ac110-155">Andare alla scheda **esenzioni** nel caso in cui si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="ac110-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="ac110-156">Fare clic sul blocco che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="ac110-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="ac110-157">Nella pagina a comparsa fare clic su **Elimina blocco**.</span><span class="sxs-lookup"><span data-stu-id="ac110-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="ac110-158">Per eliminare un caso:</span><span class="sxs-lookup"><span data-stu-id="ac110-158">To delete a case:</span></span>

1. <span data-ttu-id="ac110-159">Nel centro conformità di Microsoft 365, fare clic su **eDiscovery**  >  **Core** per visualizzare l'elenco dei casi di eDiscovery di base nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac110-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="ac110-160">Fare clic sul nome del caso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="ac110-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="ac110-161">In **Gestione stato caso** nella pagina riquadro a comparsa fare clic su **Elimina caso**.</span><span class="sxs-lookup"><span data-stu-id="ac110-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="ac110-162">Se il caso che si sta tentando di eliminare contiene ancora eDiscovery, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="ac110-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="ac110-163">Sarà necessario eliminare tutte le esenzioni associate al caso e quindi riprovare per eliminare il caso.</span><span class="sxs-lookup"><span data-stu-id="ac110-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
