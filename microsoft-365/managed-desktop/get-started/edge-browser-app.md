---
title: Nuovo Microsoft Edge
description: Spiega come distribuire e aggiornare il nuovo browser Edge
keywords: browser, Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841340"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="b32fb-104">Nuova app Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b32fb-104">New Microsoft Edge app</span></span>

<span data-ttu-id="b32fb-105">Il nuovo [browser Microsoft Edge](https://www.microsoft.com/edge) offre prestazioni di livello mondiale con maggiore privacy, maggiore produttività e più valore durante l'esplorazione.</span><span class="sxs-lookup"><span data-stu-id="b32fb-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="b32fb-106">Microsoft Managed Desktop offre un'anteprima pubblica della distribuzione del nuovo browser Edge nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b32fb-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="b32fb-107">Distribuzione iniziale</span><span class="sxs-lookup"><span data-stu-id="b32fb-107">Initial deployment</span></span>

<span data-ttu-id="b32fb-108">Per eseguire la migrazione dei dispositivi Microsoft Managed Desktop nel nuovo browser Microsoft Edge, creare un ticket di supporto IT tramite microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="b32fb-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="b32fb-109">Il canale Stable di Edge verrà distribuito al gruppo di test quando si esegue il file del ticket e quindi verrà distribuito in ogni gruppo di distribuzione successivo ogni 24 ore.</span><span class="sxs-lookup"><span data-stu-id="b32fb-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="b32fb-110">Per sospendere la distribuzione, creare un altro ticket per richiedere il blocco a Operations.</span><span class="sxs-lookup"><span data-stu-id="b32fb-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="b32fb-111">Il [Canale Beta è](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) disponibile anche su richiesta di una convalida rappresentativa all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b32fb-111">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="b32fb-112">Microsoft Managed Desktop distribuirà l'applicazione in base alle esigenze ai gruppi Test e First, in modo che tutti gli utenti hanno il Canale Beta oltre al Canale Stable.</span><span class="sxs-lookup"><span data-stu-id="b32fb-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="b32fb-113">Per tutti gli altri utenti che hanno bisogno di accedere al Canale beta, aggiungerli al gruppo **Modern Workplace - Edge Beta Users** e installarlo dal portale aziendale</span><span class="sxs-lookup"><span data-stu-id="b32fb-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="b32fb-114">Aggiornamenti a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b32fb-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="b32fb-115">Microsoft Managed Desktop distribuisce il [canale Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) di Microsoft Edge, che viene aggiornato automaticamente ogni sei settimane.</span><span class="sxs-lookup"><span data-stu-id="b32fb-115">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="b32fb-116">Gli aggiornamenti nel canale Stable [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) vengono gradualmente installati dal gruppo di prodotti Microsoft Edge per garantire la migliore esperienza per i clienti.</span><span class="sxs-lookup"><span data-stu-id="b32fb-116">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="b32fb-117">Il [canale Beta viene](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) distribuito ai dispositivi sia nei gruppi Test che First per la convalida rappresentativa all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b32fb-117">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="b32fb-118">Questo canale è completamente supportato e viene aggiornato automaticamente con nuove funzionalità circa ogni sei settimane.</span><span class="sxs-lookup"><span data-stu-id="b32fb-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="b32fb-119">Per assicurarsi che Microsoft Edge venga aggiornato correttamente, non modificare i criteri di aggiornamento [di](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="b32fb-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="b32fb-120">Impostazioni gestite da Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="b32fb-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="b32fb-121">Microsoft Managed Desktop ha creato un set predefinito di criteri per Microsoft Edge per proteggere il browser.</span><span class="sxs-lookup"><span data-stu-id="b32fb-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="b32fb-122">Le impostazioni predefinite del browser sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b32fb-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="b32fb-123">Estensioni di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b32fb-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="b32fb-124">La linea di base della sicurezza per Microsoft Edge nei dispositivi Microsoft Managed Desktop imposta due criteri per disabilitare tutte le estensioni di Chrome e proteggere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b32fb-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="b32fb-125">Per abilitare e distribuire le estensioni nell'ambiente, vedere Impostazioni gestite.</span><span class="sxs-lookup"><span data-stu-id="b32fb-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="b32fb-126">Elenco di indirizzi di installazione delle estensioni</span><span class="sxs-lookup"><span data-stu-id="b32fb-126">Extension installation blocklist</span></span>
<span data-ttu-id="b32fb-127">**Valore predefinito:** All</span><span class="sxs-lookup"><span data-stu-id="b32fb-127">**Default value:** All</span></span>

<span data-ttu-id="b32fb-128">Microsoft Managed Desktop imposta questo criterio per impedire l'installazione delle estensioni di Chrome in endpoint gestiti.</span><span class="sxs-lookup"><span data-stu-id="b32fb-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="b32fb-129">Esistono rischi noti associati al modello di estensione Chromium, tra cui la protezione della perdita di dati, la privacy e altri rischi che possono compromettere i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b32fb-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="b32fb-130">Consenti host di messaggistica nativa a livello di utente (installati senza autorizzazioni di amministratore)</span><span class="sxs-lookup"><span data-stu-id="b32fb-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="b32fb-131">**Valore predefinito:** Disabilitato</span><span class="sxs-lookup"><span data-stu-id="b32fb-131">**Default value:** Disabled</span></span>

<span data-ttu-id="b32fb-132">Disabilitando questo criterio, Microsoft Edge utilizzerà solo gli host di messaggistica nativa installati a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="b32fb-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="b32fb-133">Gli host di messaggistica nativa fanno parte delle estensioni di Chrome, che consentono al browser di interagire con altre parti dell'endpoint dell'utente, creando una serie di problemi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b32fb-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="b32fb-134">Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="b32fb-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="b32fb-135">Versione tls minima</span><span class="sxs-lookup"><span data-stu-id="b32fb-135">Minimum TLS version</span></span>

<span data-ttu-id="b32fb-136">**Valore predefinito:** Tls 1.2 minimo supportato</span><span class="sxs-lookup"><span data-stu-id="b32fb-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="b32fb-137">Se si desidera utilizzare TLS 1.1 meno sicuro, è possibile determinare una richiesta per farlo.</span><span class="sxs-lookup"><span data-stu-id="b32fb-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="b32fb-138">Consente agli utenti di procedere dalla pagina di avviso SSL</span><span class="sxs-lookup"><span data-stu-id="b32fb-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="b32fb-139">**Valore predefinito:** Disabilitato</span><span class="sxs-lookup"><span data-stu-id="b32fb-139">**Default value:** Disabled</span></span>

<span data-ttu-id="b32fb-140">Non è consigliabile abilitare questa impostazione perché consente agli utenti di visitare siti con errori TSL.</span><span class="sxs-lookup"><span data-stu-id="b32fb-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="b32fb-141">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="b32fb-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="b32fb-142">Configurare Windows Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="b32fb-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="b32fb-143">**Valore predefinito:** Abilitato</span><span class="sxs-lookup"><span data-stu-id="b32fb-143">**Default value:** Enabled</span></span>

<span data-ttu-id="b32fb-144">Abilitata per impostazione predefinita per proteggere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b32fb-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="b32fb-145">Windows Defender prompt di SmartScreen per i siti</span><span class="sxs-lookup"><span data-stu-id="b32fb-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="b32fb-146">**Valore predefinito:** Abilitato</span><span class="sxs-lookup"><span data-stu-id="b32fb-146">**Default value:** Enabled</span></span>

<span data-ttu-id="b32fb-147">Non è consigliabile disabilitare questa impostazione perché consentirebbe agli utenti di ignorare gli avvisi e continuare con siti potenzialmente dannosi.</span><span class="sxs-lookup"><span data-stu-id="b32fb-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="b32fb-148">Impedisci il bypass Windows Defender avvisi di SmartScreen sui download</span><span class="sxs-lookup"><span data-stu-id="b32fb-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="b32fb-149">**Valore predefinito:** Abilitato</span><span class="sxs-lookup"><span data-stu-id="b32fb-149">**Default value:** Enabled</span></span>

<span data-ttu-id="b32fb-150">Non è consigliabile disabilitare questa impostazione perché consentirebbe agli utenti di ignorare gli avvisi e completare i download nonverificati.</span><span class="sxs-lookup"><span data-stu-id="b32fb-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="b32fb-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="b32fb-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="b32fb-152">Impostazione predefinita di Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="b32fb-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="b32fb-153">**Valore predefinito:** Disabilitato</span><span class="sxs-lookup"><span data-stu-id="b32fb-153">**Default value:** Disabled</span></span>

<span data-ttu-id="b32fb-154">Non è consigliabile usare Flash a causa dei rischi per la sicurezza associati.</span><span class="sxs-lookup"><span data-stu-id="b32fb-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="b32fb-155">Se hai ancora processi che dipendono da Flash, imposta il criterio **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** per abilitare Flash per i siti che ne hanno bisogno.</span><span class="sxs-lookup"><span data-stu-id="b32fb-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="b32fb-156">Se non riesci a mantenere un elenco di siti consentiti per l'uso di Flash, crea una richiesta di modifica per modificare il valore in **Click to Play,** che consente agli utenti di scegliere quando è appropriato eseguire Flash.</span><span class="sxs-lookup"><span data-stu-id="b32fb-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="b32fb-157">Gestione password</span><span class="sxs-lookup"><span data-stu-id="b32fb-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="b32fb-158">Abilitare il salvataggio delle password nel gestore delle password</span><span class="sxs-lookup"><span data-stu-id="b32fb-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="b32fb-159">**Valore predefinito:** Disabilitato</span><span class="sxs-lookup"><span data-stu-id="b32fb-159">**Default value:** Disabled</span></span>

<span data-ttu-id="b32fb-160">Non è consigliabile consentire agli utenti di salvare le password nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b32fb-160">We do not recommend allowing users to save passwords on their device.</span></span>

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="b32fb-161">Modalità Internet Explorer in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b32fb-161">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="b32fb-162">La modalità IE in Microsoft Edge semplifica l'uso di tutti i siti di cui l'organizzazione ha bisogno in un unico browser.</span><span class="sxs-lookup"><span data-stu-id="b32fb-162">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="b32fb-163">Usa il motore Chromium integrato per i siti compatibili con il motore di rendering Chromium e usa il motore TRIDENT MSHTML di Internet Explorer 11 (IE11) per i siti che non sono o hanno dipendenze dalla funzionalità di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b32fb-163">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> <span data-ttu-id="b32fb-164">[Altre informazioni] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="b32fb-164">[Learn more] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span></span> 

<span data-ttu-id="b32fb-165">Microsoft Managed Desktop abilita la modalità Internet Explorer per i dispositivi per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b32fb-165">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="b32fb-166">Integrazione della modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b32fb-166">Internet Explorer mode integration</span></span>
<span data-ttu-id="b32fb-167">**Valore predefinito:** Modalità Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b32fb-167">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="b32fb-168">Per impostazione predefinita, i dispositivi sono impostati per l'uso della modalità Internet Explorer, ma puoi impostarli per aprire i siti in una finestra autonoma di Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="b32fb-168">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="b32fb-169">Per modificare questo comportamento, stenta una richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="b32fb-169">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="b32fb-170">Aggiungere siti all'elenco dei siti per la modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="b32fb-170">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="b32fb-171">Per l'apertura dei siti in modalità Internet Explorer, è necessario includerli [nell'elenco Dei siti aziendali.](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist)</span><span class="sxs-lookup"><span data-stu-id="b32fb-171">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="b32fb-172">La gestione e la distribuzione dell'elenco di siti aziendali sono di responsabilità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b32fb-172">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="b32fb-173">Per informazioni dettagliate, vedere [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="b32fb-173">For details, see [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="b32fb-174">Altre impostazioni</span><span class="sxs-lookup"><span data-stu-id="b32fb-174">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="b32fb-175">Abilitare l'isolamento del sito per ogni sito</span><span class="sxs-lookup"><span data-stu-id="b32fb-175">Enable site isolation for every site</span></span>

<span data-ttu-id="b32fb-176">**Valore predefinito:** Abilitato</span><span class="sxs-lookup"><span data-stu-id="b32fb-176">**Default value:** Enabled</span></span>

<span data-ttu-id="b32fb-177">Quando questo criterio è abilitato, gli utenti non possono rifiutare esplicitamente il comportamento predefinito in cui ogni sito viene eseguito nel proprio processo.</span><span class="sxs-lookup"><span data-stu-id="b32fb-177">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="b32fb-178">Schemi di autenticazione supportati</span><span class="sxs-lookup"><span data-stu-id="b32fb-178">Supported authentication schemes</span></span>

<span data-ttu-id="b32fb-179">**Valore predefinito:** NTLM, Negotiate</span><span class="sxs-lookup"><span data-stu-id="b32fb-179">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="b32fb-180">Microsoft Managed Desktop non supporta gli schemi di autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="b32fb-180">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="b32fb-181">Importare automaticamente i dati e le impostazioni di un altro browser alla prima esecuzione</span><span class="sxs-lookup"><span data-stu-id="b32fb-181">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="b32fb-182">**Valore predefinito:** Importa automaticamente tutti i tipi di dati e le impostazioni supportati dal browser predefinito</span><span class="sxs-lookup"><span data-stu-id="b32fb-182">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="b32fb-183">Con questo criterio applicato, la first-run experience ignora la sezione di importazione, riducendo al minimo l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b32fb-183">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="b32fb-184">I dati del browser delle versioni precedenti di Microsoft Edge verranno sempre migrati automaticamente alla prima esecuzione, indipendentemente da questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="b32fb-184">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="b32fb-185">Impostazioni gestite</span><span class="sxs-lookup"><span data-stu-id="b32fb-185">Settings you manage</span></span>

<span data-ttu-id="b32fb-186">Puoi distribuire qualsiasi impostazione di Microsoft Edge non descritta in precedenza usando il profilo Modelli amministrativi in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b32fb-186">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="b32fb-187">Per informazioni dettagliate, vedere [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune)</span><span class="sxs-lookup"><span data-stu-id="b32fb-187">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="b32fb-188">Se vuoi valutare un criterio attualmente non incluso nei modelli amministrativi di Microsoft Edge in Intune, puoi usare impostazioni personalizzate per i dispositivi Windows 10 in Intune.</span><span class="sxs-lookup"><span data-stu-id="b32fb-188">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="b32fb-189">Abilitazione di estensioni di Chrome specifiche</span><span class="sxs-lookup"><span data-stu-id="b32fb-189">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="b32fb-190">Il modello amministrativo offre un'impostazione per distribuire specifiche estensioni di Chrome con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b32fb-190">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="b32fb-191">È possibile trovarlo in Configurazione computer > Microsoft Edge > Estensioni > consenti l'installazione **di estensioni specifiche.**</span><span class="sxs-lookup"><span data-stu-id="b32fb-191">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="b32fb-192">Installare le estensioni in modo invisibile all'utente</span><span class="sxs-lookup"><span data-stu-id="b32fb-192">Install extensions silently</span></span>

<span data-ttu-id="b32fb-193">Puoi anche usare il modello amministrativo per impostare Microsoft Edge in modo che installi le estensioni senza avvisare l'utente.</span><span class="sxs-lookup"><span data-stu-id="b32fb-193">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="b32fb-194">È possibile trovarlo in Configurazione computer > Microsoft Edge > estensioni > controllare quali estensioni vengono installate in **modo invisibile all'utente.**</span><span class="sxs-lookup"><span data-stu-id="b32fb-194">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="b32fb-195">Criteri di aggiornamento di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b32fb-195">Microsoft Edge update policies</span></span>
<span data-ttu-id="b32fb-196">Per assicurarsi che Microsoft Edge venga aggiornato correttamente, non modificare i criteri di aggiornamento [di](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="b32fb-196">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="b32fb-197">Altri criteri aziendali comuni</span><span class="sxs-lookup"><span data-stu-id="b32fb-197">Other common enterprise policies</span></span>

<span data-ttu-id="b32fb-198">Microsoft Edge offre molti altri criteri.</span><span class="sxs-lookup"><span data-stu-id="b32fb-198">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="b32fb-199">Di seguito sono riportati alcuni dei più comuni:</span><span class="sxs-lookup"><span data-stu-id="b32fb-199">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="b32fb-200">Configurare i siti nell'elenco di siti enterprise e nella modalità IE</span><span class="sxs-lookup"><span data-stu-id="b32fb-200">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="b32fb-201">Configurare le impostazioni di avvio, home page e pagina nuova scheda</span><span class="sxs-lookup"><span data-stu-id="b32fb-201">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="b32fb-202">Configurare l'impostazione del gioco Surf</span><span class="sxs-lookup"><span data-stu-id="b32fb-202">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="b32fb-203">Configurare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="b32fb-203">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

