---
title: Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
description: Usa gli strumenti di gestione dei dispositivi mobili per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded nel servizio.
keywords: onboard dei dispositivi con mdm, gestione dei dispositivi, onboard dei dispositivi Windows ATP, onboard microsoft defender per dispositivi endpoint, mdm
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
ms.technology: mde
ms.openlocfilehash: 85dd6b50280f54b9d39bbb134e466171fc6268ff
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166150"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="75e15-104">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="75e15-104">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="75e15-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="75e15-105">**Applies to:**</span></span>
- [<span data-ttu-id="75e15-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="75e15-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="75e15-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75e15-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="75e15-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="75e15-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="75e15-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="75e15-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="75e15-110">Puoi usare soluzioni di gestione dei dispositivi mobili (MDM) per configurare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="75e15-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="75e15-111">Defender for Endpoint supporta gli MMM fornendo OMA-URIs creare criteri per gestire i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="75e15-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="75e15-112">Per altre informazioni sull'uso di Defender per CSP endpoint, vedi [CSP WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) e [File DDF di WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="75e15-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="75e15-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="75e15-113">Before you begin</span></span>
<span data-ttu-id="75e15-114">Se si usa Microsoft Intune, è necessario che il dispositivo MDM sia registrato.</span><span class="sxs-lookup"><span data-stu-id="75e15-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="75e15-115">In caso contrario, le impostazioni non verranno applicate correttamente.</span><span class="sxs-lookup"><span data-stu-id="75e15-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="75e15-116">Per altre informazioni sull'abilitazione di MDM con Microsoft Intune, vedi [Registrazione dei dispositivi (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="75e15-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="75e15-117">Onboardare i dispositivi con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="75e15-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="75e15-118">[![Immagine del PDF che mostra i dispositivi di onboarding in Defender for Endpoint con Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="75e15-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="75e15-119">Consultare il [PDF o](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) per visualizzare i vari percorsi nella distribuzione di Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="75e15-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="75e15-120">Seguire le istruzioni di [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="75e15-120">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="75e15-121">Per altre informazioni sull'uso di Defender per CSP endpoint, vedi [CSP WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) e [File DDF di WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="75e15-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="75e15-122">Il **criterio Stato integrità per i dispositivi onboarded** usa proprietà di sola lettura e non può essere corretti.</span><span class="sxs-lookup"><span data-stu-id="75e15-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="75e15-123">La configurazione della frequenza di segnalazione dei dati di diagnostica è disponibile solo per i dispositivi in Windows 10 versione 1703.</span><span class="sxs-lookup"><span data-stu-id="75e15-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="75e15-124">Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che un dispositivo sia stato correttamente onboarding nel servizio.</span><span class="sxs-lookup"><span data-stu-id="75e15-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="75e15-125">Per altre informazioni, vedi [Eseguire un test di rilevamento su un dispositivo Microsoft Defender for Endpoint appena onboarded.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="75e15-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="75e15-126">Consultare il [PDF o](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) per visualizzare i vari percorsi nella distribuzione di Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="75e15-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender ATP.</span></span> 

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="75e15-127">Offboard e monitora i dispositivi con gli strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="75e15-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="75e15-128">Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download.</span><span class="sxs-lookup"><span data-stu-id="75e15-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="75e15-129">I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="75e15-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="75e15-130">Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75e15-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="75e15-131">I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="75e15-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="75e15-132">Ottenere il pacchetto di offboarding da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="75e15-132">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

   1. <span data-ttu-id="75e15-133">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Offboarding.**</span><span class="sxs-lookup"><span data-stu-id="75e15-133">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

   1. <span data-ttu-id="75e15-134">Seleziona Windows 10 come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="75e15-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="75e15-135">Nel campo **Metodo di distribuzione** seleziona Gestione dispositivi mobili / Microsoft **Intune.**</span><span class="sxs-lookup"><span data-stu-id="75e15-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="75e15-136">Fai **clic su Scarica** pacchetto e salva il file ZIP.</span><span class="sxs-lookup"><span data-stu-id="75e15-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="75e15-137">Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dagli amministratori di rete che distribuiranno il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="75e15-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="75e15-138">Dovresti avere un file denominato *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="75e15-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="75e15-139">Usa i criteri di configurazione personalizzati di Microsoft Intune per distribuire le seguenti impostazioni URI OMA supportate.</span><span class="sxs-lookup"><span data-stu-id="75e15-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="75e15-140">URI OMA: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="75e15-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="75e15-141">Tipo di data: String</span><span class="sxs-lookup"><span data-stu-id="75e15-141">Date type: String</span></span><br/>
      <span data-ttu-id="75e15-142">Valore: [Copiare e incollare il valore dal contenuto del file WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="75e15-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="75e15-143">Per altre informazioni sulle impostazioni dei criteri di Microsoft Intune, vedi Impostazioni dei criteri [di Windows 10 in Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="75e15-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="75e15-144">Il **criterio Stato integrità per i dispositivi offboarded** usa proprietà di sola lettura e non può essere corretti.</span><span class="sxs-lookup"><span data-stu-id="75e15-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75e15-145">L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="75e15-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="75e15-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="75e15-146">Related topics</span></span>
- [<span data-ttu-id="75e15-147">Onboardare dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="75e15-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="75e15-148">Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="75e15-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="75e15-149">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="75e15-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="75e15-150">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="75e15-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="75e15-151">Eseguire un test di rilevamento in un dispositivo Microsoft Defender for Endpoint appena onboarded</span><span class="sxs-lookup"><span data-stu-id="75e15-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="75e15-152">Risolvere i problemi di onboarding di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="75e15-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
