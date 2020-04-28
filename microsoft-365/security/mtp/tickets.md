---
title: Creare e monitorare i ticket tramite ServiceNow
description: Microsoft 365 Security Center è in fase di miglioramento grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow. Gli amministratori della sicurezza possono inviare una raccomandazione di Punteggio sicuro direttamente a ServiceNow e creare un ticket.
keywords: sicurezza, Microsoft 365, M365, Secure score, Centro sicurezza, ServiceNow, ticket, attività
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: eb6af6b11d2d932f3bd2165aa3f597c14feb5ae8
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901023"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="f0c25-105">Gestire i ticket tramite ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f0c25-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="f0c25-106">ServiceNow è una popolare piattaforma di cloud computing che aiuta le aziende a gestire i flussi di lavoro digitali per le operazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="f0c25-106">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="f0c25-107">La piattaforma Now include i flussi di lavoro IT, i flussi di lavoro dei dipendenti e i flussi di lavoro del cliente.</span><span class="sxs-lookup"><span data-stu-id="f0c25-107">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="f0c25-108">Microsoft ha collaborato con ServiceNow per semplificare agli amministratori IT la gestione dei ticket e delle attività in entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="f0c25-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="f0c25-109">Altre informazioni su ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f0c25-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="f0c25-110">Microsoft 365 Security Center è ora migliorato grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-110">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="f0c25-111">Gli amministratori della sicurezza possono inviare un'azione di miglioramento di [Microsoft Secure Score](microsoft-secure-score.md) direttamente a ServiceNow e creare un ticket.</span><span class="sxs-lookup"><span data-stu-id="f0c25-111">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="f0c25-112">È possibile creare sia la gestione degli incidenti che i ticket di gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="f0c25-112">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="f0c25-113">Possono quindi essere registrate nella Home page del Centro protezione Microsoft e ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-113">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0c25-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f0c25-114">Prerequisites</span></span>

<span data-ttu-id="f0c25-115">Accedere al centro sicurezza Microsoft 365 e a un'istanza di ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="f0c25-115">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="f0c25-116">Kingston o versione superiore</span><span class="sxs-lookup"><span data-stu-id="f0c25-116">Kingston or higher version</span></span>
* <span data-ttu-id="f0c25-117">Dispongono di credenziali di amministratore HI</span><span class="sxs-lookup"><span data-stu-id="f0c25-117">Have admin HI credentials</span></span>
* <span data-ttu-id="f0c25-118">Disporre di privilegi di amministratore per l'istanza del fornitore di destinazione</span><span class="sxs-lookup"><span data-stu-id="f0c25-118">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="f0c25-119">ServiceNow consiglia agli utenti di mantenere le impostazioni predefinite nell'istanza di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-119">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="f0c25-120">L'utilizzo di personalizzazioni potrebbe causare errori durante il completamento dell'elenco di controllo di installazione e l'integrazione con Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="f0c25-120">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="f0c25-121">Scambio di dati</span><span class="sxs-lookup"><span data-stu-id="f0c25-121">Data exchange</span></span>

<span data-ttu-id="f0c25-122">Quando si connette Microsoft 365 Security Center a ServiceNow, Microsoft riceve i dati aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0c25-122">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="f0c25-123">Nome dell'istanza di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f0c25-123">ServiceNow instance name</span></span>
* <span data-ttu-id="f0c25-124">ID client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f0c25-124">ServiceNow client ID</span></span>
* <span data-ttu-id="f0c25-125">Segreto client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f0c25-125">ServiceNow client secret</span></span>
* <span data-ttu-id="f0c25-126">Token di aggiornamento & di accesso di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f0c25-126">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="f0c25-127">Quando si crea un ticket ServiceNow dal centro sicurezza Microsoft 365, vengono inviati i dati seguenti a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="f0c25-127">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="f0c25-128">ID utente che avvia la creazione del ticket</span><span class="sxs-lookup"><span data-stu-id="f0c25-128">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="f0c25-129">Nome attività</span><span class="sxs-lookup"><span data-stu-id="f0c25-129">Task name</span></span>
* <span data-ttu-id="f0c25-130">Descrizione attività</span><span class="sxs-lookup"><span data-stu-id="f0c25-130">Task description</span></span>
* <span data-ttu-id="f0c25-131">Priority</span><span class="sxs-lookup"><span data-stu-id="f0c25-131">Priority</span></span>
* <span data-ttu-id="f0c25-132">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="f0c25-132">Due date</span></span>
* <span data-ttu-id="f0c25-133">Origine raccomandazione (raccomandazione utente o suggerimento Microsoft)</span><span class="sxs-lookup"><span data-stu-id="f0c25-133">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="f0c25-134">Categoria di raccomandazione (dispositivi, dati, app, identità, infrastruttura)</span><span class="sxs-lookup"><span data-stu-id="f0c25-134">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="f0c25-135">Connettere il Centro sicurezza di Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f0c25-135">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="f0c25-136">Passare alla Home page del Centro sicurezza Microsoft 365 per visualizzare la scheda di connessione ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-136">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Si utilizza ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="f0c25-138">Selezionare "Connetti a ServiceNow" per accedere alla pagina di installazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-138">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="f0c25-139">Seguire le istruzioni per autorizzare l'app del connettore Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0c25-139">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="f0c25-140">Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-140">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="f0c25-141">Non utilizzare le credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="f0c25-141">Do not use your personal credentials.</span></span>

<span data-ttu-id="f0c25-142">Dopo aver seguito le istruzioni e aver autorizzato la connessione, visualizzare lo stato della connessione sia nella pagina connessione al centro sicurezza Microsoft 365 che nell'app ServiceNow di ticketing Connector di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0c25-142">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="f0c25-143">Ora è tutto pronto per iniziare a creare attività.</span><span class="sxs-lookup"><span data-stu-id="f0c25-143">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="f0c25-144">Creare un'attività e condividerla con ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f0c25-144">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="f0c25-145">Una volta configurata l'integrazione, creare attività di ServiceNow in base a specifiche azioni di miglioramento del Punteggio Microsoft sicuro.</span><span class="sxs-lookup"><span data-stu-id="f0c25-145">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="f0c25-146">Andare a qualsiasi azione di miglioramento in Secure score nel portale Microsoft 365 Security Center e selezionare l'icona "Condividi".</span><span class="sxs-lookup"><span data-stu-id="f0c25-146">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="f0c25-147">Una delle opzioni di menu a discesa è ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-147">One of the dropdown options is ServiceNow.</span></span>

![Condivisione di ServiceNow in un punteggio sicuro](../../media/servicenow-share.png)

<span data-ttu-id="f0c25-149">Viene generata un'attività in cui è possibile impostare la priorità e modificare il nome, la descrizione o la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="f0c25-149">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="f0c25-150">Una volta che tutti i campi richiesti sono stati riempiti, inviare l'attività a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-150">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="f0c25-151">L'attività è visibile in ServiceNow come richiesta di modifica della sicurezza e della configurazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0c25-151">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="f0c25-152">Registrare i ticket</span><span class="sxs-lookup"><span data-stu-id="f0c25-152">Track tickets</span></span>

<span data-ttu-id="f0c25-153">Dopo aver creato i ticket di gestione dei cambiamenti di ServiceNow e gestione degli incidenti, vengono visualizzati nelle schede nella Home page del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0c25-153">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="f0c25-154">Da queste schede, è possibile creare un ticket, visualizzare tutti i ticket o gestire la configurazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-154">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Ticket di gestione delle modifiche di ServiceNow](../../media/change-management-375.png)  ![Ticket per la gestione degli incidenti di ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="f0c25-157">Per eseguire il provisioning o la gestione dell'integrazione di ServiceNow nel centro sicurezza Microsoft 365, selezionare **Gestisci configurazione ServiceNow** su una delle schede.</span><span class="sxs-lookup"><span data-stu-id="f0c25-157">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="f0c25-158">Da qui, rimuovere la connessione ServiceNow corrente e personalizzare i nomi degli Stati dei ticket.</span><span class="sxs-lookup"><span data-stu-id="f0c25-158">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="f0c25-159">Con i ticket di ServiceNow visibili nel centro sicurezza Microsoft 365, le attività vengono riportate in un luogo in cui possono essere monitorate e applicate insieme agli altri elementi del dashboard di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f0c25-159">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f0c25-160">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="f0c25-160">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="f0c25-161">Viene visualizzato un messaggio di errore nel primo passaggio dell'elenco di controllo per l'installazione (OAuth Creation)</span><span class="sxs-lookup"><span data-stu-id="f0c25-161">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="f0c25-162">**Messaggio di errore**: l'operazione di lettura su' oauth_entity ' dall'ambito ' x_mioms_m365ticket ' è stata rifiutata a causa del criterio di accesso cross-scope della tabella</span><span class="sxs-lookup"><span data-stu-id="f0c25-162">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="f0c25-163">L'app presuppone che qualsiasi amministratore nell'istanza di ServiceNow possa creare e leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="f0c25-163">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="f0c25-164">Questo errore potrebbe essere causato da una personalizzazione dell'istanza di ServiceNow, che limita gli utenti autorizzati a creare/leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="f0c25-164">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="f0c25-165">**ServiceNow consiglia agli utenti di mantenere la funzionalità predefinita.**</span><span class="sxs-lookup"><span data-stu-id="f0c25-165">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="f0c25-166">Impostare le configurazioni di tabella "registri applicazioni" su predefinita:</span><span class="sxs-lookup"><span data-stu-id="f0c25-166">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="f0c25-167">Label = registri applicazioni</span><span class="sxs-lookup"><span data-stu-id="f0c25-167">Label = Application Registeries</span></span>
* <span data-ttu-id="f0c25-168">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="f0c25-168">Name = oauth_entity</span></span>
* <span data-ttu-id="f0c25-169">Accessibile da = tutti gli ambiti dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="f0c25-169">Accessible from = All application scopes</span></span>
* <span data-ttu-id="f0c25-170">È possibile selezionare la casella di controllo Leggi =</span><span class="sxs-lookup"><span data-stu-id="f0c25-170">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="f0c25-171">Come convalidare l'entità OAuth creata per Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="f0c25-171">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="f0c25-172">Andare alla tabella registri applicazioni (**Menu > System OAuth > Application Registry**) in ServiceNow e individuare l'entità OAuth creata dall'utente, con il nome assegnato.</span><span class="sxs-lookup"><span data-stu-id="f0c25-172">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="f0c25-173">Accesso come utente di integrazione</span><span class="sxs-lookup"><span data-stu-id="f0c25-173">Logging in as the integration user</span></span>

<span data-ttu-id="f0c25-174">Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-174">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="f0c25-175">Non utilizzare le credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="f0c25-175">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="f0c25-176">Andare alla pagina autorizzazione in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-176">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="f0c25-177">Se l'utente ha eseguito l'accesso con le proprie credenziali personali, selezionare il collegamento **che non si trova** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="f0c25-177">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="f0c25-178">Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-178">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="f0c25-179">Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-179">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="f0c25-180">Procedere con la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-180">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="f0c25-181">Come convalidare l'utente di integrazione creato con l'elenco di controllo di installazione per Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="f0c25-181">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="f0c25-182">Andare alla tabella Users **(Menu > User Administration >** Users) in ServiceNow e trovare l'utente di integrazione creato da te, con il nome che l'hai assegnato.</span><span class="sxs-lookup"><span data-stu-id="f0c25-182">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="f0c25-183">L'azienda dispone di accesso Single Sign-on che impedisce la connessione a ServiceNow tramite il Centro sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0c25-183">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="f0c25-184">Se l'azienda ha abilitato il servizio Single Sign-on e viene visualizzato un errore o un account di accesso non riuscito, seguire una delle due soluzioni.</span><span class="sxs-lookup"><span data-stu-id="f0c25-184">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="f0c25-185">Accedere a ServiceNow come utente di integrazione</span><span class="sxs-lookup"><span data-stu-id="f0c25-185">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="f0c25-186">Tornare alla pagina autorizzazione in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-186">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="f0c25-187">Selezionare il collegamento **not you** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="f0c25-187">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="f0c25-188">Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-188">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="f0c25-189">Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="f0c25-189">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="f0c25-190">Procedere con la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-190">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="f0c25-191">Creare un utente di amministrazione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f0c25-191">Create a security admin user</span></span>

1. <span data-ttu-id="f0c25-192">Creare un utente con privilegi di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0c25-192">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="f0c25-193">L'utente deve avere lo stesso nome e l'indirizzo di posta elettronica dell'utente di integrazione creato dall'elenco di controllo dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-193">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="f0c25-194">È possibile rimuovere il ruolo di amministratore della sicurezza dopo aver completato il login e la connessione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-194">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="f0c25-195">Accedere al centro sicurezza Microsoft 365 come utente e seguire la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="f0c25-195">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="f0c25-196">Filtro IP</span><span class="sxs-lookup"><span data-stu-id="f0c25-196">IP filtering</span></span>

<span data-ttu-id="f0c25-197">Se è stato abilitato il filtro IP, potrebbe essere necessario consentire esplicitamente gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="f0c25-197">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="f0c25-198">Per informazioni su come consentire gli intervalli di indirizzi IP in ServiceNow, vedere [controllo di accesso all'indirizzo IP](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) .</span><span class="sxs-lookup"><span data-stu-id="f0c25-198">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="f0c25-199">Vedere gli [intervalli e i tag di servizio di Azure IP-cloud pubblico](https://www.microsoft.com/en-us/download/details.aspx?id=56519) per un elenco di indirizzi IP da consentire.</span><span class="sxs-lookup"><span data-stu-id="f0c25-199">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="f0c25-200">L'installazione è stata completata ma non è possibile visualizzare i ticket e non condividerli</span><span class="sxs-lookup"><span data-stu-id="f0c25-200">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="f0c25-201">Se i passaggi di installazione e installazione sono stati completati, ma non vengono visualizzate le schede di ServiceNow nella Home page e non è possibile condividere ServiceNow da Microsoft Secure score, controllare lo stato della pagina di provisioning in https://security.microsoft.com/ticketProvisioning.</span><span class="sxs-lookup"><span data-stu-id="f0c25-201">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="f0c25-202">Selezionare **autorizza** e tornare alla Home page.</span><span class="sxs-lookup"><span data-stu-id="f0c25-202">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="f0c25-203">Le schede devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="f0c25-203">The cards should appear.</span></span>

