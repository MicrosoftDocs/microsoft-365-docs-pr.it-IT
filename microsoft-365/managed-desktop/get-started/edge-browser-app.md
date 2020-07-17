---
title: Nuovo Microsoft Edge
description: ''
keywords: browser, Microsoft Managed Desktop, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f4bc5f85b21148c5a923ca1fc18879a193191c4b
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094787"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="8946a-103">Nuova app Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8946a-103">New Microsoft Edge app</span></span>

<span data-ttu-id="8946a-104">Il nuovo [browser Microsoft Edge](https://www.microsoft.com/edge) offre prestazioni di livello internazionale con maggiore privacy, maggiore produttività e più valore durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8946a-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="8946a-105">Microsoft Managed Desktop offre un'anteprima pubblica della distribuzione del nuovo browser perimetrale nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="8946a-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="8946a-106">Distribuzione iniziale</span><span class="sxs-lookup"><span data-stu-id="8946a-106">Initial deployment</span></span>

<span data-ttu-id="8946a-107">Per eseguire la migrazione dei dispositivi Microsoft Managed Desktop al nuovo browser Microsoft Edge, è possibile archiviare un ticket di supporto IT tramite il portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8946a-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="8946a-108">La distribuzione del canale stable perimetrale nel gruppo di test viene distribuita quando si esegue il file del ticket e quindi viene distribuita in ogni gruppo di distribuzione successivo ogni 24 ore.</span><span class="sxs-lookup"><span data-stu-id="8946a-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="8946a-109">Per sospendere la distribuzione, eseguire il file di un altro ticket che richiede le operazioni da mantenere.</span><span class="sxs-lookup"><span data-stu-id="8946a-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="8946a-110">Aggiornamenti a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8946a-110">Updates to Microsoft Edge</span></span>

<span data-ttu-id="8946a-111">Microsoft Managed Desktop distribuisce il [canale stabile](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) di Microsoft Edge che viene aggiornato automaticamente circa ogni sei settimane.</span><span class="sxs-lookup"><span data-stu-id="8946a-111">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="8946a-112">Gli aggiornamenti sul canale stabile vengono distribuiti [progressivamente](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) dal gruppo di prodotti Microsoft Edge per garantire la migliore esperienza per i clienti.</span><span class="sxs-lookup"><span data-stu-id="8946a-112">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> <span data-ttu-id="8946a-113">Il canale Microsoft Edge beta non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="8946a-113">The Microsoft Edge Beta channel is not currently available.</span></span>

<span data-ttu-id="8946a-114">Per assicurarsi che Microsoft Edge venga aggiornato correttamente, non modificare i criteri Microsoft Edge [Update](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span><span class="sxs-lookup"><span data-stu-id="8946a-114">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="8946a-115">Impostazioni gestite da Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="8946a-115">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="8946a-116">Microsoft Managed Desktop ha creato un set predefinito di criteri per Microsoft Edge per proteggere il browser.</span><span class="sxs-lookup"><span data-stu-id="8946a-116">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="8946a-117">Di seguito sono riportate le impostazioni predefinite del browser:</span><span class="sxs-lookup"><span data-stu-id="8946a-117">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="8946a-118">Microsoft Edge Extensions</span><span class="sxs-lookup"><span data-stu-id="8946a-118">Microsoft Edge extensions</span></span>

<span data-ttu-id="8946a-119">La baseline di sicurezza per Microsoft Edge nei dispositivi Microsoft Managed Desktop imposta due criteri per disabilitare tutte le estensioni Chrome e gli utenti finali sicuri.</span><span class="sxs-lookup"><span data-stu-id="8946a-119">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="8946a-120">Per abilitare e distribuire le estensioni nell'ambiente, vedere settings you manage.</span><span class="sxs-lookup"><span data-stu-id="8946a-120">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="8946a-121">Blocco per l'installazione dell'estensione</span><span class="sxs-lookup"><span data-stu-id="8946a-121">Extension installation blocklist</span></span>
<span data-ttu-id="8946a-122">**Valore predefinito:** Tutti</span><span class="sxs-lookup"><span data-stu-id="8946a-122">**Default value:** All</span></span>

<span data-ttu-id="8946a-123">Microsoft Managed Desktop imposta questo criterio per impedire l'installazione delle estensioni Chrome negli endpoint gestiti.</span><span class="sxs-lookup"><span data-stu-id="8946a-123">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="8946a-124">Sono noti risksassociated con il modello di estensione Chromium, tra cui la protezione dalla perdita di dati, la privacy e altri rischi che possono compromettere i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8946a-124">There are known risksassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="8946a-125">Consenti host di messaggistica nativa a livello di utente (installati senza autorizzazioni di amministratore)</span><span class="sxs-lookup"><span data-stu-id="8946a-125">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="8946a-126">**Valore predefinito:** Disabili</span><span class="sxs-lookup"><span data-stu-id="8946a-126">**Default value:** Disabled</span></span>

<span data-ttu-id="8946a-127">Disabilitando questo criterio, Microsoft Edge utilizzerà solo host di messaggistica native installati a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="8946a-127">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="8946a-128">Gli host di messaggistica native fanno parte di estensioni di Chrome che consentono al browser di interagire con altre parti dell'endpoint dell'utente, creando una serie di problemi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8946a-128">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="8946a-129"> SSL (Secure Sockets Layer) </span><span class="sxs-lookup"><span data-stu-id="8946a-129">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="8946a-130">Versione SSL minima</span><span class="sxs-lookup"><span data-stu-id="8946a-130">Minimum SSL version</span></span>

<span data-ttu-id="8946a-131">**Valore predefinito:** Minimo TLS 1,2 supportato</span><span class="sxs-lookup"><span data-stu-id="8946a-131">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="8946a-132">Se si desidera utilizzare il TLS 1,1 meno sicuro, è possibile richiederlo.</span><span class="sxs-lookup"><span data-stu-id="8946a-132">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="8946a-133">Consente agli utenti di procedere dalla pagina di avviso SSL</span><span class="sxs-lookup"><span data-stu-id="8946a-133">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="8946a-134">**Valore predefinito:** Disabili</span><span class="sxs-lookup"><span data-stu-id="8946a-134">**Default value:** Disabled</span></span>

<span data-ttu-id="8946a-135">Non è consigliabile abilitare questa impostazione poiché consente agli utenti di visitare i siti con errori SSL.</span><span class="sxs-lookup"><span data-stu-id="8946a-135">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smart-screen"></a><span data-ttu-id="8946a-136">Smart Screen Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8946a-136">Microsoft Defender Smart Screen</span></span>

#### <a name="configure-microsoft-defender-smartscreen"></a><span data-ttu-id="8946a-137">Configurare Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="8946a-137">Configure Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="8946a-138">**Valore predefinito:** Abilitato</span><span class="sxs-lookup"><span data-stu-id="8946a-138">**Default value:** Enabled</span></span>

<span data-ttu-id="8946a-139">Abilitata per impostazione predefinita per garantire la protezione degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="8946a-139">Enabled by default to help protect end users.</span></span>

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="8946a-140">Microsoft Defender SmartScreen richiede i siti</span><span class="sxs-lookup"><span data-stu-id="8946a-140">Microsoft Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="8946a-141">**Valore predefinito:** Abilitato</span><span class="sxs-lookup"><span data-stu-id="8946a-141">**Default value:** Enabled</span></span>

<span data-ttu-id="8946a-142">Non è consigliabile disabilitare questa impostazione in quanto consente agli utenti di ignorare gli avvisi e continuare a siti potenzialmente dannosi.</span><span class="sxs-lookup"><span data-stu-id="8946a-142">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="8946a-143">Evitare di ignorare gli avvisi di Microsoft Defender SmartScreen sui download</span><span class="sxs-lookup"><span data-stu-id="8946a-143">Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="8946a-144">**Valore predefinito:** Abilitato</span><span class="sxs-lookup"><span data-stu-id="8946a-144">**Default value:** Enabled</span></span>

<span data-ttu-id="8946a-145">Non è consigliabile disabilitare questa impostazione in quanto consente agli utenti di ignorare gli avvisi e completare i download non verificati.</span><span class="sxs-lookup"><span data-stu-id="8946a-145">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="8946a-146">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="8946a-146">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="8946a-147">Impostazione predefinita di Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="8946a-147">Default Adobe Flash setting</span></span>

<span data-ttu-id="8946a-148">**Valore predefinito:** Disabili</span><span class="sxs-lookup"><span data-stu-id="8946a-148">**Default value:** Disabled</span></span>

<span data-ttu-id="8946a-149">Non è consigliabile utilizzare Flash a causa di rischi per la sicurezza associati.</span><span class="sxs-lookup"><span data-stu-id="8946a-149">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="8946a-150">Se si hanno ancora processi che dipendono da Flash, impostare i criteri di **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** per abilitare il flash per i siti che ne hanno bisogno.</span><span class="sxs-lookup"><span data-stu-id="8946a-150">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="8946a-151">Se non è possibile mantenere un elenco di siti consentiti per l'utilizzo di Flash, presentare una richiesta di modifica per modificare il valore da **fare clic su per riprodurre**, che consente agli utenti di scegliere quando è opportuno eseguire Flash.</span><span class="sxs-lookup"><span data-stu-id="8946a-151">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="8946a-152">Gestione password</span><span class="sxs-lookup"><span data-stu-id="8946a-152">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="8946a-153">Abilitare il salvataggio delle password per il gestore delle password</span><span class="sxs-lookup"><span data-stu-id="8946a-153">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="8946a-154">**Valore predefinito:** Disabili</span><span class="sxs-lookup"><span data-stu-id="8946a-154">**Default value:** Disabled</span></span>

<span data-ttu-id="8946a-155">È consigliabile non consentire agli utenti finali di salvare le password sul proprio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8946a-155">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="other-settings"></a><span data-ttu-id="8946a-156">Altre impostazioni</span><span class="sxs-lookup"><span data-stu-id="8946a-156">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="8946a-157">Abilitare l'isolamento dei siti per ogni sito</span><span class="sxs-lookup"><span data-stu-id="8946a-157">Enable site isolation for every site</span></span>

<span data-ttu-id="8946a-158">**Valore predefinito:** Abilitato</span><span class="sxs-lookup"><span data-stu-id="8946a-158">**Default value:** Enabled</span></span>

<span data-ttu-id="8946a-159">Quando questo criterio è abilitato, gli utenti non possono escludere il comportamento predefinito in cui ogni sito viene eseguito nel proprio processo.</span><span class="sxs-lookup"><span data-stu-id="8946a-159">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="8946a-160">Schemi di autenticazione supportati</span><span class="sxs-lookup"><span data-stu-id="8946a-160">Supported authentication schemes</span></span>

<span data-ttu-id="8946a-161">**Valore predefinito:** NTLM, negozia</span><span class="sxs-lookup"><span data-stu-id="8946a-161">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="8946a-162">Microsoft Managed Desktop non supporta schemi di autenticazione di base o di digest.</span><span class="sxs-lookup"><span data-stu-id="8946a-162">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="8946a-163">Importare automaticamente i dati e le impostazioni di un altro browser al primo avvio</span><span class="sxs-lookup"><span data-stu-id="8946a-163">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="8946a-164">**Valore predefinito:** Importare automaticamente tutti i tipi di DataType e le impostazioni supportati dal browser predefinito</span><span class="sxs-lookup"><span data-stu-id="8946a-164">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="8946a-165">Con questo criterio applicato, la prima operazione di esecuzione ignorerà la sezione Import, riducendo al minimo l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8946a-165">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="8946a-166">I dati del browser provenienti da versioni precedenti di Microsoft Edge verranno sempre migrati automaticamente al primo avvio, indipendentemente da questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="8946a-166">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="8946a-167">Impostazioni gestite</span><span class="sxs-lookup"><span data-stu-id="8946a-167">Settings you manage</span></span>

<span data-ttu-id="8946a-168">È possibile distribuire le impostazioni del server perimetrale di Microsoft non descritte in precedenza utilizzando il profilo dei modelli amministrativi in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8946a-168">You can deploy any Microsft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="8946a-169">Per ulteriori informazioni, vedere [configurare le impostazioni dei criteri Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="8946a-169">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="8946a-170">Se si desidera valutare un criterio che non è attualmente incluso nei modelli amministrativi Microsoft Edge in Intune, è possibile utilizzare le impostazioni personalizzate per i dispositivi Windows 10 in Intune.</span><span class="sxs-lookup"><span data-stu-id="8946a-170">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="8946a-171">Abilitazione di estensioni Chrome specifiche</span><span class="sxs-lookup"><span data-stu-id="8946a-171">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="8946a-172">Il modello amministrativo offre un'impostazione per la distribuzione di specifiche estensioni Chrome con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8946a-172">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="8946a-173">È possibile trovarlo in **Configurazione Computer > Microsoft Edge > extensions > consentire l'installazione di estensioni specifiche**.</span><span class="sxs-lookup"><span data-stu-id="8946a-173">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="8946a-174">Installare le estensioni in modo invisibile all'utente</span><span class="sxs-lookup"><span data-stu-id="8946a-174">Install extensions silently</span></span>

<span data-ttu-id="8946a-175">È inoltre possibile utilizzare il modello amministrativo per impostare Microsoft Edge per l'installazione delle estensioni senza avvisare l'utente.</span><span class="sxs-lookup"><span data-stu-id="8946a-175">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="8946a-176">È possibile trovarlo in **Configurazione Computer > Microsoft Edge > extensions > controllare quali estensioni vengono installate automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="8946a-176">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="8946a-177">Altri criteri dell'organizzazione comuni</span><span class="sxs-lookup"><span data-stu-id="8946a-177">Other common enterprise policies</span></span>

<span data-ttu-id="8946a-178">Microsoft Edge offre numerosi criteri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="8946a-178">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="8946a-179">Questi sono alcuni tra quelli più comuni:</span><span class="sxs-lookup"><span data-stu-id="8946a-179">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="8946a-180">Configurare i siti nell'elenco e la modalità IE del sito dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8946a-180">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="8946a-181">Configurare le impostazioni di avvio, Home page e nuova scheda pagina</span><span class="sxs-lookup"><span data-stu-id="8946a-181">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="8946a-182">Configurare l'impostazione del gioco Surf</span><span class="sxs-lookup"><span data-stu-id="8946a-182">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="8946a-183">Configurare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="8946a-183">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

