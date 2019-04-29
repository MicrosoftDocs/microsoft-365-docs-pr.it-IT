<a name="crit-windows10-step1"></a>
### <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="5b9ef-101">Obbligatorio: i domini Microsoft 365 sono stati aggiunti e verificati</span><span class="sxs-lookup"><span data-stu-id="5b9ef-101">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="5b9ef-102">Il tenant di Azure AD per le sottoscrizioni di Office 365 e Intune è configurato con i nomi di dominio Internet (come contoso.com), anziché con un solo nome di dominio che include "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="5b9ef-102">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="5b9ef-p101">Se non si esegue questa operazione, l'utente sarà limitato nei metodi di autenticazione che è possibile configurare. Ad esempio, l'autenticazione pass-through e federata non può utilizzare il nome di dominio "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="5b9ef-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="5b9ef-105">Se necessario, il [Passaggio 1](../windows10-prepare-your-org.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-105">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this requirement.</span></span>

### <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="5b9ef-106">Facoltativo: gli utenti vengono aggiunti e ricevono una licenza</span><span class="sxs-lookup"><span data-stu-id="5b9ef-106">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="5b9ef-107">Gli account corrispondenti agli utenti vengono aggiunti direttamente al tenant di Azure AD per le sottoscrizioni di Office 365 e Intune o dalla sincronizzazione delle directory da Active Directory Domain Services locale.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-107">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="5b9ef-108">Una volta aggiunti gli utenti, è possibile assegnare loro le licenze Microsoft 365 Enterprise, direttamente come amministratore globale o utente o automaticamente tramite l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-108">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="5b9ef-109">Se necessario, il [Passaggio 1](../windows10-prepare-your-org.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-109">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this option.</span></span>

### <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="5b9ef-110">Facoltativo: Diagnostica è abilitata</span><span class="sxs-lookup"><span data-stu-id="5b9ef-110">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="5b9ef-111">Le impostazioni dei dati di diagnostica sono state abilitate tramite Criteri di gruppo, Microsoft Intune, l'editor del Registro di sistema o al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-111">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="5b9ef-112">Se necessario, il [Passaggio 1](../windows10-prepare-your-org.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-112">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
### <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="5b9ef-113">Obbligatorio per l'aggiornamento sul posto: creata una sequenza di attività di Gestione configurazione per una distribuzione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="5b9ef-113">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="5b9ef-114">Per avviare una sequenza di attività di Gestione configurazione per eseguire un aggiornamento sul posto di un dispositivo con Windows 7 o Windows 8.1, è necessario:</span><span class="sxs-lookup"><span data-stu-id="5b9ef-114">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="5b9ef-115">Impostare il corretto livello dei dati di diagnostica di Windows</span><span class="sxs-lookup"><span data-stu-id="5b9ef-115">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="5b9ef-116">È stata verificata la disponibilità a eseguire l'aggiornamento di Windows</span><span class="sxs-lookup"><span data-stu-id="5b9ef-116">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="5b9ef-117">È stata creata una sequenza di attività di Gestione configurazione che include una raccolta di dispositivi e una distribuzione del sistema operativo con un'immagine del sistema operativo Windows 10</span><span class="sxs-lookup"><span data-stu-id="5b9ef-117">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="5b9ef-p102">Dopo questa operazione, è possibile eseguire aggiornamenti sul posto su dispositivi pronti per aggiornare Windows. Per trarre il massimo vantaggio da Microsoft 365 Enterprise, aggiornare il maggior numero possibile di dispositivi con Windows 7 e Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="5b9ef-p103">Ogni dispositivo che esegue Windows 10 Enterprise può ottenere i vantaggi della soluzione integrata di Microsoft 365 Enterprise. I restanti dispositivi che eseguono Windows 7 o Windows 8.1 non possono utilizzare le tecnologie connesse al cloud e le funzionalità di sicurezza avanzate di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="5b9ef-122">Se necessario, il [Passaggio 2](../windows10-deploy-inplaceupgrade.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-122">If needed, [Step 2](../windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
### <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="5b9ef-123">Obbligatorio per i nuovi dispositivi: Windows Autopilot configurato</span><span class="sxs-lookup"><span data-stu-id="5b9ef-123">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="5b9ef-124">Per utilizzare Windows Autopilot per distribuire e personalizzare Windows 10 Enterprise su un nuovo dispositivo, è necessario:</span><span class="sxs-lookup"><span data-stu-id="5b9ef-124">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="5b9ef-125">È stato configurato il corretto livello dei dati di diagnostica di Windows</span><span class="sxs-lookup"><span data-stu-id="5b9ef-125">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="5b9ef-126">Sono stati configurati i prerequisiti per Windows Autopilot, che includono:</span><span class="sxs-lookup"><span data-stu-id="5b9ef-126">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="5b9ef-127">Registrazione del dispositivo e personalizzazione Configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="5b9ef-127">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="5b9ef-128">Informazioni personalizzate distintive dell'azienda per Configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="5b9ef-128">Company branding for OOBE</span></span>
   - <span data-ttu-id="5b9ef-129">Registrazione automatica MDM in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5b9ef-129">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="5b9ef-130">Connettività di rete ai servizi cloud utilizzati da Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="5b9ef-130">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="5b9ef-131">Dispositivi preinstallati con Windows 10, versione 1703 o successive</span><span class="sxs-lookup"><span data-stu-id="5b9ef-131">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="5b9ef-132">Selezionare il programma Windows Autopilot Deployment per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="5b9ef-132">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="5b9ef-133">Una volta eseguita la configurazione di Windows Autopilot, è possibile utilizzarla per configurare e personalizzare Windows 10 Enterprise per la configurazione guidata (OOBE) di:</span><span class="sxs-lookup"><span data-stu-id="5b9ef-133">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="5b9ef-134">Nuovi dispositivi</span><span class="sxs-lookup"><span data-stu-id="5b9ef-134">New devices</span></span>
- <span data-ttu-id="5b9ef-135">Dispositivi per i quali è stata già completata una configurazione guidata nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-135">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="5b9ef-136">Windows Autopilot configura il dispositivo e lo collega ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-136">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="5b9ef-137">In mancanza di Windows Autopilot, è necessario configurare manualmente nuovi dispositivi, inclusa la connessione ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-137">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="5b9ef-138">Se necessario, il [Passaggio 3](../windows10-deploy-autopilot.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-138">If needed, [Step 3](../windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
### <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="5b9ef-139">Facoltativo: utilizzo di Integrità del dispositivo di Windows Analytics per monitorare i dispositivi basati su Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5b9ef-139">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="5b9ef-p104">Le informazioni sono state utilizzate in Monitoraggio dell'integrità dei dispositivi con Integrità del dispositivo per rilevare e risolvere i problemi che interessano gli utenti finali. Affrontare in modo rapido i problemi degli utenti finali può ridurre i costi di assistenza e dimostrare agli utenti l'impegno IT per Windows 10 Enterprise, che può aiutare l'adozione in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="5b9ef-142">Se necessario, il [Passaggio 4](../windows10-enable-windows-analytics.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-142">If needed, [Step 4](../windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
### <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="5b9ef-143">Obbligatorio: utilizzo di Windows Defender Antivirus o la propria soluzione antimalware</span><span class="sxs-lookup"><span data-stu-id="5b9ef-143">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="5b9ef-p105">Windows Defender Antivirus o la propria soluzione antivirus sono stati distribuiti per proteggere i dispositivi che eseguono Windows 10 Enterprise da software dannoso. Se è stato distribuito Windows Defender Antivirus, è stato implementato un metodo di segnalazione, come System Center Configuration Manager o Microsoft Intune, per monitorare eventi e attività antivirus.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="5b9ef-146">Se necessario, il [Passaggio 5](../windows10-enable-security-features.md#windows10-sec-av) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-146">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
### <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="5b9ef-147">Obbligatorio: utilizzo di Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="5b9ef-147">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="5b9ef-148">Windows Defender Exploit Guard è stato distribuito per proteggere i dispositivi che eseguono Windows 10 Enterprise da intrusioni ed è stato implementato un metodo di segnalazione, come System Center Configuration Manager o Microsoft Intune, per monitorare eventi e attività di intrusione.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-148">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="5b9ef-149">Se necessario, il [Passaggio 5](../windows10-enable-security-features.md#windows10-sec-eg) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-149">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
### <a name="required-you-are-using-windows-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="5b9ef-150">Obbligatorio: utilizzo di Windows Defender Advanced Threat Protection (solo Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="5b9ef-150">Required: You are using Windows Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="5b9ef-151">Windows Defender Advanced Threat Protection Defender (ATP) è stato distribuito per rilevare, investigare e rispondere alle minacce avanzate contro la rete e i dispositivi che eseguono Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-151">You deployed Windows Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="5b9ef-152">Opzionalmente, Windows Defender ATP viene integrato con altri strumenti per espandere le proprie capacità.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-152">Optionally, you have integrated Windows Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="5b9ef-153">Se necessario, il [Passaggio 5](../windows10-enable-security-features.md#windows10-sec-atp) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="5b9ef-153">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>
