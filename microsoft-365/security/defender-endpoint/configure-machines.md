---
title: Verificare che i dispositivi siano configurati correttamente
description: Configurare correttamente i dispositivi per aumentare la resilienza generale contro le minacce e migliorare la capacità di rilevare e rispondere agli attacchi.
keywords: onboard, gestione intune, MDATP, WDATP, Microsoft Defender, Windows Defender, protezione avanzata dalle minacce, riduzione della superficie di attacco, ASR, baseline di sicurezza
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7b00ceafc2761f42c316f434a27acf7c551e7cf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163364"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="dff0c-104">Verificare che i dispositivi siano configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="dff0c-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dff0c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="dff0c-105">**Applies to:**</span></span>
- [<span data-ttu-id="dff0c-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="dff0c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dff0c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dff0c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="dff0c-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="dff0c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dff0c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="dff0c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="dff0c-110">Con i dispositivi configurati correttamente, è possibile aumentare la resilienza generale contro le minacce e migliorare la capacità di rilevare e rispondere agli attacchi.</span><span class="sxs-lookup"><span data-stu-id="dff0c-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="dff0c-111">La gestione della configurazione della sicurezza garantisce che i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="dff0c-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="dff0c-112">Onboard to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dff0c-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="dff0c-113">Soddisfare o superare la configurazione di base di Defender for Endpoint security</span><span class="sxs-lookup"><span data-stu-id="dff0c-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="dff0c-114">Disporre di mitigazioni strategiche della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="dff0c-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="dff0c-115">Fai **clic su Gestione** configurazione dal menu di spostamento per aprire la pagina Gestione configurazione dispositivi.</span><span class="sxs-lookup"><span data-stu-id="dff0c-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="dff0c-116">![Pagina Gestione della configurazione della sicurezza](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="dff0c-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="dff0c-117">*Pagina Gestione configurazione dispositivi*</span><span class="sxs-lookup"><span data-stu-id="dff0c-117">*Device configuration management page*</span></span>

<span data-ttu-id="dff0c-118">È possibile tenere traccia dello stato di configurazione a livello di organizzazione e intervenire rapidamente in risposta a una scarsa copertura di onboarding, a problemi di conformità e a mitigazioni della superficie di attacco scarsamente ottimizzate tramite collegamenti diretti e diretti alle pagine di gestione dei dispositivi in Microsoft Intune e nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dff0c-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="dff0c-119">In questo modo, si trarranno vantaggio da:</span><span class="sxs-lookup"><span data-stu-id="dff0c-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="dff0c-120">Visibilità completa degli eventi nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="dff0c-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="dff0c-121">Una solida intelligence sulle minacce e potenti tecnologie di apprendimento dei dispositivi per l'elaborazione di eventi non elaborati e l'identificazione dell'attività di violazione e degli indicatori di minaccia</span><span class="sxs-lookup"><span data-stu-id="dff0c-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="dff0c-122">Una pila completa di funzionalità di sicurezza configurate per arrestare in modo efficiente l'installazione di installazioni dannose, dirottamento di file di sistema e processo, esfiltrazione dei dati e altre attività di minaccia</span><span class="sxs-lookup"><span data-stu-id="dff0c-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="dff0c-123">Mitigazioni ottimizzate della superficie di attacco, massimizzando le difese strategiche contro l'attività delle minacce riducendo al minimo l'impatto sulla produttività</span><span class="sxs-lookup"><span data-stu-id="dff0c-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="dff0c-124">Registrare i dispositivi nella gestione di Intune</span><span class="sxs-lookup"><span data-stu-id="dff0c-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="dff0c-125">La gestione della configurazione dei dispositivi funziona a stretto contatto con la gestione dei dispositivi di Intune per stabilire l'inventario dei dispositivi nell'organizzazione e la configurazione di sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="dff0c-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="dff0c-126">Sarà possibile tenere traccia e gestire i problemi di configurazione nei dispositivi Windows 10 gestiti da Intune.</span><span class="sxs-lookup"><span data-stu-id="dff0c-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="dff0c-127">Prima di poter verificare che i dispositivi siano configurati correttamente, registrarli nella gestione di Intune.</span><span class="sxs-lookup"><span data-stu-id="dff0c-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="dff0c-128">La registrazione di Intune è affidabile e include diverse opzioni di registrazione per i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dff0c-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="dff0c-129">Per altre informazioni sulle opzioni di registrazione di Intune, leggi informazioni sulla [configurazione della registrazione per i dispositivi Windows.](https://docs.microsoft.com/intune/windows-enroll)</span><span class="sxs-lookup"><span data-stu-id="dff0c-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](https://docs.microsoft.com/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="dff0c-130">Per registrare i dispositivi Windows in Intune, agli amministratori devono essere già state assegnate licenze.</span><span class="sxs-lookup"><span data-stu-id="dff0c-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="dff0c-131">[Per informazioni sull'assegnazione delle licenze per la registrazione dei dispositivi, vedere](https://docs.microsoft.com/intune/licenses-assign).</span><span class="sxs-lookup"><span data-stu-id="dff0c-131">[Read about assigning licenses for device enrollment](https://docs.microsoft.com/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="dff0c-132">Per ottimizzare la gestione dei dispositivi tramite Intune, [connetti Intune a Defender per Endpoint.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="dff0c-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="dff0c-133">Ottenere le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="dff0c-133">Obtain required permissions</span></span>
<span data-ttu-id="dff0c-134">Per impostazione predefinita, solo gli utenti a cui è stato assegnato il ruolo Amministratore globale o Amministratore servizio Intune in Azure AD possono gestire e assegnare i profili di configurazione dei dispositivi necessari per l'onboarding dei dispositivi e la distribuzione della linea di base di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dff0c-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="dff0c-135">Se sono stati assegnati altri ruoli, verificare di disporre delle autorizzazioni necessarie:</span><span class="sxs-lookup"><span data-stu-id="dff0c-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="dff0c-136">Autorizzazioni complete per le configurazioni dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="dff0c-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="dff0c-137">Autorizzazioni complete per le linee di base della sicurezza</span><span class="sxs-lookup"><span data-stu-id="dff0c-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="dff0c-138">Autorizzazioni di lettura per i criteri di conformità dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="dff0c-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="dff0c-139">Autorizzazioni di lettura per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="dff0c-139">Read permissions to the organization</span></span>

<span data-ttu-id="dff0c-140">![Autorizzazioni necessarie in Intune](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="dff0c-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="dff0c-141">*Autorizzazioni di configurazione dei dispositivi in Intune*</span><span class="sxs-lookup"><span data-stu-id="dff0c-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="dff0c-142">Per ulteriori informazioni sull'assegnazione delle autorizzazioni in Intune, [vedere creazione di ruoli personalizzati.](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role)</span><span class="sxs-lookup"><span data-stu-id="dff0c-142">To learn more about assigning permissions on Intune, [read about creating custom roles](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="dff0c-143">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="dff0c-143">In this section</span></span>
<span data-ttu-id="dff0c-144">Argomento</span><span class="sxs-lookup"><span data-stu-id="dff0c-144">Topic</span></span> | <span data-ttu-id="dff0c-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dff0c-145">Description</span></span>
:---|:---
[<span data-ttu-id="dff0c-146">Eseguire l'onboarded dei dispositivi in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dff0c-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="dff0c-147">Tenere traccia dello stato di onboarding dei dispositivi gestiti da Intune e dell'onboarding di altri dispositivi tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="dff0c-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="dff0c-148">Aumentare la conformità alla linea di base di sicurezza di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dff0c-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="dff0c-149">Tenere traccia della conformità di base e della non conformità.</span><span class="sxs-lookup"><span data-stu-id="dff0c-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="dff0c-150">Distribuire la linea di base per la sicurezza in più dispositivi gestiti da Intune.</span><span class="sxs-lookup"><span data-stu-id="dff0c-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="dff0c-151">Ottimizzare la distribuzione e i rilevamenti delle regole asr</span><span class="sxs-lookup"><span data-stu-id="dff0c-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="dff0c-152">Esaminare la distribuzione delle regole e ottimizzare i rilevamenti usando gli strumenti di analisi dell'impatto nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dff0c-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="dff0c-153">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="dff0c-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dff0c-154">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="dff0c-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)