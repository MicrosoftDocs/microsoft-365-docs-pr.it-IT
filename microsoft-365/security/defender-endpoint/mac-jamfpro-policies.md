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
ms.openlocfilehash: 1559d8dca6b6909f22473c5a8f4d25d4bac501d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062253"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-for-macos-policies-in-jamf-pro"></a><span data-ttu-id="09fab-104">Configurare i criteri di Microsoft Defender for Endpoint per macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="09fab-104">Set up the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="09fab-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="09fab-105">**Applies to:**</span></span>

- [<span data-ttu-id="09fab-106">Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="09fab-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="09fab-107">Questa pagina illustra i passaggi da eseguire per configurare i criteri macOS in Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="09fab-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="09fab-108">Dovrai eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="09fab-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="09fab-109">Ottenere il pacchetto di onboarding di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="09fab-110">Creare un profilo di configurazione in Jamf Pro usando il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="09fab-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="09fab-111">Configurare le impostazioni di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="09fab-112">Configurare le impostazioni di notifica di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="09fab-113">Configurare Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="09fab-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="09fab-114">Concedere l'accesso completo al disco a Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="09fab-115">Approvare l'estensione kernel per Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="09fab-116">Approvare le estensioni di sistema per Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="09fab-117">Configurare l'estensione di rete</span><span class="sxs-lookup"><span data-stu-id="09fab-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="09fab-118">Pianificare le analisi con Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="09fab-118">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="09fab-119">Distribuire Microsoft Defender per Endpoint per macOS</span><span class="sxs-lookup"><span data-stu-id="09fab-119">Deploy Microsoft Defender for Endpoint for macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-for-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="09fab-120">Passaggio 1: ottenere il pacchetto di onboarding di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="09fab-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com )passare a Impostazioni > **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="09fab-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="09fab-122">Seleziona macOS come sistema operativo e Gestione dispositivi mobili/ Microsoft Intune come metodo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="09fab-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Immagine di Microsoft Defender Security Center](images/onboarding-macos.png)

3. <span data-ttu-id="09fab-124">Seleziona **Scarica pacchetto di onboarding** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="09fab-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="09fab-125">`WindowsDefenderATPOnboardingPackage.zip`Estrai .</span><span class="sxs-lookup"><span data-stu-id="09fab-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="09fab-126">Copiare il file nella posizione preferita.</span><span class="sxs-lookup"><span data-stu-id="09fab-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="09fab-127">Ad esempio,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="09fab-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="09fab-128">Passaggio 2: Creare un profilo di configurazione in Jamf Pro usando il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="09fab-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="09fab-129">Individuare il file `WindowsDefenderATPOnboarding.plist` della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="09fab-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Immagine del file WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="09fab-131">Nel dashboard di Jamf Pro seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="09fab-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Immagine della creazione di un nuovo dashboard jamf pro](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="09fab-133">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-133">Enter the following details:</span></span>

   <span data-ttu-id="09fab-134">**Generale**</span><span class="sxs-lookup"><span data-stu-id="09fab-134">**General**</span></span>
   - <span data-ttu-id="09fab-135">Nome: onboarding MDATP per macOS</span><span class="sxs-lookup"><span data-stu-id="09fab-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="09fab-136">Descrizione: onboarding edR MDATP per macOS</span><span class="sxs-lookup"><span data-stu-id="09fab-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="09fab-137">Categoria: Nessuno</span><span class="sxs-lookup"><span data-stu-id="09fab-137">Category: None</span></span>
   - <span data-ttu-id="09fab-138">Metodo di distribuzione: installazione automatica</span><span class="sxs-lookup"><span data-stu-id="09fab-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="09fab-139">Livello: Livello computer</span><span class="sxs-lookup"><span data-stu-id="09fab-139">Level: Computer Level</span></span>

4. <span data-ttu-id="09fab-140">In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.</span><span class="sxs-lookup"><span data-stu-id="09fab-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Immagine dell'app configurata e delle impostazioni personalizzate](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="09fab-142">Seleziona **Carica file (file PLIST),** quindi in **Dominio preferenza** immetti: `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="09fab-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Immagine del file di caricamento jamfpro plist](images/jamfpro-plist-upload.png)

    ![Immagine del file di elenco delle proprietà del file di caricamento](images/jamfpro-plist-file.png)

7. <span data-ttu-id="09fab-145">Selezionare **Apri** e selezionare il file di onboarding.</span><span class="sxs-lookup"><span data-stu-id="09fab-145">Select **Open** and select the onboarding file.</span></span>

    ![Immagine del file di onboarding](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="09fab-147">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="09fab-147">Select **Upload**.</span></span> 

    ![Immagine del caricamento del file plist](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="09fab-149">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="09fab-149">Select the **Scope** tab.</span></span>

    ![Scheda Immagine dell'ambito](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="09fab-151">Selezionare i computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="09fab-151">Select the target computers.</span></span>

    ![Immagine dei computer di destinazione](images/jamfpro-target-computer.png)

    ![Immagine delle destinazioni](images/jamfpro-targets.png) 

11. <span data-ttu-id="09fab-154">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-154">Select **Save**.</span></span>

    ![Immagine dei computer di destinazione della distribuzione](images/jamfpro-deployment-target.png)

    ![Immagine dei computer di destinazione selezionati](images/jamfpro-target-selected.png)

12. <span data-ttu-id="09fab-157">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-157">Select **Done**.</span></span>

    ![Immagine dei computer del gruppo di destinazione](images/jamfpro-target-group.png)

    ![Elenco dei profili di configurazione](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="09fab-160">Passaggio 3: Configurare Le impostazioni di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="09fab-161">Usa le impostazioni di configurazione di Microsoft Defender for Endpoint seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="09fab-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="09fab-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="09fab-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="09fab-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="09fab-164">Non attivato per impostazione predefinita, se si prevede di eseguire un av di terze parti per macOS, impostarlo su `true` .</span><span class="sxs-lookup"><span data-stu-id="09fab-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="09fab-165">esclusioni</span><span class="sxs-lookup"><span data-stu-id="09fab-165">exclusions</span></span>
    - <span data-ttu-id="09fab-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="09fab-166">excludedPath</span></span>
    - <span data-ttu-id="09fab-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="09fab-167">excludedFileExtension</span></span>
    - <span data-ttu-id="09fab-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="09fab-168">excludedFileName</span></span>
    - <span data-ttu-id="09fab-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="09fab-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="09fab-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="09fab-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="09fab-171">EICAR è nell'esempio, se si sta passando attraverso un modello di prova, rimuoverlo soprattutto se si sta testando EICAR.</span><span class="sxs-lookup"><span data-stu-id="09fab-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="09fab-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="09fab-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="09fab-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="09fab-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="09fab-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="09fab-174">archive_bomb</span></span>
    - <span data-ttu-id="09fab-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="09fab-175">cloudService</span></span>
    - <span data-ttu-id="09fab-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="09fab-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="09fab-177">tag</span><span class="sxs-lookup"><span data-stu-id="09fab-177">tags</span></span>
    - <span data-ttu-id="09fab-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="09fab-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="09fab-179">Per informazioni, vedere [Elenco delle proprietà per il profilo di configurazione Jamf.](mac-preferences.md#property-list-for-jamf-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="09fab-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

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

2. <span data-ttu-id="09fab-180">Salvare il file con nome `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="09fab-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="09fab-181">Nel dashboard jamf pro selezionare **Generale.**</span><span class="sxs-lookup"><span data-stu-id="09fab-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Immagine del nuovo dashboard jamf pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="09fab-183">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-183">Enter the following details:</span></span>

    <span data-ttu-id="09fab-184">**Generale**</span><span class="sxs-lookup"><span data-stu-id="09fab-184">**General**</span></span>
    
    - <span data-ttu-id="09fab-185">Nome: Impostazioni di configurazione MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="09fab-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="09fab-186">Descrizione:\<blank\></span><span class="sxs-lookup"><span data-stu-id="09fab-186">Description:\<blank\></span></span>
    - <span data-ttu-id="09fab-187">Categoria: Nessuna (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-187">Category: None (default)</span></span>
    - <span data-ttu-id="09fab-188">Metodo di distribuzione: installa automaticamente (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="09fab-189">Livello: Livello computer(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-189">Level: Computer Level(default)</span></span>

    ![Immagine delle impostazioni di configurazione MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="09fab-191">In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.</span><span class="sxs-lookup"><span data-stu-id="09fab-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Immagine delle impostazioni personalizzate e dell'app](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="09fab-193">Selezionare **Carica file (file PLIST).**</span><span class="sxs-lookup"><span data-stu-id="09fab-193">Select **Upload File (PLIST file)**.</span></span>

    ![Immagine del file plist delle impostazioni di configurazione](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="09fab-195">In **Preferences Domain** immettere , quindi selezionare Upload `com.microsoft.wdav`  **PLIST File**.</span><span class="sxs-lookup"><span data-stu-id="09fab-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Immagine del dominio delle preferenze delle impostazioni di configurazione](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="09fab-197">Selezionare **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="09fab-197">Select **Choose File**.</span></span>

    ![Immagine del file di scelta delle impostazioni di configurazione](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="09fab-199">Seleziona il **MDATP_MDAV_configuration_settings.plist** e quindi seleziona **Apri.**</span><span class="sxs-lookup"><span data-stu-id="09fab-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Immagine delle impostazioni di configurazione di mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="09fab-201">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="09fab-201">Select **Upload**.</span></span>

    ![Immagine del caricamento delle impostazioni di configurazione](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Immagine dell'immagine di caricamento delle impostazioni di configurazione](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="09fab-204">Se si carica il file di Intune, verrà visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="09fab-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="09fab-205">![Immagine delle impostazioni di configurazione caricamento file intune](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="09fab-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="09fab-206">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-206">Select **Save**.</span></span> 

    ![Immagine delle impostazioni di configurazione Salva immagine](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="09fab-208">Il file viene caricato.</span><span class="sxs-lookup"><span data-stu-id="09fab-208">The file is uploaded.</span></span>

    ![Immagine dell'immagine del file delle impostazioni di configurazione caricata](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Immagine del file delle impostazioni di configurazione caricato](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="09fab-211">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="09fab-211">Select the **Scope** tab.</span></span>

    ![Immagine dell'ambito delle impostazioni di configurazione](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="09fab-213">Selezionare **Gruppo di computer di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="09fab-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="09fab-214">Seleziona **Aggiungi** e **quindi** Salva.</span><span class="sxs-lookup"><span data-stu-id="09fab-214">Select **Add**, then select **Save**.</span></span>

    ![Immagine delle impostazioni di configurazione addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Immagine delle impostazioni di configurazione salva aggiungi](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="09fab-217">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-217">Select **Done**.</span></span> <span data-ttu-id="09fab-218">Verrà visualizzato il nuovo profilo **di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="09fab-218">You'll see the new **Configuration profile**.</span></span>

    ![Immagine del profilo di configurazione delle impostazioni di configurazione](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="09fab-220">Passaggio 4: Configurare le impostazioni delle notifiche</span><span class="sxs-lookup"><span data-stu-id="09fab-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="09fab-221">Questi passaggi sono applicabili a macOS 10.15 (Catalina) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="09fab-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="09fab-222">Download `notif.mobileconfig` dal [repository GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span><span class="sxs-lookup"><span data-stu-id="09fab-222">Download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span></span>

2. <span data-ttu-id="09fab-223">Salvarlo con nome `MDATP_MDAV_notification_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="09fab-223">Save it as `MDATP_MDAV_notification_settings.plist`.</span></span>

3. <span data-ttu-id="09fab-224">Nel dashboard jamf pro selezionare **Generale.**</span><span class="sxs-lookup"><span data-stu-id="09fab-224">In the Jamf Pro dashboard, select **General**.</span></span> 
       
4. <span data-ttu-id="09fab-225">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-225">Enter the following details:</span></span>

    <span data-ttu-id="09fab-226">**Generale**</span><span class="sxs-lookup"><span data-stu-id="09fab-226">**General**</span></span> 
    
    - <span data-ttu-id="09fab-227">Name: MDATP MDAV Notification settings</span><span class="sxs-lookup"><span data-stu-id="09fab-227">Name: MDATP MDAV Notification settings</span></span>
    - <span data-ttu-id="09fab-228">Descrizione: macOS 10.15 (Catalina) o versione più recente</span><span class="sxs-lookup"><span data-stu-id="09fab-228">Description: macOS 10.15 (Catalina) or newer</span></span>
    - <span data-ttu-id="09fab-229">Categoria: Nessuna (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-229">Category: None (default)</span></span>
    - <span data-ttu-id="09fab-230">Metodo di distribuzione: installa automaticamente (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-230">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="09fab-231">Livello: Livello computer(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-231">Level: Computer Level(default)</span></span>

    ![Immagine delle impostazioni di configurazione mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)


5. <span data-ttu-id="09fab-233">Selezionare **Carica file (file PLIST).**</span><span class="sxs-lookup"><span data-stu-id="09fab-233">Select **Upload File (PLIST file)**.</span></span>

    ![Immagine delle impostazioni di configurazione carica plistfile](images/7f9138053dbcbf928e5182ee7b295ebe.png)
 

6. <span data-ttu-id="09fab-235">Selezionare **Scegli file**  >  **MDATP_MDAV_Notification_Settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="09fab-235">Select **Choose File** > **MDATP_MDAV_Notification_Settings.plist**.</span></span>


    ![Immagine delle impostazioni di configurazione mdatpmdav notsettings](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)


    ![Immagine delle impostazioni di configurazione mdatpmdav notifsettings](images/20e33b98eb54447881dc6c89e58b890f.png)

7. <span data-ttu-id="09fab-238">Selezionare **Apri**  >  **carica**.</span><span class="sxs-lookup"><span data-stu-id="09fab-238">Select **Open** > **Upload**.</span></span>

    ![Immagine delle impostazioni di configurazione upl img](images/7697c33b9fd376ae5a8023d01f9d3857.png)


    ![Immagine dell'immagine upl delle impostazioni di configurazione](images/2bda9244ec25d1526811da4ea91b1c86.png)

8. <span data-ttu-id="09fab-241">Seleziona la **scheda Ambito,** quindi seleziona **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="09fab-241">Select the **Scope** tab, then select **Add**.</span></span>

    ![Immagine dell'ambito delle impostazioni di configurazione add](images/441aa2ecd36abadcdd8aed03556080b5.png)


9. <span data-ttu-id="09fab-243">Selezionare **Gruppo di computer di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="09fab-243">Select **Contoso's Machine Group**.</span></span> 

10. <span data-ttu-id="09fab-244">Seleziona **Aggiungi** e **quindi** Salva.</span><span class="sxs-lookup"><span data-stu-id="09fab-244">Select **Add**, then select **Save**.</span></span>
    
    ![Immagine delle impostazioni di configurazione contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    
    ![Immagine delle impostazioni di configurazione aggiungi salvataggio](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

11. <span data-ttu-id="09fab-247">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-247">Select **Done**.</span></span> <span data-ttu-id="09fab-248">Verrà visualizzato il nuovo profilo **di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="09fab-248">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="09fab-249">![Immagine dell'impostazione di configurazione eseguita img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="09fab-249">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="09fab-250">Passaggio 5: Configurare Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="09fab-250">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="09fab-251">Usa le impostazioni di configurazione di Microsoft Defender for Endpoint seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-251">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

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

2. <span data-ttu-id="09fab-252">Salvarlo con nome `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="09fab-252">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="09fab-253">Nel dashboard jamf pro selezionare **Generale.**</span><span class="sxs-lookup"><span data-stu-id="09fab-253">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Immagine dell'immagine generale dell'impostazione di configurazione](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="09fab-255">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-255">Enter the following details:</span></span>

    <span data-ttu-id="09fab-256">**Generale**</span><span class="sxs-lookup"><span data-stu-id="09fab-256">**General**</span></span> 
    
    - <span data-ttu-id="09fab-257">Nome: Impostazioni MDATP MDAV MAU</span><span class="sxs-lookup"><span data-stu-id="09fab-257">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="09fab-258">Descrizione: impostazioni di Microsoft AutoUpdate per MDATP per macOS</span><span class="sxs-lookup"><span data-stu-id="09fab-258">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="09fab-259">Categoria: Nessuna (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-259">Category: None (default)</span></span>
    - <span data-ttu-id="09fab-260">Metodo di distribuzione: installa automaticamente (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-260">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="09fab-261">Livello: Livello computer(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-261">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="09fab-262">In **Impostazioni & impostazioni personalizzate selezionare** **Configura**.</span><span class="sxs-lookup"><span data-stu-id="09fab-262">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Immagine dell'app delle impostazioni di configurazione e delle impostazioni personalizzate](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="09fab-264">Selezionare **Carica file (file PLIST).**</span><span class="sxs-lookup"><span data-stu-id="09fab-264">Select **Upload File (PLIST file)**.</span></span>

    ![Immagine dell'impostazione di configurazione plist](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="09fab-266">In **Dominio preferenza** immettere: , quindi selezionare Carica file `com.microsoft.autoupdate2` **PLIST**.</span><span class="sxs-lookup"><span data-stu-id="09fab-266">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Immagine del dominio pref dell'impostazione di configurazione](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="09fab-268">Selezionare **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="09fab-268">Select **Choose File**.</span></span>

    ![Immagine dell'impostazione di configurazione choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="09fab-270">Selezionare **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="09fab-270">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Immagine delle impostazioni di configurazione mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="09fab-272">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="09fab-272">Select **Upload**.</span></span>
    <span data-ttu-id="09fab-273">![Immagine dell'impostazione di configurazione uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="09fab-273">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Immagine dell'impostazione di configurazione uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="09fab-275">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-275">Select **Save**.</span></span>

    ![Immagine dell'impostazione di configurazione saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="09fab-277">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="09fab-277">Select the **Scope** tab.</span></span>
   
     ![Immagine dell'ambito dell'impostazione di configurazione](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="09fab-279">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-279">Select **Add**.</span></span>
    
    ![Immagine dell'impostazione di configurazione addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Immagine dell'impostazione di configurazione addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Immagine dell'impostazione di configurazione addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="09fab-283">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-283">Select **Done**.</span></span>
    
    ![Immagine dell'impostazione di configurazione doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="09fab-285">Passaggio 6: concedere l'accesso completo al disco a Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-285">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="09fab-286">Nel dashboard di Jamf Pro seleziona **Profili di configurazione.**</span><span class="sxs-lookup"><span data-stu-id="09fab-286">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Immagine del profilo di configurazione dell'impostazione di configurazione](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="09fab-288">Selezionare **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="09fab-288">Select **+ New**.</span></span> 

3. <span data-ttu-id="09fab-289">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-289">Enter the following details:</span></span>

    <span data-ttu-id="09fab-290">**Generale**</span><span class="sxs-lookup"><span data-stu-id="09fab-290">**General**</span></span> 
    - <span data-ttu-id="09fab-291">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span><span class="sxs-lookup"><span data-stu-id="09fab-291">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="09fab-292">Descrizione: in macOS Catalina o versioni più nuove, il nuovo controllo dei criteri delle preferenze sulla privacy</span><span class="sxs-lookup"><span data-stu-id="09fab-292">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="09fab-293">Categoria: Nessuno</span><span class="sxs-lookup"><span data-stu-id="09fab-293">Category: None</span></span>
    - <span data-ttu-id="09fab-294">Metodo di distribuzione: installazione automatica</span><span class="sxs-lookup"><span data-stu-id="09fab-294">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="09fab-295">Livello: livello computer</span><span class="sxs-lookup"><span data-stu-id="09fab-295">Level: Computer level</span></span>


    ![Immagine dell'impostazione di configurazione generale](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="09fab-297">In **Configure Privacy Preferences Policy Control** selezionare **Configure**.</span><span class="sxs-lookup"><span data-stu-id="09fab-297">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Immagine del controllo dell'informativa sulla privacy della configurazione](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="09fab-299">In **Privacy Preferences Policy Control** immetti i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-299">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="09fab-300">Identificatore: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="09fab-300">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="09fab-301">Tipo di identificatore: ID bundle</span><span class="sxs-lookup"><span data-stu-id="09fab-301">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="09fab-302">Requisiti del codice: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="09fab-302">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Immagine dei dettagli del controllo dei criteri di preferenza della privacy dell'impostazione di configurazione](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="09fab-304">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-304">Select **+ Add**.</span></span>

    ![Immagine dell'impostazione di configurazione aggiungi criteri di sistema a tutti i file](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="09fab-306">In App o servizio: impostata su **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="09fab-306">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="09fab-307">In "accesso": impostata su **Consenti**</span><span class="sxs-lookup"><span data-stu-id="09fab-307">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="09fab-308">Seleziona **Salva** (non quello in basso a destra).</span><span class="sxs-lookup"><span data-stu-id="09fab-308">Select **Save** (not the one at the bottom right).</span></span>

    ![Immagine dell'impostazione di configurazione salva le immagini](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="09fab-310">Fare clic `+` sul segno accanto ad Accesso **app** per aggiungere una nuova voce.</span><span class="sxs-lookup"><span data-stu-id="09fab-310">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Immagine dell'impostazione di configurazione dell'accesso all'app](images/tcc-add-entry.png)

9. <span data-ttu-id="09fab-312">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-312">Enter the following details:</span></span>

    - <span data-ttu-id="09fab-313">Identificatore: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="09fab-313">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="09fab-314">Tipo di identificatore: ID bundle</span><span class="sxs-lookup"><span data-stu-id="09fab-314">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="09fab-315">Requisiti del codice: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="09fab-315">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="09fab-316">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-316">Select **+ Add**.</span></span>

    ![Immagine della voce tcc epsext dell'impostazione di configurazione](images/tcc-epsext-entry.png)

    - <span data-ttu-id="09fab-318">In App o servizio: impostata su **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="09fab-318">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="09fab-319">In "accesso": impostata su **Consenti**</span><span class="sxs-lookup"><span data-stu-id="09fab-319">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="09fab-320">Seleziona **Salva** (non quello in basso a destra).</span><span class="sxs-lookup"><span data-stu-id="09fab-320">Select **Save** (not the one at the bottom right).</span></span>

    ![Immagine dell'impostazione di configurazione tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="09fab-322">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="09fab-322">Select the **Scope** tab.</span></span>

    ![Immagine dell'ambito dell'impostazione di configurazione](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="09fab-324">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-324">Select **+ Add**.</span></span>

    ![Immagine dell'impostazione di configurazione addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="09fab-326">Selezionare **Gruppi di** computer > in Nome gruppo **>** selezionare **MachineGroup di Contoso.**</span><span class="sxs-lookup"><span data-stu-id="09fab-326">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Immagine dell'impostazione di configurazione contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="09fab-328">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-328">Select **Add**.</span></span> 

16. <span data-ttu-id="09fab-329">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-329">Select **Save**.</span></span> 
    
17. <span data-ttu-id="09fab-330">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-330">Select **Done**.</span></span>
    
    ![Immagine dell'impostazione di configurazione donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Immagine dell'impostazione di configurazione donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)


## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="09fab-333">Passaggio 7: Approvare l'estensione kernel per Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-333">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="09fab-334">In **Profili di configurazione** selezionare **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="09fab-334">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Screenshot di un post di social media Descrizione generata automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="09fab-336">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-336">Enter the following details:</span></span>

    <span data-ttu-id="09fab-337">**Generale**</span><span class="sxs-lookup"><span data-stu-id="09fab-337">**General**</span></span> 
    
    - <span data-ttu-id="09fab-338">Nome: MDATP MDAV Kernel Extension</span><span class="sxs-lookup"><span data-stu-id="09fab-338">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="09fab-339">Descrizione: estensione del kernel MDATP (kext)</span><span class="sxs-lookup"><span data-stu-id="09fab-339">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="09fab-340">Categoria: Nessuno</span><span class="sxs-lookup"><span data-stu-id="09fab-340">Category: None</span></span>
    - <span data-ttu-id="09fab-341">Metodo di distribuzione: installazione automatica</span><span class="sxs-lookup"><span data-stu-id="09fab-341">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="09fab-342">Livello: Livello computer</span><span class="sxs-lookup"><span data-stu-id="09fab-342">Level: Computer Level</span></span>

    ![Immagine delle impostazioni di configurazione del kernel mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="09fab-344">In **Configura estensioni kernel approvate** selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="09fab-344">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Immagine delle impostazioni di configurazione approvate kernel ext](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="09fab-346">In **Estensioni kernel approvate** immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-346">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="09fab-347">Nome visualizzato: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="09fab-347">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="09fab-348">ID team: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="09fab-348">Team ID: UBF8T346G9</span></span>

    ![Immagine dell'estensione del kernel appr delle impostazioni di configurazione](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="09fab-350">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="09fab-350">Select the **Scope** tab.</span></span>

    ![Immagine della scheda img dell'ambito delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="09fab-352">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-352">Select **+ Add**.</span></span>

7. <span data-ttu-id="09fab-353">Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="09fab-353">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="09fab-354">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-354">Select **+ Add**.</span></span>

    ![Immagine delle impostazioni di configurazione aggiungere immagini](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="09fab-356">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-356">Select **Save**.</span></span>

    ![Immagine delle impostazioni di configurazione saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="09fab-358">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-358">Select **Done**.</span></span>

    ![Immagine delle impostazioni di configurazione eseguite](images/1c9bd3f68db20b80193dac18f33c22d0.png)


## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="09fab-360">Passaggio 8: Approvare le estensioni di sistema per Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="09fab-360">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="09fab-361">In **Profili di configurazione** selezionare **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="09fab-361">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Screenshot di un post di social media Descrizione generata automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="09fab-363">Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-363">Enter the following details:</span></span>

    <span data-ttu-id="09fab-364">**Generale**</span><span class="sxs-lookup"><span data-stu-id="09fab-364">**General**</span></span>
    
    - <span data-ttu-id="09fab-365">Nome: MDATP MDAV System Extensions</span><span class="sxs-lookup"><span data-stu-id="09fab-365">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="09fab-366">Descrizione: estensioni di sistema MDATP</span><span class="sxs-lookup"><span data-stu-id="09fab-366">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="09fab-367">Categoria: Nessuno</span><span class="sxs-lookup"><span data-stu-id="09fab-367">Category: None</span></span>
    - <span data-ttu-id="09fab-368">Metodo di distribuzione: installazione automatica</span><span class="sxs-lookup"><span data-stu-id="09fab-368">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="09fab-369">Livello: Livello computer</span><span class="sxs-lookup"><span data-stu-id="09fab-369">Level: Computer Level</span></span>

    ![Immagine delle impostazioni di configurazione sysext new prof](images/sysext-new-profile.png)

3. <span data-ttu-id="09fab-371">In **Estensioni di sistema** selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="09fab-371">In **System Extensions** select **Configure**.</span></span>

   ![Immagine delle impostazioni di configurazione sysext config](images/sysext-configure.png)

4. <span data-ttu-id="09fab-373">In **Estensioni di sistema** immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-373">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="09fab-374">Nome visualizzato: Microsoft Corp. Estensioni di sistema</span><span class="sxs-lookup"><span data-stu-id="09fab-374">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="09fab-375">Tipi di estensioni di sistema: estensioni di sistema consentite</span><span class="sxs-lookup"><span data-stu-id="09fab-375">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="09fab-376">Identificatore del team: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="09fab-376">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="09fab-377">Estensioni di sistema consentite:</span><span class="sxs-lookup"><span data-stu-id="09fab-377">Allowed System Extensions:</span></span>
     - <span data-ttu-id="09fab-378">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="09fab-378">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="09fab-379">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="09fab-379">**com.microsoft.wdav.netext**</span></span>

    ![Immagine delle impostazioni di configurazione sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="09fab-381">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="09fab-381">Select the **Scope** tab.</span></span>

    ![Immagine dell'ambito delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="09fab-383">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-383">Select **+ Add**.</span></span>

7. <span data-ttu-id="09fab-384">Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="09fab-384">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="09fab-385">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-385">Select **+ Add**.</span></span>

   ![Immagine delle impostazioni di configurazione addima](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="09fab-387">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-387">Select **Save**.</span></span>

   ![Immagine dell'ambito sysext delle impostazioni di configurazione](images/sysext-scope.png)

10. <span data-ttu-id="09fab-389">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-389">Select **Done**.</span></span>

    ![Immagine delle impostazioni di configurazione sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="09fab-391">Passaggio 9: Configurare l'estensione di rete</span><span class="sxs-lookup"><span data-stu-id="09fab-391">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="09fab-392">Come parte delle funzionalità di rilevamento e risposta degli endpoint, Microsoft Defender per Endpoint per Mac esamina il traffico socket e segnala queste informazioni al portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="09fab-392">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="09fab-393">Il criterio seguente consente all'estensione di rete di eseguire questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="09fab-393">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="09fab-394">JAMF non dispone del supporto incorporato per i criteri di filtro dei contenuti, che sono un requisito preliminare per l'abilitazione delle estensioni di rete installate da Microsoft Defender per Endpoint per Mac nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="09fab-394">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint for Mac installs on the device.</span></span> <span data-ttu-id="09fab-395">Inoltre, JAMF a volte modifica il contenuto dei criteri distribuiti.</span><span class="sxs-lookup"><span data-stu-id="09fab-395">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="09fab-396">Di conseguenza, i passaggi seguenti forniscono una soluzione alternativa che implica la firma del profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="09fab-396">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="09fab-397">Scaricare `netfilter.mobileconfig` dal [repository GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) nel dispositivo e salvarlo con nome `com.microsoft.network-extension.mobileconfig`</span><span class="sxs-lookup"><span data-stu-id="09fab-397">Download `netfilter.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) to your device and save it as `com.microsoft.network-extension.mobileconfig`</span></span>

2. <span data-ttu-id="09fab-398">Seguire le istruzioni in [questa pagina](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) per creare un certificato di firma utilizzando l'autorità di certificazione predefinita di JAMF</span><span class="sxs-lookup"><span data-stu-id="09fab-398">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority</span></span>

3. <span data-ttu-id="09fab-399">Dopo aver creato e installato il certificato nel dispositivo, esegui il comando seguente dal terminale da un dispositivo macOS:</span><span class="sxs-lookup"><span data-stu-id="09fab-399">After the certificate is created and installed to your device, run the following command from the Terminal from a macOS device:</span></span>

   ```bash
   $ security cms -S -N "<certificate name>" -i com.microsoft.network-extension.mobileconfig -o com.microsoft.network-extension.signed.mobileconfig
   ```

   ![Finestra del terminale con il comando per creare la configurazione firmata](images/netext-create-profile.png)

4. <span data-ttu-id="09fab-401">Dal portale JAMF, accedere a **Profili di configurazione e** fare clic sul pulsante **Carica.**</span><span class="sxs-lookup"><span data-stu-id="09fab-401">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> 

   ![Immagine della finestra di caricamento](images/netext-upload-file.png)

5. <span data-ttu-id="09fab-403">Selezionare **Scegli file** e selezionare `microsoft.network-extension.signed.mobileconfig` .</span><span class="sxs-lookup"><span data-stu-id="09fab-403">Select **Choose File** and select `microsoft.network-extension.signed.mobileconfig`.</span></span>

   ![Immagine della finestra di caricamento netext choose file](images/netext-choose-file.png)

6. <span data-ttu-id="09fab-405">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="09fab-405">Select **Upload**.</span></span>

   ![Immagine della finestra di caricamento netext upload file2](images/netext-upload-file2.png)

7. <span data-ttu-id="09fab-407">Dopo aver caricato il file, si viene reindirizzati a una nuova pagina per finalizzare la creazione di questo profilo.</span><span class="sxs-lookup"><span data-stu-id="09fab-407">After uploading the file, you are redirected to a new page to finalize the creation of this profile.</span></span>

   ![Immagine della pagina del profilo netext del nuovo profilo di configurazione](images/netext-profile-page.png)

8. <span data-ttu-id="09fab-409">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="09fab-409">Select the **Scope** tab.</span></span>

   ![Immagine della scheda sco delle impostazioni di configurazione](images/0df36fc308ba569db204ee32db3fb40a.png)

9. <span data-ttu-id="09fab-411">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-411">Select **+ Add**.</span></span>

10. <span data-ttu-id="09fab-412">Selezionare **Gruppi di** > in Nome gruppo **>** selezionare Gruppo di computer **di Contoso**.</span><span class="sxs-lookup"><span data-stu-id="09fab-412">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

11. <span data-ttu-id="09fab-413">Selezionare **+ Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-413">Select **+ Add**.</span></span>

    ![Immagine delle impostazioni di configurazione adim](images/0dde8a4c41110dbc398c485433a81359.png)

12. <span data-ttu-id="09fab-415">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-415">Select **Save**.</span></span>

    ![Immagine delle impostazioni di configurazione savimg netextscop](images/netext-scope.png)

13. <span data-ttu-id="09fab-417">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-417">Select **Done**.</span></span>

    ![Immagine delle impostazioni di configurazione netextfinal](images/netext-final.png)

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="09fab-419">Passaggio 10: pianificare le analisi con Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="09fab-419">Step 10: Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>
<span data-ttu-id="09fab-420">Segui le istruzioni su [Pianifica analisi con Microsoft Defender per Endpoint per Mac.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)</span><span class="sxs-lookup"><span data-stu-id="09fab-420">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="09fab-421">Passaggio 11: Distribuire Microsoft Defender per Endpoint per macOS</span><span class="sxs-lookup"><span data-stu-id="09fab-421">Step 11: Deploy Microsoft Defender for Endpoint for macOS</span></span>

1. <span data-ttu-id="09fab-422">Passare al percorso in cui è stato salvato `wdav.pkg` .</span><span class="sxs-lookup"><span data-stu-id="09fab-422">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Immagine di Esplora file wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="09fab-424">Rinominarlo in `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="09fab-424">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Immagine di esplora file1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="09fab-426">Apri il dashboard di Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="09fab-426">Open the Jamf Pro dashboard.</span></span>

    ![Immagine delle impostazioni di configurazione jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="09fab-428">Seleziona il computer e fai clic sull'icona a forma di ingranaggio nella parte superiore, quindi seleziona **Gestione computer.**</span><span class="sxs-lookup"><span data-stu-id="09fab-428">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Immagine delle impostazioni di configurazione compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="09fab-430">In **Pacchetti** seleziona **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="09fab-430">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="09fab-431">![Un'immagine contenente una descrizione del pacchetto generato automaticamente](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="09fab-431">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="09fab-432">In **Nuovo pacchetto** immetti i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-432">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="09fab-433">**Scheda Generale**</span><span class="sxs-lookup"><span data-stu-id="09fab-433">**General tab**</span></span>
    - <span data-ttu-id="09fab-434">Nome visualizzato: lasciare vuoto per il momento.</span><span class="sxs-lookup"><span data-stu-id="09fab-434">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="09fab-435">Perché verrà reimpostato quando scegli il tuo pkg.</span><span class="sxs-lookup"><span data-stu-id="09fab-435">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="09fab-436">Categoria: Nessuna (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="09fab-436">Category: None (default)</span></span>
    - <span data-ttu-id="09fab-437">Filename: Choose File</span><span class="sxs-lookup"><span data-stu-id="09fab-437">Filename: Choose File</span></span>

    ![Immagine della scheda generale delle impostazioni di configurazione](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="09fab-439">Aprire il file e puntare a `wdav.pkg` o `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="09fab-439">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Screenshot dello schermo di un computer Descrizione generata automaticamente](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="09fab-441">Seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="09fab-441">Select **Open**.</span></span> <span data-ttu-id="09fab-442">Imposta il **nome visualizzato su** Microsoft Defender Advanced Threat Protection e Microsoft Defender **Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="09fab-442">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="09fab-443">**File manifesto** non obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="09fab-443">**Manifest File** is not required.</span></span> <span data-ttu-id="09fab-444">Microsoft Defender Advanced Threat Protection funziona senza file manifesto.</span><span class="sxs-lookup"><span data-stu-id="09fab-444">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="09fab-445">**Scheda Opzioni**</span><span class="sxs-lookup"><span data-stu-id="09fab-445">**Options tab**</span></span><br> <span data-ttu-id="09fab-446">Mantenere i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="09fab-446">Keep default values.</span></span>

    <span data-ttu-id="09fab-447">**Scheda Limitazioni**</span><span class="sxs-lookup"><span data-stu-id="09fab-447">**Limitations tab**</span></span><br> <span data-ttu-id="09fab-448">Mantenere i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="09fab-448">Keep default values.</span></span>
    
     ![Immagine della scheda limitazione delle impostazioni di configurazione](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="09fab-450">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-450">Select **Save**.</span></span> <span data-ttu-id="09fab-451">Il pacchetto viene caricato in Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="09fab-451">The package is uploaded to Jamf Pro.</span></span> 

   ![Immagine delle impostazioni di configurazione pack upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="09fab-453">La distribuzione del pacchetto può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="09fab-453">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Immagine delle impostazioni di configurazione pack upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="09fab-455">Passare alla **pagina** Criteri.</span><span class="sxs-lookup"><span data-stu-id="09fab-455">Navigate to the **Policies** page.</span></span>

    ![Immagine delle impostazioni di configurazione](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="09fab-457">Selezionare **+ Nuovo** per creare un nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="09fab-457">Select **+ New** to create a new policy.</span></span>

    ![Immagine delle impostazioni di configurazione nuovo criterio](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="09fab-459">In **Generale** Immettere i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="09fab-459">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="09fab-460">Nome visualizzato: MDATP Onboarding Contoso 200329 v100.86.92 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="09fab-460">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="09fab-461">Immagine delle impostazioni di configurazionemdatponboard</span><span class="sxs-lookup"><span data-stu-id="09fab-461">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="09fab-462">Selezionare **Archiviazione ricorrente.**</span><span class="sxs-lookup"><span data-stu-id="09fab-462">Select **Recurring Check-in**.</span></span> 
    
    ![Immagine dell'archiviazione ricorrente delle impostazioni di configurazione](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="09fab-464">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-464">Select **Save**.</span></span> 
 
14. <span data-ttu-id="09fab-465">Selezionare **Pacchetti > Configura**.</span><span class="sxs-lookup"><span data-stu-id="09fab-465">Select **Packages > Configure**.</span></span>
 
    ![Immagine delle impostazioni di configurazione configurate](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="09fab-467">Seleziona il **pulsante** Aggiungi accanto a **Microsoft Defender Advanced Threat Protection e Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="09fab-467">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Immagine delle impostazioni di configurazione MDATP e MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="09fab-469">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="09fab-469">Select **Save**.</span></span>

    ![Immagine delle impostazioni di configurazionesavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="09fab-471">Selezionare la **scheda** Ambito.</span><span class="sxs-lookup"><span data-stu-id="09fab-471">Select the **Scope** tab.</span></span>  

    ![Immagine delle impostazioni di configurazione scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="09fab-473">Selezionare i computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="09fab-473">Select the target computers.</span></span>

    ![Immagine delle impostazioni di configurazione tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="09fab-475">**Ambito**</span><span class="sxs-lookup"><span data-stu-id="09fab-475">**Scope**</span></span>
    
    <span data-ttu-id="09fab-476">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09fab-476">Select **Add**.</span></span>
    
    ![Immagine delle impostazioni di configurazione ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Immagine delle impostazioni di configurazione ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="09fab-479">**Self-Service**</span><span class="sxs-lookup"><span data-stu-id="09fab-479">**Self-Service**</span></span>
    
    ![Immagine delle impostazioni di configurazione selfservice](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="09fab-481">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="09fab-481">Select **Done**.</span></span> 

    ![Immagine delle impostazioni di configurazione do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Immagine delle impostazioni di configurazione do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)



