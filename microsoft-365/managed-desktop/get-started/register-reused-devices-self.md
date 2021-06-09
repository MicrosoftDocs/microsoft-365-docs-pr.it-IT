---
title: Registrare manualmente i dispositivi già presenti
description: Registrare i dispositivi riutilizzati che potresti già avere in modo che possano essere gestiti da Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 21b0062a337dbeb3c7dec8b715971dbbc4917db1
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893276"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="98c59-103">Registrare manualmente i dispositivi già presenti</span><span class="sxs-lookup"><span data-stu-id="98c59-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="98c59-104">Questo argomento descrive i passaggi necessari per riutilizzare i dispositivi già presenti e registrarli in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="98c59-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="98c59-105">Se stai lavorando con dispositivi nuovi, segui i passaggi descritti [in Registrare](register-devices-self.md) i nuovi dispositivi in Microsoft Managed Desktop te stesso.</span><span class="sxs-lookup"><span data-stu-id="98c59-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="98c59-106">Il processo per i partner è documentato in [Passaggi per i partner per registrare i dispositivi](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="98c59-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="98c59-107">Microsoft Managed Desktop possono funzionare con dispositivi nuovi o puoi riutilizzare i dispositivi che potresti già avere (che richiederanno di ricrearne l'immagine).</span><span class="sxs-lookup"><span data-stu-id="98c59-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="98c59-108">Puoi registrare i dispositivi con Microsoft Managed Desktop nel Microsoft Endpoint Manager portale.</span><span class="sxs-lookup"><span data-stu-id="98c59-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="98c59-109">Preparare la registrazione dei dispositivi esistenti</span><span class="sxs-lookup"><span data-stu-id="98c59-109">Prepare to register existing devices</span></span>


<span data-ttu-id="98c59-110">Per registrare i dispositivi esistenti, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="98c59-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="98c59-111">Ottenere l'hash hardware per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98c59-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="98c59-112">Unire i dati hash</span><span class="sxs-lookup"><span data-stu-id="98c59-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="98c59-113">[Registrare i dispositivi in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="98c59-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="98c59-114">Verificare che l'immagine sia corretta.</span><span class="sxs-lookup"><span data-stu-id="98c59-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="98c59-115">Recapita il dispositivo</span><span class="sxs-lookup"><span data-stu-id="98c59-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="98c59-116">Ottenere l'hash hardware</span><span class="sxs-lookup"><span data-stu-id="98c59-116">Obtain the hardware hash</span></span>

<span data-ttu-id="98c59-117">Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware.</span><span class="sxs-lookup"><span data-stu-id="98c59-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="98c59-118">Sono disponibili quattro opzioni per ottenere queste informazioni dai dispositivi già in uso:</span><span class="sxs-lookup"><span data-stu-id="98c59-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="98c59-119">Chiedere al fornitore OEM il file di registrazione AutoPilot, che includerà gli hash hardware.</span><span class="sxs-lookup"><span data-stu-id="98c59-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="98c59-120">Raccogliere informazioni in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="98c59-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="98c59-121">Eseguire uno script Windows PowerShell, utilizzando Active [](#manual-powershell-script-method) [Directory](#active-directory-powershell-script-method) o manualmente in ogni dispositivo, e raccogliere i risultati in un file.</span><span class="sxs-lookup"><span data-stu-id="98c59-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="98c59-122">Avviare ogni dispositivo, ma non completare l'Windows di installazione, e raccogliere gli hash in un'unità [flash rimovibile.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="98c59-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="98c59-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="98c59-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="98c59-124">Puoi usare Microsoft Endpoint Configuration Manager per raccogliere gli hash hardware dai dispositivi esistenti che vuoi registrare con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="98c59-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98c59-125">Tutti i dispositivi per cui vuoi ottenere queste informazioni devono essere Windows 10 versione 1703 o successiva.</span><span class="sxs-lookup"><span data-stu-id="98c59-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="98c59-126">Se sono stati soddisfatti tutti questi prerequisiti, è possibile raccogliere le informazioni seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="98c59-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="98c59-127">Nella console di Configuration Manager selezionare **Monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="98c59-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="98c59-128">Nell'area di lavoro Monitoraggio espandere il **nodo Report,** espandere **Report** e selezionare il **nodo Hardware - Generale.**</span><span class="sxs-lookup"><span data-stu-id="98c59-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="98c59-129">Eseguire il report, Windows informazioni sul dispositivo **Autopilot** e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="98c59-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="98c59-130">Nel visualizzatore di report seleziona **l'icona** Esporta e scegli l'opzione **CSV (delimitato da virgole).**</span><span class="sxs-lookup"><span data-stu-id="98c59-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="98c59-131">Dopo aver salvato il file, dovrai filtrare i risultati solo nei dispositivi che vuoi registrare con Microsoft Managed Desktop e caricare i dati in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="98c59-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="98c59-132">Apri Microsoft Endpoint Manager e passa al menu **Dispositivi,** quindi cerca la Microsoft Managed Desktop e seleziona **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="98c59-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="98c59-133">Seleziona **+ Registra dispositivi**, che apre un fly-in per registrare nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="98c59-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="98c59-134">Per altre [informazioni, vedere Registrare i dispositivi](#register-devices-by-using-the-admin-portal) tramite il portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="98c59-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="98c59-135">Metodo script di PowerShell di Active Directory</span><span class="sxs-lookup"><span data-stu-id="98c59-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="98c59-136">In un ambiente Active Directory, è possibile utilizzare il cmdlet PowerShell per raccogliere in remoto le informazioni dai dispositivi nei gruppi di `Get-WindowsAutoPilotInfo` Active Directory tramite WinRM.</span><span class="sxs-lookup"><span data-stu-id="98c59-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="98c59-137">È inoltre possibile utilizzare il `Get-AD Computer` cmdlet e ottenere risultati filtrati per un nome di modello hardware specifico incluso nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="98c59-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="98c59-138">Prima di procedere, verificare prima questi prerequisiti e quindi procedere con i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="98c59-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="98c59-139">WinRM è abilitato.</span><span class="sxs-lookup"><span data-stu-id="98c59-139">WinRM is enabled.</span></span>
- <span data-ttu-id="98c59-140">I dispositivi da registrare sono attivi nella rete, ovvero non sono disconnessi o disattivati.</span><span class="sxs-lookup"><span data-stu-id="98c59-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="98c59-141">Assicurati di disporre di un parametro delle credenziali di dominio che dispone dell'autorizzazione per l'esecuzione in remoto nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="98c59-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="98c59-142">Assicurarsi che Windows Firewall consenta l'accesso a WMI.</span><span class="sxs-lookup"><span data-stu-id="98c59-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="98c59-143">A tale scopo, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="98c59-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="98c59-144">Apri il **Windows Defender Firewall** di controllo e seleziona **Consenti un'app o una funzionalità tramite Windows Defender Firewall**.</span><span class="sxs-lookup"><span data-stu-id="98c59-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="98c59-145">Trova **Windows Strumentazione gestione Windows (WMI)** nell'elenco, abilita sia per **Private che per Public** e quindi seleziona **OK.**</span><span class="sxs-lookup"><span data-stu-id="98c59-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="98c59-146">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="98c59-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="98c59-147">Eseguire *uno di* questi script:</span><span class="sxs-lookup"><span data-stu-id="98c59-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="98c59-148">Accedere a tutte le directory in cui potrebbero essere presenti voci per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="98c59-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="98c59-149">Rimuovere le voci per ogni dispositivo da *tutte le* directory, inclusi Windows Server Servizi di dominio Active Directory e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98c59-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="98c59-150">Tenere presente che l'elaborazione completa della rimozione potrebbe richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="98c59-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="98c59-151">Accedere ai servizi di gestione in cui potrebbero essere presenti voci per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="98c59-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="98c59-152">Rimuovi le voci per ogni dispositivo da *tutti* i servizi di gestione, inclusi Microsoft Endpoint Configuration Manager, Microsoft Intune e Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="98c59-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="98c59-153">Tenere presente che l'elaborazione completa della rimozione potrebbe richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="98c59-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="98c59-154">Ora puoi procedere con la [registrazione dei dispositivi](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="98c59-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="98c59-155">Metodo di script manuale di PowerShell</span><span class="sxs-lookup"><span data-stu-id="98c59-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="98c59-156">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="98c59-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="98c59-157">Correre `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="98c59-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="98c59-158">Correre `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="98c59-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="98c59-159">Unire i dati hash.</span><span class="sxs-lookup"><span data-stu-id="98c59-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="98c59-160">Flash drive, metodo</span><span class="sxs-lookup"><span data-stu-id="98c59-160">Flash drive method</span></span>

1. <span data-ttu-id="98c59-161">In un dispositivo diverso da quello che stai registrando, inserisci un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="98c59-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="98c59-162">Aprire un prompt di PowerShell con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="98c59-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="98c59-163">Correre `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="98c59-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="98c59-164">Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione.*</span><span class="sxs-lookup"><span data-stu-id="98c59-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="98c59-165">Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare l'immagine del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98c59-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="98c59-166">Inserire l'unità USB e quindi premere MAIUSC + F10.</span><span class="sxs-lookup"><span data-stu-id="98c59-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="98c59-167">Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguire `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="98c59-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="98c59-168">Correre `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="98c59-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="98c59-169">Correre `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="98c59-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="98c59-170">Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="98c59-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="98c59-171">Unire i dati hash.</span><span class="sxs-lookup"><span data-stu-id="98c59-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="98c59-172">Non alimentare il dispositivo che stai registrando di nuovo finché non hai completato la registrazione.</span><span class="sxs-lookup"><span data-stu-id="98c59-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="98c59-173">Unire dati hash</span><span class="sxs-lookup"><span data-stu-id="98c59-173">Merge hash data</span></span>

<span data-ttu-id="98c59-174">Se i dati hash hardware sono stati raccolti tramite i metodi manuali di PowerShell o dell'unità flash, è ora necessario che i dati nei file CSV si unino in un unico file per completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="98c59-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="98c59-175">Ecco uno script di PowerShell di esempio per semplificare:</span><span class="sxs-lookup"><span data-stu-id="98c59-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="98c59-176">Con i dati hash uniti in un unico file CSV, ora puoi procedere alla [registrazione dei dispositivi](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="98c59-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


## <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="98c59-177">Registrare i dispositivi tramite il portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="98c59-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="98c59-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)selezionare **Dispositivi nel** riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="98c59-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="98c59-179">Cerca la sezione Microsoft Managed Desktop del menu e seleziona **Dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="98c59-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="98c59-180">Nell'Microsoft Managed Desktop di lavoro Dispositivi, seleziona **+ Registra dispositivi**, che apre un riquadro a comparsa per registrare nuovi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="98c59-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="98c59-181">Eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="98c59-181">Follow these steps:</span></span>

1. <span data-ttu-id="98c59-182">In **Caricamento file** specificare il percorso del file CSV creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="98c59-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="98c59-183">Seleziona un [profilo di](../service-description/profiles.md) dispositivo nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="98c59-183">Select a [device profile](../service-description/profiles.md) in the drop-down menu.</span></span>
3. <span data-ttu-id="98c59-184">Selezionare **Registra dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="98c59-184">Select **Register devices**.</span></span> <span data-ttu-id="98c59-185">Il sistema aggiungerà i dispositivi all'elenco dei dispositivi nel **pannello Dispositivi,** contrassegnati come **Registrazione in sospeso.**</span><span class="sxs-lookup"><span data-stu-id="98c59-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="98c59-186">La registrazione in genere richiede meno di 10 minuti e quando il dispositivo ha esito positivo il dispositivo viene visualizzato come **Pronto** per l'utente, ovvero è pronto e in attesa che un utente inizi a usare.</span><span class="sxs-lookup"><span data-stu-id="98c59-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>

> [!NOTE]
> <span data-ttu-id="98c59-187">Se si modifica manualmente l'appartenenza al gruppo di Azure Active Directory (AAD) di un dispositivo, questo verrà automaticamente riassegnato al gruppo per il profilo del dispositivo e rimosso da eventuali gruppi in conflitto.</span><span class="sxs-lookup"><span data-stu-id="98c59-187">If you manually change the Azure Active Directory (AAD) group membership of a device, it will be automatically reassigned to the group for its device profile and removed from any conflicting groups.</span></span>

<span data-ttu-id="98c59-188">Puoi monitorare l'avanzamento della registrazione del dispositivo nella pagina principale.</span><span class="sxs-lookup"><span data-stu-id="98c59-188">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="98c59-189">Tra i possibili stati segnalati vi sono:</span><span class="sxs-lookup"><span data-stu-id="98c59-189">Possible states reported there include:</span></span>

| <span data-ttu-id="98c59-190">Stato</span><span class="sxs-lookup"><span data-stu-id="98c59-190">State</span></span> | <span data-ttu-id="98c59-191">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98c59-191">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="98c59-192">Registrazione in sospeso</span><span class="sxs-lookup"><span data-stu-id="98c59-192">Registration Pending</span></span> | <span data-ttu-id="98c59-193">La registrazione non è ancora stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="98c59-193">Registration is not done yet.</span></span> <span data-ttu-id="98c59-194">Eseguire il check back in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="98c59-194">Check back later.</span></span> |
| <span data-ttu-id="98c59-195">Registrazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="98c59-195">Registration failed</span></span> | <span data-ttu-id="98c59-196">Impossibile completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="98c59-196">Registration could not be completed.</span></span> <span data-ttu-id="98c59-197">Per ulteriori [informazioni, vedere Risoluzione dei](#troubleshooting-device-registration) problemi di registrazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="98c59-197">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="98c59-198">Pronto per l'utente</span><span class="sxs-lookup"><span data-stu-id="98c59-198">Ready for user</span></span> | <span data-ttu-id="98c59-199">La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente.</span><span class="sxs-lookup"><span data-stu-id="98c59-199">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="98c59-200">Microsoft Managed Desktop le guiderà attraverso la prima configurazione, quindi non è necessario eseguire ulteriori operazioni di preparazione.</span><span class="sxs-lookup"><span data-stu-id="98c59-200">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="98c59-201">Attivazione</span><span class="sxs-lookup"><span data-stu-id="98c59-201">Active</span></span> | <span data-ttu-id="98c59-202">Il dispositivo è stato recapitato all'utente e si è registrato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="98c59-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="98c59-203">Questo indica anche che usano regolarmente il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98c59-203">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="98c59-204">Inattivo</span><span class="sxs-lookup"><span data-stu-id="98c59-204">Inactive</span></span> | <span data-ttu-id="98c59-205">Il dispositivo è stato recapitato all'utente e si è registrato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="98c59-205">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="98c59-206">Tuttavia, non hanno usato il dispositivo di recente (negli ultimi 7 giorni).</span><span class="sxs-lookup"><span data-stu-id="98c59-206">However, they have not used the device recently (in the last 7 days).</span></span>  | 

### <a name="troubleshooting-device-registration"></a><span data-ttu-id="98c59-207">Risoluzione dei problemi di registrazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="98c59-207">Troubleshooting device registration</span></span>

| <span data-ttu-id="98c59-208">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="98c59-208">Error message</span></span> | <span data-ttu-id="98c59-209">Dettagli</span><span class="sxs-lookup"><span data-stu-id="98c59-209">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="98c59-210">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="98c59-210">Device not found</span></span> | <span data-ttu-id="98c59-211">Non è stato possibile registrare questo dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato.</span><span class="sxs-lookup"><span data-stu-id="98c59-211">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="98c59-212">Conferma questi valori con il fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98c59-212">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="98c59-213">Hash hardware non valido</span><span class="sxs-lookup"><span data-stu-id="98c59-213">Hardware hash not valid</span></span> | <span data-ttu-id="98c59-214">L'hash hardware specificato per questo dispositivo non è stato formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="98c59-214">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="98c59-215">Controlla due volte l'hash hardware e quindi invia di nuovo.</span><span class="sxs-lookup"><span data-stu-id="98c59-215">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="98c59-216">Dispositivo già registrato</span><span class="sxs-lookup"><span data-stu-id="98c59-216">Device already registered</span></span> | <span data-ttu-id="98c59-217">Questo dispositivo è già registrato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="98c59-217">This device is already registered to your organization.</span></span> <span data-ttu-id="98c59-218">Non sono necessarie ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="98c59-218">No further action required.</span></span> |
| <span data-ttu-id="98c59-219">Dispositivo richiesto da un'altra organizzazione</span><span class="sxs-lookup"><span data-stu-id="98c59-219">Device claimed by another organization</span></span> | <span data-ttu-id="98c59-220">Questo dispositivo è già stato rivendicato da un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="98c59-220">This device has already been claimed by another organization.</span></span> <span data-ttu-id="98c59-221">Rivolgersi al fornitore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98c59-221">Check with your device supplier.</span></span> |
| <span data-ttu-id="98c59-222">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="98c59-222">Unexpected error</span></span> | <span data-ttu-id="98c59-223">Impossibile elaborare automaticamente la richiesta.</span><span class="sxs-lookup"><span data-stu-id="98c59-223">Your request could not be automatically processed.</span></span> <span data-ttu-id="98c59-224">Contattare il supporto tecnico e fornire l'ID richiesta: <requestId></span><span class="sxs-lookup"><span data-stu-id="98c59-224">Contact Support and provide the Request ID: <requestId></span></span> |

## <a name="check-the-image"></a><span data-ttu-id="98c59-225">Controllare l'immagine</span><span class="sxs-lookup"><span data-stu-id="98c59-225">Check the image</span></span>

<span data-ttu-id="98c59-226">Se il dispositivo viene da un Microsoft Managed Desktop partner, l'immagine deve essere corretta.</span><span class="sxs-lookup"><span data-stu-id="98c59-226">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="98c59-227">Se preferisci, puoi anche applicare l'immagine da solo.</span><span class="sxs-lookup"><span data-stu-id="98c59-227">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="98c59-228">To get started, contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="98c59-228">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

## <a name="deliver-the-device"></a><span data-ttu-id="98c59-229">Recapita il dispositivo</span><span class="sxs-lookup"><span data-stu-id="98c59-229">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98c59-230">Prima di consegnare il dispositivo all'utente, assicurati di aver ottenuto e applicato le [licenze appropriate](../get-ready/prerequisites.md) per tale utente.</span><span class="sxs-lookup"><span data-stu-id="98c59-230">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="98c59-231">Se vengono applicate tutte le [](get-started-devices.md)licenze, puoi fare in modo che gli utenti siano pronti per l'uso dei dispositivi e quindi l'utente può avviare il dispositivo e procedere con l'Windows di installazione.</span><span class="sxs-lookup"><span data-stu-id="98c59-231">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









