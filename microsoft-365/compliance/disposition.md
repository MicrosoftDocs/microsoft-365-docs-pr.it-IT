---
title: Disposizione del contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Monitorare e gestire lo smaltimento del contenuto, sia che si utilizzi una recensione di disposizione o che il contenuto venga eliminato automaticamente in base alle impostazioni configurate.
ms.openlocfilehash: 5751857f8b3bf0a7f63df73e9bfaa244897bf429
ms.sourcegitcommit: 4ac96855d7c269a0055ca8943000b762a70ca4ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321995"
---
# <a name="disposition-of-content"></a><span data-ttu-id="1be2b-103">Disposizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="1be2b-103">Disposition of content</span></span>

><span data-ttu-id="1be2b-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="1be2b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1be2b-105">Utilizzare la scheda **disposizione** dalla **gestione dei record** nel centro conformità di Microsoft 365 per gestire le revisioni di disposizione e visualizzare i [record](records-management.md#records) eliminati automaticamente alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="1be2b-106">Prerequisiti per la visualizzazione di disposizioni di contenuto</span><span class="sxs-lookup"><span data-stu-id="1be2b-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="1be2b-107">Per gestire le recensioni sulla disposizione e verificare che i record siano stati eliminati, è necessario disporre di autorizzazioni e controllo sufficienti.</span><span class="sxs-lookup"><span data-stu-id="1be2b-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="1be2b-108">Autorizzazioni per la disposizione</span><span class="sxs-lookup"><span data-stu-id="1be2b-108">Permissions for disposition</span></span>

<span data-ttu-id="1be2b-109">Per accedere correttamente alla scheda **disposizione** nel centro conformità di Microsoft 365, è necessario che gli utenti dispongano del ruolo amministratore **gestione disposizione** .</span><span class="sxs-lookup"><span data-stu-id="1be2b-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="1be2b-110">Questo ruolo è incluso nei gruppi di ruoli di amministratore predefiniti, nell'amministratore della **conformità** e nell' **amministratore dei dati di conformità**.</span><span class="sxs-lookup"><span data-stu-id="1be2b-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="1be2b-111">Per concedere agli utenti il ruolo di gestione della disposizione necessario, aggiungerli a uno di questi gruppi di ruoli predefiniti oppure creare un gruppo di ruoli personalizzato, ad esempio denominato "revisori disposizione", e concedere a tale gruppo il ruolo di gestione della disposizione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="1be2b-112">Anche a un amministratore globale deve essere concesso il ruolo di **gestione della disposizione** .</span><span class="sxs-lookup"><span data-stu-id="1be2b-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="1be2b-113">Per le istruzioni, vedere [Fornire agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1be2b-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="1be2b-114">Abilitazione del controllo</span><span class="sxs-lookup"><span data-stu-id="1be2b-114">Enable auditing</span></span>

<span data-ttu-id="1be2b-115">Verificare che il controllo sia abilitato almeno un giorno prima della prima azione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="1be2b-116">Per ulteriori informazioni, vedere [eseguire la ricerca nel log di controllo nel centro sicurezza e &amp; conformità di Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="1be2b-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="1be2b-117">Revisioni per l'eliminazione</span><span class="sxs-lookup"><span data-stu-id="1be2b-117">Disposition reviews</span></span>

<span data-ttu-id="1be2b-118">Quando il contenuto raggiunge la fine del periodo di conservazione, è possibile che si desideri rivedere il contenuto per decidere se può essere eliminato in modo sicuro ("Disposed").</span><span class="sxs-lookup"><span data-stu-id="1be2b-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="1be2b-119">Ad esempio, potrebbe essere necessario:</span><span class="sxs-lookup"><span data-stu-id="1be2b-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="1be2b-120">Sospendere l'eliminazione del contenuto pertinente in caso di controversia legale o di controllo.</span><span class="sxs-lookup"><span data-stu-id="1be2b-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="1be2b-121">Rimuovere il contenuto dall'elenco di disposizione per archiviarlo in un archivio, se il contenuto ha una ricerca o un valore cronologico.</span><span class="sxs-lookup"><span data-stu-id="1be2b-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="1be2b-122">Assegnare un periodo di conservazione diverso al contenuto, probabilmente perché le impostazioni di conservazione originali erano una soluzione temporanea o provvisoria.</span><span class="sxs-lookup"><span data-stu-id="1be2b-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="1be2b-123">Restituire il contenuto ai client o trasferirlo in un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="1be2b-124">Quando viene attivata una revisione della disposizione alla fine del periodo di conservazione:</span><span class="sxs-lookup"><span data-stu-id="1be2b-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="1be2b-125">Gli utenti che scelgono ricevono una notifica tramite posta elettronica che dispongono di contenuto da esaminare.</span><span class="sxs-lookup"><span data-stu-id="1be2b-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="1be2b-126">Questi revisori possono essere singoli utenti o gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1be2b-126">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="1be2b-127">Si noti che le notifiche vengono inviate su base settimanale.</span><span class="sxs-lookup"><span data-stu-id="1be2b-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="1be2b-128">I revisori passano alla scheda **disposizione** del centro conformità Microsoft 365 per esaminare il contenuto e decidere se eliminarlo definitivamente, estenderne il periodo di conservazione o applicare un'etichetta di conservazione diversa.</span><span class="sxs-lookup"><span data-stu-id="1be2b-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="1be2b-129">Una recensione di disposizione può includere il contenuto nelle cassette postali di Exchange, siti di SharePoint, account di OneDrive e gruppi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1be2b-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="1be2b-130">Il contenuto in attesa di una revisione della disposizione in tali posizioni viene eliminato solo dopo che un revisore sceglie di eliminare definitivamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="1be2b-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="1be2b-131">Una cassetta postale deve disporre di almeno 10 MB di dati per il supporto delle recensioni sulla disposizione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="1be2b-132">È possibile visualizzare una panoramica di tutte le disposizioni in sospeso nella scheda **Panoramica** . Per esempio:</span><span class="sxs-lookup"><span data-stu-id="1be2b-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Disposizioni in sospeso nella panoramica della gestione dei record](../media/dispositions-overview.png)

<span data-ttu-id="1be2b-134">Quando si seleziona la **visualizzazione tutte le disposizioni in sospeso**, viene visualizzata la pagina **disposizione** .</span><span class="sxs-lookup"><span data-stu-id="1be2b-134">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="1be2b-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1be2b-135">For example:</span></span>

![Pagina disposizioni in Microsoft 365 Compliance Center](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="1be2b-137">Flusso di lavoro per una revisione della disposizione</span><span class="sxs-lookup"><span data-stu-id="1be2b-137">Workflow for a disposition review</span></span>

<span data-ttu-id="1be2b-138">Nel diagramma seguente viene illustrato il flusso di lavoro di base per una revisione della disposizione quando viene pubblicata un'etichetta di conservazione e quindi applicata manualmente da un utente.</span><span class="sxs-lookup"><span data-stu-id="1be2b-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="1be2b-139">In alternativa, un'etichetta di conservazione configurata per una revisione di disposizione può essere applicata automaticamente al contenuto.</span><span class="sxs-lookup"><span data-stu-id="1be2b-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Grafico che mostra il flusso di come funziona la disposizione](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="1be2b-141">L'attivazione di una revisione della disposizione alla fine del periodo di conservazione è un'opzione di configurazione disponibile solo con un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="1be2b-142">Questa opzione non è disponibile per un criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="1be2b-143">Per ulteriori informazioni su queste due soluzioni di conservazione, vedere informazioni [sui criteri di conservazione e sulle etichette di conservazione](retention.md).</span><span class="sxs-lookup"><span data-stu-id="1be2b-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![Impostazioni di conservazione per un'etichetta](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="1be2b-145">Quando si seleziona l'opzione **notifica a queste persone quando sono disponibili elementi pronti per la revisione**, specificare un utente o un gruppo di sicurezza abilitato alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1be2b-145">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="1be2b-146">I gruppi Microsoft 365 (in[precedenza gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) non sono supportati per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-146">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="1be2b-147">Visualizzazione e eliminazione del contenuto</span><span class="sxs-lookup"><span data-stu-id="1be2b-147">Viewing and disposing of content</span></span>

<span data-ttu-id="1be2b-148">Quando un revisore riceve una notifica tramite posta elettronica che il contenuto è pronto per la revisione, accede alla scheda **disposizione** dalla **gestione dei record** nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1be2b-148">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1be2b-149">I revisori possono vedere quanti elementi per ogni etichetta di conservazione sono in attesa di disposizione, quindi selezionare un'etichetta di conservazione per visualizzare tutto il contenuto con quell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="1be2b-149">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="1be2b-150">Dopo aver selezionato un'etichetta di conservazione, è possibile visualizzare tutte le disposizioni in sospeso per tale etichetta dalla scheda **disposizione in sospeso** . Selezionare uno o più elementi in cui è possibile scegliere un'azione e immettere un commento di giustificazione:</span><span class="sxs-lookup"><span data-stu-id="1be2b-150">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opzioni di disposizione](../media/retention-disposition-options.png)

<span data-ttu-id="1be2b-152">Come si può vedere dall'immagine, le azioni supportate sono:</span><span class="sxs-lookup"><span data-stu-id="1be2b-152">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="1be2b-153">Elimina definitivamente l'elemento</span><span class="sxs-lookup"><span data-stu-id="1be2b-153">Permanently delete the item</span></span>
- <span data-ttu-id="1be2b-154">Estendere il periodo di conservazione</span><span class="sxs-lookup"><span data-stu-id="1be2b-154">Extend the retention period</span></span>
- <span data-ttu-id="1be2b-155">Applicazione di un'etichetta di conservazione diversa</span><span class="sxs-lookup"><span data-stu-id="1be2b-155">Apply a different retention label</span></span>

<span data-ttu-id="1be2b-156">Se si dispone delle autorizzazioni per la posizione e il contenuto, è possibile utilizzare il collegamento nella colonna **percorso** per visualizzare i documenti nel percorso originale.</span><span class="sxs-lookup"><span data-stu-id="1be2b-156">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="1be2b-157">Durante una revisione della disposizione, il contenuto non si sposta mai dal percorso originale e non viene mai eliminato fino a quando il revisore non lo sceglie.</span><span class="sxs-lookup"><span data-stu-id="1be2b-157">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="1be2b-158">Le notifiche di posta elettronica vengono inviate automaticamente ai revisori su base settimanale.</span><span class="sxs-lookup"><span data-stu-id="1be2b-158">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="1be2b-159">Questo processo pianificato indica che quando il contenuto raggiunge la fine del periodo di conservazione, potrebbero essere necessari fino a sette giorni affinché i revisori ricevano la notifica di posta elettronica che il contenuto è in attesa di disposizione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-159">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="1be2b-160">È possibile controllare tutte le azioni di disposizione e il testo di giustificazione immesso dal revisore viene salvato e visualizzato nella colonna **Commento** della pagina **elementi eliminati** .</span><span class="sxs-lookup"><span data-stu-id="1be2b-160">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="1be2b-161">Durata dell'eliminazione definitiva del contenuto eliminato</span><span class="sxs-lookup"><span data-stu-id="1be2b-161">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="1be2b-162">Il contenuto in attesa di una revisione della disposizione viene eliminato solo dopo che un revisore sceglie di eliminare definitivamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="1be2b-162">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="1be2b-163">Quando il revisore sceglie questa opzione, il contenuto del sito di SharePoint o dell'account OneDrive diventa idoneo per il processo di pulizia standard descritto in [modalità di funzionamento delle impostazioni di conservazione con il contenuto sul posto](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="1be2b-163">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="1be2b-164">Eliminazione dei record</span><span class="sxs-lookup"><span data-stu-id="1be2b-164">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="1be2b-165">L'implementazione per la prova dello smaltimento per i record in SharePoint e OneDrive è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1be2b-165">The rollout for proof of disposal for records in SharePoint and OneDrive is complete.</span></span>
>
> <span data-ttu-id="1be2b-166">La prova dello smaltimento dei record in Exchange è stata appena avviata. Al termine di questa implementazione, verrà aggiornata la nota.</span><span class="sxs-lookup"><span data-stu-id="1be2b-166">Proof of disposal for records in Exchange has just started to roll out. When this rollout is complete, we will update this note.</span></span>

<span data-ttu-id="1be2b-167">Utilizzare la scheda **disposizione** della pagina **Gestione record** per identificare i record che sono stati eliminati, automaticamente o dopo una revisione della disposizione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-167">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="1be2b-168">Questi elementi visualizzano i **record eliminati** nella colonna **tipo** .</span><span class="sxs-lookup"><span data-stu-id="1be2b-168">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="1be2b-169">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1be2b-169">For example:</span></span>

![Elementi eliminati senza una revisione di disposizione](../media/records-disposed2.png)

<span data-ttu-id="1be2b-171">Gli elementi visualizzati nella scheda **elementi eliminati** per le etichette dei record vengono conservati per un massimo di sette anni dopo che l'elemento è stato eliminato, con un limite di 1 milione elementi per ogni record per quel periodo.</span><span class="sxs-lookup"><span data-stu-id="1be2b-171">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="1be2b-172">Se si Visualizza il numero di **conteggio** vicino a questo limite di 1 milione e si ha bisogno di una prova di disposizione per i record, contattare il [supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="1be2b-172">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="1be2b-173">Questa funzionalità si basa su informazioni provenienti dal [Registro di controllo unificato](search-the-audit-log-in-security-and-compliance.md) e pertanto richiede l' [Abilitazione e la ricerca](turn-audit-log-search-on-or-off.md) in modo che gli eventi corrispondenti vengano acquisiti.</span><span class="sxs-lookup"><span data-stu-id="1be2b-173">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="1be2b-174">Filtrare ed esportare le visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="1be2b-174">Filter and export the views</span></span>

<span data-ttu-id="1be2b-175">Quando si seleziona un'etichetta di conservazione dalla pagina **disposizione** , la scheda **disposizione in sospeso** (se applicabile) e la scheda **elementi eliminati** consentono di filtrare le visualizzazioni per facilitare la ricerca di elementi in modo più semplice.</span><span class="sxs-lookup"><span data-stu-id="1be2b-175">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="1be2b-176">Per le disposizioni in sospeso, l'intervallo di tempo si basa sulla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="1be2b-176">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="1be2b-177">Per gli elementi eliminati, l'intervallo di tempo è basato sulla data di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="1be2b-177">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="1be2b-178">È possibile esportare le informazioni sugli elementi in una visualizzazione come file. csv che è possibile ordinare e gestire utilizzando Excel:</span><span class="sxs-lookup"><span data-stu-id="1be2b-178">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opzione di esportazione per la disposizione](../media/retention-export-option.png)
  
![Dati di disposizione esportati in Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


