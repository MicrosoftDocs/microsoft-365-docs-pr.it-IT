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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917641"
---
# <a name="work-with-app-control"></a><span data-ttu-id="00dcb-103">Usare il controllo delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="00dcb-103">Work with app control</span></span>

<span data-ttu-id="00dcb-104">Dopo la distribuzione del controllo dell'app nell'ambiente, sia tu che Microsoft Managed Desktop le operazioni hanno responsabilità continue.</span><span class="sxs-lookup"><span data-stu-id="00dcb-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="00dcb-105">Ad esempio, potresti voler aggiungere una nuova app nell'ambiente o aggiungere (o rimuovere) un firmatario attendibile.</span><span class="sxs-lookup"><span data-stu-id="00dcb-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="00dcb-106">Per migliorare la sicurezza, tutte le app devono essere firmate con codice prima di rilasciarle agli utenti.</span><span class="sxs-lookup"><span data-stu-id="00dcb-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="00dcb-107">I dettagli dell'autore di un'app includono informazioni sul firmatario.</span><span class="sxs-lookup"><span data-stu-id="00dcb-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="00dcb-108">Aggiungere una nuova app</span><span class="sxs-lookup"><span data-stu-id="00dcb-108">Add a new app</span></span>

<span data-ttu-id="00dcb-109">Per aggiungere una nuova app, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="00dcb-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="00dcb-110">Aggiungi l'app a [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="00dcb-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="00dcb-111">Distribuisci l'app in qualsiasi dispositivo nell'anello Test.</span><span class="sxs-lookup"><span data-stu-id="00dcb-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="00dcb-112">Testa la tua app in base ai processi aziendali standard.</span><span class="sxs-lookup"><span data-stu-id="00dcb-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="00dcb-113">Controlla Visualizzatore eventi in Registri applicazioni e **servizi\Microsoft\Windows\AppLocker,** cercando eventuali eventi **8003** o **8006.**</span><span class="sxs-lookup"><span data-stu-id="00dcb-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="00dcb-114">Questi eventi indicano che l'app verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="00dcb-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="00dcb-115">Per altre informazioni su tutti gli eventi di App Locker e sui relativi significati, vedi [Uso del Visualizzatore eventi con AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)</span><span class="sxs-lookup"><span data-stu-id="00dcb-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="00dcb-116">Se si trova uno di questi eventi, aprire una richiesta di firmatario con Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="00dcb-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="00dcb-117">Aggiungere (o rimuovere) un firmatario attendibile</span><span class="sxs-lookup"><span data-stu-id="00dcb-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="00dcb-118">Quando si apre una richiesta di firmatario, è necessario fornire prima alcuni dettagli importanti sull'autore.</span><span class="sxs-lookup"><span data-stu-id="00dcb-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="00dcb-119">Eseguire quindi la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="00dcb-119">Then follow these steps:</span></span>

1. <span data-ttu-id="00dcb-120">[Raccogliere i dettagli dell'autore](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="00dcb-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="00dcb-121">Aprire un ticket con Microsoft Managed Desktop Operations per richiedere la regola del firmatario e includere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="00dcb-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="00dcb-122">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="00dcb-122">Application name</span></span> 
    - <span data-ttu-id="00dcb-123">Versione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="00dcb-123">Application version</span></span> 
    - <span data-ttu-id="00dcb-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00dcb-124">Description</span></span> 
    - <span data-ttu-id="00dcb-125">Tipo di modifica ("aggiungi" o "rimuovi")</span><span class="sxs-lookup"><span data-stu-id="00dcb-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="00dcb-126">Publisher dettagli (ad esempio: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="00dcb-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="00dcb-127">Per rimuovere l'attendibilità per un'app, segui gli stessi passaggi, ma imposta **Cambia tipo** su *rimuovi*.</span><span class="sxs-lookup"><span data-stu-id="00dcb-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="00dcb-128">Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:</span><span class="sxs-lookup"><span data-stu-id="00dcb-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="00dcb-129">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="00dcb-129">Deployment group</span></span>  |<span data-ttu-id="00dcb-130">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="00dcb-130">Policy type</span></span>  |<span data-ttu-id="00dcb-131">Tempistiche</span><span class="sxs-lookup"><span data-stu-id="00dcb-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="00dcb-132">Test</span><span class="sxs-lookup"><span data-stu-id="00dcb-132">Test</span></span>     |  <span data-ttu-id="00dcb-133">Audit</span><span class="sxs-lookup"><span data-stu-id="00dcb-133">Audit</span></span>       |  <span data-ttu-id="00dcb-134">Giorno 0</span><span class="sxs-lookup"><span data-stu-id="00dcb-134">Day 0</span></span>       |
|<span data-ttu-id="00dcb-135">First</span><span class="sxs-lookup"><span data-stu-id="00dcb-135">First</span></span>     | <span data-ttu-id="00dcb-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="00dcb-136">Enforced</span></span>        | <span data-ttu-id="00dcb-137">Giorno 1</span><span class="sxs-lookup"><span data-stu-id="00dcb-137">Day 1</span></span>        |
|<span data-ttu-id="00dcb-138">Veloce</span><span class="sxs-lookup"><span data-stu-id="00dcb-138">Fast</span></span>     | <span data-ttu-id="00dcb-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="00dcb-139">Enforced</span></span>        |  <span data-ttu-id="00dcb-140">Giorno 2</span><span class="sxs-lookup"><span data-stu-id="00dcb-140">Day 2</span></span>       |
|<span data-ttu-id="00dcb-141">Broad</span><span class="sxs-lookup"><span data-stu-id="00dcb-141">Broad</span></span>     | <span data-ttu-id="00dcb-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="00dcb-142">Enforced</span></span>        |  <span data-ttu-id="00dcb-143">Giorno 3</span><span class="sxs-lookup"><span data-stu-id="00dcb-143">Day 3</span></span>       |


<span data-ttu-id="00dcb-144">È possibile sospendere o eseguire il rollback della distribuzione in qualsiasi momento durante l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="00dcb-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="00dcb-145">A tale scopo, aprire un'altra richiesta di servizio con Operations.</span><span class="sxs-lookup"><span data-stu-id="00dcb-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="00dcb-146">Se si sospende il rilascio di una regola del firmatario, è necessario eseguire il rollback o il completamento della regola prima di avviare un'altra implementazione.</span><span class="sxs-lookup"><span data-stu-id="00dcb-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="00dcb-147">Raccogliere i dettagli dell'autore</span><span class="sxs-lookup"><span data-stu-id="00dcb-147">Gather publisher details</span></span>

<span data-ttu-id="00dcb-148">Per accedere ai dati dell'autore per un'app, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="00dcb-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="00dcb-149">Trova un dispositivo Microsoft Managed Desktop nell'anello test a cui è applicato un criterio modalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="00dcb-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="00dcb-150">Prova a installare l'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="00dcb-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="00dcb-151">Apri visualizzatore eventi in tale dispositivo.</span><span class="sxs-lookup"><span data-stu-id="00dcb-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="00dcb-152">Nel Visualizzatore eventi passare a Registri applicazioni e **servizi\Microsoft\Windows** e quindi selezionare **AppLocker.**</span><span class="sxs-lookup"><span data-stu-id="00dcb-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="00dcb-153">Trova qualsiasi **evento 8003** o **8006** e quindi copia le informazioni dall'evento:</span><span class="sxs-lookup"><span data-stu-id="00dcb-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="00dcb-154">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="00dcb-154">Application name</span></span> 
    - <span data-ttu-id="00dcb-155">Versione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="00dcb-155">Application version</span></span> 
    - <span data-ttu-id="00dcb-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00dcb-156">Description</span></span> 
    - <span data-ttu-id="00dcb-157">Publisher dettagli (ad esempio: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="00dcb-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>