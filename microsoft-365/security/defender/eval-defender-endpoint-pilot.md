---
title: Pilotare Microsoft Defender for Endpoint, configurare un progetto pilota e testare le funzionalità di valutazione
description: Scopri come eseguire un progetto pilota per Microsoft Defender for Endpoint(MDE), inclusa la verifica del gruppo pilota e la prova delle funzionalità.
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
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458007"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a><span data-ttu-id="fb16a-103">Pilotare Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="fb16a-103">Pilot Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="fb16a-104">Questo articolo ti guiderà nel processo di esecuzione di un progetto pilota per Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="fb16a-104">This article will guide you in the process of running a pilot for Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="fb16a-105">Usa la procedura seguente per configurare il progetto pilota per Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="fb16a-105">Use the following steps to setup and configure the pilot for Microsoft Defender for Endpoint.</span></span> 

![Passaggi per l'aggiunta di Microsoft Defender per l'identità all'ambiente di valutazione di Defender](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- <span data-ttu-id="fb16a-107">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="fb16a-107">Step 1.</span></span> <span data-ttu-id="fb16a-108">Verificare il gruppo pilota</span><span class="sxs-lookup"><span data-stu-id="fb16a-108">Verify pilot group</span></span>
- <span data-ttu-id="fb16a-109">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="fb16a-109">Step 2.</span></span> <span data-ttu-id="fb16a-110">Funzionalità di prova</span><span class="sxs-lookup"><span data-stu-id="fb16a-110">Try out capabilities</span></span>

<span data-ttu-id="fb16a-111">Quando si esegue il test pilota di Microsoft Defender per Endpoint, è possibile scegliere di eseguire l'onboarding di alcuni dispositivi al servizio prima di eseguire l'onboarding dell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb16a-111">When you pilot Microsoft Defender for Endpoint, you may choose to onboard a few devices to the service before onboarding your entire organization.</span></span>  

<span data-ttu-id="fb16a-112">Puoi quindi provare le funzionalità disponibili, ad esempio l'esecuzione di simulazioni di attacco e vedere in che modo Defender for Endpoint eserciterà attività dannose e ti permetterà di eseguire una risposta efficiente.</span><span class="sxs-lookup"><span data-stu-id="fb16a-112">You can then try out capabilities that are available such as running attack simulations and seeing how Defender for Endpoint surfaces malicious activities and enables you to conduct an efficient response.</span></span> 

## <a name="step-1-verify-pilot-group"></a><span data-ttu-id="fb16a-113">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="fb16a-113">Step 1.</span></span> <span data-ttu-id="fb16a-114">Verificare il gruppo pilota</span><span class="sxs-lookup"><span data-stu-id="fb16a-114">Verify pilot group</span></span>
<span data-ttu-id="fb16a-115">Dopo aver completato i passaggi di onboarding descritti nella sezione [Abilita](eval-defender-endpoint-enable-eval.md) valutazione, dovresti vedere i dispositivi nell'elenco Inventario dispositivi circa dopo un'ora.</span><span class="sxs-lookup"><span data-stu-id="fb16a-115">After completing the onboarding steps outlined in the [Enable evaluation](eval-defender-endpoint-enable-eval.md) section, you should see the devices in the Device inventory list approximately after an hour.</span></span> 

<span data-ttu-id="fb16a-116">Quando vedi i dispositivi onboarded, puoi procedere con le funzionalità di prova.</span><span class="sxs-lookup"><span data-stu-id="fb16a-116">When you see your onboarded devices you can then proceed with trying out capabilities.</span></span> 

## <a name="step-2-try-out-capabilities"></a><span data-ttu-id="fb16a-117">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="fb16a-117">Step 2.</span></span> <span data-ttu-id="fb16a-118">Funzionalità di prova</span><span class="sxs-lookup"><span data-stu-id="fb16a-118">Try out capabilities</span></span>
<span data-ttu-id="fb16a-119">Dopo aver completato l'onboarding di alcuni dispositivi e verificato che stiano segnalando al servizio, acquisire familiarità con il prodotto provando le potenti funzionalità disponibili direttamente.</span><span class="sxs-lookup"><span data-stu-id="fb16a-119">Now that you've completed onboarding some devices and verified that they are reporting to the service, familiarize yourself with the product by trying out the powerful capabilities that are available right out of the box.</span></span>

<span data-ttu-id="fb16a-120">Durante il progetto pilota, è possibile iniziare facilmente a provare alcune delle funzionalità per visualizzare il prodotto in azione senza eseguire passaggi di configurazione complessi.</span><span class="sxs-lookup"><span data-stu-id="fb16a-120">During the pilot, you can easily get started with trying out some of the features to see the product in action without going through complex configuration steps.</span></span>

<span data-ttu-id="fb16a-121">Iniziamo con l'estrazione dei dashboard.</span><span class="sxs-lookup"><span data-stu-id="fb16a-121">Let's start by checking out the dashboards.</span></span>

### <a name="view-the-device-inventory"></a><span data-ttu-id="fb16a-122">Visualizzare l'inventario dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="fb16a-122">View the device inventory</span></span>
<span data-ttu-id="fb16a-123">L'inventario dei dispositivi è il punto in cui vedrai l'elenco di endpoint, dispositivi di rete e dispositivi IoT nella rete.</span><span class="sxs-lookup"><span data-stu-id="fb16a-123">The device inventory is where you'll see the list of endpoints, network devices, and IoT devices in your network.</span></span> <span data-ttu-id="fb16a-124">Non solo fornisce una visualizzazione dei dispositivi nella rete, ma fornisce anche informazioni approfondite su di essi, ad esempio dominio, livello di rischio, piattaforma del sistema operativo e altri dettagli per una facile identificazione dei dispositivi più a rischio.</span><span class="sxs-lookup"><span data-stu-id="fb16a-124">Not only does it provide you with a view of the devices in your network, but it also gives your in-depth information about them such as  domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="fb16a-125">Visualizzare il dashboard delle minacce gestione delle vulnerabilità sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb16a-125">View the Threat and vulnerability management dashboard</span></span> 
<span data-ttu-id="fb16a-126">Le minacce gestione delle vulnerabilità consentono di concentrarsi sui punti di debolezza che rappresentano il rischio più urgente e più alto per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb16a-126">Threat and vulnerability management helps you focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="fb16a-127">Dal dashboard, ottieni una visualizzazione di alto livello del punteggio di esposizione dell'organizzazione, microsoft secure score per i dispositivi, distribuzione dell'esposizione dei dispositivi, consigli di sicurezza principali, software più vulnerabile, attività di correzione principali e dati dei dispositivi più esposti.</span><span class="sxs-lookup"><span data-stu-id="fb16a-127">From the dashboard, get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span> 

### <a name="run-a-simulation"></a><span data-ttu-id="fb16a-128">Eseguire una simulazione</span><span class="sxs-lookup"><span data-stu-id="fb16a-128">Run a simulation</span></span>
<span data-ttu-id="fb16a-129">Microsoft Defender for Endpoint include scenari di attacco "Fai da [te"](https://securitycenter.windows.com/tutorials) che puoi eseguire nei dispositivi pilota.</span><span class="sxs-lookup"><span data-stu-id="fb16a-129">Microsoft Defender for Endpoint comes with ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials) that you can run on your pilot devices.</span></span>  <span data-ttu-id="fb16a-130">Ogni documento include i requisiti del sistema operativo e delle applicazioni, nonché istruzioni dettagliate specifiche per uno scenario di attacco.</span><span class="sxs-lookup"><span data-stu-id="fb16a-130">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span> <span data-ttu-id="fb16a-131">Questi script sono sicuri, documentati e facili da usare.</span><span class="sxs-lookup"><span data-stu-id="fb16a-131">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="fb16a-132">Questi scenari rifletteranno le funzionalità di Defender for Endpoint e illustrano l'esperienza di analisi.</span><span class="sxs-lookup"><span data-stu-id="fb16a-132">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

<span data-ttu-id="fb16a-133">Per eseguire una delle simulazioni fornite, è necessario almeno [un dispositivo onboarded.](../defender-endpoint/onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="fb16a-133">To run any of the provided simulations, you need at least [one onboarded device](../defender-endpoint/onboard-configure.md).</span></span>

1. <span data-ttu-id="fb16a-134">In   >  **Simulazioni guida & esercitazioni** selezionare quali degli scenari di attacco disponibili si desidera simulare:</span><span class="sxs-lookup"><span data-stu-id="fb16a-134">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="fb16a-135">**Scenario 1: la backdoor** del documento viene simulare la consegna di un documento di esca socialmente progettato.</span><span class="sxs-lookup"><span data-stu-id="fb16a-135">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="fb16a-136">Il documento avvia una backdoor appositamente predisposta che consente agli utenti malintenzionati di controllare.</span><span class="sxs-lookup"><span data-stu-id="fb16a-136">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="fb16a-137">**Scenario 2: script di PowerShell in** attacco senza file - Simula un attacco senza file che si basa su PowerShell, che mostra la riduzione della superficie di attacco e il rilevamento di dispositivi di apprendimento di attività di memoria dannose.</span><span class="sxs-lookup"><span data-stu-id="fb16a-137">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="fb16a-138">**Scenario 3: risposta** automatica agli eventi imprevisti : attiva un'indagine automatizzata, che cerca e correda automaticamente gli artefatti di violazione per ridimensionare la capacità di risposta agli incidenti.</span><span class="sxs-lookup"><span data-stu-id="fb16a-138">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="fb16a-139">Scaricare e leggere il documento della procedura dettagliata corrispondente fornito con lo scenario selezionato.</span><span class="sxs-lookup"><span data-stu-id="fb16a-139">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="fb16a-140">Scarica il file di simulazione o copia lo script di simulazione accedendo alla **Guida**  >  **Simulazioni & esercitazioni**.</span><span class="sxs-lookup"><span data-stu-id="fb16a-140">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="fb16a-141">Puoi scegliere di scaricare il file o lo script nel dispositivo di test, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fb16a-141">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="fb16a-142">Eseguire il file o lo script di simulazione nel dispositivo di test come indicato nel documento della procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="fb16a-142">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="fb16a-143">I file o gli script di simulazione simulano l'attività di attacco, ma sono in realtà benigni e non danneggiano o comprometteranno il dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="fb16a-143">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb16a-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fb16a-144">Next steps</span></span>
[<span data-ttu-id="fb16a-145">Valutare Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fb16a-145">Evaluate Microsoft Cloud App Security</span></span>](eval-defender-mcas-overview.md)

<span data-ttu-id="fb16a-146">Torna alla panoramica per [valutare Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fb16a-146">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="fb16a-147">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fb16a-147">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>