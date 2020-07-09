---
title: Integrazione dei ticket di ServiceNow nel centro sicurezza e conformità di Microsoft 365
description: Informazioni su come creare e registrare i ticket in ServiceNow dal centro sicurezza e conformità di Microsoft 365.
keywords: sicurezza, Microsoft 365, M365, conformità, centro conformità, Centro sicurezza, ServiceNow, ticket, attività, neve, connessione
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086668"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="24fd7-104">Integrazione dei ticket di ServiceNow nel centro sicurezza e conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24fd7-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="24fd7-105">ServiceNow è una popolare piattaforma di cloud computing che aiuta le aziende a gestire i flussi di lavoro digitali per le operazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="24fd7-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="24fd7-106">La piattaforma Now include i flussi di lavoro IT, i flussi di lavoro dei dipendenti e i flussi di lavoro del cliente.</span><span class="sxs-lookup"><span data-stu-id="24fd7-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="24fd7-107">Altre informazioni su ServiceNow</span><span class="sxs-lookup"><span data-stu-id="24fd7-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="24fd7-108">Microsoft ha collaborato con ServiceNow per semplificare agli amministratori IT la gestione dei ticket e delle attività in entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="24fd7-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="24fd7-109">[Microsoft 365 Security Center](overview-security-center.md) e [Microsoft 365 Compliance Center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) sono stati potenziati con la possibilità di creare e registrare in modo nativo i ticket in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="24fd7-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="24fd7-110">**Gestire i ticket di ServiceNow nel centro sicurezza**</span><span class="sxs-lookup"><span data-stu-id="24fd7-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="24fd7-111">**Gestire i ticket di ServiceNow nel centro conformità** (prossimamente)</span><span class="sxs-lookup"><span data-stu-id="24fd7-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24fd7-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="24fd7-112">Prerequisites</span></span>

<span data-ttu-id="24fd7-113">Accedere al centro sicurezza e alla conformità di Microsoft 365 e a un'istanza di ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="24fd7-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="24fd7-114">Kingston o versione superiore</span><span class="sxs-lookup"><span data-stu-id="24fd7-114">Kingston or higher version</span></span>
* <span data-ttu-id="24fd7-115">Dispongono di credenziali di amministratore HI</span><span class="sxs-lookup"><span data-stu-id="24fd7-115">Have admin HI credentials</span></span>
* <span data-ttu-id="24fd7-116">Disporre di privilegi di amministratore per l'istanza del fornitore di destinazione</span><span class="sxs-lookup"><span data-stu-id="24fd7-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="24fd7-117">ServiceNow consiglia agli utenti di mantenere le impostazioni predefinite nell'istanza di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="24fd7-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="24fd7-118">L'utilizzo di personalizzazioni potrebbe causare errori durante il completamento dell'elenco di controllo di installazione e l'integrazione con Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="24fd7-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="24fd7-119">Scambio di dati</span><span class="sxs-lookup"><span data-stu-id="24fd7-119">Data exchange</span></span>

<span data-ttu-id="24fd7-120">Quando si connette Microsoft 365 Security Center o il centro conformità a ServiceNow, Microsoft riceve i dati aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="24fd7-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="24fd7-121">Nome dell'istanza di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="24fd7-121">ServiceNow instance name</span></span>
* <span data-ttu-id="24fd7-122">ID client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="24fd7-122">ServiceNow client ID</span></span>
* <span data-ttu-id="24fd7-123">Segreto client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="24fd7-123">ServiceNow client secret</span></span>
* <span data-ttu-id="24fd7-124">Token di aggiornamento & di accesso di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="24fd7-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="24fd7-125">Quando si crea un ticket di ServiceNow dal centro sicurezza Microsoft 365 o dal centro conformità, vengono inviati i dati seguenti a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="24fd7-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="24fd7-126">ID utente che avvia la creazione del ticket</span><span class="sxs-lookup"><span data-stu-id="24fd7-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="24fd7-127">Nome attività</span><span class="sxs-lookup"><span data-stu-id="24fd7-127">Task name</span></span>
* <span data-ttu-id="24fd7-128">Descrizione attività</span><span class="sxs-lookup"><span data-stu-id="24fd7-128">Task description</span></span>
* <span data-ttu-id="24fd7-129">Priority</span><span class="sxs-lookup"><span data-stu-id="24fd7-129">Priority</span></span>
* <span data-ttu-id="24fd7-130">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="24fd7-130">Due date</span></span>
* <span data-ttu-id="24fd7-131">Origine raccomandazione (raccomandazione utente o suggerimento Microsoft)</span><span class="sxs-lookup"><span data-stu-id="24fd7-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="24fd7-132">Categoria di raccomandazione (dispositivi, dati, app, identità, infrastruttura)</span><span class="sxs-lookup"><span data-stu-id="24fd7-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="24fd7-133">Connettersi a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="24fd7-133">Connect to ServiceNow</span></span>

<span data-ttu-id="24fd7-134">Per informazioni su come connettersi a ServiceNow, vedere [creare e monitorare i ticket di ServiceNow nel centro sicurezza Microsoft 365](tickets-security-center.md) .</span><span class="sxs-lookup"><span data-stu-id="24fd7-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="24fd7-135">La connessione da Microsoft 365 Compliance Center è disponibile a breve.</span><span class="sxs-lookup"><span data-stu-id="24fd7-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="24fd7-136">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="24fd7-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="24fd7-137">Viene visualizzato un messaggio di errore nel primo passaggio dell'elenco di controllo per l'installazione (OAuth Creation)</span><span class="sxs-lookup"><span data-stu-id="24fd7-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="24fd7-138">**Messaggio di errore**: l'operazione di lettura su' oauth_entity ' dall'ambito ' x_mioms_m365ticket ' è stata rifiutata a causa del criterio di accesso cross-scope della tabella</span><span class="sxs-lookup"><span data-stu-id="24fd7-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="24fd7-139">L'app presuppone che qualsiasi amministratore nell'istanza di ServiceNow possa creare e leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="24fd7-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="24fd7-140">Questo errore potrebbe essere causato da una personalizzazione dell'istanza di ServiceNow, che limita gli utenti autorizzati a creare/leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="24fd7-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="24fd7-141">**ServiceNow consiglia agli utenti di mantenere la funzionalità predefinita.**</span><span class="sxs-lookup"><span data-stu-id="24fd7-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="24fd7-142">Impostare le configurazioni di tabella "registri applicazioni" su predefinita:</span><span class="sxs-lookup"><span data-stu-id="24fd7-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="24fd7-143">Label = registri applicazioni</span><span class="sxs-lookup"><span data-stu-id="24fd7-143">Label = Application Registeries</span></span>
* <span data-ttu-id="24fd7-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="24fd7-144">Name = oauth_entity</span></span>
* <span data-ttu-id="24fd7-145">Accessibile da = tutti gli ambiti dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="24fd7-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="24fd7-146">È possibile selezionare la casella di controllo Leggi =</span><span class="sxs-lookup"><span data-stu-id="24fd7-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="24fd7-147">Come convalidare l'entità OAuth creata per Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="24fd7-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="24fd7-148">Andare alla tabella registri applicazioni (**Menu > System OAuth > Application Registry**) in ServiceNow e individuare l'entità OAuth creata dall'utente, con il nome assegnato.</span><span class="sxs-lookup"><span data-stu-id="24fd7-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="24fd7-149">Accesso come utente di integrazione</span><span class="sxs-lookup"><span data-stu-id="24fd7-149">Logging in as the integration user</span></span>

<span data-ttu-id="24fd7-150">Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione.</span><span class="sxs-lookup"><span data-stu-id="24fd7-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="24fd7-151">Non utilizzare le credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="24fd7-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="24fd7-152">Andare alla pagina autorizzazione in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="24fd7-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="24fd7-153">Se l'utente ha eseguito l'accesso con le proprie credenziali personali, selezionare il collegamento **che non si trova** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="24fd7-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="24fd7-154">Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.</span><span class="sxs-lookup"><span data-stu-id="24fd7-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="24fd7-155">Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="24fd7-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="24fd7-156">Procedere con la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="24fd7-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="24fd7-157">Come convalidare l'utente di integrazione creato con l'elenco di controllo di installazione per Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="24fd7-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="24fd7-158">Andare alla tabella Users **(Menu > User Administration >** Users) in ServiceNow e trovare l'utente di integrazione creato da te, con il nome che l'hai assegnato.</span><span class="sxs-lookup"><span data-stu-id="24fd7-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="24fd7-159">L'azienda dispone di accesso Single Sign-on che impedisce la connessione a ServiceNow tramite il Centro sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24fd7-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="24fd7-160">Se l'azienda ha abilitato il servizio Single Sign-on e viene visualizzato un errore o un account di accesso non riuscito, seguire una delle due soluzioni.</span><span class="sxs-lookup"><span data-stu-id="24fd7-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="24fd7-161">Accedere a ServiceNow come utente di integrazione</span><span class="sxs-lookup"><span data-stu-id="24fd7-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="24fd7-162">Tornare alla pagina autorizzazione in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="24fd7-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="24fd7-163">Selezionare il collegamento **not you** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="24fd7-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="24fd7-164">Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.</span><span class="sxs-lookup"><span data-stu-id="24fd7-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="24fd7-165">Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="24fd7-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="24fd7-166">Procedere con la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="24fd7-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="24fd7-167">Creare un utente di amministrazione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="24fd7-167">Create a security admin user</span></span>

1. <span data-ttu-id="24fd7-168">Creare un utente con privilegi di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24fd7-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="24fd7-169">L'utente deve avere lo stesso nome e l'indirizzo di posta elettronica dell'utente di integrazione creato dall'elenco di controllo dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="24fd7-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="24fd7-170">È possibile rimuovere il ruolo di amministratore della sicurezza dopo aver completato il login e la connessione.</span><span class="sxs-lookup"><span data-stu-id="24fd7-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="24fd7-171">Accedere al centro sicurezza Microsoft 365 come utente e seguire la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="24fd7-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="24fd7-172">Filtro IP</span><span class="sxs-lookup"><span data-stu-id="24fd7-172">IP filtering</span></span>

<span data-ttu-id="24fd7-173">Se è stato abilitato il filtro IP, potrebbe essere necessario consentire esplicitamente gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="24fd7-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="24fd7-174">Per informazioni su come consentire gli intervalli di indirizzi IP in ServiceNow, vedere [controllo di accesso all'indirizzo IP](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) .</span><span class="sxs-lookup"><span data-stu-id="24fd7-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="24fd7-175">Vedere gli [intervalli e i tag di servizio di Azure IP-cloud pubblico](https://www.microsoft.com/en-us/download/details.aspx?id=56519) per un elenco di indirizzi IP da consentire.</span><span class="sxs-lookup"><span data-stu-id="24fd7-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="24fd7-176">L'installazione è stata completata ma non è possibile visualizzare i ticket e non condividerli</span><span class="sxs-lookup"><span data-stu-id="24fd7-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="24fd7-177">Se i passaggi di installazione e installazione sono stati completati, ma non vengono visualizzate le schede di ServiceNow nella Home page e non è possibile condividere ServiceNow da Microsoft Secure score, controllare lo stato della pagina di provisioning in https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="24fd7-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="24fd7-178">Selezionare **autorizza** e tornare alla Home page.</span><span class="sxs-lookup"><span data-stu-id="24fd7-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="24fd7-179">Le schede devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="24fd7-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="24fd7-180">Risorse</span><span class="sxs-lookup"><span data-stu-id="24fd7-180">Resources</span></span>

- [<span data-ttu-id="24fd7-181">Gestire i ticket di ServiceNow nel centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="24fd7-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)