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
ms.openlocfilehash: 83f1be417b706fdb66b1df71ba351ce16d5ad485
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226624"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="44007-103">Avviare la conservazione al verificarsi di un evento</span><span class="sxs-lookup"><span data-stu-id="44007-103">Start retention when an event occurs</span></span>

><span data-ttu-id="44007-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="44007-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="44007-p101">Quando si conserva il contenuto, il periodo di conservazione spesso si basa sulla data di creazione del contenuto stesso. Ad esempio, è possibile conservare i documenti per sette anni dalla creazione e quindi eliminarli. Quando si configurano [etichette di conservazione](retention.md#retention-labels), invece, il periodo di conservazione può essere basato anche sul momento in cui si verifica un determinato tipo di evento. L'evento attiva l'inizio del periodo di conservazione e a tutto il contenuto a cui è applicata un'etichetta di conservazione per quel tipo di evento vengono applicate le azioni di conservazione dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="44007-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="44007-109">Esempi per l'uso della conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="44007-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="44007-110">**Dipendenti che lasciano l'organizzazione** Si supponga che i record dei dipendenti debbano essere conservati per 10 anni dal momento in cui lasciano l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="44007-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="44007-111">Trascorsi 10 anni, tutti i documenti relativi all'assunzione, alle prestazioni e alla cessazione del rapporto lavorativo di quel dipendente devono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="44007-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="44007-112">L'evento che attiva il periodo di conservazione di 10 anni è l'uscita del dipendente dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="44007-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="44007-113">**Scadenza del contratto** Si supponga che tutti i record relativi ai contratti debbano essere conservati per cinque anni dalla data di scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="44007-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="44007-114">L'evento che attiva il periodo di conservazione di cinque anni è la scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="44007-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="44007-p104">**Durata del prodotto** L'organizzazione potrebbe avere requisiti di conservazione relativi all'ultima data di produzione dei prodotti per i contenuti, come le specifiche tecniche. In questo caso, l'ultima data di produzione è l'evento che attiva il periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="44007-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="44007-p105">La conservazione basata su eventi viene generalmente utilizzata come parte di un processo di gestione dei record. Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="44007-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="44007-119">Anche le etichette basate su eventi marcano gli elementi come record, come parte di una soluzione di gestione dei record.</span><span class="sxs-lookup"><span data-stu-id="44007-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="44007-120">Per altre informazioni, vedere [Informazioni sulla gestione dei record](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="44007-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="44007-121">Un documento che è stato dichiarato un record ma il cui trigger di evento non è ancora stato eseguito viene conservato a tempo indeterminato (i record non possono essere eliminati in modo permanente) finché un evento non attiva il periodo di conservazione di quel documento.</span><span class="sxs-lookup"><span data-stu-id="44007-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="44007-122">Le etichette di conservazione basate su eventi di solito attivano una revisione per l'eliminazione alla fine del periodo di conservazione, in modo che un responsabile dei record possa rivedere ed eliminare manualmente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="44007-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="44007-123">Per altre informazioni, vedere [Eliminazione dei contenuti](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="44007-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="44007-124">Un'etichetta di conservazione basata su un evento ha le stesse funzionalità di qualsiasi etichetta di conservazione in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44007-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="44007-125">Per altre informazioni, vedere [Informazioni sui criteri e sulle etichette di conservazione](retention.md).</span><span class="sxs-lookup"><span data-stu-id="44007-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="44007-126">Informazioni sulla relazione tra tipi di eventi, etichette, eventi e ID delle risorse</span><span class="sxs-lookup"><span data-stu-id="44007-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="44007-127">Per usare correttamente la conservazione basata su eventi, è importante comprendere la relazione tra tipi di eventi, etichette di conservazione, eventi e ID delle risorse come illustrato nei diagrammi e nella spiegazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="44007-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagramma 1 di 2: tipo di evento, etichette, eventi e ID delle risorse](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagramma 2 di 2: tipo di evento, etichette, eventi e ID delle risorse](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="44007-p109">Creare etichette di conservazione per diversi tipi di contenuti e quindi associarle a un tipo di evento. Ad esempio, le etichette di conservazione per tipi diversi di file e record di prodotti sono associate a un tipo di evento denominato Durata del prodotto, in quanto tali record devono essere conservati per 10 anni dal momento in cui il prodotto raggiunge la fine del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="44007-p109">You create retention labels for different types of content and then associate them with a type of event. For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="44007-132">Gli utenti (in genere i responsabili dei record) applicano queste etichette di conservazione al contenuto e (per i documenti di SharePoint e OneDrive) immettono un ID risorsa per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="44007-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="44007-133">In questo esempio l'ID risorsa è un codice o nome del prodotto usato dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="44007-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="44007-134">Pertanto, ai record di ogni prodotto viene assegnata un'etichetta di conservazione e ogni record ha una proprietà che contiene un ID risorsa.</span><span class="sxs-lookup"><span data-stu-id="44007-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="44007-135">Il diagramma rappresenta **tutto il contenuto** per tutti i record dei prodotti in un'organizzazione e ogni elemento contiene l'ID risorsa del prodotto a cui appartiene il record.</span><span class="sxs-lookup"><span data-stu-id="44007-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="44007-p111">Durata prodotto è il tipo di evento. Un prodotto specifico che raggiunge la fine del ciclo di vita è un evento. Quando si verifica un evento di questo tipo, in questo caso quando un prodotto raggiunge la fine del ciclo di vita, si crea un evento che specifica:</span><span class="sxs-lookup"><span data-stu-id="44007-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="44007-138">Un ID risorsa (per i documenti di SharePoint e OneDrive)</span><span class="sxs-lookup"><span data-stu-id="44007-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="44007-p112">Parole chiave (per gli articoli di Exchange). In questo esempio, l'organizzazione utilizza un codice prodotto nei messaggi contenenti i record del prodotto, pertanto la parola chiave per gli elementi di Exchange è funzionalmente uguale all'ID risorsa per i documenti di SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="44007-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="44007-p113">La data in cui si è verificato l'evento. Questa data viene utilizzata come inizio del periodo di conservazione. Questa data può essere la data attuale, una futura o una passata.</span><span class="sxs-lookup"><span data-stu-id="44007-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="44007-p114">Dopo aver creato un evento, tale data dell'evento viene sincronizzata con tutto il contenuto che ha un'etichetta di conservazione di quel tipo di evento e che contiene l'ID risorsa o la parola chiave specificati. Come qualsiasi etichetta di conservazione, questa sincronizzazione può richiedere fino a 7 giorni. Nel diagramma precedente, il periodo di conservazione di tutti gli elementi cerchiati in rosso è attivato da questo evento. In altre parole, quando questo prodotto raggiunge la fine del suo ciclo di vita, quell'evento attiva il periodo di conservazione per i record di quel prodotto.</span><span class="sxs-lookup"><span data-stu-id="44007-p114">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword. Like any retention label, this synchronization can take up to seven days. In the previous diagram, all the items circled in red have their retention period triggered by this event. In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="44007-148">È importante tenere presente che se per un evento non si specificano le parole chiave o un ID risorsa, **l'evento attiverà il periodo di conservazione di ogni contenuto** con un'etichetta di conservazione corrispondente a quel tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="44007-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="44007-149">Nel diagramma precedente, ad esempio, verrebbe avviata la conservazione di tutto il contenuto.</span><span class="sxs-lookup"><span data-stu-id="44007-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="44007-150">Questo potrebbe non essere il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="44007-150">This might not be what you intend.</span></span>

<span data-ttu-id="44007-p116">Infine, tenere presente che ogni etichetta di conservazione ha le proprie impostazioni di conservazione. In questo esempio, tutti gli elementi specificano 10 anni, ma è possibile che un evento attivi etichette di conservazione con periodi di conservazione diversi.</span><span class="sxs-lookup"><span data-stu-id="44007-p116">Finally, remember that each retention label has its own retention settings. In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="44007-153">Come configurare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="44007-153">How to set up event-driven retention</span></span>

<span data-ttu-id="44007-154">Flusso di lavoro di alto livello per la conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="44007-154">High-level workflow for event-driven retention:</span></span>
  
![Diagramma del flusso di lavoro per la configurazione di conservazione basata su eventi](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="44007-156">Vedere [Usare etichette di riservatezza per gestire il ciclo di vita dei documenti archiviati in SharePoint](auto-apply-retention-labels-scenario.md) per uno scenario dettagliato sull'uso delle proprietà gestite in SharePoint per applicare automaticamente etichette di conservazione e implementare la conservazione basata su eventi.</span><span class="sxs-lookup"><span data-stu-id="44007-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="44007-157">Passaggio 1: creare un'etichetta il cui periodo di conservazione sia basato su un evento</span><span class="sxs-lookup"><span data-stu-id="44007-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="44007-158">Per creare e configurare l'etichetta di conservazione, usare le istruzioni in [Creare le etichette di conservazione](./create-apply-retention-labels.md#step-1-create-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="44007-158">To create and configure your retention label, see the instructions for [Create retention labels](./create-apply-retention-labels.md#step-1-create-retention-labels).</span></span> <span data-ttu-id="44007-159">Ma specifico per la conservazione basata su eventi, nella pagina **Definisci impostazioni di conservazione** della procedura guidata Crea etichetta di conservazione, dopo **Avvia il periodo di conservazione in base a**, selezionare uno dei tipi di eventi predefiniti dall'elenco a discesa o creane uno personalizzato selezionando **Crea nuovo tipo di evento**:</span><span class="sxs-lookup"><span data-stu-id="44007-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![Creare un nuovo tipo di evento per un'etichetta di conservazione](../media/SPRetention6.png)

<span data-ttu-id="44007-161">Un tipo di evento è semplicemente una descrizione generale di un evento a cui si vuole associare a un’etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="44007-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="44007-162">I tipi di evento predefiniti includono **(tipo di evento)** dopo il nome nell'elenco a discesa per semplificare l'identificazione ed è anche possibile visualizzare e creare il tipo di evento da **Gestione dei record** > **Eventi** scheda > **Gestisci tipi di eventi**.</span><span class="sxs-lookup"><span data-stu-id="44007-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="44007-163">La conservazione basata su eventi richiede impostazioni di conservazione che:</span><span class="sxs-lookup"><span data-stu-id="44007-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="44007-164">Conservino il contenuto.</span><span class="sxs-lookup"><span data-stu-id="44007-164">Retain the content.</span></span>
    
- <span data-ttu-id="44007-165">Eliminino il contenuto automaticamente o attivino una revisione per l'eliminazione alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="44007-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="44007-166">La conservazione basata su eventi viene in genere usata per il contenuto dichiarato come record, quindi questo è il momento giusto per verificare se occorre selezionare anche l'opzione per contrassegnare il contenuto come [record](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="44007-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="44007-167">Se si sta usando un tipo di evento esistente anziché creare un nuovo tipo di evento, andare al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="44007-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="44007-168">Dopo aver scelto un tipo di evento e salvato l'etichetta di conservazione, il tipo di evento non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="44007-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="44007-169">Passaggio 2: creare un nuovo tipo di evento per l’etichetta</span><span class="sxs-lookup"><span data-stu-id="44007-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="44007-170">Per le impostazioni di conservazione, se si è selezionato **Creare un nuovo tipo di evento**, immettere un nome e una descrizione per il tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="44007-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="44007-171">Selezionare **Avanti**, **Invia**, e **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="44007-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="44007-172">Tornare alla pagina **Definisci impostazioni di conservazione**. Nell'opzione **Avvia il periodo di conservazione in base a**, usare l’elenco a discesa per selezionare il tipo di evento creato.</span><span class="sxs-lookup"><span data-stu-id="44007-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="44007-173">Passaggio 3: pubblicare o applicare automaticamente le etichette di conservazione basate su eventi</span><span class="sxs-lookup"><span data-stu-id="44007-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="44007-174">Come per qualsiasi etichetta di conservazione, è necessario pubblicare o applicare automaticamente un'etichetta basata su eventi perché venga applicata manualmente o automaticamente al contenuto:</span><span class="sxs-lookup"><span data-stu-id="44007-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="44007-175">Creare etichette di conservazione e applicarle nelle app</span><span class="sxs-lookup"><span data-stu-id="44007-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="44007-176">Applicare automaticamente un'etichetta di conservazione al contenuto</span><span class="sxs-lookup"><span data-stu-id="44007-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="44007-177">Passaggio 4: immettere un ID risorsa</span><span class="sxs-lookup"><span data-stu-id="44007-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="44007-p119">Dopo aver applicato al contenuto un'etichetta basata sugli eventi, è possibile immettere un ID risorsa per ogni elemento. Ad esempio, la propria organizzazione potrebbe utilizzare:</span><span class="sxs-lookup"><span data-stu-id="44007-p119">After an event-based label is applied to content, you can enter an asset ID for each item. For example, your organization might use:</span></span>
  
- <span data-ttu-id="44007-180">Codici prodotto da utilizzare per conservare i contenuti solo per un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="44007-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="44007-181">Codici prodotto da utilizzare per conservare i contenuti solo per un progetto specifico.</span><span class="sxs-lookup"><span data-stu-id="44007-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="44007-182">ID dipendente da utilizzare per conservare i contenuti solo per una persona specifica.</span><span class="sxs-lookup"><span data-stu-id="44007-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="44007-183">L'ID risorsa è semplicemente un'ulteriore proprietà di un documento disponibile in SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="44007-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="44007-184">L’organizzazione potrebbe usare già altre proprietà del documento e altri ID per classificare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="44007-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="44007-185">In questo caso, è possibile usare anche quelle proprietà e quei valori quando si crea l'evento (vedere il Passaggio 6 di seguito).</span><span class="sxs-lookup"><span data-stu-id="44007-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="44007-186">L'aspetto importante è che si deve usare una certa combinazione *proprietà:valore* nelle proprietà del documento per associare l'elemento a un tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="44007-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Casella di testo per immettere un ID risorsa](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="44007-188">Passaggio 5: creare un evento</span><span class="sxs-lookup"><span data-stu-id="44007-188">Step 5: Create an event</span></span>

<span data-ttu-id="44007-189">Quando si verifica un'istanza particolare di quel tipo di evento, ad esempio quando un prodotto raggiunge la fine del ciclo di vita, accedere alla pagina **Gestione record** > **Eventi** nel Centro conformità Microsoft 365 e selezionare **+ Crea** per creare un evento.</span><span class="sxs-lookup"><span data-stu-id="44007-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="44007-190">Per attivare l’evento occorre crearlo qui.</span><span class="sxs-lookup"><span data-stu-id="44007-190">You trigger the event by creating it, here.</span></span>

![Creare un evento per attivare l'inizio della conservazione per le etichette di conservazione basate su eventi](../media/create-event-records-management.png)

<span data-ttu-id="44007-192">È supportato fino a 1 milione di eventi per tenant.</span><span class="sxs-lookup"><span data-stu-id="44007-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="44007-193">Passaggio 6: scegliere lo stesso tipo di evento utilizzato per l'etichetta nel Passaggio 2</span><span class="sxs-lookup"><span data-stu-id="44007-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="44007-194">Durante la creazione dell'evento, scegliere lo stesso tipo di evento specificato nelle impostazioni dell'etichetta di conservazione nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="44007-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="44007-195">Ad esempio, se è stata selezionata l'opzione **Durata del prodotto** come tipo di evento per le impostazioni dell'etichetta, selezionare **Durata del prodotto** quando si crea l'evento.</span><span class="sxs-lookup"><span data-stu-id="44007-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="44007-196">Il periodo di conservazione verrà attivato solo per il contenuto a cui sono applicate le etichette di conservazione di quel tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="44007-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![Opzione in Impostazioni evento per scegliere un tipo di evento](../media/choose-event-type-records-management.png)

<span data-ttu-id="44007-198">In alternativa, se è necessario creare un evento per più etichette di conservazione con tipi di evento diversi, selezionare l'opzione **Scegliere etichette esistenti**.</span><span class="sxs-lookup"><span data-stu-id="44007-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="44007-199">Selezionare quindi le etichette configurate per i tipi di evento che si vuole associare all'evento.</span><span class="sxs-lookup"><span data-stu-id="44007-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-query-for-exchange-asset-id-for-sharepoint-and-onedrive"></a><span data-ttu-id="44007-200">Passaggio 7: immettere parole chiave o query per Exchange, ID asset per SharePoint e OneDrive</span><span class="sxs-lookup"><span data-stu-id="44007-200">Step 7: Enter keywords or query for Exchange, asset ID for SharePoint and OneDrive</span></span>

<span data-ttu-id="44007-201">Ora si restringe l'ambito del contenuto.</span><span class="sxs-lookup"><span data-stu-id="44007-201">Now you narrow the scope of the content.</span></span> <span data-ttu-id="44007-202">Per il contenuto di Exchange, è necessario specificare parole chiave o una query.</span><span class="sxs-lookup"><span data-stu-id="44007-202">For Exchange content, you do this by specifying keywords or a query.</span></span> <span data-ttu-id="44007-203">Per i contenuti di SharePoint e OneDrive, è possibile farlo specificando gli ID asset.</span><span class="sxs-lookup"><span data-stu-id="44007-203">For SharePoint and OneDrive content, you do this by specifying asset IDs.</span></span>

<span data-ttu-id="44007-204">Per gli elementi di Exchange, usare parole chiave o una query che utilizza Keyword Query Language (KQL).</span><span class="sxs-lookup"><span data-stu-id="44007-204">For Exchange items, use keywords or a query that uses Keyword Query Language (KQL).</span></span> <span data-ttu-id="44007-205">Per maggiori informazioni sulla sintassi della query, vedere le [informazioni di riferimento sulla sintassi KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="44007-205">For more information about the query syntax, see [Keyword Query Language (KQL) syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span> <span data-ttu-id="44007-206">Per altre informazioni sulle proprietà ricercabili utilizzabili per Exchange, vedere [Query con parola chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="44007-206">For more information about the searchable properties that you can use for Exchange, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="44007-207">Per gli ID risorsa, la conservazione verrà applicata solo al contenuto con la coppia *proprietà:valore* specificata.</span><span class="sxs-lookup"><span data-stu-id="44007-207">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="44007-208">Ad esempio. se si usa la proprietà ID risorsa, immettere `ComplianceAssetID:<value>` nella casella relativa agli ID risorsa mostrati nell’immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="44007-208">For example, if you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown in the following picture.</span></span>

<span data-ttu-id="44007-209">Se non si immette un ID risorsa, a tutti i contenuti con etichette di quel tipo di evento verrà applicata la stessa data di conservazione.</span><span class="sxs-lookup"><span data-stu-id="44007-209">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="44007-210">È possibile che l'organizzazione abbia applicato altre proprietà e altri ID ai documenti correlati al tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="44007-210">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="44007-211">Ad esempio, se è necessario individuare i record di un prodotto specifico, l'ID può essere una combinazione della proprietà personalizzata ProductID e del valore "XYZ"</span><span class="sxs-lookup"><span data-stu-id="44007-211">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="44007-212">In questo caso, si immetterà `ProductID:XYZ` nella casella per gli ID risorsa mostrata nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="44007-212">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>

<span data-ttu-id="44007-p128">Infine, scegliere la data in cui si è verificato l'evento. Questa data viene utilizzata come inizio del periodo di conservazione. Dopo aver creato un evento, quella data dell'evento viene sincronizzata con tutti i contenuti con un'etichetta di conservazione di quel tipo di evento, ID risorsa e parole chiave o query. Come per qualsiasi etichetta di conservazione, la sincronizzazione può richiedere fino a sette giorni.</span><span class="sxs-lookup"><span data-stu-id="44007-p128">Finally, choose the date when the event occurred; this date is used as the start of the retention period. After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords or queries. As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Pagina Impostazioni evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="44007-217">Dopo la creazione di un evento, le impostazioni di conservazione vengono applicate al contenuto già etichettato e indicizzato.</span><span class="sxs-lookup"><span data-stu-id="44007-217">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="44007-218">Se l'etichetta di conservazione viene aggiunta al nuovo contenuto dopo la creazione dell'evento, è necessario creare un nuovo evento con gli stessi dettagli.</span><span class="sxs-lookup"><span data-stu-id="44007-218">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="44007-219">L'eliminazione di un evento non annulla le impostazioni di conservazione attualmente in vigore per il contenuto già etichettato.</span><span class="sxs-lookup"><span data-stu-id="44007-219">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="44007-220">Per fare questo, creare un nuovo evento con gli stessi dettagli, ma lasciare vuota la data.</span><span class="sxs-lookup"><span data-stu-id="44007-220">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="44007-221">Usare Ricerca contenuto per trovare tutto il contenuto con un'etichetta o un ID risorsa specifico</span><span class="sxs-lookup"><span data-stu-id="44007-221">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="44007-222">Dopo che le etichette di conservazione sono state assegnate al contenuto, è possibile usare la funzionalità di ricerca di contenuto per trovare tutti i contenuti classificati con un'etichetta di conservazione specifica o che contengono un ID risorsa specifico:</span><span class="sxs-lookup"><span data-stu-id="44007-222">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="44007-223">Per trovare tutto il contenuto con un'etichetta di conservazione specifica, selezionare la condizione **Etichetta di conservazione**, quindi immettere il nome completo dell'etichetta o parte di esso e usare un carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="44007-223">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="44007-224">Per trovare tutto il contenuto con un ID risorsa specifico, inserire la proprietà **ComplianceAssetID** e un valore, usando il formato `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="44007-224">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="44007-225">Per altre informazioni, vedere [Query con parola chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="44007-225">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="44007-226">Automatizzare gli eventi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="44007-226">Automate events by using PowerShell</span></span>

<span data-ttu-id="44007-227">È possibile usare uno script di PowerShell per automatizzare la conservazione basata su eventi dalle applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="44007-227">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="44007-228">Cmdlet di PowerShell disponibili per la conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="44007-228">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="44007-229">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="44007-229">Get-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [<span data-ttu-id="44007-230">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="44007-230">New-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [<span data-ttu-id="44007-231">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="44007-231">Remove-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [<span data-ttu-id="44007-232">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="44007-232">Set-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [<span data-ttu-id="44007-233">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="44007-233">Get-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/get-complianceretentionevent)
    
- [<span data-ttu-id="44007-234">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="44007-234">New-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="44007-235">Automatizzare gli eventi con un'API REST</span><span class="sxs-lookup"><span data-stu-id="44007-235">Automate events by using a REST API</span></span>

<span data-ttu-id="44007-236">È possibile usare un'API REST per creare automaticamente gli eventi che attivano l'inizio del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="44007-236">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="44007-237">Un'API REST è un endpoint di servizio che supporta set di operazioni HTTP (metodi), che forniscono l'accesso alle risorse del servizio per la creazione, il recupero, l'aggiornamento e l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="44007-237">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="44007-238">Per altre informazioni, vedere [Componenti di una richiesta/risposta dell'API REST](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="44007-238">For more information, see [Components of a REST API request/response](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="44007-239">Con l'API REST di Microsoft 365 è possibile creare e recuperare gli eventi usando i metodi POST e GET.</span><span class="sxs-lookup"><span data-stu-id="44007-239">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="44007-240">Sono disponibili due opzioni per usare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="44007-240">There are two options for using the REST API:</span></span>

- <span data-ttu-id="44007-241">**Microsoft Power Automate o delle applicazioni simili** per attivare automaticamente l'occorrenza di un evento.</span><span class="sxs-lookup"><span data-stu-id="44007-241">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="44007-242">Microsoft Power Automate è un agente di orchestrazione per la connessione ad altri sistemi, quindi non è necessario scrivere una soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="44007-242">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="44007-243">Per altre informazioni, vedere il [sito Web di Power Automate](https://flow.microsoft.com/it-IT/).</span><span class="sxs-lookup"><span data-stu-id="44007-243">For more information, see the [Power Automate website](https://flow.microsoft.com/it-IT/).</span></span>

- <span data-ttu-id="44007-244">**PowerShell o un client HTTP per richiamare l'API REST** per creare eventi con PowerShell (versione 6 o successiva) nell'ambito di una soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="44007-244">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="44007-245">Prima di usare l'API REST, come amministratore globale, confermare l'URL da usare per chiamare l'evento di conservazione.</span><span class="sxs-lookup"><span data-stu-id="44007-245">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="44007-246">A questo scopo, eseguire una chiamata all'evento di conservazione GET usando l'URL dell'API REST:</span><span class="sxs-lookup"><span data-stu-id="44007-246">To do this, run a GET retention event call by using the REST API URL:</span></span>

```http
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="44007-247">Controllare il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="44007-247">Check the response code.</span></span> <span data-ttu-id="44007-248">Se è 302, ottenere l'URL reindirizzato dalla proprietà Location dell'intestazione della risposta e usare tale URL anziché `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` nelle istruzioni che seguono.</span><span class="sxs-lookup"><span data-stu-id="44007-248">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="44007-249">Gli eventi che vengono creati automaticamente possono essere confermati visualizzandoli in Centro conformità Microsoft 365 > **Gestione record** >  **eventi**.</span><span class="sxs-lookup"><span data-stu-id="44007-249">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="44007-250">Usare Microsoft Power Automate per creare l'evento</span><span class="sxs-lookup"><span data-stu-id="44007-250">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="44007-251">Creare un flusso che crea un evento usando l'API REST di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="44007-251">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Usare Flow per creare un evento](../media/automate-event-driven-retention-flow-1.png)

![Usare Flow per chiamare l'API REST](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="44007-254">Creare un evento</span><span class="sxs-lookup"><span data-stu-id="44007-254">Create an event</span></span>

<span data-ttu-id="44007-255">Codice di esempio per chiamare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="44007-255">Sample code to call the REST API:</span></span>

- <span data-ttu-id="44007-256">**Metodo**: POST</span><span class="sxs-lookup"><span data-stu-id="44007-256">**Method**: POST</span></span>
- <span data-ttu-id="44007-257">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="44007-257">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="44007-258">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="44007-258">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="44007-259">**Corpo**:</span><span class="sxs-lookup"><span data-stu-id="44007-259">**Body**:</span></span>
    
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
    
- <span data-ttu-id="44007-260">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="44007-260">**Authentication**: Basic</span></span>
- <span data-ttu-id="44007-261">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="44007-261">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="44007-262">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="44007-262">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="44007-263">Parametri disponibili</span><span class="sxs-lookup"><span data-stu-id="44007-263">Available parameters</span></span>


|<span data-ttu-id="44007-264">Parametri</span><span class="sxs-lookup"><span data-stu-id="44007-264">Parameters</span></span>|<span data-ttu-id="44007-265">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44007-265">Description</span></span>|<span data-ttu-id="44007-266">Note</span><span class="sxs-lookup"><span data-stu-id="44007-266">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="44007-267"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="44007-267"><d:Name></d:Name></span></span>|<span data-ttu-id="44007-268">Immettere un nome univoco per l'evento,</span><span class="sxs-lookup"><span data-stu-id="44007-268">Provide a unique name for the event,</span></span>|<span data-ttu-id="44007-269">Non può contenere spazi iniziali o finali o i caratteri seguenti: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="44007-269">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="44007-270">, : ;</span><span class="sxs-lookup"><span data-stu-id="44007-270">, : ;</span></span>|
|<span data-ttu-id="44007-271"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="44007-271"><d:EventType></d:EventType></span></span>|<span data-ttu-id="44007-272">Immettere il nome del tipo di evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="44007-272">Enter event type name (or Guid),</span></span>|<span data-ttu-id="44007-p137">Esempio: "Licenziamento dipendente". Il tipo di evento deve essere associato a un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="44007-p137">Example: "Employee termination". Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="44007-275"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="44007-275"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="44007-276">Immettere "ComplianceAssetId:" + ID dipendente</span><span class="sxs-lookup"><span data-stu-id="44007-276">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="44007-277">Esempio: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="44007-277">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="44007-278"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="44007-278"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="44007-279">Data e ora evento</span><span class="sxs-lookup"><span data-stu-id="44007-279">Event Date and Time</span></span>|<span data-ttu-id="44007-280">Formato: aaaa-MM-ggTHH:mm:ssZ, esempio: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="44007-280">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="44007-281">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="44007-281">Response codes</span></span>

| <span data-ttu-id="44007-282">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="44007-282">Response Code</span></span> | <span data-ttu-id="44007-283">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44007-283">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="44007-284">302</span><span class="sxs-lookup"><span data-stu-id="44007-284">302</span></span>               | <span data-ttu-id="44007-285">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="44007-285">Redirect</span></span>              |
| <span data-ttu-id="44007-286">201</span><span class="sxs-lookup"><span data-stu-id="44007-286">201</span></span>               | <span data-ttu-id="44007-287">Creato</span><span class="sxs-lookup"><span data-stu-id="44007-287">Created</span></span>               |
| <span data-ttu-id="44007-288">403</span><span class="sxs-lookup"><span data-stu-id="44007-288">403</span></span>               | <span data-ttu-id="44007-289">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="44007-289">Authorization Failed</span></span>  |
| <span data-ttu-id="44007-290">401</span><span class="sxs-lookup"><span data-stu-id="44007-290">401</span></span>               | <span data-ttu-id="44007-291">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="44007-291">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="44007-292">Ricevere gli eventi in base a un intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="44007-292">Get events based on a time range</span></span>

- <span data-ttu-id="44007-293">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="44007-293">**Method**: GET</span></span>

- <span data-ttu-id="44007-294">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="44007-294">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="44007-295">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="44007-295">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="44007-296">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="44007-296">**Authentication**: Basic</span></span>

- <span data-ttu-id="44007-297">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="44007-297">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="44007-298">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="44007-298">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="44007-299">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="44007-299">Response codes</span></span>

| <span data-ttu-id="44007-300">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="44007-300">Response Code</span></span> | <span data-ttu-id="44007-301">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44007-301">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="44007-302">200</span><span class="sxs-lookup"><span data-stu-id="44007-302">200</span></span>               | <span data-ttu-id="44007-303">OK, un elenco di eventi in atom+ xml</span><span class="sxs-lookup"><span data-stu-id="44007-303">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="44007-304">404</span><span class="sxs-lookup"><span data-stu-id="44007-304">404</span></span>               | <span data-ttu-id="44007-305">Non trovato</span><span class="sxs-lookup"><span data-stu-id="44007-305">Not found</span></span>                         |
| <span data-ttu-id="44007-306">302</span><span class="sxs-lookup"><span data-stu-id="44007-306">302</span></span>               | <span data-ttu-id="44007-307">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="44007-307">Redirect</span></span>                          |
| <span data-ttu-id="44007-308">401</span><span class="sxs-lookup"><span data-stu-id="44007-308">401</span></span>               | <span data-ttu-id="44007-309">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="44007-309">Authorization Failed</span></span>              |
| <span data-ttu-id="44007-310">403</span><span class="sxs-lookup"><span data-stu-id="44007-310">403</span></span>               | <span data-ttu-id="44007-311">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="44007-311">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="44007-312">Ottenere un evento in base all'ID</span><span class="sxs-lookup"><span data-stu-id="44007-312">Get an event by ID</span></span>

- <span data-ttu-id="44007-313">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="44007-313">**Method**: GET</span></span>

- <span data-ttu-id="44007-314">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="44007-314">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="44007-315">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="44007-315">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="44007-316">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="44007-316">**Authentication**: Basic</span></span>

- <span data-ttu-id="44007-317">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="44007-317">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="44007-318">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="44007-318">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="44007-319">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="44007-319">Response codes</span></span>

| <span data-ttu-id="44007-320">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="44007-320">Response Code</span></span> | <span data-ttu-id="44007-321">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44007-321">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="44007-322">200</span><span class="sxs-lookup"><span data-stu-id="44007-322">200</span></span>               | <span data-ttu-id="44007-323">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="44007-323">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="44007-324">404</span><span class="sxs-lookup"><span data-stu-id="44007-324">404</span></span>               | <span data-ttu-id="44007-325">Non trovato</span><span class="sxs-lookup"><span data-stu-id="44007-325">Not found</span></span>                                            |
| <span data-ttu-id="44007-326">302</span><span class="sxs-lookup"><span data-stu-id="44007-326">302</span></span>               | <span data-ttu-id="44007-327">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="44007-327">Redirect</span></span>                                             |
| <span data-ttu-id="44007-328">401</span><span class="sxs-lookup"><span data-stu-id="44007-328">401</span></span>               | <span data-ttu-id="44007-329">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="44007-329">Authorization Failed</span></span>                                 |
| <span data-ttu-id="44007-330">403</span><span class="sxs-lookup"><span data-stu-id="44007-330">403</span></span>               | <span data-ttu-id="44007-331">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="44007-331">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="44007-332">Ottenere un evento in base al nome</span><span class="sxs-lookup"><span data-stu-id="44007-332">Get an event by name</span></span>

- <span data-ttu-id="44007-333">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="44007-333">**Method**: GET</span></span>

- <span data-ttu-id="44007-334">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="44007-334">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="44007-335">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="44007-335">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="44007-336">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="44007-336">**Authentication**: Basic</span></span>

- <span data-ttu-id="44007-337">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="44007-337">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="44007-338">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="44007-338">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="44007-339">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="44007-339">Response codes</span></span>

| <span data-ttu-id="44007-340">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="44007-340">Response Code</span></span> | <span data-ttu-id="44007-341">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44007-341">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="44007-342">200</span><span class="sxs-lookup"><span data-stu-id="44007-342">200</span></span>               | <span data-ttu-id="44007-343">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="44007-343">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="44007-344">404</span><span class="sxs-lookup"><span data-stu-id="44007-344">404</span></span>               | <span data-ttu-id="44007-345">Non trovato</span><span class="sxs-lookup"><span data-stu-id="44007-345">Not found</span></span>                                            |
| <span data-ttu-id="44007-346">302</span><span class="sxs-lookup"><span data-stu-id="44007-346">302</span></span>               | <span data-ttu-id="44007-347">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="44007-347">Redirect</span></span>                                             |
| <span data-ttu-id="44007-348">401</span><span class="sxs-lookup"><span data-stu-id="44007-348">401</span></span>               | <span data-ttu-id="44007-349">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="44007-349">Authorization Failed</span></span>                                 |
| <span data-ttu-id="44007-350">403</span><span class="sxs-lookup"><span data-stu-id="44007-350">403</span></span>               | <span data-ttu-id="44007-351">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="44007-351">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="44007-352">Usare PowerShell o qualsiasi client HTTP per creare l'evento</span><span class="sxs-lookup"><span data-stu-id="44007-352">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="44007-353">PowerShell deve essere in versione 6 o successiva.</span><span class="sxs-lookup"><span data-stu-id="44007-353">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="44007-354">In una sessione di PowerShell eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="44007-354">In a PowerShell session, run the following script:</span></span>

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
