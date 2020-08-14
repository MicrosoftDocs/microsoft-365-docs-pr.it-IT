---
title: Interazioni dei servizi di gruppo
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Interazioni dei servizi di gruppo
ms.openlocfilehash: 9632debf1bc6fdd2fce061a4c535906410700175
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662695"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="815ce-103">Interazioni dei servizi di gruppo</span><span class="sxs-lookup"><span data-stu-id="815ce-103">Groups services interactions</span></span>

<span data-ttu-id="815ce-104">I gruppi Microsoft 365 forniscono un tessuto comune per una serie di servizi e carichi di lavoro all'interno della piattaforma Microsoft 365 per fornire un'esperienza connessa per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="815ce-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="815ce-105">Al suo interno, esiste un gruppo di Microsoft 365 per fornire:</span><span class="sxs-lookup"><span data-stu-id="815ce-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="815ce-106">Modalità di gestione dell'appartenenza (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="815ce-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="815ce-107">Una posizione per i messaggi e le conversazioni che devono essere effettuate (cassette postali di Exchange, Microsoft teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="815ce-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="815ce-108">Un luogo in cui archiviare i file (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="815ce-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="815ce-109">Calendario per la pianificazione (Exchange)</span><span class="sxs-lookup"><span data-stu-id="815ce-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="815ce-110">Un blocco appunti per le note di acquisizione (OneNote)</span><span class="sxs-lookup"><span data-stu-id="815ce-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="815ce-111">Al momento della creazione di un gruppo, vengono provisioning anche diverse altre risorse, tuttavia non sono visibili fino a quando non si accede per la prima volta dal servizio:</span><span class="sxs-lookup"><span data-stu-id="815ce-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="815ce-112">Una scheda per la gestione delle attività dei gruppi (Planner)</span><span class="sxs-lookup"><span data-stu-id="815ce-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="815ce-113">Un'area di lavoro per la creazione di report (Power BI)</span><span class="sxs-lookup"><span data-stu-id="815ce-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="815ce-114">Un'area per i video condivisi (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="815ce-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="815ce-115">Un'area per i moduli condivisi (maschere)</span><span class="sxs-lookup"><span data-stu-id="815ce-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="815ce-116">In Microsoft 365, gli altri servizi sono in grado di interagire con i gruppi di Microsoft 365 per fornire funzionalità aggiuntive e funzionalità ai membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="815ce-117">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="815ce-117">Examples of this include:</span></span>

- <span data-ttu-id="815ce-118">Applicazioni di alimentazione per le app</span><span class="sxs-lookup"><span data-stu-id="815ce-118">Power Apps for apps</span></span>
- <span data-ttu-id="815ce-119">Automatizzare l'alimentazione per i flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="815ce-119">Power Automate for workflows</span></span>
- <span data-ttu-id="815ce-120">Project sul Web e guida di orientamento per la gestione di progetti basati su cascata</span><span class="sxs-lookup"><span data-stu-id="815ce-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="815ce-121">Teams per le conversazioni basate su canale</span><span class="sxs-lookup"><span data-stu-id="815ce-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="815ce-122">Yammer per le community di interesse</span><span class="sxs-lookup"><span data-stu-id="815ce-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="815ce-123">Interazioni degli utenti con i gruppi</span><span class="sxs-lookup"><span data-stu-id="815ce-123">User interactions with groups</span></span>

<span data-ttu-id="815ce-124">È possibile creare e gestire i gruppi di Microsoft 365 da diverse interfacce, sia dagli amministratori che dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="815ce-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="815ce-125">Esperienze amministrative</span><span class="sxs-lookup"><span data-stu-id="815ce-125">Administrative experiences</span></span>

<span data-ttu-id="815ce-126">Gli amministratori possono creare e gestire i gruppi di Microsoft 365 da diversi centri di amministrazione del carico di lavoro, interfacce della riga di comando che supportano lo scripting, nonché app personalizzate che interagiscono con l'API del grafico.</span><span class="sxs-lookup"><span data-stu-id="815ce-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="815ce-127">L'unica eccezione è rappresentata dai gruppi di Yammer, che devono essere creati dall'interno dell'interfaccia Web di Yammer.</span><span class="sxs-lookup"><span data-stu-id="815ce-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="815ce-128">**Impostazioni correlate**</span><span class="sxs-lookup"><span data-stu-id="815ce-128">**Related settings**</span></span>

<span data-ttu-id="815ce-129">Tra le diverse interfacce amministrative in grado di gestire le impostazioni di gruppo esistono diverse sovrapposizioni di cui è necessario essere a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="815ce-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="815ce-130">**Interfaccia di amministrazione di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="815ce-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="815ce-131">Nell'interfaccia di amministrazione di Microsoft 365, l'accesso Guest ai gruppi è abilitato per impostazione predefinita, così come la possibilità di consentire ai proprietari di aggiungere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="815ce-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="815ce-132">Non sono disponibili ulteriori controlli a livello di organizzazione per i gruppi provenienti da questo interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="815ce-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="815ce-133">**Interfaccia di amministrazione di Azure AD**</span><span class="sxs-lookup"><span data-stu-id="815ce-133">**Azure AD admin center**</span></span>

<span data-ttu-id="815ce-134">L'interfaccia di amministrazione di Azure AD offre controlli che consentono agli utenti di creare gruppi o di assegnare proprietari nei portali di Azure, nonché di definire le impostazioni dei criteri di scadenza e di denominazione.</span><span class="sxs-lookup"><span data-stu-id="815ce-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="815ce-135">L'interfaccia di amministrazione fornisce anche numerose misure di controllo degli inviti che vanno oltre quelle dell'interfaccia di amministrazione di Microsoft 365, ad esempio la possibilità di limitare se gli utenti non proprietari possono invitare anche gli ospiti</span><span class="sxs-lookup"><span data-stu-id="815ce-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="815ce-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="815ce-136">**SharePoint**</span></span>

<span data-ttu-id="815ce-137">I siti di SharePoint vengono creati con i gruppi di sicurezza Owner, Member e Visitor, con i primi due corrispondenti alle controparti del gruppo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="815ce-138">Anche se l'appartenenza ai siti di SharePoint Online è generalmente gestita dal gruppo Microsoft 365 associato, non è una relazione bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="815ce-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="815ce-139">Tutte le modifiche apportate all'appartenenza a livello di gruppo di Microsoft 365 si riflettono in SharePoint, tuttavia se l'appartenenza viene modificata nel gruppo di SharePoint, questo non viene riflesso nel gruppo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="815ce-140">Esperienze degli utenti</span><span class="sxs-lookup"><span data-stu-id="815ce-140">User experiences</span></span>

<span data-ttu-id="815ce-141">Gli utenti finali possono creare gruppi da diversi servizi all'interno di Microsoft 365 e in altri possono condividerli solo con un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="815ce-142">I servizi seguenti consentono la creazione di gruppi per gli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="815ce-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="815ce-143">Progetto di pianificazione di Outlook per il flusso di lavoro Microsoft teams di SharePoint Yammer</span><span class="sxs-lookup"><span data-stu-id="815ce-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="815ce-144">**Limitazione della creazione di gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-144">**Restriction of group creation**</span></span>

<span data-ttu-id="815ce-145">Un approccio comune per controllare la proliferazione dei team consiste nel limitare gli utenti che possono crearli.</span><span class="sxs-lookup"><span data-stu-id="815ce-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="815ce-146">Questa operazione può essere svolta solo limitando la creazione di gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="815ce-147">In questo modo si può influire sulla possibilità di creare gruppi da altri servizi che potrebbero essere necessari per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="815ce-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="815ce-148">I gruppi di Microsoft 365 non supportano la possibilità di limitare la creazione di gruppi da alcune app o servizi mentre lo consentono ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="815ce-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="815ce-149">L'esperienza della limitazione della creazione del gruppo varia tra le applicazioni e i servizi:</span><span class="sxs-lookup"><span data-stu-id="815ce-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="815ce-150">App o servizio</span><span class="sxs-lookup"><span data-stu-id="815ce-150">App or service</span></span>|<span data-ttu-id="815ce-151">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="815ce-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="815ce-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="815ce-152">Outlook</span></span>|<span data-ttu-id="815ce-153">L'opzione **nuovo gruppo** è stata rimossa dal menu nuovo nella pagina utenti</span><span class="sxs-lookup"><span data-stu-id="815ce-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="815ce-154">Planner</span><span class="sxs-lookup"><span data-stu-id="815ce-154">Planner</span></span>|<span data-ttu-id="815ce-155">**Nuovo piano** spiega che la creazione del gruppo è stata disattivata e che offre di aggiungere il piano a un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="815ce-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="815ce-156">Progetto per il Web e la Guida di orientamento</span><span class="sxs-lookup"><span data-stu-id="815ce-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="815ce-157">**Crea menu gruppo** spiega che la creazione del gruppo è limitata e suggerisce l'utilizzo di un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="815ce-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="815ce-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="815ce-158">SharePoint</span></span>|<span data-ttu-id="815ce-159">È ancora in grado di creare un sito del team che non sia connesso a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="815ce-160">Stream</span><span class="sxs-lookup"><span data-stu-id="815ce-160">Stream</span></span>|<span data-ttu-id="815ce-161">L'opzione **gruppo** non viene visualizzata nel **menu Crea**.</span><span class="sxs-lookup"><span data-stu-id="815ce-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="815ce-162">Teams</span><span class="sxs-lookup"><span data-stu-id="815ce-162">Teams</span></span>|<span data-ttu-id="815ce-163">L'utente non è in grado di creare un team con un nuovo gruppo, ma può comunque creare un team che utilizza un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="815ce-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="815ce-164">**La creazione di un** pulsante del team viene sostituita con **create team da un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="815ce-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="815ce-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="815ce-165">Yammer</span></span>|<span data-ttu-id="815ce-166">**Creare un'** opzione di gruppo viene rimossa dall'esplorazione gruppi principali/comunità.</span><span class="sxs-lookup"><span data-stu-id="815ce-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="815ce-167">Interazioni dei servizi con i gruppi</span><span class="sxs-lookup"><span data-stu-id="815ce-167">Services interactions with groups</span></span>

<span data-ttu-id="815ce-168">Vedere i gruppi nel poster di Microsoft 365 per informazioni sui diversi tipi di gruppi, sul modo in cui vengono creati e gestiti e su alcuni consigli di governance.</span><span class="sxs-lookup"><span data-stu-id="815ce-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="815ce-169">[![Immagine di scorrimento per infografica dei gruppi](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="815ce-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="815ce-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="815ce-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="815ce-171">Nella tabella seguente viene fornita una panoramica delle interazioni tra i gruppi di Microsoft 365 e diversi servizi:</span><span class="sxs-lookup"><span data-stu-id="815ce-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="815ce-172">Prodotto</span><span class="sxs-lookup"><span data-stu-id="815ce-172">Product</span></span>|<span data-ttu-id="815ce-173">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="815ce-173">Features</span></span>|<span data-ttu-id="815ce-174">Il servizio</span><span class="sxs-lookup"><span data-stu-id="815ce-174">Does the service</span></span><br><span data-ttu-id="815ce-175">esistere senza un gruppo?</span><span class="sxs-lookup"><span data-stu-id="815ce-175">exist without a group?</span></span>|<span data-ttu-id="815ce-176">Il servizio può essere</span><span class="sxs-lookup"><span data-stu-id="815ce-176">Can the service</span></span><br><span data-ttu-id="815ce-177">creare un gruppo?</span><span class="sxs-lookup"><span data-stu-id="815ce-177">create a group?</span></span>|<span data-ttu-id="815ce-178">Elimina l'</span><span class="sxs-lookup"><span data-stu-id="815ce-178">Does deleting the</span></span><br><span data-ttu-id="815ce-179">istanza eliminare il gruppo?</span><span class="sxs-lookup"><span data-stu-id="815ce-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="815ce-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="815ce-180">Azure AD</span></span>|<span data-ttu-id="815ce-181">Appartenenza, controlli di gruppo, ospiti</span><span class="sxs-lookup"><span data-stu-id="815ce-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="815ce-182">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-182">Yes</span></span>|<span data-ttu-id="815ce-183">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-183">Yes</span></span>|<span data-ttu-id="815ce-184">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-184">Yes</span></span>|
|<span data-ttu-id="815ce-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="815ce-185">Exchange</span></span>|<span data-ttu-id="815ce-186">Calendario, cassetta postale</span><span class="sxs-lookup"><span data-stu-id="815ce-186">Calendar, mailbox</span></span>|<span data-ttu-id="815ce-187">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-187">Yes</span></span>|<span data-ttu-id="815ce-188">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-188">Yes</span></span>|<span data-ttu-id="815ce-189">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-189">Yes</span></span>|
|<span data-ttu-id="815ce-190">Forms</span><span class="sxs-lookup"><span data-stu-id="815ce-190">Forms</span></span>|<span data-ttu-id="815ce-191">Forma</span><span class="sxs-lookup"><span data-stu-id="815ce-191">Form</span></span>|<span data-ttu-id="815ce-192">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-192">Yes</span></span>|<span data-ttu-id="815ce-193">No</span><span class="sxs-lookup"><span data-stu-id="815ce-193">No</span></span>|<span data-ttu-id="815ce-194">No</span><span class="sxs-lookup"><span data-stu-id="815ce-194">No</span></span>|
|<span data-ttu-id="815ce-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="815ce-195">OneNote</span></span>|<span data-ttu-id="815ce-196">Blocco appunti</span><span class="sxs-lookup"><span data-stu-id="815ce-196">Notebook</span></span>|<span data-ttu-id="815ce-197">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-197">Yes</span></span>|<span data-ttu-id="815ce-198">No</span><span class="sxs-lookup"><span data-stu-id="815ce-198">No</span></span>|<span data-ttu-id="815ce-199">No</span><span class="sxs-lookup"><span data-stu-id="815ce-199">No</span></span>|
|<span data-ttu-id="815ce-200">Planner</span><span class="sxs-lookup"><span data-stu-id="815ce-200">Planner</span></span>|<span data-ttu-id="815ce-201">Scheda attività</span><span class="sxs-lookup"><span data-stu-id="815ce-201">Task board</span></span>|<span data-ttu-id="815ce-202">No</span><span class="sxs-lookup"><span data-stu-id="815ce-202">No</span></span>|<span data-ttu-id="815ce-203">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-203">Yes</span></span>|<span data-ttu-id="815ce-204">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-204">Yes</span></span>|
|<span data-ttu-id="815ce-205">App Power Apps</span><span class="sxs-lookup"><span data-stu-id="815ce-205">Power Apps app</span></span>|<span data-ttu-id="815ce-206">App</span><span class="sxs-lookup"><span data-stu-id="815ce-206">App</span></span>|<span data-ttu-id="815ce-207">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-207">Yes</span></span>|<span data-ttu-id="815ce-208">No</span><span class="sxs-lookup"><span data-stu-id="815ce-208">No</span></span>|<span data-ttu-id="815ce-209">No</span><span class="sxs-lookup"><span data-stu-id="815ce-209">No</span></span>|
|<span data-ttu-id="815ce-210">Automatizzare la potenza</span><span class="sxs-lookup"><span data-stu-id="815ce-210">Power Automate</span></span>|<span data-ttu-id="815ce-211">Flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="815ce-211">Workflow</span></span>|<span data-ttu-id="815ce-212">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-212">Yes</span></span>|<span data-ttu-id="815ce-213">No</span><span class="sxs-lookup"><span data-stu-id="815ce-213">No</span></span>|<span data-ttu-id="815ce-214">No</span><span class="sxs-lookup"><span data-stu-id="815ce-214">No</span></span>|
|<span data-ttu-id="815ce-215">Power BI (classica)</span><span class="sxs-lookup"><span data-stu-id="815ce-215">Power BI (classic)</span></span>|<span data-ttu-id="815ce-216">Area di lavoro</span><span class="sxs-lookup"><span data-stu-id="815ce-216">Workspace</span></span>|<span data-ttu-id="815ce-217">No</span><span class="sxs-lookup"><span data-stu-id="815ce-217">No</span></span>|<span data-ttu-id="815ce-218">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-218">Yes</span></span>|<span data-ttu-id="815ce-219">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-219">Yes</span></span>|
|<span data-ttu-id="815ce-220">Power BI (nuovo)</span><span class="sxs-lookup"><span data-stu-id="815ce-220">Power BI (new)</span></span>|<span data-ttu-id="815ce-221">Area di lavoro</span><span class="sxs-lookup"><span data-stu-id="815ce-221">Workspace</span></span>|<span data-ttu-id="815ce-222">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-222">Yes</span></span>|<span data-ttu-id="815ce-223">No</span><span class="sxs-lookup"><span data-stu-id="815ce-223">No</span></span>|<span data-ttu-id="815ce-224">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-224">Yes</span></span>|
|<span data-ttu-id="815ce-225">Project per il Web</span><span class="sxs-lookup"><span data-stu-id="815ce-225">Project for the web</span></span>|<span data-ttu-id="815ce-226">Piano di progetto</span><span class="sxs-lookup"><span data-stu-id="815ce-226">Project plan</span></span>|<span data-ttu-id="815ce-227">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-227">Yes</span></span>|<span data-ttu-id="815ce-228">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-228">Yes</span></span>|<span data-ttu-id="815ce-229">No</span><span class="sxs-lookup"><span data-stu-id="815ce-229">No</span></span>|
|<span data-ttu-id="815ce-230">Roadmap</span><span class="sxs-lookup"><span data-stu-id="815ce-230">Roadmap</span></span>|<span data-ttu-id="815ce-231">Roadmap</span><span class="sxs-lookup"><span data-stu-id="815ce-231">Roadmap</span></span>|<span data-ttu-id="815ce-232">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-232">Yes</span></span>|<span data-ttu-id="815ce-233">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-233">Yes</span></span>|<span data-ttu-id="815ce-234">No</span><span class="sxs-lookup"><span data-stu-id="815ce-234">No</span></span>|
|<span data-ttu-id="815ce-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="815ce-235">SharePoint</span></span>|<span data-ttu-id="815ce-236">Sito</span><span class="sxs-lookup"><span data-stu-id="815ce-236">Site</span></span>|<span data-ttu-id="815ce-237">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-237">Yes</span></span>|<span data-ttu-id="815ce-238">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-238">Yes</span></span>|<span data-ttu-id="815ce-239">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-239">Yes</span></span>|
|<span data-ttu-id="815ce-240">Stream</span><span class="sxs-lookup"><span data-stu-id="815ce-240">Stream</span></span>|<span data-ttu-id="815ce-241">Canale, video</span><span class="sxs-lookup"><span data-stu-id="815ce-241">Channel, video</span></span>|<span data-ttu-id="815ce-242">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-242">Yes</span></span>|<span data-ttu-id="815ce-243">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-243">Yes</span></span>|<span data-ttu-id="815ce-244">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-244">Yes</span></span>|
|<span data-ttu-id="815ce-245">Teams</span><span class="sxs-lookup"><span data-stu-id="815ce-245">Teams</span></span>|<span data-ttu-id="815ce-246">Del team</span><span class="sxs-lookup"><span data-stu-id="815ce-246">Team</span></span>|<span data-ttu-id="815ce-247">No</span><span class="sxs-lookup"><span data-stu-id="815ce-247">No</span></span>|<span data-ttu-id="815ce-248">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-248">Yes</span></span>|<span data-ttu-id="815ce-249">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-249">Yes</span></span>|
|<span data-ttu-id="815ce-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="815ce-250">Yammer</span></span>|<span data-ttu-id="815ce-251">Group</span><span class="sxs-lookup"><span data-stu-id="815ce-251">Group</span></span>|<span data-ttu-id="815ce-252">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-252">Yes</span></span>|<span data-ttu-id="815ce-253">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-253">Yes</span></span>|<span data-ttu-id="815ce-254">Sì</span><span class="sxs-lookup"><span data-stu-id="815ce-254">Yes</span></span>|

<span data-ttu-id="815ce-255">Anche se nella tabella precedente viene fornita una panoramica generale delle interazioni di gruppo con i servizi Microsoft 365, esistono numerose sfumature e complessità che è necessario comprendere.</span><span class="sxs-lookup"><span data-stu-id="815ce-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="815ce-256">Nelle sezioni seguenti vengono esaminati in modo più approfondito i carichi di lavoro specifici e le interazioni con i gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="815ce-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="815ce-257">Azure AD</span></span>

<span data-ttu-id="815ce-258">Azure AD fornisce le funzionalità di gestione delle identità sottostanti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="815ce-259">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="815ce-260">Appartenenza al gruppo</span><span class="sxs-lookup"><span data-stu-id="815ce-260">Group membership</span></span>
- <span data-ttu-id="815ce-261">Criteri di denominazione</span><span class="sxs-lookup"><span data-stu-id="815ce-261">Naming policy</span></span>
- <span data-ttu-id="815ce-262">Criteri di scadenza</span><span class="sxs-lookup"><span data-stu-id="815ce-262">Expiration policy</span></span>
- <span data-ttu-id="815ce-263">Ospiti</span><span class="sxs-lookup"><span data-stu-id="815ce-263">Guests</span></span>
- <span data-ttu-id="815ce-264">Limitazione della creazione di gruppi</span><span class="sxs-lookup"><span data-stu-id="815ce-264">Restriction of Group creation</span></span>

<span data-ttu-id="815ce-265">**È possibile creare un gruppo in Azure AD?**</span><span class="sxs-lookup"><span data-stu-id="815ce-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="815ce-266">Sì, i gruppi di Microsoft 365 possono essere creati da Azure AD tramite il portale Web di amministrazione, tramite PowerShell o l'API del grafico.</span><span class="sxs-lookup"><span data-stu-id="815ce-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="815ce-267">**Azure AD esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="815ce-268">Sì, Azure AD esegue un gran numero di servizi che non hanno alcuna relazione con i gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="815ce-269">Ogni gruppo di Microsoft 365 è rappresentato come un oggetto in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="815ce-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="815ce-270">**È possibile che vi siano più istanze di Azure AD per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="815ce-271">No, è presente una sola istanza di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="815ce-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="815ce-272">**È possibile associare Azure AD a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="815ce-273">Sì, perché Azure AD è la piattaforma sottostante che fornisce il servizio di appartenenza a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="815ce-274">**È possibile che l'associazione di Azure AD sia associata a un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="815ce-275">No, Azure AD è la piattaforma sottostante in cui sono presenti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="815ce-276">**L'eliminazione dell'istanza elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="815ce-277">L'eliminazione del gruppo in Azure AD eliminerà i servizi e i contenuti associati a un gruppo rilevanti.</span><span class="sxs-lookup"><span data-stu-id="815ce-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="815ce-278">Teams</span><span class="sxs-lookup"><span data-stu-id="815ce-278">Teams</span></span>

<span data-ttu-id="815ce-279">Teams è un'area di lavoro basata su chat che mira a migliorare la collaborazione fornendo un'interfaccia singolare per interagire con una vasta gamma di servizi Microsoft e di terze parti.</span><span class="sxs-lookup"><span data-stu-id="815ce-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="815ce-280">Per impostazione predefinita, quando viene creato un team, la cassetta postale e il calendario associati al gruppo Microsoft 365 sono nascosti sia dall'elenco indirizzi globale in Exchange sia da Outlook.</span><span class="sxs-lookup"><span data-stu-id="815ce-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="815ce-281">Questo può essere sottoposto a override manualmente da un amministratore se l'utente desidera utilizzare sia Outlook che i team nello stesso gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="815ce-282">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="815ce-283">Conversazioni</span><span class="sxs-lookup"><span data-stu-id="815ce-283">Conversations</span></span>
- <span data-ttu-id="815ce-284">Schede & canali</span><span class="sxs-lookup"><span data-stu-id="815ce-284">Channels & tabs</span></span>
- <span data-ttu-id="815ce-285">Riunioni</span><span class="sxs-lookup"><span data-stu-id="815ce-285">Meetings</span></span>

<span data-ttu-id="815ce-286">**I team possono creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="815ce-287">Sì, la creazione di un nuovo team creerà un nuovo gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="815ce-288">È anche possibile creare un team per un gruppo esistente che attualmente non ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="815ce-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="815ce-289">**I team esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="815ce-290">No, non è possibile che un team esista senza un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="815ce-291">**Possono essere presenti più team per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="815ce-292">No, la relazione tra un team e un gruppo è 1:1.</span><span class="sxs-lookup"><span data-stu-id="815ce-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="815ce-293">**Un team può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-294">No, il team può essere associato solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="815ce-295">**È possibile che l'associazione di un team con un gruppo venga modificata?**</span><span class="sxs-lookup"><span data-stu-id="815ce-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="815ce-296">No, il team può sempre essere associato al gruppo a cui era originariamente associato.</span><span class="sxs-lookup"><span data-stu-id="815ce-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="815ce-297">**L'eliminazione del team deve essere eliminata dal gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="815ce-298">Sì, l'eliminazione del team in Microsoft teams eliminerà il gruppo, i servizi associati al gruppo e il contenuto.</span><span class="sxs-lookup"><span data-stu-id="815ce-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="815ce-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="815ce-299">Exchange</span></span>

<span data-ttu-id="815ce-300">Exchange Online fornisce messaggistica, calendario, contatti e funzionalità associate.</span><span class="sxs-lookup"><span data-stu-id="815ce-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="815ce-301">Nel contesto di un gruppo, è associata una sola risorsa, invece di un'intera istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="815ce-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="815ce-302">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="815ce-303">Cassetta postale e calendario</span><span class="sxs-lookup"><span data-stu-id="815ce-303">Mailbox and calendar</span></span>
- <span data-ttu-id="815ce-304">Possibilità di inviare tramite posta elettronica tutti i membri del gruppo</span><span class="sxs-lookup"><span data-stu-id="815ce-304">Ability to email all Group members</span></span>
- <span data-ttu-id="815ce-305">Archiviazione delle conversazioni dei canali di teams per scopi eDiscovery, commenti Planner</span><span class="sxs-lookup"><span data-stu-id="815ce-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="815ce-306">**Exchange può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="815ce-307">Sì, è possibile creare un gruppo dall'interfaccia di amministrazione di Exchange Online, così come da Outlook.</span><span class="sxs-lookup"><span data-stu-id="815ce-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="815ce-308">È inoltre possibile convertire le liste di distribuzione di Exchange in gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="815ce-309">**Exchange esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="815ce-310">Sì, Exchange Online offre una serie di servizi, tra cui le cassette postali condivise e i calendari, senza alcuna associazione di gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="815ce-311">**Possono essere presenti più istanze di cassette postali di Exchange o calendari per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="815ce-312">No, può trattarsi solo di una singola cassetta postale di Exchange Online e di un calendario per un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="815ce-313">**Le cassette postali e i calendari di Exchange possono essere associati a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-314">No, la cassetta postale e il calendario hanno una relazione di 1:1 con il gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="815ce-315">È possibile condividere la cassetta postale con altri utenti o gruppi, ma questo non stabilisce alcuna forma di associazione di servizi.</span><span class="sxs-lookup"><span data-stu-id="815ce-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="815ce-316">**È possibile che la cassetta postale di Exchange o l'associazione del calendario con un gruppo siano cambiate?**</span><span class="sxs-lookup"><span data-stu-id="815ce-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="815ce-317">No, la cassetta postale e il calendario non possono essere cambiati in un gruppo diverso.</span><span class="sxs-lookup"><span data-stu-id="815ce-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="815ce-318">Tuttavia, il contenuto può essere spostato da una cassetta postale all'altra all'interno di Outlook o tramite uno strumento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="815ce-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="815ce-319">**L'eliminazione della cassetta postale Elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="815ce-320">Sì, l'eliminazione della cassetta postale in Exchange eliminerà il gruppo, nonché i servizi e i contenuti associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="815ce-321">Forms</span><span class="sxs-lookup"><span data-stu-id="815ce-321">Forms</span></span>

<span data-ttu-id="815ce-322">Moduli fornisce sondaggi e quiz basati sul Web.</span><span class="sxs-lookup"><span data-stu-id="815ce-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="815ce-323">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="815ce-324">Proprietà dei moduli</span><span class="sxs-lookup"><span data-stu-id="815ce-324">Ownership of forms</span></span>

<span data-ttu-id="815ce-325">**I moduli possono creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="815ce-326">No, i moduli non possono creare un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="815ce-327">**I moduli sono presenti senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="815ce-328">Sì, è possibile creare sondaggi e quiz direttamente nell'account di un utente finale.</span><span class="sxs-lookup"><span data-stu-id="815ce-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="815ce-329">**Possono essere presenti più moduli per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="815ce-330">Sì, possono essere presenti più moduli associati a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="815ce-331">**I moduli possono essere associati a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-332">No, un modulo può essere associato solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="815ce-333">**È possibile modificare l'associazione di un modulo con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="815ce-334">No, una volta che un modulo è associato a un gruppo (creato direttamente all'interno o a una proprietà trasferita da un singolo), non può essere spostato in un altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="815ce-335">**L'eliminazione del modulo può essere eliminata dal gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="815ce-336">No, non è possibile eliminare un gruppo dall'interfaccia moduli, solo singoli moduli.</span><span class="sxs-lookup"><span data-stu-id="815ce-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="815ce-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="815ce-337">OneNote</span></span>

<span data-ttu-id="815ce-338">OneNote è un'applicazione per notebook digitale.</span><span class="sxs-lookup"><span data-stu-id="815ce-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="815ce-339">Il blocco appunti di OneNote creato con un gruppo è un file nel sito di SharePoint associato anziché in un servizio connesso a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="815ce-340">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="815ce-341">Blocco appunti condiviso (archiviato nella raccolta di SharePoint associata a un gruppo)</span><span class="sxs-lookup"><span data-stu-id="815ce-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="815ce-342">**OneNote è in grado di creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="815ce-343">No, l'applicazione OneNote non è in grado di creare un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="815ce-344">**I blocchi appunti di OneNote esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="815ce-345">Sì, è possibile creare taccuini direttamente in OneDrive o in altre posizioni condivise.</span><span class="sxs-lookup"><span data-stu-id="815ce-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="815ce-346">**Possono essere presenti più blocchi appunti di OneNote per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="815ce-347">Sì, un blocco appunti viene creato per impostazione predefinita e altri possono essere aggiunti, tuttavia qualsiasi collegamento a OneNote dai servizi associati al gruppo passerà sempre al blocco appunti predefinito.</span><span class="sxs-lookup"><span data-stu-id="815ce-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="815ce-348">**Un blocco appunti di OneNote può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-349">No, il blocco appunti è archiviato nella raccolta siti di SharePoint associata a un gruppo e collegato da diverse interfacce.</span><span class="sxs-lookup"><span data-stu-id="815ce-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="815ce-350">Tuttavia, può essere condiviso con altri gruppi nello stesso modo in cui può essere condiviso con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="815ce-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="815ce-351">**L'associazione del blocco appunti può essere modificata da un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="815ce-352">No, il blocco appunti stesso è associato al gruppo e può accedervi direttamente da altri servizi connessi al gruppo, tuttavia il contenuto può essere spostato da un blocco appunti all'altro all'interno dell'applicazione OneNote.</span><span class="sxs-lookup"><span data-stu-id="815ce-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="815ce-353">**L'eliminazione del blocco appunti viene eliminata dal gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="815ce-354">No, tuttavia, se il blocco appunti di OneNote è stato eliminato, potrebbero essere presenti collegamenti interrotti in alcuni dei servizi associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="815ce-355">Planner</span><span class="sxs-lookup"><span data-stu-id="815ce-355">Planner</span></span>

<span data-ttu-id="815ce-356">Planner è un servizio di gestione delle attività di gruppo Lightweight.</span><span class="sxs-lookup"><span data-stu-id="815ce-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="815ce-357">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="815ce-358">Scheda per la gestione delle attività del gruppo</span><span class="sxs-lookup"><span data-stu-id="815ce-358">Board for managing group tasks</span></span>

<span data-ttu-id="815ce-359">**Planner è in grado di creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="815ce-360">Sì, la creazione di un piano creerà un nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="815ce-361">**Esiste una scheda pianificazione senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="815ce-362">No, è necessario che un piano sia associato a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="815ce-363">**Possono essere presenti più piani per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="815ce-364">Sì, possono essere presenti più piani per gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="815ce-365">**Un piano può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-366">No, un piano si basa esclusivamente sull'appartenenza ai gruppi per determinare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="815ce-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="815ce-367">**L'associazione di un piano può essere modificata con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="815ce-368">No, tuttavia, la copia di un piano crea un nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="815ce-369">Un gruppo creato da qualsiasi altra applicazione non verrà visualizzato automaticamente in Planner per un utente.</span><span class="sxs-lookup"><span data-stu-id="815ce-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="815ce-370">Per accedere alla scheda iniziale, sarà necessario aprirla da un'altra interfaccia basata su gruppo, ad esempio Outlook.</span><span class="sxs-lookup"><span data-stu-id="815ce-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="815ce-371">**L'eliminazione del piano può essere eliminata dal gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="815ce-372">Sì, eliminando il piano verrà eliminato il gruppo e i servizi associati a un gruppo e il relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="815ce-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="815ce-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="815ce-373">Power Apps</span></span>

<span data-ttu-id="815ce-374">Power Apps fornisce un'area di disegno per lo sviluppo di app senza codice.</span><span class="sxs-lookup"><span data-stu-id="815ce-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="815ce-375">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="815ce-376">Le app possono essere condivise con un gruppo per l'esecuzione e la modifica</span><span class="sxs-lookup"><span data-stu-id="815ce-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="815ce-377">**Le app di potenza possono creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="815ce-378">No, Power Apps non è in grado di creare un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="815ce-379">**Le app di alimentazione esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="815ce-380">Sì, le app possono essere create all'interno di Power Apps e risiedono all'interno dell'account Creators fino alla condivisione o alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="815ce-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="815ce-381">**Possono essere presenti più app per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="815ce-382">Sì, possono essere presenti più app condivise con un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="815ce-383">**Le app possono essere associate a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-384">Sì, un'app può essere condivisa con più gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="815ce-385">**È possibile modificare l'associazione di un'app con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="815ce-386">Sì, poiché l'associazione tra le app di alimentazione e un gruppo di Microsoft 365 è solo la condivisione, l'app risiede ancora con il creatore.</span><span class="sxs-lookup"><span data-stu-id="815ce-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="815ce-387">I [gruppi devono essere abilitati alla sicurezza prima che le app possano essere condivise con esse](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="815ce-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="815ce-388">**L'eliminazione dell'app elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="815ce-389">No, le app non sono connesse a un gruppo diverso da quello condiviso con esse.</span><span class="sxs-lookup"><span data-stu-id="815ce-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="815ce-390">Automatizzare la potenza</span><span class="sxs-lookup"><span data-stu-id="815ce-390">Power Automate</span></span>

<span data-ttu-id="815ce-391">Power automatizzate (in precedenza noto come Microsoft Flow) fornisce flussi di lavoro e servizi di automazione.</span><span class="sxs-lookup"><span data-stu-id="815ce-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="815ce-392">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="815ce-393">I flussi di lavoro possono essere condivisi con un gruppo da eseguire e modificare.</span><span class="sxs-lookup"><span data-stu-id="815ce-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="815ce-394">**È possibile automatizzare l'alimentazione per creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="815ce-395">No, Power automatizzate non è in grado di creare un gruppo di Microsoft 365 nel contesto di essere associato a uno.</span><span class="sxs-lookup"><span data-stu-id="815ce-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="815ce-396">È tuttavia possibile creare un flusso che esegua diverse operazioni, ad esempio la creazione di un gruppo di sicurezza di Azure AD o l'aggiornamento dell'appartenenza a un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="815ce-397">**I flussi esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="815ce-398">Sì, i flussi possono essere creati all'interno del Power automatizzate e risiedono all'interno dell'account Creators fino alla condivisione o alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="815ce-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="815ce-399">**Possono essere presenti più flussi per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="815ce-400">Sì, possono essere presenti più flussi condivisi con un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="815ce-401">**È possibile associare un flusso a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-402">Sì, un flusso può essere condiviso con più gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="815ce-403">**È possibile modificare l'associazione di un flusso con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="815ce-404">Sì, poiché l'associazione tra Power automatizzate e un gruppo di Microsoft 365 è solo la condivisione, il flusso risiede ancora con il creatore.</span><span class="sxs-lookup"><span data-stu-id="815ce-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="815ce-405">**L'eliminazione di un flusso Elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="815ce-406">No, come le app di alimentazione, i flussi non sono connessi al gruppo diverso da quello condiviso con essi.</span><span class="sxs-lookup"><span data-stu-id="815ce-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="815ce-407">Power BI (classica)</span><span class="sxs-lookup"><span data-stu-id="815ce-407">Power BI (classic)</span></span>

<span data-ttu-id="815ce-408">Power BI fornisce dashboard e report basati su dati interattivi.</span><span class="sxs-lookup"><span data-stu-id="815ce-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="815ce-409">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="815ce-410">Report di dati</span><span class="sxs-lookup"><span data-stu-id="815ce-410">Data reporting</span></span>

<span data-ttu-id="815ce-411">**Power BI può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="815ce-412">Sì, la creazione di un'area di lavoro classica creerà un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="815ce-413">**L'area di lavoro Power BI Classic esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="815ce-414">No, [un'area di lavoro classica in Power BI deve essere associata a un gruppo](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="815ce-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="815ce-415">**Possono essere presenti più aree di lavoro di Power BI per ogni gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="815ce-416">No, la relazione tra un'area di lavoro classica e un gruppo è 1:1.</span><span class="sxs-lookup"><span data-stu-id="815ce-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="815ce-417">**È possibile associare un'area di lavoro a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-418">Tecnicamente no, mentre l'area di lavoro classica viene creata con il gruppo, il contenuto può essere condiviso al di fuori del gruppo con gli utenti e i gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="815ce-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="815ce-419">**L'associazione dell'area di lavoro può essere modificata con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="815ce-420">No, l'area di lavoro classica è associata al gruppo, tuttavia il contenuto può essere spostato da un'area di lavoro all'altra all'interno dell'interfaccia di Power BI o esportando i contenuti localmente.</span><span class="sxs-lookup"><span data-stu-id="815ce-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="815ce-421">**L'eliminazione dell'area di lavoro elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="815ce-422">Sì, eliminando l'area di lavoro in Power BI, verranno eliminati i contenuti e i servizi associati a gruppi e gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="815ce-423">Power BI (nuovo)</span><span class="sxs-lookup"><span data-stu-id="815ce-423">Power BI (new)</span></span>

<span data-ttu-id="815ce-424">Power BI fornisce dashboard e report basati su dati interattivi.</span><span class="sxs-lookup"><span data-stu-id="815ce-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="815ce-425">Durante la creazione di una nuova area di lavoro in Power BI non viene creato un gruppo di Microsoft 365, la creazione di un gruppo con qualsiasi altro mezzo crea un nuovo Workspace (non classico) in Power BI.</span><span class="sxs-lookup"><span data-stu-id="815ce-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="815ce-426">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="815ce-427">Report di dati</span><span class="sxs-lookup"><span data-stu-id="815ce-427">Data reporting</span></span>

<span data-ttu-id="815ce-428">**Power BI può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="815ce-429">No, non è possibile creare un gruppo di Microsoft 365 dalla nuova interfaccia di Power BI.</span><span class="sxs-lookup"><span data-stu-id="815ce-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="815ce-430">**La nuova area di lavoro Power BI esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="815ce-431">Sì, è possibile che i report e le aree di lavoro vengano creati in Power BI non associati ai gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="815ce-432">**Possono essere presenti più aree di lavoro per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="815ce-433">Sì, [più aree di lavoro create da Power bi possono essere condivise con un solo gruppo](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="815ce-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="815ce-434">**È possibile associare un'area di lavoro a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-435">No, un'area di lavoro creata da Power BI può essere associata a un solo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="815ce-436">**È possibile modificare l'associazione di un'area di lavoro con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="815ce-437">Sì e no.</span><span class="sxs-lookup"><span data-stu-id="815ce-437">Yes and no.</span></span> <span data-ttu-id="815ce-438">Un'area di lavoro creata da Power BI può essere associata a un solo gruppo alla volta, ma può cambiare l'associazione in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="815ce-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="815ce-439">Un'area di lavoro creata in Power BI da un gruppo è associata definitivamente a quel gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="815ce-440">**L'eliminazione dell'area di lavoro elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="815ce-441">Sì, eliminare l'area di lavoro in Power BI eliminerà il gruppo e i servizi associati a un gruppo e il contenuto.</span><span class="sxs-lookup"><span data-stu-id="815ce-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="815ce-442">Project per il Web</span><span class="sxs-lookup"><span data-stu-id="815ce-442">Project for the web</span></span>

<span data-ttu-id="815ce-443">Project per il Web offre la possibilità di creare piani di progetto, diagrammi di Gantt e roadmap.</span><span class="sxs-lookup"><span data-stu-id="815ce-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="815ce-444">Caratteristiche principali fornite ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-444">Key features provided to groups.</span></span>

- <span data-ttu-id="815ce-445">Piani di progetto</span><span class="sxs-lookup"><span data-stu-id="815ce-445">Project plans</span></span>

<span data-ttu-id="815ce-446">**È possibile Project per il Web creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="815ce-447">Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente da Project per il Web.</span><span class="sxs-lookup"><span data-stu-id="815ce-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="815ce-448">**I progetti esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="815ce-449">Sì, i progetti possono esistere senza essere associati a un gruppo di Microsoft 365, tuttavia l'assegnazione delle attività richiede l'associazione di gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="815ce-450">**Possono essere presenti più progetti per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="815ce-451">Sì, è possibile connettere più progetti in un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="815ce-452">**Il progetto può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-453">No, un progetto può essere associato solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="815ce-454">**È possibile modificare l'associazione di un progetto con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="815ce-455">No, una volta stabilita l'associazione con un gruppo, non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="815ce-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="815ce-456">**L'eliminazione del progetto viene eliminata dal gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="815ce-457">No, l'eliminazione del progetto in Project per il Web non consente di eliminare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="815ce-458">Roadmap</span><span class="sxs-lookup"><span data-stu-id="815ce-458">Roadmap</span></span>

<span data-ttu-id="815ce-459">Roadmap fornisce la possibilità di creare roadmap di progetti con Project per il Web e Project online.</span><span class="sxs-lookup"><span data-stu-id="815ce-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="815ce-460">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="815ce-461">Roadmap del progetto</span><span class="sxs-lookup"><span data-stu-id="815ce-461">Project roadmaps</span></span>

<span data-ttu-id="815ce-462">**Roadmap può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="815ce-463">Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente dalla roadmap.</span><span class="sxs-lookup"><span data-stu-id="815ce-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="815ce-464">**La Guida di orientamento esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="815ce-465">Sì, le roadmap possono esistere senza essere associate a un gruppo di Microsoft 365, tuttavia la condivisione della roadmap richiede l'associazione di gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="815ce-466">**Possono esserci più roadmap per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="815ce-467">Sì, è possibile connettere più roadmap a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="815ce-468">**È possibile associare una roadmap a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-469">No, una guida di orientamento può essere associata solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="815ce-470">**L'associazione di una roadmap può essere modificata con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="815ce-471">No, una volta stabilita l'associazione con un gruppo, non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="815ce-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="815ce-472">**L'eliminazione della roadmap Elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="815ce-473">No, eliminando la roadmap non verrà eliminato il gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="815ce-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="815ce-474">SharePoint</span></span>

<span data-ttu-id="815ce-475">SharePoint è una piattaforma di gestione del contenuto basata sul Web che fornisce tra le altre cose servizi di archiviazione per diversi servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="815ce-476">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="815ce-477">Raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="815ce-477">Document library</span></span>
- <span data-ttu-id="815ce-478">Raccolta per l'archiviazione del blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="815ce-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="815ce-479">Archiviazione dei file wiki di Teams</span><span class="sxs-lookup"><span data-stu-id="815ce-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="815ce-480">**SharePoint può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="815ce-481">Sì, la creazione di un sito del team in SharePoint creerà un gruppo di Microsoft 365 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="815ce-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="815ce-482">È anche possibile creare un gruppo e, facoltativamente, un team per un sito esistente.</span><span class="sxs-lookup"><span data-stu-id="815ce-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="815ce-483">**I siti di SharePoint esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="815ce-484">Sì, SharePoint offre numerosi servizi e siti non associati a un gruppo, ad esempio i siti di comunicazione e Hub.</span><span class="sxs-lookup"><span data-stu-id="815ce-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="815ce-485">**Possono essere presenti più siti per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="815ce-486">No, può essere presente solo un singolo sito per gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="815ce-487">I canali privati nei team utilizzano siti aggiuntivi che non sono connessi al gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="815ce-488">**I siti possono essere associati a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-489">Tecnicamente no, ma durante la creazione di un sito con un gruppo, il contenuto può essere condiviso con altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="815ce-490">**È possibile modificare l'associazione di un sito con un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="815ce-491">No, il sito stesso è associato al gruppo, tuttavia il contenuto può essere spostato da un sito a un altro all'interno dell'interfaccia di SharePoint, esportando il contenuto localmente o utilizzando uno strumento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="815ce-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="815ce-492">**L'eliminazione del sito Elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="815ce-493">Sì, l'eliminazione del sito in SharePoint eliminerà i servizi e i contenuti associati a gruppi e gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="815ce-494">Stream</span><span class="sxs-lookup"><span data-stu-id="815ce-494">Stream</span></span>

<span data-ttu-id="815ce-495">Microsoft Stream è una piattaforma di hosting e condivisione di video.</span><span class="sxs-lookup"><span data-stu-id="815ce-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="815ce-496">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="815ce-497">Archiviazione video</span><span class="sxs-lookup"><span data-stu-id="815ce-497">Video storage</span></span>
- <span data-ttu-id="815ce-498">Registrazione riunione di Teams</span><span class="sxs-lookup"><span data-stu-id="815ce-498">Teams meeting recording</span></span>
- <span data-ttu-id="815ce-499">Canali video</span><span class="sxs-lookup"><span data-stu-id="815ce-499">Video channels</span></span>

<span data-ttu-id="815ce-500">**Stream può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="815ce-501">Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente da Stream.</span><span class="sxs-lookup"><span data-stu-id="815ce-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="815ce-502">**Il flusso esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="815ce-503">Sì, i canali video e i video possono esistere in Stream senza essere associati a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="815ce-504">**Possono essere presenti più video e canali per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="815ce-505">Sì, possono essere presenti più video e canali in ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="815ce-506">**Un video o un canale può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="815ce-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="815ce-507">Sì, mentre un video o un canale viene creato con un gruppo, può essere condiviso con altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="815ce-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="815ce-508">**La sua associazione con un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="815ce-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="815ce-509">Sì e no; i video in streaming sono di proprietà dell'Uploader o del registratore di riunioni originale e pertanto possono essere associati a qualsiasi gruppo, ma i canali video possono essere associati solo al gruppo in cui sono stati originariamente creati.</span><span class="sxs-lookup"><span data-stu-id="815ce-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="815ce-510">**L'eliminazione di video o canali Elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="815ce-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="815ce-511">No, l'eliminazione di video o canali non comporta l'eliminazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="815ce-512">Tuttavia, l'eliminazione del gruppo stesso in Stream eliminerà i servizi e i contenuti associati a un gruppo, ad eccezione dei video effettivi.</span><span class="sxs-lookup"><span data-stu-id="815ce-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="815ce-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="815ce-513">Yammer</span></span>

<span data-ttu-id="815ce-514">Yammer è una piattaforma sociale aziendale progettata per favorire l'impegno della community all'interno e tra organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="815ce-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="815ce-515">La creazione di una community (in precedenza nota come "gruppo") in Yammer crea una cassetta postale, ma al momento non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="815ce-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="815ce-516">Un gruppo di Microsoft 365 associato a Yammer non può essere utilizzato con un team di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="815ce-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="815ce-517">**Caratteristiche principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="815ce-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="815ce-518">Area di conversazione</span><span class="sxs-lookup"><span data-stu-id="815ce-518">Conversation area</span></span>

<span data-ttu-id="815ce-519">**È possibile Yammer creare un gruppo di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="815ce-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="815ce-520">Sì, la creazione di un nuovo gruppo in Yammer creerà un nuovo gruppo di Microsoft 365, se le piattaforme sono connesse e l'utente ha la possibilità di creare un gruppo.</span><span class="sxs-lookup"><span data-stu-id="815ce-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="815ce-521">Non è possibile creare un gruppo di Yammer con un gruppo di Microsoft 365 associato in nessuna interfaccia o servizio diverso da Yammer stesso.</span><span class="sxs-lookup"><span data-stu-id="815ce-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="815ce-522">**Esiste un gruppo di Yammer senza un gruppo di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="815ce-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="815ce-523">Sì, è possibile creare un gruppo di Yammer senza un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="815ce-524">Se la piattaforma Yammer non è connessa ai gruppi di Microsoft 365 o gli utenti non hanno la possibilità di creare un gruppo di Microsoft 365, i gruppi di Yammer vengono creati senza un'associazione di gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="815ce-525">**Possono essere presenti più gruppi di Yammer per gruppo di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="815ce-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="815ce-526">No, la relazione tra un gruppo di Yammer e un gruppo di Microsoft 365 è 1:1.</span><span class="sxs-lookup"><span data-stu-id="815ce-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="815ce-527">**Un gruppo di Yammer può essere associato a più gruppi di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="815ce-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="815ce-528">No, il gruppo Yammer può essere associato solo a un singolo gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="815ce-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="815ce-529">È possibile che i post vengano condivisi con o spostati in altri gruppi di Yammer.</span><span class="sxs-lookup"><span data-stu-id="815ce-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="815ce-530">**È possibile che l'associazione di un gruppo di Yammer con un gruppo di Microsoft 365 venga modificata?**</span><span class="sxs-lookup"><span data-stu-id="815ce-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="815ce-531">No, il gruppo Yammer può essere sempre associato al gruppo Microsoft 365 a cui è stato associato originariamente.</span><span class="sxs-lookup"><span data-stu-id="815ce-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="815ce-532">**Eliminazione del gruppo Yammer eliminare il gruppo Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="815ce-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="815ce-533">Sì, l'eliminazione del gruppo in Yammer eliminerà i contenuti e i servizi associati a un gruppo e il relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="815ce-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

