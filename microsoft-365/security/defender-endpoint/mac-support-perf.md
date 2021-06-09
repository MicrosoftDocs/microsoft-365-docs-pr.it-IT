---
title: Risolvere i problemi di prestazioni per Microsoft Defender per Endpoint in macOS
description: Risolvere i problemi di prestazioni in Microsoft Defender per Endpoint in macOS.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, prestazioni
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a4ebb360bc606845bfd3f80f31082c836b896477
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694258"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="c7dd4-104">Risolvere i problemi di prestazioni per Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="c7dd4-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c7dd4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c7dd4-105">**Applies to:**</span></span>

- [<span data-ttu-id="c7dd4-106">Microsoft Defender per endpoint su macOS</span><span class="sxs-lookup"><span data-stu-id="c7dd4-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="c7dd4-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c7dd4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c7dd4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7dd4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c7dd4-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c7dd4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c7dd4-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c7dd4-111">Questo argomento fornisce alcuni passaggi generali che possono essere usati per limitare i problemi di prestazioni correlati a Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="c7dd4-112">La protezione in tempo reale (RTP) è una funzionalità di Microsoft Defender for Endpoint su macOS che monitora e protegge continuamente il dispositivo dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint on macOS that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="c7dd4-113">È costituito dal monitoraggio di file e processi e da altre euristiche.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="c7dd4-114">A seconda delle applicazioni in esecuzione e delle caratteristiche del dispositivo, è possibile che si verifichino prestazioni non ottimali quando si esegue Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="c7dd4-115">In particolare, le applicazioni o i processi di sistema che accedono a molte risorse in un breve periodo di tempo possono causare problemi di prestazioni in Microsoft Defender per Endpoint in macOS.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="c7dd4-116">I passaggi seguenti possono essere utilizzati per risolvere e attenuare questi problemi:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="c7dd4-117">Disabilitare la protezione in tempo reale utilizzando uno dei metodi seguenti e osservare se le prestazioni migliorano.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="c7dd4-118">Questo approccio consente di stabilire se Microsoft Defender for Endpoint in macOS contribuisce ai problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-118">This approach helps narrow down whether Microsoft Defender for Endpoint on macOS is contributing to the performance issues.</span></span>

      <span data-ttu-id="c7dd4-119">Se il dispositivo non è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata utilizzando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="c7dd4-120">Dall'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-120">From the user interface.</span></span> <span data-ttu-id="c7dd4-121">Apri Microsoft Defender per Endpoint in macOS e passa a **Gestisci impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="c7dd4-121">Open Microsoft Defender for Endpoint on macOS and navigate to **Manage settings**.</span></span>

      ![Schermata Gestisci protezione in tempo reale](images/mdatp-36-rtp.png)

    - <span data-ttu-id="c7dd4-123">Dal terminale.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-123">From the Terminal.</span></span> <span data-ttu-id="c7dd4-124">Per motivi di sicurezza, questa operazione richiede l'elevazione.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="c7dd4-125">Se il dispositivo è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata dall'amministratore usando le istruzioni in Impostare le preferenze per [Microsoft Defender per Endpoint su macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="c7dd4-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>
      
      <span data-ttu-id="c7dd4-126">Se il problema di prestazioni persiste quando la protezione in tempo reale è disattivata, l'origine del problema potrebbe essere il componente di rilevamento e risposta degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="c7dd4-127">In questo caso, contattare il supporto tecnico per ulteriori istruzioni e misure di prevenzione.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="c7dd4-128">Apri il Finder e passa a **Utilità**  >  **applicazioni.**</span><span class="sxs-lookup"><span data-stu-id="c7dd4-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="c7dd4-129">Aprire **Monitoraggio attività** e analizzare le applicazioni che utilizzano le risorse del sistema.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="c7dd4-130">Esempi tipici sono gli aggiornamenti software e i compilatori.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="c7dd4-131">Per trovare le applicazioni che attivano il maggior numero di analisi, puoi usare le statistiche in tempo reale raccolte da Defender per Endpoint su Mac.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="c7dd4-132">Questa funzionalità è disponibile nella versione 100.90.70 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="c7dd4-133">Questa funzionalità è abilitata per impostazione predefinita nei **canali Dogfood** **e InsiderFast.**</span><span class="sxs-lookup"><span data-stu-id="c7dd4-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="c7dd4-134">Se si utilizza un canale di aggiornamento diverso, questa funzionalità può essere abilitata dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="c7dd4-135">Questa funzionalità richiede l'attivazione della protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="c7dd4-136">Per verificare lo stato della protezione in tempo reale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="c7dd4-137">Verificare che la **voce real_time_protection_enabled** sia true.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="c7dd4-138">In caso contrario, eseguire il comando seguente per abilitarlo:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="c7dd4-139">Per raccogliere le statistiche correnti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > <span data-ttu-id="c7dd4-140">**L'uso di --output json** (nota il trattino doppio) garantisce che il formato di output sia pronto per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="c7dd4-141">L'output di questo comando mostrerà tutti i processi e l'attività di analisi associata.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="c7dd4-142">Nel sistema Mac scarica il parser python di esempio high_cpu_parser.py usando il comando:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="c7dd4-143">L'output di questo comando deve essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-143">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. <span data-ttu-id="c7dd4-144">Digitare quindi i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="c7dd4-145">L'output di cui sopra è un elenco dei principali collaboratori ai problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="c7dd4-146">La prima colonna è l'identificatore di processo (PID), la seconda è il nome del processo e l'ultima colonna è il numero di file analizzati, ordinati in base all'impatto.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="c7dd4-147">Ad esempio, l'output del comando sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c7dd4-147">For example, the output of the command will be something like the below:</span></span>

      ```output
        ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
        27432 None 76703
        73467 actool     1249
        73914 xcodebuild 1081
        73873 bash 1050
        27475 None 836
        1    launchd    407
        73468 ibtool     344
        549  telemetryd_v1   325
        4764 None 228
        125  CrashPlanService 164
      ```

      <span data-ttu-id="c7dd4-148">Per migliorare le prestazioni di Defender per Endpoint su Mac, individua quello con il numero più alto nella riga Totale file analizzati e aggiungi un'esclusione.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-148">To improve the performance of Defender for Endpoint on Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="c7dd4-149">Per altre informazioni, vedi [Configurare e convalidare le esclusioni per Defender per Endpoint su Linux.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="c7dd4-149">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="c7dd4-150">L'applicazione archivia le statistiche in memoria e tiene traccia dell'attività dei file solo dopo l'avvio e l'attivazione della protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="c7dd4-151">I processi avviati prima o durante i periodi in cui la protezione in tempo reale era disattivata non vengono conteggiati.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="c7dd4-152">Inoltre, vengono conteggiati solo gli eventi che hanno attivato le analisi.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="c7dd4-153">Configurare Microsoft Defender per Endpoint in macOS con esclusioni per i processi o le posizioni del disco che contribuiscono ai problemi di prestazioni e ri-abilitare la protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-153">Configure Microsoft Defender for Endpoint on macOS with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="c7dd4-154">Per informazioni dettagliate, vedi Configurare e convalidare le esclusioni per [Microsoft Defender per Endpoint su macOS.](mac-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="c7dd4-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint on macOS](mac-exclusions.md) for details.</span></span>
