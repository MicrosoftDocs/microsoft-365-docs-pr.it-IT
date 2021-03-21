---
title: Raggruppa le interazioni dei servizi
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
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Raggruppa le interazioni dei servizi
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921025"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="3f546-103">Raggruppa le interazioni dei servizi</span><span class="sxs-lookup"><span data-stu-id="3f546-103">Groups services interactions</span></span>

<span data-ttu-id="3f546-104">I gruppi di Microsoft 365 forniscono un'infrastruttura comune per una serie di servizi e carichi di lavoro all'interno della piattaforma Microsoft 365 per offrire un'esperienza connessa per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="3f546-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="3f546-105">Di base, esiste un gruppo di Microsoft 365 per fornire:</span><span class="sxs-lookup"><span data-stu-id="3f546-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="3f546-106">Un modo per gestire l'appartenenza (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3f546-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="3f546-107">Un luogo per la messaggistica e le conversazioni (cassetta postale di Exchange, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="3f546-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="3f546-108">Posizione in cui archiviare i file (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="3f546-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="3f546-109">Calendario per la pianificazione (Exchange)</span><span class="sxs-lookup"><span data-stu-id="3f546-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="3f546-110">Blocco appunti per l'acquisizione di note (OneNote)</span><span class="sxs-lookup"><span data-stu-id="3f546-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="3f546-111">Al momento della creazione del gruppo, viene eseguito anche il provisioning di una serie di altre risorse, ma non sono visibili finché non si accede per la prima volta dal servizio:</span><span class="sxs-lookup"><span data-stu-id="3f546-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="3f546-112">Una bacheca per la gestione delle attività di gruppo (Planner)</span><span class="sxs-lookup"><span data-stu-id="3f546-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="3f546-113">Area di lavoro per la creazione di report (Power BI)</span><span class="sxs-lookup"><span data-stu-id="3f546-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="3f546-114">Un'area per i video condivisi (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="3f546-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="3f546-115">Area per moduli condivisi (moduli)</span><span class="sxs-lookup"><span data-stu-id="3f546-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="3f546-116">In Microsoft 365, altri servizi sono in grado di interagire con i gruppi di Microsoft 365 per offrire funzionalità e funzionalità aggiuntive ai membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="3f546-117">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="3f546-117">Examples of this include:</span></span>

- <span data-ttu-id="3f546-118">Power Apps per le app</span><span class="sxs-lookup"><span data-stu-id="3f546-118">Power Apps for apps</span></span>
- <span data-ttu-id="3f546-119">Power Automate per flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="3f546-119">Power Automate for workflows</span></span>
- <span data-ttu-id="3f546-120">Project on the web e Roadmap for waterfall-based project management</span><span class="sxs-lookup"><span data-stu-id="3f546-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="3f546-121">Teams per conversazioni basate su canale</span><span class="sxs-lookup"><span data-stu-id="3f546-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="3f546-122">Yammer per le community di interesse</span><span class="sxs-lookup"><span data-stu-id="3f546-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="3f546-123">Interazioni degli utenti con i gruppi</span><span class="sxs-lookup"><span data-stu-id="3f546-123">User interactions with groups</span></span>

<span data-ttu-id="3f546-124">I gruppi di Microsoft 365 possono essere creati e gestiti da un'ampia gamma di interfacce, sia da amministratori che da utenti finali.</span><span class="sxs-lookup"><span data-stu-id="3f546-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="3f546-125">Esperienze amministrative</span><span class="sxs-lookup"><span data-stu-id="3f546-125">Administrative experiences</span></span>

<span data-ttu-id="3f546-126">Gli amministratori possono creare e gestire gruppi di Microsoft 365 da diverse interfacce di amministrazione del carico di lavoro, interfacce da riga di comando che supportano gli script, nonché app personalizzate che interagiscono con l'API Graph.</span><span class="sxs-lookup"><span data-stu-id="3f546-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="3f546-127">L'unica eccezione a questo problema sono i gruppi di Yammer, che devono essere creati dall'interfaccia Web di Yammer.</span><span class="sxs-lookup"><span data-stu-id="3f546-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="3f546-128">**Impostazioni correlate**</span><span class="sxs-lookup"><span data-stu-id="3f546-128">**Related settings**</span></span>

<span data-ttu-id="3f546-129">Tra le varie interfacce amministrative in grado di gestire le impostazioni di gruppo esistono diverse sovrapposizioni di cui è necessario tenere conto.</span><span class="sxs-lookup"><span data-stu-id="3f546-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="3f546-130">**Interfaccia di amministrazione di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="3f546-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="3f546-131">Nell'interfaccia di amministrazione di Microsoft 365, l'accesso guest ai gruppi è abilitato per impostazione predefinita, così come la possibilità di consentire ai proprietari di aggiungere utenti guest.</span><span class="sxs-lookup"><span data-stu-id="3f546-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="3f546-132">Non sono disponibili altri controlli a livello di organizzazione per i gruppi di questa interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="3f546-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="3f546-133">**Interfaccia di amministrazione di Azure AD**</span><span class="sxs-lookup"><span data-stu-id="3f546-133">**Azure AD admin center**</span></span>

<span data-ttu-id="3f546-134">L'interfaccia di amministrazione di Azure AD offre controlli che consentono agli utenti di creare gruppi o assegnare proprietari nei portali di Azure, nonché le impostazioni dei criteri di scadenza e denominazione.</span><span class="sxs-lookup"><span data-stu-id="3f546-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="3f546-135">L'interfaccia di amministrazione offre anche una serie di misure di controllo degli inviti guest che vanno oltre quella dell'interfaccia di amministrazione di Microsoft 365, ad esempio la possibilità di limitare se i non proprietari possono anche invitare utenti guest</span><span class="sxs-lookup"><span data-stu-id="3f546-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="3f546-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="3f546-136">**SharePoint**</span></span>

<span data-ttu-id="3f546-137">I siti di SharePoint vengono creati con i gruppi di sicurezza Proprietario, Membro e Visitatore, con i primi due corrispondenti fino alle controparti del gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="3f546-138">Sebbene l'appartenenza ai siti di SharePoint Online sia in genere gestita dal gruppo di Microsoft 365 associato, non è una relazione bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="3f546-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="3f546-139">Qualsiasi modifica apportata all'appartenenza a livello di gruppo di Microsoft 365 si riflette in SharePoint, tuttavia, se l'appartenenza viene modificata nel gruppo di SharePoint, ciò non si riflette nel gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="3f546-140">Esperienze utente</span><span class="sxs-lookup"><span data-stu-id="3f546-140">User experiences</span></span>

<span data-ttu-id="3f546-141">Gli utenti finali possono creare gruppi da diversi servizi all'interno di Microsoft 365 e in altri possono condividere solo con un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="3f546-142">I servizi seguenti consentono la creazione di gruppi da parte degli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="3f546-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="3f546-143">Outlook Planner Project for the web SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="3f546-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="3f546-144">**Limitazione della creazione di gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-144">**Restriction of group creation**</span></span>

<span data-ttu-id="3f546-145">Un approccio comune per controllare l'espansione dei team consiste nel limitare gli utenti che possono crearli.</span><span class="sxs-lookup"><span data-stu-id="3f546-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="3f546-146">Questa operazione può essere eseguita solo limitando la creazione di gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="3f546-147">Questa operazione influisce sulla possibilità di creare gruppi da altri servizi in cui potrebbe essere necessario per l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="3f546-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="3f546-148">I gruppi di Microsoft 365 non supportano la possibilità di limitare la creazione di gruppi da alcune app o servizi consentendo al tempo stesso la creazione da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3f546-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="3f546-149">L'esperienza delle restrizioni per la creazione di gruppi varia a seconda delle app e dei servizi:</span><span class="sxs-lookup"><span data-stu-id="3f546-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="3f546-150">App o servizio</span><span class="sxs-lookup"><span data-stu-id="3f546-150">App or service</span></span>|<span data-ttu-id="3f546-151">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="3f546-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="3f546-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="3f546-152">Outlook</span></span>|<span data-ttu-id="3f546-153">**L'opzione** Nuovo gruppo viene rimossa dal menu Nuovo nella pagina utenti</span><span class="sxs-lookup"><span data-stu-id="3f546-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="3f546-154">Planner</span><span class="sxs-lookup"><span data-stu-id="3f546-154">Planner</span></span>|<span data-ttu-id="3f546-155">**Il nuovo piano** spiega che la creazione del gruppo è stata disattivata e offre di aggiungere il piano a un gruppo esistente</span><span class="sxs-lookup"><span data-stu-id="3f546-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="3f546-156">Project per il Web e roadmap</span><span class="sxs-lookup"><span data-stu-id="3f546-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="3f546-157">**Il** menu Crea gruppo spiega che la creazione del gruppo è limitata e suggerisce di usare un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="3f546-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="3f546-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3f546-158">SharePoint</span></span>|<span data-ttu-id="3f546-159">È comunque possibile creare un sito del team non connesso a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="3f546-160">Stream</span><span class="sxs-lookup"><span data-stu-id="3f546-160">Stream</span></span>|<span data-ttu-id="3f546-161">**L'opzione** Gruppo non viene visualizzata nel **menu Crea.**</span><span class="sxs-lookup"><span data-stu-id="3f546-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="3f546-162">Teams</span><span class="sxs-lookup"><span data-stu-id="3f546-162">Teams</span></span>|<span data-ttu-id="3f546-163">L'utente non può creare un team con un nuovo gruppo, ma può comunque creare un team che utilizza un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="3f546-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="3f546-164">**Il pulsante Crea team** viene sostituito con **Crea team da un gruppo.**</span><span class="sxs-lookup"><span data-stu-id="3f546-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="3f546-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="3f546-165">Yammer</span></span>|<span data-ttu-id="3f546-166">**L'opzione Crea** un gruppo viene rimossa dalla struttura di spostamento principale gruppi/community.</span><span class="sxs-lookup"><span data-stu-id="3f546-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="3f546-167">Interazioni dei servizi con i gruppi</span><span class="sxs-lookup"><span data-stu-id="3f546-167">Services interactions with groups</span></span>

<span data-ttu-id="3f546-168">Vedere il poster Gruppi in Microsoft 365 per informazioni sui diversi tipi di gruppi, su come vengono creati e gestiti e su alcuni consigli sulla governance.</span><span class="sxs-lookup"><span data-stu-id="3f546-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="3f546-169">[![Immagine di scorrimento per infografica dei gruppi](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="3f546-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="3f546-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="3f546-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="3f546-171">Nella tabella seguente viene fornita una panoramica delle interazioni dei gruppi di Microsoft 365 con vari servizi:</span><span class="sxs-lookup"><span data-stu-id="3f546-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="3f546-172">Prodotto</span><span class="sxs-lookup"><span data-stu-id="3f546-172">Product</span></span>|<span data-ttu-id="3f546-173">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="3f546-173">Features</span></span>|<span data-ttu-id="3f546-174">Il servizio</span><span class="sxs-lookup"><span data-stu-id="3f546-174">Does the service</span></span><br><span data-ttu-id="3f546-175">esiste senza un gruppo?</span><span class="sxs-lookup"><span data-stu-id="3f546-175">exist without a group?</span></span>|<span data-ttu-id="3f546-176">Può il servizio</span><span class="sxs-lookup"><span data-stu-id="3f546-176">Can the service</span></span><br><span data-ttu-id="3f546-177">creare un gruppo?</span><span class="sxs-lookup"><span data-stu-id="3f546-177">create a group?</span></span>|<span data-ttu-id="3f546-178">L'eliminazione del file</span><span class="sxs-lookup"><span data-stu-id="3f546-178">Does deleting the</span></span><br><span data-ttu-id="3f546-179">eliminare il gruppo?</span><span class="sxs-lookup"><span data-stu-id="3f546-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="3f546-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="3f546-180">Azure AD</span></span>|<span data-ttu-id="3f546-181">Appartenenza, Controlli gruppo, Guest</span><span class="sxs-lookup"><span data-stu-id="3f546-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="3f546-182">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-182">Yes</span></span>|<span data-ttu-id="3f546-183">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-183">Yes</span></span>|<span data-ttu-id="3f546-184">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-184">Yes</span></span>|
|<span data-ttu-id="3f546-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="3f546-185">Exchange</span></span>|<span data-ttu-id="3f546-186">Calendario, cassetta postale</span><span class="sxs-lookup"><span data-stu-id="3f546-186">Calendar, mailbox</span></span>|<span data-ttu-id="3f546-187">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-187">Yes</span></span>|<span data-ttu-id="3f546-188">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-188">Yes</span></span>|<span data-ttu-id="3f546-189">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-189">Yes</span></span>|
|<span data-ttu-id="3f546-190">Forms</span><span class="sxs-lookup"><span data-stu-id="3f546-190">Forms</span></span>|<span data-ttu-id="3f546-191">Modulo</span><span class="sxs-lookup"><span data-stu-id="3f546-191">Form</span></span>|<span data-ttu-id="3f546-192">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-192">Yes</span></span>|<span data-ttu-id="3f546-193">No</span><span class="sxs-lookup"><span data-stu-id="3f546-193">No</span></span>|<span data-ttu-id="3f546-194">No</span><span class="sxs-lookup"><span data-stu-id="3f546-194">No</span></span>|
|<span data-ttu-id="3f546-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="3f546-195">OneNote</span></span>|<span data-ttu-id="3f546-196">Blocco appunti</span><span class="sxs-lookup"><span data-stu-id="3f546-196">Notebook</span></span>|<span data-ttu-id="3f546-197">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-197">Yes</span></span>|<span data-ttu-id="3f546-198">No</span><span class="sxs-lookup"><span data-stu-id="3f546-198">No</span></span>|<span data-ttu-id="3f546-199">No</span><span class="sxs-lookup"><span data-stu-id="3f546-199">No</span></span>|
|<span data-ttu-id="3f546-200">Planner</span><span class="sxs-lookup"><span data-stu-id="3f546-200">Planner</span></span>|<span data-ttu-id="3f546-201">Bacheca attività</span><span class="sxs-lookup"><span data-stu-id="3f546-201">Task board</span></span>|<span data-ttu-id="3f546-202">No</span><span class="sxs-lookup"><span data-stu-id="3f546-202">No</span></span>|<span data-ttu-id="3f546-203">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-203">Yes</span></span>|<span data-ttu-id="3f546-204">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-204">Yes</span></span>|
|<span data-ttu-id="3f546-205">App Power Apps</span><span class="sxs-lookup"><span data-stu-id="3f546-205">Power Apps app</span></span>|<span data-ttu-id="3f546-206">App</span><span class="sxs-lookup"><span data-stu-id="3f546-206">App</span></span>|<span data-ttu-id="3f546-207">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-207">Yes</span></span>|<span data-ttu-id="3f546-208">No</span><span class="sxs-lookup"><span data-stu-id="3f546-208">No</span></span>|<span data-ttu-id="3f546-209">No</span><span class="sxs-lookup"><span data-stu-id="3f546-209">No</span></span>|
|<span data-ttu-id="3f546-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="3f546-210">Power Automate</span></span>|<span data-ttu-id="3f546-211">Flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3f546-211">Workflow</span></span>|<span data-ttu-id="3f546-212">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-212">Yes</span></span>|<span data-ttu-id="3f546-213">No</span><span class="sxs-lookup"><span data-stu-id="3f546-213">No</span></span>|<span data-ttu-id="3f546-214">No</span><span class="sxs-lookup"><span data-stu-id="3f546-214">No</span></span>|
|<span data-ttu-id="3f546-215">Power BI (classico)</span><span class="sxs-lookup"><span data-stu-id="3f546-215">Power BI (classic)</span></span>|<span data-ttu-id="3f546-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="3f546-216">Workspace</span></span>|<span data-ttu-id="3f546-217">No</span><span class="sxs-lookup"><span data-stu-id="3f546-217">No</span></span>|<span data-ttu-id="3f546-218">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-218">Yes</span></span>|<span data-ttu-id="3f546-219">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-219">Yes</span></span>|
|<span data-ttu-id="3f546-220">Power BI (nuovo)</span><span class="sxs-lookup"><span data-stu-id="3f546-220">Power BI (new)</span></span>|<span data-ttu-id="3f546-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="3f546-221">Workspace</span></span>|<span data-ttu-id="3f546-222">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-222">Yes</span></span>|<span data-ttu-id="3f546-223">No</span><span class="sxs-lookup"><span data-stu-id="3f546-223">No</span></span>|<span data-ttu-id="3f546-224">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-224">Yes</span></span>|
|<span data-ttu-id="3f546-225">Project per il web</span><span class="sxs-lookup"><span data-stu-id="3f546-225">Project for the web</span></span>|<span data-ttu-id="3f546-226">Piano di progetto</span><span class="sxs-lookup"><span data-stu-id="3f546-226">Project plan</span></span>|<span data-ttu-id="3f546-227">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-227">Yes</span></span>|<span data-ttu-id="3f546-228">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-228">Yes</span></span>|<span data-ttu-id="3f546-229">No</span><span class="sxs-lookup"><span data-stu-id="3f546-229">No</span></span>|
|<span data-ttu-id="3f546-230">Roadmap</span><span class="sxs-lookup"><span data-stu-id="3f546-230">Roadmap</span></span>|<span data-ttu-id="3f546-231">Roadmap</span><span class="sxs-lookup"><span data-stu-id="3f546-231">Roadmap</span></span>|<span data-ttu-id="3f546-232">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-232">Yes</span></span>|<span data-ttu-id="3f546-233">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-233">Yes</span></span>|<span data-ttu-id="3f546-234">No</span><span class="sxs-lookup"><span data-stu-id="3f546-234">No</span></span>|
|<span data-ttu-id="3f546-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3f546-235">SharePoint</span></span>|<span data-ttu-id="3f546-236">Sito</span><span class="sxs-lookup"><span data-stu-id="3f546-236">Site</span></span>|<span data-ttu-id="3f546-237">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-237">Yes</span></span>|<span data-ttu-id="3f546-238">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-238">Yes</span></span>|<span data-ttu-id="3f546-239">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-239">Yes</span></span>|
|<span data-ttu-id="3f546-240">Stream</span><span class="sxs-lookup"><span data-stu-id="3f546-240">Stream</span></span>|<span data-ttu-id="3f546-241">Canale, video</span><span class="sxs-lookup"><span data-stu-id="3f546-241">Channel, video</span></span>|<span data-ttu-id="3f546-242">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-242">Yes</span></span>|<span data-ttu-id="3f546-243">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-243">Yes</span></span>|<span data-ttu-id="3f546-244">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-244">Yes</span></span>|
|<span data-ttu-id="3f546-245">Teams</span><span class="sxs-lookup"><span data-stu-id="3f546-245">Teams</span></span>|<span data-ttu-id="3f546-246">Team</span><span class="sxs-lookup"><span data-stu-id="3f546-246">Team</span></span>|<span data-ttu-id="3f546-247">No</span><span class="sxs-lookup"><span data-stu-id="3f546-247">No</span></span>|<span data-ttu-id="3f546-248">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-248">Yes</span></span>|<span data-ttu-id="3f546-249">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-249">Yes</span></span>|
|<span data-ttu-id="3f546-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="3f546-250">Yammer</span></span>|<span data-ttu-id="3f546-251">Gruppo</span><span class="sxs-lookup"><span data-stu-id="3f546-251">Group</span></span>|<span data-ttu-id="3f546-252">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-252">Yes</span></span>|<span data-ttu-id="3f546-253">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-253">Yes</span></span>|<span data-ttu-id="3f546-254">Sì</span><span class="sxs-lookup"><span data-stu-id="3f546-254">Yes</span></span>|

<span data-ttu-id="3f546-255">Mentre la tabella precedente fornisce una panoramica generale delle interazioni di gruppo con i servizi di Microsoft 365, esistono diverse sfumature e complessità da comprendere.</span><span class="sxs-lookup"><span data-stu-id="3f546-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="3f546-256">Le sezioni seguenti illustrano in modo più approfondito i carichi di lavoro specifici e le relative interazioni con i gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="3f546-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="3f546-257">Azure AD</span></span>

<span data-ttu-id="3f546-258">Azure AD offre le funzionalità di gestione delle identità sottostanti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="3f546-259">**Funzionalità principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3f546-260">Appartenenza al gruppo</span><span class="sxs-lookup"><span data-stu-id="3f546-260">Group membership</span></span>
- <span data-ttu-id="3f546-261">Criterio di denominazione</span><span class="sxs-lookup"><span data-stu-id="3f546-261">Naming policy</span></span>
- <span data-ttu-id="3f546-262">Criteri di scadenza</span><span class="sxs-lookup"><span data-stu-id="3f546-262">Expiration policy</span></span>
- <span data-ttu-id="3f546-263">Guest</span><span class="sxs-lookup"><span data-stu-id="3f546-263">Guests</span></span>
- <span data-ttu-id="3f546-264">Restrizione della creazione di gruppi</span><span class="sxs-lookup"><span data-stu-id="3f546-264">Restriction of Group creation</span></span>

<span data-ttu-id="3f546-265">**Azure AD può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="3f546-266">Sì, i gruppi di Microsoft 365 possono essere creati da Azure AD tramite il portale Web di amministrazione, tramite PowerShell o l'API Graph.</span><span class="sxs-lookup"><span data-stu-id="3f546-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="3f546-267">**Azure AD esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="3f546-268">Sì, Azure AD esegue un gran numero di servizi che non hanno alcuna relazione con i gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="3f546-269">Ogni gruppo di Microsoft 365 è rappresentato come oggetto in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f546-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="3f546-270">**Possono essere presenti più istanze di Azure AD per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="3f546-271">No, esiste una sola istanza di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f546-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="3f546-272">**Azure AD può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="3f546-273">Sì, perché Azure AD è la piattaforma sottostante che fornisce il servizio di appartenenza ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="3f546-274">**L'associazione di Azure AD a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="3f546-275">No, Azure AD è la piattaforma sottostante in cui sono presenti gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="3f546-276">**L'eliminazione dell'istanza elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="3f546-277">L'eliminazione del gruppo in Azure AD eliminerà i servizi e il contenuto associati al gruppo pertinenti.</span><span class="sxs-lookup"><span data-stu-id="3f546-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="3f546-278">Teams</span><span class="sxs-lookup"><span data-stu-id="3f546-278">Teams</span></span>

<span data-ttu-id="3f546-279">Teams è un'area di lavoro basata su chat che mira a migliorare la collaborazione fornendo un'interfaccia singolare per interagire con un'ampia gamma di servizi Microsoft e di terze parti.</span><span class="sxs-lookup"><span data-stu-id="3f546-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="3f546-280">Per impostazione predefinita, quando viene creato un team, la cassetta postale e il calendario associati al gruppo di Microsoft 365 sono nascosti sia dall'elenco indirizzi globale in Exchange che da Outlook.</span><span class="sxs-lookup"><span data-stu-id="3f546-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="3f546-281">Questo può essere sostituito manualmente da un amministratore se l'utente desidera utilizzare sia Outlook che Teams nello stesso gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="3f546-282">**Funzionalità principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3f546-283">Conversazioni</span><span class="sxs-lookup"><span data-stu-id="3f546-283">Conversations</span></span>
- <span data-ttu-id="3f546-284">Canali & schede</span><span class="sxs-lookup"><span data-stu-id="3f546-284">Channels & tabs</span></span>
- <span data-ttu-id="3f546-285">Riunioni</span><span class="sxs-lookup"><span data-stu-id="3f546-285">Meetings</span></span>

<span data-ttu-id="3f546-286">**Teams può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="3f546-287">Sì, la creazione di un nuovo team creerà un nuovo gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="3f546-288">È inoltre possibile creare un team per un gruppo esistente che attualmente non ne dispone.</span><span class="sxs-lookup"><span data-stu-id="3f546-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="3f546-289">**I team esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="3f546-290">No, non è possibile che un team esista senza un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="3f546-291">**Possono essere presenti più team per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="3f546-292">No, la relazione tra un team e un gruppo è 1:1.</span><span class="sxs-lookup"><span data-stu-id="3f546-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="3f546-293">**Un team può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-294">No, il team stesso può essere associato solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="3f546-295">**L'associazione di un team a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="3f546-296">No, il team può essere associato solo al gruppo a cui è stato originariamente associato.</span><span class="sxs-lookup"><span data-stu-id="3f546-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="3f546-297">**L'eliminazione del team elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="3f546-298">Sì, l'eliminazione del team in Microsoft Teams eliminerà il gruppo, i servizi associati al gruppo e il contenuto.</span><span class="sxs-lookup"><span data-stu-id="3f546-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="3f546-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="3f546-299">Exchange</span></span>

<span data-ttu-id="3f546-300">Exchange Online offre funzionalità di messaggistica, calendario, contatti e associate.</span><span class="sxs-lookup"><span data-stu-id="3f546-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="3f546-301">Nel contesto di un gruppo, viene associata una sola risorsa, anziché un'intera istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="3f546-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="3f546-302">**Funzionalità principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3f546-303">Cassetta postale e calendario</span><span class="sxs-lookup"><span data-stu-id="3f546-303">Mailbox and calendar</span></span>
- <span data-ttu-id="3f546-304">Possibilità di inviare un messaggio di posta elettronica a tutti i membri del gruppo</span><span class="sxs-lookup"><span data-stu-id="3f546-304">Ability to email all Group members</span></span>
- <span data-ttu-id="3f546-305">Archiviazione delle conversazioni del canale di Teams per scopi di eDiscovery, commenti di Planner</span><span class="sxs-lookup"><span data-stu-id="3f546-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="3f546-306">**Exchange può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="3f546-307">Sì, è possibile creare un gruppo dall'interfaccia di amministrazione di Exchange Online, nonché da Outlook.</span><span class="sxs-lookup"><span data-stu-id="3f546-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="3f546-308">È inoltre possibile convertire le liste di distribuzione di Exchange in gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="3f546-309">**Exchange esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="3f546-310">Sì, Exchange Online fornisce una serie di servizi, incluse cassette postali e calendari condivisi, senza alcuna associazione di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="3f546-311">**Possono essere presenti più istanze di cassette postali o calendari di Exchange per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="3f546-312">No, può essere presente una sola cassetta postale di Exchange Online e un solo calendario per un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="3f546-313">**Le cassette postali e i calendari di Exchange possono essere associati a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-314">No, la cassetta postale e il calendario hanno una relazione 1:1 con il gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="3f546-315">È possibile condividere la cassetta postale con altri utenti o gruppi, ma ciò non stabilisce alcuna forma di associazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3f546-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="3f546-316">**L'associazione della cassetta postale o del calendario di Exchange a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="3f546-317">No, la cassetta postale e il calendario non possono essere modificati in un gruppo diverso.</span><span class="sxs-lookup"><span data-stu-id="3f546-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="3f546-318">Tuttavia, il contenuto può essere spostato da una cassetta postale a un'altra all'interno di Outlook o utilizzando uno strumento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="3f546-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="3f546-319">**L'eliminazione della cassetta postale elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="3f546-320">Sì, l'eliminazione della cassetta postale in Exchange eliminerà il gruppo, i servizi e il contenuto associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="3f546-321">Forms</span><span class="sxs-lookup"><span data-stu-id="3f546-321">Forms</span></span>

<span data-ttu-id="3f546-322">I moduli forniscono sondaggi e quiz basati sul Web.</span><span class="sxs-lookup"><span data-stu-id="3f546-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="3f546-323">**Funzionalità chiave fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="3f546-324">Proprietà dei moduli</span><span class="sxs-lookup"><span data-stu-id="3f546-324">Ownership of forms</span></span>

<span data-ttu-id="3f546-325">**I moduli possono creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="3f546-326">No, i moduli non possono creare un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="3f546-327">**I moduli esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="3f546-328">Sì, i sondaggi e i quiz possono essere creati direttamente nell'account di un utente finale.</span><span class="sxs-lookup"><span data-stu-id="3f546-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="3f546-329">**Possono essere presenti più moduli per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="3f546-330">Sì, a un gruppo possono essere associati più moduli.</span><span class="sxs-lookup"><span data-stu-id="3f546-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="3f546-331">**I moduli possono essere associati a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-332">No, un modulo può essere associato solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="3f546-333">**L'associazione di un modulo a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="3f546-334">No, una volta che un modulo è associato a un gruppo (creato direttamente all'interno o trasferito dalla proprietà da un singolo utente) non può essere spostato in un altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="3f546-335">**L'eliminazione del modulo elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="3f546-336">No, non è possibile eliminare un gruppo dall'interfaccia Forms, ma solo singoli moduli.</span><span class="sxs-lookup"><span data-stu-id="3f546-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="3f546-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="3f546-337">OneNote</span></span>

<span data-ttu-id="3f546-338">OneNote è un'applicazione per blocchi appunti digitali.</span><span class="sxs-lookup"><span data-stu-id="3f546-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="3f546-339">Il blocco appunti di OneNote creato con un gruppo è un file nel sito di SharePoint associato anziché in un servizio connesso a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="3f546-340">**Funzionalità chiave fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="3f546-341">Blocco appunti condiviso (archiviato nella raccolta di SharePoint associata al gruppo)</span><span class="sxs-lookup"><span data-stu-id="3f546-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="3f546-342">**OneNote può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="3f546-343">No, l'applicazione OneNote non può creare un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="3f546-344">**I blocchi appunti di OneNote esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="3f546-345">Sì, i blocchi appunti possono essere creati direttamente in OneDrive o in altri percorsi condivisi.</span><span class="sxs-lookup"><span data-stu-id="3f546-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="3f546-346">**Possono essere presenti più blocchi appunti di OneNote per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="3f546-347">Sì, un blocco appunti viene creato per impostazione predefinita e altri possono essere aggiunti, tuttavia qualsiasi collegamento a OneNote dai servizi associati al gruppo verrà sempre visualizzato nel blocco appunti predefinito.</span><span class="sxs-lookup"><span data-stu-id="3f546-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="3f546-348">**È possibile associare un blocco appunti di OneNote a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-349">No, il blocco appunti viene archiviato nella raccolta siti di SharePoint associata al gruppo e collegato da diverse interfacce.</span><span class="sxs-lookup"><span data-stu-id="3f546-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="3f546-350">Tuttavia, può essere condiviso con altri gruppi nello stesso modo in cui può essere condiviso con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3f546-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="3f546-351">**L'associazione del blocco appunti a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="3f546-352">No, il blocco appunti stesso è associato al gruppo ed è possibile accedervi direttamente da altri servizi connessi al gruppo, tuttavia il contenuto può essere spostato da un blocco appunti a un altro all'interno dell'applicazione OneNote.</span><span class="sxs-lookup"><span data-stu-id="3f546-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="3f546-353">**L'eliminazione del blocco appunti elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="3f546-354">No, tuttavia, se il blocco appunti di OneNote viene eliminato, potrebbero esserci collegamenti interrotti in alcuni dei servizi associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="3f546-355">Planner</span><span class="sxs-lookup"><span data-stu-id="3f546-355">Planner</span></span>

<span data-ttu-id="3f546-356">Planner è un servizio di gestione delle attività di gruppo leggero.</span><span class="sxs-lookup"><span data-stu-id="3f546-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="3f546-357">**Funzionalità chiave fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="3f546-358">Scheda per la gestione delle attività di gruppo</span><span class="sxs-lookup"><span data-stu-id="3f546-358">Board for managing group tasks</span></span>

<span data-ttu-id="3f546-359">**Planner può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="3f546-360">Sì, la creazione di un piano creerà un nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="3f546-361">**Esiste una bacheca di Planner senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="3f546-362">No, un piano deve essere associato a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="3f546-363">**Possono essere presenti più piani per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="3f546-364">Sì, possono essere presenti più piani per gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="3f546-365">**È possibile associare un piano a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-366">No, un piano si basa esclusivamente sull'appartenenza al gruppo per determinare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3f546-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="3f546-367">**L'associazione di un piano a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="3f546-368">No, tuttavia, la copia di un piano crea un nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="3f546-369">Un gruppo creato da qualsiasi altra applicazione non verrà visualizzato automaticamente in Planner per un utente.</span><span class="sxs-lookup"><span data-stu-id="3f546-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="3f546-370">Per accedere alla bacheca inizialmente dovranno aprirla da un'altra interfaccia basata su gruppo, ad esempio Outlook.</span><span class="sxs-lookup"><span data-stu-id="3f546-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="3f546-371">**L'eliminazione del piano elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="3f546-372">Sì, l'eliminazione del piano eliminerà il contenuto e i servizi associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="3f546-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="3f546-373">Power Apps</span></span>

<span data-ttu-id="3f546-374">Power Apps offre un canvas per lo sviluppo di app senza codice.</span><span class="sxs-lookup"><span data-stu-id="3f546-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="3f546-375">**Funzionalità principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3f546-376">Le app possono essere condivise con un gruppo da eseguire e modificare</span><span class="sxs-lookup"><span data-stu-id="3f546-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="3f546-377">**Power Apps può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="3f546-378">No, Power Apps non può creare un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="3f546-379">**Power Apps esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="3f546-380">Sì, le app possono essere create in Power Apps e risiedere all'interno dell'account creators fino a quando non vengono condivise o pubblicate.</span><span class="sxs-lookup"><span data-stu-id="3f546-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="3f546-381">**Possono essere presenti più app per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="3f546-382">Sì, possono essere presenti più app condivise con un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="3f546-383">**Le app possono essere associate a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-384">Sì, un'app può essere condivisa con più gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="3f546-385">**L'associazione di un'app a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="3f546-386">Sì, poiché l'associazione tra Power Apps e un gruppo di Microsoft 365 sta solo condividendo: l'app risiede ancora con il creatore.</span><span class="sxs-lookup"><span data-stu-id="3f546-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f546-387">[I gruppi devono essere abilitati per la sicurezza prima che le app possano essere condivise con essi.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="3f546-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="3f546-388">**L'eliminazione dell'app elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="3f546-389">No, le app non sono connesse al gruppo oltre a essere condivise con loro.</span><span class="sxs-lookup"><span data-stu-id="3f546-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="3f546-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="3f546-390">Power Automate</span></span>

<span data-ttu-id="3f546-391">Power Automate (in precedenza noto come Microsoft Flow) fornisce flussi di lavoro e servizi di automazione.</span><span class="sxs-lookup"><span data-stu-id="3f546-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="3f546-392">**Funzionalità chiave fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="3f546-393">I flussi di lavoro possono essere condivisi con un gruppo da eseguire e modificare.</span><span class="sxs-lookup"><span data-stu-id="3f546-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="3f546-394">**Power Automate può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="3f546-395">No, Power Automate non può creare un gruppo di Microsoft 365 nel contesto di essere associato a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="3f546-396">È tuttavia possibile creare un flusso che esegua diverse operazioni, ad esempio la creazione di un gruppo di sicurezza di Azure AD o l'aggiornamento dell'appartenenza a un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="3f546-397">**I flussi esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="3f546-398">Sì, i flussi possono essere creati in Power Automate e risiedere nell'account creators fino a quando non vengono condivisi o pubblicati.</span><span class="sxs-lookup"><span data-stu-id="3f546-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="3f546-399">**Possono essere presenti più flussi per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="3f546-400">Sì, possono essere presenti più flussi condivisi con un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="3f546-401">**Un flusso può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-402">Sì, un flusso può essere condiviso con più gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="3f546-403">**L'associazione di un flusso a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="3f546-404">Sì, poiché l'associazione tra Power Automate e un gruppo di Microsoft 365 sta solo condividendo: il flusso risiede ancora con il creatore.</span><span class="sxs-lookup"><span data-stu-id="3f546-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="3f546-405">**L'eliminazione di un flusso elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="3f546-406">No, come power apps, i flussi non sono connessi al gruppo se non condivisi con loro.</span><span class="sxs-lookup"><span data-stu-id="3f546-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="3f546-407">Power BI (classico)</span><span class="sxs-lookup"><span data-stu-id="3f546-407">Power BI (classic)</span></span>

<span data-ttu-id="3f546-408">Power BI offre dashboard e report interattivi guidati da dati.</span><span class="sxs-lookup"><span data-stu-id="3f546-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="3f546-409">**Funzionalità chiave fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="3f546-410">Creazione di report sui dati</span><span class="sxs-lookup"><span data-stu-id="3f546-410">Data reporting</span></span>

<span data-ttu-id="3f546-411">**Power BI può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="3f546-412">Sì, la creazione di un'area di lavoro classica creerà un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="3f546-413">**Esiste un'area di lavoro classica di Power BI senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="3f546-414">No, [un'area di lavoro classica in Power BI deve essere associata a un gruppo.](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)</span><span class="sxs-lookup"><span data-stu-id="3f546-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="3f546-415">**Possono essere presenti più aree di lavoro di Power BI per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="3f546-416">No, la relazione tra un'area di lavoro classica e un gruppo è 1:1.</span><span class="sxs-lookup"><span data-stu-id="3f546-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="3f546-417">**Un'area di lavoro può essere associata a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-418">Tecnicamente no, mentre l'area di lavoro classica viene creata con il gruppo, il contenuto può essere condiviso all'esterno del gruppo con utenti e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3f546-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="3f546-419">**L'associazione dell'area di lavoro a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="3f546-420">No, l'area di lavoro classica è associata al gruppo, tuttavia il contenuto può essere spostato da un'area di lavoro a un'altra nell'interfaccia di Power BI o esportando il contenuto in locale.</span><span class="sxs-lookup"><span data-stu-id="3f546-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="3f546-421">**L'eliminazione dell'area di lavoro elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="3f546-422">Sì, l'eliminazione dell'area di lavoro in Power BI eliminerà i servizi e il contenuto associati a gruppi e gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="3f546-423">Power BI (nuovo)</span><span class="sxs-lookup"><span data-stu-id="3f546-423">Power BI (new)</span></span>

<span data-ttu-id="3f546-424">Power BI offre dashboard e report interattivi guidati da dati.</span><span class="sxs-lookup"><span data-stu-id="3f546-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="3f546-425">Durante la creazione di una nuova area di lavoro in Power BI non viene creato un gruppo di Microsoft 365, la creazione di un gruppo con altri mezzi crea una nuova area di lavoro (non classica) in Power BI.</span><span class="sxs-lookup"><span data-stu-id="3f546-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="3f546-426">**Funzionalità chiave fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="3f546-427">Creazione di report sui dati</span><span class="sxs-lookup"><span data-stu-id="3f546-427">Data reporting</span></span>

<span data-ttu-id="3f546-428">**Power BI può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="3f546-429">No, non è possibile creare un gruppo di Microsoft 365 dalla nuova interfaccia di Power BI.</span><span class="sxs-lookup"><span data-stu-id="3f546-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="3f546-430">**La nuova area di lavoro di Power BI esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="3f546-431">Sì, è possibile creare report e aree di lavoro in Power BI non associati ai gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="3f546-432">**Possono essere presenti più aree di lavoro per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="3f546-433">Sì, [più aree di lavoro create da Power BI possono essere condivise con un singolo gruppo.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)</span><span class="sxs-lookup"><span data-stu-id="3f546-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="3f546-434">**Un'area di lavoro può essere associata a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-435">No, un'area di lavoro creata da Power BI può essere associata solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="3f546-436">**L'associazione di un'area di lavoro a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="3f546-437">Sì e no.</span><span class="sxs-lookup"><span data-stu-id="3f546-437">Yes and no.</span></span> <span data-ttu-id="3f546-438">Un'area di lavoro creata da Power BI può essere associata a un solo gruppo alla volta, ma può modificare l'associazione in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="3f546-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="3f546-439">Un'area di lavoro creata in Power BI da un gruppo viene associata in modo permanente a tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="3f546-440">**L'eliminazione dell'area di lavoro elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="3f546-441">Sì, l'eliminazione dell'area di lavoro in Power BI eliminerà il contenuto e i servizi associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="3f546-442">Project per il web</span><span class="sxs-lookup"><span data-stu-id="3f546-442">Project for the web</span></span>

<span data-ttu-id="3f546-443">Project per il Web offre la possibilità di creare piani di progetto, diagrammi di Gantt e roadmap.</span><span class="sxs-lookup"><span data-stu-id="3f546-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="3f546-444">Funzionalità principali fornite ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-444">Key features provided to groups.</span></span>

- <span data-ttu-id="3f546-445">Piani di progetto</span><span class="sxs-lookup"><span data-stu-id="3f546-445">Project plans</span></span>

<span data-ttu-id="3f546-446">**Project per il Web può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="3f546-447">Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente da Project per il Web.</span><span class="sxs-lookup"><span data-stu-id="3f546-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="3f546-448">**I progetti esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="3f546-449">Sì, i progetti possono esistere senza essere associati a un gruppo di Microsoft 365, tuttavia l'assegnazione delle attività richiede l'associazione di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="3f546-450">**Possono essere presenti più progetti per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="3f546-451">Sì, è possibile connettere più progetti in un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="3f546-452">**Il progetto può essere associato a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-453">No, un progetto può essere associato solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="3f546-454">**L'associazione di un progetto a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="3f546-455">No, una volta stabilita l'associazione a un gruppo, non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="3f546-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="3f546-456">**L'eliminazione del progetto elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="3f546-457">No, l'eliminazione del progetto in Project per il Web non eliminerà il gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="3f546-458">Roadmap</span><span class="sxs-lookup"><span data-stu-id="3f546-458">Roadmap</span></span>

<span data-ttu-id="3f546-459">Roadmap offre la possibilità di creare roadmap di progetto con Project per il Web e Project Online.</span><span class="sxs-lookup"><span data-stu-id="3f546-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="3f546-460">**Funzionalità principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3f546-461">Roadmap del progetto</span><span class="sxs-lookup"><span data-stu-id="3f546-461">Project roadmaps</span></span>

<span data-ttu-id="3f546-462">**La roadmap può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="3f546-463">Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente dalla roadmap.</span><span class="sxs-lookup"><span data-stu-id="3f546-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="3f546-464">**La roadmap esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="3f546-465">Sì, le roadmap possono esistere senza essere associate a un gruppo di Microsoft 365, tuttavia la condivisione della roadmap richiede l'associazione di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="3f546-466">**Possono essere presenti più roadmap per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="3f546-467">Sì, è possibile connettere più roadmap a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="3f546-468">**È possibile associare una roadmap a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-469">No, una roadmap può essere associata solo a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="3f546-470">**L'associazione di una roadmap a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="3f546-471">No, una volta stabilita l'associazione a un gruppo, non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="3f546-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="3f546-472">**L'eliminazione della roadmap elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="3f546-473">No, l'eliminazione della roadmap non eliminerà il gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="3f546-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3f546-474">SharePoint</span></span>

<span data-ttu-id="3f546-475">SharePoint è una piattaforma di gestione dei contenuti basata sul Web che fornisce, tra le altre cose, servizi di archiviazione per un certo numero di servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="3f546-476">**Funzionalità principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3f546-477">Raccolta documenti</span><span class="sxs-lookup"><span data-stu-id="3f546-477">Document library</span></span>
- <span data-ttu-id="3f546-478">Raccolta per l'archiviazione del blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="3f546-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="3f546-479">Archiviazione dei file wiki di Teams</span><span class="sxs-lookup"><span data-stu-id="3f546-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="3f546-480">**SharePoint può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="3f546-481">Sì, la creazione di un sito del team in SharePoint creerà un gruppo di Microsoft 365 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3f546-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="3f546-482">È inoltre possibile creare un gruppo e, facoltativamente, un team per un sito esistente.</span><span class="sxs-lookup"><span data-stu-id="3f546-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="3f546-483">**I siti di SharePoint esistono senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="3f546-484">Sì, SharePoint offre una serie di servizi e siti non associati al gruppo, ad esempio siti hub e di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="3f546-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="3f546-485">**Possono essere presenti più siti per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="3f546-486">No, può essere presente un solo sito per gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="3f546-487">I canali privati in Teams utilizzano siti aggiuntivi non connessi al gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="3f546-488">**I siti possono essere associati a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-489">Tecnicamente no, ma mentre un sito viene creato con un gruppo, il contenuto può essere condiviso con altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="3f546-490">**L'associazione di un sito a un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="3f546-491">No, il sito stesso è associato al gruppo, tuttavia il contenuto può essere spostato da un sito a un altro nell'interfaccia di SharePoint, esportando il contenuto in locale o utilizzando uno strumento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="3f546-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="3f546-492">**L'eliminazione del sito elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="3f546-493">Sì, l'eliminazione del sito in SharePoint eliminerà i servizi e il contenuto associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="3f546-494">Stream</span><span class="sxs-lookup"><span data-stu-id="3f546-494">Stream</span></span>

<span data-ttu-id="3f546-495">Microsoft Stream è una piattaforma di hosting e condivisione di video.</span><span class="sxs-lookup"><span data-stu-id="3f546-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="3f546-496">**Funzionalità principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3f546-497">Archiviazione video</span><span class="sxs-lookup"><span data-stu-id="3f546-497">Video storage</span></span>
- <span data-ttu-id="3f546-498">Registrazione delle riunioni di Teams</span><span class="sxs-lookup"><span data-stu-id="3f546-498">Teams meeting recording</span></span>
- <span data-ttu-id="3f546-499">Canali video</span><span class="sxs-lookup"><span data-stu-id="3f546-499">Video channels</span></span>

<span data-ttu-id="3f546-500">**Stream può creare un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="3f546-501">Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente da Stream.</span><span class="sxs-lookup"><span data-stu-id="3f546-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="3f546-502">**Stream esiste senza un gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="3f546-503">Sì, i canali video e i video possono esistere in Stream senza essere associati a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="3f546-504">**Possono essere presenti più video e canali per gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="3f546-505">Sì, possono essere presenti più video e canali in ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="3f546-506">**È possibile associare un video o un canale a più gruppi?**</span><span class="sxs-lookup"><span data-stu-id="3f546-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="3f546-507">Sì, mentre un video o un canale viene creato con un gruppo, può essere condiviso con altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="3f546-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="3f546-508">**L'associazione con un gruppo può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="3f546-509">Sì e no; I video in Stream sono di proprietà del programma di caricamento o del registratore di riunioni originale e quindi possono essere associati a qualsiasi gruppo, tuttavia i canali video possono essere associati solo al gruppo in cui sono stati originariamente creati.</span><span class="sxs-lookup"><span data-stu-id="3f546-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="3f546-510">**L'eliminazione di video o canali elimina il gruppo?**</span><span class="sxs-lookup"><span data-stu-id="3f546-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="3f546-511">No, l'eliminazione di video o canali non elimina il gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="3f546-512">Tuttavia, l'eliminazione del gruppo stesso in Stream eliminerà i servizi e il contenuto associati al gruppo, ad eccezione dei video effettivi.</span><span class="sxs-lookup"><span data-stu-id="3f546-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="3f546-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="3f546-513">Yammer</span></span>

<span data-ttu-id="3f546-514">Yammer è una piattaforma social aziendale progettata per favorire il coinvolgimento della community all'interno e tra organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3f546-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="3f546-515">La creazione di una community (in precedenza nota come "gruppo") in Yammer crea una cassetta postale, ma attualmente non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="3f546-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="3f546-516">Un gruppo di Microsoft 365 associato a Yammer non può essere utilizzato con un team in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f546-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="3f546-517">**Funzionalità principali fornite ai gruppi**</span><span class="sxs-lookup"><span data-stu-id="3f546-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3f546-518">Area conversazione</span><span class="sxs-lookup"><span data-stu-id="3f546-518">Conversation area</span></span>

<span data-ttu-id="3f546-519">**Yammer può creare un gruppo di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3f546-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="3f546-520">Sì, la creazione di un nuovo gruppo in Yammer creerà un nuovo gruppo di Microsoft 365, se le piattaforme sono connesse e l'utente ha la possibilità di creare un gruppo.</span><span class="sxs-lookup"><span data-stu-id="3f546-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="3f546-521">Non è possibile creare un gruppo di Yammer con un gruppo di Microsoft 365 associato in un'interfaccia o in un servizio diverso da Yammer stesso.</span><span class="sxs-lookup"><span data-stu-id="3f546-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="3f546-522">**Esiste un gruppo di Yammer senza un gruppo di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3f546-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="3f546-523">Sì, è possibile creare un gruppo di Yammer senza un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="3f546-524">Se la piattaforma Yammer non è connessa ai gruppi di Microsoft 365 o gli utenti non hanno la possibilità di creare un gruppo di Microsoft 365, i gruppi di Yammer vengono creati senza un'associazione di gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="3f546-525">**Possono essere presenti più gruppi di Yammer per ogni gruppo di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3f546-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="3f546-526">No, la relazione tra un gruppo di Yammer e un gruppo di Microsoft 365 è 1:1.</span><span class="sxs-lookup"><span data-stu-id="3f546-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="3f546-527">**È possibile associare un gruppo di Yammer a più gruppi di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3f546-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="3f546-528">No, il gruppo yammer può essere associato solo a un singolo gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f546-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="3f546-529">È possibile che i post siano condivisi o spostati in altri gruppi di Yammer.</span><span class="sxs-lookup"><span data-stu-id="3f546-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="3f546-530">**L'associazione di un gruppo di Yammer a un gruppo di Microsoft 365 può cambiare?**</span><span class="sxs-lookup"><span data-stu-id="3f546-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="3f546-531">No, il gruppo yammer può essere associato solo al gruppo di Microsoft 365 a cui è stato originariamente associato.</span><span class="sxs-lookup"><span data-stu-id="3f546-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="3f546-532">**L'eliminazione del gruppo di Yammer elimina il gruppo di Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3f546-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="3f546-533">Sì, l'eliminazione del gruppo in Yammer eliminerà i servizi e i contenuti associati al gruppo e al gruppo Microsoft correlati.</span><span class="sxs-lookup"><span data-stu-id="3f546-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3f546-534">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3f546-534">Related topics</span></span>

[<span data-ttu-id="3f546-535">Pianificazione dettagliata della governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="3f546-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="3f546-536">Creare il piano di governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="3f546-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)