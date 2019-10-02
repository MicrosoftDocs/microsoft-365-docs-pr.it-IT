---
title: Creare e monitorare i ticket tramite ServiceNow
description: Microsoft 365 Security Center è in fase di miglioramento grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow. In questo modo gli amministratori della sicurezza invieranno una raccomandazione di Punteggio sicuro direttamente a ServiceNow e creerà un ticket.
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350332"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="408f0-105">Gestire i ticket tramite ServiceNow</span><span class="sxs-lookup"><span data-stu-id="408f0-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="408f0-106">Microsoft 365 Security Center è in fase di miglioramento grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="408f0-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="408f0-107">Questo consente agli amministratori della sicurezza di inviare un'azione di miglioramento del [Punteggio di Microsoft Secure](microsoft-secure-score.md) direttamente a ServiceNow e di creare un ticket.</span><span class="sxs-lookup"><span data-stu-id="408f0-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="408f0-108">È possibile creare sia la gestione degli incidenti che i ticket di gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="408f0-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="408f0-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="408f0-109">Prerequisites</span></span>

<span data-ttu-id="408f0-110">Accedere al centro sicurezza Microsoft 365 e a un'istanza di ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="408f0-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="408f0-111">Kingston o versione superiore</span><span class="sxs-lookup"><span data-stu-id="408f0-111">Kingston or higher version</span></span>
* <span data-ttu-id="408f0-112">Dispongono di credenziali di amministratore HI</span><span class="sxs-lookup"><span data-stu-id="408f0-112">Have admin HI credentials</span></span>
* <span data-ttu-id="408f0-113">Disporre di privilegi di amministratore per l'istanza del fornitore di destinazione</span><span class="sxs-lookup"><span data-stu-id="408f0-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="408f0-114">ServiceNow consiglia agli utenti di tenere fuori dalle impostazioni della casella (impostazione predefinita) nell'istanza di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="408f0-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="408f0-115">L'utilizzo di personalizzazioni potrebbe causare errori durante il completamento dell'elenco di controllo di installazione e l'integrazione con Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="408f0-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="408f0-116">Scambio di dati</span><span class="sxs-lookup"><span data-stu-id="408f0-116">Data exchange</span></span>

<span data-ttu-id="408f0-117">Quando si connette Microsoft 365 Security Center a ServiceNow, Microsoft riceverà i seguenti dati aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="408f0-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="408f0-118">Nome dell'istanza di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="408f0-118">ServiceNow instance name</span></span>
* <span data-ttu-id="408f0-119">ID client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="408f0-119">ServiceNow client ID</span></span>
* <span data-ttu-id="408f0-120">Segreto client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="408f0-120">ServiceNow client secret</span></span>
* <span data-ttu-id="408f0-121">Token di aggiornamento & di accesso di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="408f0-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="408f0-122">Quando si crea un ticket ServiceNow dal centro sicurezza Microsoft 365, vengono inviati i dati seguenti a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="408f0-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="408f0-123">ID utente che avvia la creazione del ticket</span><span class="sxs-lookup"><span data-stu-id="408f0-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="408f0-124">Nome attività</span><span class="sxs-lookup"><span data-stu-id="408f0-124">Task name</span></span>
* <span data-ttu-id="408f0-125">Descrizione attività</span><span class="sxs-lookup"><span data-stu-id="408f0-125">Task description</span></span>
* <span data-ttu-id="408f0-126">Priority</span><span class="sxs-lookup"><span data-stu-id="408f0-126">Priority</span></span>
* <span data-ttu-id="408f0-127">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="408f0-127">Due date</span></span>
* <span data-ttu-id="408f0-128">Origine raccomandazione (raccomandazione utente o suggerimento Microsoft)</span><span class="sxs-lookup"><span data-stu-id="408f0-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="408f0-129">Categoria di raccomandazione (dispositivi, dati, app, identità, infrastruttura)</span><span class="sxs-lookup"><span data-stu-id="408f0-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="408f0-130">Connettere il Centro sicurezza di Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="408f0-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="408f0-131">Passare alla Home page del Centro sicurezza di Microsoft 365, dove verrà visualizzata una scheda che richiede se si utilizza ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="408f0-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![Si utilizza ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="408f0-133">Da questa pagina verrà inviata la pagina di configurazione di ServiceNow in cui verranno seguite le istruzioni per autorizzare l'app del connettore Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="408f0-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="408f0-134">Quando si autorizza la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione e non nelle credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="408f0-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="408f0-135">Dopo aver seguito le istruzioni e aver autorizzato la connessione, è possibile visualizzare lo stato della connessione sia nella pagina connessione al centro sicurezza Microsoft 365 che nell'app ServiceNow di ticketing Connector di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="408f0-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="408f0-136">Ora è tutto pronto per iniziare a creare attività.</span><span class="sxs-lookup"><span data-stu-id="408f0-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="408f0-137">Creare un'attività e condividerla con ServiceNow</span><span class="sxs-lookup"><span data-stu-id="408f0-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="408f0-138">Una volta configurata l'integrazione, è possibile creare attività di ServiceNow in base a specifiche azioni di miglioramento del Punteggio Microsoft sicuro.</span><span class="sxs-lookup"><span data-stu-id="408f0-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="408f0-139">Andare a qualsiasi azione di miglioramento in Secure score nel portale Microsoft 365 Security Center e selezionare l'icona "Condividi".</span><span class="sxs-lookup"><span data-stu-id="408f0-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="408f0-140">Una delle opzioni di menu a discesa è ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="408f0-140">One of the dropdown options is ServiceNow.</span></span>

![Condivisione di ServiceNow in un punteggio sicuro](../images/servicenow-share.png)

<span data-ttu-id="408f0-142">Verrà quindi generata un'attività in cui è possibile impostare la priorità e modificare il nome, la descrizione o la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="408f0-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="408f0-143">Una volta che tutti i campi richiesti sono stati riempiti, è possibile inviare l'attività a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="408f0-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="408f0-144">L'attività sarà visibile in ServiceNow come richiesta di modifica della sicurezza e della configurazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="408f0-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="408f0-145">Registrare i ticket</span><span class="sxs-lookup"><span data-stu-id="408f0-145">Track tickets</span></span>

<span data-ttu-id="408f0-146">Dopo aver creato i ticket per la gestione delle modifiche e la gestione degli incidenti di ServiceNow, verranno visualizzati nelle schede nella Home page del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="408f0-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="408f0-147">Da queste schede, è possibile creare un ticket, visualizzare tutti i ticket o gestire la configurazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="408f0-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Ticket di gestione delle modifiche di ServiceNow](../images/change-management-375.png)  ![Ticket per la gestione degli incidenti di ServiceNow](../images/incident-management-375.png)

<span data-ttu-id="408f0-150">Per eseguire il provisioning o la gestione dell'integrazione di ServiceNow nel centro sicurezza Microsoft 365, selezionare **Gestisci configurazione ServiceNow** su una delle schede.</span><span class="sxs-lookup"><span data-stu-id="408f0-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="408f0-151">Da qui è possibile rimuovere la connessione ServiceNow corrente e personalizzare i nomi dei ticket dello stato.</span><span class="sxs-lookup"><span data-stu-id="408f0-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="408f0-152">Con i ticket di ServiceNow visibili nel centro sicurezza Microsoft 365, le attività vivranno in un luogo in cui possono essere monitorate e attivate insieme agli altri elementi del dashboard di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="408f0-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="408f0-153">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="408f0-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="408f0-154">Sto ricevendo un errore nel primo passaggio dell'elenco di controllo di installazione (OAuth Creation)</span><span class="sxs-lookup"><span data-stu-id="408f0-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="408f0-155">**Messaggio di errore**: l'operazione di lettura su' oauth_entity ' dall'ambito ' x_mioms_m365ticket ' è stata rifiutata a causa del criterio di accesso cross-scope della tabella</span><span class="sxs-lookup"><span data-stu-id="408f0-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="408f0-156">La nostra app presuppone che qualsiasi amministratore nell'istanza di ServiceNow possa creare e leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="408f0-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="408f0-157">Questo errore potrebbe essere causato da una personalizzazione dell'istanza di ServiceNow, che limita gli utenti autorizzati a creare/leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="408f0-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="408f0-158">ServiceNow consiglia agli utenti di tenere fuori dalla funzionalità box (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="408f0-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="408f0-159">Impostare le configurazioni di tabella "registri applicazioni" su predefinita:</span><span class="sxs-lookup"><span data-stu-id="408f0-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="408f0-160">Label = registri applicazioni</span><span class="sxs-lookup"><span data-stu-id="408f0-160">Label = Application Registeries</span></span>
* <span data-ttu-id="408f0-161">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="408f0-161">Name = oauth_entity</span></span>
* <span data-ttu-id="408f0-162">Accessibile da = tutti gli ambiti dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="408f0-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="408f0-163">È possibile selezionare la casella di controllo Leggi =</span><span class="sxs-lookup"><span data-stu-id="408f0-163">Can read = check box selected</span></span>

<span data-ttu-id="408f0-164">**ServiceNow consiglia agli utenti di tenere fuori dalla funzionalità box (impostazione predefinita).**</span><span class="sxs-lookup"><span data-stu-id="408f0-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="408f0-165">Come convalidare l'entità OAuth creata per Microsoft 365 Security & Compliance Connector?</span><span class="sxs-lookup"><span data-stu-id="408f0-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="408f0-166">Andare alla tabella registri applicazioni (menu > System OAuth > Application Registry) in ServiceNow e individuare l'entità OAuth creata dall'utente (nome assegnato).</span><span class="sxs-lookup"><span data-stu-id="408f0-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="408f0-167">Come convalidare l'utente di integrazione creato nel passaggio 2 dell'elenco di controllo di installazione per Microsoft 365 Security & Compliance Connector?</span><span class="sxs-lookup"><span data-stu-id="408f0-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="408f0-168">Andare alla tabella users (menu > User Administration > Users) in ServiceNow e trovare l'utente di integrazione creato da voi (nome che è stato assegnato).</span><span class="sxs-lookup"><span data-stu-id="408f0-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="408f0-169">Quando si autorizza la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione e non nelle credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="408f0-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="408f0-170">Sono state completate le operazioni di installazione e configurazione, ma non sono in grado di visualizzare le schede di ServiceNow nella Home page e non è possibile visualizzare l'icona Condividi in Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="408f0-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="408f0-171">Controllare lo stato della pagina di provisioning accedendo a https://security.microsoft.com/ticketProvisioning.</span><span class="sxs-lookup"><span data-stu-id="408f0-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="408f0-172">Selezionare **Salva** e torna alla Home page.</span><span class="sxs-lookup"><span data-stu-id="408f0-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="408f0-173">Le schede devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="408f0-173">The cards should appear.</span></span>
