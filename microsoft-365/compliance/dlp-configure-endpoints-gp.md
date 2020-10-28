---
title: Dispositivi di bordo di Windows 10 tramite criteri di gruppo
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
description: Utilizzare criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi Windows 10 in modo che siano onboarded to the Service.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769446"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="9cdc2-103">Dispositivi di bordo di Windows 10 con criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="9cdc2-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="9cdc2-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9cdc2-104">**Applies to:**</span></span>

- [<span data-ttu-id="9cdc2-105">Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint</span><span class="sxs-lookup"><span data-stu-id="9cdc2-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="9cdc2-106">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="9cdc2-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="9cdc2-107">Per utilizzare gli aggiornamenti di criteri di gruppo per distribuire il pacchetto, è necessario essere su Windows Server 2008 R2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="9cdc2-108">Per Windows Server 2019, potrebbe essere necessario sostituire NT AUTHORITY\Well-Known-System-Account con NT AUTHORITY\SYSTEM del file XML creato dalla preferenza di criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="9cdc2-109">Dispositivi di bordo che utilizzano criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="9cdc2-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="9cdc2-110">Aprire il file con estensione zip del pacchetto di configurazione GP ( *DeviceComplianceOnboardingPackage.zip* ) scaricato dalla procedura guidata di onboarding dei servizi.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-110">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="9cdc2-111">È anche possibile ottenere il pacchetto dal [centro conformità Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="9cdc2-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="9cdc2-112">Nel riquadro di spostamento, selezionare **Settings**  >  **onboarding del dispositivo** di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-112">In the navigation pane, select **Settings** > **Device Onboarding** .</span></span>

3. <span data-ttu-id="9cdc2-113">Nel campo **metodo di distribuzione** selezionare **criteri di gruppo** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-113">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="9cdc2-114">Fare clic su **Download package** e salvare il file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="9cdc2-115">Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="9cdc2-116">È necessario disporre di una cartella denominata *OptionalParamsPolicy* e del file *DeviceComplianceLocalOnboardingScript. cmd* .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="9cdc2-117">Aprire la [console Gestione criteri di gruppo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **modifica** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="9cdc2-118">In **Editor gestione criteri di gruppo** andare a **Configurazione computer** , quindi **Preferenze** e quindi impostazioni del **Pannello di controllo** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-118">In the **Group Policy Management Editor** , go to **Computer configuration** , then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="9cdc2-119">Fare clic con il pulsante destro del mouse su **attività pianificate** , scegliere **nuovo** e quindi fare clic su **attività immediata (almeno Windows 7)** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-119">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate Task (At least Windows 7)** .</span></span>

9. <span data-ttu-id="9cdc2-120">Nella finestra **attività** visualizzata passare alla scheda **generale** . In **Opzioni di sicurezza** fare clic su **Cambia utente o gruppo** e digitare sistema e quindi fare clic su **Controlla nomi** e quindi su **OK** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK** .</span></span> <span data-ttu-id="9cdc2-121">NT AUTHORITY\SYSTEM viene visualizzato come account utente in cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="9cdc2-122">Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella **di controllo Esegui con i privilegi più alti** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="9cdc2-123">Passare alla scheda **azioni** e fare clic su **nuovo...** Verificare che sia selezionata l'opzione **avvia un programma** nel campo **azione** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="9cdc2-124">Immettere il nome del file e il percorso del file *WindowsDefenderATPOnboardingScript. cmd* condiviso.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="9cdc2-125">Fare clic su **OK** e chiudere tutte le finestre aperte di GPMC.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="9cdc2-126">Dispositivi di trasferisce che utilizzano criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="9cdc2-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="9cdc2-127">Per motivi di sicurezza, il pacchetto utilizzato per i dispositivi di trasferisce scadrà 30 giorni dopo la data in cui è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="9cdc2-128">I pacchetti di Offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="9cdc2-129">Quando si scarica un pacchetto di Offboarding verrà inviata una notifica alla data di scadenza dei pacchetti e verrà incluso anche il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="9cdc2-130">I criteri di onboarding e offboarding non devono essere distribuiti contemporaneamente nello stesso dispositivo, altrimenti ciò provocherà collisioni imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="9cdc2-131">Ottenere il pacchetto offboarding dal [centro conformità Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span><span class="sxs-lookup"><span data-stu-id="9cdc2-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="9cdc2-132">Nel riquadro di spostamento, selezionare **Impostazioni**  >  **//Device onboarding**  >  **offboarding** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="9cdc2-133">Nel campo **metodo di distribuzione** selezionare **criteri di gruppo** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-133">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="9cdc2-134">Fare clic su **Download package** e salvare il file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="9cdc2-135">Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="9cdc2-136">È necessario disporre di un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6. <span data-ttu-id="9cdc2-137">Aprire la [console Gestione criteri di gruppo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **modifica** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="9cdc2-138">In **Editor gestione criteri di gruppo** andare a **Configurazione computer,** quindi **Preferenze** e quindi impostazioni del **Pannello di controllo** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-138">In the **Group Policy Management Editor** , go to **Computer configuration,** then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="9cdc2-139">Fare clic con il pulsante destro del mouse su **attività pianificate** , scegliere **nuovo** e quindi fare clic su **attività immediata** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-139">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate task** .</span></span>

9. <span data-ttu-id="9cdc2-140">Nella finestra **attività** visualizzata passare alla scheda **generale** . Scegliere l'account utente del sistema locale (BUILTIN\SYSTEM) in **Opzioni di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options** .</span></span>

10. <span data-ttu-id="9cdc2-141">Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella **di controllo Esegui con i privilegi più alti** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="9cdc2-142">Passare alla scheda **azioni** e fare clic su **nuovo...** . Verificare che sia selezionata l'opzione **avvia un programma** nel campo **azione** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-142">Go to the **Actions** tab and click **New...** . Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="9cdc2-143">Immettere il nome del file e il percorso del file di  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* condiviso.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="9cdc2-144">Fare clic su **OK** e chiudere tutte le finestre aperte di GPMC.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cdc2-145">Offboarding fa in modo che il dispositivo smetta di inviare i dati del sensore al portale, ma i dati del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="9cdc2-146">Monitorare la configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="9cdc2-146">Monitor device configuration</span></span>
<span data-ttu-id="9cdc2-147">Con criteri di gruppo non è disponibile un'opzione per monitorare la distribuzione dei criteri nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="9cdc2-148">Il monitoraggio può essere effettuato direttamente sul portale oppure tramite gli strumenti di distribuzione diversi.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="9cdc2-149">Monitorare i dispositivi tramite il portale</span><span class="sxs-lookup"><span data-stu-id="9cdc2-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="9cdc2-150">Accedere al [centro conformità Microsoft](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9cdc2-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="9cdc2-151">Fare clic su elenco **dispositivi** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="9cdc2-152">Verificare che i dispositivi vengano visualizzati.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="9cdc2-153">È possibile che i dispositivi vengano visualizzati alcuni giorni nell' **elenco dispositivi** .</span><span class="sxs-lookup"><span data-stu-id="9cdc2-153">It can take several days for devices to start showing on the **Devices list** .</span></span> <span data-ttu-id="9cdc2-154">Questo include il tempo necessario per la distribuzione dei criteri nel dispositivo, il tempo necessario per l'accesso dell'utente e il tempo necessario per l'avvio dei report da parte dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9cdc2-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9cdc2-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9cdc2-155">Related topics</span></span>
- [<span data-ttu-id="9cdc2-156">Dispositivi di bordo di Windows 10 con Microsoft endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9cdc2-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="9cdc2-157">Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="9cdc2-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="9cdc2-158">Dispositivi di bordo di Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="9cdc2-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="9cdc2-159">Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo</span><span class="sxs-lookup"><span data-stu-id="9cdc2-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="9cdc2-160">Eseguire un test di rilevamento su un dispositivo ATP Microsoft Defender appena integrato</span><span class="sxs-lookup"><span data-stu-id="9cdc2-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="9cdc2-161">Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9cdc2-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
