---
title: Automatizzare la conservazione basata su eventi
ms.author: laurawi
author: laurawi
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
ms.openlocfilehash: 5977b79c47166fdafc76dfdb122b4fd37b63a875
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38708134"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="93890-103">Automatizzare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="93890-103">Automate event-based retention</span></span>

<span data-ttu-id="93890-p101">L'esplosione del contenuto nelle organizzazioni e il modo in cui può diventare ROT (redundant, obsolete, trivial, cioè ridondante, obsoleto e banale), è una cosa seria. Per continuare a soddisfare gli obblighi di conformità normativa, legale e finanziaria, le aziende devono poter conservare e proteggere le informazioni importanti e trovare rapidamente ciò che conta. Conservare solo informazioni importanti e pertinenti è fondamentale per il successo di un'azienda.</span><span class="sxs-lookup"><span data-stu-id="93890-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, businesses must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to a business’s success.</span></span>

<span data-ttu-id="93890-p102">Di conseguenza, le organizzazioni possono sfruttare le soluzioni di conservazione nel Centro sicurezza e conformità di Office 365. La conservazione può essere attivata usando [etichette di conservazione](labels.md), che consentono di [basare il periodo di conservazione su un evento specifico](event-driven-retention.md). In genere, il periodo di conservazione si basa su una data nota, come la data di creazione o dell'ultima modifica del contenuto. Tuttavia, le organizzazioni fanno fronte anche a requisiti di smaltimento dei contenuti in base al verificarsi di un evento, ad esempio 7 anni dopo che un dipendente ha lasciato l'azienda.</span><span class="sxs-lookup"><span data-stu-id="93890-p102">Hence organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as 7 years after an employee leaves an organization.</span></span>

<span data-ttu-id="93890-p103">Per garantire lo smaltimento conforme del contenuto, è fondamentale conoscere la data in cui si verifica un evento. Con il rapido aumento del volume di contenuti, diventa sempre più difficile conservare e smaltire i contenuti in maniera puntuale e conforme.</span><span class="sxs-lookup"><span data-stu-id="93890-p103">In order to ensure compliant disposal of content, it is imperative to know when an event takes place. With the volume of content increasing rapidly, it is becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="93890-p104">La conservazione basata sugli eventi è la soluzione a questo problema. Questo argomento illustra come configurare i flussi di processo aziendale in modo da automatizzare la conservazione attraverso gli eventi usando l'API REST di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93890-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="93890-116">Informazioni sulla conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="93890-116">About event-based retention</span></span>

<span data-ttu-id="93890-p105">Un'organizzazione può avere dimensioni piccole, medie o grandi. Il numero di documenti aziendali e legali, dossier del personale, contratti e documenti sul prodotto che vengono creati e gestiti su base quotidiana è in drastico aumento.</span><span class="sxs-lookup"><span data-stu-id="93890-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day to day basis is increasing dramatically.</span></span>

<span data-ttu-id="93890-p106">Ad esempio, ogni giorno decine o centinaia di dipendenti entrano a far parte delle organizzazioni o le lasciano. Il reparto Risorse umane continua a creare, aggiornare o eliminare i documenti relativi ai dipendenti in base ai requisiti aziendali. Questo processo è soggetto ai diversi criteri di conservazione indicati per l'azienda:</span><span class="sxs-lookup"><span data-stu-id="93890-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="93890-p107">**Il periodo di conservazione del contenuto può essere una data nota**, ad esempio la data di creazione, dell'ultima modifica o dell'assegnazione di un'etichetta al contenuto. Ad esempio, si potrebbero conservare documenti per sette anni dalla creazione per poi eliminarli.</span><span class="sxs-lookup"><span data-stu-id="93890-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="93890-p108">**Il periodo di conservazione del contenuto può essere anche una data sconosciuta**. Ad esempio, con le etichette di conservazione è anche possibile basare anche un periodo di conservazione sul momento in cui si verifica un determinato tipo di evento, ad esempio quando un dipendente lascia l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="93890-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="93890-p109">L'evento fa scattare l'inizio del periodo di conservazione e tutto il contenuto con un'etichetta applicata per quel tipo di evento riceve le azioni di conservazione dell'etichetta applicate su di esso. È ciò che si intende con conservazione basata sugli eventi. Per altre informazioni, vedere [Panoramica della conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="93890-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention - to learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="93890-128">Configurare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="93890-128">Set up event-based retention</span></span>

<span data-ttu-id="93890-129">Questa sezione descrive le operazioni da eseguire prima della conservazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="93890-129">This section describes what needs to be done prior to retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="93890-130">Identificare i ruoli</span><span class="sxs-lookup"><span data-stu-id="93890-130">Identify roles</span></span>

<span data-ttu-id="93890-131">Identificare i ruoli diversi in un'organizzazione che esegue attività di Gestione record, responsabile della conservazione efficace ed efficiente dei documenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="93890-131">Identify the different roles in an organization that perform Record Management tasks that would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="93890-132">**Persona**</span><span class="sxs-lookup"><span data-stu-id="93890-132">**Persona**</span></span>| <span data-ttu-id="93890-133">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="93890-133">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="93890-134">Amministratore</span><span class="sxs-lookup"><span data-stu-id="93890-134">Admin</span></span> | <span data-ttu-id="93890-135">Crea tipi di eventi di conservazione, etichette di conservazione e repository dei record in SharePoint</span><span class="sxs-lookup"><span data-stu-id="93890-135">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="93890-136">Responsabile della gestione dei record</span><span class="sxs-lookup"><span data-stu-id="93890-136">Records Manager</span></span>                                  | <span data-ttu-id="93890-137">Fornisce linee guida su criteri di conservazione e pianificazioni della conservazione, oltre a informazioni dettagliate sulla conformità</span><span class="sxs-lookup"><span data-stu-id="93890-137">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="93890-138">Amministratore di sistema (azienda)</span><span class="sxs-lookup"><span data-stu-id="93890-138">System Admin (business)</span></span>                          | <span data-ttu-id="93890-139">Configura e gestisce i sistemi esterni in modo da utilizzare Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93890-139">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="93890-140">Information Worker</span><span class="sxs-lookup"><span data-stu-id="93890-140">Information Worker</span></span>                               | <span data-ttu-id="93890-141">Gestisce il ciclo di vita del proprio processo aziendale (risorse umane, finanza, IT ecc.)</span><span class="sxs-lookup"><span data-stu-id="93890-141">Manages the lifecycle of their business process (HR, Finance, IT etc)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="93890-142">Configurare il Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="93890-142">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="93890-143">L'amministratore di conformità crea un tipo di evento, ad esempio Licenziamento dipendente, Scadenza contratto oppure Fine produzione. Vedere la procedura dettagliata nell'articolo sulla [conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="93890-143">Compliance admin creates an event type – for example, Employee Termination or Contract Expiration or End of Product Manufacturing (Please refer to step by step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
1. <span data-ttu-id="93890-144">L'amministratore di conformità crea un'etichetta di conservazione in base a un evento e la associa a un tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="93890-144">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
1. <span data-ttu-id="93890-145">Ci sono 4 tipi di trigger per le etichette di conservazione:</span><span class="sxs-lookup"><span data-stu-id="93890-145">There are 4 types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="93890-146">Data creazione</span><span class="sxs-lookup"><span data-stu-id="93890-146">Create date</span></span>
                
    1. <span data-ttu-id="93890-147">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="93890-147">Last modified</span></span>
                
    1. <span data-ttu-id="93890-148">Data etichetta (quando il contenuto è stato etichettato)</span><span class="sxs-lookup"><span data-stu-id="93890-148">Label date (when the content was labeled)</span></span>
                
    1. <span data-ttu-id="93890-149">Basata su eventi</span><span class="sxs-lookup"><span data-stu-id="93890-149">Event-based</span></span>
    
1. <span data-ttu-id="93890-150">L'amministratore di conformità pubblica l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="93890-150">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="93890-151">Configurare SharePoint</span><span class="sxs-lookup"><span data-stu-id="93890-151">Set up SharePoint</span></span>
   
<span data-ttu-id="93890-152">Per creare un repository dei record, l'amministratore di conformità deve:</span><span class="sxs-lookup"><span data-stu-id="93890-152">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="93890-153">Creare un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="93890-153">Creates a SharePoint site.</span></span>

1. <span data-ttu-id="93890-154">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="93890-154">Does one of the following:</span></span>
        
    - <span data-ttu-id="93890-p110">Creare una raccolta di SharePoint: configurare un'etichetta basata su eventi a livello di raccolta. Per altre informazioni, vedere [Applicazione di un'etichetta di conservazione predefinita a tutto il contenuto in una raccolta, una cartella o un set di documenti di SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="93890-p110">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="93890-p111">Configurare un set di documenti in SharePoint. Per altre informazioni, vedere [Introduzione ai set di documenti](https://support.office.com/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="93890-p111">Sets up a Document set in SharePoint. For more information, see [Introduction to document sets](https://support.office.com/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
1. <span data-ttu-id="93890-p112">Assegnare ID risorsa (cioè un nome o codice del prodotto usato dall'organizzazione, ad esempio il numero dipendente) al set di documenti di ogni dipendente. Assegnando l'ID risorsa alla cartella, ogni elemento in essa contenuto eredita automaticamente lo stesso ID risorsa. Ciò significa che è possibile attivare il periodo di conservazione di tutti gli elementi con lo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="93890-p112">Assigns Asset Id (asset ID is a product name or code used by the organization, for example, Employee number can be an asset id) to each employee document set (By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID. This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="93890-161">Modi per attivare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="93890-161">Ways to trigger event-based retention</span></span>

<span data-ttu-id="93890-162">Esistono due modi in cui è possibile attivare la conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="93890-162">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="93890-p113">**Con l'interfaccia di amministrazione**: questo processo può essere utile per conservare meno contenuti contemporaneamente o quando la frequenza di attivazione della conservazione è bassa, ad esempio mensile o annuale. Per altre informazioni su questo metodo, vedere [Panoramica della conservazione basata su eventi](event-driven-retention.md). Questa modalità di attivazione della conservazione può tuttavia comportare tempi eccessivi ed è più soggetta ad errori, impedendo così la scalabilità. Di conseguenza, per migliorare la sicurezza e la conformità dei dati, è consigliabile adottare una soluzione semplificata e automatica per attivare la conservazione.</span><span class="sxs-lookup"><span data-stu-id="93890-p113">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention is not often, such as monthly or yearly. For more information on this method, see [Overview of event-driven retention](event-driven-retention.md). However, this way to trigger retention can be time-consuming and prone to error, thus stunting scalability. Therefore, an automated, seamless solution to trigger retention can enhance the security and compliance of data.</span></span>

- <span data-ttu-id="93890-p114">**Con l'API REST di M365**: questo processo è utile quando occorre conservare grandi quantità di contenuto contemporaneamente e/o la frequenza di attivazione della conservazione è alta, ad esempio giornaliera o settimanale. Il flusso rileva il verificarsi di un evento nel sistema line-of-business e crea automaticamente un evento correlato nel Centro di sicurezza e conformità. Non è necessario creare manualmente un evento nell'interfaccia ogni volta che se ne verifica uno.</span><span class="sxs-lookup"><span data-stu-id="93890-p114">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="93890-170">Sono disponibili due opzioni per usare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="93890-170">There are two options for using the REST API:</span></span>

- <span data-ttu-id="93890-p115">**Microsoft Flow o un'applicazione simile** consente di attivare automaticamente l'occorrenza di un evento. Microsoft Flow è un agente di orchestrazione per la connessione ad altri sistemi. Microsoft Flow non richiede una soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="93890-p115">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically. Microsoft Flow is an orchestrator for connecting to other systems. Using Microsoft Flow does not require a custom solution.</span></span>

- <span data-ttu-id="93890-174">**PowerShell o un client HTTP per le chiamate all'API REST**: usare PowerShell (versione 6 o successive) per chiamare l'API REST di Microsoft 365 per creare eventi.</span><span class="sxs-lookup"><span data-stu-id="93890-174">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="93890-p116">Un'API REST è un endpoint del servizio che supporta i set di operazioni HTTP (metodi), che consentono di creare/recuperare/aggiornare/eliminare l'accesso alle risorse del servizio. Per altre informazioni, vedere [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse) (Componenti della richiesta-risposta di un'API REST). In questo caso, con le API REST di Microsoft 365, è possibile creare e recuperare eventi con le operazioni (metodi) POST e GET.</span><span class="sxs-lookup"><span data-stu-id="93890-p116">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources - for more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="93890-177">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="93890-177">Example scenarios</span></span>

<span data-ttu-id="93890-178">Considerare i seguenti scenari.</span><span class="sxs-lookup"><span data-stu-id="93890-178">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="93890-179">Scenario 1: Dipendenti che lasciano l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="93890-179">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="93890-p117">Un'organizzazione crea e archivia per ogni dipendente numerosi documenti che vengono gestiti e conservati durante il rispettivo periodo di impiego. Tuttavia, quando il dipendente lascia l'organizzazione o alla cessazione del rapporto di lavoro, l'organizzazione è obbligata in virtù dei requisiti legali e aziendali a conservare la documentazione relativa al dipendente per un periodo concordato.</span><span class="sxs-lookup"><span data-stu-id="93890-p117">An organization creates and stores numerous employee related documents per employee. These documents are managed and retained during the employment of each employee. However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="93890-183">Quindi, se più dipendenti lasciassero l'organizzazione ogni giorno, l'organizzazione dovrebbe attivare quotidianamente l'intervallo di conservazione per centinaia o migliaia di documenti.</span><span class="sxs-lookup"><span data-stu-id="93890-183">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="93890-p118">Oltre a tutto questo, occorre calcolare il periodo di conservazione per ciascun dipendente in base alla formula Data licenziamento dipendente + numero di giorni, mesi o anni in base al tipo di record del dipendente. Ad esempio, il periodo di conservazione dei documenti di assicurazione contro gli infortuni sul lavoro rispetto ai benefit del dipendente potrebbe differire.</span><span class="sxs-lookup"><span data-stu-id="93890-p118">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months or years based on the type of the employee record. For example, worker’s compensation of the employee vs benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="93890-p119">Il diagramma seguente mostra come è possibile associare più etichette a un singolo evento. In questo caso, tutti i file con l'etichetta Assicurazione contro gli infortuni sul lavoro e quelli con l'etichetta Benefit dipendenti sono associati a un singolo evento, cioè l'abbandono dell'organizzazione da parte del dipendente. Ciascuno di questi file ha un diverso intervallo di conservazione, perciò quando un dipendente lascia l'organizzazione i file con ciascuna etichetta saranno caratterizzati da un diverso periodo di conservazione. Per attivare i diversi intervalli di conservazione per ogni tipo di file o etichetta per ciascun dipendente è un'attività davvero complessa, figurarsi per più dipendenti.</span><span class="sxs-lookup"><span data-stu-id="93890-p119">The diagram below shows how there can be multiple labels that are associated with a single event. Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event which is the employee leaving the organization. Each of these different files have different retention clocks. So, when an employee leaves the organization, these files within each label experience a different retention period. To trigger all these different retention clocks for each file type or label for each employee is a very challenging task. Imagine doing this for multiple employees.</span></span>

![Diagramma del tipo di evento, evento ed etichette](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="93890-193">Di conseguenza, un processo automatizzato per attivare i diversi intervalli di conservazione per più dipendenti consente di risparmiare tempo, è privo di errori ed estremamente efficiente.</span><span class="sxs-lookup"><span data-stu-id="93890-193">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free and extremely efficient .</span></span>

<span data-ttu-id="93890-194">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="93890-194">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e azioni per lo scenario in cui il dipendente lascia l'organizzazione](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="93890-196">L'amministratore crea le cartelle del dipendente nel set di documenti, ad esempio Angela Barbariol, Luca Udinesi.</span><span class="sxs-lookup"><span data-stu-id="93890-196">Admin c reates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="93890-197">L'amministratore aggiunge i documenti dei dipendenti, ad esempio Benefit, Paghe, Assicurazione contro gli infortuni sul lavoro, a ogni cartella dipendente</span><span class="sxs-lookup"><span data-stu-id="93890-197">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder</span></span>

  - <span data-ttu-id="93890-198">L'amministratore assegna l'ID risorsa a ogni cartella dipendente.</span><span class="sxs-lookup"><span data-stu-id="93890-198">Admin assigns Asset Id to each employee folder.</span></span> 

  - <span data-ttu-id="93890-199">L'amministratore SCC</span><span class="sxs-lookup"><span data-stu-id="93890-199">SCC Admin l</span></span>

  - <span data-ttu-id="93890-200">accede al Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="93890-200">Logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="93890-201">L'amministratore SCC crea tipi di eventi correlati al dipendente, come "Licenziamento del dipendente", "Assunzione del dipendente".</span><span class="sxs-lookup"><span data-stu-id="93890-201">SCC Admin creates employee related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="93890-202">L'amministratore SCC crea l'etichetta "Conservazione dipendente".</span><span class="sxs-lookup"><span data-stu-id="93890-202">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="93890-203">L'etichetta "Conservazione dipendente" viene pubblicata e applicata manualmente o automaticamente ai documenti dei dipendenti in SharePoint</span><span class="sxs-lookup"><span data-stu-id="93890-203">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint</span></span>

  - <span data-ttu-id="93890-204">Un sistema di gestione delle risorse umane come Workday può eseguire periodicamente Microsoft Flow per gestire i documenti dei dipendenti</span><span class="sxs-lookup"><span data-stu-id="93890-204">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files</span></span>

  - <span data-ttu-id="93890-205">Se un dipendente ha lasciato l'organizzazione, Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del dipendente specifico.</span><span class="sxs-lookup"><span data-stu-id="93890-205">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="93890-206">Uso di Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="93890-206">Using Microsoft Flow</span></span>

<span data-ttu-id="93890-207">Passaggio 1: Creare un flusso per creare un evento usando le API REST di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93890-207">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usare Flow per creare un evento](media/automate-event-driven-retention-flow-1.png)

![Usare Flow per chiamare l'API REST](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="93890-210">Creare un evento</span><span class="sxs-lookup"><span data-stu-id="93890-210">Create an event</span></span>

<span data-ttu-id="93890-211">Codice di esempio per chiamare l'API REST</span><span class="sxs-lookup"><span data-stu-id="93890-211">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="93890-212">Metodo</span><span class="sxs-lookup"><span data-stu-id="93890-212">Method</span></span></th>
<th><span data-ttu-id="93890-213">POST</span><span class="sxs-lookup"><span data-stu-id="93890-213">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="93890-214">URL</span><span class="sxs-lookup"><span data-stu-id="93890-214">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="93890-215">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="93890-215">Headers</span></span></td>
<td><span data-ttu-id="93890-216">Content-Type</span><span class="sxs-lookup"><span data-stu-id="93890-216">Content-Type</span></span></td>
<td><span data-ttu-id="93890-217">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="93890-217">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="93890-218">Corpo</span><span class="sxs-lookup"><span data-stu-id="93890-218">Body</span></span></td>
<td><p><span data-ttu-id="93890-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="93890-220">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="93890-220">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="93890-221">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="93890-221">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="93890-222">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-222">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="93890-223">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-223">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="93890-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="93890-225">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-225">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="93890-226">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-226">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="93890-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="93890-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="93890-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="93890-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="93890-231">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-231">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="93890-232">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-232">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="93890-233">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-233">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="93890-234">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="93890-234">Authentication</span></span></td>
<td><span data-ttu-id="93890-235">Di base</span><span class="sxs-lookup"><span data-stu-id="93890-235">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="93890-236">Nome utente</span><span class="sxs-lookup"><span data-stu-id="93890-236">Username</span></span></td>
<td><span data-ttu-id="93890-237">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="93890-237">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="93890-238">Password</span><span class="sxs-lookup"><span data-stu-id="93890-238">Password</span></span></td>
<td><span data-ttu-id="93890-239">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="93890-239">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="93890-240">Parametri disponibili</span><span class="sxs-lookup"><span data-stu-id="93890-240">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="93890-241"><strong>Parametri</strong></span><span class="sxs-lookup"><span data-stu-id="93890-241"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="93890-242"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="93890-242"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="93890-243"><strong>Note</strong></span><span class="sxs-lookup"><span data-stu-id="93890-243"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="93890-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="93890-245">Immettere un nome univoco per l'evento,</span><span class="sxs-lookup"><span data-stu-id="93890-245">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="93890-p120">Non può contenere spazi e i caratteri seguenti: % \* \ &amp; &lt; &gt; | # ? , : ,</span><span class="sxs-lookup"><span data-stu-id="93890-p120">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="93890-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="93890-249">Immettere il nome del tipo di evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="93890-249">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="93890-p121">Esempio: "Licenziamento dipendente". Il tipo di evento deve essere associato a un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="93890-p121">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="93890-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="93890-253">Immettere "ComplianceAssetId:" + ID dipendente</span><span class="sxs-lookup"><span data-stu-id="93890-253">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="93890-254">Esempio:&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="93890-254">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="93890-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="93890-256">Data e ora evento</span><span class="sxs-lookup"><span data-stu-id="93890-256">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="93890-257">Formato: aaaa-MM-ggTHH:mm:ssZ, esempio:</span><span class="sxs-lookup"><span data-stu-id="93890-257">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="93890-258">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="93890-258">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="93890-259">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="93890-259">Response codes</span></span>

| <span data-ttu-id="93890-260">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="93890-260">**Response Code**</span></span> | <span data-ttu-id="93890-261">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="93890-261">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="93890-262">302</span><span class="sxs-lookup"><span data-stu-id="93890-262">302</span></span>               | <span data-ttu-id="93890-263">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="93890-263">Redirect</span></span>              |
| <span data-ttu-id="93890-264">201</span><span class="sxs-lookup"><span data-stu-id="93890-264">201</span></span>               | <span data-ttu-id="93890-265">Creato</span><span class="sxs-lookup"><span data-stu-id="93890-265">Created</span></span>               |
| <span data-ttu-id="93890-266">403</span><span class="sxs-lookup"><span data-stu-id="93890-266">403</span></span>               | <span data-ttu-id="93890-267">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="93890-267">Authorization Failed</span></span>  |
| <span data-ttu-id="93890-268">401</span><span class="sxs-lookup"><span data-stu-id="93890-268">401</span></span>               | <span data-ttu-id="93890-269">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="93890-269">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="93890-270">Ricevere gli eventi in base all'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="93890-270">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="93890-271">Metodo</span><span class="sxs-lookup"><span data-stu-id="93890-271">Method</span></span></th>
<th><span data-ttu-id="93890-272">GET</span><span class="sxs-lookup"><span data-stu-id="93890-272">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="93890-273">URL</span><span class="sxs-lookup"><span data-stu-id="93890-273">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="93890-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="93890-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="93890-275">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="93890-275">Headers</span></span></td>
<td><span data-ttu-id="93890-276">Content-Type</span><span class="sxs-lookup"><span data-stu-id="93890-276">Content-Type</span></span></td>
<td><span data-ttu-id="93890-277">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="93890-277">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="93890-278">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="93890-278">Authentication</span></span></td>
<td><span data-ttu-id="93890-279">Di base</span><span class="sxs-lookup"><span data-stu-id="93890-279">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="93890-280">Nome utente</span><span class="sxs-lookup"><span data-stu-id="93890-280">Username</span></span></td>
<td><span data-ttu-id="93890-281">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="93890-281">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="93890-282">Password</span><span class="sxs-lookup"><span data-stu-id="93890-282">Password</span></span></td>
<td><span data-ttu-id="93890-283">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="93890-283">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="93890-284">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="93890-284">Response codes</span></span>

| <span data-ttu-id="93890-285">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="93890-285">**Response Code**</span></span> | <span data-ttu-id="93890-286">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="93890-286">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="93890-287">200</span><span class="sxs-lookup"><span data-stu-id="93890-287">200</span></span>               | <span data-ttu-id="93890-288">OK, un elenco di eventi in atom+ xml</span><span class="sxs-lookup"><span data-stu-id="93890-288">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="93890-289">404</span><span class="sxs-lookup"><span data-stu-id="93890-289">404</span></span>               | <span data-ttu-id="93890-290">Non trovato</span><span class="sxs-lookup"><span data-stu-id="93890-290">Not found</span></span>                         |
| <span data-ttu-id="93890-291">302</span><span class="sxs-lookup"><span data-stu-id="93890-291">302</span></span>               | <span data-ttu-id="93890-292">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="93890-292">Redirect</span></span>                          |
| <span data-ttu-id="93890-293">401</span><span class="sxs-lookup"><span data-stu-id="93890-293">401</span></span>               | <span data-ttu-id="93890-294">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="93890-294">Authorization Failed</span></span>              |
| <span data-ttu-id="93890-295">403</span><span class="sxs-lookup"><span data-stu-id="93890-295">403</span></span>               | <span data-ttu-id="93890-296">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="93890-296">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="93890-297">Ottenere un evento in base all'ID</span><span class="sxs-lookup"><span data-stu-id="93890-297">Get an event by ID</span></span>

| <span data-ttu-id="93890-298">Metodo</span><span class="sxs-lookup"><span data-stu-id="93890-298">Method</span></span>         | <span data-ttu-id="93890-299">GET</span><span class="sxs-lookup"><span data-stu-id="93890-299">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="93890-300">URL</span><span class="sxs-lookup"><span data-stu-id="93890-300">URL</span></span>            | <span data-ttu-id="93890-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="93890-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="93890-302">Intestazione</span><span class="sxs-lookup"><span data-stu-id="93890-302">Header</span></span>         | <span data-ttu-id="93890-303">Content-Type</span><span class="sxs-lookup"><span data-stu-id="93890-303">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="93890-304">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="93890-304">application/atom+xml</span></span> |
| <span data-ttu-id="93890-305">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="93890-305">Authentication</span></span> | <span data-ttu-id="93890-306">Di base</span><span class="sxs-lookup"><span data-stu-id="93890-306">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="93890-307">Nome utente</span><span class="sxs-lookup"><span data-stu-id="93890-307">Username</span></span>       | <span data-ttu-id="93890-308">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="93890-308">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="93890-309">Password</span><span class="sxs-lookup"><span data-stu-id="93890-309">Password</span></span>       | <span data-ttu-id="93890-310">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="93890-310">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="93890-311">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="93890-311">Response codes</span></span>

| <span data-ttu-id="93890-312">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="93890-312">**Response Code**</span></span> | <span data-ttu-id="93890-313">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="93890-313">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="93890-314">200</span><span class="sxs-lookup"><span data-stu-id="93890-314">200</span></span>               | <span data-ttu-id="93890-315">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="93890-315">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="93890-316">404</span><span class="sxs-lookup"><span data-stu-id="93890-316">404</span></span>               | <span data-ttu-id="93890-317">Non trovato</span><span class="sxs-lookup"><span data-stu-id="93890-317">Not found</span></span>                                            |
| <span data-ttu-id="93890-318">302</span><span class="sxs-lookup"><span data-stu-id="93890-318">302</span></span>               | <span data-ttu-id="93890-319">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="93890-319">Redirect</span></span>                                             |
| <span data-ttu-id="93890-320">401</span><span class="sxs-lookup"><span data-stu-id="93890-320">401</span></span>               | <span data-ttu-id="93890-321">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="93890-321">Authorization Failed</span></span>                                 |
| <span data-ttu-id="93890-322">403</span><span class="sxs-lookup"><span data-stu-id="93890-322">403</span></span>               | <span data-ttu-id="93890-323">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="93890-323">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="93890-324">Ottenere un evento in base al nome</span><span class="sxs-lookup"><span data-stu-id="93890-324">Get an event by name</span></span>

| <span data-ttu-id="93890-325">Metodo</span><span class="sxs-lookup"><span data-stu-id="93890-325">Method</span></span>         | <span data-ttu-id="93890-326">GET</span><span class="sxs-lookup"><span data-stu-id="93890-326">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="93890-327">URL</span><span class="sxs-lookup"><span data-stu-id="93890-327">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="93890-328">Intestazioni</span><span class="sxs-lookup"><span data-stu-id="93890-328">Headers</span></span>        | <span data-ttu-id="93890-329">Content-Type</span><span class="sxs-lookup"><span data-stu-id="93890-329">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="93890-330">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="93890-330">application/atom+xml</span></span> |
| <span data-ttu-id="93890-331">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="93890-331">Authentication</span></span> | <span data-ttu-id="93890-332">Di base</span><span class="sxs-lookup"><span data-stu-id="93890-332">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="93890-333">Nome utente</span><span class="sxs-lookup"><span data-stu-id="93890-333">Username</span></span>       | <span data-ttu-id="93890-334">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="93890-334">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="93890-335">Password</span><span class="sxs-lookup"><span data-stu-id="93890-335">Password</span></span>       | <span data-ttu-id="93890-336">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="93890-336">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="93890-337">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="93890-337">Response codes</span></span>

| <span data-ttu-id="93890-338">**Codice di risposta**</span><span class="sxs-lookup"><span data-stu-id="93890-338">**Response Code**</span></span> | <span data-ttu-id="93890-339">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="93890-339">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="93890-340">200</span><span class="sxs-lookup"><span data-stu-id="93890-340">200</span></span>               | <span data-ttu-id="93890-341">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="93890-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="93890-342">404</span><span class="sxs-lookup"><span data-stu-id="93890-342">404</span></span>               | <span data-ttu-id="93890-343">Non trovato</span><span class="sxs-lookup"><span data-stu-id="93890-343">Not found</span></span>                                            |
| <span data-ttu-id="93890-344">302</span><span class="sxs-lookup"><span data-stu-id="93890-344">302</span></span>               | <span data-ttu-id="93890-345">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="93890-345">Redirect</span></span>                                             |
| <span data-ttu-id="93890-346">401</span><span class="sxs-lookup"><span data-stu-id="93890-346">401</span></span>               | <span data-ttu-id="93890-347">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="93890-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="93890-348">403</span><span class="sxs-lookup"><span data-stu-id="93890-348">403</span></span>               | <span data-ttu-id="93890-349">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="93890-349">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="93890-350">Uso di PowerShell (versione 6 o successiva) o un client HTTP</span><span class="sxs-lookup"><span data-stu-id="93890-350">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="93890-351">Passaggio 1: Connettersi a PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93890-351">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="93890-352">Passaggio 2: Eseguire lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="93890-352">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93890-353">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="93890-353">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="93890-354">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="93890-354">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="93890-355">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="93890-355">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="93890-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="93890-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="93890-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="93890-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="93890-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="93890-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="93890-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="93890-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="93890-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="93890-361">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="93890-361">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="93890-362">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="93890-362">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="93890-363">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-363">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="93890-364">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-364">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="93890-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="93890-366">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-366">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="93890-367">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-367">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="93890-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="93890-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="93890-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="93890-371">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-371">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="93890-372">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="93890-372">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="93890-373">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="93890-373">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="93890-374">$event = $null</span><span class="sxs-lookup"><span data-stu-id="93890-374">$event = $null</span></span></p>
<p><span data-ttu-id="93890-375">try</span><span class="sxs-lookup"><span data-stu-id="93890-375">try</span></span></p>
<p><span data-ttu-id="93890-376">{</span><span class="sxs-lookup"><span data-stu-id="93890-376">{</span></span></p>
<p><span data-ttu-id="93890-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="93890-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="93890-378">}</span><span class="sxs-lookup"><span data-stu-id="93890-378">}</span></span></p>
<p><span data-ttu-id="93890-379">catch</span><span class="sxs-lookup"><span data-stu-id="93890-379">catch</span></span></p>
<p><span data-ttu-id="93890-380">{</span><span class="sxs-lookup"><span data-stu-id="93890-380">{</span></span></p>
<p><span data-ttu-id="93890-381">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="93890-381">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="93890-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="93890-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="93890-383">{</span><span class="sxs-lookup"><span data-stu-id="93890-383">{</span></span></p>
<p><span data-ttu-id="93890-384">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="93890-384">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="93890-385">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="93890-385">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="93890-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="93890-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="93890-387">}</span><span class="sxs-lookup"><span data-stu-id="93890-387">}</span></span></p>
<p><span data-ttu-id="93890-388">}</span><span class="sxs-lookup"><span data-stu-id="93890-388">}</span></span></p>
<p><span data-ttu-id="93890-389">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="93890-389">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="93890-390">Verificare il risultato in entrambe le opzioni</span><span class="sxs-lookup"><span data-stu-id="93890-390">Verify the outcome in both options</span></span>

<span data-ttu-id="93890-391">Passaggio1: Passare al Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="93890-391">Step 1: Go to Security & Compliance Center</span></span>

<span data-ttu-id="93890-392">Passaggio 2: Scegliere Eventi in Governance dei dati</span><span class="sxs-lookup"><span data-stu-id="93890-392">Step 2: Click on Events under Data Governance</span></span>

<span data-ttu-id="93890-393">Passaggio 3: Verificare di aver creato l'evento.</span><span class="sxs-lookup"><span data-stu-id="93890-393">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="93890-394">È possibile usare le opzioni precedenti per automatizzare la conservazione basata sugli eventi anche per gli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="93890-394">Similarly, the above options to automate event based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="93890-395">Scenario 2: Contratti in scadenza</span><span class="sxs-lookup"><span data-stu-id="93890-395">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="93890-p122">Un'organizzazione può avere più record per un unico contratto con clienti, fornitori e partner. Questi documenti possono trovarsi in una raccolta documenti, ad esempio SharePoint. La fine del contratto determina l'inizio del periodo di conservazione dei documenti associati al contratto. Ad esempio: è necessario conservare tutti i record relativi ai contratti per cinque anni dalla scadenza del contratto. L'evento che attiva il periodo di conservazione di cinque anni è la scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="93890-p122">An organization can have multiple records for a single contract with customers, vendors and partners. These documents can reside in a document library like SharePoint. The ending of a contract determines the start of the retention period of the documents associated with the contract. For example: all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="93890-401">Un sistema di Customer Relationship Management (CRM) può interagire con Microsoft 365 per attivare la conservazione dei documenti contrattuali</span><span class="sxs-lookup"><span data-stu-id="93890-401">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="93890-402">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="93890-402">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e attività per scenari di scadenza contratto](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="93890-404">L'amministratore crea una raccolta di SharePoint con varie cartelle per ogni tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="93890-404">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="93890-405">L'amministratore aggiunge i documenti contrattuali, ad esempio Contratti di licenza e Contratti di sviluppo, a ogni cartella di contratto</span><span class="sxs-lookup"><span data-stu-id="93890-405">Admin adds contract files such as License Contracts, Development Contracts to each contract folder</span></span>

  - <span data-ttu-id="93890-406">L'amministratore assegna l'ID risorsa a ogni cartella di contratto</span><span class="sxs-lookup"><span data-stu-id="93890-406">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="93890-407">L'amministratore SCC accede al Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="93890-407">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="93890-408">L'amministratore SCC crea tipi di eventi correlati al contratto, come "Creazione contratto", "Scadenza contratto".</span><span class="sxs-lookup"><span data-stu-id="93890-408">SCC Admin creates contract related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="93890-409">L'amministratore SCC crea l'etichetta "Scadenza contratto".</span><span class="sxs-lookup"><span data-stu-id="93890-409">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="93890-410">L'etichetta "Scadenza contratto" viene pubblicata e applicata manualmente o automaticamente ai documenti contrattuali in SharePoint</span><span class="sxs-lookup"><span data-stu-id="93890-410">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint</span></span>

  - <span data-ttu-id="93890-411">Il sistema di gestione dei contrati può eseguire periodicamente Microsoft Flow o un'applicazione simile per gestire i documenti contrattuali</span><span class="sxs-lookup"><span data-stu-id="93890-411">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files</span></span>

  - <span data-ttu-id="93890-412">Se un contratto scade, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="93890-412">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="93890-413">Scenario 3: Fine produzione</span><span class="sxs-lookup"><span data-stu-id="93890-413">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="93890-p123">Un'impresa che produce diverse linee di prodotti crea molte specifiche di produzione e tariffari. Quando il prodotto esce fuori produzione, tutte le specifiche e i documenti a esso collegati devono essere conservati per un determinato periodo di tempo dopo la fine del ciclo di vita del prodotto.</span><span class="sxs-lookup"><span data-stu-id="93890-p123">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="93890-416">Un sistema ERP (Enterprise Resource Planning) può utilizzare Microsoft 365 e Microsoft Flow per attivare la conservazione.</span><span class="sxs-lookup"><span data-stu-id="93890-416">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="93890-417">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="93890-417">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e attività per uno scenario di ciclo di vita del prodotto](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="93890-419">L'amministratore crea cartelle del prodotto nel set di documenti, ad esempio Prodotto 1, Prodotto 2, ecc.</span><span class="sxs-lookup"><span data-stu-id="93890-419">Admin creates product folders in the Document set such as Product 1, Product 2, etc.</span></span>

  - <span data-ttu-id="93890-420">L'amministratore aggiunge i documenti del prodotto, ad esempio Specifiche di produzione, Prezzi del prodotto, Licenze del prodotto a ogni cartella di prodotto</span><span class="sxs-lookup"><span data-stu-id="93890-420">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder</span></span>

  - <span data-ttu-id="93890-421">L'amministratore assegna l'ID risorsa a ogni cartella di prodotto.</span><span class="sxs-lookup"><span data-stu-id="93890-421">Admin assigns Asset Id to each productfolder.</span></span>

  - <span data-ttu-id="93890-422">L'amministratore SCC accede al Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="93890-422">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="93890-423">L'amministratore SCC crea tipi di eventi correlati al prodotto, come "Inizio produzione", "Fine produzione".</span><span class="sxs-lookup"><span data-stu-id="93890-423">SCC Admin creates employee related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="93890-424">L'amministratore SCC crea l'etichetta "Fine produzione".</span><span class="sxs-lookup"><span data-stu-id="93890-424">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="93890-425">L'etichetta "Fine produzione" viene pubblicata e applicata manualmente o automaticamente ai documenti del prodotto in SharePoint</span><span class="sxs-lookup"><span data-stu-id="93890-425">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint</span></span>

  - <span data-ttu-id="93890-426">I sistemi ERP possono eseguire periodicamente Microsoft Flow o applicazioni simili per gestire i documenti del prodotto</span><span class="sxs-lookup"><span data-stu-id="93890-426">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files</span></span>

  - <span data-ttu-id="93890-427">Se un prodotto esce fuori produzione, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="93890-427">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="93890-428">Appendice</span><span class="sxs-lookup"><span data-stu-id="93890-428">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="93890-429">Uso dei risultati della risposta Redirect 302 per chiamare l'API REST</span><span class="sxs-lookup"><span data-stu-id="93890-429">Using Redirect 302 response results to call the REST API</span></span>

1.  <span data-ttu-id="93890-430">Chiamare un evento di conservazione POST usando l'URL dell'API REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (sono necessarie le autorizzazioni di amministratore globale)</span><span class="sxs-lookup"><span data-stu-id="93890-430">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2.  <span data-ttu-id="93890-p124">Controllare il codice di risposta. Se è 302, ottenere l'URL reindirizzato dalla proprietà Posizione dell'intestazione della risposta</span><span class="sxs-lookup"><span data-stu-id="93890-p124">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3.  <span data-ttu-id="93890-433">Chiamare nuovamente l'evento di conservazione POST usando l'URL reindirizzato.</span><span class="sxs-lookup"><span data-stu-id="93890-433">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="93890-434">Riconoscimenti</span><span class="sxs-lookup"><span data-stu-id="93890-434">Credits</span></span>

<span data-ttu-id="93890-435">Questo argomento è stato rivisto da:</span><span class="sxs-lookup"><span data-stu-id="93890-435">This topic was reviewed by:</span></span>

<span data-ttu-id="93890-436">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="93890-436">Antonio Maio</span></span><br/><span data-ttu-id="93890-437">MVP App e servizi di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="93890-437">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="93890-438">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="93890-438">Antonio.Maio@Protiviti.com</span></span>
