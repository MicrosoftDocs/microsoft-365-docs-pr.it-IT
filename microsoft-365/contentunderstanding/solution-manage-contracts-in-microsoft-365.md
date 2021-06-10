---
title: Gestire i contratti con una soluzione Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Scopri come gestire i contratti usando una Microsoft 365 di SharePoint Syntex, SharePoint Lists, Microsoft Teams e Power Automate.
ms.openlocfilehash: 352ebd1b9170aaf7829c414e87f7a79c4f17a1df
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843771"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="0183b-103">Gestire i contratti con una soluzione Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0183b-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="0183b-104">In questo articolo viene descritto come creare una soluzione di gestione dei contratti per l'organizzazione utilizzando SharePoint Syntex e i componenti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0183b-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="0183b-105">Offre un framework che consente di pianificare e creare una soluzione adatta alle esigenze aziendali specifiche.</span><span class="sxs-lookup"><span data-stu-id="0183b-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="0183b-106">Anche se questa soluzione non soddisfa le esigenze aziendali nel suo complesso, alcune parti di essa possono essere adottate nella pianificazione per creare una soluzione di gestione dei contratti personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0183b-106">Even if this solution doesn't suit your business needs as a whole, parts of it can be adopted in your planning to create a custom contract management solution.</span></span>

<span data-ttu-id="0183b-107">*Questo set di contenuti documenta una Microsoft 365 soluzione sviluppata da Thomas Molbach con il team modern work solution strategy di Microsoft.*</span><span class="sxs-lookup"><span data-stu-id="0183b-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="0183b-108">Identificare il problema aziendale</span><span class="sxs-lookup"><span data-stu-id="0183b-108">Identify the business problem</span></span>

<span data-ttu-id="0183b-109">Il primo passaggio nella pianificazione del sistema di gestione dei contratti consiste nel comprendere il problema che si sta tentando di risolvere.</span><span class="sxs-lookup"><span data-stu-id="0183b-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="0183b-110">Per questa soluzione, è necessario risolvere quattro problemi chiave:</span><span class="sxs-lookup"><span data-stu-id="0183b-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="0183b-111">**Identificare i contratti**.</span><span class="sxs-lookup"><span data-stu-id="0183b-111">**Identify contracts**.</span></span> <span data-ttu-id="0183b-112">L'organizzazione lavora con molti documenti, ad esempio fatture, contratti, dichiarazioni di lavoro e così via.</span><span class="sxs-lookup"><span data-stu-id="0183b-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="0183b-113">Alcuni sono asset digitali inviati tramite posta elettronica e altri sono asset cartacei inviati tramite posta tradizionale.</span><span class="sxs-lookup"><span data-stu-id="0183b-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="0183b-114">È necessario un modo per identificare tutti i contratti dei clienti da tutti gli altri documenti e classificarli come tali.</span><span class="sxs-lookup"><span data-stu-id="0183b-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="0183b-115">**Tenere traccia della cronologia delle approvazioni dei contratti.**</span><span class="sxs-lookup"><span data-stu-id="0183b-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="0183b-116">L'organizzazione necessita di un modo affidabile per stabilire se i contratti sono stati approvati o rifiutati e se il pagamento è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="0183b-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="0183b-117">**Sito per la gestione delle approvazioni dei contratti.**</span><span class="sxs-lookup"><span data-stu-id="0183b-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="0183b-118">L'organizzazione deve configurare un sito di collaborazione in cui tutti gli stakeholder necessari possano esaminare facilmente i contratti.</span><span class="sxs-lookup"><span data-stu-id="0183b-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="0183b-119">Le parti interessate dovrebbero essere in grado di esaminare l'intero contratto, se necessario, ma soprattutto di visualizzare diversi campi chiave di ogni contratto (ad esempio, nome del cliente, numero di ordine di acquisto e costo totale).</span><span class="sxs-lookup"><span data-stu-id="0183b-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="0183b-120">Le parti interessate dovrebbero essere in grado di approvare o rifiutare facilmente i contratti in arrivo.</span><span class="sxs-lookup"><span data-stu-id="0183b-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="0183b-121">**Route reviewed contracts**.</span><span class="sxs-lookup"><span data-stu-id="0183b-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="0183b-122">I contratti approvati e rifiutati devono essere instradati tramite un flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="0183b-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="0183b-123">I contratti approvati devono essere instradati a una domanda di terze parti per l'elaborazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="0183b-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="0183b-124">I contratti rifiutati devono essere instradati per un'ulteriore revisione.</span><span class="sxs-lookup"><span data-stu-id="0183b-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="0183b-125">Panoramica della soluzione</span><span class="sxs-lookup"><span data-stu-id="0183b-125">Overview of the solution</span></span>

  ![Diagramma della soluzione con SharePoint Syntex, SharePoint, Teams e Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="0183b-127">Questa guida alla soluzione di gestione dei contratti include quattro componenti di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="0183b-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="0183b-128">**Microsoft SharePoint Syntex:** creare modelli per identificare e classificare i file di contratto e quindi estrarre i dati appropriati da essi.</span><span class="sxs-lookup"><span data-stu-id="0183b-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="0183b-129">**Elenchi SharePoint Microsoft**: utilizzare la formattazione disponibile negli elenchi SharePoint moderni per presentare i contratti in un formato per le aziende.</span><span class="sxs-lookup"><span data-stu-id="0183b-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="0183b-130">**Microsoft Teams**: utilizzare la funzionalità di un canale Teams e le schede associate per consentire agli stakeholder di rivedere e gestire i contratti.</span><span class="sxs-lookup"><span data-stu-id="0183b-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="0183b-131">**Power Automate**: utilizzare i flussi per guidare i contratti attraverso il processo di approvazione e quindi a una richiesta di pagamento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0183b-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="0183b-132">Come funziona tutto</span><span class="sxs-lookup"><span data-stu-id="0183b-132">How it all works</span></span>

  ![Diagramma della soluzione che mostra il flusso di lavoro per caricare documenti, estrarre dati, inviare notifiche alle parti interessate e approvare o rifiutare il contratto.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="0183b-134">I documenti vengono caricati in una SharePoint raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="0183b-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="0183b-135">Un SharePoint di comprensione dei documenti Syntex è stato applicato alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="0183b-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="0183b-136">Controlla ogni file per verificare se una corrispondenza a un tipo di contenuto "contratto" è stata addestrata per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0183b-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="0183b-137">Se trova una corrispondenza, classifica il file come "contratto" e aggiorna il tipo di contenuto per il documento.</span><span class="sxs-lookup"><span data-stu-id="0183b-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="0183b-138">Il modello estrae anche dati specifici da ogni file di contratto che gli stakeholder sono interessati a visualizzare, ad esempio *l'importo del cliente,* del *terzista e della commissione.*</span><span class="sxs-lookup"><span data-stu-id="0183b-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="0183b-139">La pagina seguente è un esempio di un contratto che il modello ha preparato per identificare.</span><span class="sxs-lookup"><span data-stu-id="0183b-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![Esempio di contratto.](../media/content-understanding/contract.png)

3. <span data-ttu-id="0183b-141">In Microsoft Teams, tutte le parti interessate sono membri di un canale Teams sicuro in cui tutti i contratti nella raccolta documenti sono visibili per l'approvazione o il rifiuto.</span><span class="sxs-lookup"><span data-stu-id="0183b-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="0183b-142">Utilizzando la Teams, tutte le parti interessate vengono avvisate quando è necessario rivedere i nuovi contratti.</span><span class="sxs-lookup"><span data-stu-id="0183b-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>
 
4. <span data-ttu-id="0183b-143">Utilizzando il Power Automate, i contratti vengono spostati attraverso il processo di approvazione nel Teams canale.</span><span class="sxs-lookup"><span data-stu-id="0183b-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="0183b-144">Quando un membro approva un contratto, lo stato del contratto viene modificato per l'approvazione, tutti i membri vengono informati tramite un post di Teams e viene creata una voce per mostrare che il contratto è pronto per i pagamenti.</span><span class="sxs-lookup"><span data-stu-id="0183b-144">When a member approves a contract, the contract status is changed to approve, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="0183b-145">Questo processo può essere esteso per scrivere direttamente a un'applicazione finanziaria di terze parti per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="0183b-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5.  <span data-ttu-id="0183b-146">Quando un membro rifiuta un contratto, lo stato viene modificato in rifiutato e tutti i membri vengono avvisati tramite un Teams post.</span><span class="sxs-lookup"><span data-stu-id="0183b-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="0183b-147">Il risultato finale di questa soluzione è un processo aziendale automatizzato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0183b-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="0183b-148">I dipendenti possono usare facilmente la visualizzazione dei riquadri personalizzati in Teams per avviare e monitorare il flusso di lavoro di approvazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="0183b-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![Scheda Contratti.](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a><span data-ttu-id="0183b-150">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="0183b-150">Licensing requirements</span></span>

<span data-ttu-id="0183b-151">Questa soluzione si basa sulle funzionalità seguenti, tutte disponibili nell'ambito di una licenza di Microsoft 365 Enterprise (E1, E3, E5, F3) o Business (Basic, Standard o Premium):</span><span class="sxs-lookup"><span data-stu-id="0183b-151">This solution relies on the following functionality, all available as part of a Microsoft 365 Enterprise (E1, E3, E5, F3) or Business (Basic, Standard, or Premium) license:</span></span>

-   <span data-ttu-id="0183b-152">Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0183b-152">Microsoft SharePoint Syntex</span></span>
-   <span data-ttu-id="0183b-153">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0183b-153">Microsoft Teams</span></span>
-   <span data-ttu-id="0183b-154">Power Automate</span><span class="sxs-lookup"><span data-stu-id="0183b-154">Power Automate</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="0183b-155">Creare la soluzione</span><span class="sxs-lookup"><span data-stu-id="0183b-155">Create the solution</span></span>

<span data-ttu-id="0183b-156">Nelle sezioni successive verranno fornite informazioni dettagliate su come configurare la soluzione di gestione dei contratti.</span><span class="sxs-lookup"><span data-stu-id="0183b-156">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="0183b-157">È suddiviso in tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="0183b-157">It's divided into three steps:</span></span>

- [<span data-ttu-id="0183b-158">Passaggio 1. Usare SharePoint Syntex per identificare i file di contratto ed estrarre i dati</span><span class="sxs-lookup"><span data-stu-id="0183b-158">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="0183b-159">Passaggio 2. Usare Microsoft Teams per creare il canale di gestione dei contratti</span><span class="sxs-lookup"><span data-stu-id="0183b-159">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="0183b-160">Passaggio 3. Usare Power Automate per creare il flusso per elaborare i contratti</span><span class="sxs-lookup"><span data-stu-id="0183b-160">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
