---
title: Usare il controllo delle applicazioni
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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289460"
---
# <a name="work-with-app-control"></a><span data-ttu-id="620b5-103">Usare il controllo delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="620b5-103">Work with app control</span></span>

<span data-ttu-id="620b5-104">Dopo la distribuzione del controllo delle app nell'ambiente, sia l'utente che Microsoft Managed Desktop Operations hanno responsabilità continue.</span><span class="sxs-lookup"><span data-stu-id="620b5-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="620b5-105">Ad esempio, potresti voler aggiungere una nuova app nell'ambiente o aggiungere (o rimuovere) un firmatario attendibile.</span><span class="sxs-lookup"><span data-stu-id="620b5-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="620b5-106">Per migliorare la sicurezza, tutte le app devono essere firmate con codice prima di rilasciarle agli utenti.</span><span class="sxs-lookup"><span data-stu-id="620b5-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="620b5-107">I dettagli dell'autore di un'app includono informazioni sul firmatario.</span><span class="sxs-lookup"><span data-stu-id="620b5-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="620b5-108">Aggiungere una nuova app</span><span class="sxs-lookup"><span data-stu-id="620b5-108">Add a new app</span></span>

<span data-ttu-id="620b5-109">Per aggiungere una nuova app, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="620b5-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="620b5-110">Aggiungere l'app a [Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="620b5-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="620b5-111">Distribuisci l'app in qualsiasi dispositivo nell'anello Test.</span><span class="sxs-lookup"><span data-stu-id="620b5-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="620b5-112">Testa la tua app in base ai processi aziendali standard.</span><span class="sxs-lookup"><span data-stu-id="620b5-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="620b5-113">Controlla Visualizzatore eventi in **Registri applicazioni e servizi\Microsoft\Windows\AppLocker,** cercando eventuali eventi **8003** **o 8006.**</span><span class="sxs-lookup"><span data-stu-id="620b5-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="620b5-114">Questi eventi indicano che l'app verrebbe bloccata.</span><span class="sxs-lookup"><span data-stu-id="620b5-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="620b5-115">Per altre informazioni su tutti gli eventi di App Locker e sul relativo significato, vedi [Uso del Visualizzatore eventi con AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)</span><span class="sxs-lookup"><span data-stu-id="620b5-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="620b5-116">Se si trova uno di questi eventi, aprire una richiesta di firmatario con Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="620b5-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="620b5-117">Aggiungere (o rimuovere) un firmatario attendibile</span><span class="sxs-lookup"><span data-stu-id="620b5-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="620b5-118">Quando apri una richiesta di firmatario, devi prima fornire alcuni dettagli importanti sull'autore.</span><span class="sxs-lookup"><span data-stu-id="620b5-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="620b5-119">Eseguire quindi la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="620b5-119">Then follow these steps:</span></span>

1. <span data-ttu-id="620b5-120">[Raccogliere i dettagli dell'autore.](#gather-publisher-details)</span><span class="sxs-lookup"><span data-stu-id="620b5-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="620b5-121">Aprire un ticket con Microsoft Managed Desktop Operations per richiedere la regola firmatario e includere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="620b5-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="620b5-122">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="620b5-122">Application name</span></span> 
    - <span data-ttu-id="620b5-123">Versione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="620b5-123">Application version</span></span> 
    - <span data-ttu-id="620b5-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="620b5-124">Description</span></span> 
    - <span data-ttu-id="620b5-125">Tipo di modifica ("aggiungi" o "rimuovi")</span><span class="sxs-lookup"><span data-stu-id="620b5-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="620b5-126">Dettagli dell'autore (ad esempio: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="620b5-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="620b5-127">Per rimuovere l'attendibilità per un'app, segui gli stessi passaggi, ma imposta **Modifica tipo** per *rimuovere*.</span><span class="sxs-lookup"><span data-stu-id="620b5-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="620b5-128">Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:</span><span class="sxs-lookup"><span data-stu-id="620b5-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="620b5-129">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="620b5-129">Deployment group</span></span>  |<span data-ttu-id="620b5-130">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="620b5-130">Policy type</span></span>  |<span data-ttu-id="620b5-131">Tempistiche</span><span class="sxs-lookup"><span data-stu-id="620b5-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="620b5-132">Test</span><span class="sxs-lookup"><span data-stu-id="620b5-132">Test</span></span>     |  <span data-ttu-id="620b5-133">Audit</span><span class="sxs-lookup"><span data-stu-id="620b5-133">Audit</span></span>       |  <span data-ttu-id="620b5-134">Giorno 0</span><span class="sxs-lookup"><span data-stu-id="620b5-134">Day 0</span></span>       |
|<span data-ttu-id="620b5-135">First</span><span class="sxs-lookup"><span data-stu-id="620b5-135">First</span></span>     | <span data-ttu-id="620b5-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="620b5-136">Enforced</span></span>        | <span data-ttu-id="620b5-137">Giorno 1</span><span class="sxs-lookup"><span data-stu-id="620b5-137">Day 1</span></span>        |
|<span data-ttu-id="620b5-138">Veloce</span><span class="sxs-lookup"><span data-stu-id="620b5-138">Fast</span></span>     | <span data-ttu-id="620b5-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="620b5-139">Enforced</span></span>        |  <span data-ttu-id="620b5-140">Giorno 2</span><span class="sxs-lookup"><span data-stu-id="620b5-140">Day 2</span></span>       |
|<span data-ttu-id="620b5-141">Generale</span><span class="sxs-lookup"><span data-stu-id="620b5-141">Broad</span></span>     | <span data-ttu-id="620b5-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="620b5-142">Enforced</span></span>        |  <span data-ttu-id="620b5-143">Giorno 3</span><span class="sxs-lookup"><span data-stu-id="620b5-143">Day 3</span></span>       |


<span data-ttu-id="620b5-144">È possibile sospendere o eseguire il rollback della distribuzione in qualsiasi momento durante l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="620b5-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="620b5-145">A tale scopo, aprire un'altra richiesta di servizio con Operazioni.</span><span class="sxs-lookup"><span data-stu-id="620b5-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="620b5-146">Se si sospende il rilascio di una regola firmatario, è necessario eseguire il rollback o il completamento di tale regola prima di avviare un'altra implementazione.</span><span class="sxs-lookup"><span data-stu-id="620b5-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="620b5-147">Raccogliere i dettagli dell'autore</span><span class="sxs-lookup"><span data-stu-id="620b5-147">Gather publisher details</span></span>

<span data-ttu-id="620b5-148">Per accedere ai dati dell'autore per un'app, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="620b5-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="620b5-149">Trova un dispositivo Microsoft Managed Desktop nell'anello Test a cui è applicato un criterio modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="620b5-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="620b5-150">Tenta di installare l'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="620b5-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="620b5-151">Aprire il Visualizzatore eventi in tale dispositivo.</span><span class="sxs-lookup"><span data-stu-id="620b5-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="620b5-152">Nel Visualizzatore eventi passa a **Registri applicazioni e servizi\Microsoft\Windows** e quindi seleziona **AppLocker.**</span><span class="sxs-lookup"><span data-stu-id="620b5-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="620b5-153">Trovare qualsiasi **evento 8003** **o 8006** e quindi copiare le informazioni dall'evento:</span><span class="sxs-lookup"><span data-stu-id="620b5-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="620b5-154">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="620b5-154">Application name</span></span> 
    - <span data-ttu-id="620b5-155">Versione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="620b5-155">Application version</span></span> 
    - <span data-ttu-id="620b5-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="620b5-156">Description</span></span> 
    - <span data-ttu-id="620b5-157">Dettagli dell'autore (ad esempio: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="620b5-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
