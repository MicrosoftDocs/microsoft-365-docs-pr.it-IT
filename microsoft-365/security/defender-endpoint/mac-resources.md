---
title: Risorse per Microsoft Defender per Endpoint per Mac
description: Risorse per Microsoft Defender per Endpoint per Mac, tra cui come disinstallarlo, come raccogliere log di diagnostica, comandi CLI e problemi noti con il prodotto.
keywords: microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 98e123ac4775096c968bc831965a562481c848b6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862176"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>Risorse per Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Raccolta di informazioni di diagnostica

Se è possibile riprodurre un problema, aumentare il livello di registrazione, eseguire il sistema per un certo periodo di tempo e ripristinare il livello di registrazione predefinito.

1. Aumentare il livello di registrazione:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. Riprodurre il problema

3. Eseguire `sudo mdatp diagnostic create` il backup dei log di Microsoft Defender for Endpoint. I file verranno archiviati all'interno di un archivio ZIP. Questo comando stamperà anche il percorso del file per il backup al termine dell'operazione.

   > [!TIP]
   > Per impostazione predefinita, i log di diagnostica vengono salvati in `/Library/Application Support/Microsoft/Defender/wdavdiag/` . Per modificare la directory in cui vengono salvati i log di diagnostica, passare `--path [directory]` al comando seguente, sostituendo `[directory]` con la directory desiderata.

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Livello di registrazione ripristino:

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Registrazione dei problemi di installazione

Se si verifica un errore durante l'installazione, il programma di installazione segnala solo un errore generale.

Il registro dettagliato verrà salvato in `/Library/Logs/Microsoft/mdatp/install.log` . Se si verificano problemi durante l'installazione, inviare questo file in modo da poter diagnosticare la causa.

## <a name="uninstalling"></a>Disinstallazione

Esistono diversi modi per disinstallare Microsoft Defender for Endpoint in macOS. Tieni presente che, anche se la disinstallazione gestita centralmente è disponibile in JAMF, non è ancora disponibile per Microsoft Intune.

### <a name="interactive-uninstallation"></a>Disinstallazione interattiva

- Aprire **Il Finder > Applicazioni**. Fai clic con il pulsante destro del mouse su **Microsoft Defender per Endpoint > sposta nel Cestino.**

### <a name="from-the-command-line"></a>Dalla riga di comando

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a>Configurazione dalla riga di comando

Le attività importanti, ad esempio il controllo delle impostazioni del prodotto e l'attivazione di analisi su richiesta, possono essere eseguite dalla riga di comando:

|Gruppo        |Scenario                                   |Comando                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|Configurazione|Attivare/disattivare la protezione in tempo reale           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|Configurazione|Attivare/disattivare la protezione cloud               |`mdatp config cloud --value [enabled/disabled]`                                   |
|Configurazione|Attivare/disattivare la diagnostica del prodotto            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|Configurazione|Attivare/disattivare l'invio automatico di esempi    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|Configurazione|Aggiungere un nome di minaccia all'elenco delle minacce consentite      |`mdatp threat allowed add --name [threat-name]`                                   |
|Configurazione|Rimuovere un nome di minaccia dall'elenco delle minacce consentite |`mdatp threat allowed remove --name [threat-name]`                                |
|Configurazione|Elencare tutti i nomi delle minacce consentite              |`mdatp threat allowed list`                                                       |
|Configurazione|Attivare la protezione dei criteri di protezione dall'accesso di posta elettronica                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|Configurazione|Disattivare la protezione puA                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|Configurazione|Attivare la modalità di controllo per la protezione delle informazioni di accesso utente      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|Configurazione|Attivare/disattivare passiveMode                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|Diagnostica  |Modificare il livello di registrazione                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|Diagnostica  |Generare log di diagnostica                   |`mdatp diagnostic create --path [directory]`                                      |
|Sanità       |Verificare l'integrità del prodotto                 |`mdatp health`                                                                    |
|Sanità       |Verificare la presenza di un attributo del prodotto specifico       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|Protezione   |Analizzare un percorso                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|Protezione   |Eseguire un'analisi rapida                            |`mdatp scan quick`                                                                |
|Protezione   |Eseguire un'analisi completa                             |`mdatp scan full`                                                                 |
|Protezione   |Annullare un'analisi su richiesta in corso           |`mdatp scan cancel`                                                               |
|Protezione   |Richiedere un aggiornamento di security intelligence     |`mdatp definitions update`                                                        |
|EDR          |Aggiungi tag di gruppo al dispositivo. I tag EDR vengono utilizzati per la gestione dei gruppi di dispositivi. Per ulteriori informazioni, visitare https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |Rimuovere il tag di gruppo dal dispositivo               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |Aggiungere l'ID gruppo                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>Come abilitare il completamento automatico

Per abilitare il completamento automatico in bash, eseguire il comando seguente e riavviare la sessione terminale:

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

Per abilitare il completamento automatico in zsh:

- Controlla se la funzionalità di completamento automatico è abilitata nel dispositivo:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Se il comando precedente non produce alcun output, è possibile abilitare il completamento automatico utilizzando il comando seguente:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Eseguire i comandi seguenti per abilitare il completamento automatico per Microsoft Defender per Endpoint in macOS e riavviare la sessione terminal:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Client Microsoft Defender for Endpoint quarantine directory

`/Library/Application Support/Microsoft/Defender/quarantine/` contiene i file messi in quarantena da `mdatp` . I file sono denominati in base al trackingId delle minacce. L'oggetto trackingIds corrente viene visualizzato con `mdatp threat list` .

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Informazioni sul portale di Microsoft Defender for Endpoint

[Le funzionalità EDR per macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)sono ora disponibili nel blog di Microsoft Defender for Endpoint e forniscono indicazioni dettagliate su cosa aspettarsi in Microsoft Defender for Endpoint Security Center.
