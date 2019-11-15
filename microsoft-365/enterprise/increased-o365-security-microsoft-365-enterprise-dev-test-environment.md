---
title: Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per abilitare altre impostazioni di sicurezza di Microsoft 365 nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: f430acb4a7fd1842a4ae26025ad5a63cccf8392f
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640368"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="579c6-103">Maggiore sicurezza di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="579c6-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="579c6-104">Con le istruzioni riportate in questo articolo, è possibile configurare altre impostazioni di Microsoft 365 per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="579c6-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="579c6-106">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="579c6-106">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="579c6-107">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="579c6-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="579c6-108">Se si desidera configurare una maggiore sicurezza di Microsoft 365 in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="579c6-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="579c6-109">Se si desidera configurare un aumento della sicurezza di Microsoft 365 in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="579c6-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="579c6-110">La verifica dell'aumento della sicurezza di Microsoft 365 non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="579c6-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="579c6-111">Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="579c6-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="579c6-112">Fase 2: configurare un aumento della sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="579c6-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="579c6-113">In questa fase, viene abilitata la sicurezza aumentata di Microsoft 365 per l'ambiente di testing di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="579c6-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="579c6-114">Per ulteriori informazioni e impostazioni, vedere [configurare il tenant di Office 365 per una maggiore sicurezza](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="579c6-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="579c6-115">Configurare SharePoint Online per bloccare le app che non supportano l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="579c6-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="579c6-116">Per le app che non supportano l'autenticazione moderna non è possibile applicare le [configurazioni di identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) , che è un elemento importante della protezione dell'abbonamento a Microsoft 365 e delle risorse digitali.</span><span class="sxs-lookup"><span data-stu-id="579c6-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="579c6-117">Accedere all'interfaccia di amministrazione di Microsoft 365[https://portal.microsoft.com](https://portal.microsoft.com)() e accedere alla sottoscrizione di laboratorio di testing di Office 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="579c6-117">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="579c6-118">Se si utilizza l'ambiente di testing Microsoft 365 Lightweight, accedere dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="579c6-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="579c6-119">Se si utilizza l'ambiente di testing Enterprise Microsoft 365 simulato, utilizzare il [portale di Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi eseguire l'accesso da CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="579c6-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="579c6-120">Nella nuova scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic su interfaccia di **Amministrazione > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="579c6-120">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
3. <span data-ttu-id="579c6-121">Nella nuova scheda dell'interfaccia di **amministrazione di SharePoint** , fare clic su **controllo di accesso**.</span><span class="sxs-lookup"><span data-stu-id="579c6-121">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="579c6-122">In **app che non supportano l'autenticazione moderna**fare clic su **blocca**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="579c6-122">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="579c6-123">Abilitare Advanced Threat Protection per SharePoint, OneDrive for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="579c6-123">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="579c6-124">Office 365 Advanced Threat Protection (ATP) per SharePoint, OneDrive e Microsoft teams protegge l'organizzazione dall'involontaria condivisione di file dannosi.</span><span class="sxs-lookup"><span data-stu-id="579c6-124">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="579c6-125">Accedere al [centro conformità & sicurezza di Office 365](https://protection.office.com) e accedere con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="579c6-125">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="579c6-126">Nel riquadro di spostamento a sinistra, in **gestione delle minacce**, scegliere **criteri > allegati sicuri**.</span><span class="sxs-lookup"><span data-stu-id="579c6-126">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="579c6-127">Selezionare **attiva ATP per SharePoint, OneDrive e Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="579c6-127">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="579c6-128">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="579c6-128">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="579c6-129">Abilitazione anti-malware</span><span class="sxs-lookup"><span data-stu-id="579c6-129">Enable anti-malware</span></span>

<span data-ttu-id="579c6-130">Il malware è composto da virus e spyware.</span><span class="sxs-lookup"><span data-stu-id="579c6-130">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="579c6-131">I virus infettano altri programmi e dati e si diffondono nel computer cercando programmi da infettare.</span><span class="sxs-lookup"><span data-stu-id="579c6-131">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="579c6-132">Il termine spyware indica il malware che raccoglie informazioni personali, quali informazioni di accesso e dati personali, inviandoli all'autore del malware.</span><span class="sxs-lookup"><span data-stu-id="579c6-132">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="579c6-133">Office 365 dispone di funzionalità di filtro antispamming e di protezione da posta indesiderata che consentono di proteggere i messaggi in ingresso e in uscita da software dannoso e di proteggersi dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="579c6-133">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="579c6-134">Per ulteriori informazioni, vedere [anti-spam & anti-malware Protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="579c6-134">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="579c6-135">Per assicurarsi che l'elaborazione antimalware sia in esecuzione su file con tipi di file allegati comuni:</span><span class="sxs-lookup"><span data-stu-id="579c6-135">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="579c6-136">Fare clic sul pulsante indietro nel browser per tornare alla pagina dei **criteri** .</span><span class="sxs-lookup"><span data-stu-id="579c6-136">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="579c6-137">Fare clic su **anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="579c6-137">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="579c6-138">Fare doppio clic sul criterio denominato **default**.</span><span class="sxs-lookup"><span data-stu-id="579c6-138">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="579c6-139">Nella finestra **criteri antimalware** fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="579c6-139">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="579c6-140">In **filtro tipi di allegati comuni**, fare clic **su > Salva**.</span><span class="sxs-lookup"><span data-stu-id="579c6-140">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-the-threat-management-dashboard"></a><span data-ttu-id="579c6-141">Fase 3: esaminare il dashboard di gestione delle minacce</span><span class="sxs-lookup"><span data-stu-id="579c6-141">Phase 3: Examine the threat management dashboard</span></span>

<span data-ttu-id="579c6-142">La gestione delle minacce di Office 365 può essere utile per controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="579c6-142">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="579c6-143">È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti o meno eseguono lo spoofing doloso degli account provenienti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="579c6-143">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="579c6-144">Per ulteriori informazioni, vedere [gestione delle minacce nel centro sicurezza Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="579c6-144">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="579c6-145">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="579c6-145">Next steps</span></span>

<span data-ttu-id="579c6-146">Per informazioni e collegamenti per configurare queste impostazioni in produzione, vedere il passaggio [configurazione maggiore sicurezza per Microsoft 365](infoprotect-configure-increased-security-office-365.md) nella fase di **protezione delle informazioni** .</span><span class="sxs-lookup"><span data-stu-id="579c6-146">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="579c6-147">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="579c6-147">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="579c6-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="579c6-148">See also</span></span>

[<span data-ttu-id="579c6-149">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="579c6-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="579c6-150">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="579c6-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="579c6-151">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="579c6-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

