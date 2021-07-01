---
title: Configurare Microsoft Defender per le funzionalità di Endpoint in iOS
description: Descrive come distribuire Microsoft Defender for Endpoint in funzionalità iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, configurare, funzionalità, ios
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230008"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="db451-104">Configurare Microsoft Defender per le funzionalità di Endpoint in iOS</span><span class="sxs-lookup"><span data-stu-id="db451-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db451-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="db451-105">**Applies to:**</span></span>
- [<span data-ttu-id="db451-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="db451-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db451-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db451-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="db451-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="db451-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="db451-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="db451-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="db451-110">Defender for Endpoint in iOS userebbe una VPN per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="db451-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="db451-111">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="db451-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="db451-112">Accesso condizionale con Defender per Endpoint in iOS</span><span class="sxs-lookup"><span data-stu-id="db451-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="db451-113">Microsoft Defender for Endpoint su iOS insieme a Microsoft Intune e Azure Active Directory consente di far rispettare la conformità dei dispositivi e i criteri di accesso condizionale in base al punteggio di rischio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="db451-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="db451-114">Defender for Endpoint è una soluzione Mobile Threat Defense (MTD) che puoi distribuire per sfruttare questa funzionalità tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="db451-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="db451-115">Per altre informazioni su come configurare l'accesso condizionale con Defender per Endpoint in iOS, vedi [Defender per Endpoint e Intune.](/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="db451-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="db451-116">Rilevamento jailbreak da parte di Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="db451-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="db451-117">Microsoft Defender for Endpoint è in grado di rilevare i dispositivi gestiti e non gestiti che sono jailbroken.</span><span class="sxs-lookup"><span data-stu-id="db451-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="db451-118">Se viene rilevato che un dispositivo è jailbroken, verrà segnalato un avviso ad alto rischio al Centro sicurezza e se l'accesso condizionale viene configurazione in base al punteggio di rischio del dispositivo, al dispositivo verrà impedito l'accesso ai dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="db451-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="db451-119">Protezione Web e VPN</span><span class="sxs-lookup"><span data-stu-id="db451-119">Web Protection and VPN</span></span>

<span data-ttu-id="db451-120">Per impostazione predefinita, Defender per Endpoint in iOS include e abilita la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="db451-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="db451-121">[La protezione Web](web-protection-overview.md) consente di proteggere i dispositivi dalle minacce Web e proteggere gli utenti dagli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="db451-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="db451-122">Defender for Endpoint su iOS usa una VPN per fornire questa protezione.</span><span class="sxs-lookup"><span data-stu-id="db451-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="db451-123">Tieni presente che si tratta di una VPN locale e, a differenza della VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="db451-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="db451-124">Anche se abilitata per impostazione predefinita, in alcuni casi potrebbe essere necessario disabilitare vpn.</span><span class="sxs-lookup"><span data-stu-id="db451-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="db451-125">Ad esempio, vuoi eseguire alcune app che non funzionano quando è configurata una VPN.</span><span class="sxs-lookup"><span data-stu-id="db451-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="db451-126">In questi casi, puoi scegliere di disabilitare vpn dall'app nel dispositivo seguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="db451-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="db451-127">Nel dispositivo iOS, apri l'app **Impostazioni,** tocca o fai clic su **Generale** e **quindi su VPN.**</span><span class="sxs-lookup"><span data-stu-id="db451-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="db451-128">Tocca o fai clic sul pulsante "i" per Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="db451-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="db451-129">Disattiva la **Connessione su richiesta per** disabilitare la VPN.</span><span class="sxs-lookup"><span data-stu-id="db451-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="db451-130">![Connessione a richiesta della configurazione VPN](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="db451-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="db451-131">Protezione Web non sarà disponibile quando LA VPN è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="db451-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="db451-132">Per abilitare di nuovo Web Protection, apri l'app Microsoft Defender for Endpoint nel dispositivo e tocca o fai clic su **Avvia VPN.**</span><span class="sxs-lookup"><span data-stu-id="db451-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="db451-133">Coesistenza di più profili VPN</span><span class="sxs-lookup"><span data-stu-id="db451-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="db451-134">Apple iOS non supporta più VPN a livello di dispositivo per essere attive contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="db451-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="db451-135">Anche se nel dispositivo possono esistere più profili VPN, può essere attiva una sola VPN alla volta.</span><span class="sxs-lookup"><span data-stu-id="db451-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a><span data-ttu-id="db451-136">Configurare Microsoft Defender per il segnale di rischio endpoint nei criteri di protezione delle app (MAM)</span><span class="sxs-lookup"><span data-stu-id="db451-136">Configure Microsoft Defender for Endpoint risk signal in app protection policy (MAM)</span></span>

<span data-ttu-id="db451-137">Microsoft Defender for Endpoint può essere configurato per inviare segnali di minaccia da usare nei criteri di protezione delle app (APP, noto anche come MAM) in iOS/iPadOS.</span><span class="sxs-lookup"><span data-stu-id="db451-137">Microsoft Defender for Endpoint can be configured to send threat signals to be used in App Protection Policies (APP, also known as MAM) on iOS/iPadOS.</span></span> <span data-ttu-id="db451-138">Con questa funzionalità, puoi usare Microsoft Defender for Endpoint per proteggere l'accesso ai dati aziendali anche dai dispositivi di cui non è stata annullata la registrazione.</span><span class="sxs-lookup"><span data-stu-id="db451-138">With this capability, you can use Microsoft Defender for Endpoint to protect access to corporate data from unenrolled devices as well.</span></span>

<span data-ttu-id="db451-139">I passaggi per configurare i criteri di protezione delle app con Microsoft Defender for Endpoint sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="db451-139">Steps to setup app protection policies with Microsoft Defender for Endpoint are as below:</span></span>

1. <span data-ttu-id="db451-140">Configurare la connessione dal tenant Microsoft Endpoint Manager a Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="db451-140">Set up the connection from your Microsoft Endpoint Manager tenant to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="db451-141">Nell'interfaccia di amministrazione di [Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **Connettori** di amministrazione tenant e  >  **token** Microsoft Defender  >  **for Endpoint** (sotto Piattaforma incrociata) o **Endpoint Security** Microsoft Defender  >  **for Endpoint** (in Configurazione) e attiva gli interruttori in Criteri di protezione app Impostazioni per **iOS**.</span><span class="sxs-lookup"><span data-stu-id="db451-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Tenant Administration** > **Connectors and tokens** > **Microsoft Defender for Endpoint** (under Cross platform) or **Endpoint Security** > **Microsoft Defender for Endpoint** (under Setup) and turn on the toggles under **App Protection Policy Settings for iOS**.</span></span>
1. <span data-ttu-id="db451-142">Seleziona Salva.</span><span class="sxs-lookup"><span data-stu-id="db451-142">Select Save.</span></span> <span data-ttu-id="db451-143">Dovrebbe essere visualizzato **Lo stato della** connessione è ora impostato su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="db451-143">You should see **Connection status** is now set to **Enabled**.</span></span>
1. <span data-ttu-id="db451-144">Creare criteri di protezione delle app: dopo aver completato la configurazione del connettore Microsoft Defender for Endpoint, passare a App Criteri di protezione delle app (in Criteri) per creare un nuovo criterio o aggiornarne  >   uno esistente.</span><span class="sxs-lookup"><span data-stu-id="db451-144">Create app protection policy: After your Microsoft Defender for Endpoint connector setup is complete, navigate to **Apps** > **App protection policies** (under Policy) to create a new policy or update an existing one.</span></span>
1. <span data-ttu-id="db451-145">Selezionare le impostazioni dei requisiti di **piattaforma, app, protezione dei dati e** accesso richieste dall'organizzazione per i criteri.</span><span class="sxs-lookup"><span data-stu-id="db451-145">Select the platform, **Apps, Data protection, Access requirements** settings that your organization requires for your policy.</span></span>
1. <span data-ttu-id="db451-146">In **Condizioni del dispositivo di** avvio  >  **condizionale** troverai l'impostazione Max allowed device threat **level**.</span><span class="sxs-lookup"><span data-stu-id="db451-146">Under **Conditional launch** > **Device conditions**, you will find the setting **Max allowed device threat level**.</span></span> <span data-ttu-id="db451-147">Questo dovrà essere configurato su Basso, Medio, Alto o Protetto.</span><span class="sxs-lookup"><span data-stu-id="db451-147">This will need to be configured to either Low, Medium, High, or Secured.</span></span> <span data-ttu-id="db451-148">Le azioni disponibili saranno Blocca **accesso** o **Cancella dati.**</span><span class="sxs-lookup"><span data-stu-id="db451-148">The actions available to you will be **Block access** or **Wipe data**.</span></span> <span data-ttu-id="db451-149">È possibile che venga visualizzata una finestra di dialogo in formato informativo per verificare che il connettore sia configurato prima che questa impostazione abbia effetto.</span><span class="sxs-lookup"><span data-stu-id="db451-149">You may see an informational dialog to make sure you have your connector set up prior to this setting take effect.</span></span> <span data-ttu-id="db451-150">Se il connettore è già configurato, è possibile ignorare questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="db451-150">If your connector is already set up, you may ignore this dialog.</span></span>
1. <span data-ttu-id="db451-151">Completare con Assegnazioni e salvare i criteri.</span><span class="sxs-lookup"><span data-stu-id="db451-151">Finish with Assignments and save your policy.</span></span>

<span data-ttu-id="db451-152">Per altri dettagli su MAM o sui criteri di protezione delle app, vedi Impostazioni dei criteri [di protezione delle app iOS.](/mem/intune/apps/app-protection-policy-settings-ios)</span><span class="sxs-lookup"><span data-stu-id="db451-152">For more details on MAM or app protection policy, see [iOS app protection policy settings](/mem/intune/apps/app-protection-policy-settings-ios).</span></span>

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a><span data-ttu-id="db451-153">Distribuzione di Microsoft Defender per Endpoint per MAM o su dispositivi non registrazione</span><span class="sxs-lookup"><span data-stu-id="db451-153">Deploying Microsoft Defender for Endpoint for MAM or on unenrolled devices</span></span>

<span data-ttu-id="db451-154">Microsoft Defender for Endpoint su iOS abilita lo scenario dei criteri di protezione delle app ed è disponibile nell'App Store di Apple.</span><span class="sxs-lookup"><span data-stu-id="db451-154">Microsoft Defender for Endpoint on iOS enables the App Protection Policy scenario and is available in the Apple app store.</span></span>

<span data-ttu-id="db451-155">Gli utenti finali devono installare la versione più recente dell'app direttamente dall'App Store di Apple.</span><span class="sxs-lookup"><span data-stu-id="db451-155">End-users should install the latest version of the app directly from the Apple app store.</span></span>

## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="db451-156">Configurare i criteri di conformità per i dispositivi jailbroken</span><span class="sxs-lookup"><span data-stu-id="db451-156">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="db451-157">Per proteggere l'accesso ai dati aziendali nei dispositivi iOS jailbroken, è consigliabile configurare i criteri di conformità seguenti in Intune.</span><span class="sxs-lookup"><span data-stu-id="db451-157">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="db451-158">Il rilevamento jailbreak è una funzionalità fornita da Microsoft Defender per Endpoint in iOS.</span><span class="sxs-lookup"><span data-stu-id="db451-158">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="db451-159">Tuttavia, ti consigliamo di configurare questo criterio come un ulteriore livello di difesa contro gli scenari di jailbreak.</span><span class="sxs-lookup"><span data-stu-id="db451-159">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="db451-160">Segui i passaggi seguenti per creare un criterio di conformità per i dispositivi jailbroken.</span><span class="sxs-lookup"><span data-stu-id="db451-160">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="db451-161">In [Microsoft Endpoint Manager di amministrazione,](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **Criteri** di  ->  **conformità dispositivi** Crea  ->  **criterio.**</span><span class="sxs-lookup"><span data-stu-id="db451-161">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="db451-162">Seleziona "iOS/iPadOS" come piattaforma e fai clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="db451-162">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="db451-163">![Creare criteri](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="db451-163">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="db451-164">Specificare un nome del criterio, ad esempio "Criteri di conformità per Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="db451-164">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="db451-165">Nella pagina impostazioni di conformità fai clic per espandere la sezione **Integrità** dispositivo e fai clic **su Blocca** per il campo **Dispositivi Jailbroken.**</span><span class="sxs-lookup"><span data-stu-id="db451-165">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="db451-166">![Criteri Impostazioni](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="db451-166">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="db451-167">Nella sezione **Azione per la non conformità** selezionare le azioni in base ai requisiti e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="db451-167">In the **Action for noncompliance** section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="db451-168">![Azioni dei criteri](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="db451-168">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="db451-169">Nella sezione **Assegnazioni** selezionare i gruppi di utenti che si desidera includere per questo criterio e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="db451-169">In the **Assignments** section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="db451-170">Nella sezione **Revisione e creazione** verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="db451-170">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="db451-171">Configurare indicatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="db451-171">Configure custom indicators</span></span>

<span data-ttu-id="db451-172">Defender for Endpoint su iOS consente agli amministratori di configurare indicatori personalizzati anche nei dispositivi iOS.</span><span class="sxs-lookup"><span data-stu-id="db451-172">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="db451-173">Per ulteriori informazioni su come configurare gli indicatori personalizzati, vedere [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="db451-173">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="db451-174">Defender for Endpoint in iOS supporta la creazione di indicatori personalizzati solo per indirizzi IP e URL/domini.</span><span class="sxs-lookup"><span data-stu-id="db451-174">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="db451-175">Segnala sito non sicuro</span><span class="sxs-lookup"><span data-stu-id="db451-175">Report unsafe site</span></span>

<span data-ttu-id="db451-176">I siti Web di phishing rappresentano siti Web attendibili allo scopo di ottenere informazioni personali o finanziarie.</span><span class="sxs-lookup"><span data-stu-id="db451-176">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="db451-177">Visitare la [pagina Fornire commenti e](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) suggerimenti sulla protezione di rete se si desidera segnalare un sito Web che potrebbe essere un sito di phishing.</span><span class="sxs-lookup"><span data-stu-id="db451-177">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

