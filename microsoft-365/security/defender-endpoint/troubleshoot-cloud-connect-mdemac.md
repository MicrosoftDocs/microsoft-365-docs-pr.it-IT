---
title: Risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint per Mac
description: Questo argomento descrive come risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint per Mac
keywords: microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e522495fa86b5a71faa9f25cc863c29cc5d124c0
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476686"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint per Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Piattaforma** macOS

Questo argomento descrive come risolvere i problemi di connettività cloud per Microsoft Defender per Endpoint per Mac.

## <a name="run-the-connectivity-test"></a>Eseguire il test di connettività
Per verificare se Defender per Endpoint per Mac può comunicare con il cloud con le impostazioni di rete correnti, esegui un test di connettività dalla riga di comando:

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
> I proxy autenticati non sono supportati. Assicurati che vengano usati solo PAC, WPAD o un proxy statico. Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza. Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Microsoft Defender per Endpoint per Mac agli URL rilevanti senza intercettazione. L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.
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
