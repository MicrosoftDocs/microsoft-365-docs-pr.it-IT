---
title: Eseguire l'onboarded dei dispositivi in Microsoft Defender ATP
description: Tieni traccia dell'onboarding dei dispositivi gestiti da Intune in Microsoft Defender ATP e aumenta la frequenza di onboarding.
keywords: onboard, gestione intune, MDATP, WDATP, Microsoft Defender, Windows Defender, protezione avanzata dalle minacce, gestione della configurazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6145acd5e8e2743ff42dce3cf01af0128e8ca225
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166090"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="9039d-104">Eseguire l'onboarded dei dispositivi in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="9039d-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9039d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9039d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9039d-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="9039d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9039d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9039d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9039d-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9039d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9039d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9039d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="9039d-110">Ogni dispositivo onboarded aggiunge un sensore edR (Endpoint Detection and Response) aggiuntivo e aumenta la visibilità sull'attività di violazione nella rete.</span><span class="sxs-lookup"><span data-stu-id="9039d-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="9039d-111">L'onboarding garantisce inoltre che un dispositivo possa essere controllato alla ricerca di componenti vulnerabili e problemi di configurazione della sicurezza e possa ricevere azioni di correzione critiche durante gli attacchi.</span><span class="sxs-lookup"><span data-stu-id="9039d-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="9039d-112">Prima di poter tenere traccia e gestire l'onboarding dei dispositivi:</span><span class="sxs-lookup"><span data-stu-id="9039d-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="9039d-113">Registrare i dispositivi nella gestione di Intune</span><span class="sxs-lookup"><span data-stu-id="9039d-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="9039d-114">Verificare di disporre delle autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="9039d-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="9039d-115">Individuare e tenere traccia dei dispositivi non protetti</span><span class="sxs-lookup"><span data-stu-id="9039d-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="9039d-116">La scheda **di onboarding** offre una panoramica generale della frequenza di onboarding confrontando il numero di dispositivi Windows 10 effettivamente onboarding in Defender per Endpoint con il numero totale di dispositivi Windows 10 gestiti da Intune.</span><span class="sxs-lookup"><span data-stu-id="9039d-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="9039d-117">![Scheda di onboarding per la gestione della configurazione dei dispositivi](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="9039d-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="9039d-118">*Scheda che mostra i dispositivi onboarded rispetto al numero totale di dispositivi Windows 10 gestiti da Intune*</span><span class="sxs-lookup"><span data-stu-id="9039d-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="9039d-119">Se hai usato Gestione configurazione Centro sicurezza, lo script di onboarding o altri metodi di onboarding che non usano profili intune, potresti riscontrare discrepanze di dati.</span><span class="sxs-lookup"><span data-stu-id="9039d-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="9039d-120">Per risolvere queste discrepanze, crea un profilo di configurazione intune corrispondente per Defender per l'onboarding dell'endpoint e assegna il profilo ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9039d-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="9039d-121">Onboardare più dispositivi con profili intune</span><span class="sxs-lookup"><span data-stu-id="9039d-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="9039d-122">Defender for Endpoint offre diverse opzioni convenienti per [l'onboarding di dispositivi Windows 10.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="9039d-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="9039d-123">Per i dispositivi gestiti da Intune, tuttavia, puoi sfruttare i profili di Intune per distribuire comodamente il sensore Defender for Endpoint per selezionare i dispositivi, in modo efficace l'onboarding di questi dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="9039d-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="9039d-124">Nella scheda **Onboarding** seleziona **Onboarding di altri** dispositivi per creare e assegnare un profilo in Intune.</span><span class="sxs-lookup"><span data-stu-id="9039d-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="9039d-125">Il collegamento consente di accedere alla pagina di conformità del dispositivo in Intune, che fornisce una panoramica simile dello stato di onboarding.</span><span class="sxs-lookup"><span data-stu-id="9039d-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="9039d-126">![Pagina conformità dei dispositivi Microsoft Defender ATP nella gestione dei dispositivi di Intune](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="9039d-126">![Microsoft Defender ATP device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="9039d-127">*Pagina conformità dei dispositivi Microsoft Defender ATP nella gestione dei dispositivi di Intune*</span><span class="sxs-lookup"><span data-stu-id="9039d-127">*Microsoft Defender ATP device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="9039d-128">In alternativa, è possibile passare alla pagina Conformità onboarding di Defender for Endpoint nel portale di [Microsoft Azure](https://portal.azure.com/) da Tutti i servizi > Intune > Conformità dei dispositivi **> Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="9039d-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="9039d-129">Se vuoi visualizzare i dati del dispositivo più aggiornati, fai clic su Elenco di dispositivi senza sensore **ATP.**</span><span class="sxs-lookup"><span data-stu-id="9039d-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="9039d-130">Dalla pagina conformità del dispositivo, crea un profilo di configurazione specifico per la distribuzione del sensore Defender for Endpoint e assegna il profilo ai dispositivi che vuoi eseguire l'onboard.</span><span class="sxs-lookup"><span data-stu-id="9039d-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="9039d-131">A tale scopo, è possibile:</span><span class="sxs-lookup"><span data-stu-id="9039d-131">To do this, you can either:</span></span>

- <span data-ttu-id="9039d-132">Seleziona Crea un profilo di configurazione del dispositivo per configurare il sensore **ATP** in modo che inizi con un profilo di configurazione del dispositivo predefinito.</span><span class="sxs-lookup"><span data-stu-id="9039d-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="9039d-133">Crea il profilo di configurazione del dispositivo da zero.</span><span class="sxs-lookup"><span data-stu-id="9039d-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="9039d-134">Per altre informazioni, leggi l'uso dei profili di configurazione dei dispositivi [intune per eseguire l'onboardmento dei dispositivi in Defender per Endpoint.](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="9039d-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="9039d-135">Vuoi provare Microsoft Defender ATP?</span><span class="sxs-lookup"><span data-stu-id="9039d-135">Want to experience Microsoft Defender ATP?</span></span> [<span data-ttu-id="9039d-136">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9039d-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="9039d-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9039d-137">Related topics</span></span>
- [<span data-ttu-id="9039d-138">Verificare che i dispositivi siano configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="9039d-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="9039d-139">Aumentare la conformità alla linea di base di sicurezza di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9039d-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="9039d-140">Ottimizzare la distribuzione e i rilevamenti delle regole asr</span><span class="sxs-lookup"><span data-stu-id="9039d-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
