---
title: Risolvere i problemi relativi alle estensioni del kernel in Microsoft Defender ATP per Mac
description: Risolvere i problemi relativi alle estensioni del kernel in Microsoft Defender ATP per Mac.
keywords: microsoft, defender, atp, mac, kernel, estensione
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
ms.openlocfilehash: bdd5c6309a19863339b00e846c1c2670fc4f261b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187602"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a>Risolvere i problemi di estensione del kernel in Microsoft Defender per Endpoint per Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per Endpoint per Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Questo articolo fornisce informazioni su come risolvere i problemi relativi all'estensione del kernel installata come parte di Microsoft Defender per Endpoint per Mac.

A partire da macOS High Sierra (10.13), macOS richiede che tutte le estensioni del kernel siano approvate in modo esplicito prima di poter essere eseguite nel dispositivo.

Se non hai approvato l'estensione del kernel durante la distribuzione/installazione di Microsoft Defender per Endpoint per Mac, l'applicazione visualizza un banner in cui viene richiesto di abilitarla:

   ![Schermata disabilitata RTP](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-32-main-app-fix)

È inoltre possibile eseguire ```mdatp health``` . Segnala se la protezione in tempo reale è abilitata ma non disponibile. Questo indica che l'estensione del kernel non è approvata per l'esecuzione nel dispositivo.

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

Le sezioni seguenti forniscono indicazioni su come risolvere questo problema, a seconda del metodo usato per distribuire Microsoft Defender per Endpoint per Mac.

## <a name="managed-deployment"></a>Distribuzione gestita

Vedi le istruzioni corrispondenti al tool di gestione usato per distribuire il prodotto:

- [Distribuzione basata su JAMF](mac-install-with-jamf.md)
- [Distribuzione basata su Microsoft Intune](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>Distribuzione manuale

Se sono trascorsi meno di 30 minuti dall'installazione del prodotto, passare a Preferenze di sistema Sicurezza & Privacy , dove è necessario consentire il software di sistema dagli sviluppatori  >  "Microsoft Corporation". 

Se non viene visualizzato questo prompt, significa che sono trascorsi 30 o più minuti e che l'estensione del kernel non è ancora stata approvata per l'esecuzione nel dispositivo:

![Finestra sicurezza e privacy dopo la richiesta di schermata scaduta](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-33-securityprivacysettings-noprompt)

In questo caso, è necessario eseguire i passaggi seguenti per attivare di nuovo il flusso di approvazione.

1. In Terminale, tentare di installare il driver. L'operazione seguente avrà esito negativo perché l'estensione del kernel non è stata approvata per l'esecuzione nel dispositivo. Tuttavia, attiverà di nuovo il flusso di approvazione.

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. Apri **Preferenze di** sistema Sicurezza &  >  **Privacy** dal menu. Chiuderlo prima, se aperto.

3. **Consenti** software di sistema dagli sviluppatori "Microsoft Corporation"

4. In Terminale, installare di nuovo il driver. Questa volta l'operazione avrà esito positivo:

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    Il banner dovrebbe scomparire dall'applicazione Defender e dovrebbe ora segnalare che la protezione in tempo reale ```mdatp health``` è sia abilitata che disponibile:

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
