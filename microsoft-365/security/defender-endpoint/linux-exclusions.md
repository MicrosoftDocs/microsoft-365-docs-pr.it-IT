---
title: Configurare e convalidare le esclusioni per Microsoft Defender ATP per Linux
description: Fornire e convalidare le esclusioni per Microsoft Defender ATP per Linux. È possibile impostare esclusioni per file, cartelle e processi.
keywords: microsoft, defender, atp, linux, esclusioni, analisi, antivirus
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
ms.openlocfilehash: fa2d643936b8358649bf59eec3ab9570cb561419
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064261"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="67646-105">Configurare e convalidare le esclusioni per Microsoft Defender for Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="67646-105">Configure and validate exclusions for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67646-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="67646-106">**Applies to:**</span></span>
- [<span data-ttu-id="67646-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="67646-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="67646-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67646-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67646-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="67646-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="67646-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="67646-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="67646-111">In questo articolo vengono fornite informazioni su come definire le esclusioni applicabili alle analisi su richiesta e sulla protezione e il monitoraggio in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="67646-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67646-112">Le esclusioni descritte in questo articolo non si applicano ad altre funzionalità di Defender for Endpoint per Linux, tra cui il rilevamento e la risposta degli endpoint (EDR).</span><span class="sxs-lookup"><span data-stu-id="67646-112">The exclusions described in this article don't apply to other Defender for Endpoint for Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="67646-113">I file esclusi utilizzando i metodi descritti in questo articolo possono comunque attivare avvisi EDR e altri rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="67646-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="67646-114">Puoi escludere determinati file, cartelle, processi e file aperti dal processo da analisi di Defender for Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="67646-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Linux scans.</span></span>

<span data-ttu-id="67646-115">Le esclusioni possono essere utili per evitare rilevamenti non corretti su file o software univoci o personalizzati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="67646-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="67646-116">Possono anche essere utili per ridurre i problemi di prestazioni causati da Defender per Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="67646-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="67646-117">La definizione delle esclusioni riduce la protezione offerta da Defender per Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="67646-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Linux.</span></span> <span data-ttu-id="67646-118">È consigliabile valutare sempre i rischi associati all'implementazione delle esclusioni e escludere solo i file che si è certi non siano dannosi.</span><span class="sxs-lookup"><span data-stu-id="67646-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="67646-119">Tipi di esclusione supportati</span><span class="sxs-lookup"><span data-stu-id="67646-119">Supported exclusion types</span></span>

<span data-ttu-id="67646-120">La tabella seguente mostra i tipi di esclusione supportati da Defender per Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="67646-120">The follow table shows the exclusion types supported by Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="67646-121">Esclusione</span><span class="sxs-lookup"><span data-stu-id="67646-121">Exclusion</span></span> | <span data-ttu-id="67646-122">Definizione</span><span class="sxs-lookup"><span data-stu-id="67646-122">Definition</span></span> | <span data-ttu-id="67646-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="67646-123">Examples</span></span>
---|---|---
<span data-ttu-id="67646-124">Estensione del file</span><span class="sxs-lookup"><span data-stu-id="67646-124">File extension</span></span> | <span data-ttu-id="67646-125">Tutti i file con estensione, ovunque nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="67646-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="67646-126">File</span><span class="sxs-lookup"><span data-stu-id="67646-126">File</span></span> | <span data-ttu-id="67646-127">Un file specifico identificato dal percorso completo</span><span class="sxs-lookup"><span data-stu-id="67646-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="67646-128">Cartella</span><span class="sxs-lookup"><span data-stu-id="67646-128">Folder</span></span> | <span data-ttu-id="67646-129">Tutti i file nella cartella specificata (in modo ricorsivo)</span><span class="sxs-lookup"><span data-stu-id="67646-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="67646-130">Processo</span><span class="sxs-lookup"><span data-stu-id="67646-130">Process</span></span> | <span data-ttu-id="67646-131">Un processo specifico (specificato dal percorso completo o dal nome del file) e tutti i file aperti da esso</span><span class="sxs-lookup"><span data-stu-id="67646-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="67646-132">I percorsi precedenti devono essere collegamenti rigidi, non collegamenti simbolici, per essere esclusi correttamente.</span><span class="sxs-lookup"><span data-stu-id="67646-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="67646-133">È possibile verificare se un percorso è un collegamento simbolico eseguendo `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="67646-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="67646-134">Le esclusioni di file, cartelle e processi supportano i caratteri jolly seguenti:</span><span class="sxs-lookup"><span data-stu-id="67646-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="67646-135">Carattere jolly</span><span class="sxs-lookup"><span data-stu-id="67646-135">Wildcard</span></span> | <span data-ttu-id="67646-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67646-136">Description</span></span> | <span data-ttu-id="67646-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="67646-137">Example</span></span> | <span data-ttu-id="67646-138">Corrispondenze</span><span class="sxs-lookup"><span data-stu-id="67646-138">Matches</span></span> | <span data-ttu-id="67646-139">Non corrisponde</span><span class="sxs-lookup"><span data-stu-id="67646-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="67646-140">Corrisponde a qualsiasi numero di caratteri compresi nessuno (si noti che quando questo carattere jolly viene utilizzato all'interno di un percorso sostituirà una sola cartella)</span><span class="sxs-lookup"><span data-stu-id="67646-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="67646-141">?</span><span class="sxs-lookup"><span data-stu-id="67646-141">?</span></span> | <span data-ttu-id="67646-142">Corrisponde a qualsiasi carattere singolo</span><span class="sxs-lookup"><span data-stu-id="67646-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="67646-143">Come configurare l'elenco di esclusioni</span><span class="sxs-lookup"><span data-stu-id="67646-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="67646-144">Dalla console di gestione</span><span class="sxs-lookup"><span data-stu-id="67646-144">From the management console</span></span>

<span data-ttu-id="67646-145">Per altre informazioni su come configurare le esclusioni da Puppet, Ansible o da un'altra console di gestione, vedi Impostare le preferenze per [Defender per Endpoint per Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="67646-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="67646-146">Dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="67646-146">From the command line</span></span>

<span data-ttu-id="67646-147">Eseguire il comando seguente per visualizzare le opzioni disponibili per la gestione delle esclusioni:</span><span class="sxs-lookup"><span data-stu-id="67646-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="67646-148">Quando si configurano le esclusioni con caratteri jolly, racchiudere il parametro tra virgolette doppie per evitare il globbing.</span><span class="sxs-lookup"><span data-stu-id="67646-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="67646-149">Esempi:</span><span class="sxs-lookup"><span data-stu-id="67646-149">Examples:</span></span>

- <span data-ttu-id="67646-150">Aggiungere un'esclusione per un'estensione di file:</span><span class="sxs-lookup"><span data-stu-id="67646-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="67646-151">Aggiungere un'esclusione per un file:</span><span class="sxs-lookup"><span data-stu-id="67646-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="67646-152">Aggiungere un'esclusione per una cartella:</span><span class="sxs-lookup"><span data-stu-id="67646-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="67646-153">Aggiungere un'esclusione per una cartella con un carattere jolly:</span><span class="sxs-lookup"><span data-stu-id="67646-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="67646-154">Verranno esclusi solo i percorsi di un livello inferiore *a /var/*, ma non le cartelle più annidate. ad esempio, */var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="67646-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="67646-155">Verranno esclusi tutti i percorsi il cui padre è */var/*; ad *esempio, /var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="67646-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="67646-156">Aggiungere un'esclusione per un processo:</span><span class="sxs-lookup"><span data-stu-id="67646-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="67646-157">Convalidare gli elenchi di esclusioni con il file di test EICAR</span><span class="sxs-lookup"><span data-stu-id="67646-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="67646-158">Puoi verificare che gli elenchi di esclusione funzionino usando `curl` per scaricare un file di test.</span><span class="sxs-lookup"><span data-stu-id="67646-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="67646-159">Nel frammento di codice Bash seguente, sostituisci `test.txt` con un file conforme alle regole di esclusione.</span><span class="sxs-lookup"><span data-stu-id="67646-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="67646-160">Ad esempio, se l'estensione è `.testing` stata esclusa, sostituire `test.txt` con `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="67646-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="67646-161">Se si sta testando un percorso, assicurarsi di eseguire il comando all'interno di tale percorso.</span><span class="sxs-lookup"><span data-stu-id="67646-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="67646-162">Se Defender per Endpoint per Linux segnala malware, la regola non funziona.</span><span class="sxs-lookup"><span data-stu-id="67646-162">If Defender for Endpoint for Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="67646-163">Se non è presente alcun rapporto di malware e il file scaricato esiste, l'esclusione funziona.</span><span class="sxs-lookup"><span data-stu-id="67646-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="67646-164">È possibile aprire il file per verificare che il contenuto sia identico a quello descritto nel sito Web [del file di test EICAR.](http://2016.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="67646-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="67646-165">Se non si dispone dell'accesso a Internet, è possibile creare un file di test EICAR personalizzato.</span><span class="sxs-lookup"><span data-stu-id="67646-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="67646-166">Scrivi la stringa EICAR in un nuovo file di testo con il comando Bash seguente:</span><span class="sxs-lookup"><span data-stu-id="67646-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="67646-167">È inoltre possibile copiare la stringa in un file di testo vuoto e tentare di salvarla con il nome del file o nella cartella che si sta tentando di escludere.</span><span class="sxs-lookup"><span data-stu-id="67646-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="67646-168">Consenti minacce</span><span class="sxs-lookup"><span data-stu-id="67646-168">Allow threats</span></span>

<span data-ttu-id="67646-169">Oltre ad escludere determinati contenuti dall'analisi, puoi anche configurare il prodotto in modo da non rilevare alcune classi di minacce (identificate dal nome della minaccia).</span><span class="sxs-lookup"><span data-stu-id="67646-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="67646-170">È consigliabile prestare attenzione quando si usa questa funzionalità, in quanto può lasciare il dispositivo non protetto.</span><span class="sxs-lookup"><span data-stu-id="67646-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="67646-171">Per aggiungere un nome di minaccia all'elenco delle minacce consentite, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="67646-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="67646-172">Il nome della minaccia associato a un rilevamento nel dispositivo può essere ottenuto usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="67646-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="67646-173">Ad esempio, per aggiungere (il nome della minaccia associato al rilevamento EICAR) all'elenco delle minacce `EICAR-Test-File (not a virus)` consentite, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="67646-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```