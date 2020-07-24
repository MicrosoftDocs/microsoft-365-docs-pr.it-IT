---
title: Informazioni sui record
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Informazioni sui record utili per implementare una soluzione di gestione dei record in Microsoft 365.
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372521"
---
# <a name="learn-about-records"></a><span data-ttu-id="ceb50-103">Informazioni sui record</span><span class="sxs-lookup"><span data-stu-id="ceb50-103">Learn about records</span></span>

><span data-ttu-id="ceb50-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="ceb50-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="ceb50-105">La gestione dei record in Microsoft 365 consente alle organizzazioni di conformarsi alle politiche aziendali e agli obblighi legali o normativi, riducendo inoltre i rischi e le responsabilità legali.</span><span class="sxs-lookup"><span data-stu-id="ceb50-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="ceb50-106">Quando un contenuto viene contrassegnato come record:</span><span class="sxs-lookup"><span data-stu-id="ceb50-106">When content is marked as a record:</span></span>

- <span data-ttu-id="ceb50-107">Vengono applicate restrizioni agli elementi in base alle [azioni consentite o bloccate](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="ceb50-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="ceb50-108">Vengono registrate altre attività relative all'elemento.</span><span class="sxs-lookup"><span data-stu-id="ceb50-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="ceb50-109">Si ha una prova dell'eliminazione quando l'elemento viene eliminato al termine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="ceb50-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="ceb50-110">Usare [etichette di conservazione ](retention.md#retention-labels) per contrassegnare un contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="ceb50-111">È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="ceb50-112">Usando le etichette di conservazione per contrassegnare il contenuto come record, è possibile implementare una strategia unica e coerente per la gestione dei record nell'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ceb50-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="ceb50-113">Confronto tra le restrizioni relative alle azioni consentite o bloccate</span><span class="sxs-lookup"><span data-stu-id="ceb50-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="ceb50-114">Usare la tabella seguente per identificare quali restrizioni vengono applicate al contenuto in seguito all'applicazione di un'etichetta di conservazione standard e di etichette di conservazione che contrassegnano il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="ceb50-115">Un'etichetta di conservazione standard include la configurazione per mantenere i dati senza contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="ceb50-116">Per completezza di informazioni, la tabella include colonne per un record bloccato e sbloccato, applicabile a SharePoint e OneDrive, ma non a Exchange.</span><span class="sxs-lookup"><span data-stu-id="ceb50-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="ceb50-117">Per bloccare e sbloccare un record viene usato il [controllo delle versioni dei record](#record-versioning), che non è supportato per gli elementi di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ceb50-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="ceb50-118">Quindi, per tutti gli elementi di Exchange contrassegnati come record, il comportamento mappato alla colonna **Record: bloccato** e alla colonna **Record: non bloccato** non è pertinente.</span><span class="sxs-lookup"><span data-stu-id="ceb50-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="ceb50-119">Azione</span><span class="sxs-lookup"><span data-stu-id="ceb50-119">Action</span></span>| <span data-ttu-id="ceb50-120">Etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="ceb50-120">Retention label</span></span> |<span data-ttu-id="ceb50-121">Record: bloccato</span><span class="sxs-lookup"><span data-stu-id="ceb50-121">Record - locked</span></span>| <span data-ttu-id="ceb50-122">Record: sbloccato</span><span class="sxs-lookup"><span data-stu-id="ceb50-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ceb50-123">Modifica contenuti</span><span class="sxs-lookup"><span data-stu-id="ceb50-123">Edit contents</span></span>|<span data-ttu-id="ceb50-124">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-124">Allowed</span></span> | <span data-ttu-id="ceb50-125">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="ceb50-125">**Blocked**</span></span> | <span data-ttu-id="ceb50-126">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-126">Allowed</span></span>|
|<span data-ttu-id="ceb50-127">Modifica le proprietà, tra cui Rinomina</span><span class="sxs-lookup"><span data-stu-id="ceb50-127">Edit properties, including rename</span></span>|<span data-ttu-id="ceb50-128">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-128">Allowed</span></span> |<span data-ttu-id="ceb50-129">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-129">Allowed</span></span> | <span data-ttu-id="ceb50-130">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-130">Allowed</span></span>|
|<span data-ttu-id="ceb50-131">Elimina</span><span class="sxs-lookup"><span data-stu-id="ceb50-131">Delete</span></span>|<span data-ttu-id="ceb50-132">Consentito <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ceb50-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="ceb50-133">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="ceb50-133">**Blocked**</span></span> | <span data-ttu-id="ceb50-134">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="ceb50-134">**Blocked**</span></span>|
|<span data-ttu-id="ceb50-135">Copia</span><span class="sxs-lookup"><span data-stu-id="ceb50-135">Copy</span></span>|<span data-ttu-id="ceb50-136">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-136">Allowed</span></span> |<span data-ttu-id="ceb50-137">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-137">Allowed</span></span> | <span data-ttu-id="ceb50-138">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-138">Allowed</span></span>|
|<span data-ttu-id="ceb50-139">Sposta all'interno del container <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ceb50-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="ceb50-140">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-140">Allowed</span></span> |<span data-ttu-id="ceb50-141">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-141">Allowed</span></span> | <span data-ttu-id="ceb50-142">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-142">Allowed</span></span>|
|<span data-ttu-id="ceb50-143">Sposta tra container <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ceb50-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="ceb50-144">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-144">Allowed</span></span> |<span data-ttu-id="ceb50-145">Consentito se mai sbloccato</span><span class="sxs-lookup"><span data-stu-id="ceb50-145">Allowed if never unlocked</span></span> | <span data-ttu-id="ceb50-146">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-146">Allowed</span></span>|
|<span data-ttu-id="ceb50-147">Apri/leggi</span><span class="sxs-lookup"><span data-stu-id="ceb50-147">Open/Read</span></span>|<span data-ttu-id="ceb50-148">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-148">Allowed</span></span> |<span data-ttu-id="ceb50-149">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-149">Allowed</span></span> | <span data-ttu-id="ceb50-150">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-150">Allowed</span></span>|
|<span data-ttu-id="ceb50-151">Cambia etichetta</span><span class="sxs-lookup"><span data-stu-id="ceb50-151">Change label</span></span>|<span data-ttu-id="ceb50-152">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-152">Allowed</span></span> |<span data-ttu-id="ceb50-153">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="ceb50-153">Allowed - container admin only</span></span> | <span data-ttu-id="ceb50-154">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="ceb50-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="ceb50-155">Rimuovi etichetta</span><span class="sxs-lookup"><span data-stu-id="ceb50-155">Remove label</span></span>|<span data-ttu-id="ceb50-156">Consentito</span><span class="sxs-lookup"><span data-stu-id="ceb50-156">Allowed</span></span> |<span data-ttu-id="ceb50-157">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="ceb50-157">Allowed - container admin only</span></span> | <span data-ttu-id="ceb50-158">Consentito: solo amministratori container</span><span class="sxs-lookup"><span data-stu-id="ceb50-158">Allowed - container admin only</span></span>|

<span data-ttu-id="ceb50-159">Note a piè di pagina:</span><span class="sxs-lookup"><span data-stu-id="ceb50-159">Footnotes:</span></span>

<span data-ttu-id="ceb50-160"><sup>1</sup> Supportato da OneDrive ed Exchange conservando una copia in una posizione protetta, ma bloccato da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ceb50-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="ceb50-161">Messaggio che un utente vede se tenta di eliminare un documento con etichetta in SharePoint:</span><span class="sxs-lookup"><span data-stu-id="ceb50-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Messaggio che segnala che un elemento non è stato eliminato da SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="ceb50-163"><sup>2</sup> I container includono le raccolte documenti in SharePoint e le cassette postali in Exchange.</span><span class="sxs-lookup"><span data-stu-id="ceb50-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="ceb50-164">Usare le etichette di conservazione per dichiarare i record</span><span class="sxs-lookup"><span data-stu-id="ceb50-164">Using retention labels to declare records</span></span>

<span data-ttu-id="ceb50-165">Quando si crea un'etichetta di conservazione, si può scegliere di usarla per contrassegnare il contenuto come record:</span><span class="sxs-lookup"><span data-stu-id="ceb50-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="ceb50-166">Nel Centro conformità Microsoft 365 passare a **Gestione record** \> **Piano di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="ceb50-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="ceb50-167">Nella pagina **Piano di archiviazione**, selezionare **Crea un'etichetta**.</span><span class="sxs-lookup"><span data-stu-id="ceb50-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="ceb50-168">Nella pagina **Impostazioni etichetta** della procedura guidata scegliere l'opzione di impostazione dell'etichetta di conservazione per contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Fare clic sulla casella di controllo Utilizza l'etichetta per contrassegnare il contenuto come Record](../media/recordversioning6.png)

3. <span data-ttu-id="ceb50-170">Applicare l'etichetta di conservazione ai documenti di SharePoint o OneDrive e ai messaggi di posta elettronica di Exchange, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ceb50-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="ceb50-171">Per istruzioni:</span><span class="sxs-lookup"><span data-stu-id="ceb50-171">For instructions:</span></span>
    
    - [<span data-ttu-id="ceb50-172">Creare etichette di conservazione e applicarle nelle app</span><span class="sxs-lookup"><span data-stu-id="ceb50-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="ceb50-173">Applicare automaticamente un'etichetta di conservazione al contenuto</span><span class="sxs-lookup"><span data-stu-id="ceb50-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="ceb50-174">Applicare l'etichetta di conservazione configurata al contenuto</span><span class="sxs-lookup"><span data-stu-id="ceb50-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="ceb50-175">Quando le etichette di conservazione che classificano il contenuto come record vengono rese disponibili agli utenti per applicarle nelle app:</span><span class="sxs-lookup"><span data-stu-id="ceb50-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="ceb50-176">Per Exchange, qualsiasi utente con accesso in scrittura alla cassetta postale può applicare queste etichette.</span><span class="sxs-lookup"><span data-stu-id="ceb50-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="ceb50-177">Per SharePoint e OneDrive, qualsiasi utente del gruppo Membri predefinito (con livello di autorizzazione Collaborazione) può applicare queste etichette.</span><span class="sxs-lookup"><span data-stu-id="ceb50-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="ceb50-178">Esempio di documento contrassegnato come record da un'etichetta di conservazione:</span><span class="sxs-lookup"><span data-stu-id="ceb50-178">Example of a document marked as record by using a retention label:</span></span>

![Riquadro dei dettagli per un documento taggato come record](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="ceb50-180">Controllo delle versioni del record</span><span class="sxs-lookup"><span data-stu-id="ceb50-180">Record versioning</span></span>

<span data-ttu-id="ceb50-181">La possibilità di contrassegnare un documento come record e limitare le azioni che è possibile eseguire sul record rappresenta un obiettivo essenziale per qualsiasi soluzione di gestione dei record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="ceb50-182">Tuttavia, la collaborazione potrebbe essere necessaria anche per le persone che creano versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ceb50-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="ceb50-183">Ad esempio, può capitare di contrassegnare come record un contratto di vendita, e che successivamente sia necessario aggiornare il contratto con nuovi termini e contrassegnare l'ultima versione come nuovo record conservando comunque la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="ceb50-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="ceb50-184">Per scenari di questo tipo, SharePoint e OneDrive supportano il *controllo delle versioni dei record*.</span><span class="sxs-lookup"><span data-stu-id="ceb50-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="ceb50-185">Le cartelle del blocco appunti di OneNote non supportano il controllo delle versioni dei record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="ceb50-186">Per usare il controllo delle versioni dei record, è necessario prima di tutto etichettare un documento e contrassegnarlo come record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="ceb50-187">Una volta fatto ciò, accanto all'etichetta di conservazione viene visualizzata una proprietà del documento denominata *Stato del record*, con lo stato del record iniziale impostato su **Bloccato**.</span><span class="sxs-lookup"><span data-stu-id="ceb50-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="ceb50-188">È possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ceb50-188">You can now do the following things:</span></span>

  - <span data-ttu-id="ceb50-189">**Modificare e conservare continuamente come record singole versioni del documento, sbloccando e bloccando la proprietà Stato del record.**</span><span class="sxs-lookup"><span data-stu-id="ceb50-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="ceb50-190">Solo quando la proprietà **Stato del record** è impostata su **Bloccato** è una nuova versione del record conservata.</span><span class="sxs-lookup"><span data-stu-id="ceb50-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="ceb50-191">Questo consente di ridurre il rischio di mantenere le versioni e le copie inutili del documento.</span><span class="sxs-lookup"><span data-stu-id="ceb50-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="ceb50-192">**Archiviare automaticamente i record in un archivio dei record sul posto all'interno della raccolta siti.**</span><span class="sxs-lookup"><span data-stu-id="ceb50-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="ceb50-193">Ogni raccolta siti di SharePoint e OneDrive mantiene il contenuto nella propria raccolta di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ceb50-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="ceb50-194">Le versioni dei record vengono archiviate nella cartella Record della raccolta.</span><span class="sxs-lookup"><span data-stu-id="ceb50-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="ceb50-195">**Conservare un documento sempre valido che contiene tutte le versioni.**</span><span class="sxs-lookup"><span data-stu-id="ceb50-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="ceb50-196">Per impostazione predefinita, ogni documento di SharePoint e OneDrive ha una cronologia delle versioni disponibile nel menu dell’elemento.</span><span class="sxs-lookup"><span data-stu-id="ceb50-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="ceb50-197">In questa cronologia delle versioni è possibile individuare facilmente le versioni record e visualizzare tali documenti.</span><span class="sxs-lookup"><span data-stu-id="ceb50-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="ceb50-198">Il controllo delle versioni del record è automaticamente disponibile per qualsiasi documento con un'etichetta di conservazione che contrassegna l'elemento come record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="ceb50-199">Quando un utente visualizza le proprietà del documento tramite il riquadro dei dettagli, può cambiare lo **Stato del record** da **Bloccato** a **Sbloccato**.</span><span class="sxs-lookup"><span data-stu-id="ceb50-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="ceb50-200">Questa azione crea un record nella cartella Record della raccolta di archiviazione, dove rimane fino alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="ceb50-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="ceb50-201">Quando il documento è sbloccato, qualsiasi utente con autorizzazioni di modifica standard può modificare il file.</span><span class="sxs-lookup"><span data-stu-id="ceb50-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="ceb50-202">Tuttavia, gli utenti non possono eliminare il file, perché è ancora considerato un record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="ceb50-203">Una volta completato il processo di modifica, l'utente può quindi impostare lo **Stato del record** da **Sbloccato** a **Bloccato**, che impedisce ulteriori modifiche in questo stato.</span><span class="sxs-lookup"><span data-stu-id="ceb50-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Proprietà Stato del record nel documento taggato come record](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="ceb50-205">Bloccare e sbloccare un record</span><span class="sxs-lookup"><span data-stu-id="ceb50-205">Locking and unlocking a record</span></span>

<span data-ttu-id="ceb50-206">Dopo aver applicato a un documento un'etichetta di conservazione che contrassegna un contenuto come record, qualsiasi utente con il livello di autorizzazione Collaborazione o inferiore può sbloccare un record o bloccare un record sbloccato.</span><span class="sxs-lookup"><span data-stu-id="ceb50-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Lo stato del record mostra se il documento record è sbloccato](../media/recordversioning9.png)

<span data-ttu-id="ceb50-208">Quando un utente sblocca un record, si verificano le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ceb50-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="ceb50-209">Se la raccolta siti corrente non ha una raccolta di archiviazione, ne viene creata una.</span><span class="sxs-lookup"><span data-stu-id="ceb50-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="ceb50-210">Se nella raccolta di archiviazione non è presente una cartella Record, ne viene creata una.</span><span class="sxs-lookup"><span data-stu-id="ceb50-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="ceb50-211">Un’azione **Copia in** copia l'ultima versione del documento nella cartella Record.</span><span class="sxs-lookup"><span data-stu-id="ceb50-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="ceb50-212">L'azione **Copia in** include solo la versione più recente e non quelle precedenti.</span><span class="sxs-lookup"><span data-stu-id="ceb50-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="ceb50-213">Il documento copiato è ora considerato come versione record del documento e il suo nome file ha il formato: \[Titolo GUID Versione\#\]</span><span class="sxs-lookup"><span data-stu-id="ceb50-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="ceb50-214">La copia creata nella cartella Record viene aggiunta alla cronologia delle versioni del documento originale e questa versione riporta la parola **Record** nel campo Commenti.</span><span class="sxs-lookup"><span data-stu-id="ceb50-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="ceb50-215">Il documento originale è una nuova versione che può essere modificata ma non eliminata.</span><span class="sxs-lookup"><span data-stu-id="ceb50-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="ceb50-216">La colonna della raccolta del documento **L’elemento è un record** mostra ancora il valore **Sì** perché il documento è ancora un record, anche se ora può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="ceb50-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="ceb50-217">Quando un utente blocca un record, il documento originale torna a non essere modificabile.</span><span class="sxs-lookup"><span data-stu-id="ceb50-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="ceb50-218">Ma è l'azione di sbloccare un record che ne copia una versione nella cartella Record della raccolta di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ceb50-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="ceb50-219">Versioni del record</span><span class="sxs-lookup"><span data-stu-id="ceb50-219">Record versions</span></span>

<span data-ttu-id="ceb50-220">Ogni volta che un utente sblocca un record, la versione più recente viene copiata nella cartella Record della raccolta di archiviazione, che contiene il valore di **Record** nel campo **Commenti** della cronologia delle versioni.</span><span class="sxs-lookup"><span data-stu-id="ceb50-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Record mostrato nella raccolta di archiviazione](../media/recordversioning10.png)

<span data-ttu-id="ceb50-222">Per visualizzare la cronologia delle versioni, selezionare un documento nella raccolta documenti e quindi fare clic su **Cronologia delle versioni** nel menu dell’elemento.</span><span class="sxs-lookup"><span data-stu-id="ceb50-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="ceb50-223">Dove vengono archiviati i record</span><span class="sxs-lookup"><span data-stu-id="ceb50-223">Where records are stored</span></span>

<span data-ttu-id="ceb50-224">I record vengono archiviati nella cartella Record della raccolta di archiviazione nel sito principale della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="ceb50-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="ceb50-225">Nel riquadro di spostamento sinistro del sito principale scegliere **Contenuto del sito** \> **Raccolta di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="ceb50-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Raccolta di archiviazione](../media/recordversioning11.png)

<br/><br/>

![Cartella Record nella raccolta di archiviazione](../media/recordversioning12.png)

<span data-ttu-id="ceb50-228">La raccolta di archiviazione è visibile solo agli amministratori della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="ceb50-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="ceb50-229">Inoltre, la raccolta di archiviazione non esiste per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ceb50-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="ceb50-230">Viene creata solo quando il contenuto soggetto a un'etichetta o a un criterio di conservazione viene eliminato per la prima volta nella raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="ceb50-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="ceb50-231">Cercare nel log di controllo gli eventi di controllo delle versioni del record</span><span class="sxs-lookup"><span data-stu-id="ceb50-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="ceb50-232">Le azioni per bloccare e sbloccare i record vengono registrate nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="ceb50-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="ceb50-233">È possibile cercare le attività specifiche **Stato del record modificato in Bloccato** e **Stato del record modificato in Sbloccato**, che si trovano nella sezione **Attività su file e pagine** nell'elenco a discesa **Attività** nella pagina **Ricerca log di controllo** nel centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="ceb50-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Cercare nel log di controllo gli eventi di controllo delle versioni del record](../media/recordversioning13.png)

<span data-ttu-id="ceb50-235">Per altre informazioni su come cercare questi eventi, vedere la sezione "Attività su file e pagine" in [Ricerche nel log di controllo Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="ceb50-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ceb50-236">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ceb50-236">Next steps</span></span>

<span data-ttu-id="ceb50-237">Se non si hanno ancora etichette di conservazione da usare per la gestione dei record, vedere [Introduzione ai criteri e alle etichette di conservazione](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="ceb50-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="ceb50-238">Per ulteriori informazioni sull'eliminazone dei record, vedere [Eliminazione dei record](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="ceb50-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
