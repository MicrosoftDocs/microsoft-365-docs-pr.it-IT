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
ms.openlocfilehash: 0b2507497bfd90b892e95934a03f795045c9bac2
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105653"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="85bc5-103">Automatizzare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="85bc5-103">Automate event-based retention</span></span>

><span data-ttu-id="85bc5-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="85bc5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="85bc5-p101">L'esplosione del contenuto nelle organizzazioni e il modo in cui può diventare ROT (redundant, obsolete, trivial, cioè ridondante, obsoleto e banale), è una cosa seria. Per continuare a soddisfare gli obblighi di conformità normativa, legale e finanziaria, le organizzazioni devono poter conservare e proteggere le informazioni importanti e trovare rapidamente ciò che conta. Conservare solo informazioni importanti e pertinenti è fondamentale per il successo di un’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="85bc5-p102">Per riuscirci, le organizzazioni possono sfruttare le soluzioni di conservazione nel Centro sicurezza e conformità di Office 365. La conservazione può essere attivata usando [etichette di conservazione](labels.md), che consentono di [basare il periodo di conservazione su un evento specifico](event-driven-retention.md). In genere, il periodo di conservazione si basa su una data nota, come la data di creazione o dell'ultima modifica del contenuto. Tuttavia, le organizzazioni fanno fronte anche a requisiti di smaltimento dei contenuti in base al verificarsi di un evento, ad esempio sette anni dopo che un dipendente ha lasciato l’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="85bc5-p103">Per garantire lo smaltimento conforme del contenuto, è fondamentale conoscere la data in cui si verifica un evento. Con il rapido aumento del volume di contenuti, diventa sempre più difficile conservare e smaltire i contenuti in maniera puntuale e conforme.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="85bc5-p104">La conservazione basata sugli eventi è la soluzione a questo problema. Questo argomento illustra come configurare i flussi di processo aziendale in modo da automatizzare la conservazione attraverso gli eventi usando l'API REST di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="85bc5-117">Informazioni sulla conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="85bc5-117">About event-based retention</span></span>

<span data-ttu-id="85bc5-p105">Un'organizzazione può avere dimensioni piccole, medie o grandi. Il numero di documenti aziendali e legali, dossier del personale, contratti e documenti sul prodotto che vengono creati e gestiti su base quotidiana è in drastico aumento.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="85bc5-p106">Ad esempio, ogni giorno decine o centinaia di dipendenti entrano a far parte delle organizzazioni o le lasciano. Il reparto Risorse umane continua a creare, aggiornare o eliminare i documenti relativi ai dipendenti in base ai requisiti aziendali. Questo processo è soggetto ai diversi criteri di conservazione indicati per l'azienda:</span><span class="sxs-lookup"><span data-stu-id="85bc5-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="85bc5-p107">**Il periodo di conservazione del contenuto può essere una data nota**, ad esempio la data di creazione, dell'ultima modifica o dell'assegnazione di un'etichetta al contenuto. Ad esempio, si potrebbero conservare documenti per sette anni dalla creazione per poi eliminarli.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="85bc5-p108">**Il periodo di conservazione del contenuto può essere anche una data sconosciuta**. Ad esempio, con le etichette di conservazione è anche possibile basare anche un periodo di conservazione sul momento in cui si verifica un determinato tipo di evento, ad esempio quando un dipendente lascia l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="85bc5-p109">L'evento fa scattare l'inizio del periodo di conservazione e tutto il contenuto con un'etichetta applicata per quel tipo di evento riceve le azioni di conservazione dell'etichetta applicate su di esso. È ciò che si intende con conservazione basata sugli eventi. Per altre informazioni, vedere [Panoramica della conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="85bc5-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="85bc5-130">Configurare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="85bc5-130">Set up event-based retention</span></span>

<span data-ttu-id="85bc5-131">Questa sezione descrive le operazioni da eseguire prima della conservazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="85bc5-132">Identificare i ruoli</span><span class="sxs-lookup"><span data-stu-id="85bc5-132">Identify roles</span></span>

<span data-ttu-id="85bc5-133">Identificare i diversi ruoli in un'organizzazione che eseguono attività di Gestione record e che sarebbero i responsabili della conservazione efficace ed efficiente dei documenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="85bc5-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="85bc5-134">**Persona**</span><span class="sxs-lookup"><span data-stu-id="85bc5-134">**Persona**</span></span>| <span data-ttu-id="85bc5-135">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="85bc5-135">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="85bc5-136">Amministratore</span><span class="sxs-lookup"><span data-stu-id="85bc5-136">Admin</span></span> | <span data-ttu-id="85bc5-137">Crea tipi di eventi di conservazione, etichette di conservazione e repository dei record in SharePoint</span><span class="sxs-lookup"><span data-stu-id="85bc5-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="85bc5-138">Responsabile della gestione dei record</span><span class="sxs-lookup"><span data-stu-id="85bc5-138">Records Manager</span></span>                                  | <span data-ttu-id="85bc5-139">Fornisce linee guida su criteri di conservazione e pianificazioni della conservazione, oltre a informazioni dettagliate sulla conformità</span><span class="sxs-lookup"><span data-stu-id="85bc5-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="85bc5-140">Amministratore di sistema (azienda)</span><span class="sxs-lookup"><span data-stu-id="85bc5-140">System Admin (business)</span></span>                          | <span data-ttu-id="85bc5-141">Configura e gestisce i sistemi esterni in modo da utilizzare Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85bc5-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="85bc5-142">Information Worker</span><span class="sxs-lookup"><span data-stu-id="85bc5-142">Information Worker</span></span>                               | <span data-ttu-id="85bc5-143">Gestisce il ciclo di vita del proprio processo aziendale (risorse umane, finanza, IT ecc.)</span><span class="sxs-lookup"><span data-stu-id="85bc5-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="85bc5-144">Configurare il Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="85bc5-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="85bc5-145">L'amministratore di conformità crea un tipo di evento, &ndash;ad esempio Licenziamento dipendente, Scadenza contratto oppure Fine produzione.</span><span class="sxs-lookup"><span data-stu-id="85bc5-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="85bc5-146">Vedere il processo dettagliato in [Conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="85bc5-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="85bc5-147">L'amministratore di conformità crea un'etichetta di conservazione in base a un evento e la associa a un tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="85bc5-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="85bc5-148">Ci sono quattro tipi di trigger per le etichette di conservazione:</span><span class="sxs-lookup"><span data-stu-id="85bc5-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="85bc5-149">Data creazione</span><span class="sxs-lookup"><span data-stu-id="85bc5-149">Create date</span></span>
                
    2. <span data-ttu-id="85bc5-150">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="85bc5-150">Last modified</span></span>
                
    3. <span data-ttu-id="85bc5-151">Data etichetta (quando il contenuto è stato etichettato)</span><span class="sxs-lookup"><span data-stu-id="85bc5-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="85bc5-152">Basata su eventi</span><span class="sxs-lookup"><span data-stu-id="85bc5-152">Event-based</span></span>
    
3. <span data-ttu-id="85bc5-153">L'amministratore di conformità pubblica l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="85bc5-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="85bc5-154">Configurare SharePoint</span><span class="sxs-lookup"><span data-stu-id="85bc5-154">Set up SharePoint</span></span>
   
<span data-ttu-id="85bc5-155">Per creare un repository dei record, l'amministratore di conformità deve:</span><span class="sxs-lookup"><span data-stu-id="85bc5-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="85bc5-156">Creare un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="85bc5-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="85bc5-157">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85bc5-157">Does one of the following:</span></span>
        
    - <span data-ttu-id="85bc5-p111">Creare una raccolta di SharePoint: configurare un'etichetta basata su eventi a livello di raccolta. Per altre informazioni, vedere [Applicazione di un'etichetta di conservazione predefinita a tutto il contenuto in una raccolta, una cartella o un set di documenti di SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="85bc5-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="85bc5-160">Configura un set di documenti in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="85bc5-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="85bc5-161">Per ulteriori informazioni, vedere [Introduzione ai set di documenti](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="85bc5-161">For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="85bc5-162">Assegna un ID risorsa a ogni set di documenti dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="85bc5-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="85bc5-163">Un ID risorsa è il nome o codice di un prodotto usato dall'organizzazione, ad esempio il Numero dipendente può essere un ID risorsa.</span><span class="sxs-lookup"><span data-stu-id="85bc5-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="85bc5-164">Assegnando l'ID risorsa alla cartella, ogni elemento nella cartella eredita automaticamente lo stesso ID risorsa.</span><span class="sxs-lookup"><span data-stu-id="85bc5-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="85bc5-165">Di conseguenza, il periodo di conservazione di tutti gli elementi nella cartella sarà generato dallo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="85bc5-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="85bc5-166">Modi per attivare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="85bc5-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="85bc5-167">Esistono due modi in cui è possibile attivare la conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="85bc5-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="85bc5-168">**Uso dell'interfaccia di amministrazione** Si tratta di un processo che può essere sfruttato per conservare meno contenuto alla volta o per ridurre la frequenza di attivazione della conservazione e renderla, ad esempio, mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="85bc5-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="85bc5-169">Per ulteriori informazioni su questo processo, vedere [Panoramica della conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="85bc5-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="85bc5-170">Tuttavia, questo metodo di attivazione della conservazione può richiedere tempo e causare errori, e diminuire così la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="85bc5-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="85bc5-171">Di conseguenza, una soluzione automatica e semplice per attivare la conservazione può aumentare la sicurezza e la conformità dei dati.</span><span class="sxs-lookup"><span data-stu-id="85bc5-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="85bc5-p115">**Con l'API REST di M365**: questo processo è utile quando occorre conservare grandi quantità di contenuto contemporaneamente e/o la frequenza di attivazione della conservazione è alta, ad esempio giornaliera o settimanale. Il flusso rileva il verificarsi di un evento nel sistema line-of-business e crea automaticamente un evento correlato nel Centro di sicurezza e conformità. Non è necessario creare manualmente un evento nell'interfaccia ogni volta che se ne verifica uno.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="85bc5-175">Sono disponibili due opzioni per usare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="85bc5-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="85bc5-176">**Microsoft Flow o delle applicazioni simili** possono essere usate per attivare automaticamente la ricorrenza di un evento.</span><span class="sxs-lookup"><span data-stu-id="85bc5-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="85bc5-177">Microsoft Flow è un agente di orchestrazione per la connessione ad altri sistemi.</span><span class="sxs-lookup"><span data-stu-id="85bc5-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="85bc5-178">L'uso di Microsoft Flow non richiede una soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="85bc5-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="85bc5-179">**PowerShell o un client HTTP per le chiamate all'API REST**: usare PowerShell (versione 6 o successive) per chiamare l'API REST di Microsoft 365 per creare eventi.</span><span class="sxs-lookup"><span data-stu-id="85bc5-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="85bc5-180">Un'API Rest è un endpoint di servizio che supporta set di operazioni HTTP (metodi), che forniscono l'accesso alle risorse del servizio per la creazione, il ripristino, l’aggiornamento e l’eliminazione.</span><span class="sxs-lookup"><span data-stu-id="85bc5-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="85bc5-181">Per altre informazioni, vedere [Componenti di una richiesta/risposta dell'API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="85bc5-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="85bc5-182">In questo caso, con l'API REST di Microsoft 365, è possibile creare e recuperare gli eventi usando le operazioni (metodi) POST e GET.</span><span class="sxs-lookup"><span data-stu-id="85bc5-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="85bc5-183">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="85bc5-183">Example scenarios</span></span>

<span data-ttu-id="85bc5-184">Considerare i seguenti scenari.</span><span class="sxs-lookup"><span data-stu-id="85bc5-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="85bc5-185">Scenario 1: Dipendenti che lasciano l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="85bc5-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="85bc5-186">Un’organizzazione crea e archivia numerosi documenti relativi all’impiego di ogni singolo dipendente.</span><span class="sxs-lookup"><span data-stu-id="85bc5-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="85bc5-187">Questi documenti sono gestiti e conservati durante il periodo di lavoro di ogni dipendente.</span><span class="sxs-lookup"><span data-stu-id="85bc5-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="85bc5-188">Tuttavia, quando il dipendente lascia l'organizzazione o quando termina il periodo di lavoro, l'organizzazione è tenuta a rispettare i requisiti legali e aziendali e a mantenere i documenti di tale dipendente per un lasso di tempo concordato.</span><span class="sxs-lookup"><span data-stu-id="85bc5-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="85bc5-189">Quindi, se più dipendenti lasciassero l'organizzazione ogni giorno, l'organizzazione dovrebbe attivare quotidianamente l'intervallo di conservazione per centinaia o migliaia di documenti.</span><span class="sxs-lookup"><span data-stu-id="85bc5-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="85bc5-190">Oltre a tutto questo, occorre calcolare il periodo di conservazione per ciascun dipendente in base alla formula Data licenziamento dipendente + numero di giorni, mesi o anni in base al tipo di record del dipendente.</span><span class="sxs-lookup"><span data-stu-id="85bc5-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="85bc5-191">Ad esempio, il periodo di conservazione dei documenti relativi alla retribuzione del lavoratore e ai benefit dipendenti potrebbe differire.</span><span class="sxs-lookup"><span data-stu-id="85bc5-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="85bc5-192">Il diagramma di seguito illustra come possano essere presenti più etichette associate a un singolo evento.</span><span class="sxs-lookup"><span data-stu-id="85bc5-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="85bc5-193">In questo caso, tutti i file con l’etichetta Assicurazione contro gli infortuni sul lavoro e tutti i file con l’etichetta Benefit dipendenti sono associati a un singolo evento, ossia il licenziamento del dipendente dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85bc5-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="85bc5-194">Ognuno dei vari file ha intervalli di conservazione diversi.</span><span class="sxs-lookup"><span data-stu-id="85bc5-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="85bc5-195">Quindi, quando un dipendente lascia l'organizzazione, i file raggruppati sotto ogni etichetta hanno un periodo di conservazione diverso.</span><span class="sxs-lookup"><span data-stu-id="85bc5-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="85bc5-196">L'attivazione di tutti questi intervalli di conservazione, diversi per ogni tipo di file o etichetta e per ogni dipendente, è un'operazione molto complessa.</span><span class="sxs-lookup"><span data-stu-id="85bc5-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="85bc5-197">Ancora di più lo è eseguire questa operazione per più dipendenti.</span><span class="sxs-lookup"><span data-stu-id="85bc5-197">Imagine doing this for multiple employees.</span></span>

![Diagramma del tipo di evento, evento ed etichette](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="85bc5-199">Di conseguenza, un processo automatizzato per attivare i diversi intervalli di conservazione per più dipendenti consente di risparmiare tempo, è privo di errori ed estremamente efficiente.</span><span class="sxs-lookup"><span data-stu-id="85bc5-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="85bc5-200">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="85bc5-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e azioni per lo scenario in cui il dipendente lascia l'organizzazione](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="85bc5-202">L'amministratore crea le cartelle del dipendente nel set di documenti, ad esempio Angela Barbariol, Luca Udinesi.</span><span class="sxs-lookup"><span data-stu-id="85bc5-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="85bc5-203">L'amministratore aggiunge i documenti dei dipendenti, ad esempio Benefit, Paghe, Assicurazione contro gli infortuni sul lavoro, a ogni cartella dipendente.</span><span class="sxs-lookup"><span data-stu-id="85bc5-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="85bc5-204">L'amministratore assegna l'ID risorsa a ogni cartella dipendente.</span><span class="sxs-lookup"><span data-stu-id="85bc5-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="85bc5-205">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="85bc5-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="85bc5-206">L'amministratore SCC crea tipi di eventi correlati al dipendente, come "Licenziamento del dipendente", "Assunzione del dipendente".</span><span class="sxs-lookup"><span data-stu-id="85bc5-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="85bc5-207">L'amministratore SCC crea l'etichetta "Conservazione dipendente".</span><span class="sxs-lookup"><span data-stu-id="85bc5-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="85bc5-208">L'etichetta "Conservazione dipendente" viene pubblicata e applicata manualmente o automaticamente ai documenti dei dipendenti in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="85bc5-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="85bc5-209">Un sistema di gestione delle risorse umane come Workday può eseguire periodicamente Microsoft Flow per gestire i documenti dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="85bc5-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="85bc5-210">Se un dipendente ha lasciato l'organizzazione, Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del dipendente specifico.</span><span class="sxs-lookup"><span data-stu-id="85bc5-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="85bc5-211">Uso di Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="85bc5-211">Using Microsoft Flow</span></span>

<span data-ttu-id="85bc5-212">Passaggio 1: Creare un flusso per creare un evento usando le API REST di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85bc5-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usare Flow per creare un evento](../media/automate-event-driven-retention-flow-1.png)

![Usare Flow per chiamare l'API REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="85bc5-215">Creare un evento</span><span class="sxs-lookup"><span data-stu-id="85bc5-215">Create an event</span></span>

<span data-ttu-id="85bc5-216">Codice di esempio per chiamare l'API REST</span><span class="sxs-lookup"><span data-stu-id="85bc5-216">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="85bc5-217">Metodo</span><span class="sxs-lookup"><span data-stu-id="85bc5-217">Method</span></span></th>
<th><span data-ttu-id="85bc5-218">POST</span><span class="sxs-lookup"><span data-stu-id="85bc5-218">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="85bc5-219">URL</span><span class="sxs-lookup"><span data-stu-id="85bc5-219">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="85bc5-220">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="85bc5-220">Headers</span></span></td>
<td><span data-ttu-id="85bc5-221">Content-Type</span><span class="sxs-lookup"><span data-stu-id="85bc5-221">Content-Type</span></span></td>
<td><span data-ttu-id="85bc5-222">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="85bc5-222">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="85bc5-223">Corpo</span><span class="sxs-lookup"><span data-stu-id="85bc5-223">Body</span></span></td>
<td><p><span data-ttu-id="85bc5-224">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-224">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="85bc5-225">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="85bc5-225">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="85bc5-226">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="85bc5-226">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="85bc5-227">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-227">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="85bc5-228">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-228">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="85bc5-229">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-229">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="85bc5-230">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-230">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="85bc5-231">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-231">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="85bc5-232">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-232">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="85bc5-233">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-233">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="85bc5-234">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-234">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="85bc5-235">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-235">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="85bc5-236">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-236">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="85bc5-237">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-237">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="85bc5-238">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-238">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="85bc5-239">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="85bc5-239">Authentication</span></span></td>
<td><span data-ttu-id="85bc5-240">Di base</span><span class="sxs-lookup"><span data-stu-id="85bc5-240">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="85bc5-241">Nome utente</span><span class="sxs-lookup"><span data-stu-id="85bc5-241">Username</span></span></td>
<td><span data-ttu-id="85bc5-242">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="85bc5-242">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="85bc5-243">Password</span><span class="sxs-lookup"><span data-stu-id="85bc5-243">Password</span></span></td>
<td><span data-ttu-id="85bc5-244">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="85bc5-244">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="85bc5-245">Parametri disponibili</span><span class="sxs-lookup"><span data-stu-id="85bc5-245">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="85bc5-246"><strong>Parametri</strong></span><span class="sxs-lookup"><span data-stu-id="85bc5-246"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="85bc5-247"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="85bc5-247"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="85bc5-248"><strong>Note</strong></span><span class="sxs-lookup"><span data-stu-id="85bc5-248"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="85bc5-249">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-249">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="85bc5-250">Immettere un nome univoco per l'evento,</span><span class="sxs-lookup"><span data-stu-id="85bc5-250">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="85bc5-p121">Non può contenere spazi e i caratteri seguenti: % \* \ &amp; &lt; &gt; | # ? , : ,</span><span class="sxs-lookup"><span data-stu-id="85bc5-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="85bc5-253">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-253">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="85bc5-254">Immettere il nome del tipo di evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="85bc5-254">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="85bc5-p122">Esempio: "Licenziamento dipendente". Il tipo di evento deve essere associato a un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="85bc5-257">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-257">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="85bc5-258">Immettere "ComplianceAssetId:" + ID dipendente</span><span class="sxs-lookup"><span data-stu-id="85bc5-258">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="85bc5-259">Esempio:&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="85bc5-259">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="85bc5-260">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-260">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="85bc5-261">Data e ora evento</span><span class="sxs-lookup"><span data-stu-id="85bc5-261">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="85bc5-262">Formato: aaaa-MM-ggTHH:mm:ssZ, esempio:</span><span class="sxs-lookup"><span data-stu-id="85bc5-262">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="85bc5-263">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="85bc5-263">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="85bc5-264">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="85bc5-264">Response codes</span></span>

| <span data-ttu-id="85bc5-265">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="85bc5-265">**Response Code**</span></span> | <span data-ttu-id="85bc5-266">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="85bc5-266">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="85bc5-267">302</span><span class="sxs-lookup"><span data-stu-id="85bc5-267">302</span></span>               | <span data-ttu-id="85bc5-268">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="85bc5-268">Redirect</span></span>              |
| <span data-ttu-id="85bc5-269">201</span><span class="sxs-lookup"><span data-stu-id="85bc5-269">201</span></span>               | <span data-ttu-id="85bc5-270">Creato</span><span class="sxs-lookup"><span data-stu-id="85bc5-270">Created</span></span>               |
| <span data-ttu-id="85bc5-271">403</span><span class="sxs-lookup"><span data-stu-id="85bc5-271">403</span></span>               | <span data-ttu-id="85bc5-272">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="85bc5-272">Authorization Failed</span></span>  |
| <span data-ttu-id="85bc5-273">401</span><span class="sxs-lookup"><span data-stu-id="85bc5-273">401</span></span>               | <span data-ttu-id="85bc5-274">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="85bc5-274">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="85bc5-275">Ricevere gli eventi in base all'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="85bc5-275">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="85bc5-276">Metodo</span><span class="sxs-lookup"><span data-stu-id="85bc5-276">Method</span></span></th>
<th><span data-ttu-id="85bc5-277">GET</span><span class="sxs-lookup"><span data-stu-id="85bc5-277">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="85bc5-278">URL</span><span class="sxs-lookup"><span data-stu-id="85bc5-278">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="85bc5-279">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="85bc5-279">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="85bc5-280">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="85bc5-280">Headers</span></span></td>
<td><span data-ttu-id="85bc5-281">Content-Type</span><span class="sxs-lookup"><span data-stu-id="85bc5-281">Content-Type</span></span></td>
<td><span data-ttu-id="85bc5-282">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="85bc5-282">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="85bc5-283">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="85bc5-283">Authentication</span></span></td>
<td><span data-ttu-id="85bc5-284">Di base</span><span class="sxs-lookup"><span data-stu-id="85bc5-284">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="85bc5-285">Nome utente</span><span class="sxs-lookup"><span data-stu-id="85bc5-285">Username</span></span></td>
<td><span data-ttu-id="85bc5-286">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="85bc5-286">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="85bc5-287">Password</span><span class="sxs-lookup"><span data-stu-id="85bc5-287">Password</span></span></td>
<td><span data-ttu-id="85bc5-288">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="85bc5-288">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="85bc5-289">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="85bc5-289">Response codes</span></span>

| <span data-ttu-id="85bc5-290">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="85bc5-290">**Response Code**</span></span> | <span data-ttu-id="85bc5-291">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="85bc5-291">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="85bc5-292">200</span><span class="sxs-lookup"><span data-stu-id="85bc5-292">200</span></span>               | <span data-ttu-id="85bc5-293">OK, un elenco di eventi in atom+ xml</span><span class="sxs-lookup"><span data-stu-id="85bc5-293">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="85bc5-294">404</span><span class="sxs-lookup"><span data-stu-id="85bc5-294">404</span></span>               | <span data-ttu-id="85bc5-295">Non trovato</span><span class="sxs-lookup"><span data-stu-id="85bc5-295">Not found</span></span>                         |
| <span data-ttu-id="85bc5-296">302</span><span class="sxs-lookup"><span data-stu-id="85bc5-296">302</span></span>               | <span data-ttu-id="85bc5-297">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="85bc5-297">Redirect</span></span>                          |
| <span data-ttu-id="85bc5-298">401</span><span class="sxs-lookup"><span data-stu-id="85bc5-298">401</span></span>               | <span data-ttu-id="85bc5-299">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="85bc5-299">Authorization Failed</span></span>              |
| <span data-ttu-id="85bc5-300">403</span><span class="sxs-lookup"><span data-stu-id="85bc5-300">403</span></span>               | <span data-ttu-id="85bc5-301">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="85bc5-301">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="85bc5-302">Ottenere un evento in base all'ID</span><span class="sxs-lookup"><span data-stu-id="85bc5-302">Get an event by ID</span></span>

| <span data-ttu-id="85bc5-303">Metodo</span><span class="sxs-lookup"><span data-stu-id="85bc5-303">Method</span></span>         | <span data-ttu-id="85bc5-304">GET</span><span class="sxs-lookup"><span data-stu-id="85bc5-304">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="85bc5-305">URL</span><span class="sxs-lookup"><span data-stu-id="85bc5-305">URL</span></span>            | <span data-ttu-id="85bc5-306">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="85bc5-306">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="85bc5-307">Intestazione</span><span class="sxs-lookup"><span data-stu-id="85bc5-307">Header</span></span>         | <span data-ttu-id="85bc5-308">Content-Type</span><span class="sxs-lookup"><span data-stu-id="85bc5-308">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="85bc5-309">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="85bc5-309">application/atom+xml</span></span> |
| <span data-ttu-id="85bc5-310">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="85bc5-310">Authentication</span></span> | <span data-ttu-id="85bc5-311">Di base</span><span class="sxs-lookup"><span data-stu-id="85bc5-311">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="85bc5-312">Nome utente</span><span class="sxs-lookup"><span data-stu-id="85bc5-312">Username</span></span>       | <span data-ttu-id="85bc5-313">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="85bc5-313">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="85bc5-314">Password</span><span class="sxs-lookup"><span data-stu-id="85bc5-314">Password</span></span>       | <span data-ttu-id="85bc5-315">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="85bc5-315">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="85bc5-316">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="85bc5-316">Response codes</span></span>

| <span data-ttu-id="85bc5-317">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="85bc5-317">**Response Code**</span></span> | <span data-ttu-id="85bc5-318">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="85bc5-318">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="85bc5-319">200</span><span class="sxs-lookup"><span data-stu-id="85bc5-319">200</span></span>               | <span data-ttu-id="85bc5-320">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="85bc5-320">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="85bc5-321">404</span><span class="sxs-lookup"><span data-stu-id="85bc5-321">404</span></span>               | <span data-ttu-id="85bc5-322">Non trovato</span><span class="sxs-lookup"><span data-stu-id="85bc5-322">Not found</span></span>                                            |
| <span data-ttu-id="85bc5-323">302</span><span class="sxs-lookup"><span data-stu-id="85bc5-323">302</span></span>               | <span data-ttu-id="85bc5-324">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="85bc5-324">Redirect</span></span>                                             |
| <span data-ttu-id="85bc5-325">401</span><span class="sxs-lookup"><span data-stu-id="85bc5-325">401</span></span>               | <span data-ttu-id="85bc5-326">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="85bc5-326">Authorization Failed</span></span>                                 |
| <span data-ttu-id="85bc5-327">403</span><span class="sxs-lookup"><span data-stu-id="85bc5-327">403</span></span>               | <span data-ttu-id="85bc5-328">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="85bc5-328">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="85bc5-329">Ottenere un evento in base al nome</span><span class="sxs-lookup"><span data-stu-id="85bc5-329">Get an event by name</span></span>

| <span data-ttu-id="85bc5-330">Metodo</span><span class="sxs-lookup"><span data-stu-id="85bc5-330">Method</span></span>         | <span data-ttu-id="85bc5-331">GET</span><span class="sxs-lookup"><span data-stu-id="85bc5-331">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="85bc5-332">URL</span><span class="sxs-lookup"><span data-stu-id="85bc5-332">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="85bc5-333">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="85bc5-333">Headers</span></span>        | <span data-ttu-id="85bc5-334">Content-Type</span><span class="sxs-lookup"><span data-stu-id="85bc5-334">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="85bc5-335">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="85bc5-335">application/atom+xml</span></span> |
| <span data-ttu-id="85bc5-336">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="85bc5-336">Authentication</span></span> | <span data-ttu-id="85bc5-337">Di base</span><span class="sxs-lookup"><span data-stu-id="85bc5-337">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="85bc5-338">Nome utente</span><span class="sxs-lookup"><span data-stu-id="85bc5-338">Username</span></span>       | <span data-ttu-id="85bc5-339">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="85bc5-339">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="85bc5-340">Password</span><span class="sxs-lookup"><span data-stu-id="85bc5-340">Password</span></span>       | <span data-ttu-id="85bc5-341">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="85bc5-341">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="85bc5-342">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="85bc5-342">Response codes</span></span>

| <span data-ttu-id="85bc5-343">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="85bc5-343">**Response Code**</span></span> | <span data-ttu-id="85bc5-344">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="85bc5-344">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="85bc5-345">200</span><span class="sxs-lookup"><span data-stu-id="85bc5-345">200</span></span>               | <span data-ttu-id="85bc5-346">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="85bc5-346">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="85bc5-347">404</span><span class="sxs-lookup"><span data-stu-id="85bc5-347">404</span></span>               | <span data-ttu-id="85bc5-348">Non trovato</span><span class="sxs-lookup"><span data-stu-id="85bc5-348">Not found</span></span>                                            |
| <span data-ttu-id="85bc5-349">302</span><span class="sxs-lookup"><span data-stu-id="85bc5-349">302</span></span>               | <span data-ttu-id="85bc5-350">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="85bc5-350">Redirect</span></span>                                             |
| <span data-ttu-id="85bc5-351">401</span><span class="sxs-lookup"><span data-stu-id="85bc5-351">401</span></span>               | <span data-ttu-id="85bc5-352">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="85bc5-352">Authorization Failed</span></span>                                 |
| <span data-ttu-id="85bc5-353">403</span><span class="sxs-lookup"><span data-stu-id="85bc5-353">403</span></span>               | <span data-ttu-id="85bc5-354">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="85bc5-354">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="85bc5-355">Uso di PowerShell (versione 6 o successiva) o un client HTTP</span><span class="sxs-lookup"><span data-stu-id="85bc5-355">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="85bc5-356">Passaggio 1: Connettersi a PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85bc5-356">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="85bc5-357">Passaggio 2: Eseguire lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="85bc5-357">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85bc5-358">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="85bc5-358">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="85bc5-359">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="85bc5-359">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="85bc5-360">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="85bc5-360">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="85bc5-361">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="85bc5-361">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="85bc5-362">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="85bc5-362">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="85bc5-363">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="85bc5-363">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="85bc5-364">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="85bc5-364">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="85bc5-365">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-365">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="85bc5-366">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="85bc5-366">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="85bc5-367">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="85bc5-367">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="85bc5-368">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-368">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="85bc5-369">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-369">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="85bc5-370">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-370">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="85bc5-371">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-371">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="85bc5-372">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-372">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="85bc5-373">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-373">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="85bc5-374">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-374">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="85bc5-375">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-375">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="85bc5-376">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-376">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="85bc5-377">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="85bc5-377">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="85bc5-378">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="85bc5-378">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="85bc5-379">$event = $null</span><span class="sxs-lookup"><span data-stu-id="85bc5-379">$event = $null</span></span></p>
<p><span data-ttu-id="85bc5-380">try</span><span class="sxs-lookup"><span data-stu-id="85bc5-380">try</span></span></p>
<p><span data-ttu-id="85bc5-381">{</span><span class="sxs-lookup"><span data-stu-id="85bc5-381">{</span></span></p>
<p><span data-ttu-id="85bc5-382">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="85bc5-382">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="85bc5-383">}</span><span class="sxs-lookup"><span data-stu-id="85bc5-383">}</span></span></p>
<p><span data-ttu-id="85bc5-384">catch</span><span class="sxs-lookup"><span data-stu-id="85bc5-384">catch</span></span></p>
<p><span data-ttu-id="85bc5-385">{</span><span class="sxs-lookup"><span data-stu-id="85bc5-385">{</span></span></p>
<p><span data-ttu-id="85bc5-386">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="85bc5-386">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="85bc5-387">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="85bc5-387">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="85bc5-388">{</span><span class="sxs-lookup"><span data-stu-id="85bc5-388">{</span></span></p>
<p><span data-ttu-id="85bc5-389">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="85bc5-389">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="85bc5-390">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="85bc5-390">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="85bc5-391">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="85bc5-391">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="85bc5-392">}</span><span class="sxs-lookup"><span data-stu-id="85bc5-392">}</span></span></p>
<p><span data-ttu-id="85bc5-393">}</span><span class="sxs-lookup"><span data-stu-id="85bc5-393">}</span></span></p>
<p><span data-ttu-id="85bc5-394">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="85bc5-394">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="85bc5-395">Verificare il risultato in entrambe le opzioni</span><span class="sxs-lookup"><span data-stu-id="85bc5-395">Verify the outcome in both options</span></span>

<span data-ttu-id="85bc5-396">Passaggio 1: Passare al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="85bc5-396">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="85bc5-397">Passaggio 2: Scegliere **Eventi** in **Governance delle informazioni**.</span><span class="sxs-lookup"><span data-stu-id="85bc5-397">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="85bc5-398">Passaggio 3: Verificare di aver creato l'evento.</span><span class="sxs-lookup"><span data-stu-id="85bc5-398">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="85bc5-399">È possibile usare le opzioni precedenti per automatizzare la conservazione basata sugli eventi anche per gli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="85bc5-399">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="85bc5-400">Scenario 2: Contratti in scadenza</span><span class="sxs-lookup"><span data-stu-id="85bc5-400">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="85bc5-401">Un'organizzazione può avere più record per un singolo contratto con clienti, fornitori e partner.</span><span class="sxs-lookup"><span data-stu-id="85bc5-401">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="85bc5-402">Questi documenti possono trovarsi in una raccolta documenti come SharePoint.</span><span class="sxs-lookup"><span data-stu-id="85bc5-402">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="85bc5-403">Il termine di un contratto determina l'inizio del periodo di conservazione dei documenti associati al contratto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-403">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="85bc5-404">Ad esempio, tutti i record relativi ai contratti devono essere conservati per cinque anni dalla data di scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-404">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="85bc5-405">L'evento che attiva il periodo di conservazione di cinque anni è la scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-405">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="85bc5-406">Un sistema di Customer Relationship Management (CRM) può interagire con Microsoft 365 per attivare la conservazione dei documenti contrattuali</span><span class="sxs-lookup"><span data-stu-id="85bc5-406">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="85bc5-407">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="85bc5-407">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e attività per scenari di scadenza contratto](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="85bc5-409">L'amministratore crea una raccolta di SharePoint con varie cartelle per ogni tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-409">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="85bc5-410">L'amministratore aggiunge i documenti contrattuali, ad esempio Contratti di licenza e Contratti di sviluppo, a ogni cartella di contratto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-410">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="85bc5-411">L'amministratore assegna l'ID risorsa a ogni cartella di contratto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-411">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="85bc5-412">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="85bc5-412">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="85bc5-413">L'amministratore SCC crea tipi di eventi correlati al contratto, come "Creazione contratto" o "Scadenza contratto".</span><span class="sxs-lookup"><span data-stu-id="85bc5-413">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="85bc5-414">L'amministratore SCC crea l'etichetta "Scadenza contratto".</span><span class="sxs-lookup"><span data-stu-id="85bc5-414">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="85bc5-415">L'etichetta "Scadenza contratto" viene pubblicata e applicata manualmente o automaticamente ai documenti contrattuali in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="85bc5-415">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="85bc5-416">Il sistema di gestione dei contratti può eseguire periodicamente Microsoft Flow o un'applicazione simile per gestire i documenti contrattuali.</span><span class="sxs-lookup"><span data-stu-id="85bc5-416">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="85bc5-417">Se un contratto scade, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="85bc5-417">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="85bc5-418">Scenario 3: Fine produzione</span><span class="sxs-lookup"><span data-stu-id="85bc5-418">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="85bc5-p124">Un'impresa che produce diverse linee di prodotti crea molte specifiche di produzione e tariffari. Quando il prodotto esce fuori produzione, tutte le specifiche e i documenti a esso collegati devono essere conservati per un determinato periodo di tempo dopo la fine del ciclo di vita del prodotto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="85bc5-421">Un sistema ERP (Enterprise Resource Planning) può utilizzare Microsoft 365 e Microsoft Flow per attivare la conservazione.</span><span class="sxs-lookup"><span data-stu-id="85bc5-421">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="85bc5-422">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="85bc5-422">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e attività per uno scenario di ciclo di vita del prodotto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="85bc5-424">L'amministratore crea delle cartelle di prodotto nel set di documenti, ad esempio Prodotto 1, Prodotto 2, ecc.</span><span class="sxs-lookup"><span data-stu-id="85bc5-424">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="85bc5-425">L'amministratore aggiunge i documenti del prodotto, ad esempio Specifiche di produzione, Prezzi del prodotto, Licenze del prodotto a ogni cartella.</span><span class="sxs-lookup"><span data-stu-id="85bc5-425">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="85bc5-426">L'amministratore assegna l'ID risorsa a ogni cartella di prodotto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-426">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="85bc5-427">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="85bc5-427">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="85bc5-428">L'amministratore SCC crea tipi di eventi correlati al prodotto, come "Inizio produzione", "Fine produzione".</span><span class="sxs-lookup"><span data-stu-id="85bc5-428">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="85bc5-429">L'amministratore SCC crea l'etichetta "Fine produzione".</span><span class="sxs-lookup"><span data-stu-id="85bc5-429">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="85bc5-430">L'etichetta "Fine produzione" viene pubblicata e applicata manualmente o automaticamente ai documenti del prodotto in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="85bc5-430">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="85bc5-431">I sistemi ERP possono eseguire periodicamente Microsoft Flow o applicazioni simili per gestire i documenti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="85bc5-431">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="85bc5-432">Se un prodotto esce fuori produzione, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="85bc5-432">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="85bc5-433">Appendice</span><span class="sxs-lookup"><span data-stu-id="85bc5-433">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="85bc5-434">Uso dei risultati della risposta Redirect 302 per chiamare l'API REST</span><span class="sxs-lookup"><span data-stu-id="85bc5-434">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="85bc5-435">Chiamare un evento di conservazione POST usando l'URL dell'API REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (sono necessarie le autorizzazioni di amministratore globale)</span><span class="sxs-lookup"><span data-stu-id="85bc5-435">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="85bc5-p125">Controllare il codice di risposta. Se è 302, ottenere l'URL reindirizzato dalla proprietà Posizione dell'intestazione della risposta</span><span class="sxs-lookup"><span data-stu-id="85bc5-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="85bc5-438">Chiamare nuovamente l'evento di conservazione POST usando l'URL reindirizzato.</span><span class="sxs-lookup"><span data-stu-id="85bc5-438">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="85bc5-439">Riconoscimenti</span><span class="sxs-lookup"><span data-stu-id="85bc5-439">Credits</span></span>

<span data-ttu-id="85bc5-440">Questo argomento è stato rivisto da:</span><span class="sxs-lookup"><span data-stu-id="85bc5-440">This topic was reviewed by:</span></span>

<span data-ttu-id="85bc5-441">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="85bc5-441">Antonio Maio</span></span><br/><span data-ttu-id="85bc5-442">MVP App e servizi di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="85bc5-442">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="85bc5-443">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="85bc5-443">Antonio.Maio@Protiviti.com</span></span>
