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
ms.openlocfilehash: c97106597733460caeab8d1d398ff81e23dd2727
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068115"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="d5a0a-103">Automatizzare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="d5a0a-103">Automate event-based retention</span></span>

><span data-ttu-id="d5a0a-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="d5a0a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="d5a0a-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span></span> <span data-ttu-id="d5a0a-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span></span> <span data-ttu-id="d5a0a-107">Retaining only important, pertinent information is key to an organization's success.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-107">Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="d5a0a-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="d5a0a-109">Retention can be triggered by using [retention labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-109">Retention can be triggered by using [retention labels](labels.md).</span></span> <span data-ttu-id="d5a0a-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span></span> <span data-ttu-id="d5a0a-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span></span> <span data-ttu-id="d5a0a-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="d5a0a-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span></span> <span data-ttu-id="d5a0a-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="d5a0a-115">Event-based retention solves this problem.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-115">Event-based retention solves this problem.</span></span> <span data-ttu-id="d5a0a-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="d5a0a-117">Informazioni sulla conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="d5a0a-117">About event-based retention</span></span>

<span data-ttu-id="d5a0a-118">An organization can be small, medium, or large.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-118">An organization can be small, medium, or large.</span></span> <span data-ttu-id="d5a0a-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="d5a0a-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span></span> <span data-ttu-id="d5a0a-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span></span> <span data-ttu-id="d5a0a-122">This process is subject to the different retention policies outlined for the business:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-122">This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="d5a0a-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span></span> <span data-ttu-id="d5a0a-124">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-124">For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="d5a0a-125">**The period of retention of content can also be an unknown date**.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-125">**The period of retention of content can also be an unknown date**.</span></span> <span data-ttu-id="d5a0a-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="d5a0a-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span></span> <span data-ttu-id="d5a0a-128">This is called event-based retention.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-128">This is called event-based retention.</span></span> <span data-ttu-id="d5a0a-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="d5a0a-130">Configurare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="d5a0a-130">Set up event-based retention</span></span>

<span data-ttu-id="d5a0a-131">Questa sezione descrive le operazioni da eseguire prima della conservazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="d5a0a-132">Identificare i ruoli</span><span class="sxs-lookup"><span data-stu-id="d5a0a-132">Identify roles</span></span>

<span data-ttu-id="d5a0a-133">Identificare i diversi ruoli in un'organizzazione che eseguono attività di Gestione record e che sarebbero i responsabili della conservazione efficace ed efficiente dei documenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="d5a0a-134">Utente</span><span class="sxs-lookup"><span data-stu-id="d5a0a-134">Persona</span></span> | <span data-ttu-id="d5a0a-135">Ruolo</span><span class="sxs-lookup"><span data-stu-id="d5a0a-135">Role</span></span> |
  | - | - |
  | <span data-ttu-id="d5a0a-136">Amministratore</span><span class="sxs-lookup"><span data-stu-id="d5a0a-136">Admin</span></span> | <span data-ttu-id="d5a0a-137">Crea tipi di eventi di conservazione, etichette di conservazione e repository dei record in SharePoint</span><span class="sxs-lookup"><span data-stu-id="d5a0a-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="d5a0a-138">Responsabile della gestione dei record</span><span class="sxs-lookup"><span data-stu-id="d5a0a-138">Records Manager</span></span>                                  | <span data-ttu-id="d5a0a-139">Fornisce linee guida su criteri di conservazione e pianificazioni della conservazione, oltre a informazioni dettagliate sulla conformità</span><span class="sxs-lookup"><span data-stu-id="d5a0a-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="d5a0a-140">Amministratore di sistema (azienda)</span><span class="sxs-lookup"><span data-stu-id="d5a0a-140">System Admin (business)</span></span>                          | <span data-ttu-id="d5a0a-141">Configura e gestisce i sistemi esterni in modo da utilizzare Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d5a0a-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="d5a0a-142">Information Worker</span><span class="sxs-lookup"><span data-stu-id="d5a0a-142">Information Worker</span></span>                               | <span data-ttu-id="d5a0a-143">Gestisce il ciclo di vita del proprio processo aziendale (risorse umane, finanza, IT ecc.)</span><span class="sxs-lookup"><span data-stu-id="d5a0a-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="d5a0a-144">Configurare il Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d5a0a-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="d5a0a-145">L'amministratore di conformità crea un tipo di evento, &ndash;ad esempio Licenziamento dipendente, Scadenza contratto oppure Fine produzione.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="d5a0a-146">Vedere il processo dettagliato in [Conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="d5a0a-147">L'amministratore di conformità crea un'etichetta di conservazione in base a un evento e la associa a un tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="d5a0a-148">Ci sono quattro tipi di trigger per le etichette di conservazione:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="d5a0a-149">Data creazione</span><span class="sxs-lookup"><span data-stu-id="d5a0a-149">Create date</span></span>
                
    2. <span data-ttu-id="d5a0a-150">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="d5a0a-150">Last modified</span></span>
                
    3. <span data-ttu-id="d5a0a-151">Data etichetta (quando il contenuto è stato etichettato)</span><span class="sxs-lookup"><span data-stu-id="d5a0a-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="d5a0a-152">Basata su eventi</span><span class="sxs-lookup"><span data-stu-id="d5a0a-152">Event-based</span></span>
    
3. <span data-ttu-id="d5a0a-153">L'amministratore di conformità pubblica l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="d5a0a-154">Configurare SharePoint</span><span class="sxs-lookup"><span data-stu-id="d5a0a-154">Set up SharePoint</span></span>
   
<span data-ttu-id="d5a0a-155">Per creare un repository dei record, l'amministratore di conformità deve:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="d5a0a-156">Creare un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="d5a0a-157">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-157">Does one of the following:</span></span>
        
   - <span data-ttu-id="d5a0a-158">Creates a SharePoint library: Set event-based label at the library level.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-158">Creates a SharePoint library: Set event-based label at the library level.</span></span> <span data-ttu-id="d5a0a-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
   - <span data-ttu-id="d5a0a-160">Configura un set di documenti in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="d5a0a-161">Per ulteriori informazioni, vedere [Introduzione ai set di documenti](https://support.microsoft.com/it-IT/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-161">For more information, see [Introduction to document sets](https://support.microsoft.com/it-IT/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span></span>
      
3. <span data-ttu-id="d5a0a-162">Assegna un ID risorsa a ogni set di documenti dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="d5a0a-163">Un ID risorsa è il nome o codice di un prodotto usato dall'organizzazione, ad esempio il Numero dipendente può essere un ID risorsa.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="d5a0a-164">Assegnando l'ID risorsa alla cartella, ogni elemento nella cartella eredita automaticamente lo stesso ID risorsa.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="d5a0a-165">Di conseguenza, il periodo di conservazione di tutti gli elementi nella cartella sarà generato dallo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="d5a0a-166">Modi per attivare la conservazione basata su eventi</span><span class="sxs-lookup"><span data-stu-id="d5a0a-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="d5a0a-167">Esistono due modi in cui è possibile attivare la conservazione basata su eventi:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="d5a0a-168">**Uso dell'interfaccia di amministrazione** Si tratta di un processo che può essere sfruttato per conservare meno contenuto alla volta o per ridurre la frequenza di attivazione della conservazione e renderla, ad esempio, mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="d5a0a-169">Per ulteriori informazioni su questo processo, vedere [Panoramica della conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="d5a0a-170">Tuttavia, questo metodo di attivazione della conservazione può richiedere tempo e causare errori, e diminuire così la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="d5a0a-171">Di conseguenza, una soluzione automatica e semplice per attivare la conservazione può aumentare la sicurezza e la conformità dei dati.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="d5a0a-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span></span> <span data-ttu-id="d5a0a-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span></span> <span data-ttu-id="d5a0a-174">You don't need to manually create an event in the UI each time one occurs.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-174">You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="d5a0a-175">Sono disponibili due opzioni per usare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="d5a0a-176">**Microsoft Flow o delle applicazioni simili** possono essere usate per attivare automaticamente la ricorrenza di un evento.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="d5a0a-177">Microsoft Flow è un agente di orchestrazione per la connessione ad altri sistemi.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="d5a0a-178">L'uso di Microsoft Flow non richiede una soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="d5a0a-179">**PowerShell o un client HTTP per le chiamate all'API REST**: usare PowerShell (versione 6 o successive) per chiamare l'API REST di Microsoft 365 per creare eventi.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="d5a0a-180">Un'API Rest è un endpoint di servizio che supporta set di operazioni HTTP (metodi), che forniscono l'accesso alle risorse del servizio per la creazione, il ripristino, l’aggiornamento e l’eliminazione.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="d5a0a-181">Per altre informazioni, vedere [Componenti di una richiesta/risposta dell'API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="d5a0a-182">In questo caso, con l'API REST di Microsoft 365, è possibile creare e recuperare gli eventi usando le operazioni (metodi) POST e GET.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="d5a0a-183">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="d5a0a-183">Example scenarios</span></span>

<span data-ttu-id="d5a0a-184">Considerare i seguenti scenari.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="d5a0a-185">Scenario 1: Dipendenti che lasciano l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d5a0a-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="d5a0a-186">Un’organizzazione crea e archivia numerosi documenti relativi all’impiego di ogni singolo dipendente.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="d5a0a-187">Questi documenti sono gestiti e conservati durante il periodo di lavoro di ogni dipendente.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="d5a0a-188">Tuttavia, quando il dipendente lascia l'organizzazione o quando termina il periodo di lavoro, l'organizzazione è tenuta a rispettare i requisiti legali e aziendali e a mantenere i documenti di tale dipendente per un lasso di tempo concordato.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="d5a0a-189">Quindi, se più dipendenti lasciassero l'organizzazione ogni giorno, l'organizzazione dovrebbe attivare quotidianamente l'intervallo di conservazione per centinaia o migliaia di documenti.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="d5a0a-190">Oltre a tutto questo, occorre calcolare il periodo di conservazione per ciascun dipendente in base alla formula Data licenziamento dipendente + numero di giorni, mesi o anni in base al tipo di record del dipendente.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="d5a0a-191">Ad esempio, il periodo di conservazione dei documenti relativi alla retribuzione del lavoratore e ai benefit dipendenti potrebbe differire.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="d5a0a-192">Il diagramma di seguito illustra come possano essere presenti più etichette associate a un singolo evento.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="d5a0a-193">In questo caso, tutti i file con l’etichetta Assicurazione contro gli infortuni sul lavoro e tutti i file con l’etichetta Benefit dipendenti sono associati a un singolo evento, ossia il licenziamento del dipendente dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="d5a0a-194">Ognuno dei vari file ha intervalli di conservazione diversi.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="d5a0a-195">Quindi, quando un dipendente lascia l'organizzazione, i file raggruppati sotto ogni etichetta hanno un periodo di conservazione diverso.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="d5a0a-196">L'attivazione di tutti questi intervalli di conservazione, diversi per ogni tipo di file o etichetta e per ogni dipendente, è un'operazione molto complessa.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="d5a0a-197">Ancora di più lo è eseguire questa operazione per più dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-197">Imagine doing this for multiple employees.</span></span>

![Diagramma del tipo di evento, evento ed etichette](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="d5a0a-199">Di conseguenza, un processo automatizzato per attivare i diversi intervalli di conservazione per più dipendenti consente di risparmiare tempo, è privo di errori ed estremamente efficiente.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="d5a0a-200">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="d5a0a-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e azioni per lo scenario in cui il dipendente lascia l'organizzazione](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="d5a0a-202">L'amministratore crea le cartelle del dipendente nel set di documenti, ad esempio Angela Barbariol, Luca Udinesi.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="d5a0a-203">L'amministratore aggiunge i documenti dei dipendenti, ad esempio Benefit, Paghe, Assicurazione contro gli infortuni sul lavoro, a ogni cartella dipendente.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="d5a0a-204">L'amministratore assegna l'ID risorsa a ogni cartella dipendente.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="d5a0a-205">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="d5a0a-206">L'amministratore SCC crea tipi di eventi correlati al dipendente, come "Licenziamento del dipendente", "Assunzione del dipendente".</span><span class="sxs-lookup"><span data-stu-id="d5a0a-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="d5a0a-207">L'amministratore SCC crea l'etichetta "Conservazione dipendente".</span><span class="sxs-lookup"><span data-stu-id="d5a0a-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="d5a0a-208">L'etichetta "Conservazione dipendente" viene pubblicata e applicata manualmente o automaticamente ai documenti dei dipendenti in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="d5a0a-209">Un sistema di gestione delle risorse umane come Workday può eseguire periodicamente Microsoft Flow per gestire i documenti dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="d5a0a-210">Se un dipendente ha lasciato l'organizzazione, Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del dipendente specifico.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="d5a0a-211">Uso di Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="d5a0a-211">Using Microsoft Flow</span></span>

<span data-ttu-id="d5a0a-212">Passaggio 1: Creare un flusso per creare un evento usando le API REST di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d5a0a-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usare Flow per creare un evento](../media/automate-event-driven-retention-flow-1.png)

![Usare Flow per chiamare l'API REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="d5a0a-215">Creare un evento</span><span class="sxs-lookup"><span data-stu-id="d5a0a-215">Create an event</span></span>

<span data-ttu-id="d5a0a-216">Codice di esempio per chiamare l'API REST:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-216">Sample code to call the REST API:</span></span>

- <span data-ttu-id="d5a0a-217">**Metodo**: POST</span><span class="sxs-lookup"><span data-stu-id="d5a0a-217">**Method**: POST</span></span>
- <span data-ttu-id="d5a0a-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="d5a0a-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="d5a0a-219">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="d5a0a-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="d5a0a-220">**Corpo**:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-220">**Body**:</span></span>
    
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
- <span data-ttu-id="d5a0a-221">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="d5a0a-221">**Authentication**: Basic</span></span>
- <span data-ttu-id="d5a0a-222">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-222">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="d5a0a-223">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-223">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="d5a0a-224">Parametri disponibili</span><span class="sxs-lookup"><span data-stu-id="d5a0a-224">Available parameters</span></span>


|<span data-ttu-id="d5a0a-225">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5a0a-225">Parameters</span></span>|<span data-ttu-id="d5a0a-226">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5a0a-226">Description</span></span>|<span data-ttu-id="d5a0a-227">Note</span><span class="sxs-lookup"><span data-stu-id="d5a0a-227">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="d5a0a-228"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="d5a0a-228"><d:Name></d:Name></span></span>|<span data-ttu-id="d5a0a-229">Immettere un nome univoco per l'evento,</span><span class="sxs-lookup"><span data-stu-id="d5a0a-229">Provide a unique name for the event,</span></span>|<span data-ttu-id="d5a0a-230">Non può contenere spazi e i seguenti caratteri: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="d5a0a-230">Cannot contain trailing spaces, and the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="d5a0a-231">, : ;</span><span class="sxs-lookup"><span data-stu-id="d5a0a-231">, : ;</span></span>|
|<span data-ttu-id="d5a0a-232"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="d5a0a-232"><d:EventType></d:EventType></span></span>|<span data-ttu-id="d5a0a-233">Immettere il nome del tipo di evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="d5a0a-233">Enter event type name (or Guid),</span></span>|<span data-ttu-id="d5a0a-234">Example: “Employee termination”.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-234">Example: “Employee termination”.</span></span> <span data-ttu-id="d5a0a-235">Event type has to be associated with a retention label.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-235">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="d5a0a-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="d5a0a-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="d5a0a-237">Immettere "ComplianceAssetId:" + ID dipendente</span><span class="sxs-lookup"><span data-stu-id="d5a0a-237">Enter “ComplianceAssetId:” + employee Id</span></span>|<span data-ttu-id="d5a0a-238">Esempio: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-238">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="d5a0a-239"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="d5a0a-239"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="d5a0a-240">Data e ora evento</span><span class="sxs-lookup"><span data-stu-id="d5a0a-240">Event Date and Time</span></span>|<span data-ttu-id="d5a0a-241">Formato: aaaa-MM-ggTHH:mm:ssZ, esempio: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="d5a0a-241">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

##### <a name="response-codes"></a><span data-ttu-id="d5a0a-242">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="d5a0a-242">Response codes</span></span>

| <span data-ttu-id="d5a0a-243">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="d5a0a-243">Response Code</span></span> | <span data-ttu-id="d5a0a-244">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5a0a-244">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="d5a0a-245">302</span><span class="sxs-lookup"><span data-stu-id="d5a0a-245">302</span></span>               | <span data-ttu-id="d5a0a-246">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="d5a0a-246">Redirect</span></span>              |
| <span data-ttu-id="d5a0a-247">201</span><span class="sxs-lookup"><span data-stu-id="d5a0a-247">201</span></span>               | <span data-ttu-id="d5a0a-248">Creato</span><span class="sxs-lookup"><span data-stu-id="d5a0a-248">Created</span></span>               |
| <span data-ttu-id="d5a0a-249">403</span><span class="sxs-lookup"><span data-stu-id="d5a0a-249">403</span></span>               | <span data-ttu-id="d5a0a-250">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="d5a0a-250">Authorization Failed</span></span>  |
| <span data-ttu-id="d5a0a-251">401</span><span class="sxs-lookup"><span data-stu-id="d5a0a-251">401</span></span>               | <span data-ttu-id="d5a0a-252">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="d5a0a-252">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="d5a0a-253">Ricevere gli eventi in base all'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="d5a0a-253">Get Events based on time range</span></span>

- <span data-ttu-id="d5a0a-254">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="d5a0a-254">**Method**: GET</span></span>

- <span data-ttu-id="d5a0a-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="d5a0a-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="d5a0a-256">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="d5a0a-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="d5a0a-257">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="d5a0a-257">**Authentication**: Basic</span></span>

- <span data-ttu-id="d5a0a-258">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-258">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="d5a0a-259">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-259">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="d5a0a-260">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="d5a0a-260">Response codes</span></span>

| <span data-ttu-id="d5a0a-261">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="d5a0a-261">Response Code</span></span> | <span data-ttu-id="d5a0a-262">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5a0a-262">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="d5a0a-263">200</span><span class="sxs-lookup"><span data-stu-id="d5a0a-263">200</span></span>               | <span data-ttu-id="d5a0a-264">OK, un elenco di eventi in atom+ xml</span><span class="sxs-lookup"><span data-stu-id="d5a0a-264">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="d5a0a-265">404</span><span class="sxs-lookup"><span data-stu-id="d5a0a-265">404</span></span>               | <span data-ttu-id="d5a0a-266">Non trovato</span><span class="sxs-lookup"><span data-stu-id="d5a0a-266">Not found</span></span>                         |
| <span data-ttu-id="d5a0a-267">302</span><span class="sxs-lookup"><span data-stu-id="d5a0a-267">302</span></span>               | <span data-ttu-id="d5a0a-268">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="d5a0a-268">Redirect</span></span>                          |
| <span data-ttu-id="d5a0a-269">401</span><span class="sxs-lookup"><span data-stu-id="d5a0a-269">401</span></span>               | <span data-ttu-id="d5a0a-270">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="d5a0a-270">Authorization Failed</span></span>              |
| <span data-ttu-id="d5a0a-271">403</span><span class="sxs-lookup"><span data-stu-id="d5a0a-271">403</span></span>               | <span data-ttu-id="d5a0a-272">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="d5a0a-272">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="d5a0a-273">Ottenere un evento in base all'ID</span><span class="sxs-lookup"><span data-stu-id="d5a0a-273">Get an event by ID</span></span>

- <span data-ttu-id="d5a0a-274">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="d5a0a-274">**Method**: GET</span></span>

- <span data-ttu-id="d5a0a-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="d5a0a-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="d5a0a-276">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="d5a0a-276">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="d5a0a-277">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="d5a0a-277">**Authentication**: Basic</span></span>

- <span data-ttu-id="d5a0a-278">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-278">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="d5a0a-279">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-279">**Password**: "Compliancepassword"</span></span>



##### <a name="response-codes"></a><span data-ttu-id="d5a0a-280">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="d5a0a-280">Response codes</span></span>

| <span data-ttu-id="d5a0a-281">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="d5a0a-281">Response Code</span></span> | <span data-ttu-id="d5a0a-282">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5a0a-282">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="d5a0a-283">200</span><span class="sxs-lookup"><span data-stu-id="d5a0a-283">200</span></span>               | <span data-ttu-id="d5a0a-284">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="d5a0a-284">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="d5a0a-285">404</span><span class="sxs-lookup"><span data-stu-id="d5a0a-285">404</span></span>               | <span data-ttu-id="d5a0a-286">Non trovato</span><span class="sxs-lookup"><span data-stu-id="d5a0a-286">Not found</span></span>                                            |
| <span data-ttu-id="d5a0a-287">302</span><span class="sxs-lookup"><span data-stu-id="d5a0a-287">302</span></span>               | <span data-ttu-id="d5a0a-288">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="d5a0a-288">Redirect</span></span>                                             |
| <span data-ttu-id="d5a0a-289">401</span><span class="sxs-lookup"><span data-stu-id="d5a0a-289">401</span></span>               | <span data-ttu-id="d5a0a-290">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="d5a0a-290">Authorization Failed</span></span>                                 |
| <span data-ttu-id="d5a0a-291">403</span><span class="sxs-lookup"><span data-stu-id="d5a0a-291">403</span></span>               | <span data-ttu-id="d5a0a-292">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="d5a0a-292">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="d5a0a-293">Ottenere un evento in base al nome</span><span class="sxs-lookup"><span data-stu-id="d5a0a-293">Get an event by name</span></span>

- <span data-ttu-id="d5a0a-294">**Metodo**: ottieni</span><span class="sxs-lookup"><span data-stu-id="d5a0a-294">**Method**: GET</span></span>

- <span data-ttu-id="d5a0a-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="d5a0a-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="d5a0a-296">**Intestazioni**: Chiave = Content-Type, Valore = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="d5a0a-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="d5a0a-297">**Autenticazione**: di base</span><span class="sxs-lookup"><span data-stu-id="d5a0a-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="d5a0a-298">**Nome utente**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="d5a0a-299">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="d5a0a-299">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="d5a0a-300">Codici di risposta</span><span class="sxs-lookup"><span data-stu-id="d5a0a-300">Response codes</span></span>

| <span data-ttu-id="d5a0a-301">Codice di risposta</span><span class="sxs-lookup"><span data-stu-id="d5a0a-301">Response Code</span></span> | <span data-ttu-id="d5a0a-302">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5a0a-302">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="d5a0a-303">200</span><span class="sxs-lookup"><span data-stu-id="d5a0a-303">200</span></span>               | <span data-ttu-id="d5a0a-304">OK, il corpo della risposta contiene l'evento in atom+xml</span><span class="sxs-lookup"><span data-stu-id="d5a0a-304">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="d5a0a-305">404</span><span class="sxs-lookup"><span data-stu-id="d5a0a-305">404</span></span>               | <span data-ttu-id="d5a0a-306">Non trovato</span><span class="sxs-lookup"><span data-stu-id="d5a0a-306">Not found</span></span>                                            |
| <span data-ttu-id="d5a0a-307">302</span><span class="sxs-lookup"><span data-stu-id="d5a0a-307">302</span></span>               | <span data-ttu-id="d5a0a-308">Reindirizzare</span><span class="sxs-lookup"><span data-stu-id="d5a0a-308">Redirect</span></span>                                             |
| <span data-ttu-id="d5a0a-309">401</span><span class="sxs-lookup"><span data-stu-id="d5a0a-309">401</span></span>               | <span data-ttu-id="d5a0a-310">Autorizzazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="d5a0a-310">Authorization Failed</span></span>                                 |
| <span data-ttu-id="d5a0a-311">403</span><span class="sxs-lookup"><span data-stu-id="d5a0a-311">403</span></span>               | <span data-ttu-id="d5a0a-312">Autenticazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="d5a0a-312">Authentication Failed</span></span>                                |

#### <a name="using-powershell-version-6-or-later-or-any-http-client"></a><span data-ttu-id="d5a0a-313">Uso di PowerShell (versione 6 o successiva) o qualsiasi client HTTP</span><span class="sxs-lookup"><span data-stu-id="d5a0a-313">Using PowerShell (version 6 or later) or any HTTP client</span></span>

<span data-ttu-id="d5a0a-314">Passaggio 1: Connettersi a PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-314">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="d5a0a-315">Passaggio 2: Eseguire lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-315">Step 2: Run the following script.</span></span>

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


#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="d5a0a-316">Verificare il risultato in entrambe le opzioni</span><span class="sxs-lookup"><span data-stu-id="d5a0a-316">Verify the outcome in both options</span></span>

<span data-ttu-id="d5a0a-317">Passaggio 1: Passare al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-317">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="d5a0a-318">Passaggio 2: Scegliere **Eventi** in **Governance delle informazioni**.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-318">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="d5a0a-319">Passaggio 3: Verificare di aver creato l'evento.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-319">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="d5a0a-320">È possibile usare le opzioni precedenti per automatizzare la conservazione basata sugli eventi anche per gli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-320">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="d5a0a-321">Scenario 2: Contratti in scadenza</span><span class="sxs-lookup"><span data-stu-id="d5a0a-321">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="d5a0a-322">Un'organizzazione può avere più record per un singolo contratto con clienti, fornitori e partner.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-322">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="d5a0a-323">Questi documenti possono trovarsi in una raccolta documenti come SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-323">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="d5a0a-324">Il termine di un contratto determina l'inizio del periodo di conservazione dei documenti associati al contratto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-324">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="d5a0a-325">Ad esempio, tutti i record relativi ai contratti devono essere conservati per cinque anni dalla data di scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-325">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="d5a0a-326">L'evento che attiva il periodo di conservazione di cinque anni è la scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-326">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="d5a0a-327">Un sistema di Customer Relationship Management (CRM) può interagire con Microsoft 365 e attivare la conservazione dei documenti contrattuali.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-327">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents.</span></span>

<span data-ttu-id="d5a0a-328">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="d5a0a-328">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e attività per scenari di scadenza contratto](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="d5a0a-330">L'amministratore crea una raccolta di SharePoint con varie cartelle per ogni tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-330">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="d5a0a-331">L'amministratore aggiunge i documenti contrattuali, ad esempio Contratti di licenza e Contratti di sviluppo, a ogni cartella di contratto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-331">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="d5a0a-332">L'amministratore assegna l'ID risorsa a ogni cartella di contratto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-332">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="d5a0a-333">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-333">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="d5a0a-334">L'amministratore SCC crea tipi di eventi correlati al contratto, come "Creazione contratto" o "Scadenza contratto".</span><span class="sxs-lookup"><span data-stu-id="d5a0a-334">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="d5a0a-335">L'amministratore SCC crea l'etichetta "Scadenza contratto".</span><span class="sxs-lookup"><span data-stu-id="d5a0a-335">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="d5a0a-336">L'etichetta "Scadenza contratto" viene pubblicata e applicata manualmente o automaticamente ai documenti contrattuali in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-336">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="d5a0a-337">Il sistema di gestione dei contratti può eseguire periodicamente Microsoft Flow o un'applicazione simile per gestire i documenti contrattuali.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-337">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="d5a0a-338">Se un contratto scade, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-338">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="d5a0a-339">Scenario 3: Fine produzione</span><span class="sxs-lookup"><span data-stu-id="d5a0a-339">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="d5a0a-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span></span> <span data-ttu-id="d5a0a-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="d5a0a-342">Un sistema ERP (Enterprise Resource Planning) può utilizzare Microsoft 365 e Microsoft Flow per attivare la conservazione.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-342">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="d5a0a-343">**Configurazione della conservazione basata su eventi automatizzata per questo scenario:**</span><span class="sxs-lookup"><span data-stu-id="d5a0a-343">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramma di ruoli e attività per uno scenario di ciclo di vita del prodotto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="d5a0a-345">L'amministratore crea delle cartelle di prodotto nel set di documenti, ad esempio Prodotto 1, Prodotto 2, ecc.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-345">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="d5a0a-346">L'amministratore aggiunge i documenti del prodotto, ad esempio Specifiche di produzione, Prezzi del prodotto, Licenze del prodotto a ogni cartella.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-346">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="d5a0a-347">L'amministratore assegna l'ID risorsa a ogni cartella di prodotto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-347">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="d5a0a-348">L'amministratore SCC accede al Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-348">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="d5a0a-349">L'amministratore SCC crea tipi di eventi correlati al prodotto, come "Inizio produzione", "Fine produzione".</span><span class="sxs-lookup"><span data-stu-id="d5a0a-349">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="d5a0a-350">L'amministratore SCC crea l'etichetta "Fine produzione".</span><span class="sxs-lookup"><span data-stu-id="d5a0a-350">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="d5a0a-351">L'etichetta "Fine produzione" viene pubblicata e applicata manualmente o automaticamente ai documenti del prodotto in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-351">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="d5a0a-352">I sistemi ERP possono eseguire periodicamente Microsoft Flow o applicazioni simili per gestire i documenti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-352">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="d5a0a-353">Se un prodotto esce fuori produzione, Microsoft Flow attiverà l'API REST di conservazione basata sugli eventi di M365 che avvierà l'intervallo di conservazione nei documenti del prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-353">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="d5a0a-354">Appendice</span><span class="sxs-lookup"><span data-stu-id="d5a0a-354">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="d5a0a-355">Uso dei risultati della risposta Redirect 302 per chiamare l'API REST</span><span class="sxs-lookup"><span data-stu-id="d5a0a-355">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="d5a0a-356">Chiamare un evento di conservazione POST usando l'URL dell'API REST: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="d5a0a-356">Invoke a POST retention event call by using the REST API URL: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
    
    <span data-ttu-id="d5a0a-357">Sono necessarie le autorizzazioni dell'amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-357">Global administrator permissions are required.</span></span>

2. <span data-ttu-id="d5a0a-358">Controllare il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-358">Check the response code.</span></span> <span data-ttu-id="d5a0a-359">Se è 302, ottenere l'URL reindirizzato dalla proprietà Posizione dell'intestazione della risposta.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-359">If it's 302, then get the redirected URL from Location property of the response header.</span></span>

3. <span data-ttu-id="d5a0a-360">Chiamare nuovamente l'evento di conservazione POST usando l'URL reindirizzato.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-360">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="d5a0a-361">Riconoscimenti</span><span class="sxs-lookup"><span data-stu-id="d5a0a-361">Credits</span></span>

<span data-ttu-id="d5a0a-362">Questo argomento è stato rivisto da:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-362">This topic was reviewed by:</span></span>

<span data-ttu-id="d5a0a-363">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="d5a0a-363">Antonio Maio</span></span><br/><span data-ttu-id="d5a0a-364">MVP App e servizi di Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="d5a0a-364">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="d5a0a-365">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="d5a0a-365">Antonio.Maio@Protiviti.com</span></span>
