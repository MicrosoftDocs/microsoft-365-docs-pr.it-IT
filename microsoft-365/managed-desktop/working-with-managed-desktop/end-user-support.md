---
title: Ottenere supporto per gli utenti per Microsoft Managed Desktop
description: Come gli utenti possono ottenere assistenza con il servizio e i dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362607"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="a65a8-104">Ottenere assistenza per gli utenti</span><span class="sxs-lookup"><span data-stu-id="a65a8-104">Getting help for users</span></span>

<span data-ttu-id="a65a8-105">Se hai raggiunto il punto [](../service-description/user-support.md) del flusso di lavoro in cui devi richiedere l'accesso al dispositivo con privilegi elevati o l'escalation a Microsoft, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="a65a8-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="a65a8-106">Queste opzioni di supporto non sono disponibili per i dispositivi nel gruppo Test.</span><span class="sxs-lookup"><span data-stu-id="a65a8-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="a65a8-107">Richieste di elevazione</span><span class="sxs-lookup"><span data-stu-id="a65a8-107">Elevation requests</span></span>

<span data-ttu-id="a65a8-108">Prima di richiedere l'accesso con privilegi elevati a un dispositivo, è meglio esaminare le azioni più adatte.</span><span class="sxs-lookup"><span data-stu-id="a65a8-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="a65a8-109">**Le azioni tipiche** sono l'obiettivo di questo processo e vengono eseguite di routine durante la risoluzione dei problemi Microsoft Managed Desktop dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a65a8-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a65a8-110">Alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="a65a8-110">Examples include:</span></span>
    - <span data-ttu-id="a65a8-111">Elevazione degli strumenti di risoluzione dei problemi di sistema incorporati, del prompt dei comandi o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a65a8-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="a65a8-112">Risoluzione dei problemi delle applicazioni line-of-business</span><span class="sxs-lookup"><span data-stu-id="a65a8-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="a65a8-113">Uso di una soluzione alternativa per correggere un elemento che dovrebbe funzionare in base alla progettazione (ad esempio l'attivazione di BitLocker o l'ora di sistema non aggiornata)</span><span class="sxs-lookup"><span data-stu-id="a65a8-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="a65a8-114">Elevazione di Gestione dispositivi per eseguire operazioni quali l'aggiornamento dei driver, la disinstallazione di un dispositivo o la ricerca di nuove modifiche</span><span class="sxs-lookup"><span data-stu-id="a65a8-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="a65a8-115">**Le azioni non consigliate includono:**</span><span class="sxs-lookup"><span data-stu-id="a65a8-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="a65a8-116">Installazione di software o browser</span><span class="sxs-lookup"><span data-stu-id="a65a8-116">Installing software or browsers</span></span>
    - <span data-ttu-id="a65a8-117">Installazione di driver al di fuori delle Windows, incluse quelle per le periferiche</span><span class="sxs-lookup"><span data-stu-id="a65a8-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="a65a8-118">Installazione di .msi o .exe file</span><span class="sxs-lookup"><span data-stu-id="a65a8-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="a65a8-119">Installazione di Windows funzionalità</span><span class="sxs-lookup"><span data-stu-id="a65a8-119">Installing Windows features</span></span>

- <span data-ttu-id="a65a8-120">**Le azioni non supportate includono:**</span><span class="sxs-lookup"><span data-stu-id="a65a8-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="a65a8-121">Installazione di software o funzionalità in conflitto con Microsoft Managed Desktop di sicurezza o gestione o operazioni</span><span class="sxs-lookup"><span data-stu-id="a65a8-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="a65a8-122">Disabilitazione di Windows funzionalità necessaria per Microsoft Managed Desktop, ad esempio BitLocker</span><span class="sxs-lookup"><span data-stu-id="a65a8-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="a65a8-123">Modifica delle impostazioni gestite dall'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a65a8-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="a65a8-124">Per richiedere l'elevazione</span><span class="sxs-lookup"><span data-stu-id="a65a8-124">To request elevation</span></span>

1. <span data-ttu-id="a65a8-125">Accedere al portale [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) all'indirizzo e accedere con le credenziali Azure Active Directory utente.</span><span class="sxs-lookup"><span data-stu-id="a65a8-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="a65a8-126">Selezionare **Nuova richiesta di elevazione**.</span><span class="sxs-lookup"><span data-stu-id="a65a8-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="a65a8-127">Fornire questi dettagli:</span><span class="sxs-lookup"><span data-stu-id="a65a8-127">Provide these details:</span></span>
    - <span data-ttu-id="a65a8-128">**ID ticket di** supporto dal proprio sistema di ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="a65a8-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="a65a8-129">**Nome dispositivo:** immetti il numero di serie del dispositivo e quindi seleziona il dispositivo dal menu.</span><span class="sxs-lookup"><span data-stu-id="a65a8-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="a65a8-130">**Categoria**: selezionare la categoria più adatta al problema.</span><span class="sxs-lookup"><span data-stu-id="a65a8-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="a65a8-131">Se nessuna opzione sembra chiusa, seleziona **Altro** e fornisci altre informazioni nei campi **Titolo** **e Piano di** azione.</span><span class="sxs-lookup"><span data-stu-id="a65a8-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="a65a8-132">È meglio selezionare una categoria, se possibile.</span><span class="sxs-lookup"><span data-stu-id="a65a8-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="a65a8-133">**Sottocategoria:** selezionare quella più adatta al problema.</span><span class="sxs-lookup"><span data-stu-id="a65a8-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="a65a8-134">Se nessuna opzione sembra chiusa, seleziona **Altro** e fornisci una breve descrizione in **Titolo.**</span><span class="sxs-lookup"><span data-stu-id="a65a8-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="a65a8-135">In **Plan of action** fornire i passaggi per la risoluzione dei problemi che si prevede di eseguire dopo aver concesso l'elevazione.</span><span class="sxs-lookup"><span data-stu-id="a65a8-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="a65a8-136">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="a65a8-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="a65a8-137">Richieste di escalation</span><span class="sxs-lookup"><span data-stu-id="a65a8-137">Escalation requests</span></span>


<span data-ttu-id="a65a8-138">Se è necessario [inoltrare un](../service-description/user-support.md#escalation-portal) problema a Microsoft, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="a65a8-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="a65a8-139">Accedere al portale [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) all'indirizzo e accedere con le credenziali Azure Active Directory utente.</span><span class="sxs-lookup"><span data-stu-id="a65a8-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="a65a8-140">Selezionare **Richieste di escalation** e quindi Nuova richiesta di **escalation.**</span><span class="sxs-lookup"><span data-stu-id="a65a8-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="a65a8-141">Fornire questi dettagli:</span><span class="sxs-lookup"><span data-stu-id="a65a8-141">Provide these details:</span></span>
    - <span data-ttu-id="a65a8-142">**Categoria**: selezionare la categoria più adatta al problema.</span><span class="sxs-lookup"><span data-stu-id="a65a8-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="a65a8-143">**Title**: Fornire una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="a65a8-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="a65a8-144">**Descrizione:** aggiungere ulteriori dettagli che potrebbero aiutare il team a comprendere il problema.</span><span class="sxs-lookup"><span data-stu-id="a65a8-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="a65a8-145">Se è necessario allegare file, è possibile farlo tornando alla richiesta dopo l'invio.</span><span class="sxs-lookup"><span data-stu-id="a65a8-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="a65a8-146">**Informazioni di contatto principali:** fornire informazioni su come contattare la persona principale responsabile della collaborazione con il team.</span><span class="sxs-lookup"><span data-stu-id="a65a8-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="a65a8-147">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="a65a8-147">Select **Submit**.</span></span>
5. <span data-ttu-id="a65a8-148">Rivedere il ticket nello stesso portale per interagire con il team.</span><span class="sxs-lookup"><span data-stu-id="a65a8-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="a65a8-149">Solo i problemi di gravità C possono essere inoltrati attraverso questo percorso.</span><span class="sxs-lookup"><span data-stu-id="a65a8-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="a65a8-150">Per altri problemi, contattare l'amministratore IT per file la richiesta tramite il portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="a65a8-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>