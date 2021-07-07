---
title: Linee guida per i pacchetti di test
description: Esaminare le linee guida relative al pacchetto di test
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323045"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="a9035-103">Linee guida per i pacchetti di test</span><span class="sxs-lookup"><span data-stu-id="a9035-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="a9035-104">1. Script che fa riferimento</span><span class="sxs-lookup"><span data-stu-id="a9035-104">1.   Script referencing</span></span>

<span data-ttu-id="a9035-105">Quando carichi un file .zip nel portale, tutto il contenuto di tale file viene decompresso in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="a9035-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="a9035-106">Non è necessario scrivere codice per eseguire questa operazione di decompressione iniziale.</span><span class="sxs-lookup"><span data-stu-id="a9035-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="a9035-107">Puoi anche fare riferimento a qualsiasi file all'interno del .zip usando il percorso relativo al file ZIP caricato.</span><span class="sxs-lookup"><span data-stu-id="a9035-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="a9035-108">Nell'esempio seguente viene illustrato come fare riferimento ai file binari/script dal campo di input nella scheda Attività. Il testo in blu deve essere immesso nel campo **Percorso script** **senza virgolette.**</span><span class="sxs-lookup"><span data-stu-id="a9035-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="a9035-109">È importante conoscere il contenuto all'interno del file ZIP prima di caricarlo.</span><span class="sxs-lookup"><span data-stu-id="a9035-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="a9035-110">Spesso, quando si comprime una cartella, il computer locale crea una cartella principale sotto il file ZIP.</span><span class="sxs-lookup"><span data-stu-id="a9035-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="a9035-111">In questo caso, il riferimento sarà come illustrato in **grassetto di** seguito:</span><span class="sxs-lookup"><span data-stu-id="a9035-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="a9035-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="a9035-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="a9035-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="a9035-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="a9035-114">Script.ps1 – **"Contoso_App_Folder/cartella1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="a9035-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="a9035-115">Altre volte, il file ZIP potrebbe avere i file o il contenuto direttamente sotto di esso, ad esempio nessuna cartella di secondo livello:</span><span class="sxs-lookup"><span data-stu-id="a9035-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="a9035-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="a9035-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="a9035-117">ScriptX.ps1 – **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="a9035-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="a9035-118">Script.ps1 - **"cartella1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="a9035-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="a9035-119">2. Esecuzione dello script</span><span class="sxs-lookup"><span data-stu-id="a9035-119">2.   Script execution</span></span>

<span data-ttu-id="a9035-120">**Test out-of-box:** Il pacchetto dell'applicazione deve contenere almeno tre script di PowerShell che eseguono l'installazione, l'avvio e la chiusura automatica dell'applicazione e delle relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="a9035-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="a9035-121">Ogni script deve gestire il controllo dei propri prerequisiti, convalidarlo con esito positivo, nonché eseguire la pulizia dopo se stesso (se necessario).</span><span class="sxs-lookup"><span data-stu-id="a9035-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="a9035-122">**Test funzionali:** Il pacchetto dell'applicazione deve contenere almeno uno script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9035-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="a9035-123">Se vengono forniti più script, gli script vengono eseguiti in sequenza di caricamento e un errore in uno script specifico interrompe l'esecuzione degli script successivi.</span><span class="sxs-lookup"><span data-stu-id="a9035-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="a9035-124">Requisiti degli script</span><span class="sxs-lookup"><span data-stu-id="a9035-124">Script requirements</span></span>

<span data-ttu-id="a9035-125">• PowerShell versione 5.1+</span><span class="sxs-lookup"><span data-stu-id="a9035-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="a9035-126">• Esecuzione automatica</span><span class="sxs-lookup"><span data-stu-id="a9035-126">•   Unattended execution</span></span>    

<span data-ttu-id="a9035-127">• Codice restituito errore</span><span class="sxs-lookup"><span data-stu-id="a9035-127">•   Error return code</span></span>               

<span data-ttu-id="a9035-128">• Convalidare l'esito positivo</span><span class="sxs-lookup"><span data-stu-id="a9035-128">•   Validate success</span></span>            

<span data-ttu-id="a9035-129">• Registrazione in una cartella di registro specifica dello script</span><span class="sxs-lookup"><span data-stu-id="a9035-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="a9035-130">Ogni script deve essere eseguito completamente automatico per essere eseguito correttamente nella pipeline di test.</span><span class="sxs-lookup"><span data-stu-id="a9035-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="a9035-131">Gli script devono restituire "0" al completamento corretto e un codice di errore diverso da zero se si verifica un errore durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a9035-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="a9035-132">Ogni script deve verificare che sia stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9035-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="a9035-133">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="a9035-133">E.g.</span></span> <span data-ttu-id="a9035-134">lo script di installazione deve verificare l'esistenza di determinati file binari e/o chiavi del Registro di sistema nel sistema, al termine dell'esecuzione del file binario del programma di installazione per garantire con un ragionevole grado di sicurezza che l'installazione sia stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9035-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="a9035-135">Ciò è necessario per diagnosticare correttamente dove si verificano errori durante un'esecuzione di test, ad esempio non è possibile installare correttamente l'applicazione anziché non avviarla.</span><span class="sxs-lookup"><span data-stu-id="a9035-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="a9035-136">**Evitare quanto segue:** Gli script non devono riavviare il computer, se è necessario un riavvio, specificarlo durante il caricamento degli script.</span><span class="sxs-lookup"><span data-stu-id="a9035-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="a9035-137">3. Raccolta log</span><span class="sxs-lookup"><span data-stu-id="a9035-137">3.   Log collection</span></span>

<span data-ttu-id="a9035-138">Ogni script deve generare i log generati in una cartella denominata ```logs``` .</span><span class="sxs-lookup"><span data-stu-id="a9035-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="a9035-139">Tutte le cartelle nella directory denominata ```logs``` verranno copiate e presentate per il download nella ```Test Results``` pagina.</span><span class="sxs-lookup"><span data-stu-id="a9035-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="a9035-140">Ad esempio, lo script di installazione (che può trovarsi nella directory **App/scripts/install)** può determinare l'output dei registri in: **logs/install.log**, in modo che il log finale sia in: **Apps/scripts/install/logs/install.log**</span><span class="sxs-lookup"><span data-stu-id="a9035-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="a9035-141">Il sistema preleva il file insieme ad altri file all'interno di altre cartelle ```install.log``` ```logs``` e lo fascicola per il download.</span><span class="sxs-lookup"><span data-stu-id="a9035-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="a9035-142">4. File binari dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a9035-142">4.   Application binaries</span></span>

<span data-ttu-id="a9035-143">Tutti i file binari e le dipendenze devono essere inclusi nel singolo file ZIP.</span><span class="sxs-lookup"><span data-stu-id="a9035-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="a9035-144">Devono includere tutto il necessario per l'installazione dell'applicazione (ad esempio, il programma di installazione dell'applicazione); se l'applicazione ha una dipendenza da qualsiasi framework, ad esempio .NET Core/Standard o .NET Framework, questi devono essere inclusi nel file e fare riferimento correttamente negli script forniti.</span><span class="sxs-lookup"><span data-stu-id="a9035-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="a9035-145">Il file ZIP caricato non può contenere spazi o caratteri speciali nel nome</span><span class="sxs-lookup"><span data-stu-id="a9035-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9035-146">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a9035-146">Next steps</span></span>

<span data-ttu-id="a9035-147">Passare all'articolo successivo per visualizzare alcune **domande frequenti**</span><span class="sxs-lookup"><span data-stu-id="a9035-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a9035-148">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a9035-148">Next step</span></span>](faq.md)
