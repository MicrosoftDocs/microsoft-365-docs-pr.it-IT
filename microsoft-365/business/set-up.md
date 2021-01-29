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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Scopri i passaggi di configurazione per Microsoft 365 Business Premium, tra cui l'aggiunta di un dominio e utenti, la configurazione dei criteri di sicurezza e altro ancora.
ms.openlocfilehash: e7ebe179c67077dc71ae4873b0711d0e810c701a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044731"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="1007c-103">Configurare Microsoft 365 Business Premium nella configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="1007c-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="1007c-104">Guardare questo video per una panoramica della configurazione di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1007c-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="1007c-105">Aggiungere il dominio, gli utenti e configurare i criteri</span><span class="sxs-lookup"><span data-stu-id="1007c-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="1007c-106">Quando si acquista Microsoft 365 Business Premium, è possibile usare un dominio di cui si è proprietari o acquistarne uno durante [l'iscrizione.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="1007c-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="1007c-107">Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1007c-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="1007c-108">Aggiungere il proprio dominio per personalizzare l’accesso</span><span class="sxs-lookup"><span data-stu-id="1007c-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="1007c-109">Autenticarsi allì[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le proprie credenziali globali di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1007c-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="1007c-110">Scegliere **Vai alla configurazione** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1007c-110">Choose **Go to setup** to start the wizard.</span></span>

    ![Seleziona Vai alla configurazione.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="1007c-112">Nella pagina **Installa le tue app di Office**, è possibile installare le app sul proprio computer.</span><span class="sxs-lookup"><span data-stu-id="1007c-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="1007c-113">Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1007c-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1007c-114">Se un dominio è stato acquistato durante l’iscrizione, il passaggio **Aggiungi un dominio** non comparirà.</span><span class="sxs-lookup"><span data-stu-id="1007c-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="1007c-115">Proseguire al passaggio [Aggiungi utenti](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1007c-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Screenshot of the Personalize your sign-in page.](../media/adddomain.png)

    
4. <span data-ttu-id="1007c-117">Seguire i passaggi della procedura guidata per creare record DNS presso qualsiasi provider di hosting DNS per [Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica di essere proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="1007c-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="1007c-118">Se si conosce l’host del dominio, vedere anche le [istruzioni specifiche dell’host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="1007c-118">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="1007c-119">Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1007c-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="1007c-121">Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="1007c-121">Add users and assign licenses</span></span>

<span data-ttu-id="1007c-122">Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](add-users-m365b.md) nell’interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1007c-122">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="1007c-123">Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="1007c-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="1007c-124">Aggiungere utenti nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="1007c-124">Add users in the wizard</span></span>

<span data-ttu-id="1007c-125">A tutti gli utenti aggiunti nella procedura guidata viene assegnata automaticamente una licenza di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1007c-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Screenshot della pagina Aggiungi nuovi utenti della procedura guidata](../media/addnewuserspage.png)

1. <span data-ttu-id="1007c-127">Se l'abbonamento a Microsoft 365 Business Premium include utenti esistenti (ad esempio, se è stato usato Azure AD Connect), è possibile scegliere di assegnare loro le licenze.</span><span class="sxs-lookup"><span data-stu-id="1007c-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="1007c-128">Procedere aggiungendo le licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="1007c-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="1007c-129">Una volta aggiunti gli utenti, sarà disponibile un’opzione per condividere le credenziali con i nuovi utenti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="1007c-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="1007c-130">È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="1007c-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="1007c-131">Connettere il proprio dominio</span><span class="sxs-lookup"><span data-stu-id="1007c-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="1007c-132">Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="1007c-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="1007c-133">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="1007c-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="1007c-134">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="1007c-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="1007c-135">In caso contrario, modificare i server dei [nomi per configurare Microsoft 365 con qualsiasi registrar.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)</span><span class="sxs-lookup"><span data-stu-id="1007c-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="1007c-136">Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**.</span><span class="sxs-lookup"><span data-stu-id="1007c-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="1007c-137">Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.</span><span class="sxs-lookup"><span data-stu-id="1007c-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="1007c-138">Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi.</span><span class="sxs-lookup"><span data-stu-id="1007c-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="1007c-139">Vedere [Informazioni di base sul dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) per maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="1007c-139">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Pagina Attiva record.](../media/activaterecords.png)

2. <span data-ttu-id="1007c-141">Seguire i passaggi della procedura guidata, la posta elettronica e gli altri servizi saranno configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1007c-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="1007c-142">Proteggere l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1007c-142">Protect your organization</span></span> 

<span data-ttu-id="1007c-143">I criteri impostati nella procedura guidata vengono applicati automaticamente a un gruppo [di sicurezza](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominato Tutti *gli utenti.*</span><span class="sxs-lookup"><span data-stu-id="1007c-143">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="1007c-144">È inoltre possibile creare gruppi aggiuntivi a cui assegnare criteri nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1007c-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="1007c-145">In Aumenta la protezione dalle minacce **informatiche** avanzate, è consigliabile accettare le impostazioni predefinite per consentire a [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) di analizzare file e collegamenti nelle app di Office.</span><span class="sxs-lookup"><span data-stu-id="1007c-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Screenshot della pagina Aumenta protezione.](../media/increasetreatprotection.png)


2. <span data-ttu-id="1007c-147">Nella pagina **Impedisci** perdite di dati sensibili accettare le impostazioni predefinite per attivare prevenzione della perdita dei dati (DLP) di Office 365 per tenere traccia dei dati sensibili nelle app di Office e impedire la condivisione accidentale di questi dati all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1007c-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="1007c-148">Nella pagina **Proteggi i dati in Office** per dispositivi mobili lasciare selezionata la gestione delle app per dispositivi mobili, espandere le impostazioni ed esaminarle e quindi selezionare Crea criteri di gestione delle app per dispositivi **mobili.**</span><span class="sxs-lookup"><span data-stu-id="1007c-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Screenshot of Protect data in Office for mobile page.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="1007c-150">Proteggere i PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="1007c-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="1007c-151">Sulla barra di spostamento sinistra seleziona **Configurazione** e quindi, in Accesso e **sicurezza,** scegli Proteggi **i computer Windows 10.**</span><span class="sxs-lookup"><span data-stu-id="1007c-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="1007c-152">Scegliere **Visualizza** per iniziare.</span><span class="sxs-lookup"><span data-stu-id="1007c-152">Choose **View** to get started.</span></span> <span data-ttu-id="1007c-153">Per istruzioni complete, vedi proteggere i [computer Windows 10.](secure-win-10-pcs.md)</span><span class="sxs-lookup"><span data-stu-id="1007c-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="1007c-154">Distribuire le app client di Office 365</span><span class="sxs-lookup"><span data-stu-id="1007c-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="1007c-155">Se si è scelto di installare automaticamente le app di Office durante l'installazione, le app verranno installate nei dispositivi Windows 10 dopo che gli utenti hanno eseguito l'accesso ad Azure AD dai propri dispositivi Windows, usando le credenziali di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1007c-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="1007c-156">Per installare Office su dispositivi mobili iOS o Android, vedere Configurare i dispositivi mobili per gli utenti di [Microsoft 365 Business Premium.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="1007c-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="1007c-157">È inoltre possibile installare Office singolarmente.</span><span class="sxs-lookup"><span data-stu-id="1007c-157">You can also install Office individually.</span></span> <span data-ttu-id="1007c-158">Per istruzioni, vedere installare Office in [un PC o mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="1007c-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="1007c-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1007c-159">See also</span></span>

[<span data-ttu-id="1007c-160">Video di formazione su Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="1007c-160">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
