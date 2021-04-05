---
title: Risolvere i problemi di connettività cloud per Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Risolvere i problemi di connettività cloud per Microsoft Defender ATP per Linux
keywords: microsoft, defender, atp, linux, cloud, connettività, comunicazione
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 77ab7bbbb156165f26538cf3d14eae1e5e76d92c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587540"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Risolvere i problemi di connettività cloud per Microsoft Defender for Endpoint per Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>Eseguire il test di connettività

Per verificare se Defender per Endpoint per Linux può comunicare con il cloud con le impostazioni di rete correnti, eseguire un test di connettività dalla riga di comando:

```bash
mdatp connectivity test
```

output previsto:

```output
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

Se il test di connettività ha esito negativo, verificare se il dispositivo dispone dell'accesso a Internet e se uno qualsiasi [degli endpoint](microsoft-defender-endpoint-linux.md#network-connections) richiesti dal prodotto è bloccato da un proxy o da un firewall.

Errori con errore di arricciatura 35 o 60, indicare il rifiuto dell'aggiunta del certificato. Verificare se la connessione è sotto controllo SSL o HTTPS. In tal caso, aggiungi Microsoft Defender for Endpoint all'elenco consenti.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Procedura di risoluzione dei problemi per gli ambienti senza proxy o con proxy trasparente

Per verificare che una connessione non sia bloccata in un ambiente senza un proxy o con un proxy trasparente, eseguire il comando seguente nel terminale:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

L'output di questo comando deve essere simile al seguente:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Procedura di risoluzione dei problemi per gli ambienti con proxy statico

> [!WARNING]
> PAC, WPAD e proxy autenticati non sono supportati. Verificare che sia in uso solo un proxy statico o trasparente.
>
> Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza. Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Defender per Endpoint per Linux agli URL rilevanti senza intercettazione. L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.

Se è necessario un proxy statico, aggiungi un parametro proxy al comando precedente, dove `proxy_address:port` corrisponde all'indirizzo proxy e alla porta:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Assicurati di usare lo stesso indirizzo proxy e la stessa porta configurati nel `/lib/system/system/mdatp.service` file. Controlla la configurazione del proxy se sono presenti errori dai comandi precedenti.

> [!WARNING]
> Il proxy statico non può essere configurato tramite una variabile di ambiente a `HTTPS_PROXY` livello di sistema. Assicurati invece che `HTTPS_PROXY` sia impostato correttamente nel `/lib/system/system/mdatp.service` file.

Per utilizzare un proxy statico, è `mdatp.service` necessario modificare il file. Assicurarsi che `#` l'interlinea venga rimossa per rimuovere il commento dalla riga seguente `/lib/systemd/system/mdatp.service` da :

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

Assicurarsi inoltre che sia stato inserito l'indirizzo proxy statico corretto per sostituire `address:port` .

Se questo file è corretto, prova a eseguire il comando seguente nel terminale per ricaricare Defender per Endpoint per Linux e propagare l'impostazione:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

In caso di esito positivo, tentare un altro test di connettività dalla riga di comando:

```bash
mdatp connectivity test
```

Se il problema persiste, contattare il supporto tecnico.

## <a name="resources"></a>Risorse

- Per ulteriori informazioni su come configurare il prodotto per l'utilizzo di un proxy statico, vedere [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).
