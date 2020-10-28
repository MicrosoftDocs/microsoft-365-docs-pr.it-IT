---
title: Dispositivi di bordo di Windows 10 con Configuration Manager
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
description: Utilizzare Configuration Manager per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded al servizio.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769479"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="fe65c-103">Dispositivi di bordo di Windows 10 con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fe65c-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="fe65c-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fe65c-104">**Applies to:**</span></span>

- [<span data-ttu-id="fe65c-105">Prevenzione della perdita di dati (DLP) di Microsoft 365 endpoint</span><span class="sxs-lookup"><span data-stu-id="fe65c-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="fe65c-106">System Center Configuration Manager 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fe65c-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="fe65c-107">Dispositivi di bordo tramite System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fe65c-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="fe65c-108">Aprire il file con estensione zip del pacchetto di configurazione di Configuration Manager ( *DeviceComplianceOnboardingPackage.zip* ) scaricato dalla procedura guidata di onboarding dei servizi.</span><span class="sxs-lookup"><span data-stu-id="fe65c-108">Open the Configuration Manager configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="fe65c-109">È anche possibile ottenere il pacchetto dal [centro conformità Microsoft](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fe65c-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="fe65c-110">Nel riquadro di spostamento selezionare impostazioni onboarding del dispositivo di **configurazione**  >  **Device Onboarding**  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="fe65c-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="fe65c-111">Nel campo **metodo di distribuzione** selezionare **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span><span class="sxs-lookup"><span data-stu-id="fe65c-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
 
4. <span data-ttu-id="fe65c-112">Selezionare **Download package** e salvare il file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="fe65c-112">Select **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="fe65c-113">Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere gli amministratori di rete che distribuiscono il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fe65c-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="fe65c-114">È necessario disporre di un file denominato *DeviceComplianceOnboardingScript. cmd* .</span><span class="sxs-lookup"><span data-stu-id="fe65c-114">You should have a file named *DeviceComplianceOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="fe65c-115">Distribuire il pacchetto attenendosi alla procedura descritta nell'articolo [packages and programmes in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .</span><span class="sxs-lookup"><span data-stu-id="fe65c-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="fe65c-116">Scegliere un insieme di dispositivi predefinito per la distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fe65c-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="fe65c-117">Microsoft 365 endpoint la prevenzione della perdita dei dati non supporta l'onboarding durante la fase [di out-of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) .</span><span class="sxs-lookup"><span data-stu-id="fe65c-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="fe65c-118">Assicurarsi che gli utenti completino OOBE dopo l'esecuzione dell'installazione o dell'aggiornamento di Windows.</span><span class="sxs-lookup"><span data-stu-id="fe65c-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="fe65c-119">Dopo aver eseguito l'onboarding del dispositivo, è possibile scegliere di eseguire un test di rilevamento per verificare che un dispositivo sia correttamente onboarded to the Service.</span><span class="sxs-lookup"><span data-stu-id="fe65c-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="fe65c-120">Per ulteriori informazioni, vedere [eseguire un test di rilevamento su un dispositivo ATP Microsoft Defender appena integrato](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span><span class="sxs-lookup"><span data-stu-id="fe65c-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="fe65c-121">Si noti che è possibile creare una regola di rilevamento su un'applicazione di Configuration Manager per controllare continuamente se un dispositivo è stato onboarded.</span><span class="sxs-lookup"><span data-stu-id="fe65c-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="fe65c-122">Un'applicazione è un tipo di oggetto diverso rispetto a un pacchetto e a un programma.</span><span class="sxs-lookup"><span data-stu-id="fe65c-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="fe65c-123">Se un dispositivo non è ancora stato onboarded (a causa del completamento di OOBE in sospeso o di qualsiasi altro motivo), Configuration Manager ritenterà di onboard il dispositivo finché la regola non rileverà la modifica dello stato.</span><span class="sxs-lookup"><span data-stu-id="fe65c-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="fe65c-124">Questo comportamento può essere ottenuto creando una regola di rilevamento che controlla se il valore del registro di sistema "OnboardingState" (di tipo REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="fe65c-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="fe65c-125">Questo valore del registro di sistema si trova in "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="fe65c-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="fe65c-126">Per ulteriori informazioni, vedere [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span><span class="sxs-lookup"><span data-stu-id="fe65c-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="fe65c-127">Configurare le impostazioni di raccolta di esempio</span><span class="sxs-lookup"><span data-stu-id="fe65c-127">Configure sample collection settings</span></span>

<span data-ttu-id="fe65c-128">Per ogni dispositivo, è possibile impostare un valore di configurazione per indicare se è possibile raccogliere campioni dal dispositivo quando viene effettuata una richiesta tramite Microsoft Defender Security Center per inviare un file per un'analisi approfondita.</span><span class="sxs-lookup"><span data-stu-id="fe65c-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="fe65c-129">Queste impostazioni di configurazione vengono in genere eseguite tramite Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fe65c-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="fe65c-130">È possibile impostare una regola di conformità per l'elemento di configurazione in Configuration Manager per modificare l'impostazione di condivisione di esempio in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe65c-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="fe65c-131">Questa regola deve essere un *elemento di configurazione* della regola di conformità che consente di impostare il valore di una chiave del registro di sistema nei dispositivi di destinazione per assicurarsi che siano reclami.</span><span class="sxs-lookup"><span data-stu-id="fe65c-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="fe65c-132">La configurazione viene impostata tramite la seguente voce della chiave del registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="fe65c-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="fe65c-133">Dove:</span><span class="sxs-lookup"><span data-stu-id="fe65c-133">Where:</span></span><br>
<span data-ttu-id="fe65c-134">Il tipo di chiave è una D-WORD.</span><span class="sxs-lookup"><span data-stu-id="fe65c-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="fe65c-135">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fe65c-135">Possible values are:</span></span>
- <span data-ttu-id="fe65c-136">0-non consente la condivisione di campioni da questo dispositivo</span><span class="sxs-lookup"><span data-stu-id="fe65c-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="fe65c-137">1-consente la condivisione di tutti i tipi di file da questo dispositivo</span><span class="sxs-lookup"><span data-stu-id="fe65c-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="fe65c-138">Il valore predefinito nel caso in cui la chiave del registro di sistema non esiste è 1.</span><span class="sxs-lookup"><span data-stu-id="fe65c-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="fe65c-139">Per ulteriori informazioni sulla conformità di System Center Configuration Manager, vedere [Introduction to Compliance Settings in System center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="fe65c-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="fe65c-140">Altre impostazioni di configurazione consigliate</span><span class="sxs-lookup"><span data-stu-id="fe65c-140">Other recommended configuration settings</span></span>
<span data-ttu-id="fe65c-141">Dopo aver eseguito il servizio di onboarding per i dispositivi, è importante sfruttare le funzionalità di protezione delle minacce incluse, consentendo loro di utilizzare le seguenti impostazioni di configurazione consigliate.</span><span class="sxs-lookup"><span data-stu-id="fe65c-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="fe65c-142">Configurazione raccolta dispositivi</span><span class="sxs-lookup"><span data-stu-id="fe65c-142">Device collection configuration</span></span>
<span data-ttu-id="fe65c-143">Se si utilizza endpoint Configuration Manager, versione 2002 o successiva, è possibile scegliere di ampliare la distribuzione per includere server o client di livello più basso.</span><span class="sxs-lookup"><span data-stu-id="fe65c-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="fe65c-144">Configurazione di protezione di prossima generazione</span><span class="sxs-lookup"><span data-stu-id="fe65c-144">Next generation protection configuration</span></span>

<span data-ttu-id="fe65c-145">Sono consigliate le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe65c-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="fe65c-146">**Analisi**</span><span class="sxs-lookup"><span data-stu-id="fe65c-146">**Scan**</span></span>

- <span data-ttu-id="fe65c-147">Analizzare i dispositivi di archiviazione rimovibili come unità USB: Sì</span><span class="sxs-lookup"><span data-stu-id="fe65c-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="fe65c-148">**Protezione in tempo reale**</span><span class="sxs-lookup"><span data-stu-id="fe65c-148">**Real-time Protection**</span></span>

- <span data-ttu-id="fe65c-149">Abilitare il monitoraggio comportamentale: Sì</span><span class="sxs-lookup"><span data-stu-id="fe65c-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="fe65c-150">Abilitare la protezione da applicazioni potenzialmente indesiderate al download e prima dell'installazione: Sì</span><span class="sxs-lookup"><span data-stu-id="fe65c-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="fe65c-151">**Servizio di protezione cloud**</span><span class="sxs-lookup"><span data-stu-id="fe65c-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="fe65c-152">Tipo di appartenenza del servizio protezione cloud: appartenenza avanzata</span><span class="sxs-lookup"><span data-stu-id="fe65c-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="fe65c-153">**Riduzione della superficie di attacco** Configurare tutte le regole disponibili da controllare.</span><span class="sxs-lookup"><span data-stu-id="fe65c-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="fe65c-154">Il blocco di queste attività può interrompere i processi aziendali legittimi.</span><span class="sxs-lookup"><span data-stu-id="fe65c-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="fe65c-155">L'approccio migliore consiste nell'impostare tutto per il controllo, identificare quelli che possono essere attivati e quindi abilitare tali impostazioni sugli endpoint che non dispongono di rilevamenti falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="fe65c-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="fe65c-156">**Protezione di rete**</span><span class="sxs-lookup"><span data-stu-id="fe65c-156">**Network protection**</span></span>

<span data-ttu-id="fe65c-157">Prima di abilitare la protezione di rete in modalità di controllo o di blocco, verificare di aver installato l'aggiornamento della piattaforma antimalware, che può essere ottenuto dalla [pagina di supporto](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span><span class="sxs-lookup"><span data-stu-id="fe65c-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="fe65c-158">**Accesso alla cartella controllata**</span><span class="sxs-lookup"><span data-stu-id="fe65c-158">**Controlled folder access**</span></span>

<span data-ttu-id="fe65c-159">Abilitare la funzionalità in modalità di controllo per almeno 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="fe65c-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="fe65c-160">Dopo questo periodo, esaminare i rilevamenti e creare un elenco di applicazioni che possono essere scritte in directory protette.</span><span class="sxs-lookup"><span data-stu-id="fe65c-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="fe65c-161">Per ulteriori informazioni, vedere [valutare l'accesso alla cartella controllata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span><span class="sxs-lookup"><span data-stu-id="fe65c-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="fe65c-162">Dispositivi di trasferisce tramite Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fe65c-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="fe65c-163">Per motivi di sicurezza, il pacchetto utilizzato per i dispositivi di trasferisce scadrà 30 giorni dopo la data in cui è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="fe65c-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="fe65c-164">I pacchetti di Offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="fe65c-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="fe65c-165">Quando si scarica un pacchetto di Offboarding, viene inviata una notifica alla data di scadenza dei pacchetti e verrà incluso anche il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fe65c-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="fe65c-166">I criteri di onboarding e offboarding non devono essere distribuiti contemporaneamente nello stesso dispositivo, altrimenti ciò provocherà collisioni imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="fe65c-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="fe65c-167">Dispositivi di trasferisce che utilizzano la filiale corrente di Microsoft endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fe65c-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="fe65c-168">Se si utilizza la succursale corrente di Microsoft endpoint Configuration Manager, vedere [creare un file di configurazione di Offboarding](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span><span class="sxs-lookup"><span data-stu-id="fe65c-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="fe65c-169">Dispositivi di trasferisce che utilizzano System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fe65c-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="fe65c-170">Ottenere il pacchetto offboarding dal [centro conformità Microsoft](https://compliance.microsoft.com/):</span><span class="sxs-lookup"><span data-stu-id="fe65c-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="fe65c-171">Nel riquadro di spostamento, selezionare **Impostazioni**  >   **onboarding del dispositivo** >  **offboarding** .</span><span class="sxs-lookup"><span data-stu-id="fe65c-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding** .</span></span>

3. <span data-ttu-id="fe65c-172">Selezionare Windows 10 come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fe65c-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="fe65c-173">Nel campo **metodo di distribuzione** selezionare **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span><span class="sxs-lookup"><span data-stu-id="fe65c-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
    
5. <span data-ttu-id="fe65c-174">Selezionare **Download package** e salvare il file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="fe65c-174">Select **Download package** , and save the .zip file.</span></span>

6. <span data-ttu-id="fe65c-175">Estrarre il contenuto del file con estensione zip in una posizione condivisa e di sola lettura a cui è possibile accedere gli amministratori di rete che distribuiscono il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fe65c-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="fe65c-176">È necessario disporre di un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="fe65c-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

7. <span data-ttu-id="fe65c-177">Distribuire il pacchetto attenendosi alla procedura descritta nell'articolo [packages and programmes in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .</span><span class="sxs-lookup"><span data-stu-id="fe65c-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="fe65c-178">Scegliere un insieme di dispositivi predefinito per la distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fe65c-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe65c-179">Offboarding fa in modo che il dispositivo smetta di inviare i dati del sensore al portale, ma i dati del dispositivo, incluso il riferimento agli avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="fe65c-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="fe65c-180">Monitorare la configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fe65c-180">Monitor device configuration</span></span>

<span data-ttu-id="fe65c-181">Se si utilizza la succursale corrente di Microsoft endpoint Configuration Manager, utilizzare il Dashboard Microsoft Defender ATP incorporato nella console di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="fe65c-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="fe65c-182">Per ulteriori informazioni, vedere [Microsoft Defender Advanced Threat Protection-monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span><span class="sxs-lookup"><span data-stu-id="fe65c-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="fe65c-183">Se si utilizza System Center 2012 R2 Configuration Manager, il monitoraggio è costituito da due parti:</span><span class="sxs-lookup"><span data-stu-id="fe65c-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="fe65c-184">La conferma del pacchetto di configurazione è stata distribuita correttamente ed è in esecuzione (o è stata eseguita correttamente) sui dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="fe65c-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="fe65c-185">Verifica che i dispositivi siano compatibili con il servizio di prevenzione della perdita di dati di Microsoft 365 endpoint (questo garantisce che il dispositivo possa completare il processo di onboarding e possa continuare a segnalare i dati al servizio).</span><span class="sxs-lookup"><span data-stu-id="fe65c-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="fe65c-186">Confermare che il pacchetto di configurazione è stato distribuito correttamente</span><span class="sxs-lookup"><span data-stu-id="fe65c-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="fe65c-187">Nella console di Configuration Manager, fare clic su **monitoraggio** nella parte inferiore del riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="fe65c-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="fe65c-188">Selezionare **Panoramica** e quindi **distribuzioni** .</span><span class="sxs-lookup"><span data-stu-id="fe65c-188">Select **Overview** and then **Deployments** .</span></span>

3. <span data-ttu-id="fe65c-189">Selezionare la distribuzione con il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fe65c-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="fe65c-190">Esaminare gli indicatori di stato in **statistiche di completamento** e stato del **contenuto** .</span><span class="sxs-lookup"><span data-stu-id="fe65c-190">Review the status indicators under **Completion Statistics** and **Content Status** .</span></span>

    <span data-ttu-id="fe65c-191">Se sono presenti distribuzioni non riuscite (dispositivi con **errori** , **requisiti non soddisfatti** o **Stati non riusciti** ), potrebbe essere necessario risolvere i problemi relativi ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fe65c-191">If there are failed deployments (devices with **Error** , **Requirements Not Met** , or **Failed statuses** ), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="fe65c-192">Per ulteriori informazioni, vedere [risolvere i problemi relativi all'onboarding di Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="fe65c-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Configuration Manager che mostra la distribuzione completata senza errori](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="fe65c-194">Verificare che i dispositivi siano compatibili con il servizio di prevenzione della perdita di dati di Microsoft 365 endpoint</span><span class="sxs-lookup"><span data-stu-id="fe65c-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="fe65c-195">È possibile impostare una regola di conformità per l'elemento di configurazione in System Center 2012 R2 Configuration Manager per monitorare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fe65c-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="fe65c-196">Questa procedura e la voce del registro di sistema si applicano all'endpoint DLP e alla protezione avanzata dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="fe65c-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="fe65c-197">Questa regola deve essere un elemento di configurazione di una regola di conformità *non correttivo* che monitora il valore di una chiave del registro di sistema nei dispositivi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fe65c-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="fe65c-198">Monitorare la voce della chiave del registro di sistema seguente:</span><span class="sxs-lookup"><span data-stu-id="fe65c-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="fe65c-199">Per ulteriori informazioni, vedere [Introduzione alle impostazioni di conformità in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="fe65c-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe65c-200">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fe65c-200">Related topics</span></span>
- [<span data-ttu-id="fe65c-201">Dispositivi di bordo di Windows 10 con criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="fe65c-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="fe65c-202">Dispositivi di bordo di Windows 10 con strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="fe65c-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="fe65c-203">Dispositivi di bordo di Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="fe65c-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="fe65c-204">Dispositivi VDI (Virtual Desktop Infrastructure) non permanenti di bordo</span><span class="sxs-lookup"><span data-stu-id="fe65c-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="fe65c-205">Eseguire un test di rilevamento su un dispositivo ATP Microsoft Defender appena integrato</span><span class="sxs-lookup"><span data-stu-id="fe65c-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="fe65c-206">Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fe65c-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
