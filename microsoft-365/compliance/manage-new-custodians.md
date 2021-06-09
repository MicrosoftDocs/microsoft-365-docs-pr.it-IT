---
title: Gestire i custodi in un Advanced eDiscovery caso
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
description: Informazioni su come visualizzare i dettagli, modificare e modificare in blocco l'elenco dei Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739869"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="f5cbb-103">Gestire i custodi in un Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="f5cbb-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="f5cbb-104">La pagina Custodi della **scheda Origini** di un caso Advanced eDiscovery contiene un elenco di tutti i custodi che sono stati aggiunti al caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="f5cbb-105">Dopo aver aggiunto i custodi a un caso, i dettagli su ogni responsabile vengono raccolti automaticamente da Azure Active Directory e sono visualizzabili in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Gestire i custodi](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="f5cbb-107">Visualizzare i dettagli del responsabile</span><span class="sxs-lookup"><span data-stu-id="f5cbb-107">View custodian details</span></span>

<span data-ttu-id="f5cbb-108">Per visualizzare i dettagli su un responsabile, fare clic sul responsabile nell'elenco nella **scheda Custodi.** Viene visualizzata una pagina a comparsa contenente le informazioni seguenti sul responsabile:</span><span class="sxs-lookup"><span data-stu-id="f5cbb-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="f5cbb-109">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="f5cbb-109">Contact information</span></span>

  - <span data-ttu-id="f5cbb-110">**Nome visualizzato** - Nome visualizzato nella rubrica del responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="f5cbb-111">Questa è in genere la combinazione del nome, dell'iniziale e del cognome del responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="f5cbb-112">**Posta/SMTP** - Indirizzo SMTP primario per il responsabile, ad esempio, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="f5cbb-113">Viene inoltre elencato il nome dell'entità utente (UPN) del responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="f5cbb-114">**Title:** la posizione del responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="f5cbb-115">**Department** - Nome del reparto in cui lavora il responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="f5cbb-116">**Manager** : responsabile del responsabile del responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="f5cbb-117">Il manager designato riceverà tutte le comunicazioni di escalation per questo responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="f5cbb-118">Informazioni sulle posizioni</span><span class="sxs-lookup"><span data-stu-id="f5cbb-118">Location information</span></span>

  - <span data-ttu-id="f5cbb-119">**City** - Città in cui si trova il responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="f5cbb-120">**State** - Stato o provincia nell'indirizzo del responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="f5cbb-121">**Country/Region** - Paese/area geografica in cui si trova il responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="f5cbb-122">**Office** - Posizione dell'ufficio nel luogo di lavoro del responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="f5cbb-123">Informazioni sul caso</span><span class="sxs-lookup"><span data-stu-id="f5cbb-123">Case information</span></span>

  - <span data-ttu-id="f5cbb-124">**Stato blocco** - Indica se il responsabile è stato messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="f5cbb-125">**Stato comunicazione**: Indica se al responsabile della conservazione è stato emesso un avviso di blocco.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="f5cbb-126">Se al responsabile è stato emesso un avviso, il valore di questa proprietà è **Published.**</span><span class="sxs-lookup"><span data-stu-id="f5cbb-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="f5cbb-127">Se al responsabile non è stato emesso un avviso, lo stato è **Non pubblicato.**</span><span class="sxs-lookup"><span data-stu-id="f5cbb-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="f5cbb-128">**Status** : stato del responsabile del caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="f5cbb-129">Lo stato **Attivo** indica che il responsabile fa parte del caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="f5cbb-130">Se un responsabile viene rilasciato da un caso, lo stato viene modificato in **Rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="f5cbb-131">Origini dati e informazioni di indicizzazione</span><span class="sxs-lookup"><span data-stu-id="f5cbb-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="f5cbb-132">**Origini dati:** mostra il numero e il tipo di origini dati (cassette postali, siti e Teams) associate al responsabile del caso e che fanno parte del caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="f5cbb-133">**Ora aggiornamento indice** - Indica l'ora e la data dell'ultimo trigger del processo di indicizzazione avanzato.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="f5cbb-134">Questa proprietà indicherà anche quando è in corso il processo di indicizzazione avanzato.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="f5cbb-135">Modificare un responsabile</span><span class="sxs-lookup"><span data-stu-id="f5cbb-135">Edit a custodian</span></span>

<span data-ttu-id="f5cbb-136">Con l'avanzamento del caso, potresti scoprire che potrebbero essere presenti origini dati aggiuntive pertinenti a un responsabile specifico & caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="f5cbb-137">In altri scenari, è possibile rimuovere determinate origini dati che sono state esaminate e ritenute non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="f5cbb-138">Per aggiornare le origini dati associate a un responsabile:</span><span class="sxs-lookup"><span data-stu-id="f5cbb-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="f5cbb-139">Passare a **eDiscovery > Advanced eDiscovery** aprire il caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="f5cbb-140">Fare clic **sulla scheda** Origini.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="f5cbb-141">Nella pagina **Custodi** selezionare un responsabile nell'elenco e fare clic su **Modifica** nella pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Modifica origini dati](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="f5cbb-143">Fare **clic sulla scheda Scegli** origini dati per modificare le impostazioni per la cassetta postale Exchange e l'account OneDrive, fare clic su Scegli origini **dati.**</span><span class="sxs-lookup"><span data-stu-id="f5cbb-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="f5cbb-144">Fare clic **sulla scheda Seleziona** origini dati aggiuntive per aggiungere o rimuovere Teams, SharePoint o Exchange cassette postali associate al responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="f5cbb-145">Per ulteriori informazioni sulle origini dati associate a un responsabile, vedere [Add custodians to a case.](add-custodians-to-case.md)</span><span class="sxs-lookup"><span data-stu-id="f5cbb-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="f5cbb-146">Fare **clic su Inserisci blocchi di** custodia per abilitare o disabilitare il blocco per il responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="f5cbb-147">Re-index custodian data</span><span class="sxs-lookup"><span data-stu-id="f5cbb-147">Re-index custodian data</span></span>

<span data-ttu-id="f5cbb-148">Nella maggior parte dei flussi di lavoro di eDiscovery per indagini legali, viene ricercato un sottoinsieme dei dati di un responsabile dopo l'aggiunta del responsabile a una causa legale.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="f5cbb-149">A causa di file di dimensioni molto grandi o di possibili danneggiamenti dei dati, alcuni elementi nelle origini dati associate a un responsabile possono essere parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="f5cbb-150">Utilizzando la [funzionalità di indicizzazione](indexing-custodian-data.md) avanzata nell'Advanced eDiscovery, la maggior parte degli elementi parzialmente indicizzati può essere automaticamente corretti tramite la nuova indicizzazione di questi elementi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="f5cbb-151">Quando un responsabile viene aggiunto a un caso, i dati che si trovano nelle origini dati associate al responsabile vengono automaticamente indicizzati (tramite il processo di indicizzazione avanzato).</span><span class="sxs-lookup"><span data-stu-id="f5cbb-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="f5cbb-152">Ciò significa che puoi lasciare i dati sul posto invece di doverli scaricare e correggere e quindi cercarli offline.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="f5cbb-153">Tuttavia, durante il ciclo di vita di un caso legale, le nuove origini dati potrebbero essere associate a un responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="f5cbb-154">In questo caso, è possibile indicizzare nuovamente i dati del responsabile eseguendo di nuovo il processo di indicizzazione avanzato per correggere eventuali elementi parzialmente indicizzati e aggiornare l'indice per i dati del responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="f5cbb-155">Per attivare il processo di re-indicizzazione per risolvere gli elementi parzialmente indicizzati:</span><span class="sxs-lookup"><span data-stu-id="f5cbb-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="f5cbb-156">Passare a **eDiscovery > Advanced eDiscovery** aprire il caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="f5cbb-157">Fare clic **sulla scheda** Origini.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="f5cbb-158">Nella pagina **Custodi** selezionare un responsabile i cui dati devono essere reindicizzati.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="f5cbb-159">Nella pagina a comparsa fare clic su **Aggiorna indice.**</span><span class="sxs-lookup"><span data-stu-id="f5cbb-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="f5cbb-160">Viene visualizzata una finestra di dialogo che conferma la creazione del processo di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="f5cbb-161">La re-indicizzazione dei dati di custodia è un processo a esecuzione lunga. il processo corrispondente creato è denominato **Re-indexing custodian data**.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="f5cbb-162">È possibile tenere traccia dello stato nella **scheda Processi** o nella scheda **Custodi** monitorando lo stato nella **colonna Stato processo di** indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="f5cbb-163">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="f5cbb-163">For more information, see:</span></span>

- [<span data-ttu-id="f5cbb-164">Gestire gli errori di elaborazione</span><span class="sxs-lookup"><span data-stu-id="f5cbb-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="f5cbb-165">Gestire processi</span><span class="sxs-lookup"><span data-stu-id="f5cbb-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="f5cbb-166">Rilasciare un responsabile da un caso</span><span class="sxs-lookup"><span data-stu-id="f5cbb-166">Release a custodian from a case</span></span>

<span data-ttu-id="f5cbb-167">Un depositario viene rilasciato in situazioni in cui un caso è chiuso, il depositario non è più obbligato a conservare il contenuto per un caso o quando il depositario è ritenuto non più rilevante per il caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="f5cbb-168">Se rilasci un responsabile dopo la pubblicazione di un avviso di blocco, al responsabile verrà inviata una notifica di rilascio.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="f5cbb-169">Inoltre, vengono rimosse le eventuali esenzioni inserite nelle origini dati associate al responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="f5cbb-170">Se il responsabile è stato sottoposto *a* un blocco invisibile all'utente , in cui non sono state emesse notifiche di blocco legale, non verrà inviata una notifica di rilascio, ma le eventuali conservazioni nelle origini dati associate a tale responsabile verranno rimosse.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="f5cbb-171">Per rilasciare un responsabile:</span><span class="sxs-lookup"><span data-stu-id="f5cbb-171">To release a custodian:</span></span> 

1. <span data-ttu-id="f5cbb-172">Passare a **eDiscovery > Advanced eDiscovery** aprire il caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="f5cbb-173">Fare clic **sulla scheda** Origini.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="f5cbb-174">Nella pagina **Custodi,** quindi selezionare il responsabile che verrà rilasciato dal caso.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="f5cbb-175">Nella pagina a comparsa fare clic su **Rilascia responsabile.**</span><span class="sxs-lookup"><span data-stu-id="f5cbb-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="f5cbb-176">Viene visualizzata una pagina di avviso in cui viene spiegato che, se viene applicata un'esenzione a un'origine dati associata al responsabile, l'esenzione verrà rimossa e che qualsiasi altro blocco associato a un caso di Advanced eDiscovery diverso verrà comunque applicato.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="f5cbb-177">Che include altri tipi di funzionalità di conservazione e conservazione (ad esempio un criterio Microsoft 365 conservazione).</span><span class="sxs-lookup"><span data-stu-id="f5cbb-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="f5cbb-178">Fare **clic su** Sì per confermare che si desidera rilasciare il responsabile.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="f5cbb-179">Lo stato dell'utente nella scheda **Custodi** è  impostato su Rilasciato e lo stato di blocco nella pagina a comparsa viene impostato su **False.** </span><span class="sxs-lookup"><span data-stu-id="f5cbb-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="f5cbb-180">Un responsabile potrebbe essere coinvolto contemporaneamente in diversi casi legali.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="f5cbb-181">Quando un responsabile viene rilasciato da un caso, le esenzioni e le notifiche su altre questioni non saranno influenzate.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="f5cbb-182">Responsabile della modifica in blocco</span><span class="sxs-lookup"><span data-stu-id="f5cbb-182">Bulk-edit custodians</span></span>

<span data-ttu-id="f5cbb-183">Puoi usare l'editor in blocco per modificare più custodi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="f5cbb-184">A tale scopo, è sufficiente selezionare  due o più custodi nella scheda Custodi per visualizzare l'editor in blocco e quindi fare clic su una delle attività.</span><span class="sxs-lookup"><span data-stu-id="f5cbb-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Pagina a comparsa per modificare le impostazioni di più custodi](../media/AeDBulkEditCustodians.png)
