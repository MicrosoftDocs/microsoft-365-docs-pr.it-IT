---
title: Antivirus Microsoft Defender Virtual Desktop Infrastructure guida alla distribuzione
description: Informazioni su come distribuire Antivirus Microsoft Defender in un ambiente desktop virtuale per il miglior equilibrio tra protezione e prestazioni.
keywords: vdi, hyper-v, vm, macchina virtuale, windows defender, antivirus, av, desktop virtuale, rds, desktop remoto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4ecd14e055646804d81e22da7c192988cf1e6f6f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275253"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="c0585-104">Guida alla distribuzione di Microsoft Defender Antivirus in un ambiente VDI (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="c0585-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c0585-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c0585-105">**Applies to:**</span></span>

- [<span data-ttu-id="c0585-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c0585-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c0585-107">Oltre alle configurazioni hardware o locali standard, è anche possibile utilizzare Antivirus Microsoft Defender in un ambiente desktop remoto (RDS) o VDI (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="c0585-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="c0585-108">Vedi [Windows documentazione sul desktop virtuale per](/azure/virtual-desktop) ulteriori dettagli su Desktop remoto Microsoft Services e il supporto VDI.</span><span class="sxs-lookup"><span data-stu-id="c0585-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="c0585-109">Per le macchine virtuali basate su Azure, vedere [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="c0585-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="c0585-110">Con la possibilità di distribuire facilmente gli aggiornamenti alle macchine virtuali in esecuzione in VDI, questa guida è stata abbreviata per concentrarsi su come è possibile ottenere gli aggiornamenti nei computer in modo rapido e semplice.</span><span class="sxs-lookup"><span data-stu-id="c0585-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="c0585-111">Non è più necessario creare e sigillare periodicamente le immagini dorate, poiché gli aggiornamenti vengono espansi nei bit dei componenti nel server host e quindi scaricati direttamente nella macchina virtuale quando è attivata.</span><span class="sxs-lookup"><span data-stu-id="c0585-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="c0585-112">In questa guida viene descritto come configurare le macchine virtuali per garantire prestazioni e protezione ottimali, tra cui:</span><span class="sxs-lookup"><span data-stu-id="c0585-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="c0585-113">Configurare una condivisione file VDI dedicata per gli aggiornamenti delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="c0585-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="c0585-114">Analisi pianificate casuali</span><span class="sxs-lookup"><span data-stu-id="c0585-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="c0585-115">Usare analisi rapide</span><span class="sxs-lookup"><span data-stu-id="c0585-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="c0585-116">Impedisci notifiche</span><span class="sxs-lookup"><span data-stu-id="c0585-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="c0585-117">Disabilitare l'esecuzione delle analisi dopo ogni aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c0585-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="c0585-118">Eseguire l'analisi di computer o computer non aggiornati che sono stati offline per un po' di tempo</span><span class="sxs-lookup"><span data-stu-id="c0585-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="c0585-119">Applicare esclusioni</span><span class="sxs-lookup"><span data-stu-id="c0585-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="c0585-120">È inoltre possibile scaricare il white paper Antivirus Microsoft Defender su [Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), che esamina la nuova funzionalità di aggiornamento della sicurezza intelligence condivisa, oltre a test delle prestazioni e indicazioni su come testare le prestazioni dell'antivirus nel proprio VDI.</span><span class="sxs-lookup"><span data-stu-id="c0585-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0585-121">Anche se la VDI può essere ospitata in Windows Server 2012 o Windows Server 2016, le macchine virtuali devono eseguire almeno Windows 10 1607, a causa di tecnologie e funzionalità di protezione più avanzate che non sono disponibili nelle versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="c0585-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="c0585-122">Esistono miglioramenti delle prestazioni e delle funzionalità per il modo in cui Microsoft Defender AV opera sulle macchine virtuali in Windows 10 Insider Preview, build 18323 (e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="c0585-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="c0585-123">Ci identificheremo in questa guida se devi usare una build di Insider Preview; se non viene specificato, la versione minima richiesta per la protezione e le prestazioni migliori è Windows 10 1607.</span><span class="sxs-lookup"><span data-stu-id="c0585-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="c0585-124">Configurare una condivisione file VDI dedicata</span><span class="sxs-lookup"><span data-stu-id="c0585-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="c0585-125">In Windows 10, versione 1903, è stata introdotta la funzionalità di intelligence per la sicurezza condivisa, che scarica la decompressione degli aggiornamenti di security intelligence scaricati in un computer host, salvando così le risorse precedenti di CPU, disco e memoria nei singoli computer.</span><span class="sxs-lookup"><span data-stu-id="c0585-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="c0585-126">Questa funzionalità è stata backported e ora funziona in Windows 10 1703 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c0585-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="c0585-127">È possibile impostare questa funzionalità con Criteri di gruppo o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0585-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="c0585-128">Utilizzare Criteri di gruppo per abilitare la funzionalità di intelligence per la sicurezza condivisa:</span><span class="sxs-lookup"><span data-stu-id="c0585-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="c0585-129">Nel computer di gestione di Criteri di gruppo aprire console Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c0585-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="c0585-130">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="c0585-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c0585-131">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="c0585-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="c0585-132">Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Security Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="c0585-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="c0585-133">Fare doppio clic **su Definisci percorso intelligence di sicurezza per i client VDI** e quindi impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="c0585-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="c0585-134">Viene visualizzato automaticamente un campo.</span><span class="sxs-lookup"><span data-stu-id="c0585-134">A field automatically appears.</span></span>

6. <span data-ttu-id="c0585-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span><span class="sxs-lookup"><span data-stu-id="c0585-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="c0585-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0585-136">Click **OK**.</span></span>

8. <span data-ttu-id="c0585-137">Distribuire l'oggetto Criteri di gruppo alle macchine virtuali che si desidera testare.</span><span class="sxs-lookup"><span data-stu-id="c0585-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="c0585-138">Usare PowerShell per abilitare la funzionalità di intelligence per la sicurezza condivisa</span><span class="sxs-lookup"><span data-stu-id="c0585-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="c0585-139">Utilizzare il cmdlet seguente per abilitare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c0585-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="c0585-140">Sarà quindi necessario eseguire il push di questo tipo come si farebbe normalmente per eseguire il push dei criteri di configurazione basati su PowerShell nelle macchine virtuali:</span><span class="sxs-lookup"><span data-stu-id="c0585-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="c0585-141">Vedi la [sezione Download e unpackage](#download-and-unpackage-the-latest-updates) per sapere \<shared location\> quale sarà il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c0585-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="c0585-142">Scaricare e annullare il pacchetto degli aggiornamenti più recenti</span><span class="sxs-lookup"><span data-stu-id="c0585-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="c0585-143">Ora puoi iniziare a scaricare e installare nuovi aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="c0585-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="c0585-144">Di seguito è stato creato uno script di PowerShell di esempio.</span><span class="sxs-lookup"><span data-stu-id="c0585-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="c0585-145">Questo script è il modo più semplice per scaricare nuovi aggiornamenti e prepararli per le macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="c0585-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="c0585-146">È quindi consigliabile impostare lo script per l'esecuzione in un determinato momento nel computer di gestione usando un'attività pianificata (o, se si ha familiarità con l'uso di script di PowerShell in Azure, Intune o SCCM, è possibile usare anche tali script).</span><span class="sxs-lookup"><span data-stu-id="c0585-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="c0585-147">È possibile impostare un'attività pianificata per l'esecuzione una volta al giorno in modo che ogni volta che il pacchetto viene scaricato e decompresso, le macchine virtuali riceveranno il nuovo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c0585-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="c0585-148">Ti consigliamo di iniziare con una volta al giorno, ma dovresti provare ad aumentare o diminuire la frequenza per comprendere l'impatto.</span><span class="sxs-lookup"><span data-stu-id="c0585-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="c0585-149">I pacchetti di intelligence per la sicurezza vengono in genere pubblicati una volta ogni tre o quattro ore.</span><span class="sxs-lookup"><span data-stu-id="c0585-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="c0585-150">L'impostazione di una frequenza inferiore a quattro ore non è consigliata perché aumenterà il sovraccarico di rete sul computer di gestione senza alcun vantaggio.</span><span class="sxs-lookup"><span data-stu-id="c0585-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="c0585-151">Impostare un'attività pianificata per eseguire lo script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0585-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="c0585-152">Nel computer di gestione apri il menu Start e digita **Utilità di pianificazione.**</span><span class="sxs-lookup"><span data-stu-id="c0585-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="c0585-153">Aprirlo e selezionare **Crea attività...**</span><span class="sxs-lookup"><span data-stu-id="c0585-153">Open it and select **Create task…**</span></span> <span data-ttu-id="c0585-154">sul pannello laterale.</span><span class="sxs-lookup"><span data-stu-id="c0585-154">on the side panel.</span></span>

2. <span data-ttu-id="c0585-155">Immetti il nome come **Decompressione di Security intelligence**.</span><span class="sxs-lookup"><span data-stu-id="c0585-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="c0585-156">Vai alla **scheda Trigger.** Seleziona **Nuovo...**</span><span class="sxs-lookup"><span data-stu-id="c0585-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="c0585-157"> > **Daily** e selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="c0585-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="c0585-158">Passare alla **scheda** Azioni. Seleziona **Nuovo...**</span><span class="sxs-lookup"><span data-stu-id="c0585-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="c0585-159">Immettere **PowerShell** nel **campo Programma/Script.**</span><span class="sxs-lookup"><span data-stu-id="c0585-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="c0585-160">Immettere `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` nel campo **Aggiungi** argomenti.</span><span class="sxs-lookup"><span data-stu-id="c0585-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="c0585-161">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0585-161">Select **OK**.</span></span>

4. <span data-ttu-id="c0585-162">Se lo si desidera, è possibile scegliere di configurare impostazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c0585-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="c0585-163">Selezionare **OK** per salvare l'attività pianificata.</span><span class="sxs-lookup"><span data-stu-id="c0585-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="c0585-164">È possibile avviare l'aggiornamento manualmente facendo clic con il pulsante destro del mouse sull'attività e scegliendo **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c0585-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="c0585-165">Scaricare e annullare il pacchetto manualmente</span><span class="sxs-lookup"><span data-stu-id="c0585-165">Download and unpackage manually</span></span>

<span data-ttu-id="c0585-166">Se si preferisce eseguire tutte le attività manualmente, ecco cosa fare per replicare il comportamento dello script:</span><span class="sxs-lookup"><span data-stu-id="c0585-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="c0585-167">Creare una nuova cartella nella radice di sistema chiamata per archiviare gli aggiornamenti di intelligence, ad `wdav_update` esempio creare la cartella `c:\wdav_update` .</span><span class="sxs-lookup"><span data-stu-id="c0585-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="c0585-168">Creare una sottocartella *in wdav_update* con un nome GUID, ad esempio `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="c0585-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="c0585-169">Ecco un esempio: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="c0585-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0585-170">Nello script viene impostato in modo che le ultime 12 cifre del GUID siano l'anno, il mese, il giorno e l'ora in cui il file è stato scaricato in modo da creare una nuova cartella ogni volta.</span><span class="sxs-lookup"><span data-stu-id="c0585-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="c0585-171">È possibile modificare questa impostazione in modo che il file sia scaricato nella stessa cartella ogni volta.</span><span class="sxs-lookup"><span data-stu-id="c0585-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="c0585-172">Scaricare un pacchetto di intelligence per la [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  sicurezza dalla cartella GUID.</span><span class="sxs-lookup"><span data-stu-id="c0585-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="c0585-173">Il file deve essere denominato `mpam-fe.exe` .</span><span class="sxs-lookup"><span data-stu-id="c0585-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="c0585-174">Aprire una finestra del prompt dei comandi e passare alla cartella GUID creata.</span><span class="sxs-lookup"><span data-stu-id="c0585-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="c0585-175">Utilizzare il **comando /X** extraction per estrarre i file, ad esempio `mpam-fe.exe /X` .</span><span class="sxs-lookup"><span data-stu-id="c0585-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0585-176">Le macchine virtuali prelevano il pacchetto aggiornato ogni volta che viene creata una nuova cartella GUID con un pacchetto di aggiornamento estratto o ogni volta che una cartella esistente viene aggiornata con un nuovo pacchetto estratto.</span><span class="sxs-lookup"><span data-stu-id="c0585-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="c0585-177">Analisi pianificate casuali</span><span class="sxs-lookup"><span data-stu-id="c0585-177">Randomize scheduled scans</span></span>

<span data-ttu-id="c0585-178">Le analisi pianificate vengono eseguite oltre alla protezione [e all'analisi in tempo reale.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c0585-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c0585-179">L'ora di inizio dell'analisi stessa è ancora basata sul criterio di analisi pianificato (**ScheduleDay,** **ScheduleTime** e **ScheduleQuickScanTime**).</span><span class="sxs-lookup"><span data-stu-id="c0585-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="c0585-180">La casualità causerà Antivirus Microsoft Defender un'analisi su ogni computer entro un intervallo di 4 ore dall'ora impostata per l'analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="c0585-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="c0585-181">Vedere [Pianificare le analisi per](scheduled-catch-up-scans-microsoft-defender-antivirus.md) altre opzioni di configurazione disponibili per le analisi pianificate.</span><span class="sxs-lookup"><span data-stu-id="c0585-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="c0585-182">Usare analisi rapide</span><span class="sxs-lookup"><span data-stu-id="c0585-182">Use quick scans</span></span>

<span data-ttu-id="c0585-183">È possibile specificare il tipo di analisi da eseguire durante un'analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="c0585-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="c0585-184">Le analisi rapide sono l'approccio preferito perché sono progettate per cercare in tutti i luoghi in cui il malware deve risiedere per essere attivo.</span><span class="sxs-lookup"><span data-stu-id="c0585-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="c0585-185">Nella procedura seguente viene descritto come configurare analisi rapide tramite Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c0585-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="c0585-186">Nell'Editor Criteri di gruppo passare a **Modelli amministrativi**  >  **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **Analisi**.</span><span class="sxs-lookup"><span data-stu-id="c0585-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="c0585-187">Selezionare **Specificare il tipo di analisi da utilizzare per un'analisi pianificata** e quindi modificare l'impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="c0585-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="c0585-188">Impostare il criterio su **Abilitato** e quindi in **Opzioni** selezionare **Analisi rapida.**</span><span class="sxs-lookup"><span data-stu-id="c0585-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="c0585-189">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0585-189">Select **OK**.</span></span> 

5. <span data-ttu-id="c0585-190">Distribuire l'oggetto Criteri di gruppo come di consueto.</span><span class="sxs-lookup"><span data-stu-id="c0585-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="c0585-191">Impedisci notifiche</span><span class="sxs-lookup"><span data-stu-id="c0585-191">Prevent notifications</span></span>

<span data-ttu-id="c0585-192">A volte, Antivirus Microsoft Defender notifiche possono essere inviate o mantenute in più sessioni.</span><span class="sxs-lookup"><span data-stu-id="c0585-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="c0585-193">Per ridurre al minimo il problema, è possibile bloccare l'interfaccia Antivirus Microsoft Defender utente.</span><span class="sxs-lookup"><span data-stu-id="c0585-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="c0585-194">La procedura seguente descrive come eliminare le notifiche con Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c0585-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="c0585-195">Nell'Editor Criteri di gruppo passare a Windows **componenti**  >  **Antivirus Microsoft Defender**  >  **Client Interface**.</span><span class="sxs-lookup"><span data-stu-id="c0585-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="c0585-196">Selezionare **Elimina tutte le notifiche** e quindi modificare le impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="c0585-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="c0585-197">Impostare il criterio su **Abilitato** e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="c0585-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="c0585-198">Distribuire l'oggetto Criteri di gruppo come di consueto.</span><span class="sxs-lookup"><span data-stu-id="c0585-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="c0585-199">L'eliminazione delle notifiche impedisce Antivirus Microsoft Defender notifiche di essere visualizzate nel centro notifiche in Windows 10 quando vengono eseguite analisi o vengono eseguite azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="c0585-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="c0585-200">Tuttavia, il team delle operazioni di sicurezza visualizza i risultati dell'analisi nel Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="c0585-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="c0585-201">Per aprire il Centro notifiche in Windows 10, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0585-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="c0585-202">All'estremità destra della barra delle applicazioni seleziona l'icona del Centro notifiche.</span><span class="sxs-lookup"><span data-stu-id="c0585-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="c0585-203">Premi il Windows logo + A.</span><span class="sxs-lookup"><span data-stu-id="c0585-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="c0585-204">In un dispositivo touchscreen scorri rapidamente dal bordo destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="c0585-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="c0585-205">Disabilitare le analisi dopo un aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c0585-205">Disable scans after an update</span></span>

<span data-ttu-id="c0585-206">La disabilitazione di un'analisi dopo un aggiornamento impedirà l'esecuzione di un'analisi dopo la ricezione di un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c0585-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="c0585-207">È possibile applicare questa impostazione durante la creazione dell'immagine di base se è stata eseguita anche un'analisi rapida.</span><span class="sxs-lookup"><span data-stu-id="c0585-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="c0585-208">In questo modo, è possibile impedire alla macchina virtuale appena aggiornata di eseguire di nuovo un'analisi, poiché è già stata analizzata al momento della creazione dell'immagine di base.</span><span class="sxs-lookup"><span data-stu-id="c0585-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0585-209">L'esecuzione di analisi dopo un aggiornamento garantisce che le macchine virtuali siano protette con gli ultimi aggiornamenti di Security intelligence.</span><span class="sxs-lookup"><span data-stu-id="c0585-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="c0585-210">La disabilitazione di questa opzione riduce il livello di protezione delle macchine virtuali e deve essere usata solo quando si crea o distribuisce per la prima volta l'immagine di base.</span><span class="sxs-lookup"><span data-stu-id="c0585-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="c0585-211">Nell'Editor Criteri di gruppo passare a Windows **componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Security Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="c0585-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="c0585-212">Seleziona **Attiva analisi dopo l'aggiornamento delle funzionalità di intelligence** per la sicurezza e quindi modifica l'impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="c0585-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="c0585-213">Impostare il criterio su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="c0585-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="c0585-214">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0585-214">Select **OK**.</span></span>

5. <span data-ttu-id="c0585-215">Distribuire l'oggetto Criteri di gruppo come di consueto.</span><span class="sxs-lookup"><span data-stu-id="c0585-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="c0585-216">Questo criterio impedisce l'esecuzione di un'analisi immediatamente dopo un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c0585-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="c0585-217">Analizzare le macchine virtuali che sono state offline</span><span class="sxs-lookup"><span data-stu-id="c0585-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="c0585-218">Nell'Editor Criteri di gruppo passare a Windows **componenti**  >  **Antivirus Microsoft Defender**  >  **Scansione**.</span><span class="sxs-lookup"><span data-stu-id="c0585-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="c0585-219">Seleziona **Attiva analisi rapida di acquisizione e** quindi modifica l'impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="c0585-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="c0585-220">Impostare il criterio su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="c0585-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="c0585-221">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0585-221">Select **OK**.</span></span>

5. <span data-ttu-id="c0585-222">Distribuisci l'oggetto Criteri di gruppo come di solito.</span><span class="sxs-lookup"><span data-stu-id="c0585-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="c0585-223">Questo criterio forza un'analisi se la macchina virtuale ha perso due o più analisi pianificate consecutive.</span><span class="sxs-lookup"><span data-stu-id="c0585-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="c0585-224">Abilitare la modalità interfaccia utente headless</span><span class="sxs-lookup"><span data-stu-id="c0585-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="c0585-225">Nell'Editor Criteri di gruppo passare a Windows **componenti**  >  **Antivirus Microsoft Defender**  >  **Client Interface**.</span><span class="sxs-lookup"><span data-stu-id="c0585-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="c0585-226">Seleziona **Abilita modalità interfaccia utente headless** e modifica il criterio.</span><span class="sxs-lookup"><span data-stu-id="c0585-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="c0585-227">Impostare il criterio su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="c0585-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="c0585-228">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0585-228">Click **OK**.</span></span>

5. <span data-ttu-id="c0585-229">Distribuisci l'oggetto Criteri di gruppo come di solito.</span><span class="sxs-lookup"><span data-stu-id="c0585-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="c0585-230">Questo criterio nasconde l'intera Antivirus Microsoft Defender'interfaccia utente agli utenti finali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0585-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="c0585-231">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="c0585-231">Exclusions</span></span>

<span data-ttu-id="c0585-232">Le esclusioni possono essere aggiunte, rimosse o personalizzate in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="c0585-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="c0585-233">Per ulteriori informazioni, vedere [Configure Antivirus Microsoft Defender exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="c0585-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0585-234">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c0585-234">Additional resources</span></span>

- [<span data-ttu-id="c0585-235">Blog Community tech: Configurazione Antivirus Microsoft Defender per computer VDI non persistenti</span><span class="sxs-lookup"><span data-stu-id="c0585-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="c0585-236">Forum TechNet su Servizi Desktop remoto e VDI</span><span class="sxs-lookup"><span data-stu-id="c0585-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="c0585-237">Script Di PowerShell SignatureDownloadCustomTask</span><span class="sxs-lookup"><span data-stu-id="c0585-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)