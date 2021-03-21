---
title: Onboarding di dispositivi Windows 10 con Configuration Manager
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
description: Usa Configuration Manager per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded nel servizio.
ms.openlocfilehash: a84222d7654c6fb9ccab4275273e9e9c2c189790
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918002"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="cc622-103">Onboarding di dispositivi Windows 10 con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cc622-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="cc622-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cc622-104">**Applies to:**</span></span>

- [<span data-ttu-id="cc622-105">Prevenzione della perdita dei dati di Microsoft 365 Endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="cc622-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="cc622-106">System Center Configuration Manager 2012 R2</span><span class="sxs-lookup"><span data-stu-id="cc622-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="cc622-107">Onboardare i dispositivi con System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cc622-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="cc622-108">Aprire il file ZIP del pacchetto di configurazione di Configuration Manager (*DeviceComplianceOnboardingPackage.zip*) scaricato dall'onboarding guidato del servizio.</span><span class="sxs-lookup"><span data-stu-id="cc622-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="cc622-109">È anche possibile ottenere il pacchetto dal [Centro conformità Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="cc622-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="cc622-110">Nel riquadro di spostamento seleziona **Impostazioni**  >  **Onboarding dispositivo Onboarding.**  >  </span><span class="sxs-lookup"><span data-stu-id="cc622-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="cc622-111">Nel campo **Metodo di** distribuzione selezionare Microsoft Endpoint Configuration **Manager 2012/2012 R2/1511/1602.**</span><span class="sxs-lookup"><span data-stu-id="cc622-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
 
4. <span data-ttu-id="cc622-112">Seleziona **Scarica pacchetto** e salva il file ZIP.</span><span class="sxs-lookup"><span data-stu-id="cc622-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="cc622-113">Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dagli amministratori di rete che distribuiranno il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cc622-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="cc622-114">Dovresti avere un file denominato *DeviceComplianceOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="cc622-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="cc622-115">Distribuire il pacchetto seguendo la procedura descritta nell'articolo Pacchetti e programmi [in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cc622-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="cc622-116">Scegli una raccolta di dispositivi predefinita in cui distribuire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cc622-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="cc622-117">La prevenzione della perdita dei dati degli endpoint di Microsoft 365 non supporta l'onboarding durante la fase [out-of-box experience (OOBE).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)</span><span class="sxs-lookup"><span data-stu-id="cc622-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="cc622-118">Assicurarsi che gli utenti completino la Configurazione guidata dopo l'esecuzione dell'installazione o dell'aggiornamento di Windows.</span><span class="sxs-lookup"><span data-stu-id="cc622-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="cc622-119">Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che un dispositivo sia stato correttamente onboarding nel servizio.</span><span class="sxs-lookup"><span data-stu-id="cc622-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="cc622-120">Per altre informazioni, vedi [Eseguire un test di rilevamento su un dispositivo Microsoft Defender ATP appena onboarded.](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)</span><span class="sxs-lookup"><span data-stu-id="cc622-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="cc622-121">Tieni presente che è possibile creare una regola di rilevamento in un'applicazione di Configuration Manager per verificare continuamente se è stato eseguito l'onboarded di un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc622-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="cc622-122">Un'applicazione è un tipo di oggetto diverso rispetto a un pacchetto e a un programma.</span><span class="sxs-lookup"><span data-stu-id="cc622-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="cc622-123">Se un dispositivo non è ancora stato onboarded (a causa del completamento della Configurazione guidata in sospeso o di qualsiasi altro motivo), Configuration Manager ritenterà di eseguire l'onboarded del dispositivo fino a quando la regola non rileva la modifica dello stato.</span><span class="sxs-lookup"><span data-stu-id="cc622-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="cc622-124">Questo comportamento può essere ottenuto creando una regola di rilevamento che controlla se il valore del Registro di sistema "OnboardingState" (di tipo REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="cc622-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="cc622-125">Questo valore del Registro di sistema si trova in "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="cc622-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="cc622-126">Per ulteriori informazioni, vedere [Configure Detection Methods in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="cc622-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="cc622-127">Configurare le impostazioni della raccolta di esempio</span><span class="sxs-lookup"><span data-stu-id="cc622-127">Configure sample collection settings</span></span>

<span data-ttu-id="cc622-128">Per ogni dispositivo, puoi impostare un valore di configurazione per indicare se è possibile raccogliere campioni dal dispositivo quando viene effettuata una richiesta tramite Microsoft Defender Security Center per inviare un file per l'analisi approfondita.</span><span class="sxs-lookup"><span data-stu-id="cc622-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="cc622-129">Queste impostazioni di configurazione vengono in genere eseguite tramite Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cc622-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="cc622-130">Puoi impostare una regola di conformità per l'elemento di configurazione in Configuration Manager per modificare l'impostazione della condivisione di esempio in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc622-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="cc622-131">Questa regola deve essere un elemento *di configurazione* della regola di conformità che imposta il valore di una chiave del Registro di sistema nei dispositivi di destinazione per assicurarsi che siano reclami.</span><span class="sxs-lookup"><span data-stu-id="cc622-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="cc622-132">La configurazione viene impostata tramite la voce della chiave del Registro di sistema seguente:</span><span class="sxs-lookup"><span data-stu-id="cc622-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="cc622-133">Dove:</span><span class="sxs-lookup"><span data-stu-id="cc622-133">Where:</span></span><br>
<span data-ttu-id="cc622-134">Il tipo di chiave è D-WORD.</span><span class="sxs-lookup"><span data-stu-id="cc622-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="cc622-135">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="cc622-135">Possible values are:</span></span>
- <span data-ttu-id="cc622-136">0 - Non consente la condivisione di esempi da questo dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc622-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="cc622-137">1 - Consente la condivisione di tutti i tipi di file da questo dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc622-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="cc622-138">Il valore predefinito nel caso in cui la chiave del Registro di sistema non esista è 1.</span><span class="sxs-lookup"><span data-stu-id="cc622-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="cc622-139">Per ulteriori informazioni sulla conformità di System Center Configuration Manager, vedere Introduzione alle impostazioni di [conformità in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cc622-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="cc622-140">Altre impostazioni di configurazione consigliate</span><span class="sxs-lookup"><span data-stu-id="cc622-140">Other recommended configuration settings</span></span>
<span data-ttu-id="cc622-141">Dopo l'onboarding dei dispositivi al servizio, è importante sfruttare le funzionalità di protezione dalle minacce incluse abilitandoli con le impostazioni di configurazione consigliate seguenti.</span><span class="sxs-lookup"><span data-stu-id="cc622-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="cc622-142">Configurazione raccolta dispositivi</span><span class="sxs-lookup"><span data-stu-id="cc622-142">Device collection configuration</span></span>
<span data-ttu-id="cc622-143">Se si usa Endpoint Configuration Manager, versione 2002 o successiva, è possibile scegliere di ampliare la distribuzione per includere server o client di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="cc622-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="cc622-144">Configurazione di protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="cc622-144">Next generation protection configuration</span></span>

<span data-ttu-id="cc622-145">Sono consigliate le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc622-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="cc622-146">**Analisi**</span><span class="sxs-lookup"><span data-stu-id="cc622-146">**Scan**</span></span>

- <span data-ttu-id="cc622-147">Analizzare i dispositivi di archiviazione rimovibili, ad esempio le unità USB: Sì</span><span class="sxs-lookup"><span data-stu-id="cc622-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="cc622-148">**Protezione in tempo reale**</span><span class="sxs-lookup"><span data-stu-id="cc622-148">**Real-time Protection**</span></span>

- <span data-ttu-id="cc622-149">Abilita monitoraggio comportamentale: Sì</span><span class="sxs-lookup"><span data-stu-id="cc622-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="cc622-150">Abilitare la protezione da applicazioni potenzialmente indesiderate durante il download e prima dell'installazione: Sì</span><span class="sxs-lookup"><span data-stu-id="cc622-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="cc622-151">**Servizio di protezione cloud**</span><span class="sxs-lookup"><span data-stu-id="cc622-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="cc622-152">Tipo di appartenenza al servizio di protezione cloud: appartenenza avanzata</span><span class="sxs-lookup"><span data-stu-id="cc622-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="cc622-153">**Riduzione della superficie di attacco** Configurare tutte le regole disponibili su Controllo.</span><span class="sxs-lookup"><span data-stu-id="cc622-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="cc622-154">Il blocco di queste attività può interrompere i processi aziendali legittimi.</span><span class="sxs-lookup"><span data-stu-id="cc622-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="cc622-155">L'approccio migliore consiste nell'impostare tutti i controlli, identificare quelli sicuri da attivare e quindi abilitare tali impostazioni sugli endpoint che non dispongono di rilevamenti falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="cc622-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="cc622-156">**Protezione di rete**</span><span class="sxs-lookup"><span data-stu-id="cc622-156">**Network protection**</span></span>

<span data-ttu-id="cc622-157">Prima di abilitare la protezione di rete in modalità di controllo o blocco, assicurati di aver installato l'aggiornamento della piattaforma antimalware, che può essere ottenuto dalla [pagina di supporto](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span><span class="sxs-lookup"><span data-stu-id="cc622-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="cc622-158">**Accesso controllato alle cartelle**</span><span class="sxs-lookup"><span data-stu-id="cc622-158">**Controlled folder access**</span></span>

<span data-ttu-id="cc622-159">Abilita la funzionalità in modalità di controllo per almeno 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="cc622-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="cc622-160">Dopo questo periodo, esaminare i rilevamenti e creare un elenco di applicazioni che possono scrivere nelle directory protette.</span><span class="sxs-lookup"><span data-stu-id="cc622-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="cc622-161">Per ulteriori informazioni, vedere [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span><span class="sxs-lookup"><span data-stu-id="cc622-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="cc622-162">Dispositivi offboard con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cc622-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="cc622-163">Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download.</span><span class="sxs-lookup"><span data-stu-id="cc622-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="cc622-164">I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="cc622-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="cc622-165">Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cc622-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="cc622-166">I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="cc622-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="cc622-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span><span class="sxs-lookup"><span data-stu-id="cc622-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="cc622-168">Se usi il ramo corrente di Microsoft Endpoint Configuration Manager, vedi Creare un file di [configurazione di offboarding.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="cc622-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="cc622-169">Dispositivi offboard con System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cc622-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="cc622-170">Ottenere il pacchetto di offboarding dal [Centro conformità Microsoft:](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="cc622-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="cc622-171">Nel riquadro di spostamento seleziona **Impostazioni**  >   **Onboarding del dispositivo Offboarding.** >  </span><span class="sxs-lookup"><span data-stu-id="cc622-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="cc622-172">Seleziona Windows 10 come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cc622-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="cc622-173">Nel campo **Metodo di** distribuzione selezionare Microsoft Endpoint Configuration **Manager 2012/2012 R2/1511/1602.**</span><span class="sxs-lookup"><span data-stu-id="cc622-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
5. <span data-ttu-id="cc622-174">Seleziona **Scarica pacchetto** e salva il file ZIP.</span><span class="sxs-lookup"><span data-stu-id="cc622-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="cc622-175">Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dagli amministratori di rete che distribuiranno il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cc622-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="cc622-176">Dovresti avere un file denominato *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="cc622-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="cc622-177">Distribuire il pacchetto seguendo la procedura descritta nell'articolo Pacchetti e programmi [in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cc622-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="cc622-178">Scegli una raccolta di dispositivi predefinita in cui distribuire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cc622-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc622-179">L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="cc622-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="cc622-180">Monitorare la configurazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc622-180">Monitor device configuration</span></span>

<span data-ttu-id="cc622-181">Se usi il ramo corrente di Microsoft Endpoint Configuration Manager, usa il dashboard predefinito di Microsoft Defender ATP nella console di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cc622-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="cc622-182">Per ulteriori informazioni, vedere [Microsoft Defender Advanced Threat Protection - Monitor.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="cc622-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="cc622-183">Se si usa System Center 2012 R2 Configuration Manager, il monitoraggio è costituito da due parti:</span><span class="sxs-lookup"><span data-stu-id="cc622-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="cc622-184">Verificare che il pacchetto di configurazione sia stato distribuito correttamente e che sia in esecuzione (o sia stato eseguito correttamente) nei dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="cc622-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="cc622-185">Verifica che i dispositivi siano conformi al servizio di prevenzione della perdita dei dati di Microsoft 365 Endpoint (in questo modo il dispositivo può completare il processo di onboarding e può continuare a segnalare i dati al servizio).</span><span class="sxs-lookup"><span data-stu-id="cc622-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="cc622-186">Verificare che il pacchetto di configurazione sia stato distribuito correttamente</span><span class="sxs-lookup"><span data-stu-id="cc622-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="cc622-187">Nella console di Configuration Manager fare clic **su Monitoraggio** nella parte inferiore del riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="cc622-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="cc622-188">Selezionare **Panoramica** e **quindi Distribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="cc622-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="cc622-189">Selezionare nella distribuzione con il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cc622-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="cc622-190">Esaminare gli indicatori di stato in **Statistiche di completamento** e Stato **contenuto**.</span><span class="sxs-lookup"><span data-stu-id="cc622-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="cc622-191">Se sono presenti distribuzioni non riuscite (dispositivi con stato **Errore,** Requisiti **non** soddisfatti o Non **riusciti),** potrebbe essere necessario risolvere i problemi relativi ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="cc622-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="cc622-192">Per ulteriori informazioni, vedere Risoluzione dei problemi [di onboarding](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)di Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="cc622-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Configuration Manager che mostra la corretta distribuzione senza errori](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="cc622-194">Verificare che i dispositivi siano conformi al servizio di prevenzione della perdita dei dati di Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="cc622-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="cc622-195">È possibile impostare una regola di conformità per l'elemento di configurazione in System Center 2012 R2 Configuration Manager per monitorare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cc622-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="cc622-196">Questa procedura e voce del Registro di sistema si applica a Endpoint DLP e Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="cc622-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="cc622-197">Questa regola deve essere un elemento di configurazione della regola di conformità *non correttiva* che monitori il valore di una chiave del Registro di sistema nei dispositivi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cc622-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="cc622-198">Monitorare la seguente voce della chiave del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="cc622-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="cc622-199">Per ulteriori informazioni, vedere [Introduzione alle impostazioni di conformità in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cc622-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc622-200">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cc622-200">Related topics</span></span>
- [<span data-ttu-id="cc622-201">Onboardare dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="cc622-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="cc622-202">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="cc622-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="cc622-203">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="cc622-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="cc622-204">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="cc622-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="cc622-205">Eseguire un test di rilevamento su un dispositivo Microsoft Defender ATP appena onboarded</span><span class="sxs-lookup"><span data-stu-id="cc622-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="cc622-206">Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cc622-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)