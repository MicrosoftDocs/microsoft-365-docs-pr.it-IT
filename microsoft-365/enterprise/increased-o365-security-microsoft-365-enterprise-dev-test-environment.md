---
title: Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per abilitare altre impostazioni di sicurezza di Microsoft 365 nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 54e05122dcbe5d4e24f092536897f2a8ad449e05
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283656"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cf3f2-103">Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cf3f2-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cf3f2-104">Con le istruzioni riportate in questo articolo, è possibile configurare altre impostazioni di Microsoft 365 per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="cf3f2-106">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cf3f2-107">Fase 1: creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cf3f2-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cf3f2-108">Se si desidera configurare una maggiore sicurezza di Microsoft 365 in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="cf3f2-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cf3f2-109">Se si desidera configurare un aumento della sicurezza di Microsoft 365 in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cf3f2-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf3f2-110">La verifica dell'aumento della sicurezza di Microsoft 365 non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="cf3f2-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="cf3f2-111">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="cf3f2-112">Fase 2: configurare un aumento della sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf3f2-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="cf3f2-113">In questa fase, viene abilitata la sicurezza aumentata di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="cf3f2-114">Per ulteriori informazioni e impostazioni, vedere [configurare il tenant di Office 365 per una maggiore sicurezza](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="cf3f2-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="cf3f2-115">Configurare SharePoint Online per bloccare le app che non supportano l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="cf3f2-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="cf3f2-116">Per le app che non supportano l'autenticazione moderna non è possibile applicare le [configurazioni di identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) , che è un elemento importante della protezione dell'abbonamento a Microsoft 365 e delle risorse digitali.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="cf3f2-117">Accedere al portale di Office ([https://office.com](https://office.com)) e accedere alla sottoscrizione di valutazione di Office 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="cf3f2-118">Se si utilizza l'ambiente di testing Microsoft 365 Lightweight, accedere dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="cf3f2-119">Se si utilizza l'ambiente di testing Enterprise Microsoft 365 simulato, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi eseguire l'accesso da CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="cf3f2-120">Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** , fare clic su **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="cf3f2-121">Nella nuova scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic su interfaccia di **amministrazione di > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="cf3f2-122">Nella nuova scheda dell'interfaccia di **amministrazione di SharePoint** , fare clic su **controllo di accesso**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="cf3f2-123">In **app che non supportano l'autenticazione moderna**fare clic su **blocca**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="cf3f2-124">Abilitare Advanced Threat Protection per SharePoint, OneDrive for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf3f2-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="cf3f2-125">Office 365 Advanced Threat Protection (ATP) per SharePoint, OneDrive e Microsoft teams protegge l'organizzazione dall'involontaria condivisione di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="cf3f2-126">Accedere al [Centro sicurezza e conformità di Office 365 &](https://protection.office.com) e accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="cf3f2-127">Nel riquadro di spostamento a sinistra, in **gestione delle minacce**, scegliere **criteri > allegati sicuri**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-127">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="cf3f2-128">Selezionare **attiva ATP per SharePoint, OneDrive e Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-128">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="cf3f2-129">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-129">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="cf3f2-130">Abilitazione anti-malware</span><span class="sxs-lookup"><span data-stu-id="cf3f2-130">Enable anti-malware</span></span>

<span data-ttu-id="cf3f2-131">Il malware è composto da virus e spyware.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-131">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="cf3f2-132">I virus infettano altri programmi e dati e si diffondono nel computer cercando programmi da infettare.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-132">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="cf3f2-133">Il termine spyware indica il malware che raccoglie informazioni personali, quali informazioni di accesso e dati personali, inviandoli all'autore del malware.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-133">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="cf3f2-134">Office 365 dispone di funzionalità di filtro antispamming e di protezione da posta indesiderata che consentono di proteggere i messaggi in ingresso e in uscita da software dannoso e di proteggersi dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-134">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="cf3f2-135">Per ulteriori informazioni, vedere [protezione antimalware di _AMP_ anti-spam in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="cf3f2-135">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="cf3f2-136">Per assicurarsi che l'elaborazione antimalware sia in esecuzione su file con tipi di file allegati comuni:</span><span class="sxs-lookup"><span data-stu-id="cf3f2-136">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="cf3f2-137">Fare clic sul pulsante indietro nel browser per tornare alla pagina dei **criteri** .</span><span class="sxs-lookup"><span data-stu-id="cf3f2-137">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="cf3f2-138">Fare clic su **anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-138">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="cf3f2-139">Fare doppio clic sul criterio denominato **default**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-139">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="cf3f2-140">Nella finestra **criteri antimalware** fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-140">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="cf3f2-141">In **filtro tipi di allegati comuni**, fare clic **su > Save**.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-141">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="cf3f2-142">Fase 3: esaminare gli strumenti e i registri di sicurezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="cf3f2-142">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="cf3f2-143">In questa fase, si esaminano i servizi incorporati che informano gli eventi di sicurezza e misurano la posizione di sicurezza generale.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-143">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="cf3f2-144">Dashboard di gestione delle minacce</span><span class="sxs-lookup"><span data-stu-id="cf3f2-144">Threat management dashboard</span></span>

<span data-ttu-id="cf3f2-145">La gestione delle minacce di Office 365 può essere utile per controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-145">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="cf3f2-146">È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti o meno eseguono lo spoofing doloso degli account provenienti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-146">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="cf3f2-147">Per ulteriori informazioni, vedere [gestione delle minacce nel centro sicurezza Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="cf3f2-147">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>


### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="cf3f2-148">Dashboard di sicurezza delle app cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="cf3f2-148">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="cf3f2-149">Office 365 Cloud App Security, in precedenza Office 365 Advanced Security Management, consente di creare criteri che monitorano e segnalano eventuali attività sospette nella sottoscrizione di Office 365, per permettere all'utente di ricercarne le cause e trovare possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-149">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action.</span></span> <span data-ttu-id="cf3f2-150">Per ulteriori informazioni, vedere [Overview of Office 365 cloud app Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="cf3f2-150">For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="cf3f2-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cf3f2-151">Next steps</span></span>

<span data-ttu-id="cf3f2-152">Per informazioni e collegamenti per configurare queste impostazioni in produzione, vedere il passaggio [configurazione maggiore sicurezza per Microsoft 365](infoprotect-configure-increased-security-office-365.md) nella fase di **protezione delle informazioni** .</span><span class="sxs-lookup"><span data-stu-id="cf3f2-152">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="cf3f2-153">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="cf3f2-153">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf3f2-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf3f2-154">See also</span></span>

[<span data-ttu-id="cf3f2-155">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cf3f2-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cf3f2-156">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cf3f2-156">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cf3f2-157">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cf3f2-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

