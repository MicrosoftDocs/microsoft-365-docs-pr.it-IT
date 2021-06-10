---
title: Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti
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
description: Distribuisci il pacchetto di configurazione nel dispositivo VDI (Virtual Desktop Infrastructure) in modo che siano onboarded nel servizio di prevenzione della perdita dei dati Microsoft 365 Endpoint.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917952"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="d1094-103">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="d1094-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="d1094-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d1094-104">**Applies to:**</span></span>
- [<span data-ttu-id="d1094-105">Microsoft 365 Prevenzione della perdita dei dati degli endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="d1094-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="d1094-106">Dispositivi VDI (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="d1094-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="d1094-107">Microsoft 365 Il supporto per la prevenzione della perdita dei dati degli endpoint Windows desktop virtuale supporta scenari a sessione singola.</span><span class="sxs-lookup"><span data-stu-id="d1094-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="d1094-108">Gli scenari multi-sessione Windows desktop virtuale non sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="d1094-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="d1094-109">Onboard dei dispositivi VDI</span><span class="sxs-lookup"><span data-stu-id="d1094-109">Onboard VDI devices</span></span>

<span data-ttu-id="d1094-110">Microsoft 365 La prevenzione della perdita dei dati degli endpoint supporta l'onboarding di sessioni VDI non persistenti.</span><span class="sxs-lookup"><span data-stu-id="d1094-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="d1094-111">Per eseguire l'onboarding di sessioni VDI non persistenti, i dispositivi VDI devono essere Windows 10 1809 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d1094-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="d1094-112">Quando si esegue l'onboarding di VDI, potrebbero verificarsi problemi associati.</span><span class="sxs-lookup"><span data-stu-id="d1094-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="d1094-113">Di seguito sono riportate le sfide tipiche per questo scenario:</span><span class="sxs-lookup"><span data-stu-id="d1094-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="d1094-114">Onboarding immediato di sessioni di breve durata, che devono essere onboarding Microsoft 365 prevenzione della perdita di dati dell'endpoint prima del provisioning effettivo.</span><span class="sxs-lookup"><span data-stu-id="d1094-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="d1094-115">Il nome del dispositivo viene in genere riutilizzato per le nuove sessioni.</span><span class="sxs-lookup"><span data-stu-id="d1094-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="d1094-116">I dispositivi VDI possono essere visualizzati nel Centro Microsoft 365 conformità come uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1094-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="d1094-117">Voce singola per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1094-117">Single entry for each device.</span></span>  
<span data-ttu-id="d1094-118">Si noti che in  questo caso, è necessario configurare lo stesso nome del dispositivo al momento della creazione della sessione, ad esempio utilizzando un file di risposta automatico.</span><span class="sxs-lookup"><span data-stu-id="d1094-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="d1094-119">Più voci per ogni dispositivo- una per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="d1094-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="d1094-120">I passaggi seguenti ti guideranno nell'onboarding dei dispositivi VDI e indicheranno i passaggi per una o più voci.</span><span class="sxs-lookup"><span data-stu-id="d1094-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="d1094-121">Per gli ambienti in cui le configurazioni delle risorse sono scarse, la procedura di avvio VDI potrebbe rallentare l'onboarding Microsoft 365 di prevenzione della perdita di dati dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d1094-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="d1094-122">Apri il pacchetto di configurazione VDI .zip file (*DeviceCompliancePackage.zip*) scaricato dall'onboarding guidato del servizio.</span><span class="sxs-lookup"><span data-stu-id="d1094-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="d1094-123">Nel riquadro di spostamento seleziona **Impostazioni**  >    >  **onboarding del dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="d1094-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="d1094-124">Nel campo **Metodo di** distribuzione selezionare Script **di onboarding VDI per gli endpoint non persistenti.**</span><span class="sxs-lookup"><span data-stu-id="d1094-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="d1094-125">Fai **clic su Scarica pacchetto** e salva il file .zip file.</span><span class="sxs-lookup"><span data-stu-id="d1094-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="d1094-126">Copiare i file dalla cartella DeviceCompliancePackage estratta dal file .zip `golden/master` nell'immagine nel percorso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="d1094-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="d1094-127">Se non stai implementando una singola voce per ogni dispositivo, copia DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="d1094-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="d1094-128">Se stai implementando una singola voce per ogni dispositivo, copia sia Onboard-NonPersistentMachine.ps1 che DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="d1094-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1094-129">Se la cartella non è `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` visualizzata, è possibile che sia nascosta.</span><span class="sxs-lookup"><span data-stu-id="d1094-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="d1094-130">Dovrai scegliere l'opzione Mostra **cartelle e file** nascosti da Esplora file.</span><span class="sxs-lookup"><span data-stu-id="d1094-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="d1094-131">Aprire una finestra Editor Criteri di gruppo locali e passare a **Configurazione computer**  >  **Windows Impostazioni**  >  **Script di**  >  **avvio**.</span><span class="sxs-lookup"><span data-stu-id="d1094-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1094-132">I Criteri di gruppo di dominio possono essere utilizzati anche per l'onboarding di dispositivi VDI non persistenti.</span><span class="sxs-lookup"><span data-stu-id="d1094-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="d1094-133">A seconda del metodo che vuoi implementare, segui la procedura appropriata:</span><span class="sxs-lookup"><span data-stu-id="d1094-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="d1094-134">**Per una singola voce per ogni dispositivo**</span><span class="sxs-lookup"><span data-stu-id="d1094-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="d1094-135">Selezionare la **scheda Script di PowerShell,** quindi fare clic **su** Aggiungi (Windows Explorer si aprirà direttamente nel percorso in cui è stato copiato lo script di onboarding in precedenza).</span><span class="sxs-lookup"><span data-stu-id="d1094-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="d1094-136">Passare a script di PowerShell di `Onboard-NonPersistentMachine.ps1` onboarding.</span><span class="sxs-lookup"><span data-stu-id="d1094-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="d1094-137">**Per più voci per ogni dispositivo:**</span><span class="sxs-lookup"><span data-stu-id="d1094-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="d1094-138">Seleziona la **scheda Script,** quindi fai clic su **Aggiungi** (Windows Explorer si aprirà direttamente nel percorso in cui hai copiato lo script di onboarding in precedenza).</span><span class="sxs-lookup"><span data-stu-id="d1094-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="d1094-139">Passare allo script di onboarding bash `DeviceComplianceOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="d1094-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="d1094-140">Testare la soluzione:</span><span class="sxs-lookup"><span data-stu-id="d1094-140">Test your solution:</span></span>

   1. <span data-ttu-id="d1094-141">Creare un pool con un solo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1094-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="d1094-142">Accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1094-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="d1094-143">Disconnessione dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d1094-143">Logoff from device.</span></span>

   1. <span data-ttu-id="d1094-144">Accedere al dispositivo con un altro utente.</span><span class="sxs-lookup"><span data-stu-id="d1094-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="d1094-145">**Per una singola voce per ogni dispositivo:** controlla solo una voce in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="d1094-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="d1094-146">**Per più voci per ogni dispositivo**: Controllare più voci in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="d1094-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="d1094-147">Fare **clic su Elenco** dispositivi nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="d1094-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="d1094-148">Usa la funzione di ricerca immettendo il nome del dispositivo e seleziona **Dispositivo** come tipo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d1094-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="d1094-149">Aggiornamento di immagini VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="d1094-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="d1094-150">Come procedura consigliata, è consigliabile utilizzare gli strumenti di manutenzione offline per applicare patch alle immagini golden/master.</span><span class="sxs-lookup"><span data-stu-id="d1094-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="d1094-151">Ad esempio, puoi usare i comandi seguenti per installare un aggiornamento mentre l'immagine rimane offline:</span><span class="sxs-lookup"><span data-stu-id="d1094-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="d1094-152">Per ulteriori informazioni sui comandi di Gestione e manutenzione immagini distribuzione e sulla manutenzione offline, fare riferimento agli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1094-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="d1094-153">Modificare un'Windows immagine con Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="d1094-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="d1094-154">Gestione e manutenzione immagini distribuzione Command-Line opzioni</span><span class="sxs-lookup"><span data-stu-id="d1094-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="d1094-155">Ridurre le dimensioni dell'archivio componenti in un'immagine Windows offline</span><span class="sxs-lookup"><span data-stu-id="d1094-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="d1094-156">Se la manutenzione offline non è un'opzione valida per l'ambiente VDI non persistente, è necessario eseguire le operazioni seguenti per garantire la coerenza e l'integrità dei sensori:</span><span class="sxs-lookup"><span data-stu-id="d1094-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="d1094-157">Dopo aver avviato l'immagine master per la manutenzione online o l'applicazione di patch, eseguire uno script di offboarding per disattivare il sensore di prevenzione della perdita dei dati Microsoft 365 endpoint.</span><span class="sxs-lookup"><span data-stu-id="d1094-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="d1094-158">Per altre informazioni, vedi [Offboard devices using a local script.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="d1094-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="d1094-159">Assicurati che il sensore sia arrestato eseguendo il comando seguente in una finestra CMD:</span><span class="sxs-lookup"><span data-stu-id="d1094-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="d1094-160">Utilizzare l'immagine in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d1094-160">Service the image as needed.</span></span>

4. <span data-ttu-id="d1094-161">Esegui i comandi seguenti usando PsExec.exe (che può essere scaricato da per pulire il contenuto della cartella cyber che il sensore potrebbe aver https://download.sysinternals.com/files/PSTools.zip) accumulato dopo l'avvio:</span><span class="sxs-lookup"><span data-stu-id="d1094-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="d1094-162">Re-seal the golden/master image as you normally would.</span><span class="sxs-lookup"><span data-stu-id="d1094-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1094-163">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d1094-163">Related topics</span></span>
- [<span data-ttu-id="d1094-164">Onboardare Windows 10 dispositivi con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="d1094-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="d1094-165">Onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d1094-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="d1094-166">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="d1094-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="d1094-167">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="d1094-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="d1094-168">Risolvere i Microsoft Defender Advanced Threat Protection di onboarding</span><span class="sxs-lookup"><span data-stu-id="d1094-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)