---
title: Configurare le funzionalità di Microsoft Defender ATP per iOS
description: Descrive come distribuire le funzionalità di Microsoft Defender ATP per iOS
keywords: microsoft, defender, atp, ios, configurare, funzionalità, ios
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 90e65c57321fa05a62bc94f4f56d92062d0826a1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186702"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a><span data-ttu-id="f733e-104">Configurare Le funzionalità di Microsoft Defender per Endpoint per iOS</span><span class="sxs-lookup"><span data-stu-id="f733e-104">Configure Microsoft Defender for Endpoint for iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f733e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f733e-105">**Applies to:**</span></span>
- [<span data-ttu-id="f733e-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f733e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f733e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f733e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f733e-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f733e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f733e-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f733e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="f733e-110">Defender for Endpoint per iOS userebbe una VPN per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="f733e-110">Defender for Endpoint for iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="f733e-111">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f733e-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a><span data-ttu-id="f733e-112">Accesso condizionale con Defender per Endpoint per iOS</span><span class="sxs-lookup"><span data-stu-id="f733e-112">Conditional Access with Defender for Endpoint for iOS</span></span>  
<span data-ttu-id="f733e-113">Microsoft Defender for Endpoint per iOS insieme a Microsoft Intune e Azure Active Directory consente di attivare la conformità dei dispositivi e i criteri di accesso condizionale in base ai livelli di rischio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f733e-113">Microsoft Defender for Endpoint for iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="f733e-114">Defender for Endpoint è una soluzione Mobile Threat Defense (MTD) che puoi distribuire per sfruttare questa funzionalità tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="f733e-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="f733e-115">Per altre informazioni su come configurare l'accesso condizionale con Defender per Endpoint per iOS, vedi [Defender per Endpoint e Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="f733e-115">For more information about how to set up Conditional Access with Defender for Endpoint for iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="f733e-116">Protezione Web e VPN</span><span class="sxs-lookup"><span data-stu-id="f733e-116">Web Protection and VPN</span></span>

<span data-ttu-id="f733e-117">Per impostazione predefinita, Defender per Endpoint per iOS include e abilita la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="f733e-117">By default, Defender for Endpoint for iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="f733e-118">[La protezione Web](web-protection-overview.md) consente di proteggere i dispositivi dalle minacce Web e proteggere gli utenti dagli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="f733e-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="f733e-119">Defender per Endpoint per iOS usa una VPN per fornire questa protezione.</span><span class="sxs-lookup"><span data-stu-id="f733e-119">Defender for Endpoint for iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="f733e-120">Tieni presente che si tratta di una VPN locale e, a differenza della VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f733e-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="f733e-121">Anche se abilitata per impostazione predefinita, in alcuni casi potrebbe essere necessario disabilitare vpn.</span><span class="sxs-lookup"><span data-stu-id="f733e-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="f733e-122">Ad esempio, vuoi eseguire alcune app che non funzionano quando è configurata una VPN.</span><span class="sxs-lookup"><span data-stu-id="f733e-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="f733e-123">In questi casi, puoi scegliere di disabilitare vpn dall'app nel dispositivo seguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f733e-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="f733e-124">Nel dispositivo iOS apri l'app **Impostazioni,** tocca o fai clic su **Generale** e **quindi su VPN.**</span><span class="sxs-lookup"><span data-stu-id="f733e-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="f733e-125">Tocca o fai clic sul pulsante "i" per Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="f733e-125">Click or tap the "i" button for Microsoft Defender ATP.</span></span>
1. <span data-ttu-id="f733e-126">Disattiva Connetti **su richiesta per** disabilitare LA VPN.</span><span class="sxs-lookup"><span data-stu-id="f733e-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f733e-127">![Connessione a richiesta della configurazione VPN](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="f733e-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="f733e-128">Protezione Web non sarà disponibile quando LA VPN è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f733e-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="f733e-129">Per abilitare di nuovo Web Protection, apri l'app Microsoft Defender for Endpoint nel dispositivo e tocca o fai clic su **Avvia VPN.**</span><span class="sxs-lookup"><span data-stu-id="f733e-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="f733e-130">Coesistenza di più profili VPN</span><span class="sxs-lookup"><span data-stu-id="f733e-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="f733e-131">Apple iOS non supporta più VPN a livello di dispositivo per essere attive contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f733e-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="f733e-132">Anche se nel dispositivo possono esistere più profili VPN, può essere attiva una sola VPN alla volta.</span><span class="sxs-lookup"><span data-stu-id="f733e-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="f733e-133">Configurare i criteri di conformità per i dispositivi jailbroken</span><span class="sxs-lookup"><span data-stu-id="f733e-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="f733e-134">Per proteggere l'accesso ai dati aziendali nei dispositivi iOS jailbroken, è consigliabile configurare i criteri di conformità seguenti in Intune.</span><span class="sxs-lookup"><span data-stu-id="f733e-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="f733e-135">In questo momento Microsoft Defender per Endpoint per iOS non fornisce protezione contro gli scenari di jailbreak.</span><span class="sxs-lookup"><span data-stu-id="f733e-135">At this time Microsoft Defender for Endpoint for iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="f733e-136">Se usato in un dispositivo jailbroken, in scenari specifici i dati usati dall'applicazione come l'ID di posta elettronica aziendale e l'immagine del profilo aziendale (se disponibile) possono essere esposti localmente</span><span class="sxs-lookup"><span data-stu-id="f733e-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="f733e-137">Segui i passaggi seguenti per creare un criterio di conformità per i dispositivi jailbroken.</span><span class="sxs-lookup"><span data-stu-id="f733e-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="f733e-138">[Nell'interfaccia di amministrazione di Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **Criteri** di  ->  **conformità dispositivi**  ->  **Crea criterio.**</span><span class="sxs-lookup"><span data-stu-id="f733e-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="f733e-139">Seleziona "iOS/iPadOS" come piattaforma e fai clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="f733e-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f733e-140">![Creare criteri](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="f733e-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="f733e-141">Specificare un nome del criterio, ad esempio "Criteri di conformità per Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="f733e-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="f733e-142">Nella pagina impostazioni di conformità fai clic per espandere la sezione **Integrità** dispositivo e fai clic **su Blocca** per il campo **Dispositivi Jailbroken.**</span><span class="sxs-lookup"><span data-stu-id="f733e-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f733e-143">![Impostazioni dei criteri](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="f733e-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="f733e-144">Nella sezione *Azione per la non conformità* selezionare le azioni in base ai requisiti e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f733e-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f733e-145">![Azioni dei criteri](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="f733e-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="f733e-146">Nella sezione *Assegnazioni* selezionare i gruppi di utenti che si desidera includere per questo criterio e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="f733e-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="f733e-147">Nella sezione **Revisione e creazione** verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f733e-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="f733e-148">Configurare indicatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="f733e-148">Configure custom indicators</span></span>

<span data-ttu-id="f733e-149">Defender for Endpoint per iOS consente agli amministratori di configurare indicatori personalizzati anche nei dispositivi iOS.</span><span class="sxs-lookup"><span data-stu-id="f733e-149">Defender for Endpoint for iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="f733e-150">Per ulteriori informazioni su come configurare gli indicatori personalizzati, vedere [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="f733e-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="f733e-151">Defender for Endpoint per iOS supporta la creazione di indicatori personalizzati solo per indirizzi IP e URL/domini.</span><span class="sxs-lookup"><span data-stu-id="f733e-151">Defender for Endpoint for iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="f733e-152">Segnala sito non sicuro</span><span class="sxs-lookup"><span data-stu-id="f733e-152">Report unsafe site</span></span>

<span data-ttu-id="f733e-153">I siti Web di phishing rappresentano siti Web attendibili allo scopo di ottenere informazioni personali o finanziarie.</span><span class="sxs-lookup"><span data-stu-id="f733e-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="f733e-154">Visitare la [pagina Fornire commenti e](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) suggerimenti sulla protezione di rete se si desidera segnalare un sito Web che potrebbe essere un sito di phishing.</span><span class="sxs-lookup"><span data-stu-id="f733e-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>
