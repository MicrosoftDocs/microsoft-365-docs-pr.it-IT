---
title: Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per l'organizzazione
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
description: Usare questa guida del laboratorio di testing per abilitare altre impostazioni di sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 06273bda00635a65ed9821b2bac23c3a3ee1366a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686803"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="750ef-103">Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="750ef-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="750ef-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="750ef-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="750ef-105">Con le istruzioni riportate in questo articolo, è possibile configurare altre impostazioni di Microsoft 365 per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="750ef-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="750ef-107">Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="750ef-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="750ef-108">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="750ef-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="750ef-109">Se si desidera configurare una maggiore sicurezza di Microsoft 365 in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="750ef-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="750ef-110">Se si desidera configurare un aumento della sicurezza di Microsoft 365 in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="750ef-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="750ef-111">La verifica dell'aumento della sicurezza di Microsoft 365 non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="750ef-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="750ef-112">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="750ef-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="750ef-113">Fase 2: configurare un aumento della sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="750ef-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="750ef-114">In questa fase, viene abilitata l'aumento della sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="750ef-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="750ef-115">Per ulteriori informazioni e impostazioni, vedere [configurare il tenant per una maggiore sicurezza](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="750ef-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="750ef-116">Configurare SharePoint Online per bloccare le app che non supportano l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="750ef-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="750ef-117">Per le app che non supportano l'autenticazione moderna non è possibile applicare le [configurazioni di identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) , che è un elemento importante della protezione dell'abbonamento a Microsoft 365 e delle risorse digitali.</span><span class="sxs-lookup"><span data-stu-id="750ef-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="750ef-118">Accedere all'interfaccia di amministrazione di Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e accedere alla sottoscrizione di laboratorio di testing di microsoft 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="750ef-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="750ef-119">Se si utilizza l'ambiente di testing Microsoft 365 Lightweight, accedere dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="750ef-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="750ef-120">Se si utilizza l'ambiente di testing Enterprise Microsoft 365 simulato, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi eseguire l'accesso da CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="750ef-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="750ef-121">Nella nuova scheda dell'interfaccia di **amministrazione di Microsoft 365** , in interfaccia di **Amministrazione** nel riquadro di spostamento a sinistra, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="750ef-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="750ef-122">Nella nuova scheda dell'interfaccia di **amministrazione di SharePoint** , fare clic su **criteri > controllo di accesso**.</span><span class="sxs-lookup"><span data-stu-id="750ef-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="750ef-123">Fare clic su **app che non supportano l'autenticazione moderna**, selezionare **Blocca accesso**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="750ef-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="750ef-124">Abilitare Advanced Threat Protection per SharePoint, OneDrive for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="750ef-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="750ef-125">Office 365 Advanced Threat Protection (ATP) per SharePoint, OneDrive e Microsoft teams protegge l'organizzazione dall'involontaria condivisione di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="750ef-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="750ef-126">Accedere al [Centro sicurezza & Compliance](https://protection.office.com) e accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="750ef-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="750ef-127">Nel riquadro di spostamento a sinistra, in **gestione minacce**, fare clic su **criteri**, quindi fare clic su **allegati sicuri di ATP**.</span><span class="sxs-lookup"><span data-stu-id="750ef-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="750ef-128">In **proteggere i file in SharePoint, OneDrive e Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="750ef-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="750ef-129">Selezionare **attiva ATP per SharePoint, OneDrive e Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="750ef-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="750ef-130">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="750ef-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="750ef-131">Abilitazione anti-malware</span><span class="sxs-lookup"><span data-stu-id="750ef-131">Enable anti-malware</span></span>

<span data-ttu-id="750ef-132">Il malware è composto da virus e spyware.</span><span class="sxs-lookup"><span data-stu-id="750ef-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="750ef-133">I virus infettano altri programmi e dati e si diffondono nel computer cercando programmi da infettare.</span><span class="sxs-lookup"><span data-stu-id="750ef-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="750ef-134">Il termine spyware indica il malware che raccoglie informazioni personali, quali informazioni di accesso e dati personali, inviandoli all'autore del malware.</span><span class="sxs-lookup"><span data-stu-id="750ef-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="750ef-135">Microsoft 365 dispone di funzionalità di filtro antispamming e di protezione da posta indesiderata che consentono di proteggere i messaggi in ingresso e in uscita da software dannoso e di proteggersi dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="750ef-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="750ef-136">Per ulteriori informazioni, vedere [anti-spam & anti-malware Protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="750ef-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="750ef-137">Per assicurarsi che l'elaborazione antimalware sia in esecuzione su file con tipi di file allegati comuni:</span><span class="sxs-lookup"><span data-stu-id="750ef-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="750ef-138">Fare clic sul pulsante indietro nel browser per tornare alla pagina dei **criteri** .</span><span class="sxs-lookup"><span data-stu-id="750ef-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="750ef-139">Fare clic su **anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="750ef-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="750ef-140">Fare doppio clic sul criterio denominato **default**.</span><span class="sxs-lookup"><span data-stu-id="750ef-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="750ef-141">Nella finestra **criteri antimalware** fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="750ef-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="750ef-142">In **filtro tipi di allegati comuni**selezionare **On**attivato e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="750ef-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="750ef-143">Fase 3: esaminare il dashboard di sicurezza</span><span class="sxs-lookup"><span data-stu-id="750ef-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="750ef-144">La gestione delle minacce in Microsoft 365 può essere utile per controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="750ef-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="750ef-145">È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti o meno eseguono lo spoofing doloso degli account provenienti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="750ef-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="750ef-146">Per visualizzare il dashboard di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="750ef-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="750ef-147">Se necessario, passare al [Centro sicurezza & Compliance](https://protection.office.com) e accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="750ef-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="750ef-148">Nel riquadro di spostamento a sinistra, in **gestione minacce**, fare clic su **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="750ef-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="750ef-149">Esaminare tutte le schede del dashboard per acquisire familiarità con le informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="750ef-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="750ef-150">Per ulteriori informazioni, vedere [Dashboard della sicurezza](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span><span class="sxs-lookup"><span data-stu-id="750ef-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="750ef-151">Fase 4: esaminare il Punteggio sicuro di Microsoft</span><span class="sxs-lookup"><span data-stu-id="750ef-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="750ef-152">Microsoft Secure Score Visualizza la posizione di sicurezza come numero, che indica il livello corrente rispetto alle caratteristiche disponibili nell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="750ef-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="750ef-153">Inoltre, viene fornito un elenco delle azioni di miglioramento che è possibile eseguire per migliorare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="750ef-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="750ef-154">Creare una nuova scheda nel browser e passare al [Centro sicurezza Microsoft 365](https://security.microsoft.com/), quindi fare clic su **Secure Score**.</span><span class="sxs-lookup"><span data-stu-id="750ef-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="750ef-155">Nella scheda **Panoramica**  , prendere nota del Punteggio sicuro corrente e di come viene confrontato con la media globale e con le sottoscrizioni con un numero analogo di licenze.</span><span class="sxs-lookup"><span data-stu-id="750ef-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="750ef-156">Nella scheda **azioni di miglioramento** leggere l'elenco delle azioni che è possibile eseguire per aumentare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="750ef-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="750ef-157">Per ulteriori informazioni, vedere [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="750ef-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="750ef-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="750ef-158">Next steps</span></span>

<span data-ttu-id="750ef-159">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="750ef-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="750ef-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="750ef-160">See also</span></span>

[<span data-ttu-id="750ef-161">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="750ef-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="750ef-162">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="750ef-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="750ef-163">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="750ef-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
