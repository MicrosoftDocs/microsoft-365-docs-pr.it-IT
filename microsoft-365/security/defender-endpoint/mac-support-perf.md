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
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Risolvere i problemi di prestazioni per Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint su macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Questo argomento fornisce alcuni passaggi generali che possono essere usati per limitare i problemi di prestazioni correlati a Microsoft Defender per Endpoint in macOS.

La protezione in tempo reale (RTP) è una funzionalità di Microsoft Defender for Endpoint su macOS che monitora e protegge continuamente il dispositivo dalle minacce. È costituito dal monitoraggio di file e processi e da altre euristiche.

A seconda delle applicazioni in esecuzione e delle caratteristiche del dispositivo, è possibile che si verifichino prestazioni non ottimali quando si esegue Microsoft Defender per Endpoint in macOS. In particolare, le applicazioni o i processi di sistema che accedono a molte risorse in un breve periodo di tempo possono causare problemi di prestazioni in Microsoft Defender per Endpoint in macOS.

I passaggi seguenti possono essere utilizzati per risolvere e attenuare questi problemi:

1. Disabilitare la protezione in tempo reale utilizzando uno dei metodi seguenti e osservare se le prestazioni migliorano. Questo approccio consente di stabilire se Microsoft Defender for Endpoint in macOS contribuisce ai problemi di prestazioni.

      Se il dispositivo non è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata utilizzando una delle opzioni seguenti:

    - Dall'interfaccia utente. Apri Microsoft Defender per Endpoint in macOS e passa a **Gestisci impostazioni.**

      ![Schermata Gestisci protezione in tempo reale](images/mdatp-36-rtp.png)

    - Dal terminale. Per motivi di sicurezza, questa operazione richiede l'elevazione.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      Se il dispositivo è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata dall'amministratore usando le istruzioni in Impostare le preferenze per [Microsoft Defender per Endpoint su macOS.](mac-preferences.md)
      
      Se il problema di prestazioni persiste quando la protezione in tempo reale è disattivata, l'origine del problema potrebbe essere il componente di rilevamento e risposta degli endpoint. In questo caso, contattare il supporto tecnico per ulteriori istruzioni e misure di prevenzione.

2. Apri il Finder e passa a **Utilità**  >  **applicazioni.** Aprire **Monitoraggio attività** e analizzare le applicazioni che utilizzano le risorse del sistema. Esempi tipici sono gli aggiornamenti software e i compilatori.

1. Per trovare le applicazioni che attivano il maggior numero di analisi, puoi usare le statistiche in tempo reale raccolte da Defender per Endpoint su Mac.

      > [!NOTE]
      > Questa funzionalità è disponibile nella versione 100.90.70 o successiva.
      Questa funzionalità è abilitata per impostazione predefinita nei **canali Dogfood** **e InsiderFast.** Se si utilizza un canale di aggiornamento diverso, questa funzionalità può essere abilitata dalla riga di comando:
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      Questa funzionalità richiede l'attivazione della protezione in tempo reale. Per verificare lo stato della protezione in tempo reale, eseguire il comando seguente:

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    Verificare che la **voce real_time_protection_enabled** sia true. In caso contrario, eseguire il comando seguente per abilitarlo:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      Per raccogliere le statistiche correnti, eseguire:

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > **L'uso di --output json** (nota il trattino doppio) garantisce che il formato di output sia pronto per l'analisi.
      L'output di questo comando mostrerà tutti i processi e l'attività di analisi associata.

1. Nel sistema Mac scarica il parser python di esempio high_cpu_parser.py usando il comando:

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    L'output di questo comando deve essere simile al seguente:

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

1. Digitare quindi i comandi seguenti:

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      L'output di cui sopra è un elenco dei principali collaboratori ai problemi di prestazioni. La prima colonna è l'identificatore di processo (PID), la seconda è il nome del processo e l'ultima colonna è il numero di file analizzati, ordinati in base all'impatto.

      Ad esempio, l'output del comando sarà simile al seguente:

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

      Per migliorare le prestazioni di Defender per Endpoint su Mac, individua quello con il numero più alto nella riga Totale file analizzati e aggiungi un'esclusione. Per altre informazioni, vedi [Configurare e convalidare le esclusioni per Defender per Endpoint su Linux.](linux-exclusions.md)

      > [!NOTE]
      > L'applicazione archivia le statistiche in memoria e tiene traccia dell'attività dei file solo dopo l'avvio e l'attivazione della protezione in tempo reale. I processi avviati prima o durante i periodi in cui la protezione in tempo reale era disattivata non vengono conteggiati. Inoltre, vengono conteggiati solo gli eventi che hanno attivato le analisi.
      > 
1. Configurare Microsoft Defender per Endpoint in macOS con esclusioni per i processi o le posizioni del disco che contribuiscono ai problemi di prestazioni e ri-abilitare la protezione in tempo reale.

     Per informazioni dettagliate, vedi Configurare e convalidare le esclusioni per [Microsoft Defender per Endpoint su macOS.](mac-exclusions.md)
