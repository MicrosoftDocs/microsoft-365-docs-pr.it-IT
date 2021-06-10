---
title: Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti
description: Distribuisci il pacchetto di configurazione nel dispositivo VDI (Virtual Desktop Infrastructure) in modo che siano onboarded nel servizio Microsoft Defender for Endpoint.
keywords: configurare il dispositivo VDI (Virtual Desktop Infrastructure), vdi, gestione dei dispositivi, configurare Microsoft Defender per Endpoint, endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: d09967a18848365702f52f65a7f0624d2b2ae3d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843211"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="53cb1-104">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="53cb1-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53cb1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="53cb1-105">**Applies to:**</span></span>
- [<span data-ttu-id="53cb1-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="53cb1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="53cb1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53cb1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="53cb1-108">Dispositivi VDI (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="53cb1-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="53cb1-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="53cb1-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="53cb1-110">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="53cb1-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="53cb1-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="53cb1-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="53cb1-112">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="53cb1-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="53cb1-113">Defender for Endpoint supporta l'onboarding di sessioni VDI non persistenti.</span><span class="sxs-lookup"><span data-stu-id="53cb1-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="53cb1-114">Quando si esegue l'onboarding di VDI, potrebbero verificarsi problemi associati.</span><span class="sxs-lookup"><span data-stu-id="53cb1-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="53cb1-115">Di seguito sono riportate le sfide tipiche per questo scenario:</span><span class="sxs-lookup"><span data-stu-id="53cb1-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="53cb1-116">Onboarding immediato di sessioni di breve durata, che devono essere onboarding in Defender for Endpoint prima del provisioning effettivo.</span><span class="sxs-lookup"><span data-stu-id="53cb1-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="53cb1-117">Il nome del dispositivo viene in genere riutilizzato per le nuove sessioni.</span><span class="sxs-lookup"><span data-stu-id="53cb1-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="53cb1-118">I dispositivi VDI possono essere visualizzati in Defender for Endpoint Portal come:</span><span class="sxs-lookup"><span data-stu-id="53cb1-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="53cb1-119">Voce singola per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53cb1-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="53cb1-120">In questo caso, è *necessario* configurare lo stesso nome del dispositivo al momento della creazione della sessione, ad esempio utilizzando un file di risposta automatico.</span><span class="sxs-lookup"><span data-stu-id="53cb1-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="53cb1-121">Più voci per ogni dispositivo- una per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="53cb1-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="53cb1-122">I passaggi seguenti ti guideranno nell'onboarding dei dispositivi VDI e indicheranno i passaggi per una o più voci.</span><span class="sxs-lookup"><span data-stu-id="53cb1-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="53cb1-123">Per gli ambienti in cui le configurazioni delle risorse sono scarse, la procedura di avvio VDI potrebbe rallentare l'onboarding del sensore Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="53cb1-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="53cb1-124">Per Windows 10 o Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="53cb1-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="53cb1-125">Apri il pacchetto di configurazione VDI .zip file (*WindowsDefenderATPOnboardingPackage.zip*) scaricato dall'onboarding guidato del servizio.</span><span class="sxs-lookup"><span data-stu-id="53cb1-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="53cb1-126">Puoi anche ottenere il pacchetto da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="53cb1-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="53cb1-127">Nel riquadro di spostamento selezionare **Impostazioni**  >  **onboarding**.</span><span class="sxs-lookup"><span data-stu-id="53cb1-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="53cb1-128">Seleziona Windows 10 come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="53cb1-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="53cb1-129">Nel campo **Metodo di** distribuzione selezionare Script **di onboarding VDI per gli endpoint non persistenti.**</span><span class="sxs-lookup"><span data-stu-id="53cb1-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="53cb1-130">Fai **clic su Scarica pacchetto** e salva il file .zip file.</span><span class="sxs-lookup"><span data-stu-id="53cb1-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="53cb1-131">Copiare i file dalla cartella WindowsDefenderATPOnboardingPackage estratta dal file .zip nell'immagine `golden/master` nel percorso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="53cb1-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="53cb1-132">Se non stai implementando una singola voce per ogni dispositivo, copia WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="53cb1-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="53cb1-133">Se stai implementando una singola voce per ogni dispositivo, copia sia Onboard-NonPersistentMachine.ps1 windowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="53cb1-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="53cb1-134">Se la cartella non è `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` visualizzata, è possibile che sia nascosta.</span><span class="sxs-lookup"><span data-stu-id="53cb1-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="53cb1-135">Dovrai scegliere l'opzione Mostra **cartelle e file** nascosti da Esplora file.</span><span class="sxs-lookup"><span data-stu-id="53cb1-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="53cb1-136">Aprire una finestra Editor Criteri di gruppo locali e passare a **Configurazione computer**  >  **Windows Impostazioni**  >  **Script di**  >  **avvio**.</span><span class="sxs-lookup"><span data-stu-id="53cb1-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="53cb1-137">I Criteri di gruppo di dominio possono essere utilizzati anche per l'onboarding di dispositivi VDI non persistenti.</span><span class="sxs-lookup"><span data-stu-id="53cb1-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="53cb1-138">A seconda del metodo che vuoi implementare, segui la procedura appropriata:</span><span class="sxs-lookup"><span data-stu-id="53cb1-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="53cb1-139">Per una singola voce per ogni dispositivo:</span><span class="sxs-lookup"><span data-stu-id="53cb1-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="53cb1-140">Selezionare la **scheda Script di PowerShell,** quindi fare clic **su** Aggiungi (Windows Explorer si aprirà direttamente nel percorso in cui è stato copiato lo script di onboarding in precedenza).</span><span class="sxs-lookup"><span data-stu-id="53cb1-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="53cb1-141">Passare a script di PowerShell di `Onboard-NonPersistentMachine.ps1` onboarding.</span><span class="sxs-lookup"><span data-stu-id="53cb1-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="53cb1-142">Non è necessario specificare l'altro file, perché verrà attivato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="53cb1-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="53cb1-143">Per più voci per ogni dispositivo:</span><span class="sxs-lookup"><span data-stu-id="53cb1-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="53cb1-144">Seleziona la **scheda Script,** quindi fai clic su **Aggiungi** (Windows Explorer si aprirà direttamente nel percorso in cui hai copiato lo script di onboarding in precedenza).</span><span class="sxs-lookup"><span data-stu-id="53cb1-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="53cb1-145">Passare allo script di onboarding bash `WindowsDefenderATPOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="53cb1-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="53cb1-146">Testare la soluzione:</span><span class="sxs-lookup"><span data-stu-id="53cb1-146">Test your solution:</span></span>

   1. <span data-ttu-id="53cb1-147">Creare un pool con un solo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53cb1-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="53cb1-148">Accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53cb1-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="53cb1-149">Disconnessione dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53cb1-149">Logoff from device.</span></span>

   1. <span data-ttu-id="53cb1-150">Accedere al dispositivo con un altro utente.</span><span class="sxs-lookup"><span data-stu-id="53cb1-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="53cb1-151">A seconda del metodo che vuoi implementare, segui la procedura appropriata:</span><span class="sxs-lookup"><span data-stu-id="53cb1-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="53cb1-152">Per una singola voce per ogni dispositivo:</span><span class="sxs-lookup"><span data-stu-id="53cb1-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="53cb1-153">Controllare solo una voce in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="53cb1-153">Check only one entry in Microsoft Defender Security Center.</span></span>

      - <span data-ttu-id="53cb1-154">Per più voci per ogni dispositivo:</span><span class="sxs-lookup"><span data-stu-id="53cb1-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="53cb1-155">Controllare più voci in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="53cb1-155">Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="53cb1-156">Fare **clic su Elenco** dispositivi nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="53cb1-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="53cb1-157">Usa la funzione di ricerca immettendo il nome del dispositivo e seleziona **Dispositivo** come tipo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="53cb1-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="53cb1-158">Per SKU di livello inferiore</span><span class="sxs-lookup"><span data-stu-id="53cb1-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="53cb1-159">Il Registro di sistema seguente è rilevante solo quando l'obiettivo è quello di ottenere una "voce singola per ogni dispositivo".</span><span class="sxs-lookup"><span data-stu-id="53cb1-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="53cb1-160">Impostare il valore del Registro di sistema su:</span><span class="sxs-lookup"><span data-stu-id="53cb1-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="53cb1-161">o utilizzando la riga di comando:</span><span class="sxs-lookup"><span data-stu-id="53cb1-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="53cb1-162">Seguire il [processo di onboarding del server](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="53cb1-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="53cb1-163">Aggiornamento di immagini VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="53cb1-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="53cb1-164">Come procedura consigliata, è consigliabile utilizzare gli strumenti di manutenzione offline per applicare patch alle immagini golden/master.</span><span class="sxs-lookup"><span data-stu-id="53cb1-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="53cb1-165">Ad esempio, puoi usare i comandi seguenti per installare un aggiornamento mentre l'immagine rimane offline:</span><span class="sxs-lookup"><span data-stu-id="53cb1-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="53cb1-166">Per ulteriori informazioni sui comandi di Gestione e manutenzione immagini distribuzione e sulla manutenzione offline, fare riferimento agli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="53cb1-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="53cb1-167">Modificare un'Windows immagine con Gestione e manutenzione immagini distribuzione</span><span class="sxs-lookup"><span data-stu-id="53cb1-167">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="53cb1-168">Gestione e manutenzione immagini distribuzione Command-Line opzioni</span><span class="sxs-lookup"><span data-stu-id="53cb1-168">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="53cb1-169">Ridurre le dimensioni dell'archivio componenti in un'immagine Windows offline</span><span class="sxs-lookup"><span data-stu-id="53cb1-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="53cb1-170">Se la manutenzione offline non è un'opzione valida per l'ambiente VDI non persistente, è necessario eseguire le operazioni seguenti per garantire la coerenza e l'integrità dei sensori:</span><span class="sxs-lookup"><span data-stu-id="53cb1-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="53cb1-171">Dopo aver avviato l'immagine master per la manutenzione online o l'applicazione di patch, esegui uno script di offboarding per disattivare il sensore Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="53cb1-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="53cb1-172">Per altre informazioni, vedi [Offboard devices using a local script.](configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="53cb1-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="53cb1-173">Assicurati che il sensore sia arrestato eseguendo il comando seguente in una finestra CMD:</span><span class="sxs-lookup"><span data-stu-id="53cb1-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="53cb1-174">Utilizzare l'immagine in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="53cb1-174">Service the image as needed.</span></span>

4. <span data-ttu-id="53cb1-175">Esegui i comandi seguenti usando PsExec.exe (che può essere scaricato da per pulire il contenuto della cartella cyber che il sensore potrebbe aver https://download.sysinternals.com/files/PSTools.zip) accumulato dopo l'avvio:</span><span class="sxs-lookup"><span data-stu-id="53cb1-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="53cb1-176">Re-seal the golden/master image as you normally would.</span><span class="sxs-lookup"><span data-stu-id="53cb1-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="53cb1-177">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="53cb1-177">Related topics</span></span>
- [<span data-ttu-id="53cb1-178">Onboardare Windows 10 dispositivi con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="53cb1-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="53cb1-179">Onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="53cb1-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="53cb1-180">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="53cb1-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="53cb1-181">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="53cb1-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="53cb1-182">Risolvere i problemi di onboarding di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="53cb1-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
