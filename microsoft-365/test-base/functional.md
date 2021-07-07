---
title: Test funzionali sulla base di test
description: Dettagli su come testare l'applicazione con i test funzionali automatizzati esistenti
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
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323225"
---
# <a name="functional-testing"></a><span data-ttu-id="31457-103">Test funzionali</span><span class="sxs-lookup"><span data-stu-id="31457-103">Functional testing</span></span>

<span data-ttu-id="31457-104">In quanto fornitore di software, ora puoi eseguire test funzionali personalizzati usando il framework di test di tua scelta, tramite il portale Test Base self-service per M365.</span><span class="sxs-lookup"><span data-stu-id="31457-104">As a software vendor, you can now perform custom functional tests, using the test framework of your choice - via the self-serve Test Base for M365 portal.</span></span> 

<span data-ttu-id="31457-105">Quando il servizio è stato avviato inizialmente, sono stati offerti i test out-of-box, ovvero un set predefinito di test guidati tramite script standardizzati.</span><span class="sxs-lookup"><span data-stu-id="31457-105">When we initially launched the service, we offered the Out-of-box tests, which is a pre-defined set of tests driven through standardized scripting.</span></span> <span data-ttu-id="31457-106">Ciò, tuttavia, non è stato in grado di ottenere una copertura di test completa per molti fornitori di software indipendenti (ISV).</span><span class="sxs-lookup"><span data-stu-id="31457-106">This, however, could not achieve full test coverage for many Independent Software Vendors (ISVs).</span></span> 

<span data-ttu-id="31457-107">Di conseguenza, in risposta al tuo feedback, forniamo ai nostri ISV la possibilità di caricare test funzionali automatizzati.</span><span class="sxs-lookup"><span data-stu-id="31457-107">Hence, in response to your feedback, we are providing our ISVs with the ability to upload automated functional tests.</span></span>

<span data-ttu-id="31457-108">Per utilizzare questa funzionalità, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="31457-108">To use this feature, follow the steps below:</span></span>

1. <span data-ttu-id="31457-109">Upload file (file binari, dipendenze e script) come singolo pacchetto .zip file.</span><span class="sxs-lookup"><span data-stu-id="31457-109">Upload your files (binaries, dependencies and scripts) as a single .zip package.</span></span>
2. <span data-ttu-id="31457-110">Scegliere se riavviare le macchine virtuali di test in diversi punti di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="31457-110">Choose if you want to reboot the test Virtual Machines (VMs) at various points of execution.</span></span>
3. <span data-ttu-id="31457-111">Gestire le opzioni disponibili per gli script.</span><span class="sxs-lookup"><span data-stu-id="31457-111">Manage available options for your scripts.</span></span>
4. <span data-ttu-id="31457-112">Scegliere quando applicare l'aggiornamento Windows sulla macchina virtuale durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="31457-112">Choose when to apply the Windows update on the VM during execution.</span></span>

<span data-ttu-id="31457-113">Le descrizioni dettagliate dei passaggi precedenti sono evidenziate di seguito:</span><span class="sxs-lookup"><span data-stu-id="31457-113">Detailed descriptions of the above steps are highlighted below:</span></span>

<span data-ttu-id="31457-114">**Upload un pacchetto di test funzionale**</span><span class="sxs-lookup"><span data-stu-id="31457-114">**Upload a functional test package**</span></span>

<span data-ttu-id="31457-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span><span class="sxs-lookup"><span data-stu-id="31457-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span></span> <span data-ttu-id="31457-116">Da qui:</span><span class="sxs-lookup"><span data-stu-id="31457-116">From there:</span></span>

<span data-ttu-id="31457-117">Scheda 1: immettere le informazioni di base.</span><span class="sxs-lookup"><span data-stu-id="31457-117">Tab 1 - Enter basic information.</span></span> <span data-ttu-id="31457-118">Specificare il nome e la versione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="31457-118">Provide the name and version of your application.</span></span> <span data-ttu-id="31457-119">Nell'opzione Tipo di test selezionare ```Functional tests``` .</span><span class="sxs-lookup"><span data-stu-id="31457-119">In the Type of test option, select ```Functional tests```.</span></span> 

<span data-ttu-id="31457-120">*Si noti che l'opzione Out-of-Box (OOB) è obbligatoria per impostazione predefinita.*</span><span class="sxs-lookup"><span data-stu-id="31457-120">*Note that the Out-of-Box (OOB) option is required by default.*</span></span>


![Selezionare la scheda test funzionale](Media/functional_testing_tab1.png)

<span data-ttu-id="31457-122">Scheda 2: Upload i componenti del pacchetto caricando un file ZIP con l'intero test (file binari, dipendenze, script e così via).</span><span class="sxs-lookup"><span data-stu-id="31457-122">Tab 2 - Upload the components of your package by uploading a zip file with your entire test (binaries, dependencies, scripts etc).</span></span> 

<span data-ttu-id="31457-123">Vedi aka.ms/usl-package-outline per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="31457-123">See aka.ms/usl-package-outline for details.</span></span> <span data-ttu-id="31457-124">Nota: sia gli script di test out-of-box che il contenuto del test funzionale devono essere inseriti nello stesso file ZIP.</span><span class="sxs-lookup"><span data-stu-id="31457-124">(Note: Both the Out-of-Box test scripts and the Functional test contents should be placed into the same zip file).</span></span> <span data-ttu-id="31457-125">Attualmente, le dimensioni del file sono limitate a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="31457-125">Currently, the file size is limited to 2GB.</span></span>

<span data-ttu-id="31457-126">Scheda 3- Configurare le attività di test out-of-box e funzionali.</span><span class="sxs-lookup"><span data-stu-id="31457-126">Tab 3 - Configure the Out-of-Box and Functional test tasks.</span></span> <span data-ttu-id="31457-127">Qui scegli i percorsi degli script di PowerShell che installeranno, avvieranno, chiuderanno e disinstallano l'applicazione (per Out-of-Box), nonché i percorsi di tutti gli script personalizzati per eseguire il test funzionale.</span><span class="sxs-lookup"><span data-stu-id="31457-127">Here, choose the path(s) to the PowerShell scripts that will install, launch, close, and uninstall your application (for Out-of-Box) as well as the path(s) to all your custom scripts to perform your functional test.</span></span> <span data-ttu-id="31457-128">**Nota: uno script per disinstallare l'applicazione è facoltativo.**</span><span class="sxs-lookup"><span data-stu-id="31457-128">**(Note: A script to uninstall your application is optional).**</span></span>

<span data-ttu-id="31457-129">Attualmente, è possibile caricare da 1 a 8 script per i test funzionali.</span><span class="sxs-lookup"><span data-stu-id="31457-129">Currently, you can upload between 1 and 8 scripts for your functional tests.</span></span> <span data-ttu-id="31457-130">(Commenta gentilmente questo post se hai bisogno di più script!)</span><span class="sxs-lookup"><span data-stu-id="31457-130">(Kindly comment on this post if you need more scripts!)</span></span>

![Upload fino a 8 script con test funzionali](Media/functional_testing_tab3.png)

<span data-ttu-id="31457-132">(Facoltativo) Configurare un riavvio dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="31457-132">(Optional) Configure a restart after installation.</span></span> <span data-ttu-id="31457-133">Alcune applicazioni richiedono un riavvio dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="31457-133">Some applications require a restart after installation.</span></span> 

<span data-ttu-id="31457-134">Selezionare lo script specifico nella scheda Attività se si desidera che venga eseguito un riavvio ```Reboot After Execution``` dopo l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="31457-134">Select ```Reboot After Execution``` for the specific Script in the Tasks tab if you would like a restart to be conducted after the execution of that script.</span></span>

<span data-ttu-id="31457-135">Scheda 4 - Scegliere quando installare l Windows interno: l'applicazione della patch Windows Update viene eseguita prima di qualsiasi script di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="31457-135">Tab 4 - Choose when the Windows update gets installed: The application of the Windows Update patch is done before any script of your choice.</span></span> <span data-ttu-id="31457-136">È consigliabile installare un aggiornamento Windows dopo l'installazione dell'applicazione per imitare da vicino gli scenari di utilizzo delle applicazioni reali.</span><span class="sxs-lookup"><span data-stu-id="31457-136">It is recommended that you install a Windows update after the application's installation to closely mimic your real-world application use scenarios.</span></span>

![L Windows aggiornamento può essere installato dopo uno script specifico](Media/functional_testing_tab4.png)

<span data-ttu-id="31457-138">Scheda 5 - Rivedere e creare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="31457-138">Tab 5 - Review and create the package.</span></span> <span data-ttu-id="31457-139">Dopo aver completato i passaggi sopra elencati, selezionare ```Create``` per completare il processo di caricamento.</span><span class="sxs-lookup"><span data-stu-id="31457-139">Once you have completed the steps listed above, select ```Create``` to finish the uploading process.</span></span>

<span data-ttu-id="31457-140">Dopo aver creato il pacchetto, puoi controllare lo stato di verifica del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="31457-140">Once your package has been created, you can check the verification status of your package.</span></span>

<span data-ttu-id="31457-141">Viene eseguito un test iniziale per installare, avviare, chiudere e disinstallare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="31457-141">We run an initial test to install, launch, close, and uninstall your application.</span></span> <span data-ttu-id="31457-142">Questo ci consente di verificare che il pacchetto possa essere installato nel nostro servizio senza errori.</span><span class="sxs-lookup"><span data-stu-id="31457-142">This allows us to verify that your package can install on our service error-free.</span></span>

<span data-ttu-id="31457-143">Il processo di verifica può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="31457-143">The verification process could take up to 24 hours.</span></span> <span data-ttu-id="31457-144">Una volta completata la verifica, puoi visualizzare lo stato nel menu, che sarebbe ```Manage packages``` una delle due voci seguenti:</span><span class="sxs-lookup"><span data-stu-id="31457-144">Once verification is complete, you can see the status in the ```Manage packages``` menu, which would be one of two entries:</span></span>

1. <span data-ttu-id="31457-145">La verifica ha esito positivo: il pacchetto verrà testato automaticamente in base agli aggiornamenti Windows versione non definitiva per le build del sistema operativo selezionate.</span><span class="sxs-lookup"><span data-stu-id="31457-145">Verification succeeds: The package will be automatically tested against pre-release Windows updates for the OS builds you selected.</span></span>
<span data-ttu-id="31457-146">oppure</span><span class="sxs-lookup"><span data-stu-id="31457-146">or</span></span>
2. <span data-ttu-id="31457-147">La verifica non riesce: dovrai analizzare i motivi dell'errore, risolvere il problema e ricaricare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="31457-147">Verification fails: You will need to investigate the reasons for the failure, fix the issue, and re-upload your package.</span></span>

<span data-ttu-id="31457-148">Si riceverà inoltre una notifica di entrambi i risultati tramite l'icona di notifica nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="31457-148">You will also be notified of either outcome via the notification icon in the Azure portal.</span></span>
