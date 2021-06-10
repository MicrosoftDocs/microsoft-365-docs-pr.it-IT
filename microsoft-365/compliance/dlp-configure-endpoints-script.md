---
title: Onboarding di dispositivi Windows 10 con uno script locale
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
description: Usa uno script locale per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded nel servizio.
ms.openlocfilehash: 55109d8fda52db6651d4398cd84ffd6668b4d871
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843447"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="b2e0f-103">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="b2e0f-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="b2e0f-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b2e0f-104">**Applies to:**</span></span>

- [<span data-ttu-id="b2e0f-105">Microsoft 365 Prevenzione della perdita dei dati degli endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="b2e0f-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="b2e0f-106">Puoi anche eseguire manualmente l'onboardboard dei singoli dispositivi per Microsoft 365 prevenzione della perdita dei dati dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="b2e0f-107">È consigliabile eseguire questa operazione prima di testare il servizio prima di eseguire l'onboarding di tutti i dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2e0f-108">Questo script è stato ottimizzato per l'uso su un massimo di 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="b2e0f-109">Per eseguire la distribuzione su larga scala, [utilizzare altre opzioni di distribuzione.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="b2e0f-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="b2e0f-110">Ad esempio, puoi distribuire uno script di onboarding in più di 10 dispositivi in produzione con lo script disponibile in Onboard Windows 10 dispositivi usando [Criteri di gruppo.](dlp-configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="b2e0f-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="b2e0f-111">Eseguire l'onboarding dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="b2e0f-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="b2e0f-112">Aprire il file del pacchetto .zip criteri di gruppo (*DeviceComplianceOnboardingPackage.zip*) scaricato dall'onboarding guidato del servizio.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="b2e0f-113">È anche possibile ottenere il pacchetto dal [Centro conformità Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b2e0f-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="b2e0f-114">Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="b2e0f-115">Nel campo **Metodo di** distribuzione selezionare **Script locale**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="b2e0f-116">Fai **clic su Scarica pacchetto** e salva il file .zip file.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="b2e0f-117">Estrai il contenuto del pacchetto di configurazione in una posizione nel dispositivo che vuoi eseguire l'onboard(ad esempio, desktop).</span><span class="sxs-lookup"><span data-stu-id="b2e0f-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="b2e0f-118">Dovresti avere un file denominato *DeviceOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="b2e0f-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="b2e0f-119">Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:</span><span class="sxs-lookup"><span data-stu-id="b2e0f-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="b2e0f-120">Passare a **Start** e digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="b2e0f-121">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Menu Start finestra che punta a Esegui come amministratore](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="b2e0f-123">Digitare il percorso del file script.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-123">Type the location of the script file.</span></span> <span data-ttu-id="b2e0f-124">Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="b2e0f-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="b2e0f-125">Premere INVIO **o** fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="b2e0f-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="b2e0f-126">Per informazioni su come è possibile convalidare manualmente che il dispositivo sia conforme e che i dati del sensore vengano correttamente segnalati, vedere Risoluzione dei Microsoft Defender Advanced Threat Protection problemi di [onboarding.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="b2e0f-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="b2e0f-127">Dispositivi offboard con uno script locale</span><span class="sxs-lookup"><span data-stu-id="b2e0f-127">Offboard devices using a local script</span></span>
<span data-ttu-id="b2e0f-128">Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="b2e0f-129">I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="b2e0f-130">Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="b2e0f-131">I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="b2e0f-132">Ottenere il pacchetto di offboarding dal [Centro conformità Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b2e0f-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="b2e0f-133">Nel riquadro di spostamento seleziona **Impostazioni**  >  **offboarding del dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="b2e0f-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="b2e0f-134">Nel campo **Metodo di** distribuzione selezionare **Script locale**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="b2e0f-135">Fai **clic su Scarica pacchetto** e salva il file .zip file.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="b2e0f-136">Estrarre il contenuto del file .zip in un percorso condiviso di sola lettura accessibile dai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="b2e0f-137">Dovresti avere un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="b2e0f-138">Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:</span><span class="sxs-lookup"><span data-stu-id="b2e0f-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="b2e0f-139">Passare a **Start** e digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="b2e0f-140">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Menu Start finestra che punta a Esegui come amministratore](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="b2e0f-142">Digitare il percorso del file script.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-142">Type the location of the script file.</span></span> <span data-ttu-id="b2e0f-143">Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="b2e0f-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="b2e0f-144">Premere INVIO **o** fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="b2e0f-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2e0f-145">L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="b2e0f-146">Monitorare la configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b2e0f-146">Monitor device configuration</span></span>
<span data-ttu-id="b2e0f-147">Puoi seguire i diversi passaggi di verifica in [Risolvere i problemi di onboarding]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) per verificare che lo script sia stato completato correttamente e che l'agente sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="b2e0f-148">Il monitoraggio può essere eseguito anche direttamente nel portale o utilizzando i diversi strumenti di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="b2e0f-149">Monitorare i dispositivi tramite il portale</span><span class="sxs-lookup"><span data-stu-id="b2e0f-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="b2e0f-150">Vai a [Microsoft 365 conformità](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b2e0f-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="b2e0f-151">Scegliere **Impostazioni**  >  **dispositivi di onboarding del**  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="b2e0f-152">Verificare che i dispositivi siano visualizzati.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b2e0f-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b2e0f-153">Related topics</span></span>
- [<span data-ttu-id="b2e0f-154">Onboardare Windows 10 dispositivi con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="b2e0f-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="b2e0f-155">Onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b2e0f-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="b2e0f-156">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="b2e0f-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="b2e0f-157">Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="b2e0f-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="b2e0f-158">Eseguire un test di rilevamento in un dispositivo Microsoft Defender for Endpoint appena onboarded</span><span class="sxs-lookup"><span data-stu-id="b2e0f-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="b2e0f-159">Risolvere i Microsoft Defender Advanced Threat Protection di onboarding</span><span class="sxs-lookup"><span data-stu-id="b2e0f-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)