---
title: Risolvere i problemi di connettività cloud per Microsoft Defender for Endpoint in macOS
description: Questo argomento descrive come risolvere i problemi di connettività cloud per Microsoft Defender for Endpoint in macOS
keywords: microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 08e3701283dd7a2de7396a66e07214b997236bed
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764076"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Risolvere i problemi di connettività cloud per Microsoft Defender for Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Piattaforma** macOS

Questo argomento descrive come risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint in macOS.

## <a name="run-the-connectivity-test"></a>Eseguire il test di connettività
Per verificare se Defender per Endpoint su Mac può comunicare con il cloud con le impostazioni di rete correnti, esegui un test di connettività dalla riga di comando:

```Bash
mdatp connectivity test
```

output previsto:
```Bash
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

Se il test di connettività ha esito negativo, verificare se il dispositivo dispone dell'accesso a Internet e se uno qualsiasi [degli endpoint](microsoft-defender-endpoint-mac.md#network-connections) richiesti dal prodotto è bloccato da un proxy o da un firewall.

Gli errori con errore di arricciatura 35 o 60 indicano il rifiuto dell'aggiunta del certificato, che indica un potenziale problema con l'ispezione SSL o HTTPS. Vedi le istruzioni seguenti relative alla configurazione dell'ispezione SSL.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Procedura di risoluzione dei problemi per gli ambienti senza proxy o con proxy autoconfig (PAC) o con WPAD (Web Proxy Autodiscovery Protocol)
Utilizzare la procedura seguente per verificare che una connessione non sia bloccata in un ambiente senza proxy o con proxy autoconfig (PAC) o con WPAD (Web Proxy Autodiscovery Protocol).

Se un proxy o un firewall blocca il traffico anonimo, assicurati che il traffico anonimo sia consentito negli URL elencati in precedenza.

> [!WARNING]
> I proxy autenticati non sono supportati. Assicurati che vengano usati solo PAC, WPAD o un proxy statico. Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza. Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Microsoft Defender per Endpoint su macOS agli URL rilevanti senza intercettazione. L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.
Per verificare che una connessione non sia bloccata: in un browser come Microsoft Edge per Mac o Safari aprire https://x.cp.wd.microsoft.com/api/report e https://cdn.x.cp.wd.microsoft.com/ping .

Facoltativamente, in Terminale eseguire il comando seguente:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

L'output di questo comando deve essere simile al seguente:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
