---
title: Configurare Microsoft 365 Business tramite la configurazione guidata
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informazioni su come configurare Microsoft 365 Business completando i quattro passaggi.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868285"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="fa752-103">Configurare Microsoft 365 Business tramite la configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="fa752-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="fa752-104">Completare i passaggi da 1 a 4 riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="fa752-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="fa752-105">Configurare Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="fa752-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="fa752-106">Guardare un video viene illustrato come configurare Microsoft 365 Business quando non si dispone di un server di Active Directory locale:</span><span class="sxs-lookup"><span data-stu-id="fa752-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="fa752-p101">I passaggi di configurazione includono informazioni personali per le installazioni che includono Active Directory locale. Se si desidera continuare ad accedere ai dispositivi di dominio, leggere gli articoli seguenti per due diverse modalità dell'attivazione che e prima di eseguire l'installazione guidata, completare i passaggi:</span><span class="sxs-lookup"><span data-stu-id="fa752-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="fa752-109">Consentire ai dispositivi Windows 10 aggiunto al dominio da gestire da Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="fa752-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="fa752-110">-Si tratta del metodo consigliato.</span><span class="sxs-lookup"><span data-stu-id="fa752-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="fa752-111">Accesso locale risorse da un dispositivo Azure Active Directory aggiunti in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="fa752-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="fa752-112">Passaggio 1: Personalizzare accesso</span><span class="sxs-lookup"><span data-stu-id="fa752-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="fa752-p102">Accedere a [Microsoft 365 Business](https://portal.microsoft.com) usando le credenziali di amministratore globale. Selezionare il riquadro **Amministratore** per passare all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fa752-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="fa752-115">Nell'interfaccia di amministrazione scegliere **Avvia configurazione** (a seconda dello stato potrebbe invece essere visualizzato **Continua configurazione**) per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="fa752-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="fa752-116">Immettere il nome del dominio che si vuole usare, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fa752-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="fa752-p103">Proseguire e immettere il dominio, anche se è stato verificato durante l'utilizzo di Azure Active Directory Connect, ad esempio. I due passaggi seguenti non si applicano all'utente se è stato utilizzato Connetti Azure Active Directory per verificare il proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="fa752-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="fa752-119">Seguire le istruzioni della procedura guidata per [creare record DNS presso un provider di hosting DNS per Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) che consente di verificare che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="fa752-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="fa752-p104">È possibile visualizzare un video di esempio di [Video: installazione di Office 365 nuova interfaccia di amministrazione di](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Si noti che in questo video non sono incluse le operazioni di protezione dei dati di Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="fa752-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="fa752-123">Passaggio 2: Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="fa752-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="fa752-124">È possibile aggiungere utenti qui oppure [aggiungere gli utenti in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fa752-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="fa752-125">A qualsiasi utente aggiunto viene automaticamente assegnata una licenza di Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="fa752-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="fa752-p105">Se l'abbonamento a Microsoft 365 Business include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un'opzione per l'assegnazione di licenze a questi utenti. Procedere con l'aggiunta di licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="fa752-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="fa752-p106">Sarà disponibile anche un'opzione per la condivisione delle credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="fa752-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="fa752-130">Ignorare il passaggio relativo alla migrazione dei messaggi di posta elettronica e scegliere **Avanti** nella pagina **Esegui la migrazione dei messaggi di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="fa752-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="fa752-131">Se si passa da un altro provider di posta elettronica e si desidera copiare i dati in seguito, è possibile [eseguire la migrazione di posta elettronica e i contatti a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="fa752-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="fa752-133">Passaggio 3: Connettere il dominio</span><span class="sxs-lookup"><span data-stu-id="fa752-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="fa752-134">Se si sceglie di utilizzare il dominio .onmicrosoft o utilizzato Connetti Azure Active Directory, questo passaggio non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="fa752-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="fa752-135">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="fa752-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="fa752-p107">In genere, l'installazione guidata rileva la registrazione e offre un collegamento a istruzioni dettagliate per aggiornare i record NS nel sito Web di registrazione. In caso contrario, [nameservers modifiche alla configurazione di Office 365 con un registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="fa752-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="fa752-138">La posta elettronica e altri servizi verranno configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fa752-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="fa752-139">Passaggio 4: Gestire i dispositivi e file di lavoro</span><span class="sxs-lookup"><span data-stu-id="fa752-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="fa752-p108">Nel **file di lavoro Protect nei dispositivi mobili** pagina impostata **Protect lavoro file quando dispositivi sono perduti o rubati** e le impostazioni di **gestire l'accesso al file di Office su dispositivi mobili** **in**. È inoltre possibile accedere a ogni secondario impostazione facendo clic sulle virgolette acute accanto a ogni impostazione.</span><span class="sxs-lookup"><span data-stu-id="fa752-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="fa752-142">Tutti lavoro file gli utenti con licenza sono ora protetti iOS e dispositivi Android, non appena si [installa Office apps](set-up-mobile-devices.md) (e l'autenticazione con le proprie credenziali di Microsoft 365 Business).</span><span class="sxs-lookup"><span data-stu-id="fa752-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="fa752-144">Nella pagina **Configurazione dispositivo impostare Windows 10** impostazione **Sicura Windows 10 dispositivi** di **attivato**.</span><span class="sxs-lookup"><span data-stu-id="fa752-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="fa752-145">È inoltre possibile accedere a ogni secondario impostazione facendo clic sull'accento circonflesso accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="fa752-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="fa752-p109">Impostazione di **Installare Office su dispositivi 10 Windows** **Sì** se tutti gli utenti dispongono di computer Windows 10 e verrà installato alcun esistente Office o le installazioni di Office a portata di clic. In questo caso non è possibile impostare questa opzione su **No**. Dopo aver preparato il computer degli utenti, è possibile [installare automaticamente Office](auto-install-or-uninstall-office.md) successivamente dall'interfaccia di amministrazione. Per ulteriori informazioni, vedere [Preparazione dell'installazione client di Office](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="fa752-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="fa752-150">Verranno proiettare il più presto possibile man mano che i file di lavoro degli utenti con licenza nei dispositivi Windows 10 [partecipare proprio dispositivo Windows 10](set-up-windows-devices.md) a un dominio aziendale Microsoft 365 Azure Active Directory o [installare Windows 10 in un nuovo computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) durante l'unione contemporaneamente a Microsoft 365 Dominio di Azure Active Directory aziendale.</span><span class="sxs-lookup"><span data-stu-id="fa752-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="fa752-151">Fare clic su **Avanti** per completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa752-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="fa752-152">Inviare infine il proprio feedback per aiutarci a migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="fa752-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="fa752-154">Impostazioni di sicurezza aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fa752-154">Additional security settings</span></span>

<span data-ttu-id="fa752-155">Oltre a protezione e impostazione di conformità dell'installazione guidata, è possibile configurare impostazioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa752-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="fa752-p110">Consente di impostare una protezione contro gli allegati non sicuri. **Protezione da minacce avanzate** (Degli strumenti di analisi) identifica contenuto dannoso e quindi blocca il rilascio di unsafe attachments, proteggere contro gli schemi di phishing e infezioni ransomware. Per attivare la protezione degli allegati, vedere [impostazione dei criteri di sicurezza allegati di Office 365 degli strumenti di analisi](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="fa752-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="fa752-p111">Proteggere l'ambiente quando gli utenti fare clic sui collegamenti dannosi. Degli strumenti di analisi vengono esaminati i collegamenti nella posta elettronica in fase di un utente fa clic su essi. Se un collegamento non sicuro, l'utente viene avvisato non per visitare il sito o informato che il sito è stato bloccato. Consente di evitare truffe. [Impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="fa752-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="fa752-p112">È possibile preservare tutto il contenuto delle cassette postali inclusi gli elementi eliminati inserendo intera cassetta postale dell'utente controversia **attesa**. Per ulteriori informazioni, vedere</span><span class="sxs-lookup"><span data-stu-id="fa752-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="fa752-166">[Impostare il mantenimento di posta elettronica con archiviazione Exchange Online](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="fa752-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="fa752-p113">Configurare **i criteri di conservazione**personalizzata, ad esempio, per conservare per un determinato periodo di tempo o eliminare in modo permanente il contenuto alla fine del periodo di conservazione. È possibile abilitare i criteri di conservazione personalizzata nella titoli e centro conformità, andare alla **governance dati** \> **conservazione**, quindi seguire le istruzioni della procedura guidata. Per ulteriori informazioni, vedere [Panoramica di criteri di conservazione](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="fa752-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="fa752-170">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fa752-170">Next steps</span></span>

<span data-ttu-id="fa752-171">Per gli utenti che hanno le proprie licenze, il passaggio successivo consiste nel configurare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fa752-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="fa752-172">Vedere [Configurare i dispositivi Windows per utenti di Microsoft 365 Business](set-up-windows-devices.md) e [Configurare i dispositivi mobili per utenti di Microsoft 365 Business](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="fa752-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="fa752-173">Vedere [Gestire Microsoft 365 Business](manage.md) per i collegamenti agli argomenti su come impostare i criteri di protezione di dispositivi e app e su come rimuovere i dati dai dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="fa752-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


