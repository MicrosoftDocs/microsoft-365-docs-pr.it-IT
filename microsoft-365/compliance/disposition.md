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
ms.openlocfilehash: cb48d2eb6d2d06093ddea74f13269faeb4798b97
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "43950107"
---
# <a name="disposition-of-content"></a><span data-ttu-id="7e5b5-103">Disposizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="7e5b5-103">Disposition of content</span></span>

><span data-ttu-id="7e5b5-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="7e5b5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7e5b5-105">Utilizzare la scheda **disposizione** dalla **gestione dei record** nel centro conformità di Microsoft 365 per gestire le revisioni di disposizione e visualizzare i [record](records.md) eliminati automaticamente alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="7e5b5-106">Prerequisiti per la visualizzazione di disposizioni di contenuto</span><span class="sxs-lookup"><span data-stu-id="7e5b5-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="7e5b5-107">Per gestire le recensioni sulla disposizione e verificare che i record siano stati eliminati, è necessario disporre di autorizzazioni e controllo sufficienti.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="7e5b5-108">Autorizzazioni per la disposizione</span><span class="sxs-lookup"><span data-stu-id="7e5b5-108">Permissions for disposition</span></span>

<span data-ttu-id="7e5b5-109">Per accedere correttamente alla scheda **disposizione** nel centro conformità di Microsoft 365, è necessario essere membri del ruolo **gestione disposizione** e del ruolo di **controllo di sola visualizzazione** .</span><span class="sxs-lookup"><span data-stu-id="7e5b5-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, you must be members of the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="7e5b5-110">È consigliabile creare un nuovo gruppo di ruoli denominato **reviewers Disposition**e aggiungere questi due ruoli a quel gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-110">We recommend creating a new role group called **Disposition Reviewers**, and add these two roles to that role group.</span></span> 

<span data-ttu-id="7e5b5-111">Specifica del ruolo di **controllo di sola visualizzazione** :</span><span class="sxs-lookup"><span data-stu-id="7e5b5-111">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="7e5b5-112">Poiché il cmdlet sottostante utilizzato per eseguire la ricerca nel log di controllo è un cmdlet di Exchange Online, è necessario assegnare agli utenti questo ruolo utilizzando l'interfaccia di [amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), anziché utilizzando la pagina **autorizzazioni** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-112">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="7e5b5-113">Per istruzioni, vedere [gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="7e5b5-113">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="7e5b5-114">I gruppi Microsoft 365 (in[precedenza gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) non sono supportati per questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-114">Microsoft 365 Groups ([formerly Office 365 Groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="7e5b5-115">Assegnare invece le cassette postali utente, gli utenti di posta elettronica o i gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-115">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="7e5b5-116">Per istruzioni su come concedere agli utenti il ruolo di **gestione della disposizione** e creare il nuovo ruolo **revisori disposizione** , vedere [fornire agli utenti l' &amp; accesso al centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7e5b5-116">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="7e5b5-117">Abilitazione del controllo</span><span class="sxs-lookup"><span data-stu-id="7e5b5-117">Enable auditing</span></span>

<span data-ttu-id="7e5b5-118">Verificare che il controllo sia abilitato almeno un giorno prima della prima azione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-118">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="7e5b5-119">Per ulteriori informazioni, vedere [eseguire la ricerca nel log di controllo nel centro &amp; sicurezza e conformità di Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="7e5b5-119">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="7e5b5-120">Revisioni per l'eliminazione</span><span class="sxs-lookup"><span data-stu-id="7e5b5-120">Disposition reviews</span></span>

<span data-ttu-id="7e5b5-121">Quando il contenuto raggiunge la fine del periodo di conservazione, è possibile che si desideri rivedere il contenuto per decidere se può essere eliminato in modo sicuro ("Disposed").</span><span class="sxs-lookup"><span data-stu-id="7e5b5-121">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="7e5b5-122">Ad esempio, potrebbe essere necessario:</span><span class="sxs-lookup"><span data-stu-id="7e5b5-122">For example, you might need to:</span></span>
  
- <span data-ttu-id="7e5b5-123">Sospendere l'eliminazione del contenuto pertinente in caso di controversia legale o di controllo.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-123">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="7e5b5-124">Rimuovere il contenuto dall'elenco di disposizione per archiviarlo in un archivio, se il contenuto ha una ricerca o un valore cronologico.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-124">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="7e5b5-125">Assegnare un periodo di conservazione diverso al contenuto, probabilmente perché le impostazioni di conservazione originali erano una soluzione temporanea o provvisoria.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-125">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="7e5b5-126">Restituire il contenuto ai client o trasferirlo in un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-126">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="7e5b5-127">Quando viene attivata una revisione della disposizione alla fine del periodo di conservazione:</span><span class="sxs-lookup"><span data-stu-id="7e5b5-127">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="7e5b5-128">Gli utenti che scelgono ricevono una notifica tramite posta elettronica che dispongono di contenuto da esaminare.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-128">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="7e5b5-129">Questi revisori possono essere singoli utenti, gruppi di distribuzione o di sicurezza o gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-129">These reviewers can be individual users, distribution or security groups, or Office 365 groups.</span></span> <span data-ttu-id="7e5b5-130">Si noti che le notifiche vengono inviate su base settimanale.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-130">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="7e5b5-131">I revisori passano alla scheda **disposizione** del centro conformità Microsoft 365 per esaminare il contenuto e decidere se eliminarlo definitivamente, estenderne il periodo di conservazione o applicare un'etichetta di conservazione diversa.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-131">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="7e5b5-132">Una recensione di disposizione può includere il contenuto nelle cassette postali di Exchange, siti di SharePoint, account di OneDrive e gruppi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-132">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="7e5b5-133">Il contenuto in attesa di una revisione della disposizione in tali posizioni viene eliminato solo dopo che un revisore sceglie di eliminare definitivamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-133">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

<span data-ttu-id="7e5b5-134">È possibile visualizzare una panoramica di tutte le disposizioni in sospeso nella scheda **Panoramica** . Per esempio:</span><span class="sxs-lookup"><span data-stu-id="7e5b5-134">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Disposizioni in sospeso nella panoramica della gestione dei record](../media/dispositions-overview.png)

<span data-ttu-id="7e5b5-136">Quando si seleziona la **visualizzazione tutte le disposizioni in sospeso**, viene visualizzata la pagina **disposizione** .</span><span class="sxs-lookup"><span data-stu-id="7e5b5-136">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="7e5b5-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7e5b5-137">For example:</span></span>

![Pagina disposizioni in Microsoft 365 Compliance Center](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="7e5b5-139">Flusso di lavoro per una revisione della disposizione</span><span class="sxs-lookup"><span data-stu-id="7e5b5-139">Workflow for a disposition review</span></span>

<span data-ttu-id="7e5b5-140">Si tratta del flusso di lavoro di base per una revisione di disposizione quando viene pubblicata un'etichetta di conservazione e quindi applicata manualmente da un utente.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-140">This is the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="7e5b5-141">In alternativa, un'etichetta di conservazione configurata per una revisione di disposizione può essere applicata automaticamente al contenuto.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-141">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Grafico che mostra il flusso di come funziona la disposizione](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="7e5b5-143">L'attivazione di una revisione della disposizione alla fine del periodo di conservazione è un'opzione di configurazione disponibile solo con un' [etichetta di conservazione](labels.md).</span><span class="sxs-lookup"><span data-stu-id="7e5b5-143">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a [retention label](labels.md).</span></span> <span data-ttu-id="7e5b5-144">Questa opzione non è disponibile in un criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-144">This option is not available in a retention policy.</span></span>
  
![Impostazioni di conservazione per un'etichetta](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="7e5b5-146">Quando si seleziona l'opzione **notifica a queste persone quando sono disponibili elementi pronti per la revisione**, specificare un utente o un gruppo di sicurezza abilitato alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-146">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="7e5b5-147">I gruppi Microsoft 365 (in[precedenza gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) non sono supportati per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-147">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="7e5b5-148">Visualizzazione e eliminazione del contenuto</span><span class="sxs-lookup"><span data-stu-id="7e5b5-148">Viewing and disposing of content</span></span>

<span data-ttu-id="7e5b5-149">Quando un revisore riceve una notifica tramite posta elettronica che il contenuto è pronto per la revisione, accede alla scheda **disposizione** dalla **gestione dei record** nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-149">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7e5b5-150">I revisori possono vedere quanti elementi per ogni etichetta di conservazione sono in attesa di disposizione, quindi selezionare un'etichetta di conservazione per visualizzare tutto il contenuto con quell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-150">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="7e5b5-151">Dopo aver selezionato un'etichetta di conservazione, vengono visualizzate tutte le disposizioni in sospeso per tale etichetta dalla scheda **disposizione in sospeso** . Selezionare uno o più elementi in cui è possibile scegliere un'azione e immettere un commento di giustificazione:</span><span class="sxs-lookup"><span data-stu-id="7e5b5-151">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opzioni di disposizione](../media/retention-disposition-options.png)

<span data-ttu-id="7e5b5-153">Come si può vedere dall'immagine, le azioni supportate sono:</span><span class="sxs-lookup"><span data-stu-id="7e5b5-153">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="7e5b5-154">Elimina definitivamente l'elemento</span><span class="sxs-lookup"><span data-stu-id="7e5b5-154">Permanently delete the item</span></span>
- <span data-ttu-id="7e5b5-155">Estendere il periodo di conservazione</span><span class="sxs-lookup"><span data-stu-id="7e5b5-155">Extend the retention period</span></span>
- <span data-ttu-id="7e5b5-156">Applicazione di un'etichetta di conservazione diversa</span><span class="sxs-lookup"><span data-stu-id="7e5b5-156">Apply a different retention label</span></span>

<span data-ttu-id="7e5b5-157">Se si dispone delle autorizzazioni per la posizione e il contenuto, è possibile utilizzare il collegamento nella colonna **percorso** per visualizzare i documenti nel percorso originale.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-157">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="7e5b5-158">Durante una revisione della disposizione, il contenuto non si sposta mai dal percorso originale e non viene mai eliminato fino a quando il revisore non lo sceglie.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-158">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="7e5b5-159">Le notifiche di posta elettronica vengono inviate automaticamente ai revisori su base settimanale.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-159">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="7e5b5-160">Questo processo pianificato indica che quando il contenuto raggiunge la fine del periodo di conservazione, potrebbero essere necessari fino a sette giorni affinché i revisori ricevano la notifica di posta elettronica che il contenuto è in attesa di disposizione.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-160">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="7e5b5-161">È possibile controllare tutte le azioni di disposizione.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-161">All disposition actions can be audited.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="7e5b5-162">Durata dell'eliminazione definitiva del contenuto eliminato</span><span class="sxs-lookup"><span data-stu-id="7e5b5-162">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="7e5b5-163">Il contenuto in attesa di una revisione della disposizione viene eliminato solo dopo che un revisore sceglie di eliminare definitivamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-163">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="7e5b5-164">Quando il revisore sceglie questa opzione, il contenuto del sito di SharePoint o dell'account OneDrive diventa idoneo per il processo di pulizia standard descritto in [modalità di funzionamento di un criterio di conservazione con il contenuto sul posto](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="7e5b5-164">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="7e5b5-165">Disposizione dei record</span><span class="sxs-lookup"><span data-stu-id="7e5b5-165">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="7e5b5-166">La possibilità di visualizzare i record che sono stati eliminati automaticamente senza una revisione della disposizione è gradualmente distribuita ai tenant nel corso di aprile e maggio 2020, quindi potrebbe non essere possibile visualizzare immediatamente questa esperienza.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-166">The ability to see records that were automatically deleted without a disposition review is gradually rolling out to tenants during April and May 2020, so you might not see this experience immediately.</span></span>

<span data-ttu-id="7e5b5-167">Utilizzare la scheda **disposizione** della pagina **Gestione record** per identificare i record eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-167">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="7e5b5-168">Questi elementi visualizzano i **record eliminati** nella colonna **tipo** .</span><span class="sxs-lookup"><span data-stu-id="7e5b5-168">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="7e5b5-169">In confronto, i record eliminati che sono stati approvati da eliminare tramite una revisione di disposizione visualizzano una **disposizione in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-169">In comparison, disposed records that are approved to be deleted through a disposition review display **Pending Disposition**.</span></span> <span data-ttu-id="7e5b5-170">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7e5b5-170">For example:</span></span>

![Elementi eliminati senza una revisione di disposizione](../media/records-disposed2.png)

<span data-ttu-id="7e5b5-172">Gli elementi visualizzati nella scheda **elementi eliminati** per le etichette dei record vengono conservati per un massimo di 7 anni dopo l'eliminazione dell'elemento, con un limite di 1 milione elementi per ogni record per quel periodo.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-172">Items that are shown in the **Disposed Items** tab for record labels are kept for up to 7 years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="7e5b5-173">Se si Visualizza il numero di **conteggio** vicino a questo limite di 1 milione e si ha bisogno di una prova di disposizione per i record, contattare il [supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="7e5b5-173">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="7e5b5-174">Questa funzionalità si basa su informazioni provenienti dal [Registro di controllo unificato](search-the-audit-log-in-security-and-compliance.md) e pertanto richiede l' [Abilitazione e la ricerca](turn-audit-log-search-on-or-off.md) in modo che gli eventi corrispondenti vengano acquisiti.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-174">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="7e5b5-175">Filtrare ed esportare le visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="7e5b5-175">Filter and export the views</span></span>

<span data-ttu-id="7e5b5-176">Quando si seleziona un'etichetta di conservazione dalla pagina **disposizione** , la scheda **disposizione in sospeso** (se applicabile) e la scheda **elementi eliminati** consentono di filtrare le visualizzazioni per facilitare la ricerca di elementi in modo più semplice.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-176">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="7e5b5-177">Per le disposizioni in sospeso, l'intervallo di tempo si basa sulla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-177">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="7e5b5-178">Per gli elementi eliminati, l'intervallo di tempo è basato sulla data di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="7e5b5-178">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="7e5b5-179">È possibile esportare le informazioni sugli elementi in una visualizzazione come file. csv che è possibile ordinare e gestire utilizzando Excel:</span><span class="sxs-lookup"><span data-stu-id="7e5b5-179">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opzione di esportazione per la disposizione](../media/retention-export-option.png)
  
![Dati di disposizione esportati in Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


