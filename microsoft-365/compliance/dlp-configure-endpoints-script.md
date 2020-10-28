---
title: Dispositivi di bordo di Windows 10 con uno script locale
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
description: Utilizzare uno script locale per distribuire il pacchetto di configurazione nei dispositivi in modo che vengano onboarded to the Service.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769470"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="3a7fd-103">Dispositivi di bordo di Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="3a7fd-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="3a7fd-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3a7fd-104">**Applies to:**</span></span>

- [<span data-ttu-id="3a7fd-105">Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint</span><span class="sxs-lookup"><span data-stu-id="3a7fd-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="3a7fd-106">È inoltre possibile eseguire manualmente l'onboarding dei singoli dispositivi per la prevenzione della perdita di dati di Microsoft 365 endpoint.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="3a7fd-107">Potrebbe essere necessario eseguire questa operazione prima quando si verifica il servizio prima di eseguire l'onboarding di tutti i dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a7fd-108">Questo script è stato ottimizzato per l'uso su un massimo di 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="3a7fd-109">Per eseguire la distribuzione in scala, utilizzare [altre opzioni di distribuzione](dlp-configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="3a7fd-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="3a7fd-110">Ad esempio, è possibile distribuire uno script onboarding su più di 10 dispositivi in produzione con lo script disponibile nei [dispositivi di bordo di Windows 10 utilizzando criteri di gruppo](dlp-configure-endpoints-gp.md).</span><span class="sxs-lookup"><span data-stu-id="3a7fd-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="3a7fd-111">Dispositivi di bordo</span><span class="sxs-lookup"><span data-stu-id="3a7fd-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="3a7fd-112">Aprire il file con estensione zip del pacchetto di configurazione GP ( *DeviceComplianceOnboardingPackage.zip* ) scaricato dalla procedura guidata di onboarding dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-112">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="3a7fd-113">È anche possibile ottenere il pacchetto dal [centro conformità Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3a7fd-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="3a7fd-114">Nel riquadro di spostamento, selezionare **Settings**  >  **onboarding del dispositivo** di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-114">In the navigation pane, select **Settings** > **Device onboarding** .</span></span>

3. <span data-ttu-id="3a7fd-115">Nel campo **metodo di distribuzione** selezionare **script locale** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-115">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="3a7fd-116">Fare clic su **Download package** e salvare il file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="3a7fd-117">Estrarre il contenuto del pacchetto di configurazione in una posizione nel dispositivo che si desidera Onboard (ad esempio, il desktop).</span><span class="sxs-lookup"><span data-stu-id="3a7fd-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="3a7fd-118">È necessario disporre di un file denominato *DeviceOnboardingScript. cmd* .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-118">You should have a file named *DeviceOnboardingScript.cmd* .</span></span>

6.  <span data-ttu-id="3a7fd-119">Aprire una finestra del prompt dei comandi con privilegi elevati nel dispositivo ed eseguire lo script:</span><span class="sxs-lookup"><span data-stu-id="3a7fd-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="3a7fd-120">Andare a **Start** e digitare **cmd** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-120">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="3a7fd-121">Fare clic con il pulsante destro del mouse su **prompt dei comandi** e scegliere **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-121">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Menu Start della finestra che punta all'esecuzione come amministratore](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="3a7fd-123">Digitare il percorso del file di script.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-123">Type the location of the script file.</span></span> <span data-ttu-id="3a7fd-124">Se il file è stato copiato sul desktop, digitare: *%USERPROFILE%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="3a7fd-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="3a7fd-125">Premere il tasto **invio** o fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-125">Press the **Enter** key or click **OK** .</span></span>

<span data-ttu-id="3a7fd-126">Per informazioni su come è possibile convalidare manualmente che il dispositivo è conforme e segnala correttamente i dati del sensore, vedere [risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="3a7fd-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="3a7fd-127">Dispositivi di trasferisce che utilizzano uno script locale</span><span class="sxs-lookup"><span data-stu-id="3a7fd-127">Offboard devices using a local script</span></span>
<span data-ttu-id="3a7fd-128">Per motivi di sicurezza, il pacchetto utilizzato per i dispositivi di trasferisce scadrà 30 giorni dopo la data in cui è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="3a7fd-129">I pacchetti di Offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="3a7fd-130">Quando si scarica un pacchetto di Offboarding verrà inviata una notifica alla data di scadenza dei pacchetti e verrà incluso anche il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="3a7fd-131">I criteri di onboarding e offboarding non devono essere distribuiti contemporaneamente nello stesso dispositivo, altrimenti ciò provocherà collisioni imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="3a7fd-132">Ottenere il pacchetto offboarding dal [centro conformità Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3a7fd-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="3a7fd-133">Nel riquadro di spostamento, selezionare **Impostazioni**  >  **dispositivo offboarding** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-133">In the navigation pane, select **Settings** > **Device offboarding** .</span></span>

3. <span data-ttu-id="3a7fd-134">Nel campo **metodo di distribuzione** selezionare **script locale** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-134">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="3a7fd-135">Fare clic su **Download package** e salvare il file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="3a7fd-136">Estrarre il contenuto del file con estensione zip in una posizione condivisa, di sola lettura, a cui è possibile accedere dai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="3a7fd-137">È necessario disporre di un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6.  <span data-ttu-id="3a7fd-138">Aprire una finestra del prompt dei comandi con privilegi elevati nel dispositivo ed eseguire lo script:</span><span class="sxs-lookup"><span data-stu-id="3a7fd-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="3a7fd-139">Andare a **Start** e digitare **cmd** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-139">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="3a7fd-140">Fare clic con il pulsante destro del mouse su **prompt dei comandi** e scegliere **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-140">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Menu Start della finestra che punta all'esecuzione come amministratore](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="3a7fd-142">Digitare il percorso del file di script.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-142">Type the location of the script file.</span></span> <span data-ttu-id="3a7fd-143">Se il file è stato copiato sul desktop, digitare: *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd. cmd*</span><span class="sxs-lookup"><span data-stu-id="3a7fd-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="3a7fd-144">Premere il tasto **invio** o fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-144">Press the **Enter** key or click **OK** .</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a7fd-145">Offboarding fa in modo che il dispositivo smetta di inviare i dati del sensore al portale.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="3a7fd-146">Monitorare la configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3a7fd-146">Monitor device configuration</span></span>
<span data-ttu-id="3a7fd-147">È possibile seguire i diversi passaggi di verifica riportati nell'argomento [risoluzione dei problemi relativi all'onboarding] ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) per verificare che lo script sia stato completato correttamente e che l'agente sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="3a7fd-148">Il monitoraggio può essere effettuato anche direttamente sul portale oppure tramite gli strumenti di distribuzione diversi.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="3a7fd-149">Monitorare i dispositivi tramite il portale</span><span class="sxs-lookup"><span data-stu-id="3a7fd-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="3a7fd-150">Accedere a [Microsoft 365 Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3a7fd-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="3a7fd-151">Scegliere **Settings**  >  **dispositivo onboarding**  >  **Devices** .</span><span class="sxs-lookup"><span data-stu-id="3a7fd-151">Choose **Settings** > **Device onboarding** > **Devices** .</span></span>

3. <span data-ttu-id="3a7fd-152">Verificare che i dispositivi vengano visualizzati.</span><span class="sxs-lookup"><span data-stu-id="3a7fd-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3a7fd-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3a7fd-153">Related topics</span></span>
- [<span data-ttu-id="3a7fd-154">Dispositivi di bordo di Windows 10 con criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="3a7fd-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="3a7fd-155">Dispositivi di bordo di Windows 10 con Microsoft endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3a7fd-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="3a7fd-156">Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="3a7fd-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="3a7fd-157">Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo</span><span class="sxs-lookup"><span data-stu-id="3a7fd-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="3a7fd-158">Eseguire un test di rilevamento su un dispositivo ATP Microsoft Defender appena integrato</span><span class="sxs-lookup"><span data-stu-id="3a7fd-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="3a7fd-159">Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3a7fd-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
