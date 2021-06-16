---
title: Risorse di Microsoft Defender per Endpoint su Linux
ms.reviewer: ''
description: Descrive le risorse per Microsoft Defender per Endpoint su Linux, tra cui come disinstallarlo, come raccogliere log di diagnostica, comandi CLI e problemi noti con il prodotto.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installazione, distribuire, disinstallazione, pupazzo, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: aaf9c0a8eef4e050ca034d1aee69d24c5adb909d
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930368"
---
# <a name="resources"></a><span data-ttu-id="0fec1-104">Risorse</span><span class="sxs-lookup"><span data-stu-id="0fec1-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0fec1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0fec1-105">**Applies to:**</span></span>

- [<span data-ttu-id="0fec1-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0fec1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0fec1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0fec1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0fec1-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0fec1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0fec1-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0fec1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="0fec1-110">Raccogliere informazioni di diagnostica</span><span class="sxs-lookup"><span data-stu-id="0fec1-110">Collect diagnostic information</span></span>

<span data-ttu-id="0fec1-111">Se è possibile riprodurre un problema, aumentare innanzitutto il livello di registrazione, eseguire il sistema per un certo periodo di tempo e quindi ripristinare il livello di registrazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="0fec1-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="0fec1-112">Aumentare il livello di registrazione:</span><span class="sxs-lookup"><span data-stu-id="0fec1-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="0fec1-113">Riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="0fec1-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="0fec1-114">Eseguire il comando seguente per eseguire il backup dei log di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0fec1-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="0fec1-115">I file verranno archiviati all'interno di un .zip archivio.</span><span class="sxs-lookup"><span data-stu-id="0fec1-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="0fec1-116">Questo comando stamperà anche il percorso del file di backup al termine dell'operazione:</span><span class="sxs-lookup"><span data-stu-id="0fec1-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="0fec1-117">Livello di registrazione ripristino:</span><span class="sxs-lookup"><span data-stu-id="0fec1-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="0fec1-118">Registrare i problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-118">Log installation issues</span></span>

<span data-ttu-id="0fec1-119">Se si verifica un errore durante l'installazione, il programma di installazione segnala solo un errore generale.</span><span class="sxs-lookup"><span data-stu-id="0fec1-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="0fec1-120">Il registro dettagliato verrà salvato in `/var/log/microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="0fec1-120">The detailed log will be saved to `/var/log/microsoft/mdatp/install.log`.</span></span>
<span data-ttu-id="0fec1-121">Se si verificano problemi durante l'installazione, inviare questo file in modo da poter diagnosticare la causa.</span><span class="sxs-lookup"><span data-stu-id="0fec1-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="0fec1-122">Disinstalla</span><span class="sxs-lookup"><span data-stu-id="0fec1-122">Uninstall</span></span>

<span data-ttu-id="0fec1-123">Esistono diversi modi per disinstallare Defender for Endpoint in Linux.</span><span class="sxs-lookup"><span data-stu-id="0fec1-123">There are several ways to uninstall Defender for Endpoint on Linux.</span></span> <span data-ttu-id="0fec1-124">Se stai usando uno strumento di configurazione come Puppet, segui le istruzioni per la disinstallazione del pacchetto per lo strumento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0fec1-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="0fec1-125">Disinstallazione manuale</span><span class="sxs-lookup"><span data-stu-id="0fec1-125">Manual uninstallation</span></span>

- <span data-ttu-id="0fec1-126">`sudo yum remove mdatp` per RHEL e variants(CentOS e Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="0fec1-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="0fec1-127">`sudo zypper remove mdatp` per SLES e varianti.</span><span class="sxs-lookup"><span data-stu-id="0fec1-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="0fec1-128">`sudo apt-get purge mdatp` per i sistemi Ubuntu e Debian.</span><span class="sxs-lookup"><span data-stu-id="0fec1-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="0fec1-129">Configurare dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="0fec1-129">Configure from the command line</span></span>

<span data-ttu-id="0fec1-130">Attività importanti, ad esempio il controllo delle impostazioni del prodotto e l'attivazione di analisi su richiesta, possono essere eseguite dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0fec1-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="0fec1-131">Opzioni globali</span><span class="sxs-lookup"><span data-stu-id="0fec1-131">Global options</span></span>

<span data-ttu-id="0fec1-132">Per impostazione predefinita, lo strumento da riga di comando restituisce il risultato in formato leggibile dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0fec1-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="0fec1-133">Inoltre, lo strumento supporta anche l'output del risultato come JSON, che è utile per gli scenari di automazione.</span><span class="sxs-lookup"><span data-stu-id="0fec1-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="0fec1-134">Per modificare l'output in JSON, passa `--output json` uno dei comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="0fec1-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="0fec1-135">Comandi supportati</span><span class="sxs-lookup"><span data-stu-id="0fec1-135">Supported commands</span></span>

<span data-ttu-id="0fec1-136">Nella tabella seguente sono elencati i comandi per alcuni degli scenari più comuni.</span><span class="sxs-lookup"><span data-stu-id="0fec1-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="0fec1-137">Eseguire `mdatp help` dal terminale per visualizzare l'elenco completo dei comandi supportati.</span><span class="sxs-lookup"><span data-stu-id="0fec1-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="0fec1-138">Gruppo</span><span class="sxs-lookup"><span data-stu-id="0fec1-138">Group</span></span>                 |<span data-ttu-id="0fec1-139">Scenario</span><span class="sxs-lookup"><span data-stu-id="0fec1-139">Scenario</span></span>                                                |<span data-ttu-id="0fec1-140">Comando</span><span class="sxs-lookup"><span data-stu-id="0fec1-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="0fec1-141">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-141">Configuration</span></span>         |<span data-ttu-id="0fec1-142">Attivare/disattivare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="0fec1-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="0fec1-143">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-143">Configuration</span></span>         |<span data-ttu-id="0fec1-144">Attivare/disattivare il monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="0fec1-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]`
|<span data-ttu-id="0fec1-145">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-145">Configuration</span></span>         |<span data-ttu-id="0fec1-146">Attivare/disattivare la protezione cloud</span><span class="sxs-lookup"><span data-stu-id="0fec1-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="0fec1-147">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-147">Configuration</span></span>         |<span data-ttu-id="0fec1-148">Attivare/disattivare la diagnostica del prodotto</span><span class="sxs-lookup"><span data-stu-id="0fec1-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="0fec1-149">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-149">Configuration</span></span>         |<span data-ttu-id="0fec1-150">Attivare/disattivare l'invio automatico di esempi</span><span class="sxs-lookup"><span data-stu-id="0fec1-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="0fec1-151">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-151">Configuration</span></span>         |<span data-ttu-id="0fec1-152">Attivare/disattivare la modalità passiva AV</span><span class="sxs-lookup"><span data-stu-id="0fec1-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="0fec1-153">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-153">Configuration</span></span>         |<span data-ttu-id="0fec1-154">Aggiungere/rimuovere un'esclusione antivirus per un'estensione di file</span><span class="sxs-lookup"><span data-stu-id="0fec1-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="0fec1-155">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-155">Configuration</span></span>         |<span data-ttu-id="0fec1-156">Aggiungere/rimuovere un'esclusione antivirus per un file</span><span class="sxs-lookup"><span data-stu-id="0fec1-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="0fec1-157">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-157">Configuration</span></span>         |<span data-ttu-id="0fec1-158">Aggiungere/rimuovere un'esclusione antivirus per una directory</span><span class="sxs-lookup"><span data-stu-id="0fec1-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="0fec1-159">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-159">Configuration</span></span>         |<span data-ttu-id="0fec1-160">Aggiungere/rimuovere un'esclusione antivirus per un processo</span><span class="sxs-lookup"><span data-stu-id="0fec1-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="0fec1-161">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-161">Configuration</span></span>         |<span data-ttu-id="0fec1-162">Elencare tutte le esclusioni antivirus</span><span class="sxs-lookup"><span data-stu-id="0fec1-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="0fec1-163">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-163">Configuration</span></span>         |<span data-ttu-id="0fec1-164">Aggiungere un nome di minaccia all'elenco delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="0fec1-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="0fec1-165">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-165">Configuration</span></span>         |<span data-ttu-id="0fec1-166">Rimuovere un nome di minaccia dall'elenco delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="0fec1-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="0fec1-167">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-167">Configuration</span></span>         |<span data-ttu-id="0fec1-168">Elencare tutti i nomi delle minacce consentite</span><span class="sxs-lookup"><span data-stu-id="0fec1-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="0fec1-169">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-169">Configuration</span></span>         |<span data-ttu-id="0fec1-170">Attivare la protezione dei criteri di protezione dall'accesso di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0fec1-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="0fec1-171">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-171">Configuration</span></span>         |<span data-ttu-id="0fec1-172">Disattivare la protezione puA</span><span class="sxs-lookup"><span data-stu-id="0fec1-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="0fec1-173">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-173">Configuration</span></span>         |<span data-ttu-id="0fec1-174">Attivare la modalità di controllo per la protezione delle informazioni di accesso utente</span><span class="sxs-lookup"><span data-stu-id="0fec1-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="0fec1-175">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="0fec1-175">Diagnostics</span></span>           |<span data-ttu-id="0fec1-176">Modificare il livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="0fec1-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="0fec1-177">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="0fec1-177">Diagnostics</span></span>           |<span data-ttu-id="0fec1-178">Generare log di diagnostica</span><span class="sxs-lookup"><span data-stu-id="0fec1-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="0fec1-179">Sanità</span><span class="sxs-lookup"><span data-stu-id="0fec1-179">Health</span></span>                |<span data-ttu-id="0fec1-180">Verificare l'integrità del prodotto</span><span class="sxs-lookup"><span data-stu-id="0fec1-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="0fec1-181">Protezione</span><span class="sxs-lookup"><span data-stu-id="0fec1-181">Protection</span></span>            |<span data-ttu-id="0fec1-182">Analizzare un percorso</span><span class="sxs-lookup"><span data-stu-id="0fec1-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="0fec1-183">Protezione</span><span class="sxs-lookup"><span data-stu-id="0fec1-183">Protection</span></span>            |<span data-ttu-id="0fec1-184">Eseguire un'analisi rapida</span><span class="sxs-lookup"><span data-stu-id="0fec1-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="0fec1-185">Protezione</span><span class="sxs-lookup"><span data-stu-id="0fec1-185">Protection</span></span>            |<span data-ttu-id="0fec1-186">Eseguire un'analisi completa</span><span class="sxs-lookup"><span data-stu-id="0fec1-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="0fec1-187">Protezione</span><span class="sxs-lookup"><span data-stu-id="0fec1-187">Protection</span></span>            |<span data-ttu-id="0fec1-188">Annullare un'analisi su richiesta in corso</span><span class="sxs-lookup"><span data-stu-id="0fec1-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="0fec1-189">Protezione</span><span class="sxs-lookup"><span data-stu-id="0fec1-189">Protection</span></span>            |<span data-ttu-id="0fec1-190">Richiedere un aggiornamento di security intelligence</span><span class="sxs-lookup"><span data-stu-id="0fec1-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="0fec1-191">Cronologia protezione</span><span class="sxs-lookup"><span data-stu-id="0fec1-191">Protection history</span></span>    |<span data-ttu-id="0fec1-192">Stampare la cronologia di protezione completa</span><span class="sxs-lookup"><span data-stu-id="0fec1-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="0fec1-193">Cronologia protezione</span><span class="sxs-lookup"><span data-stu-id="0fec1-193">Protection history</span></span>    |<span data-ttu-id="0fec1-194">Ottenere dettagli sulle minacce</span><span class="sxs-lookup"><span data-stu-id="0fec1-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="0fec1-195">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-195">Quarantine management</span></span> |<span data-ttu-id="0fec1-196">Elencare tutti i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="0fec1-197">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-197">Quarantine management</span></span> |<span data-ttu-id="0fec1-198">Rimuovere tutti i file dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="0fec1-199">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-199">Quarantine management</span></span> |<span data-ttu-id="0fec1-200">Aggiungere un file rilevato come minaccia alla quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="0fec1-201">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-201">Quarantine management</span></span> |<span data-ttu-id="0fec1-202">Rimuovere un file rilevato come minaccia dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="0fec1-203">Gestione della quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-203">Quarantine management</span></span> |<span data-ttu-id="0fec1-204">Ripristinare un file dalla quarantena</span><span class="sxs-lookup"><span data-stu-id="0fec1-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="0fec1-205">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="0fec1-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="0fec1-206">Impostare l'anteprima anticipata (inutilizzata)</span><span class="sxs-lookup"><span data-stu-id="0fec1-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="0fec1-207">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="0fec1-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="0fec1-208">Set group-id</span><span class="sxs-lookup"><span data-stu-id="0fec1-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="0fec1-209">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="0fec1-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="0fec1-210">Tag Set/Remove, supportato `GROUP` solo</span><span class="sxs-lookup"><span data-stu-id="0fec1-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="0fec1-211">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="0fec1-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="0fec1-212">esclusioni elenco (radice)</span><span class="sxs-lookup"><span data-stu-id="0fec1-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="0fec1-213">Informazioni sul portale di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0fec1-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="0fec1-214">Nel portale defender per endpoint vedrai due categorie di informazioni:</span><span class="sxs-lookup"><span data-stu-id="0fec1-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="0fec1-215">Avvisi antivirus, tra cui:</span><span class="sxs-lookup"><span data-stu-id="0fec1-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="0fec1-216">Gravità</span><span class="sxs-lookup"><span data-stu-id="0fec1-216">Severity</span></span>
  - <span data-ttu-id="0fec1-217">Tipo di analisi</span><span class="sxs-lookup"><span data-stu-id="0fec1-217">Scan type</span></span>
  - <span data-ttu-id="0fec1-218">Informazioni sul dispositivo (nome host, identificatore dispositivo, identificatore tenant, versione dell'app e tipo di sistema operativo)</span><span class="sxs-lookup"><span data-stu-id="0fec1-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="0fec1-219">Informazioni sui file (nome, percorso, dimensioni e hash)</span><span class="sxs-lookup"><span data-stu-id="0fec1-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="0fec1-220">Informazioni sulle minacce (nome, tipo e stato)</span><span class="sxs-lookup"><span data-stu-id="0fec1-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="0fec1-221">Informazioni sul dispositivo, tra cui:</span><span class="sxs-lookup"><span data-stu-id="0fec1-221">Device information, including:</span></span>
  - <span data-ttu-id="0fec1-222">Identificatore dispositivo</span><span class="sxs-lookup"><span data-stu-id="0fec1-222">Device identifier</span></span>
  - <span data-ttu-id="0fec1-223">Identificatore tenant</span><span class="sxs-lookup"><span data-stu-id="0fec1-223">Tenant identifier</span></span>
  - <span data-ttu-id="0fec1-224">Versione dell'app</span><span class="sxs-lookup"><span data-stu-id="0fec1-224">App version</span></span>
  - <span data-ttu-id="0fec1-225">Nome host</span><span class="sxs-lookup"><span data-stu-id="0fec1-225">Hostname</span></span>
  - <span data-ttu-id="0fec1-226">Tipo di sistema operativo</span><span class="sxs-lookup"><span data-stu-id="0fec1-226">OS type</span></span>
  - <span data-ttu-id="0fec1-227">Versione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="0fec1-227">OS version</span></span>
  - <span data-ttu-id="0fec1-228">Modello di computer</span><span class="sxs-lookup"><span data-stu-id="0fec1-228">Computer model</span></span>
  - <span data-ttu-id="0fec1-229">Architettura del processore</span><span class="sxs-lookup"><span data-stu-id="0fec1-229">Processor architecture</span></span>
  - <span data-ttu-id="0fec1-230">Indica se il dispositivo è una macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="0fec1-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="0fec1-231">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="0fec1-231">Known issues</span></span>

- <span data-ttu-id="0fec1-232">Nella pagina delle informazioni del computer del portale di Microsoft Defender Security Center potrebbe essere visualizzato "Nessun dato sensore, comunicazioni compromesse" anche se il prodotto funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="0fec1-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="0fec1-233">Stiamo lavorando per risolvere questo problema.</span><span class="sxs-lookup"><span data-stu-id="0fec1-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="0fec1-234">Gli utenti connessi non vengono visualizzati nel Microsoft Defender Security Center portale.</span><span class="sxs-lookup"><span data-stu-id="0fec1-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="0fec1-235">Nelle distribuzioni SUSE, se l'installazione di *libatomic1* non riesce, è necessario verificare che il sistema operativo sia registrato:</span><span class="sxs-lookup"><span data-stu-id="0fec1-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
