---
title: Onboarding di dispositivi Windows 10 tramite Criteri di gruppo
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Usa Criteri di gruppo per distribuire il pacchetto di configurazione Windows 10 dispositivi in modo che siano onboarded nel servizio.
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893287"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="6c2f9-103">Onboardare Windows 10 dispositivi con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="6c2f9-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="6c2f9-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6c2f9-104">**Applies to:**</span></span>

- [<span data-ttu-id="6c2f9-105">Microsoft 365 Prevenzione della perdita dei dati degli endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="6c2f9-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="6c2f9-106">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="6c2f9-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="6c2f9-107">Per utilizzare gli aggiornamenti di Criteri di gruppo per distribuire il pacchetto, è necessario essere in Windows Server 2008 R2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="6c2f9-108">Per Windows Server 2019, potrebbe essere necessario sostituire NT AUTHORITY\Well-Known-System-Account con NT AUTHORITY\SYSTEM del file XML creato dalla preferenza di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="6c2f9-109">Aggiungere dispositivi con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="6c2f9-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="6c2f9-110">Aprire il file del pacchetto .zip criteri di gruppo (*DeviceComplianceOnboardingPackage.zip*) scaricato dall'onboarding guidato del servizio.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="6c2f9-111">È anche possibile ottenere il pacchetto dal [Centro conformità Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="6c2f9-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="6c2f9-112">Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="6c2f9-113">Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**</span><span class="sxs-lookup"><span data-stu-id="6c2f9-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="6c2f9-114">Fai **clic su Scarica pacchetto** e salva il file .zip file.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="6c2f9-115">Estrarre il contenuto del file .zip in un percorso condiviso di sola lettura accessibile dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="6c2f9-116">Dovresti avere una cartella denominata *OptionalParamsPolicy* e il file *DeviceComplianceLocalOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="6c2f9-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="6c2f9-117">Aprire console [Gestione Criteri di](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="6c2f9-118">**Nell'Editor Gestione Criteri di gruppo** vai a Configurazione **computer,** quindi **Preferenze** e quindi impostazioni del Pannello **di controllo.**</span><span class="sxs-lookup"><span data-stu-id="6c2f9-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="6c2f9-119">Fare clic con **il pulsante destro del mouse** su Attività pianificate, scegliere Nuovo e quindi Fare clic su Attività immediata **(almeno Windows 7).** </span><span class="sxs-lookup"><span data-stu-id="6c2f9-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="6c2f9-120">Nella **finestra Attività** visualizzata passare alla **scheda** Generale. In **Opzioni di sicurezza** fare clic su Cambia utente o **gruppo** e digitare SISTEMA e quindi fare clic su **Controlla nomi** e quindi su **OK.**</span><span class="sxs-lookup"><span data-stu-id="6c2f9-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="6c2f9-121">NT AUTHORITY\SYSTEM viene visualizzato come account utente con cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="6c2f9-122">Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella di controllo Esegui con **privilegi** più elevati.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="6c2f9-123">Vai alla scheda **Azioni** e fai clic su **Nuovo...** Verificare che **l'opzione Avvia** un programma sia selezionata nel **campo** Azione.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="6c2f9-124">Immettere il nome e il percorso del file *WindowsDefenderATPOnboardingScript.cmd* condiviso.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="6c2f9-125">Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="6c2f9-126">Dispositivi offboard con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="6c2f9-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="6c2f9-127">Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="6c2f9-128">I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="6c2f9-129">Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="6c2f9-130">I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="6c2f9-131">Ottenere il pacchetto di offboarding dal [Centro conformità Microsoft.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="6c2f9-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="6c2f9-132">Nel riquadro di spostamento, selezionare **Impostazioni**  >  **//Onboarding del** dispositivo  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="6c2f9-133">Nel campo **Metodo di distribuzione** selezionare Criteri di **gruppo.**</span><span class="sxs-lookup"><span data-stu-id="6c2f9-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="6c2f9-134">Fai **clic su Scarica pacchetto** e salva il file .zip file.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="6c2f9-135">Estrarre il contenuto del file .zip in un percorso condiviso di sola lettura accessibile dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="6c2f9-136">Dovresti avere un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="6c2f9-137">Aprire console [Gestione Criteri di](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="6c2f9-138">**Nell'Editor Gestione Criteri di gruppo** vai a Configurazione **computer,** Quindi **Preferenze** e quindi Impostazioni pannello **di controllo.**</span><span class="sxs-lookup"><span data-stu-id="6c2f9-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="6c2f9-139">Fare clic con il **pulsante destro del mouse** su Attività pianificate, scegliere **Nuovo** e quindi Fare clic su **Attività immediata.**</span><span class="sxs-lookup"><span data-stu-id="6c2f9-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="6c2f9-140">Nella **finestra Attività** visualizzata passare alla **scheda** Generale. Scegliere l'account utente SYSTEM locale (BUILTIN\SYSTEM) in **Opzioni di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="6c2f9-141">Selezionare **Esegui se l'utente è connesso o meno** e selezionare la **casella** di controllo Esegui con privilegi più elevati.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="6c2f9-142">Passare alla scheda **Azioni** e fare clic su **Nuovo...**. Verificare che **l'opzione Avvia** un programma sia selezionata nel **campo** Azione.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="6c2f9-143">Immettere il nome e il percorso del file *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="6c2f9-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="6c2f9-144">Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c2f9-145">L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="6c2f9-146">Monitorare la configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="6c2f9-146">Monitor device configuration</span></span>
<span data-ttu-id="6c2f9-147">Con Criteri di gruppo non è disponibile un'opzione per monitorare la distribuzione dei criteri nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="6c2f9-148">Il monitoraggio può essere eseguito direttamente nel portale o utilizzando i diversi strumenti di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="6c2f9-149">Monitorare i dispositivi tramite il portale</span><span class="sxs-lookup"><span data-stu-id="6c2f9-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="6c2f9-150">Passare al [Centro conformità Microsoft](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6c2f9-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="6c2f9-151">Fai clic **su Elenco** dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="6c2f9-152">Verificare che i dispositivi siano visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="6c2f9-153">L'inizio della visualizzazione dei dispositivi nell'elenco Dispositivi può richiedere **diversi giorni.**</span><span class="sxs-lookup"><span data-stu-id="6c2f9-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="6c2f9-154">Ciò include il tempo necessario per la distribuzione dei criteri al dispositivo, il tempo necessario prima che l'utente e il tempo necessario per l'avvio dei report da parte dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="6c2f9-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6c2f9-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6c2f9-155">Related topics</span></span>
- [<span data-ttu-id="6c2f9-156">Onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6c2f9-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="6c2f9-157">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="6c2f9-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="6c2f9-158">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="6c2f9-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="6c2f9-159">Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="6c2f9-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="6c2f9-160">Eseguire un test di rilevamento su un Microsoft Defender per dispositivi endpoint appena onboarded</span><span class="sxs-lookup"><span data-stu-id="6c2f9-160">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="6c2f9-161">Risolvere i Microsoft Defender Advanced Threat Protection di onboarding</span><span class="sxs-lookup"><span data-stu-id="6c2f9-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)