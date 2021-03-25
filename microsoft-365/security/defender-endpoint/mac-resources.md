---
title: Risorse per Microsoft Defender ATP per Mac
description: Risorse per Microsoft Defender ATP per Mac, tra cui come disinstallarlo, come raccogliere log di diagnostica, comandi CLI e problemi noti con il prodotto.
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
ms.openlocfilehash: 336f85b41884a441d0967c7f242b69c4d0e4941f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064114"
---
# <a name="resources-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="61111-104">Risorse per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="61111-104">Resources for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61111-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="61111-105">**Applies to:**</span></span>
- [<span data-ttu-id="61111-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="61111-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="61111-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61111-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="61111-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="61111-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="61111-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="61111-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="61111-110">Raccolta di informazioni di diagnostica</span><span class="sxs-lookup"><span data-stu-id="61111-110">Collecting diagnostic information</span></span>

<span data-ttu-id="61111-111">Se è possibile riprodurre un problema, aumentare il livello di registrazione, eseguire il sistema per un certo periodo di tempo e ripristinare il livello di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="61111-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="61111-112">Aumentare il livello di registrazione:</span><span class="sxs-lookup"><span data-stu-id="61111-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="61111-113">Riprodurre il problema</span><span class="sxs-lookup"><span data-stu-id="61111-113">Reproduce the problem</span></span>

3. <span data-ttu-id="61111-114">Eseguire `sudo mdatp diagnostic create` il backup dei log di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="61111-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="61111-115">I file verranno archiviati all'interno di un archivio ZIP.</span><span class="sxs-lookup"><span data-stu-id="61111-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="61111-116">Questo comando stamperà anche il percorso del file per il backup al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="61111-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="61111-117">Per impostazione predefinita, i log di diagnostica vengono salvati in `/Library/Application Support/Microsoft/Defender/wdavdiag/` .</span><span class="sxs-lookup"><span data-stu-id="61111-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="61111-118">Per modificare la directory in cui vengono salvati i log di diagnostica, passare `--path [directory]` al comando seguente, sostituendo `[directory]` con la directory desiderata.</span><span class="sxs-lookup"><span data-stu-id="61111-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="61111-119">Livello di registrazione ripristino:</span><span class="sxs-lookup"><span data-stu-id="61111-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="61111-120">Registrazione dei problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="61111-120">Logging installation issues</span></span>

<span data-ttu-id="61111-121">Se si verifica un errore durante l'installazione, il programma di installazione segnala solo un errore generale.</span><span class="sxs-lookup"><span data-stu-id="61111-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="61111-122">Il registro dettagliato verrà salvato in `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="61111-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="61111-123">Se si verificano problemi durante l'installazione, inviare questo file in modo da poter diagnosticare la causa.</span><span class="sxs-lookup"><span data-stu-id="61111-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="61111-124">Disinstallazione</span><span class="sxs-lookup"><span data-stu-id="61111-124">Uninstalling</span></span>

<span data-ttu-id="61111-125">Esistono diversi modi per disinstallare Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="61111-125">There are several ways to uninstall Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="61111-126">Tieni presente che, anche se la disinstallazione gestita centralmente è disponibile in JAMF, non è ancora disponibile per Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="61111-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="61111-127">Disinstallazione interattiva</span><span class="sxs-lookup"><span data-stu-id="61111-127">Interactive uninstallation</span></span>

- <span data-ttu-id="61111-128">Aprire **Il Finder > Applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="61111-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="61111-129">Fai clic con il pulsante destro del mouse su **Microsoft Defender ATP > sposta nel Cestino.**</span><span class="sxs-lookup"><span data-stu-id="61111-129">Right click on **Microsoft Defender ATP > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="61111-130">Dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="61111-130">From the command line</span></span>

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="61111-131">Configurazione dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="61111-131">Configuring from the command line</span></span>

<span data-ttu-id="61111-132">Le attività importanti, ad esempio il controllo delle impostazioni del prodotto e l'attivazione di analisi su richiesta, possono essere eseguite dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="61111-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="61111-133">Gruppo</span><span class="sxs-lookup"><span data-stu-id="61111-133">Group</span></span>        |<span data-ttu-id="61111-134">Scenario</span><span class="sxs-lookup"><span data-stu-id="61111-134">Scenario</span></span>                                   |<span data-ttu-id="61111-135">Comando</span><span class="sxs-lookup"><span data-stu-id="61111-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="61111-136">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-136">Configuration</span></span>|<span data-ttu-id="61111-137">Attivare/disattivare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="61111-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="61111-138">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-138">Configuration</span></span>|<span data-ttu-id="61111-139">Attivare/disattivare la protezione cloud</span><span class="sxs-lookup"><span data-stu-id="61111-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="61111-140">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-140">Configuration</span></span>|<span data-ttu-id="61111-141">Attivare/disattivare la diagnostica del prodotto</span><span class="sxs-lookup"><span data-stu-id="61111-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="61111-142">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-142">Configuration</span></span>|<span data-ttu-id="61111-143">Attivare/disattivare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="61111-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="61111-144">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-144">Configuration</span></span>|<span data-ttu-id="61111-145">Aggiungere un nome di minaccia all'elenco delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="61111-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="61111-146">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-146">Configuration</span></span>|<span data-ttu-id="61111-147">Rimuovere un nome di minaccia dall'elenco delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="61111-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="61111-148">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-148">Configuration</span></span>|<span data-ttu-id="61111-149">Elencare tutti i nomi delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="61111-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="61111-150">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-150">Configuration</span></span>|<span data-ttu-id="61111-151">Attivare la protezione dei criteri di protezione dall'accesso di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="61111-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="61111-152">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-152">Configuration</span></span>|<span data-ttu-id="61111-153">Disattivare la protezione puA</span><span class="sxs-lookup"><span data-stu-id="61111-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="61111-154">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-154">Configuration</span></span>|<span data-ttu-id="61111-155">Attivare la modalità di controllo per la protezione delle informazioni di accesso utente</span><span class="sxs-lookup"><span data-stu-id="61111-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="61111-156">Configurazione</span><span class="sxs-lookup"><span data-stu-id="61111-156">Configuration</span></span>|<span data-ttu-id="61111-157">Attivare/disattivare passiveMode</span><span class="sxs-lookup"><span data-stu-id="61111-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="61111-158">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="61111-158">Diagnostics</span></span>  |<span data-ttu-id="61111-159">Modificare il livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="61111-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="61111-160">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="61111-160">Diagnostics</span></span>  |<span data-ttu-id="61111-161">Generare log di diagnostica</span><span class="sxs-lookup"><span data-stu-id="61111-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="61111-162">Sanità</span><span class="sxs-lookup"><span data-stu-id="61111-162">Health</span></span>       |<span data-ttu-id="61111-163">Verificare l'integrità del prodotto</span><span class="sxs-lookup"><span data-stu-id="61111-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="61111-164">Sanità</span><span class="sxs-lookup"><span data-stu-id="61111-164">Health</span></span>       |<span data-ttu-id="61111-165">Verificare la presenza di un attributo del prodotto specifico</span><span class="sxs-lookup"><span data-stu-id="61111-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="61111-166">Protezione</span><span class="sxs-lookup"><span data-stu-id="61111-166">Protection</span></span>   |<span data-ttu-id="61111-167">Analizzare un percorso</span><span class="sxs-lookup"><span data-stu-id="61111-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="61111-168">Protezione</span><span class="sxs-lookup"><span data-stu-id="61111-168">Protection</span></span>   |<span data-ttu-id="61111-169">Eseguire un'analisi rapida</span><span class="sxs-lookup"><span data-stu-id="61111-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="61111-170">Protezione</span><span class="sxs-lookup"><span data-stu-id="61111-170">Protection</span></span>   |<span data-ttu-id="61111-171">Eseguire un'analisi completa</span><span class="sxs-lookup"><span data-stu-id="61111-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="61111-172">Protezione</span><span class="sxs-lookup"><span data-stu-id="61111-172">Protection</span></span>   |<span data-ttu-id="61111-173">Annullare un'analisi su richiesta in corso</span><span class="sxs-lookup"><span data-stu-id="61111-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="61111-174">Protezione</span><span class="sxs-lookup"><span data-stu-id="61111-174">Protection</span></span>   |<span data-ttu-id="61111-175">Richiedere un aggiornamento di security intelligence</span><span class="sxs-lookup"><span data-stu-id="61111-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="61111-176">EDR</span><span class="sxs-lookup"><span data-stu-id="61111-176">EDR</span></span>          |<span data-ttu-id="61111-177">Aggiungi tag di gruppo al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="61111-177">Add group tag to device.</span></span> <span data-ttu-id="61111-178">I tag EDR vengono utilizzati per la gestione dei gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="61111-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="61111-179">Per ulteriori informazioni, visitare https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="61111-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="61111-180">EDR</span><span class="sxs-lookup"><span data-stu-id="61111-180">EDR</span></span>          |<span data-ttu-id="61111-181">Rimuovere il tag di gruppo dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="61111-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="61111-182">EDR</span><span class="sxs-lookup"><span data-stu-id="61111-182">EDR</span></span>          |<span data-ttu-id="61111-183">Aggiungere l'ID gruppo</span><span class="sxs-lookup"><span data-stu-id="61111-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="61111-184">Come abilitare il completamento automatico</span><span class="sxs-lookup"><span data-stu-id="61111-184">How to enable autocompletion</span></span>

<span data-ttu-id="61111-185">Per abilitare il completamento automatico in bash, eseguire il comando seguente e riavviare la sessione terminale:</span><span class="sxs-lookup"><span data-stu-id="61111-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="61111-186">Per abilitare il completamento automatico in zsh:</span><span class="sxs-lookup"><span data-stu-id="61111-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="61111-187">Controlla se la funzionalità di completamento automatico è abilitata nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="61111-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="61111-188">Se il comando precedente non produce alcun output, è possibile abilitare il completamento automatico utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="61111-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="61111-189">Eseguire i comandi seguenti per abilitare il completamento automatico per Microsoft Defender per Endpoint per Mac e riavviare la sessione terminal:</span><span class="sxs-lookup"><span data-stu-id="61111-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint for Mac and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="61111-190">Client Microsoft Defender for Endpoint quarantine directory</span><span class="sxs-lookup"><span data-stu-id="61111-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="61111-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contiene i file messi in quarantena da `mdatp` .</span><span class="sxs-lookup"><span data-stu-id="61111-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="61111-192">I file sono denominati in base al trackingId delle minacce.</span><span class="sxs-lookup"><span data-stu-id="61111-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="61111-193">L'oggetto trackingIds corrente viene visualizzato con `mdatp threat list` .</span><span class="sxs-lookup"><span data-stu-id="61111-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="61111-194">Informazioni sul portale di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61111-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="61111-195">[Le funzionalità EDR per macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)sono ora disponibili nel blog di Microsoft Defender for Endpoint e forniscono indicazioni dettagliate su cosa aspettarsi in Microsoft Defender for Endpoint Security Center.</span><span class="sxs-lookup"><span data-stu-id="61111-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>