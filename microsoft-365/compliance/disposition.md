---
title: Eliminazione del contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Monitorare e gestire lo smaltimento del contenuto, sia che si utilizzi una revisione per l'eliminazione o che il contenuto venga eliminato automaticamente in base alle impostazioni configurate.
ms.openlocfilehash: d9786b5e93801153e168784d51e37a00ee1822bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051928"
---
# <a name="disposition-of-content"></a><span data-ttu-id="27cc7-103">Eliminazione del contenuto</span><span class="sxs-lookup"><span data-stu-id="27cc7-103">Disposition of content</span></span>

><span data-ttu-id="27cc7-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="27cc7-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="27cc7-105">Utilizzare la scheda **eliminazione** dalla **gestione record** nel Centro conformità Microsoft 365 per gestire le revisioni per l’eliminazione e visualizzare i [record](records-management.md#records) eliminati automaticamente al termine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="27cc7-106">Prerequisiti per la visualizzazione delle eliminazioni di contenuto</span><span class="sxs-lookup"><span data-stu-id="27cc7-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="27cc7-107">Per gestire le revisioni per l’eliminazione e verificare che i record siano stati eliminati, è necessario avere le autorizzazioni necessarie e che il controllo sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="27cc7-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="27cc7-108">Autorizzazioni per l'eliminazione</span><span class="sxs-lookup"><span data-stu-id="27cc7-108">Permissions for disposition</span></span>

<span data-ttu-id="27cc7-109">Per accedere correttamente alla scheda **eliminazione** nel Centro conformità Microsoft 365, è necessario che gli utenti abbiano il ruolo di amministratore per la **gestione dell’eliminazione**.</span><span class="sxs-lookup"><span data-stu-id="27cc7-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="27cc7-110">Da dicembre 2020, questo ruolo è incluso nel gruppo dei ruoli di amministratore predefiniti di **Gestione record**.</span><span class="sxs-lookup"><span data-stu-id="27cc7-110">From December 2020, this role is now included in the **Records Management** default admin role group.</span></span>

> [!NOTE]
> <span data-ttu-id="27cc7-111">Per impostazione predefinita, un amministratore globale non può avere il ruolo di **gestione dell'eliminazione**.</span><span class="sxs-lookup"><span data-stu-id="27cc7-111">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="27cc7-112">Per concedere agli utenti solo le autorizzazioni necessarie per le revisioni per l'eliminazione senza concedere loro l’autorizzazione a visualizzare e configurare altre funzionalità per la conservazione e la gestione dei record, creare un gruppo di ruoli personalizzato (ad esempio, denominato "Revisori per l’eliminazione") e concedere a questo gruppo il ruolo di Gestione delle eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="27cc7-112">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>

<span data-ttu-id="27cc7-113">Inoltre, per visualizzare il contenuto degli elementi durante il processo di eliminazione, aggiungere utenti ai due gruppi di ruoli seguenti: **Visualizzatore contenuto di Esplora contenuto** e **Visualizzatore elenco di Esplora contenuto**.</span><span class="sxs-lookup"><span data-stu-id="27cc7-113">Additionally, to view the contents of items during the disposition process, add users to the following two role groups: **Content Explorer Content Viewer** and **Content Explorer List Viewer**.</span></span> <span data-ttu-id="27cc7-114">Se gli utenti non hanno le autorizzazioni di questi gruppi di ruoli, possono comunque selezionare un'azione di revisione per l'eliminazione per completare l'operazione, ma devono farlo senza poter vedere il contenuto dell'elemento nel centro conformità.</span><span class="sxs-lookup"><span data-stu-id="27cc7-114">If users don't have the permissions from these role groups, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the compliance center.</span></span>

<span data-ttu-id="27cc7-115">Per le istruzioni per configurare queste autorizzazioni, vedere [Fornire agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="27cc7-115">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="27cc7-116">Abilitazione del controllo</span><span class="sxs-lookup"><span data-stu-id="27cc7-116">Enable auditing</span></span>

<span data-ttu-id="27cc7-117">Verificare che il controllo sia abilitato almeno un giorno prima della prima azione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-117">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="27cc7-118">Per ulteriori informazioni, vedere [Eseguire una ricerca nel log di controllo nel &amp;Centro sicurezza e conformità di Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="27cc7-118">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="27cc7-119">Revisioni per l'eliminazione</span><span class="sxs-lookup"><span data-stu-id="27cc7-119">Disposition reviews</span></span>

<span data-ttu-id="27cc7-120">Quando un contenuto raggiunge la fine del periodo di conservazione, ci sono diversi motivi per cui si può scegliere di esaminare il contenuto prima di decidere se eliminarlo definitivamente ("eliminato").</span><span class="sxs-lookup"><span data-stu-id="27cc7-120">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed").</span></span> <span data-ttu-id="27cc7-121">Ad esempio, invece di eliminare il contenuto può essere necessario:</span><span class="sxs-lookup"><span data-stu-id="27cc7-121">For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="27cc7-122">Sospendere l'eliminazione del contenuto pertinente in caso di controversie legali o di un controllo.</span><span class="sxs-lookup"><span data-stu-id="27cc7-122">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>

- <span data-ttu-id="27cc7-123">Assegnare un periodo di conservazione diverso al contenuto, perché ad esempio le impostazioni di conservazione originali erano una soluzione temporanea o provvisoria.</span><span class="sxs-lookup"><span data-stu-id="27cc7-123">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="27cc7-124">Spostare il contenuto dalla posizione esistente a una posizione di archiviazione, ad esempio se il contenuto ha un valore storico o di ricerca.</span><span class="sxs-lookup"><span data-stu-id="27cc7-124">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="27cc7-125">Quando viene attivata una revisione per l'eliminazione alla fine del periodo di conservazione:</span><span class="sxs-lookup"><span data-stu-id="27cc7-125">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="27cc7-126">Gli utenti prescelti ricevono una notifica di posta elettronica che indica che hanno dei contenuti da rivedere.</span><span class="sxs-lookup"><span data-stu-id="27cc7-126">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="27cc7-127">Questi revisori possono essere singoli utenti o gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="27cc7-127">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="27cc7-128">Si noti che le notifiche vengono inviate su base settimanale.</span><span class="sxs-lookup"><span data-stu-id="27cc7-128">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="27cc7-129">I revisori accedono alla scheda **eliminazione** nel Centro conformità Microsoft 365 per rivedere il contenuto e decidere se eliminarlo definitivamente, estendere il periodo di conservazione o applicare una diversa etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-129">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="27cc7-130">Una revisione per l'eliminazione può includere il contenuto di cassette postali di Exchange, siti di SharePoint, account di OneDrive e gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27cc7-130">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="27cc7-131">Il contenuto in attesa di una revisione per l'eliminazione in tali posizioni viene eliminato solo dopo che un revisore sceglie di eliminarlo definitivamente.</span><span class="sxs-lookup"><span data-stu-id="27cc7-131">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="27cc7-132">Una cassetta postale deve contenere almeno 10 MB di dati per supportare le revisioni per l’eliminazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-132">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="27cc7-133">È possibile visualizzare una panoramica di tutte le eliminazioni in sospeso nella scheda **panoramica**. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="27cc7-133">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Eliminazioni in sospeso nella panoramica sulla gestione dei record](../media/dispositions-overview.png)

<span data-ttu-id="27cc7-135">Quando si seleziona **Visualizza tutte le eliminazioni in sospeso**, viene visualizzata la pagina **eliminazione**.</span><span class="sxs-lookup"><span data-stu-id="27cc7-135">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="27cc7-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="27cc7-136">For example:</span></span>

![Pagina eliminazioni nel Centro conformità Microsoft 365.](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="27cc7-138">Flusso di lavoro della revisione per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-138">Workflow for a disposition review</span></span>

<span data-ttu-id="27cc7-139">Il diagramma seguente illustra il flusso di lavoro di base di una revisione per l'eliminazione quando viene pubblicata una etichetta di conservazione e quindi applicata manualmente da un utente.</span><span class="sxs-lookup"><span data-stu-id="27cc7-139">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="27cc7-140">In alternativa, un'etichetta di conservazione configurata per una revisione per l’eliminazione può essere applicata automaticamente al contenuto.</span><span class="sxs-lookup"><span data-stu-id="27cc7-140">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Grafico che mostra il flusso di funzionamento dell’eliminazione](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="27cc7-142">L'attivazione di una revisione per l'eliminazione alla fine del periodo di conservazione è un'opzione di configurazione disponibile solo con un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-142">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="27cc7-143">Questa opzione non è disponibile per i criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-143">This option is not available for a retention policy.</span></span> <span data-ttu-id="27cc7-144">Per saperne di più su queste due soluzioni di conservazione, vedere [Informazioni sui criteri e le etichette di conservazione](retention.md).</span><span class="sxs-lookup"><span data-stu-id="27cc7-144">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="27cc7-145">Dalla pagina **Definisci le impostazioni di conservazione** per un'etichetta di conservazione:</span><span class="sxs-lookup"><span data-stu-id="27cc7-145">From the **Define retention settings** page for a retention label:</span></span>

![Impostazioni di conservazione per l'etichetta](../media/disposition-review-option.png)
 
<span data-ttu-id="27cc7-147">Dopo aver selezionato l'opzione **Attiva una revisione per l'eliminazione**, si specificano i revisori per l’eliminazione nella pagina successiva della procedura guidata:</span><span class="sxs-lookup"><span data-stu-id="27cc7-147">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![Specifica dei revisori per l’eliminazione](../media/disposition-reviewers.png)

<span data-ttu-id="27cc7-149">Per i revisori, specificare un utente o un gruppo di sicurezza abilitato alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="27cc7-149">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="27cc7-150">I gruppi di Microsoft 365 (in precedenza[gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) non sono supportati per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-150">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="27cc7-151">Visualizzazione ed eliminazione del contenuto</span><span class="sxs-lookup"><span data-stu-id="27cc7-151">Viewing and disposing of content</span></span>

<span data-ttu-id="27cc7-152">Quando riceve una notifica tramite posta elettronica che informa che il contenuto è pronto per la revisione, il revisore può accedere alla scheda **eliminazione** dalla **gestione dei record** nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27cc7-152">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="27cc7-153">I revisori possono visualizzare il numero di elementi per ogni etichetta di conservazione in attesa di eliminazione e quindi selezionare un'etichetta di conservazione per visualizzare tutto il contenuto sotto tale etichetta.</span><span class="sxs-lookup"><span data-stu-id="27cc7-153">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="27cc7-154">Dopo aver selezionato un'etichetta di conservazione, sono visualizzate tutte le eliminazioni in sospeso relative a tale etichetta dalla scheda **eliminazione in sospeso**. Selezionare uno o più elementi, poi scegliere un’azione relativamente ad essi e inserire un commento di motivazione:</span><span class="sxs-lookup"><span data-stu-id="27cc7-154">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opzioni di eliminazione](../media/retention-disposition-options.png)

<span data-ttu-id="27cc7-156">Come si può vedere dall'immagine, le azioni supportate sono:</span><span class="sxs-lookup"><span data-stu-id="27cc7-156">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="27cc7-157">Eliminare definitivamente l'elemento.</span><span class="sxs-lookup"><span data-stu-id="27cc7-157">Permanently delete the item</span></span>
- <span data-ttu-id="27cc7-158">Estendere il periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-158">Extend the retention period</span></span>
- <span data-ttu-id="27cc7-159">Applicare un'etichetta di conservazione diversa</span><span class="sxs-lookup"><span data-stu-id="27cc7-159">Apply a different retention label</span></span>

<span data-ttu-id="27cc7-160">Se si hanno le autorizzazioni necessarie per la posizione e il contenuto, è possibile usare il collegamento nella colonna **posizione** per visualizzare i documenti nella posizione originale.</span><span class="sxs-lookup"><span data-stu-id="27cc7-160">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="27cc7-161">Durante una revisione per l'eliminazione, il contenuto non si sposta mai dalla posizione originale e non viene eliminato finché non lo decide il revisore.</span><span class="sxs-lookup"><span data-stu-id="27cc7-161">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="27cc7-162">Le notifiche di posta elettronica vengono inviate automaticamente ai revisori con cadenza settimanale.</span><span class="sxs-lookup"><span data-stu-id="27cc7-162">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="27cc7-163">Questa programmazione implica che, quando il contenuto raggiunge la fine del periodo di conservazione, possono trascorrere fino a sette giorni perché ai revisori venga notificato tramite posta elettronica che il contenuto è in attesa di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-163">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="27cc7-164">Tutte le azioni di eliminazione possono essere controllate e il testo della motivazione inserito dal revisore viene salvato e visualizzato nella colonna **commento** nella pagina **elementi eliminati**.</span><span class="sxs-lookup"><span data-stu-id="27cc7-164">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="27cc7-165">Dopo quanto tempo viene eliminato definitivamente il contenuto eliminato</span><span class="sxs-lookup"><span data-stu-id="27cc7-165">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="27cc7-166">Il contenuto in attesa di una revisione per l'eliminazione viene eliminato solo dopo che un revisore sceglie di eliminarlo definitivamente.</span><span class="sxs-lookup"><span data-stu-id="27cc7-166">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="27cc7-167">Se il revisore sceglie questa opzione, il contenuto del sito di SharePoint o dell'account di OneDrive diventa idoneo per il processo di pulizia standard descritto in [Funzionamento delle impostazioni di conservazione con i contenuti in locale](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="27cc7-167">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="27cc7-168">Eliminazione dei record</span><span class="sxs-lookup"><span data-stu-id="27cc7-168">Disposition of records</span></span>

<span data-ttu-id="27cc7-169">Usare la scheda **eliminazione** della pagina **gestione record** per identificare i record che vengono ora eliminati, automaticamente o dopo una revisione dell’eliminazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-169">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="27cc7-170">Questi elementi visualizzano i **record eliminati** nella colonna **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="27cc7-170">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="27cc7-171">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="27cc7-171">For example:</span></span>

![Elementi eliminati senza revisione per l'eliminazione](../media/records-disposed2.png)

<span data-ttu-id="27cc7-173">Gli elementi visualizzati nella scheda **elementi eliminati** delle etichette dei record vengono conservati per un massimo di sette anni dalla data di eliminazione dell'elemento, con un limite di 1 milione di elementi per ogni record per quel periodo.</span><span class="sxs-lookup"><span data-stu-id="27cc7-173">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="27cc7-174">Se la cifra di **Conteggio** visualizzata si avvicina al limite di 1 milione e occorre prova di eliminazione dei record, contattare il [supporto tecnico Microsoft](/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="27cc7-174">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="27cc7-175">Questa funzionalità si basa sulle informazioni provenienti dal [Log di controllo unificato](search-the-audit-log-in-security-and-compliance.md) e, di conseguenza, è necessario che il controllo sia [abilitato e con ricerca consentita](turn-audit-log-search-on-or-off.md) in modo da acquisire gli eventi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="27cc7-175">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="27cc7-176">Per il controllo, cercare **File eliminato contrassegnato come record** nella categoria **Attività su file e pagine**.</span><span class="sxs-lookup"><span data-stu-id="27cc7-176">For auditing, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="27cc7-177">Questo evento di controllo è applicabile ai documenti e ai messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="27cc7-177">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="27cc7-178">Filtrare ed esportare le visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="27cc7-178">Filter and export the views</span></span>

<span data-ttu-id="27cc7-179">Se si seleziona un'etichetta di conservazione dalla pagina **eliminazione**, la scheda **eliminazione in sospeso**(se applicabile) e la scheda **elementi eliminati** consentono di filtrare le visualizzazioni per trovare più facilmente gli elementi.</span><span class="sxs-lookup"><span data-stu-id="27cc7-179">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="27cc7-180">Per le eliminazioni in sospeso, l'intervallo di tempo si basa sulla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="27cc7-180">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="27cc7-181">Per gli elementi eliminati, l'intervallo di tempo si basa sulla data di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="27cc7-181">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="27cc7-182">Per entrambe le visualizzazioni è possibile esportare le informazioni sugli elementi come file .csv, che si può poi ordinare e gestire con Excel:</span><span class="sxs-lookup"><span data-stu-id="27cc7-182">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opzione Esporta per l’eliminazione](../media/retention-export-option.png)