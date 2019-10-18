---
title: Configurare Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informazioni su come configurare Microsoft 365 business.
ms.openlocfilehash: cd59570cbcb9b027780e160117b44be88770d6b9
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575549"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="43bf6-103">Configurare Microsoft 365 business nell'installazione guidata</span><span class="sxs-lookup"><span data-stu-id="43bf6-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="43bf6-104">Aggiungere il dominio, gli utenti e i criteri di configurazione</span><span class="sxs-lookup"><span data-stu-id="43bf6-104">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="43bf6-105">[![Label che consente di sapere che l'interfaccia di amministrazione sta cambiando ed è possibile trovare ulteriori dettagli su aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="43bf6-105">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="43bf6-106">Quando si acquista Microsoft 365 business, si ha la possibilità di utilizzare un dominio che si è proprietari o di acquistarne uno durante l' [iscrizione](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="43bf6-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="43bf6-107">Se si è acquistato un nuovo dominio al momento dell'iscrizione, il dominio è tutto configurato ed è possibile spostarsi per [aggiungere utenti e assegnare licenze](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="43bf6-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="43bf6-108">Aggiungere il dominio per personalizzare l'accesso</span><span class="sxs-lookup"><span data-stu-id="43bf6-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="43bf6-109">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="43bf6-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="43bf6-110">Fare clic su **Aggiungi un dominio** o su **Aggiungi utenti** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="43bf6-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="43bf6-111">Se si è acquistato un dominio durante l'iscrizione, non verrà visualizzato **aggiungere un passaggio di dominio** qui.</span><span class="sxs-lookup"><span data-stu-id="43bf6-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="43bf6-112">Andare su [Aggiungi utenti](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="43bf6-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Selezionare Vai a installazione.](media/gotosetupinadmincenter.png)
    
3. <span data-ttu-id="43bf6-114">Nella procedura guidata, immettere il nome di dominio che si desidera utilizzare (come contoso.com).</span><span class="sxs-lookup"><span data-stu-id="43bf6-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Schermata della pagina Personalizza il tuo accesso.](media/personalizesignin.png)

    
4. <span data-ttu-id="43bf6-116">Seguire i passaggi della procedura guidata per [creare record DNS presso un provider di hosting DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="43bf6-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="43bf6-117">Se si conosce l'host di dominio, vedere anche le [istruzioni specifiche dell'host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="43bf6-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="43bf6-118">Se il provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e verrà chiesto automaticamente di accedere e di consentire a Microsoft di eseguire l'autenticazione per conto dell'utente:</span><span class="sxs-lookup"><span data-stu-id="43bf6-118">If your hosting provider is GoDaddy, or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Nella pagina Conferma accesso GoDaddy selezionare autorizza.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="43bf6-120">Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="43bf6-120">Add users and assign licenses</span></span>

<span data-ttu-id="43bf6-121">È possibile aggiungere utenti nella procedura guidata, ma è anche possibile [aggiungerli in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="43bf6-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="43bf6-122">Inoltre, se si dispone di un controller di dominio locale, è possibile aggiungere utenti con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="43bf6-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="43bf6-123">Aggiungere gli utenti nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="43bf6-123">Add users in the wizard</span></span>

<span data-ttu-id="43bf6-124">Tutti gli utenti aggiunti nella procedura guidata vengono assegnati automaticamente a una licenza aziendale Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43bf6-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Schermata della pagina Aggiungi nuovi utenti nella procedura guidata](media/addnewuserspage.png)

1. <span data-ttu-id="43bf6-126">Se l'abbonamento a Microsoft 365 business ha utenti esistenti (ad esempio, se è stato utilizzato Azure AD Connect), è possibile assegnare loro le licenze.</span><span class="sxs-lookup"><span data-stu-id="43bf6-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="43bf6-127">Procedere con l'aggiunta di licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="43bf6-127">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="43bf6-128">Dopo aver aggiunto gli utenti, si otterrà anche un'opzione per condividere le credenziali con i nuovi utenti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="43bf6-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="43bf6-129">È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="43bf6-129">You can choose to print them out, email them, or download them.</span></span>

3. <span data-ttu-id="43bf6-130">Nel creare team per l'organizzazione, è possibile scegliere di aggiungere Team e aggiungergli gli utenti.</span><span class="sxs-lookup"><span data-stu-id="43bf6-130">On the Create Teams for your organization, you can choose to add Teams and add users to them.</span></span> <span data-ttu-id="43bf6-131">È inoltre possibile eseguire questa operazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="43bf6-131">You can also do this later.</span></span> <span data-ttu-id="43bf6-132">Per ulteriori informazioni, vedere [Create a Company-Wide team](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span><span class="sxs-lookup"><span data-stu-id="43bf6-132">For more information, see [create a company-wide Team](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>

4. <span data-ttu-id="43bf6-133">Ignorare il passaggio relativo alla migrazione dei messaggi di posta elettronica e scegliere **Avanti** nella pagina **Esegui la migrazione dei messaggi di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="43bf6-133">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="43bf6-134">Se si sta passando da un altro provider di posta elettronica e si desidera copiare i dati in un secondo momento, è possibile [eseguire la migrazione di posta elettronica e contatti a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="43bf6-134">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="43bf6-135">Connettere il dominio</span><span class="sxs-lookup"><span data-stu-id="43bf6-135">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="43bf6-136">Se si è scelto di utilizzare il dominio. onmicrosoft o di Azure AD Connect per configurare gli utenti, questo passaggio non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="43bf6-136">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="43bf6-137">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="43bf6-137">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="43bf6-138">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="43bf6-138">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="43bf6-139">In caso contrario, [modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="43bf6-139">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="43bf6-140">Se si dispone di record DNS esistenti, ad esempio un sito Web esistente, ma l'host DNS è abilitato per la [connessione al dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Add records for me**.</span><span class="sxs-lookup"><span data-stu-id="43bf6-140">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="43bf6-141">Nella pagina **scegliere i servizi online** accettare tutte le impostazioni predefinite e scegliere **Avanti**, quindi fare clic su **autorizza** nella pagina dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="43bf6-141">On the **Choose your online services** page, accept all the defaults, and choose **Next**,and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="43bf6-142">Se sono presenti record DNS con altri host DNS (non abilitati per la connessione al dominio), è necessario gestire i propri record DNS per assicurarsi che i servizi esistenti siano connessi.</span><span class="sxs-lookup"><span data-stu-id="43bf6-142">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="43bf6-143">Per altre informazioni, vedere [Domain nozioni di base](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="43bf6-143">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Connect Your Domain Page con I ' ll manage my own DNS Records.](media/connectyourdomainpage.png)

2. <span data-ttu-id="43bf6-145">Seguire i passaggi della procedura guidata e la posta elettronica e altri servizi verranno configurati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="43bf6-145">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-data-and-devices"></a><span data-ttu-id="43bf6-146">Proteggere i dati e i dispositivi</span><span class="sxs-lookup"><span data-stu-id="43bf6-146">Protect data and devices</span></span> 

<span data-ttu-id="43bf6-147">I criteri configurati nella procedura guidata vengono applicati automaticamente a un [gruppo di sicurezza](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominato *tutti gli utenti*.</span><span class="sxs-lookup"><span data-stu-id="43bf6-147">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="43bf6-148">È inoltre possibile creare altri gruppi per assegnare criteri nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="43bf6-148">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="43bf6-149">Nella pagina **Proteggi i file di lavoro nei dispositivi mobili** , l'opzione **Proteggi i file di lavoro quando i dispositivi vengono persi o rubati** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="43bf6-149">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="43bf6-150">È possibile abilitare la gestione del modo in cui **gli utenti accedono ai file di Office nei dispositivi mobili**e questo è consigliato.</span><span class="sxs-lookup"><span data-stu-id="43bf6-150">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Schermata della pagina Proteggi file di lavoro su dispositivi mobili.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="43bf6-152">Espandere **Proteggi file di lavoro quando i dispositivi vengono persi o rubati** per visualizzare i [valori predefiniti](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="43bf6-152">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Screenshot dei valori predefiniti per la protezione di file su dispositivi persi.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="43bf6-154">Selezionare **Gestisci la modalità di accesso degli utenti ai file di Office nei dispositivi mobili** ed espanderla per visualizzare i [valori predefiniti](manage-user-access-on-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="43bf6-154">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="43bf6-155">È consigliabile accettare i valori predefiniti durante l'installazione per creare i criteri di applicazione per Android, iOS e Windows 10 che si applicano a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="43bf6-155">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="43bf6-156">È possibile creare altri criteri al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="43bf6-156">You can create more policies after setup completes.</span></span>

        ![Schermata delle impostazioni di protezione per i file di Office su dispositivi mobili.](media/useraccessonmobile.png)

2. <span data-ttu-id="43bf6-158">L'ultimo passaggio su Protect data and Devices consente di configurare i criteri per proteggere i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="43bf6-158">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="43bf6-159">Queste impostazioni vengono applicate automaticamente quando un utente di Windows 10 si connette all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43bf6-159">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="43bf6-160">È possibile espandere i **dispositivi Windows 10 sicuri** per visualizzare e modificare i [valori predefiniti](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="43bf6-160">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="43bf6-161">È inoltre possibile scegliere di [installare automaticamente Office](install-office-on-windows-10-during-setup.md) nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="43bf6-161">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Schermata della pagina Imposta configurazione dispositivo Windows 10.](media/setwin10config.png)


## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="43bf6-163">Distribuire le app client di Office 365</span><span class="sxs-lookup"><span data-stu-id="43bf6-163">Deploy Office 365 client apps</span></span>

<span data-ttu-id="43bf6-164">Se si è scelto di installare automaticamente le app di Office durante la configurazione, le app verranno installate nei dispositivi Windows 10 dopo che gli utenti hanno effettuato l'accesso a Azure AD dai propri dispositivi Windows con le credenziali di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43bf6-164">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="43bf6-165">Per installare Office su dispositivi mobili iOS o Android, vedere [configurare i dispositivi mobili per gli utenti aziendali di Microsoft 365](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="43bf6-165">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="43bf6-166">È anche possibile installare Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="43bf6-166">You can also install Office individually.</span></span> <span data-ttu-id="43bf6-167">Per istruzioni, vedere [installare Office in un PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .</span><span class="sxs-lookup"><span data-stu-id="43bf6-167">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
