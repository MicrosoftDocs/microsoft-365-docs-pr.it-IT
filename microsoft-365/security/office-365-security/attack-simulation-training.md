---
title: Simulare un attacco di phishing con Microsoft Defender per Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a simulare gli attacchi di phishing e a formare gli utenti sulla prevenzione del phishing usando la formazione sulla simulazione di attacco in Microsoft Defender per Office 365.
ms.openlocfilehash: e7582b1f74266d988ecdf8f6dac49019699e2bc1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794257"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="98580-103">Simulare un attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="98580-103">Simulate a phishing attack</span></span>

<span data-ttu-id="98580-104">La formazione di simulazione di attacco in Microsoft Defender per Office 365 consente di eseguire simulazioni di cyberattack benigne nell'organizzazione per testare i criteri e le procedure di sicurezza, nonché formare i dipendenti per aumentare la loro consapevolezza e diminuirne la suscettibilità agli attacchi.</span><span class="sxs-lookup"><span data-stu-id="98580-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="98580-105">In questo articolo viene illustrata la creazione di un attacco di phishing simulato utilizzando la formazione di simulazione di attacco.</span><span class="sxs-lookup"><span data-stu-id="98580-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="98580-106">Per avviare un attacco di phishing simulato, aprire il [Centro sicurezza Microsoft 365](https://security.microsoft.com/), passare a **&** \> la formazione sulla **simulazione** di collaborazione e passare alla scheda [**simulazioni**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="98580-106">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="98580-107">In **simulazioni**, selezionare **+ Avvia una simulazione**.</span><span class="sxs-lookup"><span data-stu-id="98580-107">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Avviare un pulsante di simulazione in Microsoft 365 Security Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="98580-109">Durante la creazione di una simulazione, è possibile salvare e chiudere per continuare a configurare la simulazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="98580-109">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="98580-110">Selezione di una tecnica di social engineering</span><span class="sxs-lookup"><span data-stu-id="98580-110">Selecting a social engineering technique</span></span>

<span data-ttu-id="98580-111">Scegliere tra 4 diverse tecniche, a cura del [&CK® Framework](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="98580-111">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="98580-112">Sono disponibili diversi payload per tecniche diverse:</span><span class="sxs-lookup"><span data-stu-id="98580-112">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="98580-113">**Raccolta** di credenziali tentativi di raccolta delle credenziali tramite l'accesso degli utenti a un sito Web di ricerca noto con caselle di input per inviare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="98580-113">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="98580-114">L' **allegato di malware** aggiunge un allegato dannoso a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="98580-114">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="98580-115">Quando l'utente apre l'allegato, viene eseguito codice arbitrario che consentirà all'aggressore di compromettere il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98580-115">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="98580-116">**Link in Attachment** è un tipo di raccolta di credenziali ibrido.</span><span class="sxs-lookup"><span data-stu-id="98580-116">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="98580-117">Un utente malintenzionato inserisce un URL in un allegato di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="98580-117">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="98580-118">L'URL all'interno dell'allegato segue la stessa tecnica del raccolto di credenziali.</span><span class="sxs-lookup"><span data-stu-id="98580-118">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="98580-119">Il **collegamento a malware** eseguirà un codice arbitrario proveniente da un file ospitato in un servizio di condivisione file conosciuto.</span><span class="sxs-lookup"><span data-stu-id="98580-119">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="98580-120">Il messaggio inviato all'utente conterrà un collegamento a questo file dannoso.</span><span class="sxs-lookup"><span data-stu-id="98580-120">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="98580-121">Aprire il file e aiutare l'aggressore a compromettere il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98580-121">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="98580-122">Se si fa clic su **Visualizza dettagli** all'interno della descrizione di ogni tecnica, vengono visualizzate ulteriori informazioni e i passaggi di simulazione per la tecnica.</span><span class="sxs-lookup"><span data-stu-id="98580-122">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Passaggi di simulazione per la raccolta delle credenziali all'interno della formazione sulla simulazione di attacco in Microsoft 365 Security Center](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="98580-124">Dopo aver selezionato la tecnica e fare clic su **Avanti**, assegnare un nome alla simulazione e, facoltativamente, una descrizione.</span><span class="sxs-lookup"><span data-stu-id="98580-124">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="98580-125">Selezione di un payload</span><span class="sxs-lookup"><span data-stu-id="98580-125">Selecting a payload</span></span>

<span data-ttu-id="98580-126">Successivamente, è necessario selezionare un payload dal catalogo payload preesistente.</span><span class="sxs-lookup"><span data-stu-id="98580-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="98580-127">I payload dispongono di una serie di punti dati che consentono di scegliere:</span><span class="sxs-lookup"><span data-stu-id="98580-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="98580-128">**Fare clic su rate** count quante persone hanno fatto clic su questo payload.</span><span class="sxs-lookup"><span data-stu-id="98580-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="98580-129">Il **tasso di compromesso previsto** prevede la percentuale di persone che verranno compromesse da questo payload in base ai dati cronologici per il payload tra Microsoft Defender per i clienti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="98580-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="98580-130">**Simulazioni avviate** calcola il numero di volte in cui questo payload è stato utilizzato in altre simulazioni.</span><span class="sxs-lookup"><span data-stu-id="98580-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="98580-131">La **complessità**, disponibile tramite **filtri**, viene calcolata in base al numero di indicatori all'interno del payload a cui sono assegnati indizi su un attacco.</span><span class="sxs-lookup"><span data-stu-id="98580-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="98580-132">Altri indicatori conducono a una complessità inferiore.</span><span class="sxs-lookup"><span data-stu-id="98580-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="98580-133">L' **origine**, disponibile tramite **filtri**, indica se il payload è stato creato nel tenant o è parte del catalogo di payload preesistente di Microsoft (globale).</span><span class="sxs-lookup"><span data-stu-id="98580-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Payload selezionato all'interno della formazione sulla simulazione di attacco in Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="98580-135">Selezionare un payload dall'elenco per visualizzare un'anteprima del payload con ulteriori informazioni su di esso.</span><span class="sxs-lookup"><span data-stu-id="98580-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="98580-136">Se si desidera creare un payload personalizzato, leggere [creare un payload per la formazione di simulazione di attacco](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="98580-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="98580-137">Gruppi di destinatari</span><span class="sxs-lookup"><span data-stu-id="98580-137">Audience targeting</span></span>

<span data-ttu-id="98580-138">Ora è il momento di selezionare il gruppo di destinatari della simulazione.</span><span class="sxs-lookup"><span data-stu-id="98580-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="98580-139">È possibile scegliere di **includere tutti gli utenti nell'organizzazione** o **includere solo utenti e gruppi specifici**.</span><span class="sxs-lookup"><span data-stu-id="98580-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="98580-140">Quando si sceglie di **includere solo utenti e gruppi specifici,** è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98580-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="98580-141">**Aggiungere gli utenti**, che consentono di sfruttare la ricerca del tenant, nonché le funzionalità di ricerca e filtraggio avanzate, come il targeting degli utenti che non sono stati presi di mira da una simulazione negli ultimi 3 mesi.</span><span class="sxs-lookup"><span data-stu-id="98580-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="98580-142">![Filtro degli utenti in formazione sulla simulazione di attacco su Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="98580-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="98580-143">L' **importazione da CSV** consente di importare un insieme predefinito di utenti per questa simulazione.</span><span class="sxs-lookup"><span data-stu-id="98580-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="98580-144">Assegnazione della formazione</span><span class="sxs-lookup"><span data-stu-id="98580-144">Assigning training</span></span>

<span data-ttu-id="98580-145">Si consiglia di assegnare corsi di formazione per ogni simulazione, in quanto i dipendenti che passano la formazione sono meno suscettibili di attacchi simili.</span><span class="sxs-lookup"><span data-stu-id="98580-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="98580-146">È possibile scegliere di avere un training assegnato per l'utente oppure selezionare manualmente i corsi di formazione e i moduli.</span><span class="sxs-lookup"><span data-stu-id="98580-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="98580-147">Selezionare la **Data di scadenza della formazione** per assicurarsi che i dipendenti completino la propria formazione in modo tempestivo.</span><span class="sxs-lookup"><span data-stu-id="98580-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="98580-148">Se si sceglie di selezionare manualmente corsi e moduli, sarà comunque possibile visualizzare il contenuto consigliato, nonché tutti i corsi e i moduli disponibili.</span><span class="sxs-lookup"><span data-stu-id="98580-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Aggiunta di una formazione consigliata all'interno della formazione sulla simulazione di attacco in Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="98580-150">Nei passaggi successivi è necessario **aggiungere corsi di formazione** se si è scelto di selezionarlo personalmente e personalizzare la pagina di destinazione per l'addestramento.</span><span class="sxs-lookup"><span data-stu-id="98580-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="98580-151">È possibile visualizzare in anteprima la pagina di destinazione della formazione, nonché modificare l'intestazione e il corpo di esso.</span><span class="sxs-lookup"><span data-stu-id="98580-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="98580-152">Dettagli di avvio e Revisione</span><span class="sxs-lookup"><span data-stu-id="98580-152">Launch details and review</span></span>

<span data-ttu-id="98580-153">Ora che tutto è configurato, è possibile avviare questa simulazione immediatamente o pianificarla per una data successiva.</span><span class="sxs-lookup"><span data-stu-id="98580-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="98580-154">Sarà inoltre necessario scegliere quando terminare la simulazione.</span><span class="sxs-lookup"><span data-stu-id="98580-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="98580-155">L'interazione con questa simulazione verrà interrotta dopo l'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="98580-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="98580-156">**Abilitare il recapito di TimeZone** a livello di area per fornire messaggi di attacco simulati ai dipendenti durante le ore lavorative in base alla propria area geografica.</span><span class="sxs-lookup"><span data-stu-id="98580-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="98580-157">Al termine, fare clic su **Avanti** e rivedere i dettagli della simulazione.</span><span class="sxs-lookup"><span data-stu-id="98580-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="98580-158">Fare clic su **modifica** su una qualsiasi delle parti per tornare indietro e modificare eventuali dettagli che devono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="98580-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="98580-159">Una volta fatto, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="98580-159">Once done, click **Submit**.</span></span>
