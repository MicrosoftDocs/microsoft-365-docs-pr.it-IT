---
title: Introduzione al controllo delle applicazioni
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
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
# <a name="get-started-with-app-control"></a><span data-ttu-id="0fcf9-103">Introduzione al controllo delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="0fcf9-103">Get started with app control</span></span>

<span data-ttu-id="0fcf9-104">Prima di abilitare il controllo delle app nel proprio ambiente, controllare e comprendere in che [modo Microsoft Managed Desktop lo implementa](../service-description/app-control.md) e i ruoli e le responsabilità.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="0fcf9-105">Microsoft Managed Desktop semplifica il controllo delle app prendendo in considerazione gli aspetti più impegnativi per ottenere un criterio di base sicuro.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="0fcf9-106">Gli amministratori IT devono comunque testare le app nell'anello di testing e controllare i registri per eventuali avvisi o errori.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="0fcf9-107">Se un'applicazione ha bisogno di un'esenzione, è possibile archiviare una richiesta o potrebbe essere attiva l'operazione Microsoft Managed Desktop, a seconda di chi lo rileva per primo.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="0fcf9-108">Distribuzione iniziale delle app</span><span class="sxs-lookup"><span data-stu-id="0fcf9-108">Initial deployment of apps</span></span>

<span data-ttu-id="0fcf9-109">Quando si distribuisce per la prima volta le app, Microsoft Managed Desktop deve valutare il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="0fcf9-110">Gli esatti passaggi per l'abilitazione del controllo app dipendono dal fatto che i dispositivi siano già stati distribuiti nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="0fcf9-111">Dispositivi non ancora in uso</span><span class="sxs-lookup"><span data-stu-id="0fcf9-111">Devices not yet in use</span></span>

<span data-ttu-id="0fcf9-112">Se non si dispone ancora di alcun dispositivo in uso, aprire un ticket di servizio con Microsoft Managed Desktop Operations che richiede l'attivazione del controllo app.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="0fcf9-113">Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo la seguente pianificazione:</span><span class="sxs-lookup"><span data-stu-id="0fcf9-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="0fcf9-114">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="0fcf9-114">Deployment group</span></span>  |<span data-ttu-id="0fcf9-115">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="0fcf9-115">Policy type</span></span>  |<span data-ttu-id="0fcf9-116">Tempistiche</span><span class="sxs-lookup"><span data-stu-id="0fcf9-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0fcf9-117">Test</span><span class="sxs-lookup"><span data-stu-id="0fcf9-117">Test</span></span>     |  <span data-ttu-id="0fcf9-118">Audit</span><span class="sxs-lookup"><span data-stu-id="0fcf9-118">Audit</span></span>       |  <span data-ttu-id="0fcf9-119">Giorno 0</span><span class="sxs-lookup"><span data-stu-id="0fcf9-119">Day 0</span></span>       |
|<span data-ttu-id="0fcf9-120">Prima</span><span class="sxs-lookup"><span data-stu-id="0fcf9-120">First</span></span>     | <span data-ttu-id="0fcf9-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="0fcf9-121">Enforced</span></span>        | <span data-ttu-id="0fcf9-122">Giorno 1</span><span class="sxs-lookup"><span data-stu-id="0fcf9-122">Day 1</span></span>        |
|<span data-ttu-id="0fcf9-123">Veloce</span><span class="sxs-lookup"><span data-stu-id="0fcf9-123">Fast</span></span>     | <span data-ttu-id="0fcf9-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="0fcf9-124">Enforced</span></span>        |  <span data-ttu-id="0fcf9-125">Giorno 2</span><span class="sxs-lookup"><span data-stu-id="0fcf9-125">Day 2</span></span>       |
|<span data-ttu-id="0fcf9-126">Ampio</span><span class="sxs-lookup"><span data-stu-id="0fcf9-126">Broad</span></span>     | <span data-ttu-id="0fcf9-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="0fcf9-127">Enforced</span></span>        |  <span data-ttu-id="0fcf9-128">Giorno 3</span><span class="sxs-lookup"><span data-stu-id="0fcf9-128">Day 3</span></span>       |

<span data-ttu-id="0fcf9-129">È sempre possibile aprire un'altra richiesta di servizio per sospendere o ripristinare parte di questa distribuzione in qualsiasi momento durante l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="0fcf9-130">Dispositivi già in uso</span><span class="sxs-lookup"><span data-stu-id="0fcf9-130">Devices already in use</span></span>

<span data-ttu-id="0fcf9-131">Se è già in uso almeno un dispositivo Microsoft Managed Desktop, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="0fcf9-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="0fcf9-132">Aprire un ticket di servizio con Microsoft Managed Desktop Operations che richiede l'attivazione del controllo app.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="0fcf9-133">Le operazioni distribuiranno un [criterio di controllo](../service-description/app-control.md#audit-policy) su tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="0fcf9-134">[Testare le applicazioni](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) per verificare se sono state bloccate.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="0fcf9-135">Se un'applicazione verrebbe bloccata, aprire una [richiesta del firmatario](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="0fcf9-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="0fcf9-136">Dopo aver completato il testing (indipendentemente dai risultati), informare le operazioni, rilevando eventuali richieste del firmatario in sospeso.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="0fcf9-137">Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo la seguente pianificazione:</span><span class="sxs-lookup"><span data-stu-id="0fcf9-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="0fcf9-138">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="0fcf9-138">Deployment group</span></span>  |<span data-ttu-id="0fcf9-139">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="0fcf9-139">Policy type</span></span>  |<span data-ttu-id="0fcf9-140">Tempistiche</span><span class="sxs-lookup"><span data-stu-id="0fcf9-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0fcf9-141">Test</span><span class="sxs-lookup"><span data-stu-id="0fcf9-141">Test</span></span>     |  <span data-ttu-id="0fcf9-142">Audit</span><span class="sxs-lookup"><span data-stu-id="0fcf9-142">Audit</span></span>       |  <span data-ttu-id="0fcf9-143">Giorno 0</span><span class="sxs-lookup"><span data-stu-id="0fcf9-143">Day 0</span></span>       |
|<span data-ttu-id="0fcf9-144">Prima</span><span class="sxs-lookup"><span data-stu-id="0fcf9-144">First</span></span>     | <span data-ttu-id="0fcf9-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="0fcf9-145">Enforced</span></span>        | <span data-ttu-id="0fcf9-146">Giorno 1</span><span class="sxs-lookup"><span data-stu-id="0fcf9-146">Day 1</span></span>        |
|<span data-ttu-id="0fcf9-147">Veloce</span><span class="sxs-lookup"><span data-stu-id="0fcf9-147">Fast</span></span>     | <span data-ttu-id="0fcf9-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="0fcf9-148">Enforced</span></span>        |  <span data-ttu-id="0fcf9-149">Sospesa, implementazione su richiesta</span><span class="sxs-lookup"><span data-stu-id="0fcf9-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="0fcf9-150">Ampio</span><span class="sxs-lookup"><span data-stu-id="0fcf9-150">Broad</span></span>     | <span data-ttu-id="0fcf9-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="0fcf9-151">Enforced</span></span>        |  <span data-ttu-id="0fcf9-152">Sospesa, implementazione su richiesta</span><span class="sxs-lookup"><span data-stu-id="0fcf9-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="0fcf9-153">È sempre possibile aprire un'altra richiesta di servizio per sospendere o ripristinare parte di questa distribuzione in qualsiasi momento durante l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="0fcf9-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



