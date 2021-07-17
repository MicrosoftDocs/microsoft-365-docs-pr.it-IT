---
title: Esperienza di Microsoft Defender for Endpoint (MDE) tramite attacchi simulati
description: Pilotare il Microsoft 365 Defender di prova o l'ambiente pilota.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458143"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="26c00-104">Esperienza di Microsoft Defender for Endpoint (MDE) tramite attacchi simulati</span><span class="sxs-lookup"><span data-stu-id="26c00-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="26c00-105">Informazioni sugli ultimi miglioramenti in Microsoft Defender for Endpoint: [Novità di Defender per Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="26c00-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="26c00-106">Defender for Endpoint ha dimostrato le funzionalità di ottica e rilevamento leader del settore nella recente valutazione MITRE.</span><span class="sxs-lookup"><span data-stu-id="26c00-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="26c00-107">Leggere: [Insights dalla valutazione basata su CK&MITRE ATT](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="26c00-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="26c00-108">Potresti voler provare Defender for Endpoint prima di eseguire l'onboardboard di più di alcuni dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="26c00-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="26c00-109">A tale scopo, è possibile eseguire simulazioni di attacco controllate su alcuni dispositivi di test.</span><span class="sxs-lookup"><span data-stu-id="26c00-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="26c00-110">Dopo aver eseguito gli attacchi simulati, puoi esaminare il modo in cui Defender for Endpoint mostra attività dannose ed esplorare il modo in cui consente una risposta efficiente.</span><span class="sxs-lookup"><span data-stu-id="26c00-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="26c00-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="26c00-111">Before you begin</span></span>

<span data-ttu-id="26c00-112">Per eseguire una delle simulazioni fornite, è necessario almeno [un dispositivo onboarded.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="26c00-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="26c00-113">Leggere il documento della procedura dettagliata fornito con ogni scenario di attacco.</span><span class="sxs-lookup"><span data-stu-id="26c00-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="26c00-114">Ogni documento include i requisiti del sistema operativo e delle applicazioni, nonché istruzioni dettagliate specifiche per uno scenario di attacco.</span><span class="sxs-lookup"><span data-stu-id="26c00-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="26c00-115">Eseguire una simulazione</span><span class="sxs-lookup"><span data-stu-id="26c00-115">Run a simulation</span></span>

1. <span data-ttu-id="26c00-116">In   >  **Simulazioni guida & esercitazioni** selezionare quali degli scenari di attacco disponibili si desidera simulare:</span><span class="sxs-lookup"><span data-stu-id="26c00-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="26c00-117">**Scenario 1: la backdoor** del documento viene simulare la consegna di un documento di esca socialmente progettato.</span><span class="sxs-lookup"><span data-stu-id="26c00-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="26c00-118">Il documento avvia una backdoor appositamente predisposta che consente agli utenti malintenzionati di controllare.</span><span class="sxs-lookup"><span data-stu-id="26c00-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="26c00-119">**Scenario 2: script di PowerShell in** attacco senza file - Simula un attacco senza file che si basa su PowerShell, che mostra la riduzione della superficie di attacco e il rilevamento di dispositivi di apprendimento di attività di memoria dannose.</span><span class="sxs-lookup"><span data-stu-id="26c00-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="26c00-120">**Scenario 3: risposta** automatica agli eventi imprevisti : attiva un'indagine automatizzata, che cerca e correda automaticamente gli artefatti di violazione per ridimensionare la capacità di risposta agli incidenti.</span><span class="sxs-lookup"><span data-stu-id="26c00-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="26c00-121">Scaricare e leggere il documento della procedura dettagliata corrispondente fornito con lo scenario selezionato.</span><span class="sxs-lookup"><span data-stu-id="26c00-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="26c00-122">Scarica il file di simulazione o copia lo script di simulazione accedendo alla **Guida**  >  **Simulazioni & esercitazioni**.</span><span class="sxs-lookup"><span data-stu-id="26c00-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="26c00-123">Puoi scegliere di scaricare il file o lo script nel dispositivo di test, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="26c00-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="26c00-124">Eseguire il file o lo script di simulazione nel dispositivo di test come indicato nel documento della procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="26c00-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="26c00-125">I file o gli script di simulazione simulano l'attività di attacco, ma sono in realtà benigni e non danneggiano o comprometteranno il dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="26c00-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="26c00-126">TESTO ARGOMENTO ALTERNATIVO</span><span class="sxs-lookup"><span data-stu-id="26c00-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="26c00-127">Simulare scenari di attacco</span><span class="sxs-lookup"><span data-stu-id="26c00-127">Simulate attack scenarios</span></span>

<span data-ttu-id="26c00-128">Usa i dispositivi di test per eseguire le tue simulazioni di attacco connettendoti a essi.</span><span class="sxs-lookup"><span data-stu-id="26c00-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="26c00-129">Puoi simulare scenari di attacco usando:</span><span class="sxs-lookup"><span data-stu-id="26c00-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="26c00-130">Scenari di attacco ["Fai da te"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="26c00-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="26c00-131">Simulatori di minacce</span><span class="sxs-lookup"><span data-stu-id="26c00-131">Threat simulators</span></span>

<span data-ttu-id="26c00-132">È inoltre possibile utilizzare [la ricerca avanzata per](advanced-hunting-overview.md) eseguire query sui dati e [sull'analisi](threat-analytics.md) delle minacce per visualizzare i report sulle minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="26c00-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="26c00-133">Scenari di attacco fai-da-te</span><span class="sxs-lookup"><span data-stu-id="26c00-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="26c00-134">Se stai cercando una simulazione predefinita, puoi usare i nostri scenari di attacco "Fai da [te".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="26c00-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="26c00-135">Questi script sono sicuri, documentati e facili da usare.</span><span class="sxs-lookup"><span data-stu-id="26c00-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="26c00-136">Questi scenari rifletteranno le funzionalità di Defender for Endpoint e illustrano l'esperienza di analisi.</span><span class="sxs-lookup"><span data-stu-id="26c00-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="26c00-137">La connessione ai dispositivi di test viene eseguita tramite RDP.</span><span class="sxs-lookup"><span data-stu-id="26c00-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="26c00-138">Verificare che le impostazioni del firewall consentano le connessioni RDP.</span><span class="sxs-lookup"><span data-stu-id="26c00-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="26c00-139">Connessione al dispositivo ed esegui una simulazione di attacco selezionando **Connessione**.</span><span class="sxs-lookup"><span data-stu-id="26c00-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![Immagine del pulsante di connessione per i dispositivi di test](images/test-machine-table.png)

2. <span data-ttu-id="26c00-141">Salvare il file RDP e avviarlo selezionando **Connessione**.</span><span class="sxs-lookup"><span data-stu-id="26c00-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Immagine della connessione desktop remoto](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="26c00-143">Se non si dispone di una copia della password salvata durante la configurazione iniziale, è possibile reimpostare la password selezionando Reimposta **password** dal menu: Immagine della password ![ di reimpostazione](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="26c00-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="26c00-144">Il dispositivo cambierà lo stato in "Esecuzione della reimpostazione della password", quindi ti verrà presentata la nuova password in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="26c00-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="26c00-145">Immetti la password visualizzata durante il passaggio di creazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26c00-145">Enter the password that was displayed during the device creation step.</span></span>

   ![Immagine della finestra in cui immettere le credenziali](images/enter-password.png)

4. <span data-ttu-id="26c00-147">Esegui simulazioni di attacco fai-da-te nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26c00-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="26c00-148">Scenari del simulatore di minacce</span><span class="sxs-lookup"><span data-stu-id="26c00-148">Threat simulator scenarios</span></span>

<span data-ttu-id="26c00-149">Se si è scelto di installare uno dei simulatori di minacce supportati durante la configurazione del lab, è possibile eseguire le simulazioni incorporate nei dispositivi del laboratorio di valutazione.</span><span class="sxs-lookup"><span data-stu-id="26c00-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="26c00-150">L'esecuzione di simulazioni di minacce con piattaforme di terze parti è un buon modo per valutare le funzionalità di Microsoft Defender for Endpoint entro i limiti di un ambiente lab.</span><span class="sxs-lookup"><span data-stu-id="26c00-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="26c00-151">Prima di poter eseguire simulazioni, verificare che siano soddisfatti i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="26c00-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="26c00-152">I dispositivi devono essere aggiunti al laboratorio di valutazione</span><span class="sxs-lookup"><span data-stu-id="26c00-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="26c00-153">I simulatori di minacce devono essere installati nel laboratorio di valutazione</span><span class="sxs-lookup"><span data-stu-id="26c00-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="26c00-154">Nel portale selezionare **Crea simulazione**.</span><span class="sxs-lookup"><span data-stu-id="26c00-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="26c00-155">Selezionare un simulatore di minacce.</span><span class="sxs-lookup"><span data-stu-id="26c00-155">Select a threat simulator.</span></span>

    ![Immagine della selezione del simulatore di minacce](images/select-simulator.png)

3. <span data-ttu-id="26c00-157">Scegliere una simulazione o esaminare la raccolta di simulazioni per esplorare le simulazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="26c00-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="26c00-158">Puoi accedere alla raccolta di simulazioni da:</span><span class="sxs-lookup"><span data-stu-id="26c00-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="26c00-159">Dashboard di valutazione principale nel riquadro **Panoramica simulazioni** o</span><span class="sxs-lookup"><span data-stu-id="26c00-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="26c00-160">Spostandosi dal riquadro di **spostamento** Valutazione ed esercitazioni  >  **Simulazione & esercitazioni**, quindi selezionare Catalogo **simulazioni**.</span><span class="sxs-lookup"><span data-stu-id="26c00-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="26c00-161">Seleziona i dispositivi in cui vuoi eseguire la simulazione.</span><span class="sxs-lookup"><span data-stu-id="26c00-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="26c00-162">Selezionare **Crea simulazione.**</span><span class="sxs-lookup"><span data-stu-id="26c00-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="26c00-163">Visualizzare lo stato di avanzamento di una simulazione selezionando la **scheda Simulazioni.** Visualizzare lo stato della simulazione, gli avvisi attivi e altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="26c00-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="26c00-164">![Immagine della scheda simulazioni](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="26c00-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="26c00-165">Dopo aver eseguito le simulazioni, ti invitiamo a esaminare l'indicatore di stato del lab ed esplorare Microsoft Defender for Endpoint che ha attivato un'indagine e **una correzione automatizzate.**</span><span class="sxs-lookup"><span data-stu-id="26c00-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="26c00-166">Controlla le prove raccolte e analizzate dalla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="26c00-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="26c00-167">Cercare le prove di attacco tramite la ricerca avanzata usando il linguaggio di query avanzato e la telemetria non elaborata e consultare alcune minacce a livello mondiale documentate in Threat analytics.</span><span class="sxs-lookup"><span data-stu-id="26c00-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
