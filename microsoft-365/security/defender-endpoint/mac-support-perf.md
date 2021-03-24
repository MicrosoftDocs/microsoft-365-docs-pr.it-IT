---
title: Risolvere i problemi di prestazioni per Microsoft Defender ATP per Mac
description: Risolvere i problemi di prestazioni in Microsoft Defender ATP per Mac.
keywords: microsoft, defender, atp, mac, prestazioni
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
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062221"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Risolvere i problemi di prestazioni per Microsoft Defender per Endpoint per Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per Endpoint per Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Questo argomento fornisce alcuni passaggi generali che possono essere usati per limitare i problemi di prestazioni correlati a Microsoft Defender per Endpoint per Mac.

La protezione in tempo reale (RTP) è una funzionalità di Microsoft Defender per Endpoint per Mac che monitora e protegge continuamente il dispositivo dalle minacce. È costituito dal monitoraggio di file e processi e da altre euristiche.

A seconda delle applicazioni in esecuzione e delle caratteristiche del dispositivo, è possibile che si verifichino prestazioni non ottimali quando si esegue Microsoft Defender per Endpoint per Mac. In particolare, le applicazioni o i processi di sistema che accedono a molte risorse in un breve periodo di tempo possono causare problemi di prestazioni in Microsoft Defender per Endpoint per Mac.

I passaggi seguenti possono essere utilizzati per risolvere e attenuare questi problemi:

1. Disabilitare la protezione in tempo reale utilizzando uno dei metodi seguenti e osservare se le prestazioni migliorano. Questo approccio consente di stabilire se Microsoft Defender per Endpoint per Mac contribuisce ai problemi di prestazioni.

    Se il dispositivo non è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata utilizzando una delle opzioni seguenti:

    - Dall'interfaccia utente. Apri Microsoft Defender per Endpoint per Mac e passa a **Gestisci impostazioni.**

      ![Schermata Gestisci protezione in tempo reale](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - Dal terminale. Per motivi di sicurezza, questa operazione richiede l'elevazione.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    Se il dispositivo è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata dall'amministratore usando le istruzioni in Impostare le preferenze per [Microsoft Defender per Endpoint per Mac.](mac-preferences.md)

2. Apri il Finder e passa a **Utilità**  >  **applicazioni.** Aprire **Monitoraggio attività** e analizzare le applicazioni che utilizzano le risorse del sistema. Esempi tipici sono gli aggiornamenti software e i compilatori.

3. Configurare Microsoft Defender per Endpoint per Mac con esclusioni per i processi o le posizioni del disco che contribuiscono ai problemi di prestazioni e ri-abilitare la protezione in tempo reale.

    Per [informazioni dettagliate, vedi](mac-exclusions.md) Configurare e convalidare le esclusioni per Microsoft Defender per Endpoint per Mac.
