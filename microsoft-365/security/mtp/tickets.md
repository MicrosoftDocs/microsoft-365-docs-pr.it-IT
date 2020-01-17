---
title: Creare e monitorare i ticket tramite ServiceNow
description: Microsoft 365 Security Center è in fase di miglioramento grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow. Gli amministratori della sicurezza possono inviare una raccomandazione di Punteggio sicuro direttamente a ServiceNow e creare un ticket.
keywords: sicurezza, Microsoft 365, M365, Secure score, Centro sicurezza, ServiceNow, ticket, attività
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 6cd8dd42bfd1947fa8bee7a69f1febad710c808a
ms.sourcegitcommit: 7705fdbcee4f8714ce044c9e120a431023f7a367
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "41230214"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="013c4-105">Gestire i ticket tramite ServiceNow</span><span class="sxs-lookup"><span data-stu-id="013c4-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="013c4-106">Microsoft 365 Security Center è in fase di miglioramento grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="013c4-107">Gli amministratori della sicurezza possono inviare un'azione di miglioramento di [Microsoft Secure Score](microsoft-secure-score.md) direttamente a ServiceNow e creare un ticket.</span><span class="sxs-lookup"><span data-stu-id="013c4-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="013c4-108">È possibile creare sia la gestione degli incidenti che i ticket di gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="013c4-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="013c4-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="013c4-109">Prerequisites</span></span>

<span data-ttu-id="013c4-110">Accedere al centro sicurezza Microsoft 365 e a un'istanza di ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="013c4-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="013c4-111">Kingston o versione superiore</span><span class="sxs-lookup"><span data-stu-id="013c4-111">Kingston or higher version</span></span>
* <span data-ttu-id="013c4-112">Dispongono di credenziali di amministratore HI</span><span class="sxs-lookup"><span data-stu-id="013c4-112">Have admin HI credentials</span></span>
* <span data-ttu-id="013c4-113">Disporre di privilegi di amministratore per l'istanza del fornitore di destinazione</span><span class="sxs-lookup"><span data-stu-id="013c4-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="013c4-114">ServiceNow consiglia agli utenti di mantenere le impostazioni predefinite nell'istanza di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="013c4-115">L'utilizzo di personalizzazioni potrebbe causare errori durante il completamento dell'elenco di controllo di installazione e l'integrazione con Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="013c4-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="013c4-116">Scambio di dati</span><span class="sxs-lookup"><span data-stu-id="013c4-116">Data exchange</span></span>

<span data-ttu-id="013c4-117">Quando si connette Microsoft 365 Security Center a ServiceNow, Microsoft riceve i dati aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="013c4-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="013c4-118">Nome dell'istanza di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="013c4-118">ServiceNow instance name</span></span>
* <span data-ttu-id="013c4-119">ID client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="013c4-119">ServiceNow client ID</span></span>
* <span data-ttu-id="013c4-120">Segreto client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="013c4-120">ServiceNow client secret</span></span>
* <span data-ttu-id="013c4-121">Token di aggiornamento & di accesso di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="013c4-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="013c4-122">Quando si crea un ticket ServiceNow dal centro sicurezza Microsoft 365, vengono inviati i dati seguenti a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="013c4-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="013c4-123">ID utente che avvia la creazione del ticket</span><span class="sxs-lookup"><span data-stu-id="013c4-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="013c4-124">Nome attività</span><span class="sxs-lookup"><span data-stu-id="013c4-124">Task name</span></span>
* <span data-ttu-id="013c4-125">Descrizione attività</span><span class="sxs-lookup"><span data-stu-id="013c4-125">Task description</span></span>
* <span data-ttu-id="013c4-126">Priority</span><span class="sxs-lookup"><span data-stu-id="013c4-126">Priority</span></span>
* <span data-ttu-id="013c4-127">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="013c4-127">Due date</span></span>
* <span data-ttu-id="013c4-128">Origine raccomandazione (raccomandazione utente o suggerimento Microsoft)</span><span class="sxs-lookup"><span data-stu-id="013c4-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="013c4-129">Categoria di raccomandazione (dispositivi, dati, app, identità, infrastruttura)</span><span class="sxs-lookup"><span data-stu-id="013c4-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="013c4-130">Connettere il Centro sicurezza di Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="013c4-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="013c4-131">Passare alla Home page del Centro sicurezza Microsoft 365 per visualizzare la scheda di connessione ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Si utilizza ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="013c4-133">Selezionare "Connetti a ServiceNow" per accedere alla pagina di installazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="013c4-134">Seguire le istruzioni per autorizzare l'app del connettore Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="013c4-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="013c4-135">Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione.</span><span class="sxs-lookup"><span data-stu-id="013c4-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="013c4-136">Non utilizzare le credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="013c4-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="013c4-137">Dopo aver seguito le istruzioni e aver autorizzato la connessione, visualizzare lo stato della connessione sia nella pagina connessione al centro sicurezza Microsoft 365 che nell'app ServiceNow di ticketing Connector di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="013c4-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="013c4-138">Ora è tutto pronto per iniziare a creare attività.</span><span class="sxs-lookup"><span data-stu-id="013c4-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="013c4-139">Creare un'attività e condividerla con ServiceNow</span><span class="sxs-lookup"><span data-stu-id="013c4-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="013c4-140">Una volta configurata l'integrazione, creare attività di ServiceNow in base a specifiche azioni di miglioramento del Punteggio Microsoft sicuro.</span><span class="sxs-lookup"><span data-stu-id="013c4-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="013c4-141">Andare a qualsiasi azione di miglioramento in Secure score nel portale Microsoft 365 Security Center e selezionare l'icona "Condividi".</span><span class="sxs-lookup"><span data-stu-id="013c4-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="013c4-142">Una delle opzioni di menu a discesa è ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-142">One of the dropdown options is ServiceNow.</span></span>

![Condivisione di ServiceNow in un punteggio sicuro](../images/servicenow-share.png)

<span data-ttu-id="013c4-144">Viene generata un'attività in cui è possibile impostare la priorità e modificare il nome, la descrizione o la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="013c4-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="013c4-145">Una volta che tutti i campi richiesti sono stati riempiti, inviare l'attività a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="013c4-146">L'attività è visibile in ServiceNow come richiesta di modifica della sicurezza e della configurazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="013c4-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="013c4-147">Registrare i ticket</span><span class="sxs-lookup"><span data-stu-id="013c4-147">Track tickets</span></span>

<span data-ttu-id="013c4-148">Dopo aver creato i ticket di gestione dei cambiamenti di ServiceNow e gestione degli incidenti, vengono visualizzati nelle schede nella Home page del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="013c4-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="013c4-149">Da queste schede, è possibile creare un ticket, visualizzare tutti i ticket o gestire la configurazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Ticket di gestione delle modifiche di ServiceNow](../images/change-management-375.png)  ![Ticket per la gestione degli incidenti di ServiceNow](../images/incident-management-375.png)

<span data-ttu-id="013c4-152">Per eseguire il provisioning o la gestione dell'integrazione di ServiceNow nel centro sicurezza Microsoft 365, selezionare **Gestisci configurazione ServiceNow** su una delle schede.</span><span class="sxs-lookup"><span data-stu-id="013c4-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="013c4-153">Da qui, rimuovere la connessione ServiceNow corrente e personalizzare i nomi degli Stati dei ticket.</span><span class="sxs-lookup"><span data-stu-id="013c4-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="013c4-154">Con i ticket di ServiceNow visibili nel centro sicurezza Microsoft 365, le attività vengono riportate in un luogo in cui possono essere monitorate e applicate insieme agli altri elementi del dashboard di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="013c4-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="013c4-155">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="013c4-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="013c4-156">Viene visualizzato un messaggio di errore nel primo passaggio dell'elenco di controllo per l'installazione (OAuth Creation)</span><span class="sxs-lookup"><span data-stu-id="013c4-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="013c4-157">**Messaggio di errore**: l'operazione di lettura su' oauth_entity ' dall'ambito ' x_mioms_m365ticket ' è stata rifiutata a causa del criterio di accesso cross-scope della tabella</span><span class="sxs-lookup"><span data-stu-id="013c4-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="013c4-158">L'app presuppone che qualsiasi amministratore nell'istanza di ServiceNow possa creare e leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="013c4-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="013c4-159">Questo errore potrebbe essere causato da una personalizzazione dell'istanza di ServiceNow, che limita gli utenti autorizzati a creare/leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="013c4-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="013c4-160">**ServiceNow consiglia agli utenti di mantenere la funzionalità predefinita.**</span><span class="sxs-lookup"><span data-stu-id="013c4-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="013c4-161">Impostare le configurazioni di tabella "registri applicazioni" su predefinita:</span><span class="sxs-lookup"><span data-stu-id="013c4-161">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="013c4-162">Label = registri applicazioni</span><span class="sxs-lookup"><span data-stu-id="013c4-162">Label = Application Registeries</span></span>
* <span data-ttu-id="013c4-163">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="013c4-163">Name = oauth_entity</span></span>
* <span data-ttu-id="013c4-164">Accessibile da = tutti gli ambiti dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="013c4-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="013c4-165">È possibile selezionare la casella di controllo Leggi =</span><span class="sxs-lookup"><span data-stu-id="013c4-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="013c4-166">Come convalidare l'entità OAuth creata per Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="013c4-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="013c4-167">Andare alla tabella registri applicazioni (menu > System OAuth > Application Registry) in ServiceNow e individuare l'entità OAuth creata dall'utente (nome assegnato).</span><span class="sxs-lookup"><span data-stu-id="013c4-167">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="013c4-168">Accesso come utente di integrazione</span><span class="sxs-lookup"><span data-stu-id="013c4-168">Logging in as the integration user</span></span>

<span data-ttu-id="013c4-169">Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione.</span><span class="sxs-lookup"><span data-stu-id="013c4-169">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="013c4-170">Non utilizzare le credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="013c4-170">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="013c4-171">Andare alla pagina autorizzazione in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-171">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="013c4-172">Se l'utente ha eseguito l'accesso con le proprie credenziali personali, selezionare il collegamento **che non si trova** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="013c4-172">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="013c4-173">Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.</span><span class="sxs-lookup"><span data-stu-id="013c4-173">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="013c4-174">Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-174">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="013c4-175">Procedere con la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="013c4-175">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="013c4-176">Come convalidare l'utente di integrazione creato con l'elenco di controllo di installazione per Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="013c4-176">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="013c4-177">Andare alla tabella users (menu > User Administration > Users) in ServiceNow e trovare l'utente di integrazione creato da voi (nome che è stato assegnato).</span><span class="sxs-lookup"><span data-stu-id="013c4-177">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="013c4-178">L'azienda dispone di accesso Single Sign-on che impedisce la connessione a ServiceNow tramite il Centro sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="013c4-178">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="013c4-179">Se l'azienda ha abilitato il servizio Single Sign-on e viene visualizzato un errore o un account di accesso non riuscito, seguire una delle due soluzioni.</span><span class="sxs-lookup"><span data-stu-id="013c4-179">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="logging-into-servicenow-as-the-integration-user"></a><span data-ttu-id="013c4-180">Accesso a ServiceNow come utente di integrazione</span><span class="sxs-lookup"><span data-stu-id="013c4-180">Logging into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="013c4-181">Tornare alla pagina autorizzazione in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-181">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="013c4-182">Selezionare il collegamento **not you** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="013c4-182">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="013c4-183">Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.</span><span class="sxs-lookup"><span data-stu-id="013c4-183">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="013c4-184">Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="013c4-184">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="013c4-185">Procedere con la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="013c4-185">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="013c4-186">Creare un utente di amministrazione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="013c4-186">Create a security admin user</span></span>

1. <span data-ttu-id="013c4-187">Creare un utente con privilegi di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="013c4-187">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="013c4-188">L'utente deve avere lo stesso nome e l'indirizzo di posta elettronica dell'utente di integrazione creato dall'elenco di controllo dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="013c4-188">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="013c4-189">È possibile rimuovere il ruolo di amministratore della sicurezza dopo aver completato il login e la connessione.</span><span class="sxs-lookup"><span data-stu-id="013c4-189">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="013c4-190">Accedere al centro sicurezza Microsoft 365 come utente e seguire la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="013c4-190">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="013c4-191">L'installazione è stata completata ma non è possibile visualizzare i ticket e non condividerli</span><span class="sxs-lookup"><span data-stu-id="013c4-191">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="013c4-192">Se i passaggi di installazione e installazione sono stati completati, ma non vengono visualizzate le schede di ServiceNow nella Home page e non è possibile condividere ServiceNow da Microsoft Secure score, controllare lo stato della pagina di provisioning in https://security.microsoft.com/ticketProvisioning.</span><span class="sxs-lookup"><span data-stu-id="013c4-192">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="013c4-193">Selezionare **Salva** e torna alla Home page.</span><span class="sxs-lookup"><span data-stu-id="013c4-193">Select **Save** and return to the home page.</span></span> <span data-ttu-id="013c4-194">Le schede devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="013c4-194">The cards should appear.</span></span>
