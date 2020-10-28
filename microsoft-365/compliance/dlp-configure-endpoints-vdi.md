---
title: Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Distribuire il pacchetto di configurazione nel dispositivo VDI (Virtual Desktop Infrastructure) in modo che sia onboarded to the Microsoft 365 Endpoint Data Loss Prevention Service.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769453"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="3d44c-103">Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo</span><span class="sxs-lookup"><span data-stu-id="3d44c-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="3d44c-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3d44c-104">**Applies to:**</span></span>
- [<span data-ttu-id="3d44c-105">Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint</span><span class="sxs-lookup"><span data-stu-id="3d44c-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="3d44c-106">Dispositivi VDI (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="3d44c-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="3d44c-107">Supporto per la prevenzione della perdita di dati di Microsoft 365 endpoint per Windows Virtual Desktop supporta scenari di sessione singola.</span><span class="sxs-lookup"><span data-stu-id="3d44c-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="3d44c-108">Gli scenari a più sessioni su desktop virtuale di Windows non sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="3d44c-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="3d44c-109">Dispositivi VDI onboard</span><span class="sxs-lookup"><span data-stu-id="3d44c-109">Onboard VDI devices</span></span>

<span data-ttu-id="3d44c-110">La prevenzione della perdita di dati di Microsoft 365 endpoint supporta l'onboarding delle sessioni VDI non permanenti.</span><span class="sxs-lookup"><span data-stu-id="3d44c-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="3d44c-111">Per l'onboarding delle sessioni VDI non permanenti, i dispositivi VDI devono essere su Windows 10 1809 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="3d44c-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="3d44c-112">Potrebbero verificarsi problemi associati all'onboarding di VDIs.</span><span class="sxs-lookup"><span data-stu-id="3d44c-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="3d44c-113">Di seguito sono riportate le sfide tipiche di questo scenario:</span><span class="sxs-lookup"><span data-stu-id="3d44c-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="3d44c-114">Instant Early onboarding di una sessione di breve durata, che deve essere onboarded to Microsoft 365 endpoint prevenzione della perdita di dati prima del provisioning effettivo.</span><span class="sxs-lookup"><span data-stu-id="3d44c-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="3d44c-115">Il nome del dispositivo viene in genere riutilizzato per le nuove sessioni.</span><span class="sxs-lookup"><span data-stu-id="3d44c-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="3d44c-116">I dispositivi VDI possono essere visualizzati nel centro conformità di Microsoft 365 come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3d44c-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="3d44c-117">Voce singola per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3d44c-117">Single entry for each device.</span></span>  
<span data-ttu-id="3d44c-118">Tenere presente che, in questo caso, è necessario configurare lo *stesso* nome del dispositivo al momento della creazione della sessione, ad esempio utilizzando un file di risposta automatico.</span><span class="sxs-lookup"><span data-stu-id="3d44c-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="3d44c-119">Più voci per ogni dispositivo-uno per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="3d44c-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="3d44c-120">Nei passaggi seguenti viene illustrato come eseguire l'onboarding dei dispositivi VDI e vengono evidenziati i passaggi per le voci singole e multiple.</span><span class="sxs-lookup"><span data-stu-id="3d44c-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="3d44c-121">Per gli ambienti in cui sono presenti configurazioni di risorse insufficienti, la procedura di avvio VDI potrebbe rallentare l'onboarding di prevenzione della perdita di dati di Microsoft 365 endpoint.</span><span class="sxs-lookup"><span data-stu-id="3d44c-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="3d44c-122">Aprire il file con estensione zip del pacchetto di configurazione VDI ( *DeviceCompliancePackage.zip* ) scaricato dalla procedura guidata di onboarding dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3d44c-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="3d44c-123">Nel riquadro di spostamento selezionare impostazioni onboarding del dispositivo di **configurazione**  >  **Device onboarding**  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="3d44c-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="3d44c-124">Nel campo **metodo di distribuzione** selezionare gli **script di onboarding VDI per gli endpoint non permanenti** .</span><span class="sxs-lookup"><span data-stu-id="3d44c-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="3d44c-125">Fare clic su **Download package** e salvare il file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="3d44c-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="3d44c-126">Copiare i file dalla cartella DeviceCompliancePackage estratta dal file con estensione zip nell' `golden/master` immagine sotto il percorso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="3d44c-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="3d44c-127">Se non si sta implementando una singola voce per ogni dispositivo, copiare DeviceComplianceOnboardingScript. cmd.</span><span class="sxs-lookup"><span data-stu-id="3d44c-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="3d44c-128">Se si sta implementando una singola voce per ogni dispositivo, copiare sia Onboard-NonPersistentMachine.ps1 che DeviceComplianceOnboardingScript. cmd.</span><span class="sxs-lookup"><span data-stu-id="3d44c-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3d44c-129">Se la cartella non viene visualizzata `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` , potrebbe essere nascosta.</span><span class="sxs-lookup"><span data-stu-id="3d44c-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="3d44c-130">È necessario scegliere l'opzione **Mostra file nascosti e cartelle** da Esplora file.</span><span class="sxs-lookup"><span data-stu-id="3d44c-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="3d44c-131">Aprire una finestra dell'Editor criteri di gruppo locali e **Computer Configuration** passare all'  >  **avvio delle impostazioni di Windows** per la configurazione del computer  >  **Scripts**  >  **Startup** .</span><span class="sxs-lookup"><span data-stu-id="3d44c-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="3d44c-132">I criteri di gruppo di dominio possono essere utilizzati anche per l'onboarding di dispositivi VDI non permanenti.</span><span class="sxs-lookup"><span data-stu-id="3d44c-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="3d44c-133">A seconda del metodo che si desidera implementare, attenersi alla procedura appropriata:</span><span class="sxs-lookup"><span data-stu-id="3d44c-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="3d44c-134">**Per voce singola per ogni dispositivo**</span><span class="sxs-lookup"><span data-stu-id="3d44c-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="3d44c-135">Selezionare la scheda **script di PowerShell** , quindi fare clic su **Aggiungi** (Esplora risorse verrà aperto direttamente nel percorso in cui è stato copiato lo script di onboarding precedente).</span><span class="sxs-lookup"><span data-stu-id="3d44c-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="3d44c-136">Passare allo script di PowerShell onboarding `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="3d44c-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="3d44c-137">**Per più voci per ogni dispositivo** :</span><span class="sxs-lookup"><span data-stu-id="3d44c-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="3d44c-138">Selezionare la scheda **script** , quindi fare clic su **Aggiungi** (Esplora risorse verrà aperto direttamente nel percorso in cui è stato copiato lo script di onboarding precedente).</span><span class="sxs-lookup"><span data-stu-id="3d44c-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="3d44c-139">Passare allo script bash onboarding `DeviceComplianceOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="3d44c-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="3d44c-140">Testare la soluzione:</span><span class="sxs-lookup"><span data-stu-id="3d44c-140">Test your solution:</span></span>

   1. <span data-ttu-id="3d44c-141">Creare un pool con un solo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3d44c-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="3d44c-142">Accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3d44c-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="3d44c-143">Disconnessione dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3d44c-143">Logoff from device.</span></span>

   1. <span data-ttu-id="3d44c-144">Accedere al dispositivo con un altro utente.</span><span class="sxs-lookup"><span data-stu-id="3d44c-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="3d44c-145">**Per voce singola per ogni dispositivo** : selezionare una sola voce in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3d44c-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="3d44c-146">**Per più voci per ogni dispositivo** : selezionare più voci in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3d44c-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="3d44c-147">Fare clic su **elenco dispositivi** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="3d44c-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="3d44c-148">Utilizzare la funzione di ricerca digitando il nome del dispositivo e selezionando **dispositivo** come tipo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="3d44c-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="3d44c-149">Aggiornamento delle immagini VDI (Virtual Desktop Infrastructure) non permanenti</span><span class="sxs-lookup"><span data-stu-id="3d44c-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="3d44c-150">Come procedura consigliata, è consigliabile utilizzare gli strumenti di manutenzione offline per applicare la patch alle immagini Golden/Master.</span><span class="sxs-lookup"><span data-stu-id="3d44c-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="3d44c-151">Ad esempio, è possibile utilizzare i comandi riportati di seguito per installare un aggiornamento quando l'immagine rimane offline:</span><span class="sxs-lookup"><span data-stu-id="3d44c-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="3d44c-152">Per ulteriori informazioni sui comandi DISM e la manutenzione offline, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d44c-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="3d44c-153">Modificare un'immagine di Windows tramite DISM</span><span class="sxs-lookup"><span data-stu-id="3d44c-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="3d44c-154">Opzioni di gestione immagini DISM Command-Line</span><span class="sxs-lookup"><span data-stu-id="3d44c-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="3d44c-155">Ridurre le dimensioni dell'archivio componenti in un'immagine Windows offline</span><span class="sxs-lookup"><span data-stu-id="3d44c-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="3d44c-156">Se la manutenzione offline non è un'opzione valida per l'ambiente VDI non persistente, è necessario eseguire le operazioni seguenti per garantire la coerenza e l'integrità dei sensori:</span><span class="sxs-lookup"><span data-stu-id="3d44c-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="3d44c-157">Dopo l'avvio dell'immagine master per la manutenzione o l'applicazione di patch online, eseguire uno script di Offboarding per disattivare il sensore di prevenzione della perdita di dati di Microsoft 365 endpoint.</span><span class="sxs-lookup"><span data-stu-id="3d44c-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="3d44c-158">Per ulteriori informazioni, vedere [dispositivi di trasferisce che utilizzano uno script locale](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="3d44c-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="3d44c-159">Verificare che il sensore sia interrotto eseguendo il comando seguente in una finestra CMD:</span><span class="sxs-lookup"><span data-stu-id="3d44c-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="3d44c-160">Service l'immagine in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3d44c-160">Service the image as needed.</span></span>

4. <span data-ttu-id="3d44c-161">Eseguire i comandi riportati di seguito utilizzando PsExec.exe (che può essere scaricato da https://download.sysinternals.com/files/PSTools.zip) per pulire il contenuto della cartella Cyber che potrebbe essere stato accumulato dal sensore dopo l'avvio:</span><span class="sxs-lookup"><span data-stu-id="3d44c-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="3d44c-162">Ri-Seal l'immagine Golden/Master come si farebbe normalmente.</span><span class="sxs-lookup"><span data-stu-id="3d44c-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d44c-163">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3d44c-163">Related topics</span></span>
- [<span data-ttu-id="3d44c-164">Dispositivi di bordo di Windows 10 con criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="3d44c-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="3d44c-165">Dispositivi di bordo di Windows 10 con Microsoft endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3d44c-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="3d44c-166">Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="3d44c-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="3d44c-167">Dispositivi di bordo di Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="3d44c-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="3d44c-168">Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3d44c-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
