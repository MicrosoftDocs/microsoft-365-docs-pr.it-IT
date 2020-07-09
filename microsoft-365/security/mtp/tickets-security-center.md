---
title: Creare e monitorare i ticket di ServiceNow nel centro sicurezza Microsoft 365
description: Informazioni su come creare e monitorare i ticket in ServiceNow dal centro sicurezza Microsoft 365.
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 48512cf2fff802509ebaa14ca69d3ca02908902e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45087922"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="4c165-104">Creare e monitorare i ticket di ServiceNow nel centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c165-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="4c165-105">Il [Centro sicurezza di Microsoft 365](overview-security-center.md) è stato migliorato grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="4c165-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="4c165-106">Altre informazioni su ServiceNow</span><span class="sxs-lookup"><span data-stu-id="4c165-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="4c165-107">Nel centro sicurezza, gli amministratori della sicurezza possono inviare un'azione di miglioramento di [Microsoft Secure Score](microsoft-secure-score.md) direttamente a ServiceNow e creare un ticket.</span><span class="sxs-lookup"><span data-stu-id="4c165-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="4c165-108">È possibile creare sia la gestione degli incidenti che i ticket di gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="4c165-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="4c165-109">Possono quindi essere registrate nella Home page del Centro sicurezza e ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="4c165-109">They can then be tracked in the security center home page, and ServiceNow.</span></span>

- [<span data-ttu-id="4c165-110">**Informazioni sui prerequisiti, lo scambio di dati e la risoluzione dei problemi**</span><span class="sxs-lookup"><span data-stu-id="4c165-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="4c165-111">**Gestire i ticket di ServiceNow nel centro conformità** (prossimamente)</span><span class="sxs-lookup"><span data-stu-id="4c165-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="4c165-112">Connettere il Centro sicurezza di Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="4c165-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="4c165-113">Passare alla Home page del Centro sicurezza Microsoft 365 per visualizzare la scheda di connessione ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="4c165-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Si utilizza ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="4c165-115">Selezionare "Connetti a ServiceNow" per accedere alla pagina di installazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="4c165-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="4c165-116">Seguire le istruzioni per autorizzare l'app del connettore Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c165-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="4c165-117">Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione.</span><span class="sxs-lookup"><span data-stu-id="4c165-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="4c165-118">Non utilizzare le credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="4c165-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="4c165-119">Dopo aver seguito le istruzioni e aver autorizzato la connessione, visualizzare lo stato della connessione sia nella pagina connessione al centro sicurezza Microsoft 365 che nell'app ServiceNow di ticketing Connector di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c165-119">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="4c165-120">Ora è tutto pronto per iniziare a creare attività.</span><span class="sxs-lookup"><span data-stu-id="4c165-120">Now you are all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="4c165-121">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4c165-121">Troubleshooting</span></span>

<span data-ttu-id="4c165-122">Informazioni sugli errori comuni che possono verificarsi nel processo di connessione e su come attenuarli nella [sezione risoluzione dei problemi](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="4c165-122">Learn common errors you may encounter in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="4c165-123">Creare un'attività e condividerla con ServiceNow</span><span class="sxs-lookup"><span data-stu-id="4c165-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="4c165-124">Una volta configurata l'integrazione, creare attività di ServiceNow in base a specifiche azioni di miglioramento del Punteggio Microsoft sicuro.</span><span class="sxs-lookup"><span data-stu-id="4c165-124">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="4c165-125">Andare a qualsiasi azione di miglioramento in Secure score nel portale Microsoft 365 Security Center e selezionare l'icona "Condividi".</span><span class="sxs-lookup"><span data-stu-id="4c165-125">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="4c165-126">Una delle opzioni di menu a discesa è ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="4c165-126">One of the dropdown options is ServiceNow.</span></span>

![Condivisione di ServiceNow in un punteggio sicuro](../../media/servicenow-share.png)

<span data-ttu-id="4c165-128">Viene generata un'attività in cui è possibile impostare la priorità e modificare il nome, la descrizione o la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="4c165-128">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="4c165-129">Una volta che tutti i campi richiesti sono stati riempiti, inviare l'attività a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="4c165-129">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="4c165-130">L'attività è visibile in ServiceNow come richiesta di modifica della sicurezza e della configurazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c165-130">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="4c165-131">Registrare i ticket</span><span class="sxs-lookup"><span data-stu-id="4c165-131">Track tickets</span></span>

<span data-ttu-id="4c165-132">Dopo aver creato i ticket di gestione dei cambiamenti di ServiceNow e gestione degli incidenti, vengono visualizzati nelle schede nella Home page del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c165-132">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="4c165-133">Da queste schede, è possibile creare un ticket, visualizzare tutti i ticket o gestire la configurazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="4c165-133">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Ticket di gestione delle modifiche di ServiceNow](../../media/change-management-375.png)  ![Ticket per la gestione degli incidenti di ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="4c165-136">Per eseguire il provisioning o la gestione dell'integrazione di ServiceNow nel centro sicurezza Microsoft 365, selezionare **Gestisci configurazione ServiceNow** su una delle schede.</span><span class="sxs-lookup"><span data-stu-id="4c165-136">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="4c165-137">Da qui, rimuovere la connessione ServiceNow corrente e personalizzare i nomi degli Stati dei ticket.</span><span class="sxs-lookup"><span data-stu-id="4c165-137">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="4c165-138">Con i ticket di ServiceNow visibili nel centro sicurezza Microsoft 365, le attività vengono riportate in un luogo in cui possono essere monitorate e applicate insieme agli altri elementi del dashboard di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4c165-138">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="4c165-139">Risorse</span><span class="sxs-lookup"><span data-stu-id="4c165-139">Resources</span></span>

- [<span data-ttu-id="4c165-140">Informazioni sui prerequisiti, lo scambio di dati e la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4c165-140">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="4c165-141">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="4c165-141">Microsoft Secure Score</span></span>](microsoft-secure-score.md)