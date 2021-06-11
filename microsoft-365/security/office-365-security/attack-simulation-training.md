---
title: Simulare un attacco di phishing con Microsoft Defender per Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a simulare gli attacchi di phishing e formare gli utenti sulla prevenzione del phishing usando la formazione di simulazione degli attacchi in Microsoft Defender per Office 365.
ms.technology: mdo
ms.openlocfilehash: d82e7544e6795e4514cf1949645107c53fc69c61
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878365"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="a0c9c-103">Simulare un attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="a0c9c-103">Simulate a phishing attack</span></span>

<span data-ttu-id="a0c9c-104">**Si applica a** [Microsoft Defender per Office 365 piano 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a0c9c-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="a0c9c-105">La formazione sulla simulazione di attacchi in Microsoft Defender per Office 365 ti consente di eseguire simulazioni di attacchi informatici benigni nell'organizzazione per testare i criteri e le procedure di sicurezza, oltre a formare i dipendenti per aumentare la consapevolezza e ridurre la loro suscettibilità agli attacchi.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-105">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="a0c9c-106">In questo articolo viene illustrata la creazione di un attacco di phishing simulato tramite la formazione di simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-106">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="a0c9c-107">Per informazioni introduttive sulla formazione sulla simulazione di attacco, vedere Introduzione all'uso della formazione [sulla simulazione di attacco.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="a0c9c-107">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="a0c9c-108">Per avviare un attacco di phishing simulato, aprire il portale di Microsoft 365 Defender ( ), passare a Email & collaboration Attack simulation training e passare alla <https://security.microsoft.com/>  \>  **[scheda Simulations.](https://security.microsoft.com/attacksimulator?viewid=simulations)**</span><span class="sxs-lookup"><span data-stu-id="a0c9c-108">To launch a simulated phishing attack, open the Microsoft 365 Defender portal (<https://security.microsoft.com/>), go to **Email & collaboration** \> **Attack simulation training**, and switch to the **[Simulations](https://security.microsoft.com/attacksimulator?viewid=simulations)** tab.</span></span>

<span data-ttu-id="a0c9c-109">In **Simulazioni** selezionare **+ Avvia una simulazione.**</span><span class="sxs-lookup"><span data-stu-id="a0c9c-109">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Avviare un pulsante di simulazione nel portale Microsoft 365 Defender](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="a0c9c-111">In qualsiasi momento durante la creazione della simulazione, è possibile salvare e chiudere per continuare a configurare la simulazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-111">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="a0c9c-112">Selezione di una tecnica di social engineering</span><span class="sxs-lookup"><span data-stu-id="a0c9c-112">Selecting a social engineering technique</span></span>

<span data-ttu-id="a0c9c-113">Scegli tra 4 tecniche diverse, a cura del [framework MITRE ATT&CK®](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="a0c9c-113">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="a0c9c-114">Sono disponibili payload diversi per tecniche diverse:</span><span class="sxs-lookup"><span data-stu-id="a0c9c-114">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="a0c9c-115">**La raccolta delle** credenziali tenta di raccogliere le credenziali portando gli utenti in un sito Web dall'aspetto noto con caselle di input per inviare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-115">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="a0c9c-116">**L'allegato** malware aggiunge un allegato dannoso a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-116">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="a0c9c-117">Quando l'utente apre l'allegato, viene eseguito codice arbitrario che aiuterà l'utente malintenzionato a compromettere il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-117">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="a0c9c-118">**Il collegamento nell'allegato** è un tipo di ibrido di raccolta delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-118">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="a0c9c-119">Un utente malintenzionato inserisce un URL in un allegato di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-119">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="a0c9c-120">L'URL all'interno dell'allegato segue la stessa tecnica del raccolto delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-120">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="a0c9c-121">**Il collegamento al malware** eseguirà codice arbitrario da un file ospitato in un noto servizio di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-121">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="a0c9c-122">Il messaggio inviato all'utente conterrà un collegamento a questo file dannoso.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-122">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="a0c9c-123">Aprire il file e aiutare l'autore dell'attacco a compromettere il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-123">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="a0c9c-124">**L'URL drive-by** è il punto in cui l'URL dannoso nel messaggio porta l'utente a un sito Web dall'aspetto familiare che viene eseguito in modo invisibile all'utente e/o installa codice nel dispositivo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-124">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="a0c9c-125">Facendo clic **su Visualizza dettagli** all'interno della descrizione di ogni tecnica verranno visualizzate ulteriori informazioni e i passaggi di simulazione per la tecnica.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-125">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Passaggi di simulazione per la raccolta delle credenziali all'interno del training di simulazione degli attacchi nel portale Microsoft 365 Defender](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="a0c9c-127">Dopo aver selezionato la tecnica e aver fatto clic su **Avanti,** assegna alla simulazione un nome e facoltativamente una descrizione.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-127">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="a0c9c-128">Selezione di un payload</span><span class="sxs-lookup"><span data-stu-id="a0c9c-128">Selecting a payload</span></span>

<span data-ttu-id="a0c9c-129">Successivamente, dovrai selezionare un payload dal catalogo di payload preesiste.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-129">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="a0c9c-130">I payload hanno una serie di punti dati per aiutarti a scegliere:</span><span class="sxs-lookup"><span data-stu-id="a0c9c-130">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="a0c9c-131">**La frequenza** dei clic conta il numero di persone che hanno fatto clic su questo payload.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-131">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="a0c9c-132">**La percentuale di compromissione** stimata prevede la percentuale di persone compromesse da questo payload in base ai dati cronologici per il payload in Microsoft Defender per i Office 365 clienti.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-132">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="a0c9c-133">**Le simulazioni avviate** conteggia il numero di volte in cui questo payload è stato usato in altre simulazioni.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-133">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="a0c9c-134">**La complessità,** disponibile tramite **filtri,** viene calcolata in base al numero di indicatori all'interno del payload che consentono di descrizione degli obiettivi di un attacco.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-134">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="a0c9c-135">Più indicatori portano a una minore complessità.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-135">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="a0c9c-136">**Source**, disponibile tramite **filtri**, indica se il payload è stato creato nel tenant o fa parte del catalogo payload preesistevo di Microsoft (globale).</span><span class="sxs-lookup"><span data-stu-id="a0c9c-136">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Payload selezionato nel training della simulazione di attacco nel portale Microsoft 365 Defender](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="a0c9c-138">Seleziona un payload dall'elenco per visualizzare un'anteprima del payload con ulteriori informazioni su di esso.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-138">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="a0c9c-139">Se vuoi creare un payload personalizzato, leggi creare un payload per il [training della simulazione di attacco.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="a0c9c-139">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="a0c9c-140">Gruppi di destinatari</span><span class="sxs-lookup"><span data-stu-id="a0c9c-140">Audience targeting</span></span>

<span data-ttu-id="a0c9c-141">Ora è il momento di selezionare il gruppo di destinatari di questa simulazione.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-141">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="a0c9c-142">È possibile scegliere di **includere tutti gli utenti nell'organizzazione** o includere solo utenti e gruppi **specifici.**</span><span class="sxs-lookup"><span data-stu-id="a0c9c-142">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="a0c9c-143">Quando si sceglie di **includere solo utenti e gruppi** specifici, è possibile:</span><span class="sxs-lookup"><span data-stu-id="a0c9c-143">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="a0c9c-144">**Aggiungere utenti**, che consente di sfruttare la ricerca per il tenant, nonché funzionalità avanzate di ricerca e filtro, ad esempio la destinazione degli utenti che non sono stati presi di mira da una simulazione negli ultimi 3 mesi.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-144">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>

  ![Filtro utente nel training della simulazione di attacchi nel portale Microsoft 365 Defender](../../media/attack-sim-preview-user-targeting.png)

- <span data-ttu-id="a0c9c-146">**L'importazione da CSV** consente di importare un set predefinito di utenti per questa simulazione.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-146">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="a0c9c-147">Assegnazione di corsi di formazione</span><span class="sxs-lookup"><span data-stu-id="a0c9c-147">Assigning training</span></span>

<span data-ttu-id="a0c9c-148">Ti consigliamo di assegnare una formazione per ogni simulazione, poiché i dipendenti che passano attraverso la formazione sono meno soggetti ad attacchi simili.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-148">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="a0c9c-149">È possibile scegliere se assegnare la formazione oppure selezionare i corsi e i moduli di formazione manualmente.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-149">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="a0c9c-150">Selezionare la **data di scadenza della formazione** per assicurarsi che i dipendenti finiscano la formazione in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-150">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="a0c9c-151">Se si sceglie di selezionare i corsi e i moduli manualmente, sarà comunque possibile visualizzare il contenuto consigliato, nonché tutti i corsi e i moduli disponibili.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-151">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Aggiunta di formazione consigliata all'interno della formazione per la simulazione di attacchi nel portale Microsoft 365 Defender](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="a0c9c-153">Nei passaggi successivi dovrai  aggiungere corsi di formazione se hai scelto di selezionarlo manualmente e personalizzare la pagina di destinazione della formazione.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-153">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="a0c9c-154">Potrai visualizzare in anteprima la pagina di destinazione del training, nonché modificare l'intestazione e il corpo della pagina.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-154">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="a0c9c-155">Dettagli di avvio e revisione</span><span class="sxs-lookup"><span data-stu-id="a0c9c-155">Launch details and review</span></span>

<span data-ttu-id="a0c9c-156">Ora che tutto è configurato, puoi avviare questa simulazione immediatamente o pianificarla per una data successiva.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-156">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="a0c9c-157">Dovrai anche scegliere quando terminare questa simulazione.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-157">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="a0c9c-158">L'acquisizione dell'interazione con questa simulazione verrà interrotta dopo l'ora selezionata.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-158">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="a0c9c-159">**Abilitare il recapito del fuso orario** in grado di riconoscere l'area geografica per recapitare messaggi di attacco simulati ai dipendenti durante l'orario di lavoro in base all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-159">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="a0c9c-160">Al termine, fare clic su **Avanti** ed esaminare i dettagli della simulazione.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-160">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="a0c9c-161">Fare clic **su** Modifica in una delle parti per tornare indietro e modificare i dettagli che devono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="a0c9c-161">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="a0c9c-162">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="a0c9c-162">Once done, click **Submit**.</span></span>
