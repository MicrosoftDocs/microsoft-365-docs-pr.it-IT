---
title: Avviare la conservazione al verificarsi di un evento
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: In genere, nell’ambito di una soluzione di gestione dei record, è possibile configurare un’etichetta di conservazione per avviare il periodo di conservazione in base a un evento identificato.
ms.openlocfilehash: a3760feafa5307c8c71e83dcc72b988258b94a2a
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391508"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="f2802-103">Avviare la conservazione al verificarsi di un evento</span><span class="sxs-lookup"><span data-stu-id="f2802-103">Start retention when an event occurs</span></span>

><span data-ttu-id="f2802-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="f2802-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f2802-p101">Quando si conserva il contenuto, il periodo di conservazione spesso si basa sulla data di creazione del contenuto stesso. Ad esempio, è possibile conservare i documenti per sette anni dalla creazione e quindi eliminarli. Quando si configurano [etichette di conservazione](labels.md), invece, il periodo di conservazione può essere basato anche sul momento in cui si verifica un determinato tipo di evento. L'evento attiva l'inizio del periodo di conservazione e a tutto il contenuto a cui è applicata un'etichetta di conservazione per quel tipo di evento vengono applicate le azioni di conservazione dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f2802-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="f2802-109">Esempi per l'uso della conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="f2802-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="f2802-110">**Dipendenti che lasciano l'organizzazione** Si supponga che i record dei dipendenti debbano essere conservati per 10 anni dal momento in cui lasciano l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="f2802-111">Trascorsi 10 anni, tutti i documenti relativi all'assunzione, alle prestazioni e alla cessazione del rapporto lavorativo di quel dipendente devono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="f2802-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="f2802-112">L'evento che attiva il periodo di conservazione di 10 anni è l'uscita del dipendente dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="f2802-113">**Scadenza del contratto** Si supponga che tutti i record relativi ai contratti debbano essere conservati per cinque anni dalla data di scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="f2802-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="f2802-114">L'evento che attiva il periodo di conservazione di cinque anni è la scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="f2802-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="f2802-p104">**Durata del prodotto** L'organizzazione potrebbe avere requisiti di conservazione relativi all'ultima data di produzione dei prodotti per i contenuti, come le specifiche tecniche. In questo caso, l'ultima data di produzione è l'evento che attiva il periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="f2802-p105">La conservazione basata su eventi viene generalmente utilizzata come parte di un processo di gestione dei record. Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="f2802-p105">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="f2802-119">Anche le etichette basate su eventi classificano il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="f2802-119">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="f2802-120">Per altre informazioni, vedere [Informazioni sui record](records.md).</span><span class="sxs-lookup"><span data-stu-id="f2802-120">For more information, see [Learn about records](records.md).</span></span>

- <span data-ttu-id="f2802-121">Un documento che è stato dichiarato come record, ma il cui trigger di evento non si è ancora verificato, viene conservato a tempo indeterminato (i record non possono essere eliminati definitivamente) finché un evento non attiva il periodo di conservazione di quel documento.</span><span class="sxs-lookup"><span data-stu-id="f2802-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="f2802-122">Le etichette di conservazione basate su eventi di solito attivano una revisione per l'eliminazione alla fine del periodo di conservazione, in modo che un responsabile dei record possa rivedere ed eliminare manualmente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="f2802-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="f2802-123">Per altre informazioni, vedere [Eliminazione dei contenuti](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="f2802-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="f2802-124">Un’etichetta basata su un evento ha le stesse funzionalità di qualsiasi etichetta in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2802-124">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="f2802-125">Per altre informazioni, vedere [Informazioni sui criteri e sulle etichette di conservazione](retention.md).</span><span class="sxs-lookup"><span data-stu-id="f2802-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="f2802-126">Informazioni sulla relazione tra tipi di eventi, etichette, eventi e ID delle risorse</span><span class="sxs-lookup"><span data-stu-id="f2802-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="f2802-127">Per usare correttamente la conservazione basata su eventi, è importante comprendere la relazione tra tipi di eventi, etichette di conservazione, eventi e ID delle risorse come illustrato nei diagrammi e nella spiegazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2802-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagramma del tipo di evento, etichette, eventi e ID delle risorse](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagramma del tipo di evento, etichette, eventi e ID delle risorse](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="f2802-130">Vengono create etichette di conservazione per diversi tipi di contenuto, che vengono poi associate a un tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="f2802-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="f2802-131">Ad esempio, le etichette di conservazione per tipi diversi di file e record di prodotti sono associate a un tipo di evento denominato Durata del prodotto, in quanto tali record devono essere conservati per 10 anni dal momento in cui il prodotto raggiunge la fine del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="f2802-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="f2802-132">Gli utenti (in genere i responsabili dei record) applicano queste etichette di conservazione al contenuto e (per i documenti di SharePoint e OneDrive) immettono un ID risorsa per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="f2802-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="f2802-133">In questo esempio l'ID risorsa è un codice o nome del prodotto usato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="f2802-134">In questo modo, ai record di ogni prodotto viene assegnata un'etichetta di conservazione e ogni record ha una proprietà che contiene un ID risorsa.</span><span class="sxs-lookup"><span data-stu-id="f2802-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="f2802-135">Il diagramma rappresenta **tutto il contenuto** per tutti i record dei prodotti in un'organizzazione e ogni elemento contiene l'ID risorsa del prodotto a cui appartiene il record.</span><span class="sxs-lookup"><span data-stu-id="f2802-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="f2802-p111">Durata prodotto è il tipo di evento. Un prodotto specifico che raggiunge la fine del ciclo di vita è un evento. Quando si verifica un evento di questo tipo, in questo caso quando un prodotto raggiunge la fine del ciclo di vita, si crea un evento che specifica:</span><span class="sxs-lookup"><span data-stu-id="f2802-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="f2802-138">Un ID risorsa (per i documenti di SharePoint e OneDrive)</span><span class="sxs-lookup"><span data-stu-id="f2802-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="f2802-p112">Parole chiave (per gli articoli di Exchange). In questo esempio, l'organizzazione utilizza un codice prodotto nei messaggi contenenti i record del prodotto, pertanto la parola chiave per gli elementi di Exchange è uguale all'ID risorsa per i documenti di SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f2802-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="f2802-p113">La data in cui si è verificato l'evento. Questa data viene utilizzata come inizio del periodo di conservazione. Questa data può essere la data attuale, una futura o una passata.</span><span class="sxs-lookup"><span data-stu-id="f2802-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="f2802-144">Dopo aver creato un evento, la data dell'evento viene sincronizzata con tutto il contenuto che ha un'etichetta di conservazione di quel tipo di evento e che contiene la parola chiave o l'ID risorsa specificato.</span><span class="sxs-lookup"><span data-stu-id="f2802-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="f2802-145">Come per qualsiasi etichetta di conservazione, la sincronizzazione può richiedere fino a sette giorni.</span><span class="sxs-lookup"><span data-stu-id="f2802-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="f2802-146">Come mostrato nel diagramma precedente, questo evento ha attivato il periodo di conservazione di tutti gli elementi cerchiati in rosso.</span><span class="sxs-lookup"><span data-stu-id="f2802-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="f2802-147">In altre parole, quando il prodotto raggiunge la fine del ciclo di vita, questo evento attiva il periodo di conservazione per i record del prodotto.</span><span class="sxs-lookup"><span data-stu-id="f2802-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="f2802-148">È importante tenere presente che se non si specificano parole chiave o un ID risorsa per un evento, l’evento attiverà il periodo di conservazione di **tutti i contenuti** con un'etichetta relativa a quel tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="f2802-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="f2802-149">Nel diagramma precedente, ad esempio, verrebbe avviata la conservazione di tutto il contenuto.</span><span class="sxs-lookup"><span data-stu-id="f2802-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="f2802-150">Questo potrebbe non essere il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="f2802-150">This might not be what you intend.</span></span> 

<span data-ttu-id="f2802-151">Tenere infine presente che ogni etichetta di conservazione ha le proprie impostazioni di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="f2802-152">In questo esempio, queste specificano tutte 10 anni ma un evento può attivare etichette con diversi periodi di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="f2802-153">Come configurare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="f2802-153">How to set up event-driven retention</span></span>

<span data-ttu-id="f2802-154">Flusso di lavoro di alto livello per la conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="f2802-154">High-level workflow for event-driven retention:</span></span>
  
![Diagramma del flusso di lavoro per la configurazione di conservazione basata su eventi](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="f2802-156">Vedere [Gestire il ciclo di vita dei documenti di SharePoint con le etichette di conservazione](auto-apply-retention-labels-scenario.md) per uno scenario dettagliato sull'uso delle proprietà gestite in SharePoint per applicare automaticamente etichette di conservazione e implementare la conservazione basata su eventi.</span><span class="sxs-lookup"><span data-stu-id="f2802-156">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="f2802-157">Passaggio 1: creare un'etichetta il cui periodo di conservazione sia basato su un evento</span><span class="sxs-lookup"><span data-stu-id="f2802-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="f2802-158">Per creare e configurare l'etichetta di conservazione, usare le istruzioni in [Creare e configurare etichette di conservazione](create-retention-labels.md#create-and-configure-retention-labels) e, quando si attiva la conservazione, scegliere l'opzione per conservare o eliminare il contenuto in base a un evento.</span><span class="sxs-lookup"><span data-stu-id="f2802-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="f2802-159">Questo significa che le impostazioni di conservazione non verranno attivate fino al passaggio 5, quando si creerà un evento nella pagina **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="f2802-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="f2802-160">La conservazione basata su eventi viene in genere usata per il contenuto classificato come record, quindi questo è il momento giusto per verificare se occorre selezionare anche l'opzione per contrassegnare il contenuto come record.</span><span class="sxs-lookup"><span data-stu-id="f2802-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="f2802-161">La conservazione basata su eventi richiede impostazioni di conservazione che:</span><span class="sxs-lookup"><span data-stu-id="f2802-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="f2802-162">Conservino il contenuto.</span><span class="sxs-lookup"><span data-stu-id="f2802-162">Retain the content.</span></span>
    
- <span data-ttu-id="f2802-163">Eliminino il contenuto automaticamente o attivino una revisione per l'eliminazione alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![Opzione per basare un'etichetta su un evento](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="f2802-165">Passaggio 2: scegliere un tipo di evento per l'etichetta</span><span class="sxs-lookup"><span data-stu-id="f2802-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="f2802-166">Nelle impostazioni dell’etichetta, dopo avere selezionato l’opzione per basare l’etichetta su **un evento**, sarà presente l’opzione **Scegliere un tipo di evento**.</span><span class="sxs-lookup"><span data-stu-id="f2802-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="f2802-167">Un tipo di evento è semplicemente una descrizione generale di un evento a cui si vuole associare un’etichetta.</span><span class="sxs-lookup"><span data-stu-id="f2802-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="f2802-168">Ad esempio, se si crea un tipo di evento denominato Durata del prodotto, verranno create le etichette di conservazione basate su eventi con i nomi che descrivono i tipi di contenuti a cui si desidera applicare le etichette, ad esempio "File di sviluppo prodotto" o "Record decisione prodotto aziendale".</span><span class="sxs-lookup"><span data-stu-id="f2802-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="f2802-169">Selezionare uno dei tipi di evento predefiniti oppure crearne uno personalizzato e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="f2802-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="f2802-170">Dopo aver scelto un tipo di evento e salvato l'etichetta di conservazione, il tipo di evento non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="f2802-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![Opzioni per creare o scegliere un tipo di evento](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="f2802-172">Passaggio 3: pubblicare o applicare automaticamente le etichette di conservazione basate su eventi</span><span class="sxs-lookup"><span data-stu-id="f2802-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="f2802-173">Come per qualsiasi etichetta di conservazione, è necessario pubblicare o applicare automaticamente un'etichetta basata su eventi perché venga applicata manualmente o automaticamente al contenuto:</span><span class="sxs-lookup"><span data-stu-id="f2802-173">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="f2802-174">Creare etichette di conservazione e applicarle nelle app</span><span class="sxs-lookup"><span data-stu-id="f2802-174">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="f2802-175">Applicare automaticamente un'etichetta di conservazione al contenuto</span><span class="sxs-lookup"><span data-stu-id="f2802-175">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


> [!NOTE]
> <span data-ttu-id="f2802-176">Se si seleziona un'etichetta di conservazione basata su eventi dalla scheda **Gestione record** > **Piano file** o dalla scheda **Governance dei dati** > **Etichette**, il pulsante **Applica automaticamente un'etichetta** non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="f2802-176">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="f2802-177">Anziché questo pulsante, usare l'opzione **Applica automaticamente un'etichetta** sopra l'elenco di etichette o criteri da una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2802-177">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="f2802-178">Scheda **Gestione record** > **Criteri etichetta**</span><span class="sxs-lookup"><span data-stu-id="f2802-178">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="f2802-179">Scheda **Governance dati** > **Etichette** o scheda **Criteri etichette**</span><span class="sxs-lookup"><span data-stu-id="f2802-179">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![Opzioni per pubblicare o applicare automaticamente un'etichetta di conservazione](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="f2802-181">Passaggio 4: immettere un ID risorsa</span><span class="sxs-lookup"><span data-stu-id="f2802-181">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="f2802-182">Dopo avere applicato al contenuto un'etichetta basata su eventi, è possibile immettere un ID risorsa per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="f2802-182">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="f2802-183">Ad esempio, l'organizzazione può usare:</span><span class="sxs-lookup"><span data-stu-id="f2802-183">For example, your organization might use:</span></span>
  
- <span data-ttu-id="f2802-184">Codici prodotto da utilizzare per conservare i contenuti solo per un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="f2802-184">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="f2802-185">Codici prodotto da utilizzare per conservare i contenuti solo per un progetto specifico.</span><span class="sxs-lookup"><span data-stu-id="f2802-185">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="f2802-186">ID dipendente da utilizzare per conservare i contenuti solo per una persona specifica.</span><span class="sxs-lookup"><span data-stu-id="f2802-186">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="f2802-187">L'ID risorsa è semplicemente un'ulteriore proprietà di un documento disponibile in SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f2802-187">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="f2802-188">L’organizzazione potrebbe usare già altre proprietà del documento e altri ID per classificare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="f2802-188">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="f2802-189">In questo caso, è possibile usare anche quelle proprietà e quei valori quando si crea l'evento (vedere il Passaggio 6 di seguito).</span><span class="sxs-lookup"><span data-stu-id="f2802-189">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="f2802-190">L'aspetto importante è che si deve usare una certa combinazione *proprietà:valore* nelle proprietà del documento per associare l'elemento a un tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="f2802-190">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Casella di testo per immettere un ID risorsa](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="f2802-192">Passaggio 5: creare un evento</span><span class="sxs-lookup"><span data-stu-id="f2802-192">Step 5: Create an event</span></span>

<span data-ttu-id="f2802-193">Quando si verifica un'istanza particolare di quel tipo di evento, ad esempio quando un prodotto raggiunge la fine del ciclo di vita, accedere alla pagina **Gestione record** > **Eventi** nel Centro conformità di Microsoft 365 e creare un evento.</span><span class="sxs-lookup"><span data-stu-id="f2802-193">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="f2802-194">Per attivare un evento occorre crearlo.</span><span class="sxs-lookup"><span data-stu-id="f2802-194">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="f2802-195">Passaggio 6: scegliere lo stesso tipo di evento utilizzato per l'etichetta nel Passaggio 2</span><span class="sxs-lookup"><span data-stu-id="f2802-195">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="f2802-196">Quando si crea l'evento, scegliere lo stesso tipo di evento usato per l'etichetta di conservazione nel passaggio 2, ad esempio Durata del prodotto.</span><span class="sxs-lookup"><span data-stu-id="f2802-196">When you create the event, choose the same event type used by the retention label in step 2—for example, Product Lifetime.</span></span> <span data-ttu-id="f2802-197">Il periodo di conservazione verrà attivato solo per il contenuto a cui sono applicate le etichette di conservazione di quel tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="f2802-197">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![Opzione in Impostazioni evento per scegliere un tipo di evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="f2802-199">Passaggio 7: immettere parole chiave o un ID risorsa</span><span class="sxs-lookup"><span data-stu-id="f2802-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="f2802-200">A questo punto si limiterà l’ambito del contenuto, specificando gli ID risorsa per il contenuto di SharePoint e OneDrive o le parole chiave per il contenuto di Exchange.</span><span class="sxs-lookup"><span data-stu-id="f2802-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="f2802-201">Per gli ID risorsa, la conservazione verrà applicata solo al contenuto con la coppia *proprietà:valore* specificata.</span><span class="sxs-lookup"><span data-stu-id="f2802-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="f2802-202">Se non si immette un ID risorsa, a tutti i contenuti con etichette di quel tipo di evento verrà applicata la stessa data di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="f2802-203">Ad esempio: se si usa la proprietà ID risorsa, immettere `ComplianceAssetID:<value>` nella casella relativa agli ID risorsa mostrati sotto.</span><span class="sxs-lookup"><span data-stu-id="f2802-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="f2802-204">È possibile che l'organizzazione abbia applicato altre proprietà e altri ID ai documenti correlati al tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="f2802-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="f2802-205">Ad esempio, se è necessario individuare i record di un prodotto specifico, l'ID può essere una combinazione della proprietà personalizzata ProductID e del valore "XYZ"</span><span class="sxs-lookup"><span data-stu-id="f2802-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="f2802-206">In questo caso, si immetterà `ProductID:XYZ` nella casella per gli ID risorsa mostrata nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="f2802-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="f2802-207">Per gli elementi di Exchange includere parole chiave.</span><span class="sxs-lookup"><span data-stu-id="f2802-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="f2802-208">È possibile usare una query con gli operatori di ricerca come AND, OR e NOT.</span><span class="sxs-lookup"><span data-stu-id="f2802-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="f2802-209">Per altre informazioni, vedere [Query con parola chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="f2802-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="f2802-210">Infine, scegliere la data in cui si è verificato l'evento; questa data viene utilizzata come inizio del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="f2802-211">Dopo aver creato un evento, la data dell'evento viene sincronizzata con tutto i contenuti che hanno un'etichetta di conservazione per il tipo di evento, l'ID risorsa e le parole chiave.</span><span class="sxs-lookup"><span data-stu-id="f2802-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="f2802-212">Come per qualsiasi etichetta di conservazione, la sincronizzazione può richiedere fino a sette giorni.</span><span class="sxs-lookup"><span data-stu-id="f2802-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Pagina Impostazioni evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="f2802-214">Dopo la creazione di un evento, le impostazioni di conservazione vengono applicate al contenuto già etichettato e indicizzato.</span><span class="sxs-lookup"><span data-stu-id="f2802-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="f2802-215">Se l'etichetta di conservazione viene aggiunta al nuovo contenuto dopo la creazione dell'evento, è necessario creare un nuovo evento con gli stessi dettagli.</span><span class="sxs-lookup"><span data-stu-id="f2802-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="f2802-216">L'eliminazione di un evento non annulla le impostazioni di conservazione attualmente in vigore per il contenuto già etichettato.</span><span class="sxs-lookup"><span data-stu-id="f2802-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="f2802-217">Per fare questo, creare un nuovo evento con gli stessi dettagli, ma lasciare vuota la data.</span><span class="sxs-lookup"><span data-stu-id="f2802-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="f2802-218">Usare Ricerca contenuto per trovare tutto il contenuto con un'etichetta o un ID risorsa specifico</span><span class="sxs-lookup"><span data-stu-id="f2802-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="f2802-219">Dopo che le etichette di conservazione sono state assegnate al contenuto, è possibile usare la funzionalità di ricerca di contenuto per trovare tutti i contenuti classificati con un'etichetta di conservazione specifica o che contengono un ID risorsa specifico:</span><span class="sxs-lookup"><span data-stu-id="f2802-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="f2802-220">Per trovare tutto il contenuto con un'etichetta di conservazione specifica, selezionare la condizione **Etichetta di conservazione**, quindi immettere il nome completo dell'etichetta o parte di esso e usare un carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="f2802-220">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="f2802-221">Per trovare tutto il contenuto con un ID risorsa specifico, inserire la proprietà **ComplianceAssetID** e un valore, usando il formato `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="f2802-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="f2802-222">Per altre informazioni, vedere [Query con parola chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="f2802-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="f2802-223">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f2802-223">Permissions</span></span>

<span data-ttu-id="f2802-p129">Per accedere alla pagina **Eventi**, i revisori devono essere membri di un gruppo di ruoli con il ruolo **Gestione eliminazione** e **Solo visualizzazione log di controllo**. Si consiglia di creare un nuovo gruppo di ruoli denominato Revisori eliminazione, aggiungendo questi due ruoli, e quindi membri, a quel gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="f2802-p129">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="f2802-226">Per ulteriori informazioni, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f2802-226">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="f2802-227">Automatizzare gli eventi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2802-227">Automate events by using PowerShell</span></span>

<span data-ttu-id="f2802-228">È possibile usare uno script di PowerShell per automatizzare la conservazione basata su eventi dalle applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="f2802-228">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="f2802-229">Cmdlet di PowerShell disponibili per la conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="f2802-229">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="f2802-230">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f2802-230">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="f2802-231">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f2802-231">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="f2802-232">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f2802-232">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="f2802-233">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f2802-233">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="f2802-234">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="f2802-234">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="f2802-235">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="f2802-235">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="f2802-236">Automatizzare gli eventi con un'API REST</span><span class="sxs-lookup"><span data-stu-id="f2802-236">Automate events by using a REST API</span></span>

<span data-ttu-id="f2802-237">È possibile usare un'API REST per creare automaticamente gli eventi che attivano l'inizio del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-237">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="f2802-238">Un'API REST è un endpoint di servizio che supporta set di operazioni HTTP (metodi), che forniscono l'accesso alle risorse del servizio per la creazione, il recupero, l'aggiornamento e l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-238">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="f2802-239">Per altre informazioni, vedere [Componenti di una richiesta/risposta dell'API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="f2802-239">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="f2802-240">Con l'API REST di Microsoft 365 è possibile creare e recuperare gli eventi usando i metodi POST e GET.</span><span class="sxs-lookup"><span data-stu-id="f2802-240">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="f2802-241">Sono disponibili due opzioni per usare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="f2802-241">There are two options for using the REST API:</span></span>

- <span data-ttu-id="f2802-242">**Microsoft Power Automate o delle applicazioni simili** per attivare automaticamente l'occorrenza di un evento.</span><span class="sxs-lookup"><span data-stu-id="f2802-242">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="f2802-243">Microsoft Power Automate è un agente di orchestrazione per la connessione ad altri sistemi, quindi non è necessario scrivere una soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f2802-243">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="f2802-244">Per altre informazioni, vedere il [sito Web di Power Automate](https://flow.microsoft.com/it-IT/).</span><span class="sxs-lookup"><span data-stu-id="f2802-244">For more information, see the [Power Automate website](https://flow.microsoft.com/it-IT/).</span></span>

- <span data-ttu-id="f2802-245">**PowerShell o un client HTTP per richiamare l'API REST** per creare eventi con PowerShell (versione 6 o successiva) nell'ambito di una soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f2802-245">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="f2802-246">Prima di usare l'API REST, come amministratore globale, confermare l'URL da usare per chiamare l'evento di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-246">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="f2802-247">A questo scopo, eseguire una chiamata all'evento di conservazione GET usando l'URL dell'API REST:</span><span class="sxs-lookup"><span data-stu-id="f2802-247">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="f2802-248">Controllare il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="f2802-248">Check the response code.</span></span> <span data-ttu-id="f2802-249">Se è 302, ottenere l'URL reindirizzato dalla proprietà Location dell'intestazione della risposta e usare tale URL anziché `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` nelle istruzioni che seguono.</span><span class="sxs-lookup"><span data-stu-id="f2802-249">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="f2802-250">Gli eventi che vengono creati automaticamente possono essere confermati visualizzandoli in Centro conformità Microsoft 365 > **Gestione record** >  **eventi**.</span><span class="sxs-lookup"><span data-stu-id="f2802-250">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="f2802-251">Usare Microsoft Power Automate per creare l'evento</span><span class="sxs-lookup"><span data-stu-id="f2802-251">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="f2802-252">Creare un flusso che crea un evento usando l'API REST di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f2802-252">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Usare Flow per creare un evento](../media/automate-event-driven-retention-flow-1.png)

![Usare Flow per chiamare l'API REST](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="f2802-255">Creare un evento</span><span class="sxs-lookup"><span data-stu-id="f2802-255">Create an event</span></span>

<span data-ttu-id="f2802-256">Codice di esempio per chiamare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="f2802-256">Sample code to call the REST API:</span></span>

- <span data-ttu-id="f2802-257">**Metodo**: POST</span><span class="sxs-lookup"><span data-stu-id="f2802-257">**Method**: POST</span></span>
- <span data-ttu-id="f2802-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="f2802-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="f2802-259">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="f2802-259">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="f2802-260">**Corpo**:</span><span class="sxs-lookup"><span data-stu-id="f2802-260">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="f2802-261">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="f2802-261">**Authentication**: Basic</span></span>
- <span data-ttu-id="f2802-262">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="f2802-262">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="f2802-263">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="f2802-263">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="f2802-264">Parametri disponibili</span><span class="sxs-lookup"><span data-stu-id="f2802-264">Available parameters</span></span>


|<span data-ttu-id="f2802-265">Parametri</span><span class="sxs-lookup"><span data-stu-id="f2802-265">Parameters</span></span>|<span data-ttu-id="f2802-266">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2802-266">Description</span></span>|<span data-ttu-id="f2802-267">Note</span><span class="sxs-lookup"><span data-stu-id="f2802-267">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="f2802-268"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="f2802-268"><d:Name></d:Name></span></span>|<span data-ttu-id="f2802-269">Immettere un nome univoco per l'evento,</span><span class="sxs-lookup"><span data-stu-id="f2802-269">Provide a unique name for the event,</span></span>|<span data-ttu-id="f2802-270">Non può contenere spazi iniziali o finali o i caratteri seguenti: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="f2802-270">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="f2802-271">, : ;</span><span class="sxs-lookup"><span data-stu-id="f2802-271">, : ;</span></span>|
|<span data-ttu-id="f2802-272"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="f2802-272"><d:EventType></d:EventType></span></span>|<span data-ttu-id="f2802-273">Immettere il nome del tipo di evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="f2802-273">Enter event type name (or Guid),</span></span>|<span data-ttu-id="f2802-274">Esempio: "Licenziamento dipendente".</span><span class="sxs-lookup"><span data-stu-id="f2802-274">Example: "Employee termination".</span></span> <span data-ttu-id="f2802-275">Il tipo di evento deve essere associato a un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f2802-275">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="f2802-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="f2802-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="f2802-277">Immettere "ComplianceAssetId:" + ID dipendente</span><span class="sxs-lookup"><span data-stu-id="f2802-277">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="f2802-278">Esempio: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="f2802-278">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="f2802-279"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="f2802-279"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="f2802-280">Data e ora evento</span><span class="sxs-lookup"><span data-stu-id="f2802-280">Event Date and Time</span></span>|<span data-ttu-id="f2802-281">Formato: aaaa-MM-ggTHH:mm:ssZ, esempio: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="f2802-281">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="f2802-282">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="f2802-282">Response codes</span></span>

| <span data-ttu-id="f2802-283">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="f2802-283">Response Code</span></span> | <span data-ttu-id="f2802-284">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2802-284">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="f2802-285">302</span><span class="sxs-lookup"><span data-stu-id="f2802-285">302</span></span>               | <span data-ttu-id="f2802-286">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="f2802-286">Redirect</span></span>              |
| <span data-ttu-id="f2802-287">201</span><span class="sxs-lookup"><span data-stu-id="f2802-287">201</span></span>               | <span data-ttu-id="f2802-288">Creato</span><span class="sxs-lookup"><span data-stu-id="f2802-288">Created</span></span>               |
| <span data-ttu-id="f2802-289">403</span><span class="sxs-lookup"><span data-stu-id="f2802-289">403</span></span>               | <span data-ttu-id="f2802-290">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2802-290">Authorization Failed</span></span>  |
| <span data-ttu-id="f2802-291">401</span><span class="sxs-lookup"><span data-stu-id="f2802-291">401</span></span>               | <span data-ttu-id="f2802-292">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2802-292">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="f2802-293">Ricevere gli eventi in base a un intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="f2802-293">Get events based on a time range</span></span>

- <span data-ttu-id="f2802-294">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="f2802-294">**Method**: GET</span></span>

- <span data-ttu-id="f2802-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="f2802-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="f2802-296">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="f2802-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="f2802-297">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="f2802-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="f2802-298">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="f2802-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="f2802-299">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="f2802-299">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="f2802-300">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="f2802-300">Response codes</span></span>

| <span data-ttu-id="f2802-301">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="f2802-301">Response Code</span></span> | <span data-ttu-id="f2802-302">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2802-302">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="f2802-303">200</span><span class="sxs-lookup"><span data-stu-id="f2802-303">200</span></span>               | <span data-ttu-id="f2802-304">OK, un elenco di eventi in atom+ xml</span><span class="sxs-lookup"><span data-stu-id="f2802-304">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="f2802-305">404</span><span class="sxs-lookup"><span data-stu-id="f2802-305">404</span></span>               | <span data-ttu-id="f2802-306">Non trovato</span><span class="sxs-lookup"><span data-stu-id="f2802-306">Not found</span></span>                         |
| <span data-ttu-id="f2802-307">302</span><span class="sxs-lookup"><span data-stu-id="f2802-307">302</span></span>               | <span data-ttu-id="f2802-308">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="f2802-308">Redirect</span></span>                          |
| <span data-ttu-id="f2802-309">401</span><span class="sxs-lookup"><span data-stu-id="f2802-309">401</span></span>               | <span data-ttu-id="f2802-310">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2802-310">Authorization Failed</span></span>              |
| <span data-ttu-id="f2802-311">403</span><span class="sxs-lookup"><span data-stu-id="f2802-311">403</span></span>               | <span data-ttu-id="f2802-312">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2802-312">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="f2802-313">Ottenere un evento in base all'ID</span><span class="sxs-lookup"><span data-stu-id="f2802-313">Get an event by ID</span></span>

- <span data-ttu-id="f2802-314">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="f2802-314">**Method**: GET</span></span>

- <span data-ttu-id="f2802-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="f2802-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="f2802-316">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="f2802-316">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="f2802-317">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="f2802-317">**Authentication**: Basic</span></span>

- <span data-ttu-id="f2802-318">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="f2802-318">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="f2802-319">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="f2802-319">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="f2802-320">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="f2802-320">Response codes</span></span>

| <span data-ttu-id="f2802-321">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="f2802-321">Response Code</span></span> | <span data-ttu-id="f2802-322">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2802-322">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="f2802-323">200</span><span class="sxs-lookup"><span data-stu-id="f2802-323">200</span></span>               | <span data-ttu-id="f2802-324">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="f2802-324">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="f2802-325">404</span><span class="sxs-lookup"><span data-stu-id="f2802-325">404</span></span>               | <span data-ttu-id="f2802-326">Non trovato</span><span class="sxs-lookup"><span data-stu-id="f2802-326">Not found</span></span>                                            |
| <span data-ttu-id="f2802-327">302</span><span class="sxs-lookup"><span data-stu-id="f2802-327">302</span></span>               | <span data-ttu-id="f2802-328">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="f2802-328">Redirect</span></span>                                             |
| <span data-ttu-id="f2802-329">401</span><span class="sxs-lookup"><span data-stu-id="f2802-329">401</span></span>               | <span data-ttu-id="f2802-330">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2802-330">Authorization Failed</span></span>                                 |
| <span data-ttu-id="f2802-331">403</span><span class="sxs-lookup"><span data-stu-id="f2802-331">403</span></span>               | <span data-ttu-id="f2802-332">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2802-332">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="f2802-333">Ottenere un evento in base al nome</span><span class="sxs-lookup"><span data-stu-id="f2802-333">Get an event by name</span></span>

- <span data-ttu-id="f2802-334">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="f2802-334">**Method**: GET</span></span>

- <span data-ttu-id="f2802-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="f2802-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="f2802-336">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="f2802-336">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="f2802-337">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="f2802-337">**Authentication**: Basic</span></span>

- <span data-ttu-id="f2802-338">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="f2802-338">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="f2802-339">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="f2802-339">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="f2802-340">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="f2802-340">Response codes</span></span>

| <span data-ttu-id="f2802-341">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="f2802-341">Response Code</span></span> | <span data-ttu-id="f2802-342">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2802-342">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="f2802-343">200</span><span class="sxs-lookup"><span data-stu-id="f2802-343">200</span></span>               | <span data-ttu-id="f2802-344">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="f2802-344">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="f2802-345">404</span><span class="sxs-lookup"><span data-stu-id="f2802-345">404</span></span>               | <span data-ttu-id="f2802-346">Non trovato</span><span class="sxs-lookup"><span data-stu-id="f2802-346">Not found</span></span>                                            |
| <span data-ttu-id="f2802-347">302</span><span class="sxs-lookup"><span data-stu-id="f2802-347">302</span></span>               | <span data-ttu-id="f2802-348">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="f2802-348">Redirect</span></span>                                             |
| <span data-ttu-id="f2802-349">401</span><span class="sxs-lookup"><span data-stu-id="f2802-349">401</span></span>               | <span data-ttu-id="f2802-350">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2802-350">Authorization Failed</span></span>                                 |
| <span data-ttu-id="f2802-351">403</span><span class="sxs-lookup"><span data-stu-id="f2802-351">403</span></span>               | <span data-ttu-id="f2802-352">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2802-352">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="f2802-353">Usare PowerShell o qualsiasi client HTTP per creare l'evento</span><span class="sxs-lookup"><span data-stu-id="f2802-353">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="f2802-354">PowerShell deve essere in versione 6 o successiva.</span><span class="sxs-lookup"><span data-stu-id="f2802-354">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="f2802-355">In una sessione di PowerShell eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f2802-355">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```

