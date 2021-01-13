---
title: Registrare manualmente i dispositivi già presenti
description: Registrare i dispositivi riutilizzati che potrebbero essere già disponibili in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840516"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="71819-103">Registrare manualmente i dispositivi già presenti</span><span class="sxs-lookup"><span data-stu-id="71819-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="71819-104">In questo argomento vengono descritti i passaggi necessari per riutilizzare i dispositivi già presenti e registrarli in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="71819-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="71819-105">Se si utilizzano dispositivi nuovi di zecca, eseguire i passaggi descritti in [registrare i nuovi dispositivi in Microsoft Managed Desktop](register-devices-self.md) .</span><span class="sxs-lookup"><span data-stu-id="71819-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="71819-106">Il processo per i partner è documentato nei [passaggi per i partner per la registrazione dei dispositivi](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="71819-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="71819-107">Microsoft Managed Desktop è in grado di lavorare con dispositivi nuovi di zecca oppure è possibile riutilizzare i dispositivi già presenti (che richiedono di rivisualizzarli).</span><span class="sxs-lookup"><span data-stu-id="71819-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="71819-108">È possibile registrare i dispositivi con Microsoft Managed Desktop nel portale di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="71819-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="71819-109">Preparare la registrazione di dispositivi esistenti</span><span class="sxs-lookup"><span data-stu-id="71819-109">Prepare to register existing devices</span></span>


<span data-ttu-id="71819-110">Per registrare i dispositivi esistenti, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="71819-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="71819-111">Ottenere l'hash hardware per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71819-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="71819-112">Unire i dati hash</span><span class="sxs-lookup"><span data-stu-id="71819-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="71819-113">[Registrare i dispositivi in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="71819-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="71819-114">Verificare che l'immagine sia corretta.</span><span class="sxs-lookup"><span data-stu-id="71819-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="71819-115">Recapito del dispositivo</span><span class="sxs-lookup"><span data-stu-id="71819-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="71819-116">Ottenere l'hash hardware</span><span class="sxs-lookup"><span data-stu-id="71819-116">Obtain the hardware hash</span></span>

<span data-ttu-id="71819-117">Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware.</span><span class="sxs-lookup"><span data-stu-id="71819-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="71819-118">Sono disponibili quattro opzioni per ottenere queste informazioni dai dispositivi che si stanno già usando:</span><span class="sxs-lookup"><span data-stu-id="71819-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="71819-119">Rivolgersi al fornitore OEM per il file di registrazione Autopilot, che includerà gli hash hardware.</span><span class="sxs-lookup"><span data-stu-id="71819-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="71819-120">Raccogliere informazioni in [Microsoft endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="71819-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="71819-121">Eseguire uno script di Windows PowerShell, utilizzando [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) su ogni dispositivo, e raccogliere i risultati in un file.</span><span class="sxs-lookup"><span data-stu-id="71819-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="71819-122">Avviare ogni dispositivo--ma non completare l'esperienza di installazione di Windows--e [raccogliere gli hash su un'unità flash rimovibile](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="71819-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="71819-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71819-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="71819-124">È possibile utilizzare Gestione configurazione endpoint Microsoft per raccogliere gli hash hardware dai dispositivi esistenti che si desidera registrare con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="71819-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71819-125">Tutti i dispositivi per i quali si desidera ottenere queste informazioni devono essere in esecuzione Windows 10, versione 1703 o successiva.</span><span class="sxs-lookup"><span data-stu-id="71819-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="71819-126">Se sono stati soddisfatti tutti questi prerequisiti, è possibile raccogliere le informazioni attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="71819-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="71819-127">Nella console di Configuration Manager, selezionare **monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="71819-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="71819-128">Nell'area di lavoro Monitoraggio espandere il nodo **report** , espandere **report** e selezionare il nodo **hardware-generale** .</span><span class="sxs-lookup"><span data-stu-id="71819-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="71819-129">Eseguire il report, le **informazioni sul dispositivo Autopilot di Windows** e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="71819-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="71819-130">Nel Visualizzatore di report selezionare l'icona **Esporta** e scegliere l'opzione **CSV (delimitato da virgole)** .</span><span class="sxs-lookup"><span data-stu-id="71819-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="71819-131">Dopo aver salvato il file, è necessario filtrare i risultati in base ai soli dispositivi che si intende registrare con Microsoft Managed Desktop e caricare i dati in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="71819-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="71819-132">Aprire Microsoft Endpoint Manager e passare al menu **dispositivi** , quindi cercare la sezione Microsoft Managed Desktop e selezionare **dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="71819-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="71819-133">Selezionare **+ registra dispositivi**, che consente di aprire un Fly-in per registrare i nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="71819-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="71819-134">Per ulteriori informazioni, vedere [registrazione dei dispositivi tramite il portale di amministrazione](#register-devices-by-using-the-admin-portal) .</span><span class="sxs-lookup"><span data-stu-id="71819-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="71819-135">Metodo script di PowerShell di Active Directory</span><span class="sxs-lookup"><span data-stu-id="71819-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="71819-136">In un ambiente Active Directory, è possibile utilizzare il `Get-WindowsAutoPilotInfo` cmdlet di PowerShell per raccogliere in remoto le informazioni dai dispositivi nei gruppi di Active Directory tramite WinRM.</span><span class="sxs-lookup"><span data-stu-id="71819-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="71819-137">È inoltre possibile utilizzare il `Get-AD Computer` cmdlet e ottenere i risultati filtrati per uno specifico nome di modello hardware incluso nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="71819-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="71819-138">Prima di procedere, confermare i prerequisiti e quindi procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="71819-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="71819-139">Gestione remota Windows è abilitata.</span><span class="sxs-lookup"><span data-stu-id="71819-139">WinRM is enabled.</span></span>
- <span data-ttu-id="71819-140">I dispositivi che si desidera registrare sono attivi sulla rete (ovvero non sono disconnessi o disattivati).</span><span class="sxs-lookup"><span data-stu-id="71819-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="71819-141">Verificare di disporre di un parametro di credenziali di dominio che disponga dell'autorizzazione per l'esecuzione remota sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="71819-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="71819-142">Verificare che Windows Firewall consenta l'accesso a WMI.</span><span class="sxs-lookup"><span data-stu-id="71819-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="71819-143">A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="71819-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="71819-144">Aprire il pannello di controllo di **Windows Defender Firewall** e selezionare **Consenti un'app o una funzionalità tramite il firewall di Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="71819-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="71819-145">Individuare **Windows Management Instrumentation (WMI)** nell'elenco, abilitare sia per il **privato che** per il pubblico, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="71819-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="71819-146">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="71819-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="71819-147">Eseguire *uno* di questi script:</span><span class="sxs-lookup"><span data-stu-id="71819-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="71819-148">Accedere a tutte le directory in cui possono essere presenti voci per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="71819-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="71819-149">Rimuovere le voci per ogni dispositivo da *tutte le* directory, inclusi i servizi di dominio di Windows Server Active Directory e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71819-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="71819-150">Tenere presente che la rimozione potrebbe richiedere alcune ore per elaborarla completamente.</span><span class="sxs-lookup"><span data-stu-id="71819-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="71819-151">Servizi di gestione accessi in cui possono essere presenti voci per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="71819-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="71819-152">Rimuovere le voci per ogni dispositivo da *tutti i* servizi di gestione, tra cui Microsoft endpoint Configuration Manager, Microsoft Intune e Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="71819-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="71819-153">Tenere presente che la rimozione potrebbe richiedere alcune ore per elaborarla completamente.</span><span class="sxs-lookup"><span data-stu-id="71819-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="71819-154">A questo punto è possibile procedere alla [registrazione di dispositivi](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="71819-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="71819-155">Metodo script di PowerShell manuale</span><span class="sxs-lookup"><span data-stu-id="71819-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="71819-156">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="71819-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="71819-157">Correre `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="71819-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="71819-158">Correre `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="71819-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="71819-159">Unire i dati hash.</span><span class="sxs-lookup"><span data-stu-id="71819-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="71819-160">Metodo dell'unità flash</span><span class="sxs-lookup"><span data-stu-id="71819-160">Flash drive method</span></span>

1. <span data-ttu-id="71819-161">In un dispositivo diverso da quello che si sta registrando, inserire un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="71819-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="71819-162">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="71819-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="71819-163">Correre `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="71819-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="71819-164">Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione*.</span><span class="sxs-lookup"><span data-stu-id="71819-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="71819-165">Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71819-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="71819-166">Inserire l'unità USB e quindi premere MAIUSC + F10.</span><span class="sxs-lookup"><span data-stu-id="71819-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="71819-167">Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguirlo `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="71819-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="71819-168">Correre `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="71819-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="71819-169">Correre `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="71819-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="71819-170">Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="71819-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="71819-171">Unire i dati hash.</span><span class="sxs-lookup"><span data-stu-id="71819-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="71819-172">Non accendere il dispositivo che si sta registrando di nuovo fino a quando non si è completata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="71819-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="71819-173">Unire i dati hash</span><span class="sxs-lookup"><span data-stu-id="71819-173">Merge hash data</span></span>

<span data-ttu-id="71819-174">Se i dati dell'hash hardware sono stati raccolti tramite i metodi di PowerShell manuale o di unità flash, è necessario che i dati dei file CSV siano combinati in un unico file per completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="71819-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="71819-175">Di seguito è indicato uno script PowerShell di esempio per agevolare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71819-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="71819-176">Con i dati hash Uniti in un unico file CSV, è ora possibile procedere alla [registrazione dei dispositivi](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="71819-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="71819-177">Registrare i dispositivi tramite il portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="71819-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="71819-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)selezionare **dispositivi** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="71819-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="71819-179">Cercare la sezione Microsoft Managed Desktop del menu e selezionare **dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="71819-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="71819-180">Nell'area di lavoro Microsoft Managed Desktop Devices selezionare **+ Register Devices**, che consente di aprire un Fly-in per registrare i nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="71819-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="71819-181">attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="71819-181">Follow these steps:</span></span>

1. <span data-ttu-id="71819-182">In **caricamento file**, specificare un percorso per il file CSV creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="71819-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="71819-183">Selezionare **registra dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="71819-183">Select **Register devices**.</span></span> <span data-ttu-id="71819-184">Il sistema aggiungerà i dispositivi all'elenco di dispositivi sul Blade dei **dispositivi**, contrassegnati come **registrazione in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="71819-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="71819-185">La registrazione richiede in genere meno di 10 minuti e, in caso di esito positivo, il dispositivo verrà visualizzato come **pronto per il significato dell'utente** è pronto e in attesa che un utente inizi a utilizzare.</span><span class="sxs-lookup"><span data-stu-id="71819-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="71819-186">È possibile monitorare lo stato di avanzamento della registrazione dei dispositivi nella pagina principale.</span><span class="sxs-lookup"><span data-stu-id="71819-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="71819-187">Gli stati possibili segnalati includono:</span><span class="sxs-lookup"><span data-stu-id="71819-187">Possible states reported there include:</span></span>

| <span data-ttu-id="71819-188">Stato</span><span class="sxs-lookup"><span data-stu-id="71819-188">State</span></span> | <span data-ttu-id="71819-189">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71819-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="71819-190">Registrazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="71819-190">Registration Pending</span></span> | <span data-ttu-id="71819-191">La registrazione non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="71819-191">Registration is not done yet.</span></span> <span data-ttu-id="71819-192">Controllare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="71819-192">Check back later.</span></span> |
| <span data-ttu-id="71819-193">Registrazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="71819-193">Registration failed</span></span> | <span data-ttu-id="71819-194">La registrazione non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="71819-194">Registration could not be completed.</span></span> <span data-ttu-id="71819-195">Per ulteriori informazioni, vedere [risoluzione dei problemi relativi alla registrazione del dispositivo](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="71819-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="71819-196">Pronto per l'utente</span><span class="sxs-lookup"><span data-stu-id="71819-196">Ready for user</span></span> | <span data-ttu-id="71819-197">La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente.</span><span class="sxs-lookup"><span data-stu-id="71819-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="71819-198">Microsoft Managed Desktop li guiderà per la prima volta, quindi non è necessario eseguire ulteriori preparativi.</span><span class="sxs-lookup"><span data-stu-id="71819-198">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="71819-199">Attivazione</span><span class="sxs-lookup"><span data-stu-id="71819-199">Active</span></span> | <span data-ttu-id="71819-200">Il dispositivo è stato recapitato all'utente ed è stato registrato con il tenant.</span><span class="sxs-lookup"><span data-stu-id="71819-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="71819-201">Questo indica anche che stanno usando regolarmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71819-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="71819-202">Inattivo</span><span class="sxs-lookup"><span data-stu-id="71819-202">Inactive</span></span> | <span data-ttu-id="71819-203">Il dispositivo è stato recapitato all'utente ed è stato registrato con il tenant.</span><span class="sxs-lookup"><span data-stu-id="71819-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="71819-204">Tuttavia, non hanno utilizzato il dispositivo di recente (negli ultimi 7 giorni).</span><span class="sxs-lookup"><span data-stu-id="71819-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="71819-205">Risoluzione dei problemi relativi alla registrazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="71819-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="71819-206">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="71819-206">Error message</span></span> | <span data-ttu-id="71819-207">Dettagli</span><span class="sxs-lookup"><span data-stu-id="71819-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="71819-208">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="71819-208">Device not found</span></span> | <span data-ttu-id="71819-209">Non è stato possibile registrare il dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato.</span><span class="sxs-lookup"><span data-stu-id="71819-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="71819-210">Confermare questi valori con il fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71819-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="71819-211">Hash hardware non valido</span><span class="sxs-lookup"><span data-stu-id="71819-211">Hardware hash not valid</span></span> | <span data-ttu-id="71819-212">L'hash hardware fornito per il dispositivo non è stato formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="71819-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="71819-213">Fare doppio check sull'hash hardware e quindi inviare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="71819-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="71819-214">Dispositivo già registrato</span><span class="sxs-lookup"><span data-stu-id="71819-214">Device already registered</span></span> | <span data-ttu-id="71819-215">Questo dispositivo è già registrato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="71819-215">This device is already registered to your organization.</span></span> <span data-ttu-id="71819-216">Non sono necessarie ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="71819-216">No further action required.</span></span> |
| <span data-ttu-id="71819-217">Dispositivo rivendicato da un'altra organizzazione</span><span class="sxs-lookup"><span data-stu-id="71819-217">Device claimed by another organization</span></span> | <span data-ttu-id="71819-218">Questo dispositivo è già stato rivendicato da un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="71819-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="71819-219">Controllare con il fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71819-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="71819-220">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="71819-220">Unexpected error</span></span> | <span data-ttu-id="71819-221">La richiesta non è stata elaborata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="71819-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="71819-222">Contattare il supporto tecnico e fornire l'ID richiesta: <requestId></span><span class="sxs-lookup"><span data-stu-id="71819-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="71819-223">Controllare l'immagine</span><span class="sxs-lookup"><span data-stu-id="71819-223">Check the image</span></span>

<span data-ttu-id="71819-224">Se il dispositivo proviene da un fornitore di partner di Microsoft Managed Desktop, è necessario che l'immagine sia corretta.</span><span class="sxs-lookup"><span data-stu-id="71819-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="71819-225">Se si preferisce, è anche possibile applicare l'immagine da soli.</span><span class="sxs-lookup"><span data-stu-id="71819-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="71819-226">Per iniziare, contattare il rappresentante Microsoft che si sta utilizzando e fornirà la posizione e i passaggi per l'applicazione dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="71819-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="71819-227">Recapito del dispositivo</span><span class="sxs-lookup"><span data-stu-id="71819-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71819-228">Prima di distribuire il dispositivo all'utente, verificare di aver ottenuto e applicato le [licenze appropriate](../get-ready/prerequisites.md) per l'utente.</span><span class="sxs-lookup"><span data-stu-id="71819-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="71819-229">Se vengono applicate tutte le licenze, è possibile [ottenere gli utenti pronti per l'utilizzo dei dispositivi](get-started-devices.md)e quindi l'utente può avviare il dispositivo e procedere con l'esperienza di installazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="71819-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









