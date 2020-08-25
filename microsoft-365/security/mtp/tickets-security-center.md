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
ms.openlocfilehash: bd5bf8533d38337c063acdf0dda073e4961e416a
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867246"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="95423-104">Creare e monitorare i ticket di ServiceNow nel centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95423-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="95423-105">Il [Centro sicurezza di Microsoft 365](overview-security-center.md) è stato migliorato grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="95423-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="95423-106">Altre informazioni su ServiceNow</span><span class="sxs-lookup"><span data-stu-id="95423-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="95423-107">Nel centro sicurezza, gli amministratori della sicurezza possono inviare un'azione di miglioramento di [Microsoft Secure Score](microsoft-secure-score.md) direttamente a ServiceNow e creare un ticket.</span><span class="sxs-lookup"><span data-stu-id="95423-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="95423-108">È possibile creare sia la gestione degli incidenti che i ticket di gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="95423-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="95423-109">Registrare i ticket nella Home page del Centro sicurezza e ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="95423-109">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="95423-110">**Informazioni sui prerequisiti, lo scambio di dati e la risoluzione dei problemi**</span><span class="sxs-lookup"><span data-stu-id="95423-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="95423-111">**Gestire i ticket di ServiceNow nel centro conformità** (prossimamente)</span><span class="sxs-lookup"><span data-stu-id="95423-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="95423-112">Connettere il Centro sicurezza di Microsoft 365 a ServiceNow</span><span class="sxs-lookup"><span data-stu-id="95423-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="95423-113">Passare alla Home page del Centro sicurezza Microsoft 365 per visualizzare la scheda di connessione ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="95423-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Si utilizza ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="95423-115">Selezionare "Connetti a ServiceNow" per accedere alla pagina di installazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="95423-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="95423-116">Seguire le istruzioni per autorizzare l'app del connettore Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95423-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="95423-117">Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione.</span><span class="sxs-lookup"><span data-stu-id="95423-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="95423-118">Non utilizzare le credenziali personali.</span><span class="sxs-lookup"><span data-stu-id="95423-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="95423-119">Dopo aver seguito le istruzioni e aver autorizzato la connessione, visualizzare lo stato della connessione nella pagina connessione al centro sicurezza di Microsoft 365 e nell'app ServiceNow di ticketing Connector di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95423-119">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="95423-120">Ora è tutto pronto per iniziare a creare attività.</span><span class="sxs-lookup"><span data-stu-id="95423-120">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="95423-121">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="95423-121">Troubleshooting</span></span>

<span data-ttu-id="95423-122">Informazioni sugli errori comuni che è possibile incontrare nel processo di connessione e su come attenuarli, nella [sezione risoluzione dei problemi](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="95423-122">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="95423-123">Creare un'attività e condividerla con ServiceNow</span><span class="sxs-lookup"><span data-stu-id="95423-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="95423-124">Una volta configurata l'integrazione, creare attività di ServiceNow in base a specifiche azioni di miglioramento del [Punteggio Microsoft sicuro](microsoft-secure-score.md) .</span><span class="sxs-lookup"><span data-stu-id="95423-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="95423-125">Passare a qualsiasi azione di miglioramento del Punteggio sicuro nel centro sicurezza Microsoft 365 e selezionare **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="95423-125">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share**.</span></span> <span data-ttu-id="95423-126">Una delle opzioni di menu a discesa è ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="95423-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="95423-127">Viene generata un'attività in cui è possibile impostare la priorità e modificare il nome, la descrizione o la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="95423-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="95423-128">Una volta che tutti i campi richiesti sono stati riempiti, inviare l'attività a ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="95423-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="95423-129">L'attività è visibile in ServiceNow come richiesta di modifica della sicurezza e della configurazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95423-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="95423-130">Registrare i ticket</span><span class="sxs-lookup"><span data-stu-id="95423-130">Track tickets</span></span>

<span data-ttu-id="95423-131">Dopo aver creato i ticket per la gestione delle modifiche e la gestione degli incidenti di ServiceNow, vengono visualizzati su schede nella Home page del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95423-131">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="95423-132">Da queste schede, è possibile creare un ticket, visualizzare tutti i ticket o gestire la configurazione di ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="95423-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Ticket di gestione delle modifiche di ServiceNow](../../media/change-management-375.png)  ![Ticket per la gestione degli incidenti di ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="95423-135">Per eseguire il provisioning o la gestione dell'integrazione di ServiceNow nel centro sicurezza Microsoft 365, selezionare **Gestisci configurazione ServiceNow** su una delle schede.</span><span class="sxs-lookup"><span data-stu-id="95423-135">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="95423-136">Da qui, rimuovere la connessione ServiceNow corrente e personalizzare i nomi degli Stati dei ticket.</span><span class="sxs-lookup"><span data-stu-id="95423-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="95423-137">Con i ticket di ServiceNow visibili nel centro sicurezza Microsoft 365, le attività vengono riportate in un luogo in cui possono essere monitorate e applicate insieme agli altri elementi del dashboard di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="95423-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="95423-138">Risorse</span><span class="sxs-lookup"><span data-stu-id="95423-138">Resources</span></span>

- [<span data-ttu-id="95423-139">Informazioni sui prerequisiti, lo scambio di dati e la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="95423-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="95423-140">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="95423-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)