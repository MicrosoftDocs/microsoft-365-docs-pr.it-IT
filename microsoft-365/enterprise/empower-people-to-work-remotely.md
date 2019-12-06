---
title: Supportare i lavoratori remoti
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Configurare l'infrastruttura e le funzionalità di sicurezza necessarie per consentire ai dipendenti di lavorare in remoto ovunque e in qualsiasi momento.
ms.openlocfilehash: 2544820b577b81062550a8c0a84513f2a8c28668
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831967"
---
# <a name="empower-remote-workers"></a><span data-ttu-id="14b48-103">Supportare i lavoratori remoti</span><span class="sxs-lookup"><span data-stu-id="14b48-103">Empower remote workers</span></span>

<span data-ttu-id="14b48-104">*Questo scenario si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="14b48-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="14b48-105">Per molte organizzazioni, consentire al personale di lavorare facilmente e in sicurezza fuori dall'ufficio è importante, per risparmiare spazio fisico, assumere e trattenere dipendenti che non sono disposti al trasferimento e ridurre il pendolarismo, lasciando così ai dipendenti più tempo per essere produttivi e ridurre lo stress.</span><span class="sxs-lookup"><span data-stu-id="14b48-105">Allowing employees to work away from the office seamlessly and securely is important for many organizations to save on office space, hire and retain employees who are unwilling to relocate, and reduce employee commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="14b48-106">Il telelavoro può abbracciare uno spettro che include:</span><span class="sxs-lookup"><span data-stu-id="14b48-106">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="14b48-107">Dipendenti che sono lontani dall'ufficio solo occasionalmente, per convegni o riunioni con i clienti.</span><span class="sxs-lookup"><span data-stu-id="14b48-107">Employees that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="14b48-108">Alcuni dipendenti che lavorano in remoto a tempo pieno.</span><span class="sxs-lookup"><span data-stu-id="14b48-108">Some employees that work remotely full-time.</span></span>
- <span data-ttu-id="14b48-109">Un'organizzazione completamente remota in cui non ci sono uffici e tutti i dipendenti sono telelavoratori.</span><span class="sxs-lookup"><span data-stu-id="14b48-109">A fully remote organization in which tHere's no office and all employees are remote.</span></span>

<span data-ttu-id="14b48-110">Per supportare il telelavoro, Microsoft 365 Enterprise offre una serie di funzionalità che consentono ai dipendenti di collaborare in modo estremamente semplice da remoto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="14b48-110">To support remote workers, a combination of features in Microsoft 365 Enterprise enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="14b48-111">Riunioni online e sessioni di chat.</span><span class="sxs-lookup"><span data-stu-id="14b48-111">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="14b48-112">Aree di lavoro condivise per l'archiviazione di file basata sul cloud, con accessibilità globale e collaborazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="14b48-112">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="14b48-113">Attività e flussi di lavoro condivisi per dividere il lavoro e portare a termine le attività.</span><span class="sxs-lookup"><span data-stu-id="14b48-113">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="14b48-114">Per la massima sicurezza, Microsoft 365 Enterprise include:</span><span class="sxs-lookup"><span data-stu-id="14b48-114">For strong security, Microsoft 365 Enterprise includes:</span></span>

- <span data-ttu-id="14b48-115">Applicazione di requisiti di autenticazione, con rilevamento e risposta agli accessi ad alto rischio e blocco di app selezionate e dispositivi non conformi.</span><span class="sxs-lookup"><span data-stu-id="14b48-115">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="14b48-116">Connessioni crittografate e risorse digitali nel cloud.</span><span class="sxs-lookup"><span data-stu-id="14b48-116">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="14b48-117">Autorizzazioni per definire le operazioni che possono essere eseguite da ciascun utente sui file.</span><span class="sxs-lookup"><span data-stu-id="14b48-117">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="14b48-118">Prevenzione della perdita dei dati (DLP) per evitare la divulgazione di dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="14b48-118">Data loss prevention (DLP) to prevent leakage of highly regulated data.</span></span>

<span data-ttu-id="14b48-119">Per soddisfare questi criteri per i lavoratori remoti, usare le funzionalità di Microsoft 365 Enterprise seguenti:</span><span class="sxs-lookup"><span data-stu-id="14b48-119">To meet these criteria for remote workers, use the following Microsoft 365 Enterprise features:</span></span>

- <span data-ttu-id="14b48-120">Identità utente e protezione degli accessi</span><span class="sxs-lookup"><span data-stu-id="14b48-120">User identity and sign-in security</span></span>
  - <span data-ttu-id="14b48-121">Account utente di Azure Active Directory (Azure AD) con autenticazione a più fattori (MFA)</span><span class="sxs-lookup"><span data-stu-id="14b48-121">Azure Active Directory (Azure AD) user accounts with multi-factor authentication (MFA)</span></span>
  - <span data-ttu-id="14b48-122">Criteri di accesso condizionale per richiedere l'autenticazione MFA per gli accessi a rischio</span><span class="sxs-lookup"><span data-stu-id="14b48-122">Conditional Access policies to require MFA for risky sign-ins</span></span>
- <span data-ttu-id="14b48-123">Piattaforme di collaborazione</span><span class="sxs-lookup"><span data-stu-id="14b48-123">Collaboration platforms</span></span>
  - <span data-ttu-id="14b48-124">Microsoft Teams, SharePoint e OneDrive, con cui i lavoratori remoti possono programmare e partecipare a riunioni video online e lavorare contemporaneamente agli stessi documenti.</span><span class="sxs-lookup"><span data-stu-id="14b48-124">Microsoft Teams, SharePoint, and OneDrive, with which remote workers can schedule and attend online video-based meetings and work on the same documents at the same time</span></span>
- <span data-ttu-id="14b48-125">Protezione dell'accesso alle risorse</span><span class="sxs-lookup"><span data-stu-id="14b48-125">Secure access to resources</span></span>
  - <span data-ttu-id="14b48-126">Gruppi e autorizzazioni per Teams, siti di SharePoint e OneDrive, in modo che possano accedere solo gli utenti autenticati e consentiti</span><span class="sxs-lookup"><span data-stu-id="14b48-126">Groups and permissions for Teams, SharePoint sites, and OneDrive so that only authenticated and permitted users have access</span></span>
- <span data-ttu-id="14b48-127">Protezione dalla perdita di file</span><span class="sxs-lookup"><span data-stu-id="14b48-127">Protection for leaked files</span></span>
  - <span data-ttu-id="14b48-128">Criteri DLP di Office 365</span><span class="sxs-lookup"><span data-stu-id="14b48-128">Office 365 DLP policies</span></span>
  - <span data-ttu-id="14b48-129">Etichette di riservatezza per la crittografia e autorizzazioni che seguono i file</span><span class="sxs-lookup"><span data-stu-id="14b48-129">Sensitivity labels for encryption and permissions that travel with files</span></span>
- <span data-ttu-id="14b48-130">Sicurezza e gestione dei dispositivi con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="14b48-130">Device management and security with Microsoft Intune</span></span>
  - <span data-ttu-id="14b48-131">Registrazione per i dispositivi gestiti</span><span class="sxs-lookup"><span data-stu-id="14b48-131">Enrollment for managed devices</span></span>
  - <span data-ttu-id="14b48-132">Impostazioni delle app per i dispositivi personali</span><span class="sxs-lookup"><span data-stu-id="14b48-132">App settings for personal devices</span></span>
  - <span data-ttu-id="14b48-133">Criteri per dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="14b48-133">Device and app policies</span></span>
- <span data-ttu-id="14b48-134">App di produttività per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="14b48-134">Productivity apps for devices</span></span>
  - <span data-ttu-id="14b48-135">App di Office 365 ProPlus per esperienze di collaborazione con Teams, SharePoint e OneDrive</span><span class="sxs-lookup"><span data-stu-id="14b48-135">Office 365 ProPlus apps for collaborative experiences with Teams, SharePoint, and OneDrive</span></span> 
- <span data-ttu-id="14b48-136">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="14b48-136">Windows 10 Enterprise</span></span>
  - <span data-ttu-id="14b48-137">Funzionalità di sicurezza complete per la protezione dai cyberattacchi e la prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="14b48-137">Comprehensive security features to protect against cyberattacks and prevent data leakage</span></span>
- <span data-ttu-id="14b48-138">Accesso alle app locali</span><span class="sxs-lookup"><span data-stu-id="14b48-138">Access to on-premises apps</span></span>
  - <span data-ttu-id="14b48-139">Le organizzazioni con identità ibride possono usare Azure AD Application Proxy anziché connessioni di rete privata virtuale (VPN)</span><span class="sxs-lookup"><span data-stu-id="14b48-139">Organizations that have hybrid identity can use Azure AD Application Proxy instead of virtual private network (VPN) connections</span></span>

<span data-ttu-id="14b48-140">Le fasi seguenti illustrano come distribuire le funzionalità di Microsoft 365 Enterprise per l'accesso remoto e incoraggiarne l'adozione da parte dei lavoratori remoti.</span><span class="sxs-lookup"><span data-stu-id="14b48-140">The following phases step you through deploying the feature of Microsoft 365 Enterprise for remote access and driving adoption for remote workers.</span></span> <span data-ttu-id="14b48-141">Se sono già stati distribuiti elementi di queste fasi, assicurarsi che soddisfino i requisiti indicati prima di passare all'elemento successivo.</span><span class="sxs-lookup"><span data-stu-id="14b48-141">If you have already deployed elements of these phases, ensure that they meet the stated requirements before moving on to the next element.</span></span>

<a name="poster"></a> <span data-ttu-id="14b48-142">Per un riepilogo di 1 pagina di questo scenario vedere il [poster Supportare i lavoratori remoti](media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf).</span><span class="sxs-lookup"><span data-stu-id="14b48-142">For a 1-page summary of this scenario, see the [Empower remote workers poster](media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf).</span></span>

<span data-ttu-id="14b48-143">[![Poster Supportare i lavoratori remoti](./media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)</span><span class="sxs-lookup"><span data-stu-id="14b48-143">[![Empower remote workers poster](./media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)</span></span>

<span data-ttu-id="14b48-144">È anche possibile scaricare il poster in formato [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) o [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).</span><span class="sxs-lookup"><span data-stu-id="14b48-144">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="phase-1-deploy-microsoft-365-features-and-capabilities-for-remote-workers"></a><span data-ttu-id="14b48-145">Fase 1: distribuire le caratteristiche e le funzionalità di Microsoft 365 per i lavoratori remoti</span><span class="sxs-lookup"><span data-stu-id="14b48-145">Phase 1: Deploy Microsoft 365 features and capabilities for remote workers</span></span>

<span data-ttu-id="14b48-146">Visti il numero e l'ampiezza delle caratteristiche e delle funzionalità richieste per questo scenario, verranno illustrati gli elementi necessari delle sezioni relative all'infrastruttura di base e ai carichi di lavoro della [Guida alla distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="14b48-146">Because of the breadth and number of features and capabilities required for this scenario, we’ll step you through the required elements of the foundation infrastructure and workloads sections of the [Microsoft 365 Enterprise Deployment Guide](deploy-microsoft-365-enterprise.md).</span></span>

### <a name="step-1-foundation-infrastructure-requirements-for-remote-workers"></a><span data-ttu-id="14b48-147">Passaggio 1: requisiti dell'infrastruttura di base per i lavoratori remoti</span><span class="sxs-lookup"><span data-stu-id="14b48-147">Step 1: Foundation infrastructure requirements for remote workers</span></span>

<span data-ttu-id="14b48-148">In questo passaggio si esamineranno le fasi relative all'[infrastruttura di base](deploy-foundation-infrastructure.md) e verranno elencati gli elementi necessari per abilitare i lavoratori remoti.</span><span class="sxs-lookup"><span data-stu-id="14b48-148">In this step, we’ll visit the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) and list the required elements to enable remote workers.</span></span>

<span data-ttu-id="14b48-149">Per la [Fase 2: identità](identity-infrastructure.md), distribuire quanto segue per l'identità utente e la protezione degli accessi:</span><span class="sxs-lookup"><span data-stu-id="14b48-149">For [Phase 2: Identity](identity-infrastructure.md), deploy the following for user identity and sign-in security:</span></span>

- <span data-ttu-id="14b48-150">Per l'identità ibrida, account utente e gruppi sincronizzati da Active Directory Domain Services (AD DS) locale.</span><span class="sxs-lookup"><span data-stu-id="14b48-150">For hybrid identity, user accounts and groups synchronized from on-premises Active Directory Domain Services (AD DS).</span></span>
- <span data-ttu-id="14b48-151">Per l'assegnazione delle autorizzazioni, gruppi di Azure AD o sincronizzati con i membri appropriati.</span><span class="sxs-lookup"><span data-stu-id="14b48-151">For assigning permissions, synchronized or Azure AD groups with the appropriate members.</span></span>
- <span data-ttu-id="14b48-152">Impostazioni di autenticazione, ad esempio l'obbligo di MFA.</span><span class="sxs-lookup"><span data-stu-id="14b48-152">Authentication settings, such as requiring MFA.</span></span>
- <span data-ttu-id="14b48-153">Criteri di accesso condizionale per richiedere l'autenticazione MFA per gli accessi a rischio e bloccare i client che non supportano l'autenticazione moderna.</span><span class="sxs-lookup"><span data-stu-id="14b48-153">Conditional Access policies to require MFA for risky sign-ins and block clients that don’t support modern authentication.</span></span>

<span data-ttu-id="14b48-154">Ecco la configurazione risultante con gli elementi relativi all'identità evidenziati.</span><span class="sxs-lookup"><span data-stu-id="14b48-154">Here's the resulting configuration with the identity elements highlighted.</span></span>

![Elementi relativi all'identità per i lavoratori remoti](./media/empower-people-to-work-remotely/remote-workers-id-phase.png)
 
<span data-ttu-id="14b48-156">Per la [Fase 3: Windows 10 Enterprise](windows10-infrastructure.md):</span><span class="sxs-lookup"><span data-stu-id="14b48-156">For [Phase 3: Windows 10 Enterprise](windows10-infrastructure.md), deploy:</span></span>

- <span data-ttu-id="14b48-157">Distribuire l'infrastruttura per l'implementazione di nuovi dispositivi con Windows 10 Enterprise e per l'aggiornamento dei dispositivi Windows 7 o Windows 8.1 a Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="14b48-157">The infrastructure to deploy new devices with Windows 10 Enterprise and to upgrade of your Windows 7 or Windows 8.1 devices to Windows 10 Enterprise</span></span>
- <span data-ttu-id="14b48-158">Abilitare funzionalità di sicurezza complete per la protezione delle identità, delle informazioni e contro le minacce</span><span class="sxs-lookup"><span data-stu-id="14b48-158">Enabling comprehensive security features for identity, threat, and information protection</span></span>

<span data-ttu-id="14b48-159">Ecco la configurazione risultante con i dispositivi Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="14b48-159">Here's the resulting configuration with Windows 10 Enterprise devices.</span></span>

![Elementi di Windows 10 Enterprise per i lavoratori remoti](./media/empower-people-to-work-remotely/remote-workers-win10-phase.png)
 
<span data-ttu-id="14b48-161">Per la [Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md), distribuire l'infrastruttura per installare Office 365 ProPlus o aggiornare a Office 365 ProPlus la famiglia di prodotti Office attualmente installata, ad esempio Office 2010 o Office 2013, nei dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14b48-161">For [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md), deploy the infrastructure to install Office 365 ProPlus or upgrade your currently installed Office suite, such as Office 2010 or Office 2013, to Office 365 ProPlus on your organization devices.</span></span> <span data-ttu-id="14b48-162">Questo consentirà di offrire agli utenti la miglior esperienza possibile di sicurezza e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="14b48-162">This will give your users the best security and collaborative experiences.</span></span>

<span data-ttu-id="14b48-163">Ecco la configurazione risultante con Office 365 ProPlus installato nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="14b48-163">Here's the resulting configuration with Office 365 ProPlus installed on devices.</span></span>

![Elementi di Office 365 ProPlus per i lavoratori remoti](./media/empower-people-to-work-remotely/remote-workers-proplus-phase.png)
 
<span data-ttu-id="14b48-165">Per la [Fase 5: gestione dei dispositivi mobili](mobility-infrastructure.md), distribuire la gestione dei dispositivi e delle app di Intune per:</span><span class="sxs-lookup"><span data-stu-id="14b48-165">For [Phase 5: Mobile device management](mobility-infrastructure.md), deploy Intune device and app management for:</span></span>

- <span data-ttu-id="14b48-166">Registrazione dei dispositivi Windows 10 Enterprise, iOS, macOS, Android e Android Enterprise in modo che ricevano impostazioni di sicurezza e funzionalità definite dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14b48-166">Enrollment of your Windows 10 Enterprise, iOS, macOS, Android, and Android Enterprise devices so they receive features and security settings defined by your organization.</span></span>
- <span data-ttu-id="14b48-167">Impostazioni delle app per una maggiore sicurezza e per consentire o bloccare app, anche nei dispositivi personali di proprietà dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="14b48-167">App settings for extra security and to allow or block apps, even on employee-owned personal devices.</span></span>
- <span data-ttu-id="14b48-168">Criteri di conformità con accesso condizionale per impedire la connessione di dispositivi non conformi.</span><span class="sxs-lookup"><span data-stu-id="14b48-168">Compliance policies with Conditional Access to prevent non-compliant devices from connecting.</span></span>

<span data-ttu-id="14b48-169">Ecco la configurazione risultante con i criteri e i dispositivi registrati in Intune evidenziati.</span><span class="sxs-lookup"><span data-stu-id="14b48-169">Here's the resulting configuration with Intune enrolled devices and policies highlighted.</span></span>

![Elementi relativi alla gestione dei dispositivi mobili per i lavoratori remoti](./media/empower-people-to-work-remotely/remote-workers-mdm-phase.png)
 
<span data-ttu-id="14b48-171">Per la [Fase 6: protezione delle informazioni](infoprotect-infrastructure.md), progettare e configurare la protezione per le risorse digitali con:</span><span class="sxs-lookup"><span data-stu-id="14b48-171">For [Phase 6: Information protection](infoprotect-infrastructure.md), design and configure protection for your digital assets with:</span></span>

- <span data-ttu-id="14b48-172">Criteri DLP di Office 365.</span><span class="sxs-lookup"><span data-stu-id="14b48-172">Office 365 DLP policies.</span></span>
- <span data-ttu-id="14b48-173">Etichette di riservatezza di Office 365 per la crittografia e autorizzazioni che seguono i file.</span><span class="sxs-lookup"><span data-stu-id="14b48-173">Office 365 sensitivity labels for encryption and permissions that travel with files.</span></span>

<span data-ttu-id="14b48-174">Ecco la configurazione risultante con i criteri DLP e le etichette di riservatezza evidenziati.</span><span class="sxs-lookup"><span data-stu-id="14b48-174">Here's the resulting configuration with DLP policies and sensitivity labels highlighted.</span></span>

![Elementi relativi alla protezione delle informazioni per i lavoratori remoti](./media/empower-people-to-work-remotely/remote-workers-ip-phase.png)
 
<span data-ttu-id="14b48-176">Per l'accesso alle app locali si può usare [Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy), che richiede un ambiente ibrido di gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="14b48-176">For access to on-premises apps, you can use [Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy), which requires a hybrid identity environment.</span></span>

<span data-ttu-id="14b48-177">Ecco la configurazione risultante con i componenti del proxy di applicazione evidenziati.</span><span class="sxs-lookup"><span data-stu-id="14b48-177">Here's the resulting configuration with the application proxy components highlighted.</span></span>

![Elementi relativi al proxy applicazione per i lavoratori remoti](./media/empower-people-to-work-remotely/remote-workers-app-proxy.png)
 
### <a name="step-2-workloads-for-remote-workers"></a><span data-ttu-id="14b48-179">Passaggio 2: carichi di lavoro per lavoratori remoti</span><span class="sxs-lookup"><span data-stu-id="14b48-179">Step 2: Workloads for remote workers</span></span>

<span data-ttu-id="14b48-180">Per [Exchange Online](exchangeonline-workload.md), distribuire cassette postali di Exchange Online a ogni utente.</span><span class="sxs-lookup"><span data-stu-id="14b48-180">For [Exchange Online](exchangeonline-workload.md), deploy Exchange Online mailboxes to each of your users.</span></span>

<span data-ttu-id="14b48-181">Per [Teams](teams-workload.md), distribuire Teams agli utenti e ai gruppi aziendali.</span><span class="sxs-lookup"><span data-stu-id="14b48-181">For [Teams](teams-workload.md), deploy Teams to your users and groups.</span></span>

<span data-ttu-id="14b48-182">Per [SharePoint e OneDrive](sharepoint-online-onedrive-workload.md), distribuire siti del team o di comunicazione di SharePoint e cartelle di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="14b48-182">For [SharePoint and OneDrive](sharepoint-online-onedrive-workload.md), deploy SharePoint team or communication sites and OneDrive folders.</span></span>

<span data-ttu-id="14b48-183">Ecco la configurazione risultante con i carichi di lavoro evidenziati.</span><span class="sxs-lookup"><span data-stu-id="14b48-183">Here's the resulting configuration with the workloads highlighted.</span></span>

![Carichi di lavoro di Microsoft 365 per lavoratori remoti](./media/empower-people-to-work-remotely/remote-workers-workloads.png)
 
### <a name="deployment-results"></a><span data-ttu-id="14b48-185">Risultati della distribuzione</span><span class="sxs-lookup"><span data-stu-id="14b48-185">Deployment results</span></span>

<span data-ttu-id="14b48-186">A seguito della distribuzione dell'infrastruttura di base e dei carichi di lavoro e dell'implementazione di Windows 10 Enterprise e Office 365 ProPlus, i lavoratori remoti:</span><span class="sxs-lookup"><span data-stu-id="14b48-186">After deploying the foundation infrastructure and workloads and rolling out Windows 10 Enterprise and Office 365 ProPlus, remote workers:</span></span>

- <span data-ttu-id="14b48-187">Sono soggetti a protezione dell'identità e autenticazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="14b48-187">Are subject to strong authentication and identity protection.</span></span>
- <span data-ttu-id="14b48-188">Hanno la versione più recente e sicura di Windows nei propri dispositivi Windows.</span><span class="sxs-lookup"><span data-stu-id="14b48-188">Have the latest and most secure version of Windows on their Windows devices.</span></span>
- <span data-ttu-id="14b48-189">Hanno la versione più recente e più produttiva della famiglia di prodotti Office nei propri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="14b48-189">Have the latest and most productive version of the Office suite on their devices.</span></span>
- <span data-ttu-id="14b48-190">Sono soggetti a criteri di gestione delle app e di conformità dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="14b48-190">Are subject to app management and device compliance policies.</span></span>
- <span data-ttu-id="14b48-191">Sono soggetti a criteri DLP e restrizioni.</span><span class="sxs-lookup"><span data-stu-id="14b48-191">Are subject to DLP policies and restrictions.</span></span>
- <span data-ttu-id="14b48-192">Possono assegnare etichette di riservatezza per la crittografia e autorizzazioni che seguono i file e i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="14b48-192">Can assign sensitivity labels for encryption and permissions that travel with files and email.</span></span>
- <span data-ttu-id="14b48-193">Possono accedere alle app locali senza una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="14b48-193">Can access on-premises apps without a VPN connection.</span></span>
- <span data-ttu-id="14b48-194">Possono svolgere il proprio lavoro e collaborare in tempo reale con i colleghi usando chat, riunioni e file in Teams e file in SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="14b48-194">Can perform their own work and participate in real-time collaboration with co-workers with chats, meetings, and files in Teams and files in SharePoint and OneDrive.</span></span>

<span data-ttu-id="14b48-195">Quando sono offline (non connessi a Internet), i lavoratori remoti possono modificare le copie locali dei file.</span><span class="sxs-lookup"><span data-stu-id="14b48-195">When offline (not connected to the Internet), your remote workers can change local copies of files.</span></span> <span data-ttu-id="14b48-196">Quando si riconnettono a Internet, OneDrive sincronizza le copie locali con i file archiviati nell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14b48-196">When they reconnect to the Internet, OneDrive synchronizes local copies with the files stored in your Microsoft 365 subscription.</span></span> 

<span data-ttu-id="14b48-197">Ecco la configurazione risultante per i lavoratori remoti dell'organizzazione se si usa l'identità ibrida.</span><span class="sxs-lookup"><span data-stu-id="14b48-197">Here's the resulting configuration for remote workers of your organization if you use hybrid identity.</span></span>

![Configurazione finale per un'organizzazione con identità ibrida](./media/empower-people-to-work-remotely/remote-workers-hybrid.png) 
 
<span data-ttu-id="14b48-199">Ecco la configurazione risultante per i lavoratori remoti dell'organizzazione se si usa l'identità solo cloud.</span><span class="sxs-lookup"><span data-stu-id="14b48-199">Here's the resulting configuration for remote workers your organization if you use cloud-only identity.</span></span>

![Configurazione finale per un'organizzazione con identità solo cloud](./media/empower-people-to-work-remotely/remote-workers-cloud-only.png)

## <a name="phase-2-drive-user-adoption-for-remote-workers"></a><span data-ttu-id="14b48-201">Fase 2: incoraggiare l'adozione da parte dei lavoratori remoti</span><span class="sxs-lookup"><span data-stu-id="14b48-201">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="14b48-202">Una volta predisposti l'infrastruttura di base e i carichi di lavoro, è il momento di incoraggiare l'utilizzo continuativo di queste funzionalità da parte dei lavoratori remoti, in modo che possano essere produttivi ovunque e in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="14b48-202">Now that the foundation infrastructure and workloads are in place, it’s time to drive the ongoing usage of these capabilities to your remote workers so they can be productive anywhere and at any time.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="14b48-203">Passaggio 1: formare gli utenti</span><span class="sxs-lookup"><span data-stu-id="14b48-203">Step 1: Train your users</span></span>

<span data-ttu-id="14b48-204">Formare i lavoratori remoti su:</span><span class="sxs-lookup"><span data-stu-id="14b48-204">Train your remote workers on:</span></span>

- <span data-ttu-id="14b48-205">Procedure di accesso appropriate, tra cui registrazione MFA e richiesta di verifica dell'accesso quando viene rilevato un rischio.</span><span class="sxs-lookup"><span data-stu-id="14b48-205">Proper sign-in procedures, including MFA registration, and how sign ins can be challenged when risk is detected.</span></span>
- <span data-ttu-id="14b48-206">Uso dei dispositivi e modo in cui è possibile usare i criteri per bloccare l'accesso per dispositivi non conformi.</span><span class="sxs-lookup"><span data-stu-id="14b48-206">The use of devices and how policies can be used to block access for non-compliant devices.</span></span>
- <span data-ttu-id="14b48-207">Uso delle app consentite e modo in cui è possibile usare i criteri app di Intune per bloccare le app.</span><span class="sxs-lookup"><span data-stu-id="14b48-207">The use of allowed apps and how Intune app polices can be used to block apps.</span></span>
- <span data-ttu-id="14b48-208">Funzionalità di sicurezza di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="14b48-208">Windows 10 Enterprise security features.</span></span>
- <span data-ttu-id="14b48-209">Come usare Outlook per la posta elettronica e la gestione dei calendari.</span><span class="sxs-lookup"><span data-stu-id="14b48-209">How to use Outlook for email and calendaring.</span></span>
- <span data-ttu-id="14b48-210">Come usare [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) per chat, videoconferenze, condivisione di documenti e conversazioni in thread.</span><span class="sxs-lookup"><span data-stu-id="14b48-210">How to use [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) for chat, video-based conferencing, document sharing, and threaded conversations.</span></span>
- <span data-ttu-id="14b48-211">Come usare i siti del team o di comunicazione di SharePoint e le cartelle di OneDrive per esplorare i file nella raccolta di un utente e quelli che appartengono a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="14b48-211">How to use SharePoint team or communication sites and OneDrive folders to browse files in a user's library and those belonging to a group.</span></span>
- <span data-ttu-id="14b48-212">Come usare e applicare etichette di riservatezza per i file che contengono dati sensibili o altamente regolamentati, sia per le versioni locali che per quelle online dei file.</span><span class="sxs-lookup"><span data-stu-id="14b48-212">How to use and apply sensitivity labels for files containing sensitive or highly regulated data, for both local and online versions of files.</span></span>

<span data-ttu-id="14b48-213">Questa formazione dovrebbe includere esercizi pratici in modo che gli utenti possano sperimentare queste funzionalità e i loro risultati.</span><span class="sxs-lookup"><span data-stu-id="14b48-213">This training should include hands-on exercises so that your students can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-worker-feedback"></a><span data-ttu-id="14b48-214">Passaggio 2: effettuare revisioni periodiche dell'utilizzo e rispondere al feedback dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="14b48-214">Step 2: Conduct periodic reviews of usage and address worker feedback</span></span>

<span data-ttu-id="14b48-215">Nelle settimane successive alla formazione:</span><span class="sxs-lookup"><span data-stu-id="14b48-215">In the weeks after training:</span></span>

- <span data-ttu-id="14b48-216">Rispondere rapidamente al feedback dei lavoratori remoti e ottimizzare i criteri e le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="14b48-216">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="14b48-217">Analizzare l'utilizzo di Teams, siti di SharePoint e cartelle di OneDrive e confrontarlo con le aspettative di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="14b48-217">Analyze usage for teams, SharePoint sites, and OneDrive folders and compare it with usage expectations.</span></span>
- <span data-ttu-id="14b48-218">Verificare che i file sensibili o altamente regolamentati siano stati etichettati correttamente con l'etichetta di riservatezza appropriata.</span><span class="sxs-lookup"><span data-stu-id="14b48-218">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="14b48-219">Ripetere la formazione degli utenti se necessario.</span><span class="sxs-lookup"><span data-stu-id="14b48-219">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="14b48-220">Risultati dell'adozione da parte degli utenti</span><span class="sxs-lookup"><span data-stu-id="14b48-220">User adoption results</span></span>

<span data-ttu-id="14b48-221">I lavoratori remoti possono usare i propri dispositivi Windows 10 Enterprise o altri dispositivi e Office 365 ProPlus per accedere a servizi e risorse cloud di Microsoft 365 Enterprise condivisi in un ambiente sicuro, incontrandosi, lavorando e collaborando in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="14b48-221">Your remote workers can use their Windows 10 Enterprise or other devices and Office 365 ProPlus to access and work on shared Microsoft 365 Enterprise cloud services and resources in a secure environment, and they’re meeting, creating, and collaborating in real time.</span></span>

## <a name="see-also"></a><span data-ttu-id="14b48-222">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14b48-222">See also</span></span>

[<span data-ttu-id="14b48-223">Carichi di lavoro e scenari</span><span class="sxs-lookup"><span data-stu-id="14b48-223">Workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="14b48-224">[Raccolta di produttività di Microsoft 365](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="14b48-224">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="14b48-225">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="14b48-225">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
