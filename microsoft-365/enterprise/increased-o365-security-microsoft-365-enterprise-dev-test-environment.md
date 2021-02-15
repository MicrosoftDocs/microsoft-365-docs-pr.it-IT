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
description: Usare questa guida del laboratorio di testing per abilitare ulteriori impostazioni di sicurezza di Microsoft 365 nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847001"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1895c-103">Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="1895c-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1895c-104">*Questa guida del laboratorio di testing può essere usata solo per gli ambienti di testing di Microsoft 365 per le aziende.*</span><span class="sxs-lookup"><span data-stu-id="1895c-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="1895c-105">Con le istruzioni contenute in questo articolo, configurare ulteriori impostazioni di Microsoft 365 per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="1895c-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1895c-107">Fare clic [qui](../downloads/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="1895c-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1895c-108">Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="1895c-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1895c-109">Se si desidera solo configurare una maggiore sicurezza di Microsoft 365 in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base leggera.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="1895c-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1895c-110">Se si desidera configurare una maggiore sicurezza di Microsoft 365 in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="1895c-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1895c-111">Il testing di una maggiore sicurezza di Microsoft 365 non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1895c-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1895c-112">Qui viene fornito come opzione, in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="1895c-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="1895c-113">Fase 2: configurare una maggiore sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1895c-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="1895c-114">In questa fase, si abilita una maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="1895c-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="1895c-115">Per ulteriori dettagli e impostazioni, vedere [Configurare il tenant per una maggiore sicurezza.](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)</span><span class="sxs-lookup"><span data-stu-id="1895c-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="1895c-116">Configurare SharePoint Online per bloccare le app che non supportano l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="1895c-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="1895c-117">Alle app che non supportano l'autenticazione moderna non possono essere applicate configurazioni di identità e accesso ai dispositivi, che è un elemento importante per proteggere l'abbonamento a Microsoft 365 e le relative risorse digitali. [](../security/office-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="1895c-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="1895c-118">Accedere all'interfaccia di amministrazione di Microsoft 365 ( ) e accedere all'abbonamento al laboratorio di testing di [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1895c-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="1895c-119">Se si usa l'ambiente di testing leggero di Microsoft 365, accedere dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="1895c-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="1895c-120">Se si usa l'ambiente di testing di Microsoft 365 aziendale simulato, usare il portale di [Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi accedere da CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="1895c-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="1895c-121">Nella nuova scheda dell'interfaccia di amministrazione di **Microsoft 365,** in **Interfaccia** di amministrazione nel riquadro di spostamento sinistro, fare clic su **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="1895c-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="1895c-122">Nella nuova scheda **dell'interfaccia di amministrazione di SharePoint** fare clic su **Criteri > controllo di accesso.**</span><span class="sxs-lookup"><span data-stu-id="1895c-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="1895c-123">Fare **clic su App che non supportano l'autenticazione moderna,** selezionare Blocca **accesso** e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="1895c-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="1895c-124">Abilitare Defender per Office 365 per SharePoint, OneDrive for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1895c-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="1895c-125">Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams protegge l'organizzazione dalla condivisione accidentale di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="1895c-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="1895c-126">Accedere al [Centro sicurezza & conformità](https://protection.office.com) e accedere con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1895c-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="1895c-127">Nel riquadro di spostamento sinistro, in **Gestione minacce,** fare clic **su Criteri** e quindi su **Allegati sicuri.**</span><span class="sxs-lookup"><span data-stu-id="1895c-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="1895c-128">In **Proteggi file in SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="1895c-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="1895c-129">selezionare **Attiva ATP per SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="1895c-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="1895c-130">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1895c-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="1895c-131">Abilitare l'antimalware</span><span class="sxs-lookup"><span data-stu-id="1895c-131">Enable anti-malware</span></span>

<span data-ttu-id="1895c-132">Il malware è composto da virus e spyware.</span><span class="sxs-lookup"><span data-stu-id="1895c-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="1895c-133">I virus infettano altri programmi e dati e si diffondono nel computer cercando programmi da infettare.</span><span class="sxs-lookup"><span data-stu-id="1895c-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="1895c-134">Il termine spyware indica il malware che raccoglie informazioni personali, quali informazioni di accesso e dati personali, inviandoli all'autore del malware.</span><span class="sxs-lookup"><span data-stu-id="1895c-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="1895c-135">Microsoft 365 include funzionalità di filtro antimalware e posta indesiderata integrate che consentono di proteggere i messaggi in ingresso e in uscita da software dannoso e di proteggersi dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1895c-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="1895c-136">Per ulteriori informazioni, vedere [Protezione antispam & antimalware.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="1895c-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="1895c-137">Per garantire che l'elaborazione antimalware venga eseguita su file con tipi di file allegati comuni:</span><span class="sxs-lookup"><span data-stu-id="1895c-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="1895c-138">Fare clic sul pulsante Indietro nel browser per tornare alla **pagina** Criteri.</span><span class="sxs-lookup"><span data-stu-id="1895c-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="1895c-139">Fare **clic su Antimalware.**</span><span class="sxs-lookup"><span data-stu-id="1895c-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="1895c-140">Fare doppio clic sul criterio denominato **Predefinito.**</span><span class="sxs-lookup"><span data-stu-id="1895c-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="1895c-141">Nella finestra **dei criteri antimalware** fare clic su **Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="1895c-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="1895c-142">In **Common Attachment Types filter** selezionare **On** e quindi fare clic su **Save.**</span><span class="sxs-lookup"><span data-stu-id="1895c-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="1895c-143">Fase 3: esaminare il dashboard di sicurezza</span><span class="sxs-lookup"><span data-stu-id="1895c-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="1895c-144">La gestione delle minacce in Microsoft 365 consente di controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1895c-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="1895c-145">È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti effettuano o meno lo spoofing di account dal dominio.</span><span class="sxs-lookup"><span data-stu-id="1895c-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="1895c-146">Per visualizzare il dashboard di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="1895c-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="1895c-147">Se necessario, accedere al [Centro sicurezza & conformità](https://protection.office.com) e accedere con l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1895c-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="1895c-148">Nel riquadro di spostamento sinistro, in **Gestione minacce,** fare clic su **Dashboard.**</span><span class="sxs-lookup"><span data-stu-id="1895c-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="1895c-149">Esaminare da vicino tutte le schede del dashboard per acquisire familiarità con le informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="1895c-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="1895c-150">Per ulteriori informazioni, vedere [Dashboard di sicurezza.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)</span><span class="sxs-lookup"><span data-stu-id="1895c-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="1895c-151">Fase 4: esaminare Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="1895c-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="1895c-152">Microsoft Secure Score mostra il livello di sicurezza come un numero, che indica il livello corrente rispetto alle funzionalità disponibili nell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1895c-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="1895c-153">Fornisce inoltre un elenco delle azioni di miglioramento che è possibile eseguire per migliorare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="1895c-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="1895c-154">Creare una nuova scheda nel browser e passare al Centro sicurezza [Microsoft 365](https://security.microsoft.com/)e quindi fare clic su **Secure Score.**</span><span class="sxs-lookup"><span data-stu-id="1895c-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="1895c-155">Nella scheda **Panoramica,**  prendere nota del secure score corrente e di come viene confrontato con la media globale e le sottoscrizioni con un numero simile di licenze.</span><span class="sxs-lookup"><span data-stu-id="1895c-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="1895c-156">Nella scheda **Azioni di miglioramento** leggere l'elenco delle azioni che è possibile eseguire per aumentare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="1895c-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="1895c-157">Per ulteriori informazioni, vedere [Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)</span><span class="sxs-lookup"><span data-stu-id="1895c-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1895c-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1895c-158">Next steps</span></span>

<span data-ttu-id="1895c-159">Esplorare le [funzionalità e le funzionalità di](m365-enterprise-test-lab-guides.md#information-protection) protezione delle informazioni aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="1895c-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1895c-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1895c-160">See also</span></span>

[<span data-ttu-id="1895c-161">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="1895c-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1895c-162">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="1895c-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1895c-163">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="1895c-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
