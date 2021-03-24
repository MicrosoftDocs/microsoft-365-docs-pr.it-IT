---
title: Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Usare questa guida al laboratorio di testing per abilitare ulteriori impostazioni di sicurezza di Microsoft 365 nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 186452396af4227a94a7f6cd0fa0109e9d6a7e17
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051271"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="76c16-103">Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="76c16-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="76c16-104">*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*</span><span class="sxs-lookup"><span data-stu-id="76c16-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="76c16-105">Con le istruzioni contenute in questo articolo, configurare ulteriori impostazioni di Microsoft 365 per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="76c16-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="76c16-107">Fare clic [qui](../downloads/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="76c16-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="76c16-108">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="76c16-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="76c16-109">Se si desidera solo configurare una maggiore sicurezza di Microsoft 365 in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base leggera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="76c16-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="76c16-110">Se si desidera configurare una maggiore sicurezza di Microsoft 365 in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="76c16-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="76c16-111">Il testing di una maggiore sicurezza di Microsoft 365 non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="76c16-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="76c16-112">Viene fornito qui come opzione in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="76c16-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="76c16-113">Fase 2: configurare una maggiore sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76c16-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="76c16-114">In questa fase, si abilita una maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="76c16-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="76c16-115">Per ulteriori dettagli e impostazioni, vedere [Configure your tenant for increased security.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)</span><span class="sxs-lookup"><span data-stu-id="76c16-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="76c16-116">Configurare SharePoint Online per bloccare le app che non supportano l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="76c16-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="76c16-117">Alle app che non supportano l'autenticazione moderna non possono essere applicate configurazioni di identità e accesso ai dispositivi, che è un elemento importante per proteggere l'abbonamento a Microsoft 365 e le relative risorse digitali. [](../security/defender-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="76c16-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="76c16-118">Accedere all'interfaccia di amministrazione di Microsoft 365 ( ) e accedere all'abbonamento al laboratorio di testing di [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="76c16-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="76c16-119">Se si utilizza l'ambiente di testing leggero di Microsoft 365, accedere dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="76c16-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="76c16-120">Se si usa l'ambiente di testing di Microsoft 365 aziendale simulato, usare il portale di [Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi accedere da CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="76c16-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="76c16-121">Nella nuova scheda interfaccia di amministrazione di **Microsoft 365,** in **Interfaccia di** amministrazione nel riquadro di spostamento sinistro fare clic su **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="76c16-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="76c16-122">Nella nuova scheda **interfaccia di amministrazione di SharePoint** fare clic su Criteri > controllo di **accesso**.</span><span class="sxs-lookup"><span data-stu-id="76c16-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="76c16-123">Fare **clic su App che non supportano l'autenticazione moderna,** selezionare Blocca **accesso** e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="76c16-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="76c16-124">Abilitare Defender per Office 365 per SharePoint, OneDrive for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76c16-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="76c16-125">Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams protegge l'organizzazione dalla condivisione accidentale di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="76c16-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="76c16-126">Passare al [Centro sicurezza & conformità](https://protection.office.com) e accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="76c16-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="76c16-127">Nel riquadro di spostamento sinistro, in **Gestione delle minacce,** fare clic **su Criteri** e quindi su **Allegati sicuri.**</span><span class="sxs-lookup"><span data-stu-id="76c16-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="76c16-128">In **Proteggi file in SharePoint, OneDrive e Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="76c16-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="76c16-129">selezionare **Attiva ATP per SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="76c16-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="76c16-130">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="76c16-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="76c16-131">Abilitare l'antimalware</span><span class="sxs-lookup"><span data-stu-id="76c16-131">Enable anti-malware</span></span>

<span data-ttu-id="76c16-132">Il malware è composto da virus e spyware.</span><span class="sxs-lookup"><span data-stu-id="76c16-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="76c16-133">I virus infettano altri programmi e dati e si diffondono nel computer cercando programmi da infettare.</span><span class="sxs-lookup"><span data-stu-id="76c16-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="76c16-134">Il termine spyware indica il malware che raccoglie informazioni personali, quali informazioni di accesso e dati personali, inviandoli all'autore del malware.</span><span class="sxs-lookup"><span data-stu-id="76c16-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="76c16-135">Microsoft 365 include funzionalità di filtro antimalware e posta indesiderata integrate che consentono di proteggere i messaggi in ingresso e in uscita da software dannoso e di proteggerti dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="76c16-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="76c16-136">Per ulteriori informazioni, vedere [Protezione da posta indesiderata & antimalware](../security/defender-365-security/anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="76c16-136">For more information, see [Anti-spam & anti-malware protection](../security/defender-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="76c16-137">Per garantire che l'elaborazione antimalware venga eseguita su file con tipi di file allegati comuni:</span><span class="sxs-lookup"><span data-stu-id="76c16-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="76c16-138">Fai clic sul pulsante Indietro nel browser per tornare alla **pagina** Criteri.</span><span class="sxs-lookup"><span data-stu-id="76c16-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="76c16-139">Fare **clic su Antimalware**.</span><span class="sxs-lookup"><span data-stu-id="76c16-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="76c16-140">Fare doppio clic sul criterio denominato **Default.**</span><span class="sxs-lookup"><span data-stu-id="76c16-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="76c16-141">Nella finestra **Criteri antimalware** fare clic su **Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="76c16-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="76c16-142">In **Filtro tipi di allegati comuni** selezionare **Su** e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="76c16-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="76c16-143">Fase 3: esaminare il dashboard di sicurezza</span><span class="sxs-lookup"><span data-stu-id="76c16-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="76c16-144">La gestione delle minacce in Microsoft 365 consente di controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="76c16-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="76c16-145">È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti stanno effettuando lo spoofing dannoso degli account dal dominio.</span><span class="sxs-lookup"><span data-stu-id="76c16-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="76c16-146">Per visualizzare il dashboard di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="76c16-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="76c16-147">Se necessario, passare al [Centro sicurezza & conformità](https://protection.office.com) e accedere con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="76c16-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="76c16-148">Nel riquadro di spostamento sinistro, in **Gestione delle minacce,** fare clic su **Dashboard.**</span><span class="sxs-lookup"><span data-stu-id="76c16-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="76c16-149">Esaminare da vicino tutte le schede del dashboard per acquisire familiarità con le informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="76c16-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="76c16-150">Per ulteriori informazioni, vedere [Dashboard di sicurezza](../security/defender-365-security/security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="76c16-150">For more information, see [Security Dashboard](../security/defender-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="76c16-151">Fase 4: esaminare Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="76c16-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="76c16-152">Microsoft Secure Score mostra la posizione di sicurezza come un numero, che indica il livello corrente rispetto alle funzionalità disponibili nell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="76c16-153">Fornisce inoltre un elenco delle azioni di miglioramento che è possibile eseguire per migliorare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="76c16-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="76c16-154">Creare una nuova scheda nel browser e passare al Centro sicurezza [Microsoft 365](https://security.microsoft.com/)e quindi fare clic su **Punteggio sicuro.**</span><span class="sxs-lookup"><span data-stu-id="76c16-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="76c16-155">Nella scheda **Panoramica**  annotare il punteggio di protezione corrente e il confronto con la media globale e le sottoscrizioni con un numero simile di licenze.</span><span class="sxs-lookup"><span data-stu-id="76c16-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="76c16-156">Nella scheda **Azioni di miglioramento** leggere l'elenco delle azioni che è possibile eseguire per aumentare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="76c16-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="76c16-157">Per ulteriori informazioni, vedere [Microsoft Secure Score.](../security/defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="76c16-157">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="76c16-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="76c16-158">Next steps</span></span>

<span data-ttu-id="76c16-159">Esplorare ulteriori [funzionalità e funzionalità di](m365-enterprise-test-lab-guides.md#information-protection) protezione delle informazioni nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="76c16-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="76c16-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76c16-160">See also</span></span>

[<span data-ttu-id="76c16-161">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="76c16-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="76c16-162">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="76c16-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="76c16-163">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="76c16-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)