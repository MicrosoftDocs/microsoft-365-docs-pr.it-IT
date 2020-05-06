---
title: Configurare Microsoft 365 Business Premium
f1.keywords:
- NOCSH
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
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Individuare i passaggi di installazione per Microsoft 365 Business Premium, tra cui l'aggiunta di un dominio e degli utenti, la configurazione dei criteri di sicurezza e altro ancora.
ms.openlocfilehash: cfc8523fe88ebca6b8c03db0ad0f6caeba662923
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048038"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="e0489-103">Configurare Microsoft 365 Business Premium nell'installazione guidata</span><span class="sxs-lookup"><span data-stu-id="e0489-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="e0489-104">Guardare questo video per una panoramica della configurazione di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e0489-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="e0489-105">Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="e0489-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="e0489-106">Aggiungere il dominio, gli utenti e i criteri di configurazione</span><span class="sxs-lookup"><span data-stu-id="e0489-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="e0489-107">[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="e0489-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="e0489-108">Quando si acquista Microsoft 365 Business Premium, si ha la possibilità di utilizzare un dominio che si è proprietari o di acquistarne uno durante l' [iscrizione](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="e0489-108">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="e0489-109">Se si è acquistato un nuovo dominio al momento dell'iscrizione, il dominio è tutto configurato ed è possibile spostarsi per [aggiungere utenti e assegnare licenze](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="e0489-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="e0489-110">Aggiungere il dominio per personalizzare l'accesso</span><span class="sxs-lookup"><span data-stu-id="e0489-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="e0489-111">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e0489-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="e0489-112">Scegliere **Vai a installazione** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e0489-112">Choose **Go to setup** to start the wizard.</span></span>

    ![Selezionare Vai a installazione.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="e0489-114">Nella pagina **installa le app di Office** , è possibile installare le app nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="e0489-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="e0489-115">Nel passaggio **Aggiungi dominio** , immettere il nome di dominio che si desidera utilizzare (come contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e0489-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e0489-116">Se si è acquistato un dominio durante l'iscrizione, non verrà visualizzato **aggiungere un passaggio di dominio** qui.</span><span class="sxs-lookup"><span data-stu-id="e0489-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="e0489-117">Andare su [Aggiungi utenti](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="e0489-117">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Schermata della pagina Personalizza il tuo accesso.](../media/adddomain.png)

    
4. <span data-ttu-id="e0489-119">Seguire i passaggi della procedura guidata per [creare record DNS presso un provider di hosting DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="e0489-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="e0489-120">Se si conosce l'host di dominio, vedere anche le [istruzioni specifiche dell'host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="e0489-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="e0489-121">Se il provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e verrà automaticamente chiesto di accedere e di consentire a Microsoft di eseguire l'autenticazione per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e0489-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Nella pagina Conferma accesso GoDaddy selezionare autorizza.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="e0489-123">Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="e0489-123">Add users and assign licenses</span></span>

<span data-ttu-id="e0489-124">È possibile aggiungere utenti nella procedura guidata, ma è anche possibile [aggiungerli in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e0489-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="e0489-125">Inoltre, se si dispone di un controller di dominio locale, è possibile aggiungere utenti con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="e0489-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="e0489-126">Aggiungere gli utenti nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="e0489-126">Add users in the wizard</span></span>

<span data-ttu-id="e0489-127">Tutti gli utenti aggiunti nella procedura guidata vengono assegnati automaticamente a una licenza Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e0489-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Schermata della pagina Aggiungi nuovi utenti nella procedura guidata](../media/addnewuserspage.png)

1. <span data-ttu-id="e0489-129">Se l'abbonamento Microsoft 365 Business Premium ha utenti esistenti (ad esempio, se è stato utilizzato Azure AD Connect), è possibile assegnare loro le licenze adesso.</span><span class="sxs-lookup"><span data-stu-id="e0489-129">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="e0489-130">Procedere con l'aggiunta di licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="e0489-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="e0489-131">Dopo aver aggiunto gli utenti, si otterrà anche un'opzione per condividere le credenziali con i nuovi utenti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="e0489-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="e0489-132">È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="e0489-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="e0489-133">Connettere il dominio</span><span class="sxs-lookup"><span data-stu-id="e0489-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="e0489-134">Se si è scelto di utilizzare il dominio. onmicrosoft o di Azure AD Connect per configurare gli utenti, questo passaggio non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e0489-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="e0489-135">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="e0489-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="e0489-136">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="e0489-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="e0489-137">In caso contrario, [modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="e0489-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="e0489-138">Se si dispone di record DNS esistenti, ad esempio un sito Web esistente, ma l'host DNS è abilitato per la [connessione al dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Add records for me**.</span><span class="sxs-lookup"><span data-stu-id="e0489-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="e0489-139">Nella pagina **scegliere i servizi online** accettare tutte le impostazioni predefinite e scegliere **Avanti**, quindi fare clic su **autorizza** nella pagina dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="e0489-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="e0489-140">Se sono presenti record DNS con altri host DNS (non abilitati per la connessione al dominio), è necessario gestire i propri record DNS per assicurarsi che i servizi esistenti siano connessi.</span><span class="sxs-lookup"><span data-stu-id="e0489-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="e0489-141">Per altre informazioni, vedere [Domain nozioni di base](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="e0489-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Attiva la pagina dei record.](../media/activaterecords.png)

2. <span data-ttu-id="e0489-143">Seguire i passaggi della procedura guidata e la posta elettronica e altri servizi verranno configurati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="e0489-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="e0489-144">Proteggere l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e0489-144">Protect your organization</span></span> 

<span data-ttu-id="e0489-145">I criteri configurati nella procedura guidata vengono applicati automaticamente a un [gruppo di sicurezza](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominato *tutti gli utenti*.</span><span class="sxs-lookup"><span data-stu-id="e0489-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="e0489-146">È inoltre possibile creare altri gruppi per assegnare criteri nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e0489-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="e0489-147">Per **aumentare la protezione da minacce informatiche avanzate**, è consigliabile accettare le impostazioni predefinite per consentire a [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) di eseguire l'analisi dei file di protezione dalle minacce e i collegamenti nelle app di Office.</span><span class="sxs-lookup"><span data-stu-id="e0489-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Schermata della pagina aumenta protezione.](../media/increasetreatprotection.png)


2. <span data-ttu-id="e0489-149">Nella pagina **Impedisci perdite di dati sensibili** , accettare le impostazioni predefinite per abilitare la prevenzione della perdita di dati (DLP) di Office 365 per tenere sotto controllo i dati sensibili nelle app di Office e impedire la condivisione accidentale di questi all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0489-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="e0489-150">Nella pagina **Proteggi dati in Office per dispositivi** mobili, lascia la gestione delle app per dispositivi mobili, Espandi le impostazioni e rivedile e quindi seleziona **Crea criteri di gestione delle app per dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="e0489-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Schermata della pagina Proteggi dati in Office per dispositivi mobili.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="e0489-152">Proteggere i PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="e0489-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="e0489-153">Sulla barra di spostamento sinistra, selezionare **installazione** e quindi, in **accesso e sicurezza**, scegliere **Proteggi i computer Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="e0489-153">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="e0489-154">Scegliere **View** per iniziare.</span><span class="sxs-lookup"><span data-stu-id="e0489-154">Choose **View** to get started.</span></span> <span data-ttu-id="e0489-155">Per istruzioni complete, vedere [proteggere i computer Windows 10](secure-win-10-pcs.md) .</span><span class="sxs-lookup"><span data-stu-id="e0489-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="e0489-156">Distribuire le app client di Office 365</span><span class="sxs-lookup"><span data-stu-id="e0489-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="e0489-157">Se si è scelto di installare automaticamente le app di Office durante l'installazione, le app verranno installate nei dispositivi Windows 10 dopo che gli utenti hanno effettuato l'accesso a Azure AD dai propri dispositivi Windows, utilizzando le proprie credenziali di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e0489-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="e0489-158">Per installare Office su dispositivi mobili iOS o Android, vedere [configurare i dispositivi mobili per gli utenti di Microsoft 365 Business Premium](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="e0489-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="e0489-159">È anche possibile installare Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="e0489-159">You can also install Office individually.</span></span> <span data-ttu-id="e0489-160">Per istruzioni, vedere [installare Office in un PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .</span><span class="sxs-lookup"><span data-stu-id="e0489-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0489-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0489-161">See also</span></span>

[<span data-ttu-id="e0489-162">Video di formazione su Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="e0489-162">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
