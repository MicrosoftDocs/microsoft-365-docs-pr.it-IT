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
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informazioni su come configurare Microsoft 365 business completando quattro passaggi.
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283916"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="18f5f-103">Configurare Microsoft 365 Business tramite la configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="18f5f-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="18f5f-104">Completare i passaggi 1-4 riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="18f5f-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="18f5f-105">Configurare Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="18f5f-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="18f5f-106">Guardare un video su come configurare Microsoft 365 business quando non si dispone di un Active Directory locale:</span><span class="sxs-lookup"><span data-stu-id="18f5f-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="18f5f-107">I passaggi di configurazione includono informazioni per le configurazioni che includono Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="18f5f-107">The set-up steps include information for setups that include local Active Directory.</span></span> <span data-ttu-id="18f5f-108">Se si desidera continuare ad accedere ai dispositivi appartenenti al dominio, leggere gli articoli seguenti per due diverse modalità di abilitazione e completare la procedura prima di eseguire l'installazione guidata:</span><span class="sxs-lookup"><span data-stu-id="18f5f-108">If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="18f5f-109">Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="18f5f-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="18f5f-110">-Questo è il modo consigliato.</span><span class="sxs-lookup"><span data-stu-id="18f5f-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="18f5f-111">Accedere alle risorse locali da un dispositivo di Azure AD-join in Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="18f5f-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="18f5f-112">Passaggio 1: personalizzare l'accesso</span><span class="sxs-lookup"><span data-stu-id="18f5f-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="18f5f-p102">Accedere a [Microsoft 365 Business](https://portal.microsoft.com) usando le credenziali di amministratore globale. Selezionare il riquadro **Amministratore** per passare all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="18f5f-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="18f5f-115">Nell'interfaccia di amministrazione scegliere **Avvia configurazione** (a seconda dello stato potrebbe invece essere visualizzato **Continua configurazione**) per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="18f5f-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="18f5f-116">Immettere il nome del dominio che si vuole usare, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="18f5f-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="18f5f-117">Immettere il dominio anche se è già stato verificato durante l'uso di Azure AD Connect, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="18f5f-117">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example.</span></span> <span data-ttu-id="18f5f-118">I due passaggi seguenti non si applicano all'utente se si utilizza Azure AD Connect per verificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="18f5f-118">The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="18f5f-119">Seguire i passaggi della procedura guidata per [creare record DNS presso un provider di hosting DNS per Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) che verifica che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="18f5f-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="18f5f-120">È possibile visualizzare un video di esempio del [video: configurare Office 365 nella nuova](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="18f5f-120">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8).</span></span> <span data-ttu-id="18f5f-121">Questo video non include i passaggi per la protezione dei dati di Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="18f5f-121">Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="18f5f-123">Passaggio 2: aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="18f5f-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="18f5f-124">È possibile aggiungere utenti qui oppure [aggiungere gli utenti in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="18f5f-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="18f5f-125">A qualsiasi utente aggiunto viene automaticamente assegnata una licenza di Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="18f5f-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="18f5f-p105">Se l'abbonamento a Microsoft 365 Business include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un'opzione per l'assegnazione di licenze a questi utenti. Procedere con l'aggiunta di licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="18f5f-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="18f5f-p106">Sarà disponibile anche un'opzione per la condivisione delle credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="18f5f-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="18f5f-130">Ignorare il passaggio relativo alla migrazione dei messaggi di posta elettronica e scegliere **Avanti** nella pagina **Esegui la migrazione dei messaggi di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="18f5f-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="18f5f-131">Se si sta passando da un altro provider di posta elettronica e si desidera copiare i dati in un secondo momento, è possibile [eseguire la migrazione di posta elettronica e contatti a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="18f5f-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="18f5f-133">Passaggio 3: connettere il dominio</span><span class="sxs-lookup"><span data-stu-id="18f5f-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="18f5f-134">Se si è scelto di utilizzare il dominio. onmicrosoft o Azure AD Connect, questo passaggio non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="18f5f-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="18f5f-135">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="18f5f-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="18f5f-136">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="18f5f-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="18f5f-137">In caso contrario, [modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="18f5f-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="18f5f-138">La posta elettronica e altri servizi verranno configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="18f5f-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="18f5f-139">Passaggio 4: gestire i dispositivi e i file di lavoro</span><span class="sxs-lookup"><span data-stu-id="18f5f-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="18f5f-140">Nella pagina **Proteggi i file di lavoro nei dispositivi mobili** **attivare** sia **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi** che **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="18f5f-140">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**.</span></span> <span data-ttu-id="18f5f-141">È inoltre possibile accedere a ogni impostazione secondaria facendo clic sulle virgolette acute accanto a ogni impostazione.</span><span class="sxs-lookup"><span data-stu-id="18f5f-141">You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="18f5f-142">Tutti i file di lavoro degli utenti con licenza sono ora protetti nei dispositivi iOS e Android, non appena installano le [app di Office](set-up-mobile-devices.md) (ed eseguono l'autenticazione con le credenziali aziendali di Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="18f5f-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="18f5f-144">Nella pagina **Imposta configurazione dispositivo Windows 10** , impostare **Secure Windows 10 Devices** setting **su on**.</span><span class="sxs-lookup"><span data-stu-id="18f5f-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="18f5f-145">È inoltre possibile accedere a ogni impostazione secondaria facendo clic sul simbolo chevron accanto a esso.</span><span class="sxs-lookup"><span data-stu-id="18f5f-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="18f5f-146">Impostare l'opzione **Installa Office nei dispositivi Windows 10** su **Sì** se tutti gli utenti hanno computer Windows 10 e nessuna installazione di Office esistente oppure installazioni di Office A portata di clic.</span><span class="sxs-lookup"><span data-stu-id="18f5f-146">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs.</span></span> <span data-ttu-id="18f5f-147">In caso contrario, impostare questa opzione su **No**.</span><span class="sxs-lookup"><span data-stu-id="18f5f-147">If this is not the case, set this option to **No**.</span></span> <span data-ttu-id="18f5f-148">È possibile [installare Office automaticamente](auto-install-or-uninstall-office.md) in un secondo momento dall'interfaccia di amministrazione dopo aver preparato i computer degli utenti.</span><span class="sxs-lookup"><span data-stu-id="18f5f-148">You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers.</span></span> <span data-ttu-id="18f5f-149">Per istruzioni, vedere [Prepare for Office Client Installation](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="18f5f-149">For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="18f5f-150">I file di lavoro degli utenti con licenza nei dispositivi Windows 10 verranno proiettati non appena entreranno a [far parte del dispositivo Windows 10](set-up-windows-devices.md) a un dominio di Microsoft 365 business Azure ad o [installeranno Windows 10 in un nuovo computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) e contemporaneamente entreranno a far parte di Microsoft 365. Dominio di Azure AD aziendale.</span><span class="sxs-lookup"><span data-stu-id="18f5f-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="18f5f-151">Fare clic su **Avanti** per completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="18f5f-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="18f5f-152">Inviare infine il proprio feedback per aiutarci a migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="18f5f-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="18f5f-154">Impostazioni di sicurezza aggiuntive</span><span class="sxs-lookup"><span data-stu-id="18f5f-154">Additional security settings</span></span>

<span data-ttu-id="18f5f-155">Oltre all'impostazione sicurezza e conformità nell'installazione guidata, è anche possibile configurare le seguenti impostazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="18f5f-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="18f5f-156">Impostare la protezione contro gli allegati non sicuri.</span><span class="sxs-lookup"><span data-stu-id="18f5f-156">Set up protection against unsafe attachments.</span></span> <span data-ttu-id="18f5f-157">**Protezione avanzata dalle minacce** (ATP) identifica i contenuti dannosi e quindi blocca il recapito degli allegati non sicuri, contribuendo a proteggersi dagli schemi di phishing e dalle infezioni ransomware.</span><span class="sxs-lookup"><span data-stu-id="18f5f-157">**Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="18f5f-158">Per attivare la protezione degli allegati, vedere [set up Office 365 ATP SAFE Attachment Policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="18f5f-158">To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="18f5f-159">Proteggere l'ambiente quando gli utenti fanno clic su collegamenti dannosi.</span><span class="sxs-lookup"><span data-stu-id="18f5f-159">Protect your environment when users click malicious links.</span></span> <span data-ttu-id="18f5f-160">ATP esamina i collegamenti nella posta elettronica al momento in cui un utente fa clic su di essi.</span><span class="sxs-lookup"><span data-stu-id="18f5f-160">ATP examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="18f5f-161">Se un collegamento non è sicuro, l'utente viene avvisato di non visitare il sito o ha informato che il sito è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="18f5f-161">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="18f5f-162">Ciò consente di proteggere gli schemi di phishing.</span><span class="sxs-lookup"><span data-stu-id="18f5f-162">This helps protect against phishing schemes.</span></span> <span data-ttu-id="18f5f-163">[Configurare i criteri dei collegamenti sicuri ATP di office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [configurare i criteri dei collegamenti sicuri atp di Office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="18f5f-163">[Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="18f5f-164">È possibile mantenere tutti i contenuti delle cassette postali, compresi gli elementi eliminati, inserendo l'intera cassetta postale di un utente sul **blocco per controversia legale**.</span><span class="sxs-lookup"><span data-stu-id="18f5f-164">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**.</span></span> <span data-ttu-id="18f5f-165">Per istruzioni, vedere</span><span class="sxs-lookup"><span data-stu-id="18f5f-165">For instructions, see</span></span> 
- <span data-ttu-id="18f5f-166">[Configurare la conservazione della posta elettronica con Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="18f5f-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="18f5f-167">Impostare criteri di **conservazione**personalizzati, ad esempio per mantenere un determinato intervallo di tempo o eliminare il contenuto in modo permanente alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="18f5f-167">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="18f5f-168">È possibile abilitare i criteri di conservazione personalizzati nel centro titoli e conformità, passare a \> **conservazione**della **governance dei dati** e quindi seguire i passaggi della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="18f5f-168">You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard.</span></span> <span data-ttu-id="18f5f-169">Per ulteriori informazioni, vedere [Overview of](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)Retention Policies.</span><span class="sxs-lookup"><span data-stu-id="18f5f-169">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="18f5f-170">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="18f5f-170">Next steps</span></span>

<span data-ttu-id="18f5f-171">Per gli utenti che hanno le proprie licenze, il passaggio successivo consiste nel configurare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="18f5f-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="18f5f-172">Vedere [Configurare i dispositivi Windows per utenti di Microsoft 365 Business](set-up-windows-devices.md) e [Configurare i dispositivi mobili per utenti di Microsoft 365 Business](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="18f5f-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="18f5f-173">Vedere [Gestire Microsoft 365 Business](manage.md) per i collegamenti agli argomenti su come impostare i criteri di protezione di dispositivi e app e su come rimuovere i dati dai dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="18f5f-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


