---
title: Risolvere i problemi di prestazioni per Microsoft Defender for Endpoint per Linux
description: Risolvere i problemi di prestazioni in Microsoft Defender Endpoint per Linux.
keywords: microsoft, defender, atp, linux, prestazioni
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cb43fd383606ab26ba2688ad5704bb7653e82a7f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860340"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="8c238-104">Risolvere i problemi di prestazioni per Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="8c238-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c238-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8c238-105">**Applies to:**</span></span>
- [<span data-ttu-id="8c238-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8c238-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c238-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c238-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="8c238-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8c238-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8c238-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8c238-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="8c238-110">Questo articolo fornisce alcuni passaggi generali che possono essere usati per limitare i problemi di prestazioni correlati a Defender per Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="8c238-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="8c238-111">La protezione in tempo reale (RTP) è una funzionalità di Defender for Endpoint per Linux che monitora e protegge continuamente il dispositivo dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="8c238-111">Real-time protection (RTP) is a feature of Defender for Endpoint for Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="8c238-112">È costituito dal monitoraggio di file e processi e da altre euristiche.</span><span class="sxs-lookup"><span data-stu-id="8c238-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="8c238-113">A seconda delle applicazioni in esecuzione e delle caratteristiche del dispositivo, è possibile che si verifichino prestazioni non ottimali quando si esegue Defender per Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="8c238-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint for Linux.</span></span> <span data-ttu-id="8c238-114">In particolare, le applicazioni o i processi di sistema che accedono a molte risorse in un breve periodo di tempo possono causare problemi di prestazioni in Defender for Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="8c238-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="8c238-115">Prima di iniziare, assicurati che altri prodotti di **sicurezza non siano attualmente in esecuzione nel dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="8c238-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="8c238-116">Più prodotti di sicurezza potrebbero essere in conflitto e influire sulle prestazioni dell'host.</span><span class="sxs-lookup"><span data-stu-id="8c238-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="8c238-117">I passaggi seguenti possono essere utilizzati per risolvere e attenuare questi problemi:</span><span class="sxs-lookup"><span data-stu-id="8c238-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="8c238-118">Disabilitare la protezione in tempo reale utilizzando uno dei metodi seguenti e osservare se le prestazioni migliorano.</span><span class="sxs-lookup"><span data-stu-id="8c238-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="8c238-119">Questo approccio consente di stabilire se Defender for Endpoint per Linux contribuisce ai problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8c238-119">This approach helps narrow down whether Defender for Endpoint for Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="8c238-120">Se il dispositivo non è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="8c238-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="8c238-121">Se il dispositivo è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata dall'amministratore usando le istruzioni in Impostare le preferenze per [Defender per Endpoint per Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="8c238-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="8c238-122">Se il problema di prestazioni persiste quando la protezione in tempo reale è disattivata, l'origine del problema potrebbe essere il componente di rilevamento e risposta degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="8c238-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="8c238-123">In questo caso, contattare il supporto tecnico per ulteriori istruzioni e misure di prevenzione.</span><span class="sxs-lookup"><span data-stu-id="8c238-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="8c238-124">Per trovare le applicazioni che attivano il maggior numero di analisi, puoi usare le statistiche in tempo reale raccolte da Defender per Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="8c238-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c238-125">Questa funzionalità è disponibile nella versione 100.90.70 o successiva.</span><span class="sxs-lookup"><span data-stu-id="8c238-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="8c238-126">Questa funzionalità è abilitata per impostazione predefinita nei `Dogfood` canali e `InsiderFast` .</span><span class="sxs-lookup"><span data-stu-id="8c238-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="8c238-127">Se si utilizza un canale di aggiornamento diverso, questa funzionalità può essere abilitata dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="8c238-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="8c238-128">Questa funzionalità richiede l'attivazione della protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="8c238-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="8c238-129">Per verificare lo stato della protezione in tempo reale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8c238-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="8c238-130">Verificare che la `real_time_protection_enabled` voce sia `true` .</span><span class="sxs-lookup"><span data-stu-id="8c238-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="8c238-131">In caso contrario, eseguire il comando seguente per abilitarlo:</span><span class="sxs-lookup"><span data-stu-id="8c238-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="8c238-132">Per raccogliere le statistiche correnti, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8c238-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="8c238-133">```--output json```L'uso (nota il trattino doppio) garantisce che il formato di output sia pronto per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="8c238-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="8c238-134">L'output di questo comando mostrerà tutti i processi e l'attività di analisi associata.</span><span class="sxs-lookup"><span data-stu-id="8c238-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="8c238-135">Nel sistema Linux, scarica il parser python **di esempio high_cpu_parser.py** usando il comando:</span><span class="sxs-lookup"><span data-stu-id="8c238-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="8c238-136">L'output di questo comando deve essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8c238-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="8c238-137">Digitare quindi i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c238-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="8c238-138">L'output di cui sopra è un elenco dei principali collaboratori ai problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8c238-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="8c238-139">La prima colonna è l'identificatore di processo (PID), la seconda è il nome del processo e l'ultima colonna è il numero di file analizzati, ordinati in base all'impatto.</span><span class="sxs-lookup"><span data-stu-id="8c238-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="8c238-140">Ad esempio, l'output del comando sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8c238-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
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

    <span data-ttu-id="8c238-141">Per migliorare le prestazioni di Defender per Endpoint per Linux, individua quello con il numero più alto sotto la riga e `Total files scanned` aggiungi un'esclusione per esso.</span><span class="sxs-lookup"><span data-stu-id="8c238-141">To improve the performance of Defender for Endpoint for Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="8c238-142">Per altre informazioni, vedi [Configurare e convalidare le esclusioni per Defender per Endpoint per Linux.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="8c238-142">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="8c238-143">L'applicazione archivia le statistiche in memoria e tiene traccia dell'attività dei file solo dopo l'avvio e l'attivazione della protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="8c238-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="8c238-144">I processi avviati prima o durante i periodi in cui la protezione in tempo reale era disattivata non vengono conteggiati.</span><span class="sxs-lookup"><span data-stu-id="8c238-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="8c238-145">Inoltre, vengono conteggiati solo gli eventi che hanno attivato le analisi.</span><span class="sxs-lookup"><span data-stu-id="8c238-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="8c238-146">Configurare Microsoft Defender ATP per Linux con esclusioni per i processi o le posizioni del disco che contribuiscono ai problemi di prestazioni e ri-abilitare la protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="8c238-146">Configure Microsoft Defender ATP for Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="8c238-147">Per altre informazioni, vedi [Configurare e convalidare le esclusioni per Microsoft Defender ATP per Linux.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="8c238-147">For more information, see [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span></span>
