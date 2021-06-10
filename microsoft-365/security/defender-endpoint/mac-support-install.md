---
title: Risolvere i problemi di installazione per Microsoft Defender per Endpoint su Mac
description: Risolvere i problemi di installazione in Microsoft Defender per Endpoint su Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installare
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
ms.openlocfilehash: 5166de3a7c7017979a93ac7026636ba24671892e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935150"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Risolvere i problemi di installazione per Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint su macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Installazione non riuscita

Per l'installazione manuale, nella pagina Riepilogo dell'installazione guidata viene visualizzato il messaggio "Si è verificato un errore durante l'installazione. Il programma di installazione ha rilevato un errore che ha causato l'errore dell'installazione. Contattare il produttore del software per assistenza." Per le distribuzioni MDM, viene visualizzato anche come errore di installazione generico.

Anche se non viene visualizzato un errore esatto per l'utente finale, si mantiene un file di registro con lo stato di avanzamento dell'installazione in `/Library/Logs/Microsoft/mdatp/install.log` . Ogni sessione di installazione viene aggiunta a questo file di registro. È possibile utilizzare solo `sed` per l'output dell'ultima sessione di installazione:

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

In questo esempio, il motivo effettivo è preceduto da `[ERROR]` .
L'installazione non è riuscita perché non è supportato un downgrade tra queste versioni.

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP log di installazione mancante o non aggiornato

In rari casi, l'installazione non lascia traccia nel file /Library/Logs/Microsoft/mdatp/install.log di MDATP.
Puoi verificare che sia stata eseguita un'installazione e analizzare i possibili errori tramite query sui log macOS (questa operazione è utile nella distribuzione MDM, quando non è disponibile un'interfaccia utente client). È consigliabile utilizzare un intervallo di tempo ristretto per eseguire una query e filtrare in base al nome del processo di registrazione, in quanto saranno disponibili un'enorme quantità di informazioni.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
