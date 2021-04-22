---
title: Aumentare la conformità alla linea di base di sicurezza di Microsoft Defender for Endpoint
description: La linea di base per la sicurezza di Microsoft Defender per endpoint imposta i controlli di sicurezza per garantire una protezione ottimale.
keywords: Gestione di Intune, Microsoft Defender for Endpoint, Microsoft Defender, Microsoft Defender for Endpoint ASR, baseline di sicurezza
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
ms.openlocfilehash: fbdc0d02d4c5ba5cfda9773e62082217ba4f8c4e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933602"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="db5e5-104">Aumentare la conformità alla linea di base di sicurezza di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db5e5-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db5e5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="db5e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="db5e5-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="db5e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db5e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db5e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="db5e5-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="db5e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="db5e5-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="db5e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="db5e5-110">Le linee di base della sicurezza assicurano che le funzionalità di sicurezza siano configurate in base alle indicazioni degli esperti di sicurezza e degli amministratori di sistema di Windows esperti.</span><span class="sxs-lookup"><span data-stu-id="db5e5-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="db5e5-111">Quando viene distribuita, la linea di base di defender per la sicurezza degli endpoint imposta Defender per i controlli di sicurezza degli endpoint in modo da garantire una protezione ottimale.</span><span class="sxs-lookup"><span data-stu-id="db5e5-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="db5e5-112">Per comprendere le linee di base della sicurezza e come vengono assegnate in Intune usando i profili di configurazione, [leggere queste domande frequenti](https://docs.microsoft.com/intune/security-baselines#q--a).</span><span class="sxs-lookup"><span data-stu-id="db5e5-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="db5e5-113">Prima di poter distribuire e tenere traccia della conformità alle linee di base della sicurezza:</span><span class="sxs-lookup"><span data-stu-id="db5e5-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="db5e5-114">Registrare i dispositivi nella gestione di Intune</span><span class="sxs-lookup"><span data-stu-id="db5e5-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="db5e5-115">Verificare di disporre delle autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="db5e5-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="db5e5-116">Confronto tra Microsoft Defender per Endpoint e le linee di base della sicurezza di Windows Intune</span><span class="sxs-lookup"><span data-stu-id="db5e5-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="db5e5-117">La linea di base per la sicurezza di Windows Intune fornisce un set completo di impostazioni consigliate necessarie per configurare in modo sicuro i dispositivi che eseguono Windows, incluse le impostazioni del browser, le impostazioni di PowerShell, nonché le impostazioni per alcune funzionalità di sicurezza come Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="db5e5-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="db5e5-118">Al contrario, la linea di base di Defender for Endpoint fornisce impostazioni che ottimizzano tutti i controlli di sicurezza nello stack defender per endpoint, incluse le impostazioni per il rilevamento e la risposta degli endpoint (EDR) e le impostazioni disponibili anche nella linea di base di sicurezza di Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="db5e5-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="db5e5-119">Per ulteriori informazioni su ogni previsione, vedere:</span><span class="sxs-lookup"><span data-stu-id="db5e5-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="db5e5-120">Impostazioni di base della sicurezza di Windows per Intune</span><span class="sxs-lookup"><span data-stu-id="db5e5-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="db5e5-121">Impostazioni di base di Microsoft Defender for Endpoint per Intune</span><span class="sxs-lookup"><span data-stu-id="db5e5-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="db5e5-122">Idealmente, i dispositivi onboarded in Defender for Endpoint vengono distribuiti entrambe le linee di base: la linea di base di sicurezza di Windows Intune per proteggere inizialmente Windows e quindi la linea di base di sicurezza di Defender for Endpoint su più livelli per configurare in modo ottimale i controlli di sicurezza defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="db5e5-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="db5e5-123">Per trarre vantaggio dai dati più recenti su rischi e minacce e per ridurre al minimo i conflitti con l'evolversi delle linee di base, applicare sempre le versioni più recenti delle linee di base in tutti i prodotti non appena vengono rilasciati.</span><span class="sxs-lookup"><span data-stu-id="db5e5-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="db5e5-124">La baseline di sicurezza di Defender for Endpoint è stata ottimizzata per i dispositivi fisici e attualmente non è consigliata per l'uso in macchine virtuali (VM) o endpoint VDI.</span><span class="sxs-lookup"><span data-stu-id="db5e5-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="db5e5-125">Alcune impostazioni di base possono influire sulle sessioni interattive remote in ambienti virtualizzati.</span><span class="sxs-lookup"><span data-stu-id="db5e5-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="db5e5-126">Monitorare la conformità alla baseline di sicurezza di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db5e5-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="db5e5-127">La **scheda di base** Sicurezza nella gestione [della](configure-machines.md) configurazione dei dispositivi fornisce una panoramica della conformità nei dispositivi Windows 10 a cui è stata assegnata la linea di base di sicurezza defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="db5e5-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="db5e5-128">![Scheda di base sicurezza](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="db5e5-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="db5e5-129">*Scheda che mostra la conformità alla linea di base di sicurezza di Defender for Endpoint*</span><span class="sxs-lookup"><span data-stu-id="db5e5-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="db5e5-130">A ogni dispositivo viene assegnato uno dei seguenti tipi di stato:</span><span class="sxs-lookup"><span data-stu-id="db5e5-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="db5e5-131">**Corrisponde alla linea di** base: le impostazioni del dispositivo corrispondono a tutte le impostazioni della linea di base</span><span class="sxs-lookup"><span data-stu-id="db5e5-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="db5e5-132">**Non corrisponde alla linea di base:** almeno un'impostazione del dispositivo non corrisponde alla linea di base</span><span class="sxs-lookup"><span data-stu-id="db5e5-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="db5e5-133">**Configurazione non corretta:** almeno un'impostazione di base non è configurata correttamente nel dispositivo ed è in conflitto, errore o stato in sospeso</span><span class="sxs-lookup"><span data-stu-id="db5e5-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="db5e5-134">**Non applicabile:** almeno un'impostazione di base non è applicabile nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="db5e5-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="db5e5-135">Per esaminare dispositivi specifici, selezionare **Configura baseline di sicurezza** nella scheda.</span><span class="sxs-lookup"><span data-stu-id="db5e5-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="db5e5-136">Questo consente di accedere alla gestione dei dispositivi di Intune.</span><span class="sxs-lookup"><span data-stu-id="db5e5-136">This takes you to Intune device management.</span></span> <span data-ttu-id="db5e5-137">Da qui, seleziona **Stato del** dispositivo per i nomi e gli stati dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="db5e5-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="db5e5-138">Potrebbero verificarsi discrepanze nei dati aggregati visualizzati nella pagina di gestione della configurazione del dispositivo e in quelli visualizzati nelle schermate di panoramica in Intune.</span><span class="sxs-lookup"><span data-stu-id="db5e5-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="db5e5-139">Esaminare e assegnare microsoft Defender for Endpoint security baseline</span><span class="sxs-lookup"><span data-stu-id="db5e5-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="db5e5-140">La gestione della configurazione dei dispositivi monitora la conformità di base solo dei dispositivi Windows 10 a cui è stata assegnata in modo specifico la baseline di sicurezza di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="db5e5-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="db5e5-141">Puoi esaminare comodamente la linea di base e assegnarla ai dispositivi nella gestione dei dispositivi di Intune.</span><span class="sxs-lookup"><span data-stu-id="db5e5-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="db5e5-142">Seleziona **Configure security baseline** nella scheda Security **baseline** per passare a Intune device management.</span><span class="sxs-lookup"><span data-stu-id="db5e5-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="db5e5-143">Viene visualizzata una panoramica simile della conformità di base.</span><span class="sxs-lookup"><span data-stu-id="db5e5-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="db5e5-144">In alternativa, è possibile passare a Defender for Endpoint security baseline nel portale di Microsoft Azure da **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span><span class="sxs-lookup"><span data-stu-id="db5e5-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="db5e5-145">Creare un nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="db5e5-145">Create a new profile.</span></span>

   <span data-ttu-id="db5e5-146">![Panoramica di base sulla sicurezza di Microsoft Defender per endpoint in Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="db5e5-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="db5e5-147">*Panoramica di base sulla sicurezza di Microsoft Defender per endpoint in Intune*</span><span class="sxs-lookup"><span data-stu-id="db5e5-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="db5e5-148">Durante la creazione del profilo, è possibile rivedere e modificare impostazioni specifiche sulla linea di base.</span><span class="sxs-lookup"><span data-stu-id="db5e5-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="db5e5-149">![Opzioni di base della sicurezza durante la creazione del profilo in Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="db5e5-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="db5e5-150">*Opzioni di base della sicurezza durante la creazione del profilo in Intune*</span><span class="sxs-lookup"><span data-stu-id="db5e5-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="db5e5-151">Assegnare il profilo al gruppo di dispositivi appropriato.</span><span class="sxs-lookup"><span data-stu-id="db5e5-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="db5e5-152">![Profili di base della sicurezza in Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="db5e5-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="db5e5-153">*Assegnazione del profilo di base della sicurezza in Intune*</span><span class="sxs-lookup"><span data-stu-id="db5e5-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="db5e5-154">Crea il profilo per salvarlo e distribuirlo al gruppo di dispositivi assegnato.</span><span class="sxs-lookup"><span data-stu-id="db5e5-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="db5e5-155">![Assegnazione della linea di base della sicurezza in Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="db5e5-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="db5e5-156">*Creazione del profilo di base della sicurezza in Intune*</span><span class="sxs-lookup"><span data-stu-id="db5e5-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="db5e5-157">Le linee di base della sicurezza in Intune offrono un modo pratico per proteggere e proteggere in modo completo i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="db5e5-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="db5e5-158">[Altre informazioni sulle linee di base della sicurezza in Intune](https://docs.microsoft.com/intune/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="db5e5-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="db5e5-159">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="db5e5-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="db5e5-160">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="db5e5-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="db5e5-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="db5e5-161">Related topics</span></span>
- [<span data-ttu-id="db5e5-162">Verificare che i dispositivi siano configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="db5e5-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="db5e5-163">Eseguire l'onboarded dei dispositivi in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="db5e5-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="db5e5-164">Ottimizzare la distribuzione e i rilevamenti delle regole asr</span><span class="sxs-lookup"><span data-stu-id="db5e5-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
