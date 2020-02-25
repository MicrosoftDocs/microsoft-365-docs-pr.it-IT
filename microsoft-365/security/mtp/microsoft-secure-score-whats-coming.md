---
title: Che cosa viene in Microsoft Secure Score?
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, in che modo vengono calcolati i dettagli e quali amministratori della sicurezza possono aspettarsi.
keywords: sicurezza, malware, Microsoft 365, M365, Punteggio sicuro, Centro sicurezza, azioni di miglioramento
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266974"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="77894-104">Che cosa viene in Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="77894-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="77894-105">Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza e migliorare l'usabilità, vengono apportate alcune modifiche nel prossimo futuro.</span><span class="sxs-lookup"><span data-stu-id="77894-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="77894-106">Il Punteggio e il punteggio massimo possono variare.</span><span class="sxs-lookup"><span data-stu-id="77894-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="77894-107">Tuttavia, ciò non implica una modifica della posizione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="77894-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="77894-108">Per informazioni sulle modifiche recenti, vedere [What ' s New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="77894-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="77894-109">2 marzo 2020</span><span class="sxs-lookup"><span data-stu-id="77894-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="77894-110">Rimozione di azioni di miglioramento da Intune</span><span class="sxs-lookup"><span data-stu-id="77894-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="77894-111">Dopo una valutazione delle azioni di miglioramento di Microsoft Secure Score forniti da Intune, è stato deciso che non forniscono una rappresentazione utile della posizione di sicurezza dei dispositivi nelle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="77894-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="77894-112">Invece di concentrarsi sui criteri, stiamo lavorando per portare i controlli di sicurezza che valutano direttamente lo stato di configurazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="77894-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="77894-113">Verranno rimosse le seguenti azioni di miglioramento di Intune:</span><span class="sxs-lookup"><span data-stu-id="77894-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="77894-114">Abilitare la gestione dei dispositivi mobili di Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="77894-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="77894-115">Creare un criterio di conformità di Microsoft Intune per Android</span><span class="sxs-lookup"><span data-stu-id="77894-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="77894-116">Creare un criterio di conformità di Microsoft Intune per Android per il lavoro</span><span class="sxs-lookup"><span data-stu-id="77894-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="77894-117">Creare un criterio di protezione delle app di Microsoft Intune per Android</span><span class="sxs-lookup"><span data-stu-id="77894-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="77894-118">Creare un criterio di protezione delle app di Microsoft Intune per iOS</span><span class="sxs-lookup"><span data-stu-id="77894-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="77894-119">Contrassegnare i dispositivi senza criteri di conformità di Microsoft Intune assegnati come non conformi</span><span class="sxs-lookup"><span data-stu-id="77894-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="77894-120">Creare un criterio di conformità di Microsoft Intune per iOS</span><span class="sxs-lookup"><span data-stu-id="77894-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="77894-121">Creare un criterio di conformità di Microsoft Intune per macOS</span><span class="sxs-lookup"><span data-stu-id="77894-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="77894-122">Creare un criterio di conformità di Microsoft Intune per Windows</span><span class="sxs-lookup"><span data-stu-id="77894-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="77894-123">Creare un profilo di configurazione di Microsoft Intune per Android</span><span class="sxs-lookup"><span data-stu-id="77894-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="77894-124">Creare un profilo di configurazione di Microsoft Intune per Android per il lavoro</span><span class="sxs-lookup"><span data-stu-id="77894-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="77894-125">Creare un profilo di configurazione di Microsoft Intune per macOS</span><span class="sxs-lookup"><span data-stu-id="77894-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="77894-126">Creare un profilo di configurazione di Microsoft Intune per iOS</span><span class="sxs-lookup"><span data-stu-id="77894-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="77894-127">Creare un profilo di configurazione di Microsoft Intune per Windows</span><span class="sxs-lookup"><span data-stu-id="77894-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="77894-128">Abilitare il rilevamento migliorato del jailbreak in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="77894-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="77894-129">Richiedere la correzione di tutti i dispositivi, disporre di antivirus e firewall abilitati</span><span class="sxs-lookup"><span data-stu-id="77894-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="77894-130">Abilitare l'integrazione di Windows Defender ATP in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="77894-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="77894-131">Creare un criterio di protezione delle informazioni di Windows per Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="77894-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="77894-132">Richiedere che tutti i dispositivi dispongano di configurazioni di sicurezza avanzate</span><span class="sxs-lookup"><span data-stu-id="77894-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="77894-133">Rivedere i dispositivi bloccati segnala settimanalmente</span><span class="sxs-lookup"><span data-stu-id="77894-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="77894-134">Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili</span><span class="sxs-lookup"><span data-stu-id="77894-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="77894-135">Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="77894-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="77894-136">Abilitare la registrazione dei dati di controllo</span><span class="sxs-lookup"><span data-stu-id="77894-136">Turn on audit data recording</span></span>
- <span data-ttu-id="77894-137">Individuare le applicazioni IT Shadow a rischio e non conformi</span><span class="sxs-lookup"><span data-stu-id="77894-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="77894-138">Esaminare le autorizzazioni & bloccare le applicazioni OAuth rischiose connesse all'ambiente</span><span class="sxs-lookup"><span data-stu-id="77894-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="77894-139">Configurare il controllo delle versioni nelle raccolte documenti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="77894-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="77894-140">Aggiornamenti dell'azione per il miglioramento dell'AMF</span><span class="sxs-lookup"><span data-stu-id="77894-140">MFA improvement action updates</span></span>

<span data-ttu-id="77894-141">Per riflettere la necessità per le aziende di garantire la massima sicurezza durante l'applicazione di criteri che funzionano con le loro attività, Microsoft Secure Score rimuove tre azioni di miglioramento incentrate sull'autenticazione a più fattori e l'aggiunta di due.</span><span class="sxs-lookup"><span data-stu-id="77894-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="77894-142">I tre che verranno rimossi:</span><span class="sxs-lookup"><span data-stu-id="77894-142">The three that will be removed:</span></span>

- <span data-ttu-id="77894-143">Registrare tutti gli utenti per l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="77894-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="77894-144">Richiedi l'AMF per tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="77894-144">Require MFA for all users</span></span>
- <span data-ttu-id="77894-145">Richiedere l'autenticazione master per i ruoli con privilegi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="77894-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="77894-146">Sono state aggiunte nuove azioni di miglioramento:</span><span class="sxs-lookup"><span data-stu-id="77894-146">New improvement actions added:</span></span>

- <span data-ttu-id="77894-147">Garantire che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro</span><span class="sxs-lookup"><span data-stu-id="77894-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="77894-148">Richiedere l'AMF per i ruoli amministrativi</span><span class="sxs-lookup"><span data-stu-id="77894-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="77894-149">Queste nuove azioni di miglioramento richiedono la registrazione di utenti o amministratori per l'autenticazione a più fattori (AMF) all'interno della directory e la definizione del set di criteri appropriato che soddisfano le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="77894-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="77894-150">L'obiettivo principale è la flessibilità garantendo che tutti gli utenti e gli amministratori siano in grado di eseguire l'autenticazione con più fattori o richieste di verifica dell'identità basata sui rischi.</span><span class="sxs-lookup"><span data-stu-id="77894-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="77894-151">Che può assumere la forma di avere più criteri che applicano decisioni con ambito o impostazione dei valori predefiniti per la sicurezza (a partire dal 16 marzo) che consentono a Microsoft di decidere quando sfidare gli utenti per l'AMF.</span><span class="sxs-lookup"><span data-stu-id="77894-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="77894-152">Rimozione delle azioni di miglioramento "revisione"</span><span class="sxs-lookup"><span data-stu-id="77894-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="77894-153">Uno dei principi del Punteggio sicuro è che il punteggio dovrebbe essere standardizzato e facilmente correlabile.</span><span class="sxs-lookup"><span data-stu-id="77894-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="77894-154">L'utilizzo di azioni di miglioramento non misurabili o utilizzabili ha provocato confusione.</span><span class="sxs-lookup"><span data-stu-id="77894-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="77894-155">Un punteggio sicuro di Microsoft ha senso solo quando ogni suggerimento può avere un effetto chiaro sulla partitura.</span><span class="sxs-lookup"><span data-stu-id="77894-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="77894-156">Esaminare le azioni di miglioramento non vengono misurate allo stesso livello di altre azioni di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="77894-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="77894-157">Per questi motivi, tutte le azioni di miglioramento che richiedono una cadenza di revisione verranno temporaneamente rimosse.</span><span class="sxs-lookup"><span data-stu-id="77894-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="77894-158">Non è necessaria alcuna azione da parte vostra.</span><span class="sxs-lookup"><span data-stu-id="77894-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="77894-159">16 marzo 2020</span><span class="sxs-lookup"><span data-stu-id="77894-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="77894-160">Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili</span><span class="sxs-lookup"><span data-stu-id="77894-160">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="77894-161">Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="77894-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="77894-162">Archiviare i documenti degli utenti in OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="77894-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="77894-163">Impostare i criteri degli allegati sicuri di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="77894-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="77894-164">Configurare i collegamenti sicuri di Office 365 per verificare gli URL</span><span class="sxs-lookup"><span data-stu-id="77894-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="77894-165">Non consentire la delega delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="77894-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="77894-166">Consenti collegamenti di condivisione guest anonimi per siti e documenti</span><span class="sxs-lookup"><span data-stu-id="77894-166">Allow anonymous guest sharing links for sites and docs</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="77894-167">Supporto delle impostazioni predefinite per la sicurezza per le azioni di miglioramento di Azure AD</span><span class="sxs-lookup"><span data-stu-id="77894-167">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="77894-168">Microsoft Secure Score aggiornerà le azioni di miglioramento per supportare le impostazioni predefinite per la [sicurezza di Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), che facilitano la protezione dell'organizzazione con quelle preconfigurate per gli attacchi più comuni.</span><span class="sxs-lookup"><span data-stu-id="77894-168">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="77894-169">Influenzerà le operazioni di miglioramento seguenti:</span><span class="sxs-lookup"><span data-stu-id="77894-169">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="77894-170">Garantire che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro</span><span class="sxs-lookup"><span data-stu-id="77894-170">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="77894-171">Richiedere l'AMF per i ruoli amministrativi</span><span class="sxs-lookup"><span data-stu-id="77894-171">Require MFA for administrative roles</span></span>
- <span data-ttu-id="77894-172">Abilitazione del criterio per bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="77894-172">Enable policy to block legacy authentication</span></span>
