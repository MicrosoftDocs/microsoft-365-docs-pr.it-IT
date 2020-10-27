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
ms.openlocfilehash: a2650efbac0966b84e6fbfd6ce78cb732f4933b3
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769654"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="041df-104">Integrazione dei ticket di ServiceNow nel centro sicurezza e conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="041df-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="041df-105">**Il periodo di anteprima per il connettore ServiceNow termina**</span><span class="sxs-lookup"><span data-stu-id="041df-105">**The preview period for the ServiceNow connector is ending**</span></span><br>
><span data-ttu-id="041df-106">Questa funzionalità non sarà più disponibile entro la fine del 2020 novembre.</span><span class="sxs-lookup"><span data-stu-id="041df-106">This capability will no longer available by the end of November 2020.</span></span> <span data-ttu-id="041df-107">La ringrazio per i commenti e il supporto continuo, mentre si determinano i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="041df-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="041df-108">ServiceNow è una popolare piattaforma di cloud computing che aiuta le aziende a gestire i flussi di lavoro digitali per le operazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="041df-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="041df-109">La piattaforma Now include i flussi di lavoro IT, i flussi di lavoro dei dipendenti e i flussi di lavoro del cliente.</span><span class="sxs-lookup"><span data-stu-id="041df-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="041df-110">Altre informazioni su ServiceNow</span><span class="sxs-lookup"><span data-stu-id="041df-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="041df-111">Microsoft ha collaborato con ServiceNow per semplificare agli amministratori IT la gestione dei ticket e delle attività in entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="041df-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="041df-112">[Microsoft 365 Security Center](overview-security-center.md) e [Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) sono stati potenziati con la possibilità di creare e registrare in modo nativo i ticket in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="041df-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="041df-113">**Gestire i ticket di ServiceNow nel centro sicurezza**</span><span class="sxs-lookup"><span data-stu-id="041df-113">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="041df-114">**Gestire i ticket di ServiceNow nel centro conformità** (prossimamente)</span><span class="sxs-lookup"><span data-stu-id="041df-114">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="041df-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="041df-115">Prerequisites</span></span>

<span data-ttu-id="041df-116">Accedere al centro sicurezza e alla conformità di Microsoft 365 e a un'istanza di ServiceNow con:</span><span class="sxs-lookup"><span data-stu-id="041df-116">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="041df-117">Kingston o versione superiore</span><span class="sxs-lookup"><span data-stu-id="041df-117">Kingston or higher version</span></span>
* <span data-ttu-id="041df-118">Dispongono di credenziali di amministratore HI</span><span class="sxs-lookup"><span data-stu-id="041df-118">Have admin HI credentials</span></span>
* <span data-ttu-id="041df-119">Disporre di privilegi di amministratore per l'istanza del fornitore di destinazione</span><span class="sxs-lookup"><span data-stu-id="041df-119">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="041df-120">ServiceNow consiglia agli utenti di mantenere le impostazioni predefinite nell'istanza di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="041df-120">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="041df-121">L'utilizzo di personalizzazioni potrebbe causare errori durante il completamento dell'elenco di controllo di installazione e l'integrazione con Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="041df-121">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="041df-122">Scambio di dati</span><span class="sxs-lookup"><span data-stu-id="041df-122">Data exchange</span></span>

<span data-ttu-id="041df-123">Quando si connette Microsoft 365 Security Center o il centro conformità a ServiceNow, Microsoft riceve i dati aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="041df-123">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="041df-124">Nome dell'istanza di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="041df-124">ServiceNow instance name</span></span>
* <span data-ttu-id="041df-125">ID client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="041df-125">ServiceNow client ID</span></span>
* <span data-ttu-id="041df-126">Segreto client di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="041df-126">ServiceNow client secret</span></span>
* <span data-ttu-id="041df-127">Token di aggiornamento & di accesso di ServiceNow</span><span class="sxs-lookup"><span data-stu-id="041df-127">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="041df-128">Quando si crea un ticket di ServiceNow dal centro sicurezza Microsoft 365 o dal centro conformità, vengono inviati i dati seguenti a ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="041df-128">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="041df-129">ID utente che avvia la creazione del ticket</span><span class="sxs-lookup"><span data-stu-id="041df-129">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="041df-130">Nome attività</span><span class="sxs-lookup"><span data-stu-id="041df-130">Task name</span></span>
* <span data-ttu-id="041df-131">Descrizione attività</span><span class="sxs-lookup"><span data-stu-id="041df-131">Task description</span></span>
* <span data-ttu-id="041df-132">Priority</span><span class="sxs-lookup"><span data-stu-id="041df-132">Priority</span></span>
* <span data-ttu-id="041df-133">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="041df-133">Due date</span></span>
* <span data-ttu-id="041df-134">Origine raccomandazione (raccomandazione utente o suggerimento Microsoft)</span><span class="sxs-lookup"><span data-stu-id="041df-134">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="041df-135">Categoria di raccomandazione (dispositivi, dati, app, identità, infrastruttura)</span><span class="sxs-lookup"><span data-stu-id="041df-135">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="041df-136">Connettersi a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="041df-136">Connect to ServiceNow</span></span>

<span data-ttu-id="041df-137">Per informazioni su come connettersi a ServiceNow, vedere [creare e monitorare i ticket di ServiceNow nel centro sicurezza Microsoft 365](tickets-security-center.md) .</span><span class="sxs-lookup"><span data-stu-id="041df-137">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="041df-138">La connessione da Microsoft 365 Compliance Center è disponibile a breve.</span><span class="sxs-lookup"><span data-stu-id="041df-138">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="041df-139">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="041df-139">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="041df-140">Viene visualizzato un messaggio di errore nel primo passaggio dell'elenco di controllo per l'installazione (OAuth Creation)</span><span class="sxs-lookup"><span data-stu-id="041df-140">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="041df-141">**Messaggio di errore** : l'operazione di lettura su' oauth_entity ' dall'ambito ' x_mioms_m365ticket ' è stata rifiutata a causa del criterio di accesso cross-scope della tabella</span><span class="sxs-lookup"><span data-stu-id="041df-141">**Error Message** : Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="041df-142">L'app presuppone che qualsiasi amministratore nell'istanza di ServiceNow possa creare e leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="041df-142">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="041df-143">Questo errore potrebbe essere causato da una personalizzazione nell'istanza di ServiceNow che limita gli utenti autorizzati a creare o leggere le entità OAuth.</span><span class="sxs-lookup"><span data-stu-id="041df-143">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="041df-144">**ServiceNow consiglia agli utenti di mantenere la funzionalità predefinita.**</span><span class="sxs-lookup"><span data-stu-id="041df-144">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="041df-145">Impostare le configurazioni di tabella "registri applicazioni" su predefinita:</span><span class="sxs-lookup"><span data-stu-id="041df-145">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="041df-146">Label = registri applicazioni</span><span class="sxs-lookup"><span data-stu-id="041df-146">Label = Application Registeries</span></span>
* <span data-ttu-id="041df-147">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="041df-147">Name = oauth_entity</span></span>
* <span data-ttu-id="041df-148">Accessibile da = tutti gli ambiti dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="041df-148">Accessible from = All application scopes</span></span>
* <span data-ttu-id="041df-149">È possibile selezionare la casella di controllo Leggi =</span><span class="sxs-lookup"><span data-stu-id="041df-149">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="041df-150">Come convalidare l'entità OAuth creata per Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="041df-150">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="041df-151">Andare alla tabella registri applicazioni ( **Menu > System OAuth > Application Registry** ) in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="041df-151">Go to application registries table ( **Menu > System OAuth > Application Registry** ) in ServiceNow.</span></span> <span data-ttu-id="041df-152">Individuare l'entità OAuth creata dall'utente, con il nome assegnato.</span><span class="sxs-lookup"><span data-stu-id="041df-152">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="041df-153">Accesso come utente di integrazione</span><span class="sxs-lookup"><span data-stu-id="041df-153">Signing in as the integration user</span></span>

<span data-ttu-id="041df-154">Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'accesso dell'utente di integrazione e la password creata nei passaggi di installazione.</span><span class="sxs-lookup"><span data-stu-id="041df-154">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="041df-155">Non utilizzare le credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="041df-155">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="041df-156">Andare alla pagina autorizzazione in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="041df-156">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="041df-157">Se l'utente ha eseguito l'accesso con le proprie credenziali personali, selezionare il collegamento **che non si trova** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="041df-157">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="041df-158">Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.</span><span class="sxs-lookup"><span data-stu-id="041df-158">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="041df-159">Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="041df-159">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="041df-160">Continuare con la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="041df-160">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="041df-161">Come convalidare l'utente di integrazione creato con l'elenco di controllo di installazione per Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="041df-161">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="041df-162">Andare alla tabella Users **(Menu > User Administration >** Users) in ServiceNow e trovare l'utente di integrazione creato da te, con il nome che l'hai assegnato.</span><span class="sxs-lookup"><span data-stu-id="041df-162">Go to Users Table **(Menu > User Administration > Users** ) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="041df-163">L'azienda dispone di accesso Single Sign-on che impedisce la connessione a ServiceNow tramite il Centro sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="041df-163">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="041df-164">Se l'azienda ha abilitato l'accesso Single Sign-on e si riceve un errore o l'accesso non è riuscito, seguire una delle due soluzioni.</span><span class="sxs-lookup"><span data-stu-id="041df-164">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="041df-165">Accedere a ServiceNow come utente di integrazione</span><span class="sxs-lookup"><span data-stu-id="041df-165">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="041df-166">Tornare alla pagina autorizzazione in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="041df-166">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="041df-167">Selezionare il collegamento **not you** nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="041df-167">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="041df-168">Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.</span><span class="sxs-lookup"><span data-stu-id="041df-168">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="041df-169">Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="041df-169">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="041df-170">Continuare con la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="041df-170">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="041df-171">Creare un utente di amministrazione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="041df-171">Create a security admin user</span></span>

1. <span data-ttu-id="041df-172">Creare un utente con privilegi di amministratore della sicurezza in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="041df-172">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="041df-173">L'utente deve avere lo stesso nome e l'indirizzo di posta elettronica dell'utente di integrazione creato dall'elenco di controllo dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="041df-173">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="041df-174">È possibile rimuovere il ruolo di amministratore della protezione una volta che l'accesso e la connessione sono state completate.</span><span class="sxs-lookup"><span data-stu-id="041df-174">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="041df-175">Accedere al centro sicurezza Microsoft 365 come utente e seguire la procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="041df-175">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="041df-176">Filtro IP</span><span class="sxs-lookup"><span data-stu-id="041df-176">IP filtering</span></span>

<span data-ttu-id="041df-177">Se è stato abilitato il filtro IP, potrebbe essere necessario consentire esplicitamente gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="041df-177">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="041df-178">Per informazioni su come consentire gli intervalli di indirizzi IP in ServiceNow, vedere [controllo di accesso all'indirizzo IP](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) .</span><span class="sxs-lookup"><span data-stu-id="041df-178">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="041df-179">Vedere gli [intervalli e i tag di servizio di Azure IP-cloud pubblico](https://www.microsoft.com/en-us/download/details.aspx?id=56519) per un elenco di indirizzi IP da consentire.</span><span class="sxs-lookup"><span data-stu-id="041df-179">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="041df-180">L'installazione è stata completata ma non è possibile visualizzare i ticket e non condividerli</span><span class="sxs-lookup"><span data-stu-id="041df-180">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="041df-181">Se i passaggi di installazione e installazione sono stati completati, ma non vengono visualizzate le schede di ServiceNow nella Home page e non è possibile condividere ServiceNow da Microsoft Secure score, controllare lo stato della pagina di provisioning in https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="041df-181">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="041df-182">Selezionare **autorizza** e tornare alla Home page.</span><span class="sxs-lookup"><span data-stu-id="041df-182">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="041df-183">Le schede devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="041df-183">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="041df-184">Risorse</span><span class="sxs-lookup"><span data-stu-id="041df-184">Resources</span></span>

- [<span data-ttu-id="041df-185">Gestire i ticket di ServiceNow nel centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="041df-185">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)
