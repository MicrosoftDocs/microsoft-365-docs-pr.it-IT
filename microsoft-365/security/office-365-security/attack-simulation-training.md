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
description: Gli amministratori possono imparare a simulare gli attacchi di phishing e formare gli utenti sulla prevenzione del phishing usando la formazione sulla simulazione degli attacchi in Microsoft Defender per Office 365.
ms.technology: mdo
ms.openlocfilehash: f22fe8633d8ffa8856f851369739a0f12364342b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929203"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="5eb80-103">Simulare un attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="5eb80-103">Simulate a phishing attack</span></span>

<span data-ttu-id="5eb80-104">La formazione sulla simulazione degli attacchi in Microsoft Defender per Office 365 consente di eseguire simulazioni di attacchi informatici innocue nell'organizzazione per testare i criteri e le procedure di sicurezza, oltre a formare i dipendenti ad aumentare la consapevolezza e a ridurre la loro sensibilità agli attacchi.</span><span class="sxs-lookup"><span data-stu-id="5eb80-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="5eb80-105">In questo articolo viene illustrata la creazione di un attacco di phishing simulato utilizzando il training di simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="5eb80-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="5eb80-106">Per informazioni introduttive sulla formazione sulla simulazione degli attacchi, vedere [Introduzione all'uso della formazione sulla simulazione degli attacchi.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="5eb80-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="5eb80-107">Per avviare un attacco di phishing simulato, aprire il Centro sicurezza [Microsoft 365,](https://security.microsoft.com/)passare & Formazione sulla simulazione degli attacchi **di** collaborazione e passare alla scheda \>  [**Simulazioni.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="5eb80-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="5eb80-108">In **Simulazioni** selezionare **+ Avvia una simulazione.**</span><span class="sxs-lookup"><span data-stu-id="5eb80-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Avviare un pulsante di simulazione nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="5eb80-110">In qualsiasi momento durante la creazione della simulazione, è possibile salvare e chiudere per continuare a configurare la simulazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="5eb80-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="5eb80-111">Selezione di una tecnica di social engineering</span><span class="sxs-lookup"><span data-stu-id="5eb80-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="5eb80-112">Scegli tra 4 tecniche diverse, a cura del [framework MITRE ATT&CK®](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="5eb80-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="5eb80-113">Sono disponibili payload diversi per tecniche diverse:</span><span class="sxs-lookup"><span data-stu-id="5eb80-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="5eb80-114">**Credential Harvest** tenta di raccogliere le credenziali portando gli utenti a un sito Web dall'aspetto noto con caselle di input per inviare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="5eb80-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="5eb80-115">**L'allegato** malware aggiunge un allegato dannoso a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5eb80-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="5eb80-116">Quando l'utente apre l'allegato, viene eseguito un codice arbitrario che aiuterà l'utente malintenzionato a compromettere il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="5eb80-117">**Il collegamento nell'allegato** è un tipo di soluzione ibrida di raccolta delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="5eb80-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="5eb80-118">Un utente malintenzionato inserisce un URL in un allegato di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5eb80-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="5eb80-119">L'URL all'interno dell'allegato segue la stessa tecnica di raccolta delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="5eb80-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="5eb80-120">**Il collegamento al malware** eseguirà codice arbitrario da un file ospitato in un servizio di condivisione file noto.</span><span class="sxs-lookup"><span data-stu-id="5eb80-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="5eb80-121">Il messaggio inviato all'utente conterrà un collegamento a questo file dannoso.</span><span class="sxs-lookup"><span data-stu-id="5eb80-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="5eb80-122">Aprire il file e aiutare l'utente malintenzionato a compromettere il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-122">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="5eb80-123">Facendo clic **su Visualizza dettagli** all'interno della descrizione di ogni tecnica verranno visualizzate ulteriori informazioni e i passaggi di simulazione per la tecnica.</span><span class="sxs-lookup"><span data-stu-id="5eb80-123">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Passaggi di simulazione per la raccolta delle credenziali all'interno della formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="5eb80-125">Dopo aver selezionato la tecnica e aver fatto clic su **Avanti,** assegna alla simulazione un nome e facoltativamente una descrizione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-125">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="5eb80-126">Selezione di un payload</span><span class="sxs-lookup"><span data-stu-id="5eb80-126">Selecting a payload</span></span>

<span data-ttu-id="5eb80-127">Successivamente, dovrai selezionare un payload dal catalogo di payload preesiste.</span><span class="sxs-lookup"><span data-stu-id="5eb80-127">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="5eb80-128">I payload hanno una serie di punti dati che ti aiutano a scegliere:</span><span class="sxs-lookup"><span data-stu-id="5eb80-128">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="5eb80-129">**La frequenza** di clic conta il numero di persone che hanno fatto clic su questo payload.</span><span class="sxs-lookup"><span data-stu-id="5eb80-129">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="5eb80-130">**Il tasso di compromissione** previsto prevede la percentuale di persone che verranno compromesse da questo payload in base ai dati cronologici per il payload tra i clienti di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="5eb80-130">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="5eb80-131">**Le simulazioni avviate** contano il numero di volte in cui questo payload è stato usato in altre simulazioni.</span><span class="sxs-lookup"><span data-stu-id="5eb80-131">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="5eb80-132">**La complessità,** disponibile tramite **i** filtri, viene calcolata in base al numero di indicatori all'interno del payload che indicano come destinazione un attacco.</span><span class="sxs-lookup"><span data-stu-id="5eb80-132">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="5eb80-133">Un numero maggiore di indicatori riduce la complessità.</span><span class="sxs-lookup"><span data-stu-id="5eb80-133">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="5eb80-134">**L'origine,** disponibile tramite i **filtri,** indica se il payload è stato creato nel tenant o fa parte del catalogo di payload preesistnte di Microsoft (globale).</span><span class="sxs-lookup"><span data-stu-id="5eb80-134">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Payload selezionato all'interno della formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="5eb80-136">Seleziona un payload dall'elenco per visualizzare un'anteprima del payload con informazioni aggiuntive su di esso.</span><span class="sxs-lookup"><span data-stu-id="5eb80-136">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="5eb80-137">Se si desidera creare un payload personalizzato, leggere creare un payload per il [training della simulazione di attacco.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="5eb80-137">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="5eb80-138">Gruppi di destinatari</span><span class="sxs-lookup"><span data-stu-id="5eb80-138">Audience targeting</span></span>

<span data-ttu-id="5eb80-139">Ora è il momento di selezionare il gruppo di destinatari di questa simulazione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-139">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="5eb80-140">È possibile scegliere di **includere tutti gli utenti dell'organizzazione** o solo utenti e gruppi **specifici.**</span><span class="sxs-lookup"><span data-stu-id="5eb80-140">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="5eb80-141">Quando si sceglie di **includere solo utenti e gruppi** specifici, è possibile:</span><span class="sxs-lookup"><span data-stu-id="5eb80-141">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="5eb80-142">**Aggiungere utenti**, che consente di sfruttare la ricerca per il tenant, nonché funzionalità avanzate di ricerca e filtro, come la destinazione degli utenti che non sono stati presi di mira da una simulazione negli ultimi 3 mesi.</span><span class="sxs-lookup"><span data-stu-id="5eb80-142">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="5eb80-143">![Filtro utenti nella formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="5eb80-143">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="5eb80-144">**L'importazione da CSV** consente di importare un set predefinito di utenti per questa simulazione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-144">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="5eb80-145">Assegnazione di corsi di formazione</span><span class="sxs-lookup"><span data-stu-id="5eb80-145">Assigning training</span></span>

<span data-ttu-id="5eb80-146">Ti consigliamo di assegnare una formazione per ogni simulazione, in quanto i dipendenti che passano attraverso la formazione sono meno esposti ad attacchi simili.</span><span class="sxs-lookup"><span data-stu-id="5eb80-146">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="5eb80-147">È possibile scegliere se assegnare la formazione oppure selezionare manualmente i corsi e i moduli di formazione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-147">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="5eb80-148">Selezionare la **data di scadenza della formazione** per assicurarsi che i dipendenti finisca la formazione in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="5eb80-148">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="5eb80-149">Se si sceglie di selezionare i corsi e i moduli manualmente, sarà comunque possibile visualizzare il contenuto consigliato, nonché tutti i corsi e i moduli disponibili.</span><span class="sxs-lookup"><span data-stu-id="5eb80-149">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Aggiunta di formazione consigliata all'interno della formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="5eb80-151">Nei passaggi successivi dovrai  aggiungere corsi di formazione se hai scelto di selezionarlo manualmente e personalizzare la pagina di destinazione della formazione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-151">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="5eb80-152">Potrai visualizzare in anteprima la pagina di destinazione del training, nonché modificare l'intestazione e il corpo della pagina.</span><span class="sxs-lookup"><span data-stu-id="5eb80-152">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="5eb80-153">Dettagli di avvio e revisione</span><span class="sxs-lookup"><span data-stu-id="5eb80-153">Launch details and review</span></span>

<span data-ttu-id="5eb80-154">Ora che tutto è configurato, puoi avviare questa simulazione immediatamente o pianificarla per una data successiva.</span><span class="sxs-lookup"><span data-stu-id="5eb80-154">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="5eb80-155">Dovrai anche scegliere quando terminare la simulazione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-155">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="5eb80-156">Interrompiamo l'acquisizione dell'interazione con questa simulazione oltre l'ora selezionata.</span><span class="sxs-lookup"><span data-stu-id="5eb80-156">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="5eb80-157">**Abilitare il recapito del fuso orario in** grado di riconoscere l'area geografica per recapitare messaggi di attacco simulati ai dipendenti durante l'orario di lavoro in base all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="5eb80-157">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="5eb80-158">Al termine, fare clic su **Avanti** ed esaminare i dettagli della simulazione.</span><span class="sxs-lookup"><span data-stu-id="5eb80-158">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="5eb80-159">Fare clic **su** Modifica in una delle parti per tornare indietro e modificare i dettagli che devono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="5eb80-159">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="5eb80-160">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="5eb80-160">Once done, click **Submit**.</span></span>
