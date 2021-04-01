---
title: Onboard di dispositivi Windows 10 in Microsoft Defender ATP tramite Criteri di gruppo
description: Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi Windows 10 in modo che siano onboarded nel servizio.
keywords: configurare i dispositivi usando Criteri di gruppo, gestione dei dispositivi, configurare i dispositivi Windows ATP, onboard microsoft defender per dispositivi endpoint, criteri di gruppo
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: fc4b17ef96e85d3bacd4e83c2de3f4bb7fbfa5c3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166172"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="1f8a8-104">Onboardare dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="1f8a8-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f8a8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-105">**Applies to:**</span></span>

- <span data-ttu-id="1f8a8-106">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="1f8a8-106">Group Policy</span></span>
- [<span data-ttu-id="1f8a8-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1f8a8-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1f8a8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f8a8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1f8a8-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1f8a8-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1f8a8-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="1f8a8-111">Per usare gli aggiornamenti di Criteri di gruppo per distribuire il pacchetto, devi essere in Windows Server 2008 R2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="1f8a8-112">Per Windows Server 2019, potrebbe essere necessario sostituire NT AUTHORITY\Well-Known-System-Account con NT AUTHORITY\SYSTEM del file XML creato dalla preferenza di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="1f8a8-113">Onboardare i dispositivi con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="1f8a8-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="1f8a8-114">[![Immagine del PDF che mostra i vari percorsi di distribuzione](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="1f8a8-115">Consultare il [PDF o](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) per visualizzare i vari percorsi nella distribuzione di Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="1f8a8-116">Aprire il file ZIP del pacchetto di configurazione criteri *di gruppo*(WindowsDefenderATPOnboardingPackage.zip) scaricato dall'onboarding guidato del servizio.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="1f8a8-117">Puoi anche ottenere il pacchetto da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="1f8a8-118">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="1f8a8-119">Seleziona Windows 10 come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="1f8a8-120">Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="1f8a8-121">Fai **clic su Scarica** pacchetto e salva il file ZIP.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="1f8a8-122">Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="1f8a8-123">Dovresti avere una cartella denominata *OptionalParamsPolicy* e il file *WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="1f8a8-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="1f8a8-124">Aprire console [Gestione Criteri di](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-124">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="1f8a8-125">**Nell'Editor Gestione Criteri di gruppo** vai a Configurazione **computer,** quindi **Preferenze** e quindi impostazioni del Pannello **di controllo.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="1f8a8-126">Fare clic con il **pulsante destro del mouse** su Attività pianificate, scegliere **Nuovo** e quindi Attività immediata **(almeno Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="1f8a8-127">Nella **finestra Attività** visualizzata passare alla **scheda** Generale. In **Opzioni di sicurezza** fare clic su Cambia utente o **gruppo** e digitare SISTEMA e quindi fare clic su **Controlla nomi** e quindi su **OK.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="1f8a8-128">NT AUTHORITY\SYSTEM viene visualizzato come account utente con cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="1f8a8-129">Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella di controllo Esegui con **privilegi** più elevati.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="1f8a8-130">Vai alla scheda **Azioni** e fai clic su **Nuovo...** Verificare che **l'opzione Avvia** un programma sia selezionata nel **campo** Azione.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="1f8a8-131">Immettere il nome e il percorso del file *WindowsDefenderATPOnboardingScript.cmd* condiviso.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="1f8a8-132">Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="1f8a8-133">Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che il dispositivo sia stato correttamente onboarding nel servizio.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="1f8a8-134">Per altre informazioni, vedi Eseguire un test di rilevamento in un dispositivo [Defender per endpoint appena onboarded.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="1f8a8-135">Ulteriori impostazioni di configurazione di Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1f8a8-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="1f8a8-136">Per ogni dispositivo, puoi indicare se è possibile raccogliere campioni dal dispositivo quando viene effettuata una richiesta tramite Microsoft Defender Security Center per inviare un file per l'analisi approfondita.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="1f8a8-137">È possibile utilizzare Criteri di gruppo per configurare le impostazioni, ad esempio le impostazioni per la condivisione di esempio utilizzata nella funzionalità di analisi approfondita.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="1f8a8-138">Configurare le impostazioni della raccolta di esempio</span><span class="sxs-lookup"><span data-stu-id="1f8a8-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="1f8a8-139">Nel dispositivo di gestione Criteri di gruppo copiare i file seguenti dal pacchetto di configurazione:</span><span class="sxs-lookup"><span data-stu-id="1f8a8-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="1f8a8-140">Copia _AtpConfiguration.admx_ in _C: \\ Windows \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="1f8a8-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="1f8a8-141">Copia _AtpConfiguration.adml_ in _C: \\ Windows \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="1f8a8-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="1f8a8-142">Se si utilizza un [archivio centrale per i modelli](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)amministrativi di Criteri di gruppo, copiare i file seguenti dal pacchetto di configurazione:</span><span class="sxs-lookup"><span data-stu-id="1f8a8-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="1f8a8-143">Copiare _AtpConfiguration.admx_ in _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="1f8a8-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="1f8a8-144">Copiare _AtpConfiguration.adml_ in _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="1f8a8-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="1f8a8-145">Aprire la [Console Gestione Criteri di gruppo,](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-145">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="1f8a8-146">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="1f8a8-147">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="1f8a8-148">Fare **clic su** Componenti di Windows e quindi Windows Defender **ATP.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6.  <span data-ttu-id="1f8a8-149">Scegli se abilitare o disabilitare la condivisione dei campioni dai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="1f8a8-150">Se non si imposta un valore, il valore predefinito è abilitare la raccolta di esempi.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="1f8a8-151">Altre impostazioni di configurazione consigliate</span><span class="sxs-lookup"><span data-stu-id="1f8a8-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="1f8a8-152">Aggiornare la configurazione di endpoint protection</span><span class="sxs-lookup"><span data-stu-id="1f8a8-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="1f8a8-153">Dopo aver configurato lo script di onboarding, continuare a modificare gli stessi criteri di gruppo per aggiungere configurazioni di endpoint protection.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="1f8a8-154">Eseguire modifiche ai Criteri di gruppo da un sistema che esegue Windows 10 o Server 2019 per assicurarsi di disporre di tutte le funzionalità di Microsoft Defender Antivirus necessarie.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="1f8a8-155">Potrebbe essere necessario chiudere e riaprire l'oggetto Criteri di gruppo per registrare le impostazioni di configurazione di Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="1f8a8-156">Tutti i criteri si trovano in `Computer Configuration\Policies\Administrative Templates` .</span><span class="sxs-lookup"><span data-stu-id="1f8a8-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="1f8a8-157">**Percorso dei criteri:** \Componenti di Windows\Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1f8a8-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="1f8a8-158">Criteri</span><span class="sxs-lookup"><span data-stu-id="1f8a8-158">Policy</span></span> | <span data-ttu-id="1f8a8-159">Impostazione</span><span class="sxs-lookup"><span data-stu-id="1f8a8-159">Setting</span></span> 
:---|:---
<span data-ttu-id="1f8a8-160">Enable\Disable Sample collection</span><span class="sxs-lookup"><span data-stu-id="1f8a8-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="1f8a8-161">Enabled - "Enable sample collection on machines" checked</span><span class="sxs-lookup"><span data-stu-id="1f8a8-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="1f8a8-162">**Percorso dei criteri:**  \Componenti di Windows\Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1f8a8-162">**Policy location:**  \Windows Components\Windows Defender Antivirus</span></span>

<span data-ttu-id="1f8a8-163">Criteri</span><span class="sxs-lookup"><span data-stu-id="1f8a8-163">Policy</span></span> | <span data-ttu-id="1f8a8-164">Impostazione</span><span class="sxs-lookup"><span data-stu-id="1f8a8-164">Setting</span></span> 
:---|:---
<span data-ttu-id="1f8a8-165">Configurare il rilevamento per applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="1f8a8-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="1f8a8-166">Enabled, Block</span><span class="sxs-lookup"><span data-stu-id="1f8a8-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="1f8a8-167">**Percorso dei criteri:** \Componenti di Windows\Windows Defender Antivirus\MAPS</span><span class="sxs-lookup"><span data-stu-id="1f8a8-167">**Policy location:** \Windows Components\Windows Defender Antivirus\MAPS</span></span>

<span data-ttu-id="1f8a8-168">Criteri</span><span class="sxs-lookup"><span data-stu-id="1f8a8-168">Policy</span></span> | <span data-ttu-id="1f8a8-169">Impostazione</span><span class="sxs-lookup"><span data-stu-id="1f8a8-169">Setting</span></span> 
:---|:---
<span data-ttu-id="1f8a8-170">Partecipare a Microsoft MAPS</span><span class="sxs-lookup"><span data-stu-id="1f8a8-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="1f8a8-171">Enabled, Advanced MAPS</span><span class="sxs-lookup"><span data-stu-id="1f8a8-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="1f8a8-172">Inviare esempi di file quando è necessaria un'ulteriore analisi</span><span class="sxs-lookup"><span data-stu-id="1f8a8-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="1f8a8-173">Enabled, Send safe samples</span><span class="sxs-lookup"><span data-stu-id="1f8a8-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="1f8a8-174">**Percorso dei criteri:** \Componenti di Windows\Windows Defender Antivirus\Protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="1f8a8-174">**Policy location:** \Windows Components\Windows Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="1f8a8-175">Criteri</span><span class="sxs-lookup"><span data-stu-id="1f8a8-175">Policy</span></span> | <span data-ttu-id="1f8a8-176">Impostazione</span><span class="sxs-lookup"><span data-stu-id="1f8a8-176">Setting</span></span> 
:---|:---
<span data-ttu-id="1f8a8-177">Disattivare la protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="1f8a8-177">Turn off real-time protection</span></span>|<span data-ttu-id="1f8a8-178">Disattivato</span><span class="sxs-lookup"><span data-stu-id="1f8a8-178">Disabled</span></span>
<span data-ttu-id="1f8a8-179">Attivare il monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="1f8a8-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="1f8a8-180">Abilitato</span><span class="sxs-lookup"><span data-stu-id="1f8a8-180">Enabled</span></span>
<span data-ttu-id="1f8a8-181">Analizzare tutti i file e gli allegati scaricati</span><span class="sxs-lookup"><span data-stu-id="1f8a8-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="1f8a8-182">Abilitato</span><span class="sxs-lookup"><span data-stu-id="1f8a8-182">Enabled</span></span>
<span data-ttu-id="1f8a8-183">Monitorare le attività di file e programmi nel computer</span><span class="sxs-lookup"><span data-stu-id="1f8a8-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="1f8a8-184">Abilitato</span><span class="sxs-lookup"><span data-stu-id="1f8a8-184">Enabled</span></span>

<br/>

<span data-ttu-id="1f8a8-185">**Percorso dei criteri:**  \Componenti di Windows\Windows Defender Antivirus\Scan</span><span class="sxs-lookup"><span data-stu-id="1f8a8-185">**Policy location:**  \Windows Components\Windows Defender Antivirus\Scan</span></span>

<span data-ttu-id="1f8a8-186">Queste impostazioni configurano analisi periodiche dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="1f8a8-187">È consigliabile eseguire un'analisi rapida settimanale, permettendo le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="1f8a8-188">Criteri</span><span class="sxs-lookup"><span data-stu-id="1f8a8-188">Policy</span></span> | <span data-ttu-id="1f8a8-189">Impostazione</span><span class="sxs-lookup"><span data-stu-id="1f8a8-189">Setting</span></span> 
:---|:---
<span data-ttu-id="1f8a8-190">Prima di eseguire un'analisi pianificata, verificare la disponibilità delle informazioni di sicurezza più recenti su virus e spyware</span><span class="sxs-lookup"><span data-stu-id="1f8a8-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="1f8a8-191">Abilitato</span><span class="sxs-lookup"><span data-stu-id="1f8a8-191">Enabled</span></span>


<br/>

<span data-ttu-id="1f8a8-192">**Posizione dei criteri:** \Componenti di Windows\Windows Defender Antivirus\Windows Defender Exploit Guard\Riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="1f8a8-192">**Policy location:** \Windows Components\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="1f8a8-193">Ottenere l'elenco corrente dei GUID di riduzione della superficie di attacco da [Personalizzare le regole di riduzione della superficie di attacco](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="1f8a8-194">Apri il **criterio Configura riduzione superficie di** attacco.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="1f8a8-195">Selezionare **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="1f8a8-196">Selezionare il **pulsante** Mostra.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="1f8a8-197">Aggiungere ogni GUID nel **campo Nome valore** con un valore pari a 2.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="1f8a8-198">Questa impostazione verrà impostata solo per il controllo.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-198">This will set each up for audit only.</span></span>

   ![Immagine della configurazione di riduzione della superficie di attacco](images/asr-guid.png)



<span data-ttu-id="1f8a8-200">Criteri</span><span class="sxs-lookup"><span data-stu-id="1f8a8-200">Policy</span></span> | <span data-ttu-id="1f8a8-201">Impostazione</span><span class="sxs-lookup"><span data-stu-id="1f8a8-201">Setting</span></span> 
:---|:---
<span data-ttu-id="1f8a8-202">Configurare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="1f8a8-202">Configure Controlled folder access</span></span>| <span data-ttu-id="1f8a8-203">Abilitato, modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="1f8a8-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="1f8a8-204">Dispositivi offboard con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="1f8a8-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="1f8a8-205">Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="1f8a8-206">I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="1f8a8-207">Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="1f8a8-208">I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="1f8a8-209">Ottenere il pacchetto di offboarding da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="1f8a8-210">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Offboarding.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="1f8a8-211">Seleziona Windows 10 come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="1f8a8-212">Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="1f8a8-213">Fai **clic su Scarica** pacchetto e salva il file ZIP.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="1f8a8-214">Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="1f8a8-215">Dovresti avere un file denominato *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="1f8a8-216">Aprire console [Gestione Criteri di](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-216">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="1f8a8-217">**Nell'Editor Gestione Criteri di gruppo** vai a Configurazione **computer,** Quindi **Preferenze** e quindi Impostazioni pannello **di controllo.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="1f8a8-218">Fare clic con il **pulsante destro del mouse** su Attività pianificate, scegliere **Nuovo** e quindi Fare clic su **Attività immediata.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="1f8a8-219">Nella **finestra Attività** visualizzata passare alla **scheda** Generale. Scegliere l'account utente SYSTEM locale (BUILTIN\SYSTEM) in **Opzioni di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="1f8a8-220">Selezionare **Esegui se l'utente è connesso o meno** e selezionare la **casella** di controllo Esegui con privilegi più elevati.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="1f8a8-221">Passare alla scheda **Azioni** e fare clic su **Nuovo...**. Verificare che **l'opzione Avvia** un programma sia selezionata nel **campo** Azione.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="1f8a8-222">Immettere il nome e il percorso del file  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* condiviso.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="1f8a8-223">Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f8a8-224">L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="1f8a8-225">Monitorare la configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1f8a8-225">Monitor device configuration</span></span>
<span data-ttu-id="1f8a8-226">Con Criteri di gruppo non è disponibile un'opzione per monitorare la distribuzione dei criteri nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="1f8a8-227">Il monitoraggio può essere eseguito direttamente nel portale o utilizzando i diversi strumenti di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="1f8a8-228">Monitorare i dispositivi tramite il portale</span><span class="sxs-lookup"><span data-stu-id="1f8a8-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="1f8a8-229">Passare a [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="1f8a8-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="1f8a8-230">Fare **clic su Elenco dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="1f8a8-231">Verificare che i dispositivi siano visualizzati.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="1f8a8-232">L'inizio della visualizzazione dei dispositivi nell'elenco Dispositivi può richiedere **diversi giorni.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="1f8a8-233">Ciò include il tempo necessario per la distribuzione dei criteri al dispositivo, il tempo necessario prima che l'utente e il tempo necessario per l'avvio dei report da parte dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1f8a8-234">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1f8a8-234">Related topics</span></span>
- [<span data-ttu-id="1f8a8-235">Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1f8a8-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="1f8a8-236">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="1f8a8-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="1f8a8-237">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="1f8a8-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="1f8a8-238">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="1f8a8-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="1f8a8-239">Eseguire un test di rilevamento su un Microsoft Defender per dispositivi endpoint appena onboarded</span><span class="sxs-lookup"><span data-stu-id="1f8a8-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="1f8a8-240">Risolvere i problemi di onboarding di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1f8a8-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)