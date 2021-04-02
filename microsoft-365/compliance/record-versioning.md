---
title: Usare il controllo delle versioni per aggiornare i record archiviati in SharePoint o OneDrive
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
description: Informazioni sui record che semplificano l’implementazione di una soluzione di gestione dei record in Microsoft 365.
ms.openlocfilehash: 5c828f06f2ce9e2bd18869f897f1f372c1a62f21
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471125"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="679cb-103">Usare il controllo delle versioni per aggiornare i record archiviati in SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="679cb-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="679cb-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="679cb-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

>[!NOTE] 
> <span data-ttu-id="679cb-105">Poiché i record normativi bloccano la modifica, il controllo delle versioni dei record non è disponibile per i record normativi.</span><span class="sxs-lookup"><span data-stu-id="679cb-105">Because regulatory records block editing, record versioning is not available for regulatory records.</span></span>

<span data-ttu-id="679cb-106">La possibilità di contrassegnare un documento come [record](records-management.md#records) e limitare le azioni che è possibile eseguire su di esso rappresenta un obiettivo essenziale per qualsiasi soluzione di gestione dei record.</span><span class="sxs-lookup"><span data-stu-id="679cb-106">The ability to mark a document as a [record](records-management.md#records) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="679cb-107">Tuttavia, la collaborazione potrebbe essere necessaria anche per le persone che creano versioni successive.</span><span class="sxs-lookup"><span data-stu-id="679cb-107">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="679cb-108">Ad esempio, può capitare di contrassegnare come record un contratto di vendita, e che successivamente sia necessario aggiornare il contratto con nuovi termini e contrassegnare l'ultima versione come nuovo record conservando comunque la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="679cb-108">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="679cb-109">Per scenari di questo tipo, SharePoint e OneDrive supportano il *controllo delle versioni dei record*.</span><span class="sxs-lookup"><span data-stu-id="679cb-109">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="679cb-110">Le cartelle del blocco appunti di OneNote non supportano il controllo delle versioni dei record.</span><span class="sxs-lookup"><span data-stu-id="679cb-110">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="679cb-111">Per usare il controllo delle versioni dei record, è necessario prima di tutto [etichettare un documento e contrassegnarlo come record](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="679cb-111">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="679cb-112">Una volta fatto ciò, accanto all'etichetta di conservazione viene visualizzata una proprietà del documento denominata *Stato del record*, con lo stato del record iniziale impostato su **Bloccato**.</span><span class="sxs-lookup"><span data-stu-id="679cb-112">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="679cb-113">È possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="679cb-113">You can now do the following things:</span></span>

  - <span data-ttu-id="679cb-114">**Modificare e conservare continuamente come record singole versioni del documento, sbloccando e bloccando la proprietà Stato del record.**</span><span class="sxs-lookup"><span data-stu-id="679cb-114">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="679cb-115">Solo quando la proprietà **Stato del record** è impostata su **Bloccato** è una nuova versione del record conservata.</span><span class="sxs-lookup"><span data-stu-id="679cb-115">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="679cb-116">Questo consente di ridurre il rischio di mantenere le versioni e le copie inutili del documento.</span><span class="sxs-lookup"><span data-stu-id="679cb-116">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="679cb-117">**Archiviare automaticamente i record in un archivio dei record sul posto all'interno della raccolta siti.**</span><span class="sxs-lookup"><span data-stu-id="679cb-117">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="679cb-118">Ogni raccolta siti di SharePoint e OneDrive mantiene il contenuto nella propria raccolta di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="679cb-118">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="679cb-119">Le versioni dei record vengono archiviate nella cartella Record della raccolta.</span><span class="sxs-lookup"><span data-stu-id="679cb-119">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="679cb-120">**Conservare un documento sempre valido che contiene tutte le versioni.**</span><span class="sxs-lookup"><span data-stu-id="679cb-120">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="679cb-121">Per impostazione predefinita, ogni documento di SharePoint e OneDrive ha una cronologia delle versioni disponibile nel menu dell’elemento.</span><span class="sxs-lookup"><span data-stu-id="679cb-121">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="679cb-122">In questa cronologia delle versioni è possibile individuare facilmente le versioni record e visualizzare tali documenti.</span><span class="sxs-lookup"><span data-stu-id="679cb-122">In this version history, you can easily see which versions are records and view those documents.</span></span>

> [!TIP]
> <span data-ttu-id="679cb-123">Quando si usa il controllo delle versioni dei record con un'etichetta di conservazione che include un'azione di eliminazione, è consigliabile configurare anche l'impostazione di conservazione **Avvia il periodo di conservazione in base a:** impostandola su **Quando gli elementi sono stati etichettati**.</span><span class="sxs-lookup"><span data-stu-id="679cb-123">When you use record versioning with a retention label that has a delete action, consider configuring the retention setting **Start the retention period based on:** to be **When items were labeled**.</span></span> <span data-ttu-id="679cb-124">Con questa impostazione dell'etichetta, l'inizio del periodo di conservazione viene reimpostato per ogni nuova versione del record, in modo da garantire l'eliminazione delle versioni meno recenti prima di quelle più recenti.</span><span class="sxs-lookup"><span data-stu-id="679cb-124">With this label setting, the start of the retention period is reset for each new record version, which ensures that older versions will be deleted before newer versions.</span></span>

<span data-ttu-id="679cb-125">Il controllo delle versioni del record è automaticamente disponibile per qualsiasi documento con un'etichetta di conservazione che contrassegna l'elemento come record.</span><span class="sxs-lookup"><span data-stu-id="679cb-125">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="679cb-126">Quando un utente visualizza le proprietà del documento tramite il riquadro dei dettagli, può cambiare lo **Stato del record** da **Bloccato** a **Sbloccato**.</span><span class="sxs-lookup"><span data-stu-id="679cb-126">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="679cb-127">Questa azione crea un record nella cartella Record della raccolta di archiviazione, dove rimane fino alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="679cb-127">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="679cb-128">Quando il documento è sbloccato, qualsiasi utente con autorizzazioni di modifica standard può modificare il file.</span><span class="sxs-lookup"><span data-stu-id="679cb-128">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="679cb-129">Tuttavia, gli utenti non possono eliminare il file, perché è ancora considerato un record.</span><span class="sxs-lookup"><span data-stu-id="679cb-129">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="679cb-130">Una volta completato il processo di modifica, l'utente può quindi impostare lo **Stato del record** da **Sbloccato** a **Bloccato**, che impedisce ulteriori modifiche in questo stato.</span><span class="sxs-lookup"><span data-stu-id="679cb-130">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Proprietà Stato del record nel documento taggato come record](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="679cb-132">Bloccare e sbloccare un record</span><span class="sxs-lookup"><span data-stu-id="679cb-132">Locking and unlocking a record</span></span>

<span data-ttu-id="679cb-133">Dopo aver applicato a un documento un'etichetta di conservazione che contrassegna un contenuto come record, qualsiasi utente con il livello di autorizzazione Collaborazione o inferiore può sbloccare un record o bloccare un record sbloccato.</span><span class="sxs-lookup"><span data-stu-id="679cb-133">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Lo stato del record mostra se il documento record è sbloccato](../media/recordversioning9.png)

<span data-ttu-id="679cb-135">Quando un utente sblocca un record, si verificano le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="679cb-135">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="679cb-136">Se la raccolta siti corrente non ha una raccolta di archiviazione, ne viene creata una.</span><span class="sxs-lookup"><span data-stu-id="679cb-136">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="679cb-137">Se nella raccolta di archiviazione non è presente una cartella Record, ne viene creata una.</span><span class="sxs-lookup"><span data-stu-id="679cb-137">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="679cb-138">Un’azione **Copia in** copia l'ultima versione del documento nella cartella Record.</span><span class="sxs-lookup"><span data-stu-id="679cb-138">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="679cb-139">L'azione **Copia in** include solo la versione più recente e non quelle precedenti.</span><span class="sxs-lookup"><span data-stu-id="679cb-139">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="679cb-140">Il documento copiato è ora considerato come versione record del documento e il suo nome file ha il formato: \[Titolo GUID Versione\#\]</span><span class="sxs-lookup"><span data-stu-id="679cb-140">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="679cb-141">La copia creata nella cartella Record viene aggiunta alla cronologia delle versioni del documento originale e questa versione riporta la parola **Record** nel campo Commenti.</span><span class="sxs-lookup"><span data-stu-id="679cb-141">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="679cb-142">Il documento originale è una nuova versione che può essere modificata ma non eliminata.</span><span class="sxs-lookup"><span data-stu-id="679cb-142">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="679cb-143">La colonna della raccolta del documento **L’elemento è un record** mostra ancora il valore **Sì** perché il documento è ancora un record, anche se ora può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="679cb-143">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="679cb-144">Quando un utente blocca un record, il documento originale torna a non essere modificabile.</span><span class="sxs-lookup"><span data-stu-id="679cb-144">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="679cb-145">Ma è l'azione di sbloccare un record che ne copia una versione nella cartella Record della raccolta di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="679cb-145">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="679cb-146">Versioni del record</span><span class="sxs-lookup"><span data-stu-id="679cb-146">Record versions</span></span>

<span data-ttu-id="679cb-147">Ogni volta che un utente sblocca un record, la versione più recente viene copiata nella raccolta di archiviazione, che contiene il valore di **Record** nel campo **Commenti** della cronologia delle versioni.</span><span class="sxs-lookup"><span data-stu-id="679cb-147">Each time a user unlocks a record, the latest version is copied to the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Record mostrato nella raccolta di archiviazione](../media/recordversioning10.png)

<span data-ttu-id="679cb-149">Per visualizzare la cronologia delle versioni, selezionare un documento nella raccolta documenti e quindi fare clic su **Cronologia delle versioni** nel menu dell’elemento.</span><span class="sxs-lookup"><span data-stu-id="679cb-149">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="679cb-150">Dove vengono archiviati i record</span><span class="sxs-lookup"><span data-stu-id="679cb-150">Where records are stored</span></span>

<span data-ttu-id="679cb-151">I record vengono archiviati nella cartella Record della raccolta di archiviazione nel sito principale della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="679cb-151">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="679cb-152">Nel riquadro di spostamento sinistro del sito principale scegliere **Contenuto del sito** \> **Raccolta di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="679cb-152">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Raccolta di archiviazione](../media/recordversioning11.png)

<br/><br/>

![Cartella Record nella raccolta di archiviazione](../media/recordversioning12.png)

<span data-ttu-id="679cb-155">Per altre informazioni sul funzionamento della raccolta di archiviazione, vedere [Come funziona la conservazione per SharePoint e OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span><span class="sxs-lookup"><span data-stu-id="679cb-155">For more information about how the Preservation Hold library works, see [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="679cb-156">Cercare nel log di controllo gli eventi di controllo delle versioni del record</span><span class="sxs-lookup"><span data-stu-id="679cb-156">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="679cb-157">Le azioni per bloccare e sbloccare i record vengono registrate nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="679cb-157">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="679cb-158">In **Attività su file e pagine** selezionare **Stato del record modificato in Bloccato** e **Stato del record modificato in Sbloccato**.</span><span class="sxs-lookup"><span data-stu-id="679cb-158">From **File and page activities**, select **Changed record status to locked** and **Changed record status to unlocked**.</span></span>

<span data-ttu-id="679cb-159">Per altre informazioni su come cercare questi eventi, vedere [Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="679cb-159">For more information about searching for these events, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="679cb-160">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="679cb-160">Next steps</span></span>

<span data-ttu-id="679cb-161">Per altri scenari supportati dalla gestione dei record, vedere [Scenari comuni per la gestione dei record](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="679cb-161">For other scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>