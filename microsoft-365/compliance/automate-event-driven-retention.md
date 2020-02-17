---
title: Automatizzare la conservazione basata su eventi
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Questo argomento illustra come configurare i flussi di processo aziendale in modo da automatizzare la conservazione attraverso gli eventi usando l'API REST di Microsoft 365.
ms.openlocfilehash: 692671ca5e7d956cb168ac0de2e409e7023cfd04
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079088"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="cfdde-103">Automatizzare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="cfdde-103">Automate event-based retention</span></span>

<span data-ttu-id="cfdde-p101">L'esplosione del contenuto nelle organizzazioni e il modo in cui può diventare ROT (redundant, obsolete, trivial, cioè ridondante, obsoleto e banale), è una cosa seria. Per continuare a soddisfare gli obblighi di conformità normativa, legale e finanziaria, le organizzazioni devono poter conservare e proteggere le informazioni importanti e trovare rapidamente ciò che conta. Conservare solo informazioni importanti e pertinenti è fondamentale per il successo di un’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="cfdde-p102">Per riuscirci, le organizzazioni possono sfruttare le soluzioni di conservazione nel Centro sicurezza e conformità di Office 365. La conservazione può essere attivata usando [etichette di conservazione](labels.md), che consentono di [basare il periodo di conservazione su un evento specifico](event-driven-retention.md). In genere, il periodo di conservazione si basa su una data nota, come la data di creazione o dell'ultima modifica del contenuto. Tuttavia, le organizzazioni fanno fronte anche a requisiti di smaltimento dei contenuti in base al verificarsi di un evento, ad esempio sette anni dopo che un dipendente ha lasciato l’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="cfdde-p103">Per garantire lo smaltimento conforme del contenuto, è fondamentale conoscere la data in cui si verifica un evento. Con il rapido aumento del volume di contenuti, diventa sempre più difficile conservare e smaltire i contenuti in maniera puntuale e conforme.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="cfdde-p104">La conservazione basata sugli eventi è la soluzione a questo problema. Questo argomento illustra come configurare i flussi di processo aziendale in modo da automatizzare la conservazione attraverso gli eventi usando l'API REST di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="cfdde-116">Informazioni sulla conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="cfdde-116">About event-based retention</span></span>

<span data-ttu-id="cfdde-p105">Un'organizzazione può avere dimensioni piccole, medie o grandi. Il numero di documenti aziendali e legali, dossier del personale, contratti e documenti sul prodotto che vengono creati e gestiti su base quotidiana è in drastico aumento.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="cfdde-p106">Ad esempio, ogni giorno decine o centinaia di dipendenti entrano a far parte delle organizzazioni o le lasciano. Il reparto Risorse umane continua a creare, aggiornare o eliminare i documenti relativi ai dipendenti in base ai requisiti aziendali. Questo processo è soggetto ai diversi criteri di conservazione indicati per l'azienda:</span><span class="sxs-lookup"><span data-stu-id="cfdde-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="cfdde-p107">**Il periodo di conservazione del contenuto può essere una data nota**, ad esempio la data di creazione, dell'ultima modifica o dell'assegnazione di un'etichetta al contenuto. Ad esempio, si potrebbero conservare documenti per sette anni dalla creazione per poi eliminarli.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="cfdde-p108">**Il periodo di conservazione del contenuto può essere anche una data sconosciuta**. Ad esempio, con le etichette di conservazione è anche possibile basare anche un periodo di conservazione sul momento in cui si verifica un determinato tipo di evento, ad esempio quando un dipendente lascia l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="cfdde-p109">L'evento fa scattare l'inizio del periodo di conservazione e tutto il contenuto con un'etichetta applicata per quel tipo di evento riceve le azioni di conservazione dell'etichetta applicate su di esso. È ciò che si intende con conservazione basata sugli eventi. Per altre informazioni, vedere [Panoramica della conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="cfdde-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="cfdde-129">Configurare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="cfdde-129">Set up event-based retention</span></span>

<span data-ttu-id="cfdde-130">Questa sezione descrive le operazioni da eseguire prima della conservazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-130">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="cfdde-131">Identificare i ruoli</span><span class="sxs-lookup"><span data-stu-id="cfdde-131">Identify roles</span></span>

<span data-ttu-id="cfdde-132">Identificare i diversi ruoli in un'organizzazione che eseguono attività di Gestione record e che sarebbero i responsabili della conservazione efficace ed efficiente dei documenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="cfdde-132">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="cfdde-133">**Persona**</span><span class="sxs-lookup"><span data-stu-id="cfdde-133">**Persona**</span></span>| <span data-ttu-id="cfdde-134">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="cfdde-134">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="cfdde-135">Amministratore</span><span class="sxs-lookup"><span data-stu-id="cfdde-135">Admin</span></span> | <span data-ttu-id="cfdde-136">Crea tipi di eventi di conservazione, etichette di conservazione e repository dei record in SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfdde-136">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="cfdde-137">Responsabile della gestione dei record</span><span class="sxs-lookup"><span data-stu-id="cfdde-137">Records Manager</span></span>                                  | <span data-ttu-id="cfdde-138">Fornisce linee guida su criteri di conservazione e pianificazioni della conservazione, oltre a informazioni dettagliate sulla conformità</span><span class="sxs-lookup"><span data-stu-id="cfdde-138">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="cfdde-139">Amministratore di sistema (azienda)</span><span class="sxs-lookup"><span data-stu-id="cfdde-139">System Admin (business)</span></span>                          | <span data-ttu-id="cfdde-140">Configura e gestisce i sistemi esterni in modo da utilizzare Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cfdde-140">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="cfdde-141">Information Worker</span><span class="sxs-lookup"><span data-stu-id="cfdde-141">Information Worker</span></span>                               | <span data-ttu-id="cfdde-142">Gestisce il ciclo di vita del proprio processo aziendale (risorse umane, finanza, IT ecc.)</span><span class="sxs-lookup"><span data-stu-id="cfdde-142">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="cfdde-143">Configurare il Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="cfdde-143">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="cfdde-144">L'amministratore di conformità crea un tipo di evento, &ndash;ad esempio Licenziamento dipendente, Scadenza contratto oppure Fine produzione.</span><span class="sxs-lookup"><span data-stu-id="cfdde-144">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="cfdde-145">Vedere il processo dettagliato in [Conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="cfdde-145">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="cfdde-146">L'amministratore di conformità crea un'etichetta di conservazione in base a un evento e la associa a un tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="cfdde-146">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="cfdde-147">Ci sono quattro tipi di trigger per le etichette di conservazione:</span><span class="sxs-lookup"><span data-stu-id="cfdde-147">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="cfdde-148">Data creazione</span><span class="sxs-lookup"><span data-stu-id="cfdde-148">Create date</span></span>
                
    2. <span data-ttu-id="cfdde-149">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="cfdde-149">Last modified</span></span>
                
    3. <span data-ttu-id="cfdde-150">Data etichetta (quando il contenuto è stato etichettato)</span><span class="sxs-lookup"><span data-stu-id="cfdde-150">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="cfdde-151">Basata su eventi</span><span class="sxs-lookup"><span data-stu-id="cfdde-151">Event-based</span></span>
    
3. <span data-ttu-id="cfdde-152">L'amministratore di conformità pubblica l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="cfdde-152">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="cfdde-153">Configurare SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfdde-153">Set up SharePoint</span></span>
   
<span data-ttu-id="cfdde-154">Per creare un repository dei record, l'amministratore di conformità deve:</span><span class="sxs-lookup"><span data-stu-id="cfdde-154">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="cfdde-155">Creare un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfdde-155">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="cfdde-156">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfdde-156">Does one of the following:</span></span>
        
    - <span data-ttu-id="cfdde-p111">Creare una raccolta di SharePoint: configurare un'etichetta basata su eventi a livello di raccolta. Per altre informazioni, vedere [Applicazione di un'etichetta di conservazione predefinita a tutto il contenuto in una raccolta, una cartella o un set di documenti di SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="cfdde-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="cfdde-159">Configura un set di documenti in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfdde-159">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="cfdde-160">Per ulteriori informazioni, vedere [Introduzione ai set di documenti](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="cfdde-160">For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="cfdde-161">Assegna un ID risorsa a ogni set di documenti dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="cfdde-161">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="cfdde-162">Un ID risorsa è il nome o codice di un prodotto usato dall'organizzazione, ad esempio il Numero dipendente può essere un ID risorsa.</span><span class="sxs-lookup"><span data-stu-id="cfdde-162">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="cfdde-163">Assegnando l'ID risorsa alla cartella, ogni elemento nella cartella eredita automaticamente lo stesso ID risorsa.</span><span class="sxs-lookup"><span data-stu-id="cfdde-163">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="cfdde-164">Di conseguenza, il periodo di conservazione di tutti gli elementi nella cartella sarà generato dallo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="cfdde-164">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="cfdde-165">Modi per attivare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="cfdde-165">Ways to trigger event-based retention</span></span>

<span data-ttu-id="cfdde-166">Esistono due modi in cui è possibile attivare la conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="cfdde-166">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="cfdde-167">**Uso dell'interfaccia di amministrazione** Si tratta di un processo che può essere sfruttato per conservare meno contenuto alla volta o per ridurre la frequenza di attivazione della conservazione e renderla, ad esempio, mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="cfdde-167">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="cfdde-168">Per ulteriori informazioni su questo processo, vedere [Panoramica della conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="cfdde-168">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="cfdde-169">Tuttavia, questo metodo di attivazione della conservazione può richiedere tempo e causare errori, e diminuire così la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="cfdde-169">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="cfdde-170">Di conseguenza, una soluzione automatica e semplice per attivare la conservazione può aumentare la sicurezza e la conformità dei dati.</span><span class="sxs-lookup"><span data-stu-id="cfdde-170">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="cfdde-p115">**Con l'API REST di M365**: questo processo è utile quando occorre conservare grandi quantità di contenuto contemporaneamente e/o la frequenza di attivazione della conservazione è alta, ad esempio giornaliera o settimanale. Il flusso rileva il verificarsi di un evento nel sistema line-of-business e crea automaticamente un evento correlato nel Centro di sicurezza e conformità. Non è necessario creare manualmente un evento nell'interfaccia ogni volta che se ne verifica uno.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="cfdde-174">Sono disponibili due opzioni per usare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="cfdde-174">There are two options for using the REST API:</span></span>

- <span data-ttu-id="cfdde-175">**Microsoft Flow o delle applicazioni simili** possono essere usate per attivare automaticamente la ricorrenza di un evento.</span><span class="sxs-lookup"><span data-stu-id="cfdde-175">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="cfdde-176">Microsoft Flow è un agente di orchestrazione per la connessione ad altri sistemi.</span><span class="sxs-lookup"><span data-stu-id="cfdde-176">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="cfdde-177">L'uso di Microsoft Flow non richiede una soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cfdde-177">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="cfdde-178">**PowerShell o un client HTTP per le chiamate all'API REST**: usare PowerShell (versione 6 o successive) per chiamare l'API REST di Microsoft 365 per creare eventi.</span><span class="sxs-lookup"><span data-stu-id="cfdde-178">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="cfdde-179">Un'API Rest è un endpoint di servizio che supporta set di operazioni HTTP (metodi), che forniscono l'accesso alle risorse del servizio per la creazione, il ripristino, l’aggiornamento e l’eliminazione.</span><span class="sxs-lookup"><span data-stu-id="cfdde-179">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="cfdde-180">Per altre informazioni, vedere [Componenti di una richiesta/risposta dell'API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="cfdde-180">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="cfdde-181">In questo caso, con l'API REST di Microsoft 365, è possibile creare e recuperare gli eventi usando le operazioni (metodi) POST e GET.</span><span class="sxs-lookup"><span data-stu-id="cfdde-181">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="cfdde-182">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="cfdde-182">Example scenarios</span></span>

<span data-ttu-id="cfdde-183">Considerare i seguenti scenari.</span><span class="sxs-lookup"><span data-stu-id="cfdde-183">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="cfdde-184">Scenario 1: Dipendenti che lasciano l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="cfdde-184">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="cfdde-185">Un’organizzazione crea e archivia numerosi documenti relativi all’impiego di ogni singolo dipendente.</span><span class="sxs-lookup"><span data-stu-id="cfdde-185">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="cfdde-186">Questi documenti sono gestiti e conservati durante il periodo di lavoro di ogni dipendente.</span><span class="sxs-lookup"><span data-stu-id="cfdde-186">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="cfdde-187">Tuttavia, quando il dipendente lascia l'organizzazione o quando termina il periodo di lavoro, l'organizzazione è tenuta a rispettare i requisiti legali e aziendali e a mantenere i documenti di tale dipendente per un lasso di tempo concordato.</span><span class="sxs-lookup"><span data-stu-id="cfdde-187">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="cfdde-188">Quindi, se più dipendenti lasciassero l'organizzazione ogni giorno, l'organizzazione dovrebbe attivare quotidianamente l'intervallo di conservazione per centinaia o migliaia di documenti.</span><span class="sxs-lookup"><span data-stu-id="cfdde-188">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="cfdde-189">Oltre a tutto questo, occorre calcolare il periodo di conservazione per ciascun dipendente in base alla formula Data licenziamento dipendente + numero di giorni, mesi o anni in base al tipo di record del dipendente.</span><span class="sxs-lookup"><span data-stu-id="cfdde-189">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="cfdde-190">Ad esempio, il periodo di conservazione dei documenti relativi alla retribuzione del lavoratore e ai benefit dipendenti potrebbe differire.</span><span class="sxs-lookup"><span data-stu-id="cfdde-190">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="cfdde-191">Il diagramma di seguito illustra come possano essere presenti più etichette associate a un singolo evento.</span><span class="sxs-lookup"><span data-stu-id="cfdde-191">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="cfdde-192">In questo caso, tutti i file con l’etichetta Assicurazione contro gli infortuni sul lavoro e tutti i file con l’etichetta Benefit dipendenti sono associati a un singolo evento, ossia il licenziamento del dipendente dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfdde-192">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="cfdde-193">Ognuno dei vari file ha intervalli di conservazione diversi.</span><span class="sxs-lookup"><span data-stu-id="cfdde-193">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="cfdde-194">Quindi, quando un dipendente lascia l'organizzazione, i file raggruppati sotto ogni etichetta hanno un periodo di conservazione diverso.</span><span class="sxs-lookup"><span data-stu-id="cfdde-194">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="cfdde-195">L'attivazione di tutti questi intervalli di conservazione, diversi per ogni tipo di file o etichetta e per ogni dipendente, è un'operazione molto complessa.</span><span class="sxs-lookup"><span data-stu-id="cfdde-195">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="cfdde-196">Ancora di più lo è eseguire questa operazione per più dipendenti.</span><span class="sxs-lookup"><span data-stu-id="cfdde-196">Imagine doing this for multiple employees.</span></span>

![Diagramma del tipo di evento, evento ed etichette](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="cfdde-198">Di conseguenza, un processo automatizzato per attivare i diversi intervalli di conservazione per più dipendenti consente di risparmiare tempo, è privo di errori ed estremamente efficiente.</span><span class="sxs-lookup"><span data-stu-id="cfdde-198">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="cfdde-199">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="cfdde-199">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e azioni per lo scenario in cui il dipendente lascia l'organizzazione](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="cfdde-201">L'amministratore crea le cartelle del dipendente nel set di documenti, ad esempio Angela Barbariol, Luca Udinesi.</span><span class="sxs-lookup"><span data-stu-id="cfdde-201">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="cfdde-202">L'amministratore aggiunge i documenti dei dipendenti, ad esempio Benefit, Paghe, Assicurazione contro gli infortuni sul lavoro, a ogni cartella dipendente.</span><span class="sxs-lookup"><span data-stu-id="cfdde-202">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="cfdde-203">L'amministratore assegna l'ID risorsa a ogni cartella dipendente.</span><span class="sxs-lookup"><span data-stu-id="cfdde-203">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="cfdde-204">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="cfdde-204">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="cfdde-205">L'amministratore SCC crea tipi di eventi correlati al dipendente, come "Licenziamento del dipendente", "Assunzione del dipendente".</span><span class="sxs-lookup"><span data-stu-id="cfdde-205">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="cfdde-206">L'amministratore SCC crea l'etichetta "Conservazione dipendente".</span><span class="sxs-lookup"><span data-stu-id="cfdde-206">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="cfdde-207">L'etichetta "Conservazione dipendente" viene pubblicata e applicata manualmente o automaticamente ai documenti dei dipendenti in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfdde-207">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="cfdde-208">Un sistema di gestione delle risorse umane come Workday può eseguire periodicamente Microsoft Flow per gestire i documenti dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="cfdde-208">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="cfdde-209">Se un dipendente ha lasciato l'organizzazione, Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del dipendente specifico.</span><span class="sxs-lookup"><span data-stu-id="cfdde-209">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="cfdde-210">Uso di Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="cfdde-210">Using Microsoft Flow</span></span>

<span data-ttu-id="cfdde-211">Passaggio 1: Creare un flusso per creare un evento usando le API REST di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cfdde-211">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usare Flow per creare un evento](../media/automate-event-driven-retention-flow-1.png)

![Usare Flow per chiamare l'API REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="cfdde-214">Creare un evento</span><span class="sxs-lookup"><span data-stu-id="cfdde-214">Create an event</span></span>

<span data-ttu-id="cfdde-215">Codice di esempio per chiamare l'API REST</span><span class="sxs-lookup"><span data-stu-id="cfdde-215">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cfdde-216">Metodo</span><span class="sxs-lookup"><span data-stu-id="cfdde-216">Method</span></span></th>
<th><span data-ttu-id="cfdde-217">POST</span><span class="sxs-lookup"><span data-stu-id="cfdde-217">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cfdde-218">URL</span><span class="sxs-lookup"><span data-stu-id="cfdde-218">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cfdde-219">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="cfdde-219">Headers</span></span></td>
<td><span data-ttu-id="cfdde-220">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cfdde-220">Content-Type</span></span></td>
<td><span data-ttu-id="cfdde-221">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="cfdde-221">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cfdde-222">Corpo</span><span class="sxs-lookup"><span data-stu-id="cfdde-222">Body</span></span></td>
<td><p><span data-ttu-id="cfdde-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="cfdde-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="cfdde-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="cfdde-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="cfdde-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="cfdde-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="cfdde-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="cfdde-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="cfdde-229">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-229">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="cfdde-230">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-230">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="cfdde-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="cfdde-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="cfdde-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="cfdde-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="cfdde-235">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-235">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="cfdde-236">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-236">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="cfdde-237">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-237">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cfdde-238">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="cfdde-238">Authentication</span></span></td>
<td><span data-ttu-id="cfdde-239">Di base</span><span class="sxs-lookup"><span data-stu-id="cfdde-239">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cfdde-240">Nome utente</span><span class="sxs-lookup"><span data-stu-id="cfdde-240">Username</span></span></td>
<td><span data-ttu-id="cfdde-241">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="cfdde-241">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cfdde-242">Password</span><span class="sxs-lookup"><span data-stu-id="cfdde-242">Password</span></span></td>
<td><span data-ttu-id="cfdde-243">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="cfdde-243">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="cfdde-244">Parametri disponibili</span><span class="sxs-lookup"><span data-stu-id="cfdde-244">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cfdde-245"><strong>Parametri</strong></span><span class="sxs-lookup"><span data-stu-id="cfdde-245"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="cfdde-246"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="cfdde-246"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="cfdde-247"><strong>Note</strong></span><span class="sxs-lookup"><span data-stu-id="cfdde-247"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cfdde-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="cfdde-249">Immettere un nome univoco per l'evento,</span><span class="sxs-lookup"><span data-stu-id="cfdde-249">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="cfdde-p121">Non può contenere spazi e i caratteri seguenti: % \* \ &amp; &lt; &gt; | # ? , : ,</span><span class="sxs-lookup"><span data-stu-id="cfdde-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cfdde-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="cfdde-253">Immettere il nome del tipo di evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="cfdde-253">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="cfdde-p122">Esempio: "Licenziamento dipendente". Il tipo di evento deve essere associato a un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cfdde-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="cfdde-257">Immettere "ComplianceAssetId:" + ID dipendente</span><span class="sxs-lookup"><span data-stu-id="cfdde-257">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="cfdde-258">Esempio:&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="cfdde-258">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cfdde-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="cfdde-260">Data e ora evento</span><span class="sxs-lookup"><span data-stu-id="cfdde-260">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="cfdde-261">Formato: aaaa-MM-ggTHH:mm:ssZ, esempio:</span><span class="sxs-lookup"><span data-stu-id="cfdde-261">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="cfdde-262">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="cfdde-262">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="cfdde-263">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="cfdde-263">Response codes</span></span>

| <span data-ttu-id="cfdde-264">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="cfdde-264">**Response Code**</span></span> | <span data-ttu-id="cfdde-265">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cfdde-265">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="cfdde-266">302</span><span class="sxs-lookup"><span data-stu-id="cfdde-266">302</span></span>               | <span data-ttu-id="cfdde-267">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="cfdde-267">Redirect</span></span>              |
| <span data-ttu-id="cfdde-268">201</span><span class="sxs-lookup"><span data-stu-id="cfdde-268">201</span></span>               | <span data-ttu-id="cfdde-269">Creato</span><span class="sxs-lookup"><span data-stu-id="cfdde-269">Created</span></span>               |
| <span data-ttu-id="cfdde-270">403</span><span class="sxs-lookup"><span data-stu-id="cfdde-270">403</span></span>               | <span data-ttu-id="cfdde-271">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cfdde-271">Authorization Failed</span></span>  |
| <span data-ttu-id="cfdde-272">401</span><span class="sxs-lookup"><span data-stu-id="cfdde-272">401</span></span>               | <span data-ttu-id="cfdde-273">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cfdde-273">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="cfdde-274">Ricevere gli eventi in base all'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="cfdde-274">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cfdde-275">Metodo</span><span class="sxs-lookup"><span data-stu-id="cfdde-275">Method</span></span></th>
<th><span data-ttu-id="cfdde-276">GET</span><span class="sxs-lookup"><span data-stu-id="cfdde-276">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cfdde-277">URL</span><span class="sxs-lookup"><span data-stu-id="cfdde-277">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="cfdde-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="cfdde-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cfdde-279">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="cfdde-279">Headers</span></span></td>
<td><span data-ttu-id="cfdde-280">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cfdde-280">Content-Type</span></span></td>
<td><span data-ttu-id="cfdde-281">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="cfdde-281">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cfdde-282">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="cfdde-282">Authentication</span></span></td>
<td><span data-ttu-id="cfdde-283">Di base</span><span class="sxs-lookup"><span data-stu-id="cfdde-283">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cfdde-284">Nome utente</span><span class="sxs-lookup"><span data-stu-id="cfdde-284">Username</span></span></td>
<td><span data-ttu-id="cfdde-285">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="cfdde-285">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cfdde-286">Password</span><span class="sxs-lookup"><span data-stu-id="cfdde-286">Password</span></span></td>
<td><span data-ttu-id="cfdde-287">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="cfdde-287">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="cfdde-288">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="cfdde-288">Response codes</span></span>

| <span data-ttu-id="cfdde-289">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="cfdde-289">**Response Code**</span></span> | <span data-ttu-id="cfdde-290">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cfdde-290">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="cfdde-291">200</span><span class="sxs-lookup"><span data-stu-id="cfdde-291">200</span></span>               | <span data-ttu-id="cfdde-292">OK, un elenco di eventi in atom+ xml</span><span class="sxs-lookup"><span data-stu-id="cfdde-292">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="cfdde-293">404</span><span class="sxs-lookup"><span data-stu-id="cfdde-293">404</span></span>               | <span data-ttu-id="cfdde-294">Non trovato</span><span class="sxs-lookup"><span data-stu-id="cfdde-294">Not found</span></span>                         |
| <span data-ttu-id="cfdde-295">302</span><span class="sxs-lookup"><span data-stu-id="cfdde-295">302</span></span>               | <span data-ttu-id="cfdde-296">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="cfdde-296">Redirect</span></span>                          |
| <span data-ttu-id="cfdde-297">401</span><span class="sxs-lookup"><span data-stu-id="cfdde-297">401</span></span>               | <span data-ttu-id="cfdde-298">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cfdde-298">Authorization Failed</span></span>              |
| <span data-ttu-id="cfdde-299">403</span><span class="sxs-lookup"><span data-stu-id="cfdde-299">403</span></span>               | <span data-ttu-id="cfdde-300">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cfdde-300">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="cfdde-301">Ottenere un evento in base all'ID</span><span class="sxs-lookup"><span data-stu-id="cfdde-301">Get an event by ID</span></span>

| <span data-ttu-id="cfdde-302">Metodo</span><span class="sxs-lookup"><span data-stu-id="cfdde-302">Method</span></span>         | <span data-ttu-id="cfdde-303">GET</span><span class="sxs-lookup"><span data-stu-id="cfdde-303">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="cfdde-304">URL</span><span class="sxs-lookup"><span data-stu-id="cfdde-304">URL</span></span>            | <span data-ttu-id="cfdde-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="cfdde-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="cfdde-306">Intestazione</span><span class="sxs-lookup"><span data-stu-id="cfdde-306">Header</span></span>         | <span data-ttu-id="cfdde-307">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cfdde-307">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="cfdde-308">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="cfdde-308">application/atom+xml</span></span> |
| <span data-ttu-id="cfdde-309">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="cfdde-309">Authentication</span></span> | <span data-ttu-id="cfdde-310">Di base</span><span class="sxs-lookup"><span data-stu-id="cfdde-310">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="cfdde-311">Nome utente</span><span class="sxs-lookup"><span data-stu-id="cfdde-311">Username</span></span>       | <span data-ttu-id="cfdde-312">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="cfdde-312">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="cfdde-313">Password</span><span class="sxs-lookup"><span data-stu-id="cfdde-313">Password</span></span>       | <span data-ttu-id="cfdde-314">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="cfdde-314">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="cfdde-315">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="cfdde-315">Response codes</span></span>

| <span data-ttu-id="cfdde-316">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="cfdde-316">**Response Code**</span></span> | <span data-ttu-id="cfdde-317">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cfdde-317">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="cfdde-318">200</span><span class="sxs-lookup"><span data-stu-id="cfdde-318">200</span></span>               | <span data-ttu-id="cfdde-319">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="cfdde-319">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="cfdde-320">404</span><span class="sxs-lookup"><span data-stu-id="cfdde-320">404</span></span>               | <span data-ttu-id="cfdde-321">Non trovato</span><span class="sxs-lookup"><span data-stu-id="cfdde-321">Not found</span></span>                                            |
| <span data-ttu-id="cfdde-322">302</span><span class="sxs-lookup"><span data-stu-id="cfdde-322">302</span></span>               | <span data-ttu-id="cfdde-323">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="cfdde-323">Redirect</span></span>                                             |
| <span data-ttu-id="cfdde-324">401</span><span class="sxs-lookup"><span data-stu-id="cfdde-324">401</span></span>               | <span data-ttu-id="cfdde-325">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cfdde-325">Authorization Failed</span></span>                                 |
| <span data-ttu-id="cfdde-326">403</span><span class="sxs-lookup"><span data-stu-id="cfdde-326">403</span></span>               | <span data-ttu-id="cfdde-327">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cfdde-327">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="cfdde-328">Ottenere un evento in base al nome</span><span class="sxs-lookup"><span data-stu-id="cfdde-328">Get an event by name</span></span>

| <span data-ttu-id="cfdde-329">Metodo</span><span class="sxs-lookup"><span data-stu-id="cfdde-329">Method</span></span>         | <span data-ttu-id="cfdde-330">GET</span><span class="sxs-lookup"><span data-stu-id="cfdde-330">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="cfdde-331">URL</span><span class="sxs-lookup"><span data-stu-id="cfdde-331">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="cfdde-332">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="cfdde-332">Headers</span></span>        | <span data-ttu-id="cfdde-333">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cfdde-333">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="cfdde-334">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="cfdde-334">application/atom+xml</span></span> |
| <span data-ttu-id="cfdde-335">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="cfdde-335">Authentication</span></span> | <span data-ttu-id="cfdde-336">Di base</span><span class="sxs-lookup"><span data-stu-id="cfdde-336">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="cfdde-337">Nome utente</span><span class="sxs-lookup"><span data-stu-id="cfdde-337">Username</span></span>       | <span data-ttu-id="cfdde-338">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="cfdde-338">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="cfdde-339">Password</span><span class="sxs-lookup"><span data-stu-id="cfdde-339">Password</span></span>       | <span data-ttu-id="cfdde-340">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="cfdde-340">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="cfdde-341">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="cfdde-341">Response codes</span></span>

| <span data-ttu-id="cfdde-342">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="cfdde-342">**Response Code**</span></span> | <span data-ttu-id="cfdde-343">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cfdde-343">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="cfdde-344">200</span><span class="sxs-lookup"><span data-stu-id="cfdde-344">200</span></span>               | <span data-ttu-id="cfdde-345">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="cfdde-345">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="cfdde-346">404</span><span class="sxs-lookup"><span data-stu-id="cfdde-346">404</span></span>               | <span data-ttu-id="cfdde-347">Non trovato</span><span class="sxs-lookup"><span data-stu-id="cfdde-347">Not found</span></span>                                            |
| <span data-ttu-id="cfdde-348">302</span><span class="sxs-lookup"><span data-stu-id="cfdde-348">302</span></span>               | <span data-ttu-id="cfdde-349">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="cfdde-349">Redirect</span></span>                                             |
| <span data-ttu-id="cfdde-350">401</span><span class="sxs-lookup"><span data-stu-id="cfdde-350">401</span></span>               | <span data-ttu-id="cfdde-351">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cfdde-351">Authorization Failed</span></span>                                 |
| <span data-ttu-id="cfdde-352">403</span><span class="sxs-lookup"><span data-stu-id="cfdde-352">403</span></span>               | <span data-ttu-id="cfdde-353">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="cfdde-353">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="cfdde-354">Uso di PowerShell (versione 6 o successiva) o un client HTTP</span><span class="sxs-lookup"><span data-stu-id="cfdde-354">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="cfdde-355">Passaggio 1: Connettersi a PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfdde-355">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="cfdde-356">Passaggio 2: Eseguire lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="cfdde-356">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfdde-357">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="cfdde-357">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="cfdde-358">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="cfdde-358">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="cfdde-359">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="cfdde-359">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="cfdde-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="cfdde-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="cfdde-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="cfdde-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="cfdde-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="cfdde-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="cfdde-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="cfdde-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="cfdde-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="cfdde-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="cfdde-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="cfdde-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="cfdde-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="cfdde-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="cfdde-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="cfdde-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="cfdde-370">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-370">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="cfdde-371">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-371">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="cfdde-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="cfdde-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="cfdde-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="cfdde-375">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-375">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="cfdde-376">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="cfdde-376">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="cfdde-377">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="cfdde-377">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="cfdde-378">$event = $null</span><span class="sxs-lookup"><span data-stu-id="cfdde-378">$event = $null</span></span></p>
<p><span data-ttu-id="cfdde-379">try</span><span class="sxs-lookup"><span data-stu-id="cfdde-379">try</span></span></p>
<p><span data-ttu-id="cfdde-380">{</span><span class="sxs-lookup"><span data-stu-id="cfdde-380">{</span></span></p>
<p><span data-ttu-id="cfdde-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="cfdde-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="cfdde-382">}</span><span class="sxs-lookup"><span data-stu-id="cfdde-382">}</span></span></p>
<p><span data-ttu-id="cfdde-383">catch</span><span class="sxs-lookup"><span data-stu-id="cfdde-383">catch</span></span></p>
<p><span data-ttu-id="cfdde-384">{</span><span class="sxs-lookup"><span data-stu-id="cfdde-384">{</span></span></p>
<p><span data-ttu-id="cfdde-385">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="cfdde-385">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="cfdde-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="cfdde-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="cfdde-387">{</span><span class="sxs-lookup"><span data-stu-id="cfdde-387">{</span></span></p>
<p><span data-ttu-id="cfdde-388">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="cfdde-388">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="cfdde-389">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="cfdde-389">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="cfdde-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="cfdde-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="cfdde-391">}</span><span class="sxs-lookup"><span data-stu-id="cfdde-391">}</span></span></p>
<p><span data-ttu-id="cfdde-392">}</span><span class="sxs-lookup"><span data-stu-id="cfdde-392">}</span></span></p>
<p><span data-ttu-id="cfdde-393">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="cfdde-393">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="cfdde-394">Verificare il risultato in entrambe le opzioni</span><span class="sxs-lookup"><span data-stu-id="cfdde-394">Verify the outcome in both options</span></span>

<span data-ttu-id="cfdde-395">Passaggio 1: Passare al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="cfdde-395">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="cfdde-396">Passaggio 2: Scegliere **Eventi** in **Governance delle informazioni**.</span><span class="sxs-lookup"><span data-stu-id="cfdde-396">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="cfdde-397">Passaggio 3: Verificare di aver creato l'evento.</span><span class="sxs-lookup"><span data-stu-id="cfdde-397">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="cfdde-398">È possibile usare le opzioni precedenti per automatizzare la conservazione basata sugli eventi anche per gli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="cfdde-398">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="cfdde-399">Scenario 2: Contratti in scadenza</span><span class="sxs-lookup"><span data-stu-id="cfdde-399">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="cfdde-400">Un'organizzazione può avere più record per un singolo contratto con clienti, fornitori e partner.</span><span class="sxs-lookup"><span data-stu-id="cfdde-400">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="cfdde-401">Questi documenti possono trovarsi in una raccolta documenti come SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfdde-401">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="cfdde-402">Il termine di un contratto determina l'inizio del periodo di conservazione dei documenti associati al contratto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-402">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="cfdde-403">Ad esempio, tutti i record relativi ai contratti devono essere conservati per cinque anni dalla data di scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-403">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="cfdde-404">L'evento che attiva il periodo di conservazione di cinque anni è la scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-404">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="cfdde-405">Un sistema di Customer Relationship Management (CRM) può interagire con Microsoft 365 per attivare la conservazione dei documenti contrattuali</span><span class="sxs-lookup"><span data-stu-id="cfdde-405">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="cfdde-406">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="cfdde-406">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e attività per scenari di scadenza contratto](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="cfdde-408">L'amministratore crea una raccolta di SharePoint con varie cartelle per ogni tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-408">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="cfdde-409">L'amministratore aggiunge i documenti contrattuali, ad esempio Contratti di licenza e Contratti di sviluppo, a ogni cartella di contratto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-409">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="cfdde-410">L'amministratore assegna l'ID risorsa a ogni cartella di contratto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-410">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="cfdde-411">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="cfdde-411">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="cfdde-412">L'amministratore SCC crea tipi di eventi correlati al contratto, come "Creazione contratto" o "Scadenza contratto".</span><span class="sxs-lookup"><span data-stu-id="cfdde-412">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="cfdde-413">L'amministratore SCC crea l'etichetta "Scadenza contratto".</span><span class="sxs-lookup"><span data-stu-id="cfdde-413">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="cfdde-414">L'etichetta "Scadenza contratto" viene pubblicata e applicata manualmente o automaticamente ai documenti contrattuali in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfdde-414">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="cfdde-415">Il sistema di gestione dei contratti può eseguire periodicamente Microsoft Flow o un'applicazione simile per gestire i documenti contrattuali.</span><span class="sxs-lookup"><span data-stu-id="cfdde-415">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="cfdde-416">Se un contratto scade, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="cfdde-416">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="cfdde-417">Scenario 3: Fine produzione</span><span class="sxs-lookup"><span data-stu-id="cfdde-417">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="cfdde-p124">Un'impresa che produce diverse linee di prodotti crea molte specifiche di produzione e tariffari. Quando il prodotto esce fuori produzione, tutte le specifiche e i documenti a esso collegati devono essere conservati per un determinato periodo di tempo dopo la fine del ciclo di vita del prodotto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="cfdde-420">Un sistema ERP (Enterprise Resource Planning) può utilizzare Microsoft 365 e Microsoft Flow per attivare la conservazione.</span><span class="sxs-lookup"><span data-stu-id="cfdde-420">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="cfdde-421">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="cfdde-421">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e attività per uno scenario di ciclo di vita del prodotto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="cfdde-423">L'amministratore crea delle cartelle di prodotto nel set di documenti, ad esempio Prodotto 1, Prodotto 2, ecc.</span><span class="sxs-lookup"><span data-stu-id="cfdde-423">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="cfdde-424">L'amministratore aggiunge i documenti del prodotto, ad esempio Specifiche di produzione, Prezzi del prodotto, Licenze del prodotto a ogni cartella.</span><span class="sxs-lookup"><span data-stu-id="cfdde-424">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="cfdde-425">L'amministratore assegna l'ID risorsa a ogni cartella di prodotto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-425">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="cfdde-426">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="cfdde-426">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="cfdde-427">L'amministratore SCC crea tipi di eventi correlati al prodotto, come "Inizio produzione", "Fine produzione".</span><span class="sxs-lookup"><span data-stu-id="cfdde-427">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="cfdde-428">L'amministratore SCC crea l'etichetta "Fine produzione".</span><span class="sxs-lookup"><span data-stu-id="cfdde-428">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="cfdde-429">L'etichetta "Fine produzione" viene pubblicata e applicata manualmente o automaticamente ai documenti del prodotto in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfdde-429">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="cfdde-430">I sistemi ERP possono eseguire periodicamente Microsoft Flow o applicazioni simili per gestire i documenti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="cfdde-430">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="cfdde-431">Se un prodotto esce fuori produzione, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="cfdde-431">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="cfdde-432">Appendice</span><span class="sxs-lookup"><span data-stu-id="cfdde-432">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="cfdde-433">Uso dei risultati della risposta Redirect 302 per chiamare l'API REST</span><span class="sxs-lookup"><span data-stu-id="cfdde-433">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="cfdde-434">Chiamare un evento di conservazione POST usando l'URL dell'API REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (sono necessarie le autorizzazioni di amministratore globale)</span><span class="sxs-lookup"><span data-stu-id="cfdde-434">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="cfdde-p125">Controllare il codice di risposta. Se è 302, ottenere l'URL reindirizzato dalla proprietà Posizione dell'intestazione della risposta</span><span class="sxs-lookup"><span data-stu-id="cfdde-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="cfdde-437">Chiamare nuovamente l'evento di conservazione POST usando l'URL reindirizzato.</span><span class="sxs-lookup"><span data-stu-id="cfdde-437">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="cfdde-438">Riconoscimenti</span><span class="sxs-lookup"><span data-stu-id="cfdde-438">Credits</span></span>

<span data-ttu-id="cfdde-439">Questo argomento è stato rivisto da:</span><span class="sxs-lookup"><span data-stu-id="cfdde-439">This topic was reviewed by:</span></span>

<span data-ttu-id="cfdde-440">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="cfdde-440">Antonio Maio</span></span><br/><span data-ttu-id="cfdde-441">MVP App e servizi di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="cfdde-441">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="cfdde-442">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="cfdde-442">Antonio.Maio@Protiviti.com</span></span>
