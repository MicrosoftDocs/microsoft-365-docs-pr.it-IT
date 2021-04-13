---
title: Configurare i criteri di Microsoft Defender ATP per macOS in Jamf Pro
description: Scopri come configurare i criteri di Microsoft Defender ATP per macOS in Jamf Pro
keywords: criteri, microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 9b00d81d3d51c343565ec4eb743181baa2750b01
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687734"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="94db5-104">Configurare i criteri di Microsoft Defender for Endpoint su macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="94db5-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="94db5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="94db5-105">**Applies to:**</span></span>

- [<span data-ttu-id="94db5-106">Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="94db5-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="94db5-107">Questa pagina illustra i passaggi da eseguire per configurare i criteri macOS in Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="94db5-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="94db5-108">Dovrai eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="94db5-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="94db5-109">Ottenere il pacchetto di onboarding di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="94db5-110">Creare un profilo di configurazione in Jamf Pro usando il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="94db5-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="94db5-111">Configurare le impostazioni di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="94db5-112">Configurare le impostazioni di notifica di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="94db5-113">Configurare Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="94db5-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="94db5-114">Concedere l'accesso completo al disco a Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="94db5-115">Approvare l'estensione kernel per Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="94db5-116">Approvare le estensioni di sistema per Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="94db5-117">Configurare l'estensione di rete</span><span class="sxs-lookup"><span data-stu-id="94db5-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="94db5-118">Pianificare le analisi con Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="94db5-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="94db5-119">Distribuire Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="94db5-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="94db5-120">Passaggio 1: ottenere il pacchetto di onboarding di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="94db5-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com )passare a Impostazioni > **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="94db5-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="94db5-122">Seleziona macOS come sistema operativo e Gestione dispositivi mobili/ Microsoft Intune come metodo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="94db5-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Immagine di Microsoft Defender Security Center](images/onboarding-macos.png)

3. <span data-ttu-id="94db5-124">Seleziona **Scarica pacchetto di onboarding** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="94db5-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="94db5-125">`WindowsDefenderATPOnboardingPackage.zip`Estrai .</span><span class="sxs-lookup"><span data-stu-id="94db5-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="94db5-126">Copiare il file nella posizione preferita.</span><span class="sxs-lookup"><span data-stu-id="94db5-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="94db5-127">Ad esempio,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="94db5-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="94db5-128">Passaggio 2: Creare un profilo di configurazione in Jamf Pro usando il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="94db5-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="94db5-129">Individuare il file `WindowsDefenderATPOnboarding.plist` della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="94db5-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Immagine del file WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="94db5-131">Nel dashboard di Jamf Pro seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="94db5-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Immagine della creazione di un nuovo dashboard jamf pro](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="94db5-133">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-133">Enter the following details:</span></span>

   <span data-ttu-id="94db5-134">**Generale**</span><span class="sxs-lookup"><span data-stu-id="94db5-134">**General**</span></span>
   - <span data-ttu-id="94db5-135">Nome: onboarding MDATP per macOS</span><span class="sxs-lookup"><span data-stu-id="94db5-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="94db5-136">Descrizione: onboarding edR MDATP per macOS</span><span class="sxs-lookup"><span data-stu-id="94db5-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="94db5-137">Categoria: Nessuno</span><span class="sxs-lookup"><span data-stu-id="94db5-137">Category: None</span></span>
   - <span data-ttu-id="94db5-138">Metodo di distribuzione: installazione automatica</span><span class="sxs-lookup"><span data-stu-id="94db5-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="94db5-139">Livello: Livello computer</span><span class="sxs-lookup"><span data-stu-id="94db5-139">Level: Computer Level</span></span>

4. <span data-ttu-id="94db5-140">In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.</span><span class="sxs-lookup"><span data-stu-id="94db5-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Immagine dell'app configurata e delle impostazioni personalizzate](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="94db5-142">Seleziona **Carica file (file PLIST),** quindi in **Dominio preferenza** immetti: `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="94db5-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Immagine del file di caricamento jamfpro plist](images/jamfpro-plist-upload.png)

    ![Immagine del file di elenco delle proprietà del file di caricamento](images/jamfpro-plist-file.png)

7. <span data-ttu-id="94db5-145">Selezionare **Apri** e selezionare il file di onboarding.</span><span class="sxs-lookup"><span data-stu-id="94db5-145">Select **Open** and select the onboarding file.</span></span>

    ![Immagine del file di onboarding](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="94db5-147">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="94db5-147">Select **Upload**.</span></span> 

    ![Immagine del caricamento del file plist](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="94db5-149">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="94db5-149">Select the **Scope** tab.</span></span>

    ![Scheda Immagine dell'ambito](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="94db5-151">Selezionare i computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="94db5-151">Select the target computers.</span></span>

    ![Immagine dei computer di destinazione](images/jamfpro-target-computer.png)

    ![Immagine delle destinazioni](images/jamfpro-targets.png) 

11. <span data-ttu-id="94db5-154">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-154">Select **Save**.</span></span>

    ![Immagine dei computer di destinazione della distribuzione](images/jamfpro-deployment-target.png)

    ![Immagine dei computer di destinazione selezionati](images/jamfpro-target-selected.png)

12. <span data-ttu-id="94db5-157">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-157">Select **Done**.</span></span>

    ![Immagine dei computer del gruppo di destinazione](images/jamfpro-target-group.png)

    ![Elenco dei profili di configurazione](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="94db5-160">Passaggio 3: Configurare Le impostazioni di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="94db5-161">Usa le impostazioni di configurazione di Microsoft Defender for Endpoint seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="94db5-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="94db5-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="94db5-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="94db5-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="94db5-164">Non attivato per impostazione predefinita, se si prevede di eseguire un av di terze parti per macOS, impostarlo su `true` .</span><span class="sxs-lookup"><span data-stu-id="94db5-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="94db5-165">esclusioni</span><span class="sxs-lookup"><span data-stu-id="94db5-165">exclusions</span></span>
    - <span data-ttu-id="94db5-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="94db5-166">excludedPath</span></span>
    - <span data-ttu-id="94db5-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="94db5-167">excludedFileExtension</span></span>
    - <span data-ttu-id="94db5-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="94db5-168">excludedFileName</span></span>
    - <span data-ttu-id="94db5-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="94db5-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="94db5-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="94db5-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="94db5-171">EICAR è nell'esempio, se si sta passando attraverso un modello di prova, rimuoverlo soprattutto se si sta testando EICAR.</span><span class="sxs-lookup"><span data-stu-id="94db5-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="94db5-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="94db5-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="94db5-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="94db5-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="94db5-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="94db5-174">archive_bomb</span></span>
    - <span data-ttu-id="94db5-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="94db5-175">cloudService</span></span>
    - <span data-ttu-id="94db5-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="94db5-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="94db5-177">tag</span><span class="sxs-lookup"><span data-stu-id="94db5-177">tags</span></span>
    - <span data-ttu-id="94db5-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="94db5-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="94db5-179">Per informazioni, vedere [Elenco delle proprietà per il profilo di configurazione Jamf.](mac-preferences.md#property-list-for-jamf-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="94db5-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. <span data-ttu-id="94db5-180">Salvare il file con nome `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="94db5-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="94db5-181">Nel dashboard jamf pro selezionare **Generale.**</span><span class="sxs-lookup"><span data-stu-id="94db5-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Immagine del nuovo dashboard jamf pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="94db5-183">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-183">Enter the following details:</span></span>

    <span data-ttu-id="94db5-184">**Generale**</span><span class="sxs-lookup"><span data-stu-id="94db5-184">**General**</span></span>
    
    - <span data-ttu-id="94db5-185">Nome: Impostazioni di configurazione MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="94db5-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="94db5-186">Descrizione:\<blank\></span><span class="sxs-lookup"><span data-stu-id="94db5-186">Description:\<blank\></span></span>
    - <span data-ttu-id="94db5-187">Categoria: Nessuna (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="94db5-187">Category: None (default)</span></span>
    - <span data-ttu-id="94db5-188">Metodo di distribuzione: installa automaticamente (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="94db5-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="94db5-189">Livello: Livello computer(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="94db5-189">Level: Computer Level(default)</span></span>

    ![Immagine delle impostazioni di configurazione MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="94db5-191">In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.</span><span class="sxs-lookup"><span data-stu-id="94db5-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Immagine delle impostazioni personalizzate e dell'app](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="94db5-193">Selezionare **Carica file (file PLIST).**</span><span class="sxs-lookup"><span data-stu-id="94db5-193">Select **Upload File (PLIST file)**.</span></span>

    ![Immagine del file plist delle impostazioni di configurazione](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="94db5-195">In **Preferences Domain** immettere , quindi selezionare Upload `com.microsoft.wdav`  **PLIST File**.</span><span class="sxs-lookup"><span data-stu-id="94db5-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Immagine del dominio delle preferenze delle impostazioni di configurazione](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="94db5-197">Selezionare **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="94db5-197">Select **Choose File**.</span></span>

    ![Immagine del file di scelta delle impostazioni di configurazione](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="94db5-199">Seleziona il **MDATP_MDAV_configuration_settings.plist** e quindi seleziona **Apri.**</span><span class="sxs-lookup"><span data-stu-id="94db5-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Immagine delle impostazioni di configurazione di mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="94db5-201">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="94db5-201">Select **Upload**.</span></span>

    ![Immagine del caricamento delle impostazioni di configurazione](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Immagine dell'immagine di caricamento delle impostazioni di configurazione](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="94db5-204">Se si carica il file di Intune, verrà visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="94db5-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="94db5-205">![Immagine delle impostazioni di configurazione caricamento file intune](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="94db5-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="94db5-206">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-206">Select **Save**.</span></span> 

    ![Immagine delle impostazioni di configurazione Salva immagine](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="94db5-208">Il file viene caricato.</span><span class="sxs-lookup"><span data-stu-id="94db5-208">The file is uploaded.</span></span>

    ![Immagine dell'immagine del file delle impostazioni di configurazione caricata](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Immagine del file delle impostazioni di configurazione caricato](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="94db5-211">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="94db5-211">Select the **Scope** tab.</span></span>

    ![Immagine dell'ambito delle impostazioni di configurazione](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="94db5-213">Selezionare **Gruppo di computer di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="94db5-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="94db5-214">Seleziona **Aggiungi** e **quindi** Salva.</span><span class="sxs-lookup"><span data-stu-id="94db5-214">Select **Add**, then select **Save**.</span></span>

    ![Immagine delle impostazioni di configurazione addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Immagine delle impostazioni di configurazione salva aggiungi](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="94db5-217">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-217">Select **Done**.</span></span> <span data-ttu-id="94db5-218">Verrà visualizzato il nuovo profilo **di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="94db5-218">You'll see the new **Configuration profile**.</span></span>

    ![Immagine del profilo di configurazione delle impostazioni di configurazione](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="94db5-220">Passaggio 4: Configurare le impostazioni delle notifiche</span><span class="sxs-lookup"><span data-stu-id="94db5-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="94db5-221">Questi passaggi sono applicabili a macOS 10.15 (Catalina) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="94db5-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="94db5-222">Nel dashboard di Jamf Pro seleziona **Computer**, quindi **Profili di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="94db5-222">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="94db5-223">Fare **clic su** Nuovo e immettere i dettagli seguenti per **Opzioni:**</span><span class="sxs-lookup"><span data-stu-id="94db5-223">Click **New**, and enter the following details for **Options**:</span></span>
    
    - <span data-ttu-id="94db5-224">Scheda **Generale**:</span><span class="sxs-lookup"><span data-stu-id="94db5-224">Tab **General**:</span></span> 
        - <span data-ttu-id="94db5-225">**Name**: MDATP MDAV Notification settings</span><span class="sxs-lookup"><span data-stu-id="94db5-225">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="94db5-226">**Descrizione**: macOS 10.15 (Catalina) o versione più recente</span><span class="sxs-lookup"><span data-stu-id="94db5-226">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="94db5-227">**Category**: None *(impostazione predefinita)*</span><span class="sxs-lookup"><span data-stu-id="94db5-227">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="94db5-228">**Metodo di distribuzione**: Installa *automaticamente (impostazione predefinita)*</span><span class="sxs-lookup"><span data-stu-id="94db5-228">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="94db5-229">**Level**: Computer Level *(impostazione predefinita)*</span><span class="sxs-lookup"><span data-stu-id="94db5-229">**Level**: Computer Level *(default)*</span></span>

        ![Immagine delle impostazioni del profilo di configurazione mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="94db5-231">Scheda **Notifiche**, fare **clic su Aggiungi** e immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-231">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="94db5-232">**ID bundle**: `com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="94db5-232">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="94db5-233">**Avvisi critici**: fare clic su **Disabilita**</span><span class="sxs-lookup"><span data-stu-id="94db5-233">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="94db5-234">**Notifiche**: fare clic su **Abilita**</span><span class="sxs-lookup"><span data-stu-id="94db5-234">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="94db5-235">**Tipo di avviso banner:** selezionare **Includi** e **temporaneo** *(impostazione predefinita)*</span><span class="sxs-lookup"><span data-stu-id="94db5-235">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="94db5-236">**Notifiche nella schermata di blocco**: fare clic su **Nascondi**</span><span class="sxs-lookup"><span data-stu-id="94db5-236">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="94db5-237">**Notifiche nel Centro notifiche**: fare clic **su Visualizza**</span><span class="sxs-lookup"><span data-stu-id="94db5-237">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="94db5-238">**Icona dell'app Badge**: fare clic su **Visualizza**</span><span class="sxs-lookup"><span data-stu-id="94db5-238">**Badge app icon**: Click **Display**</span></span>

        ![Immagine della barra delle notifiche mdatpmdav delle impostazioni di configurazione](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="94db5-240">Scheda **Notifiche,** fare **clic su Aggiungi** ancora una volta, scorrere verso il basso fino a Nuove impostazioni **notifiche**</span><span class="sxs-lookup"><span data-stu-id="94db5-240">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="94db5-241">**ID bundle**: `com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="94db5-241">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="94db5-242">Configurare il resto delle impostazioni con gli stessi valori di cui sopra</span><span class="sxs-lookup"><span data-stu-id="94db5-242">Configure the rest of the settings to the same values as above</span></span>

        ![Immagine delle impostazioni di configurazione mdatpmdav notifications mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="94db5-244">Tieni presente che ora hai due "tabelle" con configurazioni di notifica, una per **l'ID bundle: com.microsoft.wdav.tray** e un'altra per l'ID **bundle: com.microsoft.autoupdate2.**</span><span class="sxs-lookup"><span data-stu-id="94db5-244">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="94db5-245">Sebbene sia possibile configurare le impostazioni degli avvisi in base ai propri requisiti, gli ID bundle devono essere esattamente gli stessi descritti in precedenza e l'opzione **Includi** deve essere **attivata** per le **notifiche.**</span><span class="sxs-lookup"><span data-stu-id="94db5-245">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="94db5-246">Seleziona la **scheda Ambito,** quindi seleziona **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="94db5-246">Select the **Scope** tab, then select **Add**.</span></span>

    ![Immagine dell'ambito delle impostazioni di configurazione add](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="94db5-248">Selezionare **Gruppo di computer di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="94db5-248">Select **Contoso's Machine Group**.</span></span> 

5. <span data-ttu-id="94db5-249">Seleziona **Aggiungi** e **quindi** Salva.</span><span class="sxs-lookup"><span data-stu-id="94db5-249">Select **Add**, then select **Save**.</span></span>
    
    ![Immagine delle impostazioni di configurazione contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Immagine delle impostazioni di configurazione aggiungi salvataggio](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="94db5-252">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-252">Select **Done**.</span></span> <span data-ttu-id="94db5-253">Verrà visualizzato il nuovo profilo **di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="94db5-253">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="94db5-254">![Immagine dell'impostazione di configurazione eseguita img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="94db5-254">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="94db5-255">Passaggio 5: Configurare Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="94db5-255">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="94db5-256">Usa le impostazioni di configurazione di Microsoft Defender for Endpoint seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-256">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. <span data-ttu-id="94db5-257">Salvarlo con nome `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="94db5-257">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="94db5-258">Nel dashboard jamf pro selezionare **Generale.**</span><span class="sxs-lookup"><span data-stu-id="94db5-258">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Immagine dell'immagine generale dell'impostazione di configurazione](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="94db5-260">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-260">Enter the following details:</span></span>

    <span data-ttu-id="94db5-261">**Generale**</span><span class="sxs-lookup"><span data-stu-id="94db5-261">**General**</span></span> 
    
    - <span data-ttu-id="94db5-262">Nome: Impostazioni MDATP MDAV MAU</span><span class="sxs-lookup"><span data-stu-id="94db5-262">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="94db5-263">Descrizione: impostazioni di Microsoft AutoUpdate per MDATP per macOS</span><span class="sxs-lookup"><span data-stu-id="94db5-263">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="94db5-264">Categoria: Nessuna (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="94db5-264">Category: None (default)</span></span>
    - <span data-ttu-id="94db5-265">Metodo di distribuzione: installa automaticamente (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="94db5-265">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="94db5-266">Livello: Livello computer(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="94db5-266">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="94db5-267">In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.</span><span class="sxs-lookup"><span data-stu-id="94db5-267">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Immagine dell'app delle impostazioni di configurazione e delle impostazioni personalizzate](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="94db5-269">Selezionare **Carica file (file PLIST).**</span><span class="sxs-lookup"><span data-stu-id="94db5-269">Select **Upload File (PLIST file)**.</span></span>

    ![Immagine dell'impostazione di configurazione plist](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="94db5-271">In **Dominio preferenza** immettere: , quindi selezionare Carica file `com.microsoft.autoupdate2` **PLIST**.</span><span class="sxs-lookup"><span data-stu-id="94db5-271">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Immagine del dominio pref dell'impostazione di configurazione](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="94db5-273">Selezionare **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="94db5-273">Select **Choose File**.</span></span>

    ![Immagine dell'impostazione di configurazione choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="94db5-275">Selezionare **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="94db5-275">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Immagine delle impostazioni di configurazione mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="94db5-277">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="94db5-277">Select **Upload**.</span></span>
    <span data-ttu-id="94db5-278">![Immagine dell'impostazione di configurazione uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="94db5-278">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Immagine dell'impostazione di configurazione uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="94db5-280">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-280">Select **Save**.</span></span>

    ![Immagine dell'impostazione di configurazione saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="94db5-282">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="94db5-282">Select the **Scope** tab.</span></span>
   
     ![Immagine dell'ambito dell'impostazione di configurazione](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="94db5-284">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-284">Select **Add**.</span></span>
    
    ![Immagine dell'impostazione di configurazione addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Immagine dell'impostazione di configurazione addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Immagine dell'impostazione di configurazione addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="94db5-288">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-288">Select **Done**.</span></span>
    
    ![Immagine dell'impostazione di configurazione doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="94db5-290">Passaggio 6: concedere l'accesso completo al disco a Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-290">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="94db5-291">Nel dashboard di Jamf Pro seleziona **Profili di configurazione.**</span><span class="sxs-lookup"><span data-stu-id="94db5-291">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Immagine del profilo di configurazione dell'impostazione di configurazione](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="94db5-293">Selezionare **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="94db5-293">Select **+ New**.</span></span> 

3. <span data-ttu-id="94db5-294">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-294">Enter the following details:</span></span>

    <span data-ttu-id="94db5-295">**Generale**</span><span class="sxs-lookup"><span data-stu-id="94db5-295">**General**</span></span> 
    - <span data-ttu-id="94db5-296">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span><span class="sxs-lookup"><span data-stu-id="94db5-296">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="94db5-297">Descrizione: in macOS Catalina o versioni più nuove, il nuovo controllo dei criteri delle preferenze sulla privacy</span><span class="sxs-lookup"><span data-stu-id="94db5-297">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="94db5-298">Categoria: Nessuno</span><span class="sxs-lookup"><span data-stu-id="94db5-298">Category: None</span></span>
    - <span data-ttu-id="94db5-299">Metodo di distribuzione: installazione automatica</span><span class="sxs-lookup"><span data-stu-id="94db5-299">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="94db5-300">Livello: livello computer</span><span class="sxs-lookup"><span data-stu-id="94db5-300">Level: Computer level</span></span>


    ![Immagine dell'impostazione di configurazione generale](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="94db5-302">In **Configure Privacy Preferences Policy Control** selezionare **Configure**.</span><span class="sxs-lookup"><span data-stu-id="94db5-302">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Immagine del controllo dell'informativa sulla privacy della configurazione](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="94db5-304">In **Privacy Preferences Policy Control** immetti i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-304">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="94db5-305">Identificatore: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="94db5-305">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="94db5-306">Tipo di identificatore: ID bundle</span><span class="sxs-lookup"><span data-stu-id="94db5-306">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="94db5-307">Requisiti del codice: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="94db5-307">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Immagine dei dettagli del controllo dei criteri di preferenza della privacy dell'impostazione di configurazione](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="94db5-309">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-309">Select **+ Add**.</span></span>

    ![Immagine dell'impostazione di configurazione aggiungi criteri di sistema a tutti i file](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="94db5-311">In App o servizio: impostata su **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="94db5-311">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="94db5-312">In "accesso": impostata su **Consenti**</span><span class="sxs-lookup"><span data-stu-id="94db5-312">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="94db5-313">Seleziona **Salva** (non quello in basso a destra).</span><span class="sxs-lookup"><span data-stu-id="94db5-313">Select **Save** (not the one at the bottom right).</span></span>

    ![Immagine dell'impostazione di configurazione salva le immagini](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="94db5-315">Fare clic `+` sul segno accanto ad Accesso **app** per aggiungere una nuova voce.</span><span class="sxs-lookup"><span data-stu-id="94db5-315">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Immagine dell'impostazione di configurazione dell'accesso all'app](images/tcc-add-entry.png)

9. <span data-ttu-id="94db5-317">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-317">Enter the following details:</span></span>

    - <span data-ttu-id="94db5-318">Identificatore: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="94db5-318">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="94db5-319">Tipo di identificatore: ID bundle</span><span class="sxs-lookup"><span data-stu-id="94db5-319">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="94db5-320">Requisiti del codice: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="94db5-320">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="94db5-321">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-321">Select **+ Add**.</span></span>

    ![Immagine della voce tcc epsext dell'impostazione di configurazione](images/tcc-epsext-entry.png)

    - <span data-ttu-id="94db5-323">In App o servizio: impostata su **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="94db5-323">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="94db5-324">In "accesso": impostata su **Consenti**</span><span class="sxs-lookup"><span data-stu-id="94db5-324">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="94db5-325">Seleziona **Salva** (non quello in basso a destra).</span><span class="sxs-lookup"><span data-stu-id="94db5-325">Select **Save** (not the one at the bottom right).</span></span>

    ![Immagine dell'impostazione di configurazione tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="94db5-327">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="94db5-327">Select the **Scope** tab.</span></span>

    ![Immagine dell'ambito dell'impostazione di configurazione](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="94db5-329">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-329">Select **+ Add**.</span></span>

    ![Immagine dell'impostazione di configurazione addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="94db5-331">Selezionare **Gruppi di** computer > in Nome gruppo **>** selezionare **MachineGroup di Contoso.**</span><span class="sxs-lookup"><span data-stu-id="94db5-331">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Immagine dell'impostazione di configurazione contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="94db5-333">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-333">Select **Add**.</span></span> 

16. <span data-ttu-id="94db5-334">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-334">Select **Save**.</span></span> 
    
17. <span data-ttu-id="94db5-335">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-335">Select **Done**.</span></span>
    
    ![Immagine dell'impostazione di configurazione donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Immagine dell'impostazione di configurazione donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="94db5-338">In alternativa, è possibile scaricare [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) e caricarlo nei profili di configurazione JAMF come descritto in [Deploying Custom Configuration Profiles using Jamf Pro| Metodo 2: Caricare un profilo di configurazione in Jamf Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)</span><span class="sxs-lookup"><span data-stu-id="94db5-338">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="94db5-339">Passaggio 7: Approvare l'estensione kernel per Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-339">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="94db5-340">I dispositivi Apple Silicon (M1) non supportano KEXT.</span><span class="sxs-lookup"><span data-stu-id="94db5-340">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="94db5-341">L'installazione di un profilo di configurazione costituito da criteri KEXT avrà esito negativo in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="94db5-341">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="94db5-342">In **Profili di configurazione** selezionare **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="94db5-342">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Screenshot di un post di social media Descrizione generata automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="94db5-344">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-344">Enter the following details:</span></span>

    <span data-ttu-id="94db5-345">**Generale**</span><span class="sxs-lookup"><span data-stu-id="94db5-345">**General**</span></span> 
    
    - <span data-ttu-id="94db5-346">Nome: MDATP MDAV Kernel Extension</span><span class="sxs-lookup"><span data-stu-id="94db5-346">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="94db5-347">Descrizione: estensione del kernel MDATP (kext)</span><span class="sxs-lookup"><span data-stu-id="94db5-347">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="94db5-348">Categoria: Nessuno</span><span class="sxs-lookup"><span data-stu-id="94db5-348">Category: None</span></span>
    - <span data-ttu-id="94db5-349">Metodo di distribuzione: installazione automatica</span><span class="sxs-lookup"><span data-stu-id="94db5-349">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="94db5-350">Livello: Livello computer</span><span class="sxs-lookup"><span data-stu-id="94db5-350">Level: Computer Level</span></span>

    ![Immagine delle impostazioni di configurazione del kernel mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="94db5-352">In **Configura estensioni kernel approvate** selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="94db5-352">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Immagine delle impostazioni di configurazione approvate kernel ext](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="94db5-354">In **Estensioni kernel approvate** immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-354">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="94db5-355">Nome visualizzato: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="94db5-355">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="94db5-356">ID team: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="94db5-356">Team ID: UBF8T346G9</span></span>

    ![Immagine dell'estensione del kernel appr delle impostazioni di configurazione](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="94db5-358">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="94db5-358">Select the **Scope** tab.</span></span>

    ![Immagine della scheda img dell'ambito delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="94db5-360">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-360">Select **+ Add**.</span></span>

7. <span data-ttu-id="94db5-361">Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="94db5-361">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="94db5-362">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-362">Select **+ Add**.</span></span>

    ![Immagine delle impostazioni di configurazione aggiungere immagini](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="94db5-364">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-364">Select **Save**.</span></span>

    ![Immagine delle impostazioni di configurazione saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="94db5-366">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-366">Select **Done**.</span></span>

    ![Immagine delle impostazioni di configurazione eseguite](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="94db5-368">In alternativa, è possibile scaricare [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) e caricarlo nei profili di configurazione JAMF come descritto in [Deploying Custom Configuration Profiles using Jamf Pro| Metodo 2: Caricare un profilo di configurazione in Jamf Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)</span><span class="sxs-lookup"><span data-stu-id="94db5-368">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="94db5-369">Passaggio 8: Approvare le estensioni di sistema per Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="94db5-369">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="94db5-370">In **Profili di configurazione** selezionare **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="94db5-370">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Screenshot di un post di social media Descrizione generata automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="94db5-372">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-372">Enter the following details:</span></span>

    <span data-ttu-id="94db5-373">**Generale**</span><span class="sxs-lookup"><span data-stu-id="94db5-373">**General**</span></span>
    
    - <span data-ttu-id="94db5-374">Nome: MDATP MDAV System Extensions</span><span class="sxs-lookup"><span data-stu-id="94db5-374">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="94db5-375">Descrizione: estensioni di sistema MDATP</span><span class="sxs-lookup"><span data-stu-id="94db5-375">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="94db5-376">Categoria: Nessuno</span><span class="sxs-lookup"><span data-stu-id="94db5-376">Category: None</span></span>
    - <span data-ttu-id="94db5-377">Metodo di distribuzione: installazione automatica</span><span class="sxs-lookup"><span data-stu-id="94db5-377">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="94db5-378">Livello: Livello computer</span><span class="sxs-lookup"><span data-stu-id="94db5-378">Level: Computer Level</span></span>

    ![Immagine delle impostazioni di configurazione sysext new prof](images/sysext-new-profile.png)

3. <span data-ttu-id="94db5-380">In **Estensioni di sistema** selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="94db5-380">In **System Extensions** select **Configure**.</span></span>

   ![Immagine delle impostazioni di configurazione sysext config](images/sysext-configure.png)

4. <span data-ttu-id="94db5-382">In **Estensioni di sistema** immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-382">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="94db5-383">Nome visualizzato: Microsoft Corp. Estensioni di sistema</span><span class="sxs-lookup"><span data-stu-id="94db5-383">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="94db5-384">Tipi di estensioni di sistema: estensioni di sistema consentite</span><span class="sxs-lookup"><span data-stu-id="94db5-384">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="94db5-385">Identificatore del team: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="94db5-385">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="94db5-386">Estensioni di sistema consentite:</span><span class="sxs-lookup"><span data-stu-id="94db5-386">Allowed System Extensions:</span></span>
     - <span data-ttu-id="94db5-387">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="94db5-387">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="94db5-388">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="94db5-388">**com.microsoft.wdav.netext**</span></span>

    ![Immagine delle impostazioni di configurazione sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="94db5-390">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="94db5-390">Select the **Scope** tab.</span></span>

    ![Immagine dell'ambito delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="94db5-392">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-392">Select **+ Add**.</span></span>

7. <span data-ttu-id="94db5-393">Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="94db5-393">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="94db5-394">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-394">Select **+ Add**.</span></span>

   ![Immagine delle impostazioni di configurazione addima](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="94db5-396">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-396">Select **Save**.</span></span>

   ![Immagine dell'ambito sysext delle impostazioni di configurazione](images/sysext-scope.png)

10. <span data-ttu-id="94db5-398">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-398">Select **Done**.</span></span>

    ![Immagine delle impostazioni di configurazione sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="94db5-400">Passaggio 9: Configurare l'estensione di rete</span><span class="sxs-lookup"><span data-stu-id="94db5-400">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="94db5-401">Come parte delle funzionalità di rilevamento e risposta degli endpoint, Microsoft Defender for Endpoint su macOS esamina il traffico socket e segnala queste informazioni al portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="94db5-401">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="94db5-402">Il criterio seguente consente all'estensione di rete di eseguire questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="94db5-402">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="94db5-403">Questi passaggi sono applicabili a macOS 10.15 (Catalina) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="94db5-403">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="94db5-404">Nel dashboard di Jamf Pro seleziona **Computer**, quindi **Profili di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="94db5-404">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="94db5-405">Fare **clic su** Nuovo e immettere i dettagli seguenti per **Opzioni:**</span><span class="sxs-lookup"><span data-stu-id="94db5-405">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="94db5-406">Scheda **Generale**:</span><span class="sxs-lookup"><span data-stu-id="94db5-406">Tab **General**:</span></span> 
        - <span data-ttu-id="94db5-407">**Nome**: Estensione di rete di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="94db5-407">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="94db5-408">**Descrizione**: macOS 10.15 (Catalina) o versione più recente</span><span class="sxs-lookup"><span data-stu-id="94db5-408">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="94db5-409">**Category**: None *(impostazione predefinita)*</span><span class="sxs-lookup"><span data-stu-id="94db5-409">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="94db5-410">**Metodo di distribuzione**: Installa *automaticamente (impostazione predefinita)*</span><span class="sxs-lookup"><span data-stu-id="94db5-410">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="94db5-411">**Level**: Computer Level *(impostazione predefinita)*</span><span class="sxs-lookup"><span data-stu-id="94db5-411">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="94db5-412">Filtro **contenuto scheda**:</span><span class="sxs-lookup"><span data-stu-id="94db5-412">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="94db5-413">**Nome filtro**: Filtro contenuto di Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="94db5-413">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="94db5-414">**Identificatore**: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="94db5-414">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="94db5-415">Lasciare **vuoto l'indirizzo** **del** servizio, l'organizzazione, **il** nome utente, la **password,** **il** certificato (**Include** *non è* selezionato)</span><span class="sxs-lookup"><span data-stu-id="94db5-415">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="94db5-416">**Filter Order**: Inspector</span><span class="sxs-lookup"><span data-stu-id="94db5-416">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="94db5-417">**Filtro socket**: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="94db5-417">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="94db5-418">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="94db5-418">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="94db5-419">Lasciare **vuoti i** campi filtro di rete **(l'opzione** Includi *non è* selezionata)</span><span class="sxs-lookup"><span data-stu-id="94db5-419">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="94db5-420">Tieni presente **che i valori di Identifier,** Socket **Filter** e Socket **Filter Designated Requirement** sono esattamente come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="94db5-420">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![Immagine dell'impostazione di configurazione mdatpmdav](images/netext-create-profile.png)

3. <span data-ttu-id="94db5-422">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="94db5-422">Select the **Scope** tab.</span></span>

   ![Immagine della scheda sco delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="94db5-424">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-424">Select **+ Add**.</span></span>

5. <span data-ttu-id="94db5-425">Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="94db5-425">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="94db5-426">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-426">Select **+ Add**.</span></span>

    ![Immagine delle impostazioni di configurazione adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="94db5-428">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-428">Select **Save**.</span></span>

    ![Immagine delle impostazioni di configurazione savimg netextscop](images/netext-scope.png)

8. <span data-ttu-id="94db5-430">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-430">Select **Done**.</span></span>

    ![Immagine delle impostazioni di configurazione netextfinal](images/netext-final.png)

<span data-ttu-id="94db5-432">In alternativa, è possibile scaricare [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) e caricarlo nei profili di configurazione JAMF come descritto in [Deploying Custom Configuration Profiles using Jamf Pro| Metodo 2: Caricare un profilo di configurazione in Jamf Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)</span><span class="sxs-lookup"><span data-stu-id="94db5-432">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="94db5-433">Passaggio 10: pianificare le analisi con Microsoft Defender for Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="94db5-433">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="94db5-434">Segui le istruzioni su [Pianifica analisi con Microsoft Defender for Endpoint in macOS.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)</span><span class="sxs-lookup"><span data-stu-id="94db5-434">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="94db5-435">Passaggio 11: Distribuire Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="94db5-435">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="94db5-436">Passare al percorso in cui è stato salvato `wdav.pkg` .</span><span class="sxs-lookup"><span data-stu-id="94db5-436">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Immagine di Esplora file wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="94db5-438">Rinominarlo in `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="94db5-438">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Immagine di esplora file1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="94db5-440">Apri il dashboard di Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="94db5-440">Open the Jamf Pro dashboard.</span></span>

    ![Immagine delle impostazioni di configurazione jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="94db5-442">Seleziona il computer e fai clic sull'icona a forma di ingranaggio nella parte superiore, quindi seleziona **Gestione computer.**</span><span class="sxs-lookup"><span data-stu-id="94db5-442">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Immagine delle impostazioni di configurazione compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="94db5-444">In **Pacchetti** seleziona **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="94db5-444">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="94db5-445">![Un'immagine contenente una descrizione del pacchetto generato automaticamente](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="94db5-445">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="94db5-446">In **Nuovo pacchetto** immetti i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-446">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="94db5-447">**Scheda Generale**</span><span class="sxs-lookup"><span data-stu-id="94db5-447">**General tab**</span></span>
    - <span data-ttu-id="94db5-448">Nome visualizzato: lasciare vuoto per il momento.</span><span class="sxs-lookup"><span data-stu-id="94db5-448">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="94db5-449">Perché verrà reimpostato quando scegli il tuo pkg.</span><span class="sxs-lookup"><span data-stu-id="94db5-449">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="94db5-450">Categoria: Nessuna (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="94db5-450">Category: None (default)</span></span>
    - <span data-ttu-id="94db5-451">Filename: Choose File</span><span class="sxs-lookup"><span data-stu-id="94db5-451">Filename: Choose File</span></span>

    ![Immagine della scheda generale delle impostazioni di configurazione](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="94db5-453">Aprire il file e puntare a `wdav.pkg` o `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="94db5-453">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Screenshot dello schermo di un computer Descrizione generata automaticamente](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="94db5-455">Seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="94db5-455">Select **Open**.</span></span> <span data-ttu-id="94db5-456">Imposta il **nome visualizzato su** Microsoft Defender Advanced Threat Protection e Microsoft Defender **Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="94db5-456">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="94db5-457">**File manifesto** non obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="94db5-457">**Manifest File** is not required.</span></span> <span data-ttu-id="94db5-458">Microsoft Defender Advanced Threat Protection funziona senza file manifesto.</span><span class="sxs-lookup"><span data-stu-id="94db5-458">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="94db5-459">**Scheda Opzioni**</span><span class="sxs-lookup"><span data-stu-id="94db5-459">**Options tab**</span></span><br> <span data-ttu-id="94db5-460">Mantenere i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="94db5-460">Keep default values.</span></span>

    <span data-ttu-id="94db5-461">**Scheda Limitazioni**</span><span class="sxs-lookup"><span data-stu-id="94db5-461">**Limitations tab**</span></span><br> <span data-ttu-id="94db5-462">Mantenere i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="94db5-462">Keep default values.</span></span>
    
     ![Immagine della scheda limitazione delle impostazioni di configurazione](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="94db5-464">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-464">Select **Save**.</span></span> <span data-ttu-id="94db5-465">Il pacchetto viene caricato in Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="94db5-465">The package is uploaded to Jamf Pro.</span></span> 

   ![Immagine delle impostazioni di configurazione pack upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="94db5-467">La distribuzione del pacchetto può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="94db5-467">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Immagine delle impostazioni di configurazione pack upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="94db5-469">Passare alla **pagina** Criteri.</span><span class="sxs-lookup"><span data-stu-id="94db5-469">Navigate to the **Policies** page.</span></span>

    ![Immagine delle impostazioni di configurazione](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="94db5-471">Selezionare **+ Nuovo** per creare un nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="94db5-471">Select **+ New** to create a new policy.</span></span>

    ![Immagine delle impostazioni di configurazione nuovo criterio](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="94db5-473">In **Generale** Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94db5-473">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="94db5-474">Nome visualizzato: MDATP Onboarding Contoso 200329 v100.86.92 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="94db5-474">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="94db5-475">Immagine delle impostazioni di configurazionemdatponboard</span><span class="sxs-lookup"><span data-stu-id="94db5-475">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="94db5-476">Selezionare **Archiviazione ricorrente.**</span><span class="sxs-lookup"><span data-stu-id="94db5-476">Select **Recurring Check-in**.</span></span> 
    
    ![Immagine dell'archiviazione ricorrente delle impostazioni di configurazione](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="94db5-478">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-478">Select **Save**.</span></span> 
 
14. <span data-ttu-id="94db5-479">Selezionare **Pacchetti > Configura**.</span><span class="sxs-lookup"><span data-stu-id="94db5-479">Select **Packages > Configure**.</span></span>
 
    ![Immagine delle impostazioni di configurazione configurate](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="94db5-481">Seleziona il **pulsante** Aggiungi accanto a **Microsoft Defender Advanced Threat Protection e Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="94db5-481">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Immagine delle impostazioni di configurazione MDATP e MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="94db5-483">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94db5-483">Select **Save**.</span></span>

    ![Immagine delle impostazioni di configurazionesavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="94db5-485">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="94db5-485">Select the **Scope** tab.</span></span>  

    ![Immagine delle impostazioni di configurazione scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="94db5-487">Selezionare i computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="94db5-487">Select the target computers.</span></span>

    ![Immagine delle impostazioni di configurazione tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="94db5-489">**Ambito**</span><span class="sxs-lookup"><span data-stu-id="94db5-489">**Scope**</span></span>
    
    <span data-ttu-id="94db5-490">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94db5-490">Select **Add**.</span></span>
    
    ![Immagine delle impostazioni di configurazione ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Immagine delle impostazioni di configurazione ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="94db5-493">**Self-Service**</span><span class="sxs-lookup"><span data-stu-id="94db5-493">**Self-Service**</span></span>
    
    ![Immagine delle impostazioni di configurazione selfservice](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="94db5-495">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="94db5-495">Select **Done**.</span></span> 

    ![Immagine delle impostazioni di configurazione do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Immagine delle impostazioni di configurazione do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




