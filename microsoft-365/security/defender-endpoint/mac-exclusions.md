---
title: Configurare e convalidare le esclusioni per Microsoft Defender ATP per Mac
description: Fornire e convalidare le esclusioni per Microsoft Defender ATP per Mac. È possibile impostare esclusioni per file, cartelle e processi.
keywords: microsoft, defender, atp, mac, esclusioni, analisi, antivirus
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
ms.openlocfilehash: 8efb90de58576b7c76a3b600d1e94713eb0c7b93
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062397"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="1bb79-105">Configurare e convalidare le esclusioni per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="1bb79-105">Configure and validate exclusions for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1bb79-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1bb79-106">**Applies to:**</span></span>
- [<span data-ttu-id="1bb79-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1bb79-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="1bb79-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bb79-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1bb79-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1bb79-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1bb79-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1bb79-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1bb79-111">In questo articolo vengono fornite informazioni su come definire le esclusioni applicabili alle analisi su richiesta e sulla protezione e il monitoraggio in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="1bb79-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

>[!IMPORTANT]
><span data-ttu-id="1bb79-112">Le esclusioni descritte in questo articolo non si applicano ad altre funzionalità di Defender per Endpoint per Mac, tra cui il rilevamento e la risposta degli endpoint (EDR).</span><span class="sxs-lookup"><span data-stu-id="1bb79-112">The exclusions described in this article don't apply to other Defender for Endpoint for Mac capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="1bb79-113">I file esclusi utilizzando i metodi descritti in questo articolo possono comunque attivare avvisi EDR e altri rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="1bb79-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="1bb79-114">Puoi escludere determinati file, cartelle, processi e file aperti dal processo da analisi di Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="1bb79-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Mac scans.</span></span>

<span data-ttu-id="1bb79-115">Le esclusioni possono essere utili per evitare rilevamenti non corretti su file o software univoci o personalizzati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1bb79-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="1bb79-116">Possono anche essere utili per ridurre i problemi di prestazioni causati da Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="1bb79-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Mac.</span></span>

>[!WARNING]
><span data-ttu-id="1bb79-117">La definizione delle esclusioni riduce la protezione offerta da Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="1bb79-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="1bb79-118">È consigliabile valutare sempre i rischi associati all'implementazione delle esclusioni e escludere solo i file che si è certi non siano dannosi.</span><span class="sxs-lookup"><span data-stu-id="1bb79-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="1bb79-119">Tipi di esclusione supportati</span><span class="sxs-lookup"><span data-stu-id="1bb79-119">Supported exclusion types</span></span>

<span data-ttu-id="1bb79-120">La tabella seguente mostra i tipi di esclusione supportati da Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="1bb79-120">The follow table shows the exclusion types supported by Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="1bb79-121">Esclusione</span><span class="sxs-lookup"><span data-stu-id="1bb79-121">Exclusion</span></span> | <span data-ttu-id="1bb79-122">Definizione</span><span class="sxs-lookup"><span data-stu-id="1bb79-122">Definition</span></span> | <span data-ttu-id="1bb79-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="1bb79-123">Examples</span></span>
---|---|---
<span data-ttu-id="1bb79-124">Estensione del file</span><span class="sxs-lookup"><span data-stu-id="1bb79-124">File extension</span></span> | <span data-ttu-id="1bb79-125">Tutti i file con estensione, in qualsiasi punto del computer</span><span class="sxs-lookup"><span data-stu-id="1bb79-125">All files with the extension, anywhere on the machine</span></span> | `.test`
<span data-ttu-id="1bb79-126">File</span><span class="sxs-lookup"><span data-stu-id="1bb79-126">File</span></span> | <span data-ttu-id="1bb79-127">Un file specifico identificato dal percorso completo</span><span class="sxs-lookup"><span data-stu-id="1bb79-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="1bb79-128">Cartella</span><span class="sxs-lookup"><span data-stu-id="1bb79-128">Folder</span></span> | <span data-ttu-id="1bb79-129">Tutti i file nella cartella specificata (in modo ricorsivo)</span><span class="sxs-lookup"><span data-stu-id="1bb79-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="1bb79-130">Processo</span><span class="sxs-lookup"><span data-stu-id="1bb79-130">Process</span></span> | <span data-ttu-id="1bb79-131">Un processo specifico (specificato dal percorso completo o dal nome del file) e tutti i file aperti da esso</span><span class="sxs-lookup"><span data-stu-id="1bb79-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

<span data-ttu-id="1bb79-132">Le esclusioni di file, cartelle e processi supportano i caratteri jolly seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bb79-132">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="1bb79-133">Carattere jolly</span><span class="sxs-lookup"><span data-stu-id="1bb79-133">Wildcard</span></span> | <span data-ttu-id="1bb79-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bb79-134">Description</span></span> | <span data-ttu-id="1bb79-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bb79-135">Example</span></span> | <span data-ttu-id="1bb79-136">Corrispondenze</span><span class="sxs-lookup"><span data-stu-id="1bb79-136">Matches</span></span> | <span data-ttu-id="1bb79-137">Non corrisponde</span><span class="sxs-lookup"><span data-stu-id="1bb79-137">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="1bb79-138">Corrisponde a qualsiasi numero di caratteri compresi nessuno (si noti che quando questo carattere jolly viene utilizzato all'interno di un percorso sostituirà una sola cartella)</span><span class="sxs-lookup"><span data-stu-id="1bb79-138">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/*/*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="1bb79-139">?</span><span class="sxs-lookup"><span data-stu-id="1bb79-139">?</span></span> | <span data-ttu-id="1bb79-140">Corrisponde a qualsiasi carattere singolo</span><span class="sxs-lookup"><span data-stu-id="1bb79-140">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

>[!NOTE]
><span data-ttu-id="1bb79-141">Il prodotto tenta di risolvere i collegamenti di società durante la valutazione delle esclusioni.</span><span class="sxs-lookup"><span data-stu-id="1bb79-141">The product attempts to resolve firmlinks when evaluating exclusions.</span></span> <span data-ttu-id="1bb79-142">La risoluzione firmlink non funziona quando l'esclusione contiene caratteri jolly o il file di destinazione (nel `Data` volume) non esiste.</span><span class="sxs-lookup"><span data-stu-id="1bb79-142">Firmlink resolution does not work when the exclusion contains wildcards or the target file (on the `Data` volume) does not exist.</span></span>

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="1bb79-143">Come configurare l'elenco di esclusioni</span><span class="sxs-lookup"><span data-stu-id="1bb79-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="1bb79-144">Dalla console di gestione</span><span class="sxs-lookup"><span data-stu-id="1bb79-144">From the management console</span></span>

<span data-ttu-id="1bb79-145">Per altre informazioni su come configurare le esclusioni da JAMF, Intune o un'altra console di gestione, vedi Impostare le preferenze per [Defender per Endpoint per Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="1bb79-145">For more information on how to configure exclusions from JAMF, Intune, or another management console, see [Set preferences for Defender for Endpoint for Mac](mac-preferences.md).</span></span>

### <a name="from-the-user-interface"></a><span data-ttu-id="1bb79-146">Dall'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="1bb79-146">From the user interface</span></span>

<span data-ttu-id="1bb79-147">Apri l'applicazione Defender for Endpoint e passa a **Gestisci impostazioni** Aggiungi o  >  **rimuovi esclusione...**, come illustrato nello screenshot seguente:</span><span class="sxs-lookup"><span data-stu-id="1bb79-147">Open the Defender for Endpoint application and navigate to **Manage settings** > **Add or Remove Exclusion...**, as shown in the following screenshot:</span></span>

![Schermata Gestisci esclusioni](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-37-exclusions)

<span data-ttu-id="1bb79-149">Selezionare il tipo di esclusione che si desidera aggiungere e seguire le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="1bb79-149">Select the type of exclusion that you wish to add and follow the prompts.</span></span>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="1bb79-150">Convalidare gli elenchi di esclusioni con il file di test EICAR</span><span class="sxs-lookup"><span data-stu-id="1bb79-150">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="1bb79-151">Puoi verificare che gli elenchi di esclusione funzionino usando `curl` per scaricare un file di test.</span><span class="sxs-lookup"><span data-stu-id="1bb79-151">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="1bb79-152">Nel frammento di codice Bash seguente, sostituisci `test.txt` con un file conforme alle regole di esclusione.</span><span class="sxs-lookup"><span data-stu-id="1bb79-152">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="1bb79-153">Ad esempio, se l'estensione è `.testing` stata esclusa, sostituire `test.txt` con `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="1bb79-153">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="1bb79-154">Se si sta testando un percorso, assicurarsi di eseguire il comando all'interno di tale percorso.</span><span class="sxs-lookup"><span data-stu-id="1bb79-154">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="1bb79-155">Se Defender per Endpoint per Mac segnala malware, la regola non funziona.</span><span class="sxs-lookup"><span data-stu-id="1bb79-155">If Defender for Endpoint for Mac reports malware, then the rule is not working.</span></span> <span data-ttu-id="1bb79-156">Se non è presente alcun rapporto di malware e il file scaricato esiste, l'esclusione funziona.</span><span class="sxs-lookup"><span data-stu-id="1bb79-156">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="1bb79-157">È possibile aprire il file per verificare che il contenuto sia identico a quello descritto nel sito Web [del file di test EICAR.](http://2016.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="1bb79-157">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="1bb79-158">Se non si dispone dell'accesso a Internet, è possibile creare un file di test EICAR personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1bb79-158">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="1bb79-159">Scrivi la stringa EICAR in un nuovo file di testo con il comando Bash seguente:</span><span class="sxs-lookup"><span data-stu-id="1bb79-159">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="1bb79-160">È inoltre possibile copiare la stringa in un file di testo vuoto e tentare di salvarla con il nome del file o nella cartella che si sta tentando di escludere.</span><span class="sxs-lookup"><span data-stu-id="1bb79-160">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="1bb79-161">Consenti minacce</span><span class="sxs-lookup"><span data-stu-id="1bb79-161">Allow threats</span></span>

<span data-ttu-id="1bb79-162">Oltre ad escludere determinati contenuti dall'analisi, puoi anche configurare il prodotto in modo da non rilevare alcune classi di minacce (identificate dal nome della minaccia).</span><span class="sxs-lookup"><span data-stu-id="1bb79-162">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="1bb79-163">È consigliabile prestare attenzione quando si usa questa funzionalità, in quanto può lasciare il dispositivo non protetto.</span><span class="sxs-lookup"><span data-stu-id="1bb79-163">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="1bb79-164">Per aggiungere un nome di minaccia all'elenco delle minacce consentite, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1bb79-164">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="1bb79-165">Il nome della minaccia associato a un rilevamento nel dispositivo può essere ottenuto usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1bb79-165">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="1bb79-166">Ad esempio, per aggiungere (il nome della minaccia associato al rilevamento EICAR) all'elenco delle minacce `EICAR-Test-File (not a virus)` consentite, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1bb79-166">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```