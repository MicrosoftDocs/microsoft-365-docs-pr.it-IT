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
ms.openlocfilehash: 7196053ffef3dffc3c737d0df26a5d12bdfe8a4c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187758"
---
# <a name="resources"></a><span data-ttu-id="41440-104">Risorse</span><span class="sxs-lookup"><span data-stu-id="41440-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="41440-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="41440-105">**Applies to:**</span></span>
- [<span data-ttu-id="41440-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="41440-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41440-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41440-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="41440-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="41440-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="41440-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="41440-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="41440-110">Raccogliere informazioni di diagnostica</span><span class="sxs-lookup"><span data-stu-id="41440-110">Collect diagnostic information</span></span>

<span data-ttu-id="41440-111">Se è possibile riprodurre un problema, aumentare innanzitutto il livello di registrazione, eseguire il sistema per un certo periodo di tempo e quindi ripristinare il livello di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="41440-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="41440-112">Aumentare il livello di registrazione:</span><span class="sxs-lookup"><span data-stu-id="41440-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="41440-113">Riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="41440-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="41440-114">Eseguire il comando seguente per eseguire il backup dei log di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="41440-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="41440-115">I file verranno archiviati all'interno di un archivio ZIP.</span><span class="sxs-lookup"><span data-stu-id="41440-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="41440-116">Questo comando stamperà anche il percorso del file di backup al termine dell'operazione:</span><span class="sxs-lookup"><span data-stu-id="41440-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="41440-117">Livello di registrazione ripristino:</span><span class="sxs-lookup"><span data-stu-id="41440-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="41440-118">Registrare i problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="41440-118">Log installation issues</span></span>

<span data-ttu-id="41440-119">Se si verifica un errore durante l'installazione, il programma di installazione segnala solo un errore generale.</span><span class="sxs-lookup"><span data-stu-id="41440-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="41440-120">Il registro dettagliato verrà salvato in `/var/log/microsoft/mdatp_install.log` .</span><span class="sxs-lookup"><span data-stu-id="41440-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="41440-121">Se si verificano problemi durante l'installazione, inviare questo file in modo da poter diagnosticare la causa.</span><span class="sxs-lookup"><span data-stu-id="41440-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="41440-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="41440-122">Uninstall</span></span>

<span data-ttu-id="41440-123">Esistono diversi modi per disinstallare Defender for Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="41440-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="41440-124">Se stai usando uno strumento di configurazione come Puppet, segui le istruzioni per la disinstallazione del pacchetto per lo strumento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="41440-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="41440-125">Disinstallazione manuale</span><span class="sxs-lookup"><span data-stu-id="41440-125">Manual uninstallation</span></span>

- <span data-ttu-id="41440-126">`sudo yum remove mdatp` per RHEL e variants(CentOS e Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="41440-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="41440-127">`sudo zypper remove mdatp` per SLES e varianti.</span><span class="sxs-lookup"><span data-stu-id="41440-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="41440-128">`sudo apt-get purge mdatp` per i sistemi Ubuntu e Debian.</span><span class="sxs-lookup"><span data-stu-id="41440-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="41440-129">Configurare dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="41440-129">Configure from the command line</span></span>

<span data-ttu-id="41440-130">Attività importanti, ad esempio il controllo delle impostazioni del prodotto e l'attivazione di analisi su richiesta, possono essere eseguite dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="41440-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="41440-131">Opzioni globali</span><span class="sxs-lookup"><span data-stu-id="41440-131">Global options</span></span>

<span data-ttu-id="41440-132">Per impostazione predefinita, lo strumento da riga di comando restituisce il risultato in formato leggibile dall'utente.</span><span class="sxs-lookup"><span data-stu-id="41440-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="41440-133">Inoltre, lo strumento supporta anche l'output del risultato come JSON, che è utile per gli scenari di automazione.</span><span class="sxs-lookup"><span data-stu-id="41440-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="41440-134">Per modificare l'output in JSON, passa `--output json` uno dei comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="41440-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="41440-135">Comandi supportati</span><span class="sxs-lookup"><span data-stu-id="41440-135">Supported commands</span></span>

<span data-ttu-id="41440-136">Nella tabella seguente sono elencati i comandi per alcuni degli scenari più comuni.</span><span class="sxs-lookup"><span data-stu-id="41440-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="41440-137">Eseguire `mdatp help` dal terminale per visualizzare l'elenco completo dei comandi supportati.</span><span class="sxs-lookup"><span data-stu-id="41440-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="41440-138">Gruppo</span><span class="sxs-lookup"><span data-stu-id="41440-138">Group</span></span>                 |<span data-ttu-id="41440-139">Scenario</span><span class="sxs-lookup"><span data-stu-id="41440-139">Scenario</span></span>                                                |<span data-ttu-id="41440-140">Comando</span><span class="sxs-lookup"><span data-stu-id="41440-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="41440-141">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-141">Configuration</span></span>         |<span data-ttu-id="41440-142">Attivare/disattivare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="41440-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="41440-143">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-143">Configuration</span></span>         |<span data-ttu-id="41440-144">Attivare/disattivare la protezione cloud</span><span class="sxs-lookup"><span data-stu-id="41440-144">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="41440-145">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-145">Configuration</span></span>         |<span data-ttu-id="41440-146">Attivare/disattivare la diagnostica del prodotto</span><span class="sxs-lookup"><span data-stu-id="41440-146">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="41440-147">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-147">Configuration</span></span>         |<span data-ttu-id="41440-148">Attivare/disattivare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="41440-148">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="41440-149">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-149">Configuration</span></span>         |<span data-ttu-id="41440-150">Attivare/disattivare la modalità passiva AV</span><span class="sxs-lookup"><span data-stu-id="41440-150">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="41440-151">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-151">Configuration</span></span>         |<span data-ttu-id="41440-152">Aggiungere/rimuovere un'esclusione antivirus per un'estensione di file</span><span class="sxs-lookup"><span data-stu-id="41440-152">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="41440-153">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-153">Configuration</span></span>         |<span data-ttu-id="41440-154">Aggiungere/rimuovere un'esclusione antivirus per un file</span><span class="sxs-lookup"><span data-stu-id="41440-154">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="41440-155">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-155">Configuration</span></span>         |<span data-ttu-id="41440-156">Aggiungere/rimuovere un'esclusione antivirus per una directory</span><span class="sxs-lookup"><span data-stu-id="41440-156">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="41440-157">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-157">Configuration</span></span>         |<span data-ttu-id="41440-158">Aggiungere/rimuovere un'esclusione antivirus per un processo</span><span class="sxs-lookup"><span data-stu-id="41440-158">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="41440-159">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-159">Configuration</span></span>         |<span data-ttu-id="41440-160">Elencare tutte le esclusioni antivirus</span><span class="sxs-lookup"><span data-stu-id="41440-160">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="41440-161">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-161">Configuration</span></span>         |<span data-ttu-id="41440-162">Aggiungere un nome di minaccia all'elenco delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="41440-162">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="41440-163">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-163">Configuration</span></span>         |<span data-ttu-id="41440-164">Rimuovere un nome di minaccia dall'elenco delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="41440-164">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="41440-165">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-165">Configuration</span></span>         |<span data-ttu-id="41440-166">Elencare tutti i nomi delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="41440-166">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="41440-167">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-167">Configuration</span></span>         |<span data-ttu-id="41440-168">Attivare la protezione dei criteri di protezione dall'accesso di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="41440-168">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="41440-169">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-169">Configuration</span></span>         |<span data-ttu-id="41440-170">Disattivare la protezione puA</span><span class="sxs-lookup"><span data-stu-id="41440-170">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="41440-171">Configurazione</span><span class="sxs-lookup"><span data-stu-id="41440-171">Configuration</span></span>         |<span data-ttu-id="41440-172">Attivare la modalità di controllo per la protezione delle informazioni di accesso utente</span><span class="sxs-lookup"><span data-stu-id="41440-172">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="41440-173">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="41440-173">Diagnostics</span></span>           |<span data-ttu-id="41440-174">Modificare il livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="41440-174">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="41440-175">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="41440-175">Diagnostics</span></span>           |<span data-ttu-id="41440-176">Generare log di diagnostica</span><span class="sxs-lookup"><span data-stu-id="41440-176">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="41440-177">Sanità</span><span class="sxs-lookup"><span data-stu-id="41440-177">Health</span></span>                |<span data-ttu-id="41440-178">Verificare l'integrità del prodotto</span><span class="sxs-lookup"><span data-stu-id="41440-178">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="41440-179">Protezione</span><span class="sxs-lookup"><span data-stu-id="41440-179">Protection</span></span>            |<span data-ttu-id="41440-180">Analizzare un percorso</span><span class="sxs-lookup"><span data-stu-id="41440-180">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="41440-181">Protezione</span><span class="sxs-lookup"><span data-stu-id="41440-181">Protection</span></span>            |<span data-ttu-id="41440-182">Eseguire un'analisi rapida</span><span class="sxs-lookup"><span data-stu-id="41440-182">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="41440-183">Protezione</span><span class="sxs-lookup"><span data-stu-id="41440-183">Protection</span></span>            |<span data-ttu-id="41440-184">Eseguire un'analisi completa</span><span class="sxs-lookup"><span data-stu-id="41440-184">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="41440-185">Protezione</span><span class="sxs-lookup"><span data-stu-id="41440-185">Protection</span></span>            |<span data-ttu-id="41440-186">Annullare un'analisi su richiesta in corso</span><span class="sxs-lookup"><span data-stu-id="41440-186">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="41440-187">Protezione</span><span class="sxs-lookup"><span data-stu-id="41440-187">Protection</span></span>            |<span data-ttu-id="41440-188">Richiedere un aggiornamento di security intelligence</span><span class="sxs-lookup"><span data-stu-id="41440-188">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="41440-189">Cronologia protezione</span><span class="sxs-lookup"><span data-stu-id="41440-189">Protection history</span></span>    |<span data-ttu-id="41440-190">Stampare la cronologia di protezione completa</span><span class="sxs-lookup"><span data-stu-id="41440-190">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="41440-191">Cronologia protezione</span><span class="sxs-lookup"><span data-stu-id="41440-191">Protection history</span></span>    |<span data-ttu-id="41440-192">Ottenere dettagli sulle minacce</span><span class="sxs-lookup"><span data-stu-id="41440-192">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="41440-193">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-193">Quarantine management</span></span> |<span data-ttu-id="41440-194">Elencare tutti i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-194">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="41440-195">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-195">Quarantine management</span></span> |<span data-ttu-id="41440-196">Rimuovere tutti i file dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-196">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="41440-197">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-197">Quarantine management</span></span> |<span data-ttu-id="41440-198">Aggiungere un file rilevato come minaccia alla quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-198">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="41440-199">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-199">Quarantine management</span></span> |<span data-ttu-id="41440-200">Rimuovere un file rilevato come minaccia dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-200">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="41440-201">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-201">Quarantine management</span></span> |<span data-ttu-id="41440-202">Ripristinare un file dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="41440-202">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="41440-203">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="41440-203">Endpoint Detection and Response</span></span> |<span data-ttu-id="41440-204">Impostare l'anteprima anticipata (inutilizzata)</span><span class="sxs-lookup"><span data-stu-id="41440-204">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="41440-205">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="41440-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="41440-206">Set group-id</span><span class="sxs-lookup"><span data-stu-id="41440-206">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="41440-207">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="41440-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="41440-208">Tag Set/Remove, supportato `GROUP` solo</span><span class="sxs-lookup"><span data-stu-id="41440-208">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="41440-209">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="41440-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="41440-210">esclusioni elenco (radice)</span><span class="sxs-lookup"><span data-stu-id="41440-210">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="41440-211">Informazioni sul portale di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="41440-211">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="41440-212">Nel portale defender per endpoint vedrai due categorie di informazioni:</span><span class="sxs-lookup"><span data-stu-id="41440-212">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="41440-213">Avvisi antivirus, tra cui:</span><span class="sxs-lookup"><span data-stu-id="41440-213">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="41440-214">Gravità</span><span class="sxs-lookup"><span data-stu-id="41440-214">Severity</span></span>
  - <span data-ttu-id="41440-215">Tipo di analisi</span><span class="sxs-lookup"><span data-stu-id="41440-215">Scan type</span></span>
  - <span data-ttu-id="41440-216">Informazioni sul dispositivo (nome host, identificatore dispositivo, identificatore tenant, versione dell'app e tipo di sistema operativo)</span><span class="sxs-lookup"><span data-stu-id="41440-216">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="41440-217">Informazioni sui file (nome, percorso, dimensioni e hash)</span><span class="sxs-lookup"><span data-stu-id="41440-217">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="41440-218">Informazioni sulle minacce (nome, tipo e stato)</span><span class="sxs-lookup"><span data-stu-id="41440-218">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="41440-219">Informazioni sul dispositivo, tra cui:</span><span class="sxs-lookup"><span data-stu-id="41440-219">Device information, including:</span></span>
  - <span data-ttu-id="41440-220">Identificatore dispositivo</span><span class="sxs-lookup"><span data-stu-id="41440-220">Device identifier</span></span>
  - <span data-ttu-id="41440-221">Identificatore tenant</span><span class="sxs-lookup"><span data-stu-id="41440-221">Tenant identifier</span></span>
  - <span data-ttu-id="41440-222">Versione dell'app</span><span class="sxs-lookup"><span data-stu-id="41440-222">App version</span></span>
  - <span data-ttu-id="41440-223">Nome host</span><span class="sxs-lookup"><span data-stu-id="41440-223">Hostname</span></span>
  - <span data-ttu-id="41440-224">Tipo di sistema operativo</span><span class="sxs-lookup"><span data-stu-id="41440-224">OS type</span></span>
  - <span data-ttu-id="41440-225">Versione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="41440-225">OS version</span></span>
  - <span data-ttu-id="41440-226">Modello di computer</span><span class="sxs-lookup"><span data-stu-id="41440-226">Computer model</span></span>
  - <span data-ttu-id="41440-227">Architettura del processore</span><span class="sxs-lookup"><span data-stu-id="41440-227">Processor architecture</span></span>
  - <span data-ttu-id="41440-228">Indica se il dispositivo è una macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="41440-228">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="41440-229">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="41440-229">Known issues</span></span>

- <span data-ttu-id="41440-230">Potresti vedere "Nessun dato del sensore, comunicazioni compromesse" nella pagina delle informazioni sul computer del portale di Microsoft Defender Security Center, anche se il prodotto funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="41440-230">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="41440-231">Stiamo lavorando per risolvere questo problema.</span><span class="sxs-lookup"><span data-stu-id="41440-231">We are working on addressing this issue.</span></span>
- <span data-ttu-id="41440-232">Gli utenti connessi non vengono visualizzati nel portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="41440-232">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="41440-233">Nelle distribuzioni SUSE, se l'installazione di *libatomic1* non riesce, è necessario verificare che il sistema operativo sia registrato:</span><span class="sxs-lookup"><span data-stu-id="41440-233">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
