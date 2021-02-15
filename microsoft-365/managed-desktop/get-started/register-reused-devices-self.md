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
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="58c16-103">Registrare manualmente i dispositivi già presenti</span><span class="sxs-lookup"><span data-stu-id="58c16-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="58c16-104">In questo argomento vengono descritti i passaggi necessari per riutilizzare i dispositivi già presenti e registrarli in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="58c16-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="58c16-105">Se si lavora con dispositivi nuovi, seguire la procedura descritta in Registrare i nuovi [dispositivi in Microsoft Managed Desktop.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="58c16-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="58c16-106">Il processo per i partner è documentato in [Passaggi per i partner per registrare i dispositivi.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="58c16-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="58c16-107">Microsoft Managed Desktop può funzionare con dispositivi completamente nuovi oppure è possibile riutilizzare i dispositivi già disponibili (che richiederanno di ricrearne l'immagine).</span><span class="sxs-lookup"><span data-stu-id="58c16-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="58c16-108">Puoi registrare i dispositivi con Microsoft Managed Desktop nel portale di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="58c16-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="58c16-109">Preparare la registrazione dei dispositivi esistenti</span><span class="sxs-lookup"><span data-stu-id="58c16-109">Prepare to register existing devices</span></span>


<span data-ttu-id="58c16-110">Per registrare i dispositivi esistenti, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="58c16-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="58c16-111">Ottenere l'hash hardware per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58c16-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="58c16-112">Unire i dati hash</span><span class="sxs-lookup"><span data-stu-id="58c16-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="58c16-113">[Registrare i dispositivi in Microsoft Managed Desktop.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="58c16-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="58c16-114">Verifica che l'immagine sia corretta.</span><span class="sxs-lookup"><span data-stu-id="58c16-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="58c16-115">Recapitare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="58c16-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="58c16-116">Ottenere l'hash hardware</span><span class="sxs-lookup"><span data-stu-id="58c16-116">Obtain the hardware hash</span></span>

<span data-ttu-id="58c16-117">Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware.</span><span class="sxs-lookup"><span data-stu-id="58c16-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="58c16-118">Sono disponibili quattro opzioni per ottenere queste informazioni dai dispositivi già in uso:</span><span class="sxs-lookup"><span data-stu-id="58c16-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="58c16-119">Chiedere al fornitore OEM il file di registrazione AutoPilot, che includerà gli hash hardware.</span><span class="sxs-lookup"><span data-stu-id="58c16-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="58c16-120">Raccogliere informazioni in [Microsoft Endpoint Configuration Manager.](#microsoft-endpoint-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="58c16-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="58c16-121">Eseguire uno script Windows PowerShell, utilizzando [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) in ogni dispositivo, e raccogliere i risultati in un file.</span><span class="sxs-lookup"><span data-stu-id="58c16-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="58c16-122">Avvia ogni dispositivo, ma non completa l'esperienza di installazione di Windows, e raccogli gli hash in un'unità [flash rimovibile.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="58c16-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="58c16-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="58c16-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="58c16-124">Puoi usare Microsoft Endpoint Configuration Manager per raccogliere gli hash hardware dai dispositivi esistenti che vuoi registrare in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="58c16-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58c16-125">Tutti i dispositivi per cui vuoi ottenere queste informazioni devono eseguire Windows 10 versione 1703 o successiva.</span><span class="sxs-lookup"><span data-stu-id="58c16-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="58c16-126">Se sono stati soddisfatti tutti questi prerequisiti, è possibile raccogliere le informazioni seguendo questa procedura:</span><span class="sxs-lookup"><span data-stu-id="58c16-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="58c16-127">Nella console di Configuration Manager selezionare **Monitoraggio.**</span><span class="sxs-lookup"><span data-stu-id="58c16-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="58c16-128">Nell'area di lavoro Monitoraggio espandere il nodo **Report,** espandere **Report** e selezionare il **nodo Hardware - Generale.**</span><span class="sxs-lookup"><span data-stu-id="58c16-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="58c16-129">Esegui il report, **Windows Autopilot Device Information** e visualizza i risultati.</span><span class="sxs-lookup"><span data-stu-id="58c16-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="58c16-130">Nel visualizzatore di  report selezionare l'icona Esporta e scegliere l'opzione **CSV (delimitato da virgole).**</span><span class="sxs-lookup"><span data-stu-id="58c16-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="58c16-131">Dopo aver salvato il file, sarà necessario filtrare i risultati solo nei dispositivi che si prevede di registrare con Microsoft Managed Desktop e caricare i dati in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="58c16-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="58c16-132">Apri Microsoft Endpoint Manager e passa al menu **Dispositivi,** quindi cerca la sezione Microsoft Managed Desktop e seleziona **Dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="58c16-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="58c16-133">Seleziona **+ Registra dispositivi**, che apre un riquadro a comparsa per registrare i nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="58c16-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="58c16-134">Per altre [informazioni, fare riferimento](#register-devices-by-using-the-admin-portal) a Registrare i dispositivi tramite il portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="58c16-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="58c16-135">Metodo di script di PowerShell di Active Directory</span><span class="sxs-lookup"><span data-stu-id="58c16-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="58c16-136">In un ambiente Active Directory, è possibile utilizzare il cmdlet di PowerShell per raccogliere in remoto le informazioni dai dispositivi nei gruppi di `Get-WindowsAutoPilotInfo` Active Directory tramite WinRM.</span><span class="sxs-lookup"><span data-stu-id="58c16-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="58c16-137">È inoltre possibile utilizzare il `Get-AD Computer` cmdlet e ottenere risultati filtrati per un nome di modello hardware specifico incluso nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="58c16-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="58c16-138">Prima di procedere, verificare questi prerequisiti e quindi procedere con i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="58c16-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="58c16-139">WinRM è abilitato.</span><span class="sxs-lookup"><span data-stu-id="58c16-139">WinRM is enabled.</span></span>
- <span data-ttu-id="58c16-140">I dispositivi da registrare sono attivi nella rete, ovvero non sono disconnessi o disattivati.</span><span class="sxs-lookup"><span data-stu-id="58c16-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="58c16-141">Assicurati di disporre di un parametro delle credenziali di dominio che dispone dell'autorizzazione per l'esecuzione in remoto nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="58c16-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="58c16-142">Assicurarsi che Windows Firewall consenta l'accesso a WMI.</span><span class="sxs-lookup"><span data-stu-id="58c16-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="58c16-143">A tale scopo, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="58c16-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="58c16-144">Apri il **Windows Defender di controllo del firewall** e seleziona Consenti **un'app** o una funzionalità tramite Windows Defender Firewall.</span><span class="sxs-lookup"><span data-stu-id="58c16-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="58c16-145">Trova **Strumentazione gestione Windows (WMI)** nell'elenco, abilita sia per **Private che per Public** e quindi seleziona **OK.**</span><span class="sxs-lookup"><span data-stu-id="58c16-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="58c16-146">Apri un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="58c16-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="58c16-147">Eseguire *uno di* questi script:</span><span class="sxs-lookup"><span data-stu-id="58c16-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="58c16-148">Accedere a tutte le directory in cui potrebbero essere presenti voci per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="58c16-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="58c16-149">Rimuovere le voci per ogni dispositivo da *tutte le* directory, inclusi Servizi di dominio Active Directory di Windows Server e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58c16-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="58c16-150">Tenere presente che l'elaborazione completa della rimozione potrebbe richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="58c16-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="58c16-151">Accedere ai servizi di gestione in cui potrebbero essere presenti voci per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="58c16-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="58c16-152">Rimuovi le voci per ogni dispositivo da *tutti i* servizi di gestione, tra cui Microsoft Endpoint Configuration Manager, Microsoft Intune e Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="58c16-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="58c16-153">Tenere presente che l'elaborazione completa della rimozione potrebbe richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="58c16-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="58c16-154">Ora puoi procedere con la [registrazione dei dispositivi.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="58c16-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="58c16-155">Metodo di script di PowerShell manuale</span><span class="sxs-lookup"><span data-stu-id="58c16-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="58c16-156">Apri un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="58c16-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="58c16-157">Correre `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="58c16-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="58c16-158">Correre `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="58c16-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="58c16-159">Unire i dati hash.</span><span class="sxs-lookup"><span data-stu-id="58c16-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="58c16-160">Metodo di unità flash</span><span class="sxs-lookup"><span data-stu-id="58c16-160">Flash drive method</span></span>

1. <span data-ttu-id="58c16-161">In un dispositivo diverso da quello che stai registrando, inserisci un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="58c16-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="58c16-162">Apri un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="58c16-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="58c16-163">Correre `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="58c16-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="58c16-164">Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione.*</span><span class="sxs-lookup"><span data-stu-id="58c16-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="58c16-165">Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare l'immagine del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58c16-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="58c16-166">Inserire l'unità USB e quindi premere MAIUSC+F10.</span><span class="sxs-lookup"><span data-stu-id="58c16-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="58c16-167">Aprire un prompt di PowerShell con diritti amministrativi ed eseguire `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="58c16-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="58c16-168">Correre `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="58c16-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="58c16-169">Correre `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="58c16-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="58c16-170">Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="58c16-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="58c16-171">Unire i dati hash.</span><span class="sxs-lookup"><span data-stu-id="58c16-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="58c16-172">Non accensione del dispositivo che stai registrando di nuovo fino a quando non hai completato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="58c16-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="58c16-173">Unire dati hash</span><span class="sxs-lookup"><span data-stu-id="58c16-173">Merge hash data</span></span>

<span data-ttu-id="58c16-174">Se i dati hash hardware sono stati raccolti con i metodi manuali di PowerShell o unità flash, è ora necessario combinare i dati nei file CSV in un unico file per completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="58c16-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="58c16-175">Ecco uno script di PowerShell di esempio per semplificare:</span><span class="sxs-lookup"><span data-stu-id="58c16-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="58c16-176">Con i dati hash uniti in un unico file CSV, è ora possibile procedere alla [registrazione dei dispositivi.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="58c16-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="58c16-177">Registrare i dispositivi tramite il portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="58c16-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="58c16-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)seleziona Dispositivi **nel** riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="58c16-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="58c16-179">Cerca la sezione Microsoft Managed Desktop del menu e seleziona **Dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="58c16-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="58c16-180">Nell'area di lavoro Microsoft Managed Desktop Devices seleziona **+ Registra** dispositivi, che apre un riquadro a comparsa per registrare i nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="58c16-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="58c16-181">attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="58c16-181">Follow these steps:</span></span>

1. <span data-ttu-id="58c16-182">In **Caricamento file** specificare il percorso del file CSV creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="58c16-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="58c16-183">Selezionare **Registra dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="58c16-183">Select **Register devices**.</span></span> <span data-ttu-id="58c16-184">Il sistema aggiungerà i dispositivi all'elenco dei dispositivi nel **pannello** Dispositivi, contrassegnati come in sospeso **per la registrazione.**</span><span class="sxs-lookup"><span data-stu-id="58c16-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="58c16-185">La registrazione in genere richiede meno di 10  minuti e, se l'operazione riesce, il dispositivo viene visualizzato come Pronto per l'utente, ovvero è pronto e in attesa che l'utente inizi a usare.</span><span class="sxs-lookup"><span data-stu-id="58c16-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="58c16-186">Puoi monitorare l'avanzamento della registrazione del dispositivo nella pagina principale.</span><span class="sxs-lookup"><span data-stu-id="58c16-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="58c16-187">Gli stati possibili segnalati includono:</span><span class="sxs-lookup"><span data-stu-id="58c16-187">Possible states reported there include:</span></span>

| <span data-ttu-id="58c16-188">Stato</span><span class="sxs-lookup"><span data-stu-id="58c16-188">State</span></span> | <span data-ttu-id="58c16-189">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58c16-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="58c16-190">Registrazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="58c16-190">Registration Pending</span></span> | <span data-ttu-id="58c16-191">La registrazione non è ancora stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="58c16-191">Registration is not done yet.</span></span> <span data-ttu-id="58c16-192">Riestrarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="58c16-192">Check back later.</span></span> |
| <span data-ttu-id="58c16-193">Registrazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="58c16-193">Registration failed</span></span> | <span data-ttu-id="58c16-194">Impossibile completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="58c16-194">Registration could not be completed.</span></span> <span data-ttu-id="58c16-195">Per altre [informazioni, fai](#troubleshooting-device-registration) riferimento a Risoluzione dei problemi di registrazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="58c16-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="58c16-196">Pronto per l'utente</span><span class="sxs-lookup"><span data-stu-id="58c16-196">Ready for user</span></span> | <span data-ttu-id="58c16-197">La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente.</span><span class="sxs-lookup"><span data-stu-id="58c16-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="58c16-198">Microsoft Managed Desktop li guiderà nella configurazione della prima volta, quindi non è necessario eseguire ulteriori operazioni di preparazione.</span><span class="sxs-lookup"><span data-stu-id="58c16-198">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="58c16-199">Attivazione</span><span class="sxs-lookup"><span data-stu-id="58c16-199">Active</span></span> | <span data-ttu-id="58c16-200">Il dispositivo è stato recapitato all'utente e registrato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="58c16-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="58c16-201">Questo indica anche che usano regolarmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58c16-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="58c16-202">Inattivo</span><span class="sxs-lookup"><span data-stu-id="58c16-202">Inactive</span></span> | <span data-ttu-id="58c16-203">Il dispositivo è stato recapitato all'utente e registrato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="58c16-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="58c16-204">Tuttavia, non hanno usato il dispositivo di recente (negli ultimi 7 giorni).</span><span class="sxs-lookup"><span data-stu-id="58c16-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="58c16-205">Risoluzione dei problemi di registrazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="58c16-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="58c16-206">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="58c16-206">Error message</span></span> | <span data-ttu-id="58c16-207">Dettagli</span><span class="sxs-lookup"><span data-stu-id="58c16-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="58c16-208">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="58c16-208">Device not found</span></span> | <span data-ttu-id="58c16-209">Non è stato possibile registrare questo dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato.</span><span class="sxs-lookup"><span data-stu-id="58c16-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="58c16-210">Verificare questi valori con il fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58c16-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="58c16-211">Hash hardware non valido</span><span class="sxs-lookup"><span data-stu-id="58c16-211">Hardware hash not valid</span></span> | <span data-ttu-id="58c16-212">L'hash hardware fornito per questo dispositivo non è stato formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="58c16-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="58c16-213">Controlla l'hash hardware e quindi reinvio.</span><span class="sxs-lookup"><span data-stu-id="58c16-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="58c16-214">Dispositivo già registrato</span><span class="sxs-lookup"><span data-stu-id="58c16-214">Device already registered</span></span> | <span data-ttu-id="58c16-215">Questo dispositivo è già registrato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58c16-215">This device is already registered to your organization.</span></span> <span data-ttu-id="58c16-216">Non sono necessarie ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="58c16-216">No further action required.</span></span> |
| <span data-ttu-id="58c16-217">Dispositivo richiesto da un'altra organizzazione</span><span class="sxs-lookup"><span data-stu-id="58c16-217">Device claimed by another organization</span></span> | <span data-ttu-id="58c16-218">Questo dispositivo è già stato richiesto da un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58c16-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="58c16-219">Rivolgersi al fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58c16-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="58c16-220">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="58c16-220">Unexpected error</span></span> | <span data-ttu-id="58c16-221">Non è stato possibile elaborare automaticamente la richiesta.</span><span class="sxs-lookup"><span data-stu-id="58c16-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="58c16-222">Contattare il supporto tecnico e fornire l'ID richiesta: <requestId></span><span class="sxs-lookup"><span data-stu-id="58c16-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="58c16-223">Controllare l'immagine</span><span class="sxs-lookup"><span data-stu-id="58c16-223">Check the image</span></span>

<span data-ttu-id="58c16-224">Se il dispositivo è stato provengono da un fornitore partner Microsoft Managed Desktop, l'immagine dovrebbe essere corretta.</span><span class="sxs-lookup"><span data-stu-id="58c16-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="58c16-225">Puoi anche applicare l'immagine da solo, se preferisci.</span><span class="sxs-lookup"><span data-stu-id="58c16-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="58c16-226">To get started, contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="58c16-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="58c16-227">Recapitare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="58c16-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58c16-228">Prima di consegnare il dispositivo all'utente, assicurati di aver ottenuto e applicato le [licenze appropriate](../get-ready/prerequisites.md) per tale utente.</span><span class="sxs-lookup"><span data-stu-id="58c16-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="58c16-229">Se vengono applicate tutte le [](get-started-devices.md)licenze, puoi fare in modo che gli utenti siano pronti a usare i dispositivi e quindi l'utente può avviare il dispositivo e procedere con l'esperienza di installazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="58c16-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









