---
title: Risorse di Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Descrive le risorse per Microsoft Defender ATP per Linux, tra cui come disinstallarlo, come raccogliere log di diagnostica, comandi CLI e problemi noti con il prodotto.
keywords: microsoft, defender, atp, linux, installazione, distribuire, disinstallazione, pupazzo, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: ab5400a197a1f0ac61c8b298a06165d217f44fd1
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394735"
---
# <a name="resources"></a>Risorse

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Raccogliere informazioni di diagnostica

Se è possibile riprodurre un problema, aumentare innanzitutto il livello di registrazione, eseguire il sistema per un certo periodo di tempo e quindi ripristinare il livello di registrazione predefinito.

1. Aumentare il livello di registrazione:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Riprodurre il problema.

3. Eseguire il comando seguente per eseguire il backup dei log di Defender for Endpoint. I file verranno archiviati all'interno di un archivio ZIP.

   ```bash
   sudo mdatp diagnostic create
   ```

    Questo comando stamperà anche il percorso del file di backup al termine dell'operazione:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Livello di registrazione ripristino:

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Registrare i problemi di installazione

Se si verifica un errore durante l'installazione, il programma di installazione segnala solo un errore generale.

Il registro dettagliato verrà salvato in `/var/log/microsoft/mdatp_install.log` . Se si verificano problemi durante l'installazione, inviare questo file in modo da poter diagnosticare la causa.

## <a name="uninstall"></a>Uninstall

Esistono diversi modi per disinstallare Defender for Endpoint per Linux. Se stai usando uno strumento di configurazione come Puppet, segui le istruzioni per la disinstallazione del pacchetto per lo strumento di configurazione.

### <a name="manual-uninstallation"></a>Disinstallazione manuale

- `sudo yum remove mdatp` per RHEL e variants(CentOS e Oracle Linux).
- `sudo zypper remove mdatp` per SLES e varianti.
- `sudo apt-get purge mdatp` per i sistemi Ubuntu e Debian.

## <a name="configure-from-the-command-line"></a>Configurare dalla riga di comando

Attività importanti, ad esempio il controllo delle impostazioni del prodotto e l'attivazione di analisi su richiesta, possono essere eseguite dalla riga di comando.

### <a name="global-options"></a>Opzioni globali

Per impostazione predefinita, lo strumento da riga di comando restituisce il risultato in formato leggibile dall'utente. Inoltre, lo strumento supporta anche l'output del risultato come JSON, che è utile per gli scenari di automazione. Per modificare l'output in JSON, passa `--output json` uno dei comandi seguenti.

### <a name="supported-commands"></a>Comandi supportati

Nella tabella seguente sono elencati i comandi per alcuni degli scenari più comuni. Eseguire `mdatp help` dal terminale per visualizzare l'elenco completo dei comandi supportati.

|Gruppo                 |Scenario                                                |Comando                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|Configurazione         |Attivare/disattivare la protezione in tempo reale                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|Configurazione         |Attivare/disattivare il monitoraggio del comportamento                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|Configurazione         |Attivare/disattivare la protezione cloud                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|Configurazione         |Attivare/disattivare la diagnostica del prodotto                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|Configurazione         |Attivare/disattivare l'invio automatico di esempi                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|Configurazione         |Attivare/disattivare la modalità passiva AV                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|Configurazione         |Aggiungere/rimuovere un'esclusione antivirus per un'estensione di file  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|Configurazione         |Aggiungere/rimuovere un'esclusione antivirus per un file            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|Configurazione         |Aggiungere/rimuovere un'esclusione antivirus per una directory       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|Configurazione         |Aggiungere/rimuovere un'esclusione antivirus per un processo         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|Configurazione         |Elencare tutte le esclusioni antivirus                           |`mdatp exclusion list`                                                 |
|Configurazione         |Aggiungere un nome di minaccia all'elenco delle minacce consentite                   |`mdatp threat allowed add --name [threat-name]`                        |
|Configurazione         |Rimuovere un nome di minaccia dall'elenco delle minacce consentite              |`mdatp threat allowed remove --name [threat-name]`                     |
|Configurazione         |Elencare tutti i nomi delle minacce consentite                           |`mdatp threat allowed list`                                            |
|Configurazione         |Attivare la protezione dei criteri di protezione dall'accesso di posta elettronica                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|Configurazione         |Disattivare la protezione puA                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|Configurazione         |Attivare la modalità di controllo per la protezione delle informazioni di accesso utente                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|Diagnostica           |Modificare il livello di registrazione                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|Diagnostica           |Generare log di diagnostica                                |`mdatp diagnostic create --path [directory]`                           |
|Sanità                |Verificare l'integrità del prodotto                              |`mdatp health`                                                         |
|Protezione            |Analizzare un percorso                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|Protezione            |Eseguire un'analisi rapida                                         |`mdatp scan quick`                                                     |
|Protezione            |Eseguire un'analisi completa                                          |`mdatp scan full`                                                      |
|Protezione            |Annullare un'analisi su richiesta in corso                        |`mdatp scan cancel`                                                    |
|Protezione            |Richiedere un aggiornamento di security intelligence                  |`mdatp definitions update`                                             |
|Cronologia protezione    |Stampare la cronologia di protezione completa                       |`mdatp threat list`                                                    |
|Cronologia protezione    |Ottenere dettagli sulle minacce                                      |`mdatp threat get --id [threat-id]`                                    |
|Gestione della quarantena |Elencare tutti i file in quarantena                              |`mdatp threat quarantine list`                                         |
|Gestione della quarantena |Rimuovere tutti i file dalla quarantena                    |`mdatp threat quarantine remove-all`                                   |
|Gestione della quarantena |Aggiungere un file rilevato come minaccia alla quarantena       |`mdatp threat quarantine add --id [threat-id]`                         |
|Gestione della quarantena |Rimuovere un file rilevato come minaccia dalla quarantena  |`mdatp threat quarantine remove --id [threat-id]`                      |
|Gestione della quarantena |Ripristinare un file dalla quarantena                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|Rilevamento e risposta degli endpoint |Impostare l'anteprima anticipata (inutilizzata)                    |`mdatp edr early-preview [enable|disable]`                             |
|Rilevamento e risposta degli endpoint |Set group-id                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|Rilevamento e risposta degli endpoint |Tag Set/Remove, supportato `GROUP` solo        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|Rilevamento e risposta degli endpoint |esclusioni elenco (radice)                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Informazioni sul portale di Microsoft Defender for Endpoint

Nel portale defender per endpoint vedrai due categorie di informazioni:

- Avvisi antivirus, tra cui:
  - Gravità
  - Tipo di analisi
  - Informazioni sul dispositivo (nome host, identificatore dispositivo, identificatore tenant, versione dell'app e tipo di sistema operativo)
  - Informazioni sui file (nome, percorso, dimensioni e hash)
  - Informazioni sulle minacce (nome, tipo e stato)
- Informazioni sul dispositivo, tra cui:
  - Identificatore dispositivo
  - Identificatore tenant
  - Versione dell'app
  - Nome host
  - Tipo di sistema operativo
  - Versione del sistema operativo
  - Modello di computer
  - Architettura del processore
  - Indica se il dispositivo è una macchina virtuale

### <a name="known-issues"></a>Problemi noti

- Potresti vedere "Nessun dato del sensore, comunicazioni compromesse" nella pagina delle informazioni sul computer del portale di Microsoft Defender Security Center, anche se il prodotto funziona come previsto. Stiamo lavorando per risolvere questo problema.
- Gli utenti connessi non vengono visualizzati nel portale di Microsoft Defender Security Center.
- Nelle distribuzioni SUSE, se l'installazione di *libatomic1* non riesce, è necessario verificare che il sistema operativo sia registrato:

   ```bash
   sudo SUSEConnect --status-text
   ```
