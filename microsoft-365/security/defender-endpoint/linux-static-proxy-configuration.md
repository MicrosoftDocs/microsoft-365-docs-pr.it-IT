---
title: Individuazione proxy statico di Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Descrive come configurare Microsoft Defender ATP per l'individuazione di proxy statici.
keywords: microsoft, defender, atp, linux, installazione, proxy
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
ms.openlocfilehash: 461c728f6b61aa407d76e3674ba3339027c21a25
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187458"
---
# <a name="configure-microsoft-defender-for-endpoint-for-linux-for-static-proxy-discovery"></a>Configurare Microsoft Defender per Endpoint per Linux per l'individuazione di proxy statici

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender ATP può individuare un server proxy utilizzando la ```HTTPS_PROXY``` variabile di ambiente. Questa impostazione deve essere **configurata sia al** momento dell'installazione che dopo l'installazione del prodotto.

## <a name="installation-time-configuration"></a>Configurazione del tempo di installazione

Durante l'installazione, ```HTTPS_PROXY``` la variabile di ambiente deve essere passata a Gestione pacchetti. Gestione pacchetti può leggere questa variabile in uno dei modi seguenti:

- La ```HTTPS_PROXY``` variabile è definita nella riga ```/etc/environment``` seguente:

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- La variabile è definita nella configurazione globale `HTTPS_PROXY` di Gestione pacchetti. Ad esempio, in Ubuntu 18.04, è possibile aggiungere la riga seguente a `/etc/apt/apt.conf.d/proxy.conf` :
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > Si noti che i due metodi precedenti potrebbero definire il proxy da utilizzare per altre applicazioni nel sistema. Utilizzare questo metodo con cautela o solo se si tratta di una configurazione generalmente globale.
  
- La `HTTPS_PROXY` variabile viene anteposta ai comandi di installazione o disinstallazione. Ad esempio, con gestione pacchetti APT, anteporre la variabile come segue durante l'installazione di Microsoft Defender per Endpoint: 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > Non aggiungere sudo tra la definizione della variabile di ambiente e apt, altrimenti la variabile non verrà propagata.

La `HTTPS_PROXY` variabile di ambiente può essere definita in modo analogo durante la disinstallazione.

Si noti che l'installazione e la disinstallazione non avranno necessariamente esito negativo se è necessario un proxy ma non è configurato. Tuttavia, la telemetria non verrà inviata e l'operazione potrebbe richiedere molto più tempo a causa dei timeout di rete.

## <a name="post-installation-configuration"></a>Configurazione post-installazione
  
Dopo l'installazione, `HTTPS_PROXY` la variabile di ambiente deve essere definita nel file del servizio Defender for Endpoint. A tale scopo, apri `/lib/systemd/system/mdatp.service` in un editor di testo durante l'esecuzione come utente radice. È quindi possibile propagare la variabile al servizio in uno dei due modi seguenti:

- Rimuovere il commento dalla riga `#Environment="HTTPS_PROXY=http://address:port"` e specificare l'indirizzo proxy statico.

- Aggiungere una riga `EnvironmentFile=/path/to/env/file` . Questo percorso può puntare a o a un file personalizzato, uno dei quali `/etc/environment` deve aggiungere la riga seguente:
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

Dopo aver modificato il `mdatp.service` file, salvarlo e chiuderlo. Riavviare il servizio in modo che le modifiche possano essere applicate. In Ubuntu, questo implica due comandi:  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
