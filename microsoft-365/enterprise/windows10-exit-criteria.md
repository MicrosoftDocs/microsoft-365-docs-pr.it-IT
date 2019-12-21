---
title: "Fase 3: criteri uscita dell'infrastruttura Windows 10 Enterprise"
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise per Windows 10 Enterprise.
ms.openlocfilehash: d51392572c78edb1a21f5edc3229057b9af3f514
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801221"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="8dcb1-103">Fase 3: criteri uscita dell'infrastruttura Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8dcb1-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="8dcb1-105">Verificare che l'infrastruttura di Windows 10 Enterprise soddisfi i criteri obbligatori seguenti e assicurarsi di tenere in considerazione quelli facoltativi.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-105">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="8dcb1-106">Obbligatorio: i domini Microsoft 365 sono stati aggiunti e verificati</span><span class="sxs-lookup"><span data-stu-id="8dcb1-106">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="8dcb1-107">Il tenant di Azure AD per le sottoscrizioni di Office 365 e Intune è configurato con i nomi di dominio Internet (come contoso.com), anziché con un solo nome di dominio che include "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="8dcb1-107">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="8dcb1-p101">Se non si esegue questa operazione, l'utente sarà limitato nei metodi di autenticazione che è possibile configurare. Ad esempio, l'autenticazione pass-through e federata non può utilizzare il nome di dominio "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="8dcb1-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="8dcb1-110">Se necessario, il [Passaggio 1](windows10-prepare-your-org.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-110">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="8dcb1-111">Facoltativo: gli utenti vengono aggiunti e ricevono una licenza</span><span class="sxs-lookup"><span data-stu-id="8dcb1-111">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="8dcb1-112">Gli account corrispondenti agli utenti vengono aggiunti direttamente al tenant di Azure AD per gli abbonamenti di Office 365 e Intune o dalla sincronizzazione delle directory da Active Directory Domain Services locale.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-112">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="8dcb1-113">Una volta aggiunti gli utenti, è possibile assegnare loro le licenze Microsoft 365 Enterprise, direttamente come amministratore globale o utente o automaticamente tramite l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-113">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="8dcb1-114">Se necessario, il [Passaggio 1](windows10-prepare-your-org.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-114">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="8dcb1-115">Facoltativo: Diagnostica è abilitata</span><span class="sxs-lookup"><span data-stu-id="8dcb1-115">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="8dcb1-116">Le impostazioni dei dati di diagnostica sono state abilitate tramite Criteri di gruppo, Microsoft Intune, l'editor del Registro di sistema o al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-116">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="8dcb1-117">Se necessario, il [Passaggio 1](windows10-prepare-your-org.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-117">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="8dcb1-118">Obbligatorio per l'aggiornamento sul posto: creata una sequenza di attività di Gestione configurazione per una distribuzione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8dcb1-118">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="8dcb1-119">Per avviare una sequenza di attività di Gestione configurazione per eseguire un aggiornamento sul posto di un dispositivo con Windows 7 o Windows 8.1, è necessario:</span><span class="sxs-lookup"><span data-stu-id="8dcb1-119">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="8dcb1-120">Impostare il corretto livello dei dati di diagnostica di Windows</span><span class="sxs-lookup"><span data-stu-id="8dcb1-120">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="8dcb1-121">È stata verificata la disponibilità a eseguire l'aggiornamento di Windows</span><span class="sxs-lookup"><span data-stu-id="8dcb1-121">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="8dcb1-122">È stata creata una sequenza di attività di Gestione configurazione che include una raccolta di dispositivi e una distribuzione del sistema operativo con un'immagine del sistema operativo Windows 10</span><span class="sxs-lookup"><span data-stu-id="8dcb1-122">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="8dcb1-p102">Dopo questa operazione, è possibile eseguire aggiornamenti sul posto su dispositivi pronti per aggiornare Windows. Per trarre il massimo vantaggio da Microsoft 365 Enterprise, aggiornare il maggior numero possibile di dispositivi con Windows 7 e Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="8dcb1-p103">Ogni dispositivo che esegue Windows 10 Enterprise può ottenere i vantaggi della soluzione integrata di Microsoft 365 Enterprise. I restanti dispositivi che eseguono Windows 7 o Windows 8.1 non possono utilizzare le tecnologie connesse al cloud e le funzionalità di sicurezza avanzate di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="8dcb1-127">Se necessario, il [Passaggio 2](windows10-deploy-inplaceupgrade.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-127">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="8dcb1-128">Obbligatorio per i nuovi dispositivi: Windows Autopilot configurato</span><span class="sxs-lookup"><span data-stu-id="8dcb1-128">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="8dcb1-129">Per utilizzare Windows Autopilot per distribuire e personalizzare Windows 10 Enterprise su un nuovo dispositivo, è necessario:</span><span class="sxs-lookup"><span data-stu-id="8dcb1-129">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="8dcb1-130">È stato configurato il corretto livello dei dati di diagnostica di Windows</span><span class="sxs-lookup"><span data-stu-id="8dcb1-130">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="8dcb1-131">Sono stati configurati i prerequisiti per Windows Autopilot, che includono:</span><span class="sxs-lookup"><span data-stu-id="8dcb1-131">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="8dcb1-132">Registrazione del dispositivo e personalizzazione Configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="8dcb1-132">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="8dcb1-133">Informazioni personalizzate distintive dell'azienda per Configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="8dcb1-133">Company branding for OOBE</span></span>
   - <span data-ttu-id="8dcb1-134">Registrazione automatica MDM in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8dcb1-134">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="8dcb1-135">Connettività di rete ai servizi cloud utilizzati da Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="8dcb1-135">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="8dcb1-136">Dispositivi preinstallati con Windows 10, versione 1703 o successive</span><span class="sxs-lookup"><span data-stu-id="8dcb1-136">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="8dcb1-137">Selezionare il programma Windows Autopilot Deployment per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="8dcb1-137">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="8dcb1-138">Una volta eseguita la configurazione di Windows Autopilot, è possibile utilizzarla per configurare e personalizzare Windows 10 Enterprise per la configurazione guidata (OOBE) di:</span><span class="sxs-lookup"><span data-stu-id="8dcb1-138">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="8dcb1-139">Nuovi dispositivi</span><span class="sxs-lookup"><span data-stu-id="8dcb1-139">New devices</span></span>
- <span data-ttu-id="8dcb1-140">Dispositivi per i quali è stata già completata una configurazione guidata nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-140">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="8dcb1-141">Windows Autopilot configura il dispositivo e lo collega ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-141">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="8dcb1-142">In mancanza di Windows Autopilot, è necessario configurare manualmente nuovi dispositivi, inclusa la connessione ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-142">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="8dcb1-143">Se necessario, il [Passaggio 3](windows10-deploy-autopilot.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-143">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="8dcb1-144">Facoltativo: utilizzo di Integrità del dispositivo di Windows Analytics per monitorare i dispositivi basati su Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8dcb1-144">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="8dcb1-p104">Le informazioni sono state utilizzate in Monitoraggio dell'integrità dei dispositivi con Integrità del dispositivo per rilevare e risolvere i problemi che interessano gli utenti finali. Affrontare in modo rapido i problemi degli utenti finali può ridurre i costi di assistenza e dimostrare agli utenti l'impegno IT per Windows 10 Enterprise, che può aiutare l'adozione in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="8dcb1-147">Se necessario, il [Passaggio 4](windows10-enable-windows-analytics.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-147">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="8dcb1-148">Obbligatorio: utilizzo di Windows Defender Antivirus o la propria soluzione antimalware</span><span class="sxs-lookup"><span data-stu-id="8dcb1-148">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="8dcb1-p105">Windows Defender Antivirus o la propria soluzione antivirus sono stati distribuiti per proteggere i dispositivi che eseguono Windows 10 Enterprise da software dannoso. Se è stato distribuito Windows Defender Antivirus, è stato implementato un metodo di segnalazione, come Microsoft Endpoint Configuration Manager o Microsoft Intune, per monitorare eventi e attività antivirus.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as Microsoft Endpoint Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="8dcb1-151">Se necessario, il [Passaggio 5](windows10-enable-security-features.md#windows10-sec-av) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-151">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="8dcb1-152">Obbligatorio: utilizzo di Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="8dcb1-152">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="8dcb1-153">Windows Defender Exploit Guard è stato distribuito per proteggere i dispositivi che eseguono Windows 10 Enterprise da intrusioni ed è stato implementato un metodo di segnalazione, come Configuration Manager o Microsoft Intune, per monitorare eventi e attività di intrusione.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-153">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="8dcb1-154">Se necessario, il [Passaggio 5](windows10-enable-security-features.md#windows10-sec-eg) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-154">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a><span data-ttu-id="8dcb1-155">Obbligatorio: utilizzo di Microsoft Defender Advanced Threat Protection (solo Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="8dcb1-155">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="8dcb1-156">Microsoft Defender Advanced Threat Protection Defender (ATP) è stato distribuito per rilevare, investigare e rispondere alle minacce avanzate contro la rete e i dispositivi che eseguono Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-156">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="8dcb1-157">In modo facoltativo, Microsoft Defender ATP viene integrato con altri strumenti per espandere le proprie capacità.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-157">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="8dcb1-158">Se necessario, il [Passaggio 5](windows10-enable-security-features.md#windows10-sec-atp) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-158">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="8dcb1-159">Risultati e passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8dcb1-159">Results and next steps</span></span>

<span data-ttu-id="8dcb1-160">L'infrastruttura di Windows 10 Enterprise è pronta per iniziare l'installazione in nuovi dispositivi e aggiornamenti sul posto in dispositivi con versioni precedenti di Windows e si stanno usando le principali funzionalità di sicurezza di Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8dcb1-160">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![Fase 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="8dcb1-162">Se si stanno seguendo le fasi della distribuzione end-to-end di Microsoft 365 Enterprise, la fase successiva è [Office 365 ProPlus](office365proplus-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="8dcb1-162">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
