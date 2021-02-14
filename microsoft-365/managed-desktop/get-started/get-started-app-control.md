---
title: Introduzione al controllo delle applicazioni
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430460"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="9e6de-103">Introduzione al controllo delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="9e6de-103">Get started with app control</span></span>

<span data-ttu-id="9e6de-104">Prima di abilitare il controllo delle app nel tuo ambiente, assicurati di esaminare e comprendere in che modo [Microsoft Managed Desktop](../service-description/app-control.md) lo implementa e i tuoi ruoli e responsabilità.</span><span class="sxs-lookup"><span data-stu-id="9e6de-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="9e6de-105">Microsoft Managed Desktop semplifica il controllo delle app prendendosi cura degli aspetti più impegnativi di ottenere un criterio di base sicuro.</span><span class="sxs-lookup"><span data-stu-id="9e6de-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="9e6de-106">Gli amministratori IT devono comunque testare le app nell'anello Test ed esaminare i log per verificare la presenza di avvisi o errori.</span><span class="sxs-lookup"><span data-stu-id="9e6de-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="9e6de-107">Se un'app necessita di un'esenzione, puoi richiedere una richiesta o Microsoft Managed Desktop Operation potrebbe, a seconda di chi la rileva per prima.</span><span class="sxs-lookup"><span data-stu-id="9e6de-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="9e6de-108">Distribuzione iniziale delle app</span><span class="sxs-lookup"><span data-stu-id="9e6de-108">Initial deployment of apps</span></span>

<span data-ttu-id="9e6de-109">Quando distribuisci per la prima volta le app, Microsoft Managed Desktop deve valutarne il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="9e6de-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="9e6de-110">I passaggi esatti per abilitare il controllo delle app dipendono dal fatto che i dispositivi siano già stati distribuiti nel tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="9e6de-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="9e6de-111">Dispositivi non ancora in uso</span><span class="sxs-lookup"><span data-stu-id="9e6de-111">Devices not yet in use</span></span>

<span data-ttu-id="9e6de-112">Se non hai ancora dispositivi in uso, apri un ticket di servizio con Microsoft Managed Desktop Operations che richiede di attivare il controllo delle app.</span><span class="sxs-lookup"><span data-stu-id="9e6de-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="9e6de-113">Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:</span><span class="sxs-lookup"><span data-stu-id="9e6de-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="9e6de-114">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="9e6de-114">Deployment group</span></span>  |<span data-ttu-id="9e6de-115">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="9e6de-115">Policy type</span></span>  |<span data-ttu-id="9e6de-116">Tempistiche</span><span class="sxs-lookup"><span data-stu-id="9e6de-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9e6de-117">Test</span><span class="sxs-lookup"><span data-stu-id="9e6de-117">Test</span></span>     |  <span data-ttu-id="9e6de-118">Audit</span><span class="sxs-lookup"><span data-stu-id="9e6de-118">Audit</span></span>       |  <span data-ttu-id="9e6de-119">Giorno 0</span><span class="sxs-lookup"><span data-stu-id="9e6de-119">Day 0</span></span>       |
|<span data-ttu-id="9e6de-120">First</span><span class="sxs-lookup"><span data-stu-id="9e6de-120">First</span></span>     | <span data-ttu-id="9e6de-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="9e6de-121">Enforced</span></span>        | <span data-ttu-id="9e6de-122">Giorno 1</span><span class="sxs-lookup"><span data-stu-id="9e6de-122">Day 1</span></span>        |
|<span data-ttu-id="9e6de-123">Veloce</span><span class="sxs-lookup"><span data-stu-id="9e6de-123">Fast</span></span>     | <span data-ttu-id="9e6de-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="9e6de-124">Enforced</span></span>        |  <span data-ttu-id="9e6de-125">Giorno 2</span><span class="sxs-lookup"><span data-stu-id="9e6de-125">Day 2</span></span>       |
|<span data-ttu-id="9e6de-126">Generale</span><span class="sxs-lookup"><span data-stu-id="9e6de-126">Broad</span></span>     | <span data-ttu-id="9e6de-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="9e6de-127">Enforced</span></span>        |  <span data-ttu-id="9e6de-128">Giorno 3</span><span class="sxs-lookup"><span data-stu-id="9e6de-128">Day 3</span></span>       |

<span data-ttu-id="9e6de-129">È sempre possibile aprire un'altra richiesta di servizio per sospendere o eseguire il rollback di parte di questa distribuzione in qualsiasi momento durante l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="9e6de-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="9e6de-130">Dispositivi già in uso</span><span class="sxs-lookup"><span data-stu-id="9e6de-130">Devices already in use</span></span>

<span data-ttu-id="9e6de-131">Se è già in uso almeno un dispositivo Microsoft Managed Desktop, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="9e6de-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="9e6de-132">Apri un ticket di servizio con Microsoft Managed Desktop Operations che richiede di attivare il controllo dell'app.</span><span class="sxs-lookup"><span data-stu-id="9e6de-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="9e6de-133">Le operazioni distribuiranno [un criterio di](../service-description/app-control.md#audit-policy) controllo a tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9e6de-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="9e6de-134">[Testare le applicazioni](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) per verificare se ne verrebbero bloccate.</span><span class="sxs-lookup"><span data-stu-id="9e6de-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="9e6de-135">Se un'applicazione viene bloccata, aprire una [richiesta del firmatario.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)</span><span class="sxs-lookup"><span data-stu-id="9e6de-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="9e6de-136">Dopo aver completato il test (indipendentemente dai risultati), notifica operazioni, segnalando eventuali richieste di firmatario in sospeso.</span><span class="sxs-lookup"><span data-stu-id="9e6de-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="9e6de-137">Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:</span><span class="sxs-lookup"><span data-stu-id="9e6de-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="9e6de-138">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="9e6de-138">Deployment group</span></span>  |<span data-ttu-id="9e6de-139">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="9e6de-139">Policy type</span></span>  |<span data-ttu-id="9e6de-140">Tempistiche</span><span class="sxs-lookup"><span data-stu-id="9e6de-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9e6de-141">Test</span><span class="sxs-lookup"><span data-stu-id="9e6de-141">Test</span></span>     |  <span data-ttu-id="9e6de-142">Audit</span><span class="sxs-lookup"><span data-stu-id="9e6de-142">Audit</span></span>       |  <span data-ttu-id="9e6de-143">Giorno 0</span><span class="sxs-lookup"><span data-stu-id="9e6de-143">Day 0</span></span>       |
|<span data-ttu-id="9e6de-144">First</span><span class="sxs-lookup"><span data-stu-id="9e6de-144">First</span></span>     | <span data-ttu-id="9e6de-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="9e6de-145">Enforced</span></span>        | <span data-ttu-id="9e6de-146">Giorno 1</span><span class="sxs-lookup"><span data-stu-id="9e6de-146">Day 1</span></span>        |
|<span data-ttu-id="9e6de-147">Veloce</span><span class="sxs-lookup"><span data-stu-id="9e6de-147">Fast</span></span>     | <span data-ttu-id="9e6de-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="9e6de-148">Enforced</span></span>        |  <span data-ttu-id="9e6de-149">Sospesa, implementazione su richiesta</span><span class="sxs-lookup"><span data-stu-id="9e6de-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="9e6de-150">Generale</span><span class="sxs-lookup"><span data-stu-id="9e6de-150">Broad</span></span>     | <span data-ttu-id="9e6de-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="9e6de-151">Enforced</span></span>        |  <span data-ttu-id="9e6de-152">Sospesa, implementazione su richiesta</span><span class="sxs-lookup"><span data-stu-id="9e6de-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="9e6de-153">È sempre possibile aprire un'altra richiesta di servizio per sospendere o eseguire il rollback di parte di questa distribuzione in qualsiasi momento durante l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="9e6de-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



