---
title: Usare il controllo delle applicazioni
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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289460"
---
# <a name="work-with-app-control"></a><span data-ttu-id="339b9-103">Usare il controllo delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="339b9-103">Work with app control</span></span>

<span data-ttu-id="339b9-104">Una volta che il controllo app è stato distribuito nell'ambiente in uso, sia le operazioni di Microsoft Managed Desktop che quelle gestite hanno responsabilità continuative.</span><span class="sxs-lookup"><span data-stu-id="339b9-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="339b9-105">Ad esempio, è possibile aggiungere una nuova app nell'ambiente o aggiungere (o rimuovere) un firmatario attendibile.</span><span class="sxs-lookup"><span data-stu-id="339b9-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="339b9-106">Per migliorare la sicurezza, tutte le app devono essere firmate con codice prima di rilasciarle agli utenti.</span><span class="sxs-lookup"><span data-stu-id="339b9-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="339b9-107">I dettagli dell'editore di un'app includono informazioni sul firmatario.</span><span class="sxs-lookup"><span data-stu-id="339b9-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="339b9-108">Aggiungere una nuova app</span><span class="sxs-lookup"><span data-stu-id="339b9-108">Add a new app</span></span>

<span data-ttu-id="339b9-109">Per aggiungere una nuova app, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="339b9-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="339b9-110">Aggiungere l'app a [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="339b9-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="339b9-111">Distribuire l'app a qualsiasi dispositivo nell'anello di test.</span><span class="sxs-lookup"><span data-stu-id="339b9-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="339b9-112">Testare l'app in base ai processi aziendali standard.</span><span class="sxs-lookup"><span data-stu-id="339b9-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="339b9-113">Controllare il Visualizzatore eventi in **Logs\Microsoft\Windows\AppLocker di applicazioni e servizi**, cercando qualsiasi evento **8003** o **8006** .</span><span class="sxs-lookup"><span data-stu-id="339b9-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="339b9-114">Questi eventi indicano che l'applicazione verrebbe bloccata.</span><span class="sxs-lookup"><span data-stu-id="339b9-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="339b9-115">Per ulteriori informazioni su tutti gli eventi degli armadietti delle app e sui relativi significati, vedere [using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="339b9-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="339b9-116">Se si trova uno qualsiasi di questi eventi, aprire una richiesta di firmatario con le operazioni di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="339b9-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="339b9-117">Aggiungere (o rimuovere) un firmatario attendibile</span><span class="sxs-lookup"><span data-stu-id="339b9-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="339b9-118">Quando si apre una richiesta del firmatario, è necessario prima fornire alcuni dettagli importanti dell'editore.</span><span class="sxs-lookup"><span data-stu-id="339b9-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="339b9-119">Eseguire quindi la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="339b9-119">Then follow these steps:</span></span>

1. <span data-ttu-id="339b9-120">[Raccogliere i dettagli dell'editore](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="339b9-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="339b9-121">Aprire un ticket con le operazioni di Microsoft Managed Desktop per richiedere la regola del firmatario e includere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="339b9-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="339b9-122">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="339b9-122">Application name</span></span> 
    - <span data-ttu-id="339b9-123">Versione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="339b9-123">Application version</span></span> 
    - <span data-ttu-id="339b9-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="339b9-124">Description</span></span> 
    - <span data-ttu-id="339b9-125">Tipo di modifica ("Aggiungi" o "Rimuovi")</span><span class="sxs-lookup"><span data-stu-id="339b9-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="339b9-126">Dettagli editore (ad esempio: "O = <publisher name> , L = <location> , S = stato, C = paese")</span><span class="sxs-lookup"><span data-stu-id="339b9-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="339b9-127">Per rimuovere la relazione di trust per un'app, eseguire gli stessi passaggi, ma impostare **tipo di modifica** da *rimuovere*.</span><span class="sxs-lookup"><span data-stu-id="339b9-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="339b9-128">Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo la seguente pianificazione:</span><span class="sxs-lookup"><span data-stu-id="339b9-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="339b9-129">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="339b9-129">Deployment group</span></span>  |<span data-ttu-id="339b9-130">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="339b9-130">Policy type</span></span>  |<span data-ttu-id="339b9-131">Tempistiche</span><span class="sxs-lookup"><span data-stu-id="339b9-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="339b9-132">Test</span><span class="sxs-lookup"><span data-stu-id="339b9-132">Test</span></span>     |  <span data-ttu-id="339b9-133">Audit</span><span class="sxs-lookup"><span data-stu-id="339b9-133">Audit</span></span>       |  <span data-ttu-id="339b9-134">Giorno 0</span><span class="sxs-lookup"><span data-stu-id="339b9-134">Day 0</span></span>       |
|<span data-ttu-id="339b9-135">Prima</span><span class="sxs-lookup"><span data-stu-id="339b9-135">First</span></span>     | <span data-ttu-id="339b9-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="339b9-136">Enforced</span></span>        | <span data-ttu-id="339b9-137">Giorno 1</span><span class="sxs-lookup"><span data-stu-id="339b9-137">Day 1</span></span>        |
|<span data-ttu-id="339b9-138">Veloce</span><span class="sxs-lookup"><span data-stu-id="339b9-138">Fast</span></span>     | <span data-ttu-id="339b9-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="339b9-139">Enforced</span></span>        |  <span data-ttu-id="339b9-140">Giorno 2</span><span class="sxs-lookup"><span data-stu-id="339b9-140">Day 2</span></span>       |
|<span data-ttu-id="339b9-141">Ampio</span><span class="sxs-lookup"><span data-stu-id="339b9-141">Broad</span></span>     | <span data-ttu-id="339b9-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="339b9-142">Enforced</span></span>        |  <span data-ttu-id="339b9-143">Giorno 3</span><span class="sxs-lookup"><span data-stu-id="339b9-143">Day 3</span></span>       |


<span data-ttu-id="339b9-144">È possibile sospendere o eseguire il rollback della distribuzione in qualsiasi momento durante l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="339b9-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="339b9-145">A tale scopo, aprire un'altra richiesta di servizio con le operazioni.</span><span class="sxs-lookup"><span data-stu-id="339b9-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="339b9-146">Se si sospende la liberazione di una regola del firmatario, è necessario eseguire il rollback o il completamento di una regola prima che sia possibile avviare un'altra implementazione.</span><span class="sxs-lookup"><span data-stu-id="339b9-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="339b9-147">Raccogliere i dettagli dell'editore</span><span class="sxs-lookup"><span data-stu-id="339b9-147">Gather publisher details</span></span>

<span data-ttu-id="339b9-148">Per accedere ai dati del server di pubblicazione per un'app, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="339b9-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="339b9-149">Individuare un dispositivo Microsoft Managed Desktop nell'anello di testing in cui è stato applicato un criterio modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="339b9-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="339b9-150">Tentativo di installazione dell'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="339b9-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="339b9-151">Aprire il Visualizzatore eventi su quel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="339b9-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="339b9-152">In Visualizzatore eventi passare a **Logs\Microsoft\Windows applicazione e servizi**, quindi selezionare **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="339b9-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="339b9-153">Individuare qualsiasi evento **8003** o **8006** e quindi copiare le informazioni dall'evento:</span><span class="sxs-lookup"><span data-stu-id="339b9-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="339b9-154">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="339b9-154">Application name</span></span> 
    - <span data-ttu-id="339b9-155">Versione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="339b9-155">Application version</span></span> 
    - <span data-ttu-id="339b9-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="339b9-156">Description</span></span> 
    - <span data-ttu-id="339b9-157">Dettagli editore (ad esempio: "O = <publisher name> , L = <location> , S = stato, C = paese")</span><span class="sxs-lookup"><span data-stu-id="339b9-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
