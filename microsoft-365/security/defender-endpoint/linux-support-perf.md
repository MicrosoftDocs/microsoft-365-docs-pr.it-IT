---
title: Risolvere i problemi di prestazioni per Microsoft Defender ATP per Linux
description: Risolvere i problemi di prestazioni in Microsoft Defender ATP per Linux.
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
ms.openlocfilehash: 5c64d16e0753fa87713f2a34583825234fb9c98c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062485"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Risolvere i problemi di prestazioni per Microsoft Defender for Endpoint per Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Questo articolo fornisce alcuni passaggi generali che possono essere usati per limitare i problemi di prestazioni correlati a Defender per Endpoint per Linux.

La protezione in tempo reale (RTP) è una funzionalità di Defender for Endpoint per Linux che monitora e protegge continuamente il dispositivo dalle minacce. È costituito dal monitoraggio di file e processi e da altre euristiche.

A seconda delle applicazioni in esecuzione e delle caratteristiche del dispositivo, è possibile che si verifichino prestazioni non ottimali quando si esegue Defender per Endpoint per Linux. In particolare, le applicazioni o i processi di sistema che accedono a molte risorse in un breve periodo di tempo possono causare problemi di prestazioni in Defender for Endpoint per Linux.

Prima di iniziare, assicurati che altri prodotti di **sicurezza non siano attualmente in esecuzione nel dispositivo.** Più prodotti di sicurezza potrebbero essere in conflitto e influire sulle prestazioni dell'host.

I passaggi seguenti possono essere utilizzati per risolvere e attenuare questi problemi:

1. Disabilitare la protezione in tempo reale utilizzando uno dei metodi seguenti e osservare se le prestazioni migliorano. Questo approccio consente di stabilire se Defender for Endpoint per Linux contribuisce ai problemi di prestazioni.

    Se il dispositivo non è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata dalla riga di comando:

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    Se il dispositivo è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata dall'amministratore usando le istruzioni in Impostare le preferenze per [Defender per Endpoint per Linux.](linux-preferences.md)

    Se il problema di prestazioni persiste quando la protezione in tempo reale è disattivata, l'origine del problema potrebbe essere il componente di rilevamento e risposta degli endpoint. In questo caso, contattare il supporto tecnico per ulteriori istruzioni e misure di prevenzione.

2. Per trovare le applicazioni che attivano il maggior numero di analisi, puoi usare le statistiche in tempo reale raccolte da Defender per Endpoint per Linux.

    > [!NOTE]
    > Questa funzionalità è disponibile nella versione 100.90.70 o successiva.

    Questa funzionalità è abilitata per impostazione predefinita nei `Dogfood` canali e `InsiderFast` . Se si utilizza un canale di aggiornamento diverso, questa funzionalità può essere abilitata dalla riga di comando:
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    Questa funzionalità richiede l'attivazione della protezione in tempo reale. Per verificare lo stato della protezione in tempo reale, eseguire il comando seguente:

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    Verificare che la `real_time_protection_enabled` voce sia `true` . In caso contrario, eseguire il comando seguente per abilitarlo:

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    Per raccogliere le statistiche correnti, eseguire:

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > ```--output json```L'uso (nota il trattino doppio) garantisce che il formato di output sia pronto per l'analisi.

    L'output di questo comando mostrerà tutti i processi e l'attività di analisi associata.

3. Nel sistema Linux, scarica il parser python **di esempio high_cpu_parser.py** usando il comando:

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    L'output di questo comando deve essere simile al seguente:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. Digitare quindi i comandi seguenti:

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      L'output di cui sopra è un elenco dei principali collaboratori ai problemi di prestazioni. La prima colonna è l'identificatore di processo (PID), la seconda è il nome del processo e l'ultima colonna è il numero di file analizzati, ordinati in base all'impatto.
    Ad esempio, l'output del comando sarà simile al seguente: 

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

    Per migliorare le prestazioni di Defender per Endpoint per Linux, individua quello con il numero più alto sotto la riga e `Total files scanned` aggiungi un'esclusione per esso. Per altre informazioni, vedi [Configurare e convalidare le esclusioni per Defender per Endpoint per Linux.](linux-exclusions.md)

    >[!NOTE]
    > L'applicazione archivia le statistiche in memoria e tiene traccia dell'attività dei file solo dopo l'avvio e l'attivazione della protezione in tempo reale. I processi avviati prima o durante i periodi in cui la protezione in tempo reale era disattivata non vengono conteggiati. Inoltre, vengono conteggiati solo gli eventi che hanno attivato le analisi.

5. Configurare Microsoft Defender ATP per Linux con esclusioni per i processi o le posizioni del disco che contribuiscono ai problemi di prestazioni e ri-abilitare la protezione in tempo reale.

    Per altre informazioni, vedi [Configurare e convalidare le esclusioni per Microsoft Defender ATP per Linux.](linux-exclusions.md)
