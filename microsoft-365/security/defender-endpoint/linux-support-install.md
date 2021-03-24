---
title: Risolvere i problemi di installazione per Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Risolvere i problemi di installazione per Microsoft Defender ATP per Linux
keywords: microsoft, defender, atp, linux, installazione
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
ms.openlocfilehash: a83794675a20a61f4075e0f9c729cef95400e64e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065709"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Risolvere i problemi di installazione per Microsoft Defender for Endpoint per Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>Verificare se l'installazione è riuscita

Un errore durante l'installazione può causare o meno un messaggio di errore significativo da parte di Gestione pacchetti. Per verificare se l'installazione è riuscita, ottenere e controllare i registri di installazione utilizzando:

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

Un output del comando precedente con data e ora di installazione corrette indica l'esito positivo.

Controlla anche la [configurazione client per](linux-install-manually.md#client-configuration) verificare l'integrità del prodotto e rilevare il file di testo EICAR.

## <a name="make-sure-you-have-the-correct-package"></a>Assicurati di avere il pacchetto corretto

Tenere presente che il pacchetto che si sta installando corrisponde alla distribuzione host e alla versione.

| pacchetto                       | distribuzione                             |
|-------------------------------|------------------------------------------|
| mdatp-rhel8. Linux.x86_64.rpm  | Oracle, RHEL e CentOS 8.x              |
| mdatp-sles12. Linux.x86_64.rpm | SuSE Linux Enterprise Server 12.x        |
| mdatp-sles15. Linux.x86_64.rpm | SuSE Linux Enterprise Server 15.x        |
| mdatp. Linux.x86_64.rpm        | Oracle, RHEL e CentOS 7.x              |
| mdatp. Linux.x86_64.deb        | Debian e Ubuntu 16.04, 18.04 e 20.04 |

Per [la distribuzione](linux-install-manually.md)manuale, verificare che sia stata scelta la versione e la distribuzione corrette.

## <a name="installation-failed"></a>Installazione non riuscita

Verificare se il servizio mdatp è in esecuzione:

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>Procedura per la risoluzione dei problemi se il servizio mdatp non è in esecuzione

1. Verificare se l'utente "mdatp" esiste:

    ```bash
    id "mdatp"
    ```

    Se non è disponibile alcun output, eseguire

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Prova ad abilitare e riavviare il servizio usando:

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. Se mdatp.service non viene trovato durante l'esecuzione del comando precedente, eseguire:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    dove ```<systemd_path>``` è per le ```/lib/systemd/system``` distribuzioni di Ubuntu e Debian e ```/usr/lib/systemd/system``` per Rhel, CentOS, Oracle e SLES.
   Eseguire di nuovo il passaggio 2.

4. Se i passaggi precedenti non funzionano, controlla se SELinux è installato e in modalità di applicazione. In tal caso, prova a impostarlo sulla modalità permissiva (preferibilmente) o disabilitata. Può essere fatto impostando il parametro `SELINUX` su "permissive" o "disabled" nel `/etc/selinux/config` file, seguito dal riavvio. Controlla la pagina man-of-selinux per altri dettagli.
Provare a riavviare il servizio mdatp utilizzando il passaggio 2. Ripristinare immediatamente la modifica della configurazione per motivi di sicurezza dopo averli provati e aver riavviato.

5. Se `/opt` la directory è un collegamento simbolico, crea un binding mount per `/opt/microsoft` .

6. Verificare che il daemon abbia l'autorizzazione eseguibile.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Se il daemon non dispone di autorizzazioni eseguibili, rendilo eseguibile usando:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    e riprovare a eseguire il passaggio 2.

7. Assicurati che il file system contenente wdavdaemon non sia montato con "noexec".

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>Se il servizio mdatp è in esecuzione, ma il rilevamento dei file di testo EICAR non funziona

1. Controllare il tipo di file system usando:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    I file system attualmente supportati per le attività di accesso sono elencati [qui.](microsoft-defender-endpoint-linux.md#system-requirements) I file esterni a questi file system non verranno analizzati.

## <a name="command-line-tool-mdatp-isnt-working"></a>Lo strumento da riga di comando "mdatp" non funziona

1. Se l'esecuzione dello strumento da riga di comando `mdatp` restituisce un `command not found` errore, eseguire il comando seguente:

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    e riprovare.

    Se nessuno dei passaggi precedenti è utile, raccogliere i log di diagnostica:

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    Il percorso di un file ZIP contenente i registri verrà visualizzato come output. Contattare il supporto tecnico con questi log.
