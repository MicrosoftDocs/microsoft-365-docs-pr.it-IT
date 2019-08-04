---
title: Strategie di distribuzione dell'infrastruttura di base di Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su alcuni modi in cui è possibile distribuire le fasi dell'infrastruttura di base di Microsoft 365 Enterprise.
ms.openlocfilehash: 2c30420390be97d33f66888eac533b89c907b3b2
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073886"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="9734c-103">Strategie di distribuzione dell'infrastruttura di base di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9734c-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="9734c-p101">Per distribuire le fasi dell'[infrastruttura di base](deploy-foundation-infrastructure.md) di Microsoft 365 Enterprise e implementarne le capacità, il software e i servizi agli utenti, è possibile scegliere tra numerose opzioni. Per iniziare a gestire i progetti di questa attività, che può essere lunga e complessa a seconda delle dimensioni dell'organizzazione e dell'infrastruttura esistente, prendere in considerazione le strategie di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="9734c-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="9734c-106">Distribuzione seriale</span><span class="sxs-lookup"><span data-stu-id="9734c-106">Serial deployment</span></span>
- <span data-ttu-id="9734c-107">Distribuzione in parallelo con implementazione utente senza sovrapposizione</span><span class="sxs-lookup"><span data-stu-id="9734c-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="9734c-108">Distribuzione in parallelo con implementazione utente con sovrapposizione</span><span class="sxs-lookup"><span data-stu-id="9734c-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="9734c-109">Infrastruttura predisposta in precedenza e implementazione della configurazione end-to-end</span><span class="sxs-lookup"><span data-stu-id="9734c-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="9734c-110">Usare queste strategie come suggerimenti su come gestire l'intero progetto e comprendere più rapidamente i vantaggi offerti da Microsoft 365 Enterprise per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="9734c-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="9734c-p102">Questo articolo contiene ipotesi e semplificazioni per descrivere in modo coerente le strategie di distribuzione. Queste strategie sono generalizzate, di conseguenza non implicano tempistiche specifiche, né possono essere considerate valide per qualsiasi situazione e organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9734c-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="9734c-113">Elementi della gestione dei progetti IT per organizzazioni aziendali standard</span><span class="sxs-lookup"><span data-stu-id="9734c-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="9734c-p103">L'infrastruttura IT include i servizi back-end e l'implementazione di funzionalità nuove o migliorate oppure di software installato per gli utenti finali. I reparti IT distribuiscono in genere gli elementi di un'infrastruttura IT in modo sistematico. Un approccio per la corretta distribuzione di un elemento dell'infrastruttura IT prevede:</span><span class="sxs-lookup"><span data-stu-id="9734c-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="9734c-117">Un'implementazione pilota</span><span class="sxs-lookup"><span data-stu-id="9734c-117">A pilot rollout</span></span> 

  <span data-ttu-id="9734c-118">Include la configurazione e l'implementazione dell'infrastruttura iniziale per un set pilota di utenti, l'esecuzione di test e le successive modifiche alla configurazione dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="9734c-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="9734c-119">Un'implementazione utente</span><span class="sxs-lookup"><span data-stu-id="9734c-119">A user rollout</span></span>

  <span data-ttu-id="9734c-120">Include l'implementazione nel resto dell'organizzazione in base ad aree geografiche, reparti, gruppi o altri tipi di propagazione sistematica della configurazione o del software.</span><span class="sxs-lookup"><span data-stu-id="9734c-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="9734c-121">Il set di utenti nell'implementazione pilota non è uguale a quello dell'implementazione utente.</span><span class="sxs-lookup"><span data-stu-id="9734c-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="9734c-122">Per illustrare queste definizioni, in questo articolo si usano le immagini seguenti:</span><span class="sxs-lookup"><span data-stu-id="9734c-122">This article uses the following graphics to depict these definitions:</span></span> 

![](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="9734c-123">L'ombreggiatura nell'immagine relativa all'implementazione utente indica la percentuale di implementazione (da 0% a 100%) nell'organizzazione usando un approccio strutturato o metodico, ad esempio per gruppi, reparti o aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="9734c-123">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="9734c-124">Strategie di distribuzione</span><span class="sxs-lookup"><span data-stu-id="9734c-124">Deployment strategies</span></span>

<span data-ttu-id="9734c-125">Prendere in considerazione le strategie di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="9734c-125">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="9734c-126">Distribuzione seriale</span><span class="sxs-lookup"><span data-stu-id="9734c-126">Serial deployment</span></span>
- <span data-ttu-id="9734c-127">Distribuzione in parallelo con implementazione utente senza sovrapposizione</span><span class="sxs-lookup"><span data-stu-id="9734c-127">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="9734c-128">Distribuzione in parallelo con implementazione utente con sovrapposizione</span><span class="sxs-lookup"><span data-stu-id="9734c-128">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="9734c-129">Infrastruttura predisposta in precedenza e implementazione della configurazione end-to-end</span><span class="sxs-lookup"><span data-stu-id="9734c-129">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="9734c-130">Distribuzione seriale</span><span class="sxs-lookup"><span data-stu-id="9734c-130">Serial deployment</span></span>

<span data-ttu-id="9734c-p104">Con una distribuzione seriale si implementa completamente una fase, ovvero si consente alla fase di completare la distribuzione per tutti gli utenti, prima di passare a quella successiva. Ecco alcuni dei motivi per cui è consigliabile eseguire la distribuzione in questo modo:</span><span class="sxs-lookup"><span data-stu-id="9734c-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="9734c-133">Riduzione dei rischi</span><span class="sxs-lookup"><span data-stu-id="9734c-133">Risk mitigation</span></span>
- <span data-ttu-id="9734c-134">Vincoli relativi alla gestione delle risorse</span><span class="sxs-lookup"><span data-stu-id="9734c-134">Resourcing constraints</span></span>
- <span data-ttu-id="9734c-135">Cicli di finanziamento del reparto IT</span><span class="sxs-lookup"><span data-stu-id="9734c-135">IT department funding cycles</span></span>
- <span data-ttu-id="9734c-136">Dipendenze delle tecnologie IT</span><span class="sxs-lookup"><span data-stu-id="9734c-136">IT technology dependencies</span></span>
- <span data-ttu-id="9734c-137">Gestione delle modifiche aziendali e riluttanza degli utenti finali</span><span class="sxs-lookup"><span data-stu-id="9734c-137">Business change management and end-user resistance</span></span>

<span data-ttu-id="9734c-138">Questo diagramma di Gantt mostra una distribuzione seriale semplificata delle fasi 2-6 dell'infrastruttura di base per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9734c-138">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="9734c-139">Per semplificare la discussione e l'esempio, si presuppone che ogni fase e ogni segmento di distribuzione all'interno di ogni fase richieda lo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="9734c-139">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="9734c-p105">Fase 1: la connessione dell'infrastruttura di base di Microsoft 365 Enterprise è una fase di competenza esclusiva del reparto IT. Gli utenti possono usufruire dei vantaggi di una connettività ottimizzata alle risorse cloud di Microsoft, ma non sono obbligati a farlo.</span><span class="sxs-lookup"><span data-stu-id="9734c-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="9734c-142">Esperienza utente pilota semplificata di esempio:</span><span class="sxs-lookup"><span data-stu-id="9734c-142">Simplified example pilot user experience:</span></span>

- <span data-ttu-id="9734c-p106">A dicembre si deve usare lo smartphone personale per la MFA. (Identity)</span><span class="sxs-lookup"><span data-stu-id="9734c-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="9734c-p107">A marzo si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="9734c-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="9734c-p108">A giugno si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="9734c-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="9734c-p109">A settembre si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)</span><span class="sxs-lookup"><span data-stu-id="9734c-p109">In September, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="9734c-p110">A dicembre si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="9734c-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="9734c-153">Ne risulta una cadenza di 90 giorni tra due implementazioni pilota.</span><span class="sxs-lookup"><span data-stu-id="9734c-153">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="9734c-154">Esperienza utente finale semplificata di esempio:</span><span class="sxs-lookup"><span data-stu-id="9734c-154">Simplified example end-user experience:</span></span>

- <span data-ttu-id="9734c-p111">A gennaio si deve usare lo smartphone personale per la MFA. (Identity)</span><span class="sxs-lookup"><span data-stu-id="9734c-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="9734c-p112">Ad aprile si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="9734c-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="9734c-p113">A luglio si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="9734c-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="9734c-p114">A ottobre si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)</span><span class="sxs-lookup"><span data-stu-id="9734c-p114">In October, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="9734c-p115">A gennaio dell'anno successivo si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="9734c-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="9734c-165">Ne risulta una cadenza di 90 giorni tra due implementazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9734c-165">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="9734c-166">Lo svantaggio di questa strategia di distribuzione è che la distribuzione completa dell'infrastruttura di base di Microsoft 365 Enterprise può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="9734c-166">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="9734c-167">Distribuzione in parallelo con implementazione utente senza sovrapposizione (in parallelo 1)</span><span class="sxs-lookup"><span data-stu-id="9734c-167">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="9734c-p116">Per questa strategia di distribuzione si avvia l'implementazione pilota della fase successiva durante l'ultima parte dell'implementazione utente della fase corrente. Ecco la distribuzione delle fasi 2-6 quando l'implementazione pilota viene avviata quando l'implementazione utente della fase precedente sta per terminare.</span><span class="sxs-lookup"><span data-stu-id="9734c-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

<span data-ttu-id="9734c-170">Ecco un confronto semplificato tra le strategie di distribuzione seriale e in parallelo.</span><span class="sxs-lookup"><span data-stu-id="9734c-170">Here is a simplified comparison between parallel and serial deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="9734c-p117">Il risultato finale è che l'implementazione utente per la fase corrente viene completata in tutta l'organizzazione prima dell'avvio di quella successiva. Gli utenti che non sono inclusi nelle implementazioni pilota non devono gestire le implementazioni di più fasi contemporaneamente, ma le implementazioni pilota vengano eseguite in parallelo con quelle utente.</span><span class="sxs-lookup"><span data-stu-id="9734c-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="9734c-173">Esperienza utente pilota semplificata di esempio:</span><span class="sxs-lookup"><span data-stu-id="9734c-173">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="9734c-p118">A dicembre si deve usare lo smartphone personale per la MFA. (Identity)</span><span class="sxs-lookup"><span data-stu-id="9734c-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="9734c-p119">A febbraio si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="9734c-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="9734c-p120">Ad aprile si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="9734c-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="9734c-p121">A giugno si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)</span><span class="sxs-lookup"><span data-stu-id="9734c-p121">In June, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="9734c-p122">Ad agosto si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="9734c-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="9734c-184">Ne risulta una cadenza di 60 giorni tra due implementazioni pilota.</span><span class="sxs-lookup"><span data-stu-id="9734c-184">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="9734c-185">Esperienza utente finale semplificata di esempio:</span><span class="sxs-lookup"><span data-stu-id="9734c-185">Simplified example end-user experience:</span></span>

- <span data-ttu-id="9734c-p123">A gennaio si deve usare lo smartphone personale per la MFA. (Identity)</span><span class="sxs-lookup"><span data-stu-id="9734c-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="9734c-p124">A marzo si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="9734c-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="9734c-p125">A maggio si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="9734c-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="9734c-p126">A luglio si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)</span><span class="sxs-lookup"><span data-stu-id="9734c-p126">In July, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="9734c-p127">A settembre si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="9734c-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="9734c-196">Ne risulta una cadenza di 60 giorni tra due implementazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9734c-196">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="9734c-197">Il vantaggio di questa strategia di distribuzione è che può richiedere meno tempo per distribuire completamente l'infrastruttura di base di Microsoft 365 Enterprise, senza che il reparto IT e gli utenti debbano gestire più implementazioni contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9734c-197">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="9734c-198">Distribuzione in parallelo con implementazione utente con sovrapposizione (in parallelo 2)</span><span class="sxs-lookup"><span data-stu-id="9734c-198">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="9734c-199">Per questa strategia di distribuzione si avviano:</span><span class="sxs-lookup"><span data-stu-id="9734c-199">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="9734c-200">L'implementazione pilota della fase successiva durante l'ultima parte dell'implementazione utente della fase corrente.</span><span class="sxs-lookup"><span data-stu-id="9734c-200">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="9734c-p128">L'implementazione utente della fase successiva durante l'implementazione utente della fase corrente in modo che nessun utente debba gestire l'implementazione di più fasi contemporaneamente. Questa operazione presuppone che ogni fase dell'infrastruttura di base venga implementata nello stesso modo, tramite aree geografiche, reparti o altri criteri.</span><span class="sxs-lookup"><span data-stu-id="9734c-p128">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time. This assumes that you are rolling out each phase of the foundation infrastructure in the same way, via regions, departments, or other.</span></span>

<span data-ttu-id="9734c-203">Ecco un confronto semplificato tra le diverse strategie di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9734c-203">Here is a simplified comparison between the different deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="9734c-204">Il risultato finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="9734c-204">The end result is that:</span></span>

- <span data-ttu-id="9734c-205">Le implementazioni pilota passano da una fase all'altra senza pause.</span><span class="sxs-lookup"><span data-stu-id="9734c-205">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="9734c-206">L'implementazione utente per una fase inizia prima del completamento dell'implementazione utente della fase precedente, ma nessun singolo utente implementa più di una fase alla volta.</span><span class="sxs-lookup"><span data-stu-id="9734c-206">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="9734c-207">Esperienza utente pilota semplificata di esempio:</span><span class="sxs-lookup"><span data-stu-id="9734c-207">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="9734c-p129">A dicembre si deve usare lo smartphone personale per la MFA. (Identity)</span><span class="sxs-lookup"><span data-stu-id="9734c-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="9734c-p130">A gennaio si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="9734c-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="9734c-p131">A febbraio si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="9734c-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="9734c-p132">A marzo si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)</span><span class="sxs-lookup"><span data-stu-id="9734c-p132">In March, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="9734c-p133">Ad aprile si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="9734c-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="9734c-218">Ne risulta una cadenza di 30 giorni tra due implementazioni pilota.</span><span class="sxs-lookup"><span data-stu-id="9734c-218">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="9734c-219">Esperienza utente finale semplificata di esempio:</span><span class="sxs-lookup"><span data-stu-id="9734c-219">Simplified example end-user experience:</span></span>

- <span data-ttu-id="9734c-p134">A gennaio si deve usare lo smartphone personale per la MFA. (Identity)</span><span class="sxs-lookup"><span data-stu-id="9734c-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="9734c-p135">A febbraio si installa Windows 10 Enterprise nel desktop Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="9734c-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="9734c-p136">A marzo si installa Office 365 ProPlus, in sostituzione di Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="9734c-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="9734c-p137">Ad aprile si applicano i criteri di accesso condizionale e alle app e di registrazione dei dispositivi. (Gestione dispositivi mobili)</span><span class="sxs-lookup"><span data-stu-id="9734c-p137">In April, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="9734c-p138">A maggio si installa il client Azure Information Protection e si impara ad applicare etichette ai documenti. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="9734c-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="9734c-230">Ne risulta una cadenza di 30 giorni tra due implementazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9734c-230">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="9734c-p139">Il vantaggio di questa strategia di distribuzione è che può richiedere ancor meno tempo per la distribuzione completa dell'infrastruttura di base di Microsoft 365 Enterprise, e anche in questo caso senza che gli utenti debbano gestire più implementazioni contemporaneamente. Non è però prevista una pausa per gli utenti tra una fase e l'altra.</span><span class="sxs-lookup"><span data-stu-id="9734c-p139">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having individual users deal with multiple rollouts the same time. However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-end-to-end-configuration"></a><span data-ttu-id="9734c-233">Infrastruttura predisposta in precedenza e implementazione della configurazione end-to-end</span><span class="sxs-lookup"><span data-stu-id="9734c-233">Up-front infrastructure and rollout of end-to-end configuration</span></span>

<span data-ttu-id="9734c-234">Per le organizzazioni di dimensioni inferiori che possono comprimere le fasi 2-6 in un unico segmento di distribuzione, la distribuzione risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="9734c-234">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="9734c-p140">Il reparto IT configura l'infrastruttura per le fasi 2-6, quindi esegue l'implementazione per gli utenti pilota per verificare la funzionalità end-to-end. Ad esempio, gli utenti pilota ottengono contemporaneamente tutte le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="9734c-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="9734c-237">MFA e altre funzionalità per la gestione delle identità (Identity)</span><span class="sxs-lookup"><span data-stu-id="9734c-237">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="9734c-238">Windows 10 Enterprise in dispositivi Windows (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="9734c-238">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="9734c-239">Office 365 ProPlus per la famiglia di prodotti Office (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="9734c-239">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="9734c-240">Criteri di accesso condizionale e alle app (Gestione dispositivi mobili)</span><span class="sxs-lookup"><span data-stu-id="9734c-240">App and conditional access policies (Mobile device management)</span></span>
- <span data-ttu-id="9734c-241">Installazione del client Azure Information Protection e training su come applicare etichette ai documenti (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="9734c-241">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="9734c-242">Al termine dell'implementazione pilota, viene avviata l'implementazione utente in cui ogni utente ottiene contemporaneamente tutte le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9734c-242">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="9734c-243">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9734c-243">Next step</span></span>

<span data-ttu-id="9734c-244">Avviare la distribuzione di Microsoft 365 Enterprise con l'[infrastruttura di base](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="9734c-244">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
