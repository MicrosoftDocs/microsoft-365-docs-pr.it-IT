---
title: Sicurezza aumentata di Office 365 per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida dei laboratori di testing per abilitare ulteriori impostazioni di protezione di Office 365 l'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868546"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a3a14-103">Sicurezza aumentata di Office 365 per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a3a14-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a3a14-104">Con le istruzioni riportate in questo articolo, è configurare impostazioni aggiuntive di Office 365 per aumentare la protezione dell'ambiente di test Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a3a14-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a3a14-106">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a3a14-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a3a14-107">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a3a14-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a3a14-108">Se si desidera configurare aumentare la protezione di Office 365 in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a3a14-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a3a14-109">Se si desidera configurare aumentare la protezione di Office 365 in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a3a14-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3a14-p101">Test aumentare la protezione di Office 365 non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a3a14-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="a3a14-112">Fase 2: Configurare aumentare la protezione di Office 365</span><span class="sxs-lookup"><span data-stu-id="a3a14-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="a3a14-p102">In questa fase si abilita aumentare la protezione di Office 365 per l'ambiente di test Microsoft 365 Enterprise. Per ulteriori informazioni e le impostazioni, vedere [Configure Office 365 tenant per aumentare la protezione](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="a3a14-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="a3a14-115">Configurare SharePoint Online per bloccare le applicazioni che non supportano l'autenticazione moderno</span><span class="sxs-lookup"><span data-stu-id="a3a14-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="a3a14-116">Applicazioni che non supportano l'autenticazione moderno non possono avere [identità e il dispositivo accedere configurazioni](microsoft-365-policies-configurations.md) applicato alle stesse, ovvero un importante elemento di protezione dell'abbonamento Microsoft 365 e le risorse digitali.</span><span class="sxs-lookup"><span data-stu-id="a3a14-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="a3a14-117">Accedere al portale di Office ([https://office.com](https://office.com)) ed eseguire l'accesso alla sottoscrizione di prova di Office 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="a3a14-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="a3a14-118">Se si utilizza l'ambiente di testing Microsoft 365 semplificata, l'accesso dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="a3a14-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="a3a14-119">Se si utilizza l'ambiente di testing simulato aziendale Microsoft 365, utilizzare il [portale Azure](https://portal.azure.com) per connettersi alla macchina virtuale CLIENT1 e quindi effettuare l'accesso da CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="a3a14-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="a3a14-120">Dalla scheda di **interfaccia di amministrazione di Microsoft 365** , fare clic su **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="a3a14-121">Nella nuova scheda di **interfaccia di amministrazione di Microsoft 365** , fare clic su **Admin Center > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="a3a14-122">Nella nuova scheda di **interfaccia di amministrazione di SharePoint** , fare clic su **controllo di accesso**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="a3a14-123">In **applicazioni che non supportano l'autenticazione moderno**, fare clic su **blocco**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="a3a14-124">Abilita avanzate di protezione da minacce) per SharePoint, OneDrive for Business e team di Microsoft</span><span class="sxs-lookup"><span data-stu-id="a3a14-124">Enable Advanced Threat Protection) for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="a3a14-p103">Office 365 avanzate Threat Protection (degli strumenti di analisi) è una funzionalità di Exchange Online Protection (EOP) che consente di mantenere malware fuori la posta elettronica. Con degli strumenti di analisi, creare i criteri nell'interfaccia di amministrazione di Exchange (EAC) o la protezione e accedere a centro conformità per garantire che gli utenti solo collegamenti o allegati nei messaggi di posta elettronica che vengono identificati come non dannoso. Per ulteriori informazioni, vedere [protezione rischio avanzata per gli allegati sicuri e collegamenti sicuri](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="a3a14-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange Admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="a3a14-128">Nella scheda di **interfaccia di amministrazione di Microsoft 365** del browser, fare clic su **Admin Center > sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="a3a14-129">Nella scheda **sicurezza e conformità** nuova, fare clic su **gestione delle minacce > criteri**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="a3a14-130">Fare clic su **allegati sicuri degli strumenti di analisi**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="a3a14-131">Nel riquadro **allegati sicuri** selezionare **attiva degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="a3a14-132">Abilitare anti-malware</span><span class="sxs-lookup"><span data-stu-id="a3a14-132">Enable anti-malware</span></span>

<span data-ttu-id="a3a14-p104">Malware è costituito da virus e spyware. Virus infettare altri programmi e i dati e vengono distribuiti in tutto il computer per programmi infetti. Spyware fa riferimento a malware che raccoglie informazioni personali, ad esempio informazioni di accesso e i dati personali e lo invia all'autore di malware.</span><span class="sxs-lookup"><span data-stu-id="a3a14-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="a3a14-p105">Office 365 dispone di funzionalità di migliorare la protezione dei messaggi in ingresso e in uscita da malware e garantire la protezione da posta indesiderata di filtraggio della posta indesiderata e antimalware incorporata. Per ulteriori informazioni, vedere [protezione antispam e antimalware in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="a3a14-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="a3a14-138">Per verificare che l'elaborazione anti-malware viene eseguita nel file con tipi di file allegato comuni:</span><span class="sxs-lookup"><span data-stu-id="a3a14-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="a3a14-139">Fare clic sul pulsante Indietro nel browser per tornare alla pagina del **criterio** .</span><span class="sxs-lookup"><span data-stu-id="a3a14-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="a3a14-140">Fare clic su **protezione Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="a3a14-141">Fare doppio clic sul criterio denominato **Default**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="a3a14-142">Nella finestra **criteri Anti-malware** , fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="a3a14-143">Nella sezione **filtro comuni tipi di allegati**, fare clic su **in > Salva**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="a3a14-144">Fase 3: Esaminare i registri e gli strumenti di protezione di Office 365</span><span class="sxs-lookup"><span data-stu-id="a3a14-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="a3a14-145">In questa fase è esaminare servizi incorporati informano gli eventi di protezione e misurano le generali di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a3a14-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="a3a14-146">Dashboard di gestione dei rischi</span><span class="sxs-lookup"><span data-stu-id="a3a14-146">Threat management dashboard</span></span>

<span data-ttu-id="a3a14-p106">Gestione di Office 365 rischio consentono di definire e gestire l'accesso dei dispositivi mobili per i dati dell'organizzazione, proteggere l'organizzazione da perdita di dati e migliorare la protezione dei messaggi in ingresso e in uscita da posta indesiderata e malware. È inoltre possibile utilizzare threat management per la protezione di reputazione del dominio e per determinare se i mittenti sono da utenti malintenzionati lo spoofing degli account di dominio. Per ulteriori informazioni, vedere [gestione delle minacce nel centro di conformità e sicurezza di Office 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="a3a14-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="a3a14-150">Utilizzare la procedura seguente per visualizzare il dashboard di Office 365 Threat management:</span><span class="sxs-lookup"><span data-stu-id="a3a14-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="a3a14-151">Nella scheda di **interfaccia di amministrazione di Microsoft 365** del browser, fare clic su **Admin Center > sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="a3a14-152">Nella scheda **sicurezza e conformità** nuova, fare clic su **gestione delle minacce > Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="a3a14-153">Nella scheda nuova **Dashboard** nel browser, nota tendenze malware, sui concetti e altre sezioni del dashboard.</span><span class="sxs-lookup"><span data-stu-id="a3a14-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="a3a14-154">Dashboard di sicurezza App Cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="a3a14-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="a3a14-p107">Protezione di Office 365 Cloud App, in precedenza noto come Office 365 Advanced Security Management, consente di creare i criteri che per monitorare e informano l'utente delle attività potenzialmente dannoso nella sottoscrizione a Office 365, in modo da poter analizzare e richiedere possibili azione di risoluzione dei problemi. Per ulteriori informazioni, vedere [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="a3a14-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="a3a14-157">Nella scheda di **interfaccia di amministrazione di Microsoft 365** del browser, fare clic su **Admin Center > sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="a3a14-158">Nella scheda **sicurezza e conformità** nuova, fare clic su **avvisi > Gestisci avvisi avanzate > passare a Office 365 Cloud App sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="a3a14-159">Nella scheda **Sicurezza App Cloud** nuovo, tenere presente la visualizzazione di dashboard e l'elenco dei criteri predefiniti che monitorare per varie attività nella sottoscrizione a Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3a14-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="a3a14-160">Fare clic sull'icona del dashboard per visualizzare un riepilogo delle attività di sicurezza di applicazione Cloud che si desidera tenere traccia.</span><span class="sxs-lookup"><span data-stu-id="a3a14-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="a3a14-161">Fare clic su **indagare** (l'icona a forma di lente) e quindi **registro attività** per visualizzare l'elenco di recente gli accessi e altre attività.</span><span class="sxs-lookup"><span data-stu-id="a3a14-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="a3a14-162">Punteggio protetto</span><span class="sxs-lookup"><span data-stu-id="a3a14-162">Secure Score</span></span>

1. <span data-ttu-id="a3a14-163">Creare una nuova scheda nel browser e passare a **securescore.office.com**.</span><span class="sxs-lookup"><span data-stu-id="a3a14-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="a3a14-164">Nella **scheda del Dashboard**, si noti il punteggio sicura corrente e l'elenco delle operazioni nella coda per incrementare il punteggio.</span><span class="sxs-lookup"><span data-stu-id="a3a14-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="a3a14-165">Nella fase di **protezione delle informazioni** per informazioni e collegamenti per configurare queste impostazioni nell'ambiente di produzione, vedere la sezione [configurare maggiore sicurezza per Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) .</span><span class="sxs-lookup"><span data-stu-id="a3a14-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a3a14-166">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a3a14-166">Next step</span></span>

<span data-ttu-id="a3a14-167">Esplorare le funzionalità aggiuntive [la protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) e le funzionalità nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="a3a14-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3a14-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3a14-168">See also</span></span>

[<span data-ttu-id="a3a14-169">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a3a14-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a3a14-170">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a3a14-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a3a14-171">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a3a14-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

