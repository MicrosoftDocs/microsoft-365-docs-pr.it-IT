---
title: Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
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
description: Usa gli strumenti di gestione dei dispositivi mobili per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded nel servizio.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769480"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="aa53f-103">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="aa53f-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="aa53f-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="aa53f-104">**Applies to:**</span></span>

- [<span data-ttu-id="aa53f-105">Prevenzione della perdita dei dati degli endpoint di Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="aa53f-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="aa53f-106">Puoi usare soluzioni di gestione dei dispositivi mobili (MDM) per configurare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="aa53f-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="aa53f-107">La prevenzione della perdita dei dati degli endpoint di Microsoft 365 supporta gli MPM fornendo OMA-URIs creare criteri per la gestione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="aa53f-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="aa53f-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="aa53f-108">Before you begin</span></span>
<span data-ttu-id="aa53f-109">Se si usa Microsoft Intune, è necessario che il dispositivo MDM sia registrato.</span><span class="sxs-lookup"><span data-stu-id="aa53f-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="aa53f-110">In caso contrario, le impostazioni non verranno applicate correttamente.</span><span class="sxs-lookup"><span data-stu-id="aa53f-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="aa53f-111">Per altre informazioni sull'abilitazione di MDM con Microsoft Intune, vedi [Registrazione dei dispositivi (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="aa53f-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="aa53f-112">Onboard dei dispositivi con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="aa53f-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="aa53f-113">Seguire le istruzioni di [Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="aa53f-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="aa53f-114">Il **criterio Stato integrità per i dispositivi onboarded** usa proprietà di sola lettura e non può essere corretti.</span><span class="sxs-lookup"><span data-stu-id="aa53f-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="aa53f-115">Eseguire l'offboard e monitorare i dispositivi con gli strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="aa53f-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="aa53f-116">Per motivi di sicurezza, il pacchetto usato per l'offboard dei dispositivi scadrà 30 giorni dopo la data di download.</span><span class="sxs-lookup"><span data-stu-id="aa53f-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="aa53f-117">I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="aa53f-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="aa53f-118">Quando scarii un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="aa53f-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="aa53f-119">I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà conflitti imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="aa53f-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="aa53f-120">Ottenere il pacchetto offboarding dal [Centro conformità Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="aa53f-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="aa53f-121">Nel riquadro di spostamento seleziona **Impostazioni**  >  **onboarding del** dispositivo  >  **Offboarding.**</span><span class="sxs-lookup"><span data-stu-id="aa53f-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="aa53f-122">Nel campo **Metodo di distribuzione** selezionare Gestione dispositivi **mobili/ Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="aa53f-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="aa53f-123">Fai **clic su Scarica** pacchetto e salva il file ZIP.</span><span class="sxs-lookup"><span data-stu-id="aa53f-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="aa53f-124">Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dagli amministratori di rete che distribuiranno il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="aa53f-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="aa53f-125">Dovresti avere un file denominato *DeviceCompliance_valid_until_YYYY-MM-D.offboarding.*</span><span class="sxs-lookup"><span data-stu-id="aa53f-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="aa53f-126">Usa i criteri di configurazione personalizzati di Microsoft Intune per distribuire le seguenti impostazioni URI OMA supportate.</span><span class="sxs-lookup"><span data-stu-id="aa53f-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="aa53f-127">URI OMA: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="aa53f-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="aa53f-128">Tipo di data: Stringa</span><span class="sxs-lookup"><span data-stu-id="aa53f-128">Date type: String</span></span>      
      <span data-ttu-id="aa53f-129">Valore: [Copiare e incollare il valore dal contenuto del DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="aa53f-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="aa53f-130">Per altre informazioni sulle impostazioni dei criteri di Microsoft Intune, vedi le impostazioni dei criteri di [Windows 10 in Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="aa53f-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="aa53f-131">Il criterio Stato integrità per i **dispositivi offboarded** usa proprietà di sola lettura e non può essere corretti.</span><span class="sxs-lookup"><span data-stu-id="aa53f-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa53f-132">L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati del dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="aa53f-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aa53f-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="aa53f-133">Related topics</span></span>
- [<span data-ttu-id="aa53f-134">Onboard dei dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="aa53f-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="aa53f-135">Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aa53f-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="aa53f-136">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="aa53f-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="aa53f-137">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="aa53f-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="aa53f-138">Risolvere i problemi di onboarding di Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="aa53f-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
