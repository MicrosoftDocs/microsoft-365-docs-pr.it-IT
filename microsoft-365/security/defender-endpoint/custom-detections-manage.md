---
title: Visualizzare e gestire regole di rilevamento personalizzate in Microsoft Defender ATP
ms.reviewer: ''
description: Informazioni su come visualizzare e gestire regole di rilevamento personalizzate
keywords: rilevamenti personalizzati, visualizzare, gestire, avvisi, modificare, eseguire su richiesta, regole di rilevamento, ricerca avanzata, ricerca, query, azioni di risposta, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6a7fc4d4141b19f9c5129eea9b89943d07695b2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165778"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="2c3c1-104">Visualizzare e gestire regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="2c3c1-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c3c1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2c3c1-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c3c1-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2c3c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2c3c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c3c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2c3c1-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2c3c1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2c3c1-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2c3c1-110">Gestisci le regole [di rilevamento personalizzate esistenti](custom-detection-rules.md) per assicurarti che trovino in modo efficace minacce ed esercitino azioni.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="2c3c1-111">Scopri come visualizzare l'elenco delle regole, controllare le esecuzioni precedenti ed esaminare gli avvisi che hanno attivato.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="2c3c1-112">È inoltre possibile eseguire una regola su richiesta e modificarla.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="2c3c1-113">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="2c3c1-113">Required permissions</span></span>

<span data-ttu-id="2c3c1-114">Per creare o gestire rilevamenti personalizzati, [il ruolo](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) deve disporre dell'autorizzazione gestisci **impostazioni di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="2c3c1-115">Visualizzare le regole esistenti</span><span class="sxs-lookup"><span data-stu-id="2c3c1-115">View existing rules</span></span>

<span data-ttu-id="2c3c1-116">Per visualizzare tutte le regole di rilevamento personalizzate esistenti, passare a **Impostazioni**  >  **Rilevamenti personalizzati.**</span><span class="sxs-lookup"><span data-stu-id="2c3c1-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="2c3c1-117">Nella pagina sono elencate tutte le regole con le seguenti informazioni di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="2c3c1-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="2c3c1-118">**Ultima esecuzione:** data dell'ultima esecuzione di una regola per verificare la presenza di corrispondenze di query e generare avvisi</span><span class="sxs-lookup"><span data-stu-id="2c3c1-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="2c3c1-119">**Stato dell'ultima esecuzione:** indica se una regola è stata eseguita correttamente</span><span class="sxs-lookup"><span data-stu-id="2c3c1-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="2c3c1-120">**Esecuzione successiva:** l'esecuzione pianificata successiva</span><span class="sxs-lookup"><span data-stu-id="2c3c1-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="2c3c1-121">**Stato:** indica se una regola è stata attivata o disattivata</span><span class="sxs-lookup"><span data-stu-id="2c3c1-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="2c3c1-122">Visualizzare i dettagli della regola, modificare la regola ed eseguire la regola</span><span class="sxs-lookup"><span data-stu-id="2c3c1-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="2c3c1-123">Per visualizzare informazioni complete su una regola di rilevamento personalizzata, selezionare il nome della regola nell'elenco delle regole in **Impostazioni**  >  **Rilevamenti personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="2c3c1-124">In una pagina sulla regola selezionata vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c3c1-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="2c3c1-125">Informazioni generali sulla regola, inclusi i dettagli dell'avviso, lo stato di esecuzione e l'ambito</span><span class="sxs-lookup"><span data-stu-id="2c3c1-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="2c3c1-126">Elenco degli avvisi attivati</span><span class="sxs-lookup"><span data-stu-id="2c3c1-126">List of triggered alerts</span></span>
- <span data-ttu-id="2c3c1-127">Elenco delle azioni attivate</span><span class="sxs-lookup"><span data-stu-id="2c3c1-127">List of triggered actions</span></span>

<span data-ttu-id="2c3c1-128">![Pagina regola di rilevamento personalizzata](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="2c3c1-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="2c3c1-129">*Pagina regola di rilevamento personalizzata*</span><span class="sxs-lookup"><span data-stu-id="2c3c1-129">*Custom detection rule page*</span></span>

<span data-ttu-id="2c3c1-130">È inoltre possibile eseguire le azioni seguenti nella regola da questa pagina:</span><span class="sxs-lookup"><span data-stu-id="2c3c1-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="2c3c1-131">**Esegui:** eseguire immediatamente la regola.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="2c3c1-132">Questa azione reimposta anche l'intervallo per l'esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="2c3c1-133">**Modifica:** modificare la regola senza modificare la query</span><span class="sxs-lookup"><span data-stu-id="2c3c1-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="2c3c1-134">**Modifica query**: modifica la query in ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="2c3c1-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="2c3c1-135">**Attivare**  /  **Disattiva:** abilita la regola o arresta l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="2c3c1-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="2c3c1-136">**Delete:** disattivare la regola e rimuoverla</span><span class="sxs-lookup"><span data-stu-id="2c3c1-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="2c3c1-137">Per visualizzare rapidamente le informazioni ed eseguire azioni su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.</span><span class="sxs-lookup"><span data-stu-id="2c3c1-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2c3c1-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2c3c1-138">Related topics</span></span>
- [<span data-ttu-id="2c3c1-139">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="2c3c1-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="2c3c1-140">Creare regole di rilevamento</span><span class="sxs-lookup"><span data-stu-id="2c3c1-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="2c3c1-141">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="2c3c1-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2c3c1-142">Visualizzare e organizzare gli avvisi</span><span class="sxs-lookup"><span data-stu-id="2c3c1-142">View and organize alerts</span></span>](alerts-queue.md)
