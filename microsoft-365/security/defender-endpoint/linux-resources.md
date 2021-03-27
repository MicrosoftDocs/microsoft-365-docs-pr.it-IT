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
# <a name="resources"></a><span data-ttu-id="71cc3-104">Risorse</span><span class="sxs-lookup"><span data-stu-id="71cc3-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="71cc3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="71cc3-105">**Applies to:**</span></span>
- [<span data-ttu-id="71cc3-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="71cc3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71cc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71cc3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="71cc3-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="71cc3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="71cc3-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="71cc3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="71cc3-110">Raccogliere informazioni di diagnostica</span><span class="sxs-lookup"><span data-stu-id="71cc3-110">Collect diagnostic information</span></span>

<span data-ttu-id="71cc3-111">Se è possibile riprodurre un problema, aumentare innanzitutto il livello di registrazione, eseguire il sistema per un certo periodo di tempo e quindi ripristinare il livello di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="71cc3-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="71cc3-112">Aumentare il livello di registrazione:</span><span class="sxs-lookup"><span data-stu-id="71cc3-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="71cc3-113">Riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="71cc3-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="71cc3-114">Eseguire il comando seguente per eseguire il backup dei log di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="71cc3-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="71cc3-115">I file verranno archiviati all'interno di un archivio ZIP.</span><span class="sxs-lookup"><span data-stu-id="71cc3-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="71cc3-116">Questo comando stamperà anche il percorso del file di backup al termine dell'operazione:</span><span class="sxs-lookup"><span data-stu-id="71cc3-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="71cc3-117">Livello di registrazione ripristino:</span><span class="sxs-lookup"><span data-stu-id="71cc3-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="71cc3-118">Registrare i problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-118">Log installation issues</span></span>

<span data-ttu-id="71cc3-119">Se si verifica un errore durante l'installazione, il programma di installazione segnala solo un errore generale.</span><span class="sxs-lookup"><span data-stu-id="71cc3-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="71cc3-120">Il registro dettagliato verrà salvato in `/var/log/microsoft/mdatp_install.log` .</span><span class="sxs-lookup"><span data-stu-id="71cc3-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="71cc3-121">Se si verificano problemi durante l'installazione, inviare questo file in modo da poter diagnosticare la causa.</span><span class="sxs-lookup"><span data-stu-id="71cc3-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="71cc3-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="71cc3-122">Uninstall</span></span>

<span data-ttu-id="71cc3-123">Esistono diversi modi per disinstallare Defender for Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="71cc3-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="71cc3-124">Se stai usando uno strumento di configurazione come Puppet, segui le istruzioni per la disinstallazione del pacchetto per lo strumento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="71cc3-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="71cc3-125">Disinstallazione manuale</span><span class="sxs-lookup"><span data-stu-id="71cc3-125">Manual uninstallation</span></span>

- <span data-ttu-id="71cc3-126">`sudo yum remove mdatp` per RHEL e variants(CentOS e Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="71cc3-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="71cc3-127">`sudo zypper remove mdatp` per SLES e varianti.</span><span class="sxs-lookup"><span data-stu-id="71cc3-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="71cc3-128">`sudo apt-get purge mdatp` per i sistemi Ubuntu e Debian.</span><span class="sxs-lookup"><span data-stu-id="71cc3-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="71cc3-129">Configurare dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="71cc3-129">Configure from the command line</span></span>

<span data-ttu-id="71cc3-130">Attività importanti, ad esempio il controllo delle impostazioni del prodotto e l'attivazione di analisi su richiesta, possono essere eseguite dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="71cc3-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="71cc3-131">Opzioni globali</span><span class="sxs-lookup"><span data-stu-id="71cc3-131">Global options</span></span>

<span data-ttu-id="71cc3-132">Per impostazione predefinita, lo strumento da riga di comando restituisce il risultato in formato leggibile dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71cc3-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="71cc3-133">Inoltre, lo strumento supporta anche l'output del risultato come JSON, che è utile per gli scenari di automazione.</span><span class="sxs-lookup"><span data-stu-id="71cc3-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="71cc3-134">Per modificare l'output in JSON, passa `--output json` uno dei comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="71cc3-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="71cc3-135">Comandi supportati</span><span class="sxs-lookup"><span data-stu-id="71cc3-135">Supported commands</span></span>

<span data-ttu-id="71cc3-136">Nella tabella seguente sono elencati i comandi per alcuni degli scenari più comuni.</span><span class="sxs-lookup"><span data-stu-id="71cc3-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="71cc3-137">Eseguire `mdatp help` dal terminale per visualizzare l'elenco completo dei comandi supportati.</span><span class="sxs-lookup"><span data-stu-id="71cc3-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="71cc3-138">Gruppo</span><span class="sxs-lookup"><span data-stu-id="71cc3-138">Group</span></span>                 |<span data-ttu-id="71cc3-139">Scenario</span><span class="sxs-lookup"><span data-stu-id="71cc3-139">Scenario</span></span>                                                |<span data-ttu-id="71cc3-140">Comando</span><span class="sxs-lookup"><span data-stu-id="71cc3-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="71cc3-141">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-141">Configuration</span></span>         |<span data-ttu-id="71cc3-142">Attivare/disattivare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="71cc3-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="71cc3-143">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-143">Configuration</span></span>         |<span data-ttu-id="71cc3-144">Attivare/disattivare il monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="71cc3-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|<span data-ttu-id="71cc3-145">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-145">Configuration</span></span>         |<span data-ttu-id="71cc3-146">Attivare/disattivare la protezione cloud</span><span class="sxs-lookup"><span data-stu-id="71cc3-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="71cc3-147">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-147">Configuration</span></span>         |<span data-ttu-id="71cc3-148">Attivare/disattivare la diagnostica del prodotto</span><span class="sxs-lookup"><span data-stu-id="71cc3-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="71cc3-149">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-149">Configuration</span></span>         |<span data-ttu-id="71cc3-150">Attivare/disattivare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="71cc3-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="71cc3-151">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-151">Configuration</span></span>         |<span data-ttu-id="71cc3-152">Attivare/disattivare la modalità passiva AV</span><span class="sxs-lookup"><span data-stu-id="71cc3-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="71cc3-153">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-153">Configuration</span></span>         |<span data-ttu-id="71cc3-154">Aggiungere/rimuovere un'esclusione antivirus per un'estensione di file</span><span class="sxs-lookup"><span data-stu-id="71cc3-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="71cc3-155">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-155">Configuration</span></span>         |<span data-ttu-id="71cc3-156">Aggiungere/rimuovere un'esclusione antivirus per un file</span><span class="sxs-lookup"><span data-stu-id="71cc3-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="71cc3-157">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-157">Configuration</span></span>         |<span data-ttu-id="71cc3-158">Aggiungere/rimuovere un'esclusione antivirus per una directory</span><span class="sxs-lookup"><span data-stu-id="71cc3-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="71cc3-159">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-159">Configuration</span></span>         |<span data-ttu-id="71cc3-160">Aggiungere/rimuovere un'esclusione antivirus per un processo</span><span class="sxs-lookup"><span data-stu-id="71cc3-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="71cc3-161">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-161">Configuration</span></span>         |<span data-ttu-id="71cc3-162">Elencare tutte le esclusioni antivirus</span><span class="sxs-lookup"><span data-stu-id="71cc3-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="71cc3-163">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-163">Configuration</span></span>         |<span data-ttu-id="71cc3-164">Aggiungere un nome di minaccia all'elenco delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="71cc3-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="71cc3-165">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-165">Configuration</span></span>         |<span data-ttu-id="71cc3-166">Rimuovere un nome di minaccia dall'elenco delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="71cc3-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="71cc3-167">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-167">Configuration</span></span>         |<span data-ttu-id="71cc3-168">Elencare tutti i nomi delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="71cc3-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="71cc3-169">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-169">Configuration</span></span>         |<span data-ttu-id="71cc3-170">Attivare la protezione dei criteri di protezione dall'accesso di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="71cc3-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="71cc3-171">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-171">Configuration</span></span>         |<span data-ttu-id="71cc3-172">Disattivare la protezione puA</span><span class="sxs-lookup"><span data-stu-id="71cc3-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="71cc3-173">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-173">Configuration</span></span>         |<span data-ttu-id="71cc3-174">Attivare la modalità di controllo per la protezione delle informazioni di accesso utente</span><span class="sxs-lookup"><span data-stu-id="71cc3-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="71cc3-175">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="71cc3-175">Diagnostics</span></span>           |<span data-ttu-id="71cc3-176">Modificare il livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="71cc3-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="71cc3-177">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="71cc3-177">Diagnostics</span></span>           |<span data-ttu-id="71cc3-178">Generare log di diagnostica</span><span class="sxs-lookup"><span data-stu-id="71cc3-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="71cc3-179">Sanità</span><span class="sxs-lookup"><span data-stu-id="71cc3-179">Health</span></span>                |<span data-ttu-id="71cc3-180">Verificare l'integrità del prodotto</span><span class="sxs-lookup"><span data-stu-id="71cc3-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="71cc3-181">Protezione</span><span class="sxs-lookup"><span data-stu-id="71cc3-181">Protection</span></span>            |<span data-ttu-id="71cc3-182">Analizzare un percorso</span><span class="sxs-lookup"><span data-stu-id="71cc3-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="71cc3-183">Protezione</span><span class="sxs-lookup"><span data-stu-id="71cc3-183">Protection</span></span>            |<span data-ttu-id="71cc3-184">Eseguire un'analisi rapida</span><span class="sxs-lookup"><span data-stu-id="71cc3-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="71cc3-185">Protezione</span><span class="sxs-lookup"><span data-stu-id="71cc3-185">Protection</span></span>            |<span data-ttu-id="71cc3-186">Eseguire un'analisi completa</span><span class="sxs-lookup"><span data-stu-id="71cc3-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="71cc3-187">Protezione</span><span class="sxs-lookup"><span data-stu-id="71cc3-187">Protection</span></span>            |<span data-ttu-id="71cc3-188">Annullare un'analisi su richiesta in corso</span><span class="sxs-lookup"><span data-stu-id="71cc3-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="71cc3-189">Protezione</span><span class="sxs-lookup"><span data-stu-id="71cc3-189">Protection</span></span>            |<span data-ttu-id="71cc3-190">Richiedere un aggiornamento di security intelligence</span><span class="sxs-lookup"><span data-stu-id="71cc3-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="71cc3-191">Cronologia protezione</span><span class="sxs-lookup"><span data-stu-id="71cc3-191">Protection history</span></span>    |<span data-ttu-id="71cc3-192">Stampare la cronologia di protezione completa</span><span class="sxs-lookup"><span data-stu-id="71cc3-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="71cc3-193">Cronologia protezione</span><span class="sxs-lookup"><span data-stu-id="71cc3-193">Protection history</span></span>    |<span data-ttu-id="71cc3-194">Ottenere dettagli sulle minacce</span><span class="sxs-lookup"><span data-stu-id="71cc3-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="71cc3-195">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-195">Quarantine management</span></span> |<span data-ttu-id="71cc3-196">Elencare tutti i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="71cc3-197">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-197">Quarantine management</span></span> |<span data-ttu-id="71cc3-198">Rimuovere tutti i file dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="71cc3-199">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-199">Quarantine management</span></span> |<span data-ttu-id="71cc3-200">Aggiungere un file rilevato come minaccia alla quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="71cc3-201">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-201">Quarantine management</span></span> |<span data-ttu-id="71cc3-202">Rimuovere un file rilevato come minaccia dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="71cc3-203">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-203">Quarantine management</span></span> |<span data-ttu-id="71cc3-204">Ripristinare un file dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="71cc3-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="71cc3-205">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="71cc3-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="71cc3-206">Impostare l'anteprima anticipata (inutilizzata)</span><span class="sxs-lookup"><span data-stu-id="71cc3-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="71cc3-207">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="71cc3-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="71cc3-208">Set group-id</span><span class="sxs-lookup"><span data-stu-id="71cc3-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="71cc3-209">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="71cc3-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="71cc3-210">Tag Set/Remove, supportato `GROUP` solo</span><span class="sxs-lookup"><span data-stu-id="71cc3-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="71cc3-211">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="71cc3-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="71cc3-212">esclusioni elenco (radice)</span><span class="sxs-lookup"><span data-stu-id="71cc3-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="71cc3-213">Informazioni sul portale di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="71cc3-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="71cc3-214">Nel portale defender per endpoint vedrai due categorie di informazioni:</span><span class="sxs-lookup"><span data-stu-id="71cc3-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="71cc3-215">Avvisi antivirus, tra cui:</span><span class="sxs-lookup"><span data-stu-id="71cc3-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="71cc3-216">Gravità</span><span class="sxs-lookup"><span data-stu-id="71cc3-216">Severity</span></span>
  - <span data-ttu-id="71cc3-217">Tipo di analisi</span><span class="sxs-lookup"><span data-stu-id="71cc3-217">Scan type</span></span>
  - <span data-ttu-id="71cc3-218">Informazioni sul dispositivo (nome host, identificatore dispositivo, identificatore tenant, versione dell'app e tipo di sistema operativo)</span><span class="sxs-lookup"><span data-stu-id="71cc3-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="71cc3-219">Informazioni sui file (nome, percorso, dimensioni e hash)</span><span class="sxs-lookup"><span data-stu-id="71cc3-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="71cc3-220">Informazioni sulle minacce (nome, tipo e stato)</span><span class="sxs-lookup"><span data-stu-id="71cc3-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="71cc3-221">Informazioni sul dispositivo, tra cui:</span><span class="sxs-lookup"><span data-stu-id="71cc3-221">Device information, including:</span></span>
  - <span data-ttu-id="71cc3-222">Identificatore dispositivo</span><span class="sxs-lookup"><span data-stu-id="71cc3-222">Device identifier</span></span>
  - <span data-ttu-id="71cc3-223">Identificatore tenant</span><span class="sxs-lookup"><span data-stu-id="71cc3-223">Tenant identifier</span></span>
  - <span data-ttu-id="71cc3-224">Versione dell'app</span><span class="sxs-lookup"><span data-stu-id="71cc3-224">App version</span></span>
  - <span data-ttu-id="71cc3-225">Nome host</span><span class="sxs-lookup"><span data-stu-id="71cc3-225">Hostname</span></span>
  - <span data-ttu-id="71cc3-226">Tipo di sistema operativo</span><span class="sxs-lookup"><span data-stu-id="71cc3-226">OS type</span></span>
  - <span data-ttu-id="71cc3-227">Versione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="71cc3-227">OS version</span></span>
  - <span data-ttu-id="71cc3-228">Modello di computer</span><span class="sxs-lookup"><span data-stu-id="71cc3-228">Computer model</span></span>
  - <span data-ttu-id="71cc3-229">Architettura del processore</span><span class="sxs-lookup"><span data-stu-id="71cc3-229">Processor architecture</span></span>
  - <span data-ttu-id="71cc3-230">Indica se il dispositivo è una macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="71cc3-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="71cc3-231">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="71cc3-231">Known issues</span></span>

- <span data-ttu-id="71cc3-232">Potresti vedere "Nessun dato del sensore, comunicazioni compromesse" nella pagina delle informazioni sul computer del portale di Microsoft Defender Security Center, anche se il prodotto funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="71cc3-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="71cc3-233">Stiamo lavorando per risolvere questo problema.</span><span class="sxs-lookup"><span data-stu-id="71cc3-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="71cc3-234">Gli utenti connessi non vengono visualizzati nel portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="71cc3-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="71cc3-235">Nelle distribuzioni SUSE, se l'installazione di *libatomic1* non riesce, è necessario verificare che il sistema operativo sia registrato:</span><span class="sxs-lookup"><span data-stu-id="71cc3-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
