---
title: Configurare Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Scopri i passaggi di configurazione per Microsoft 365 Business Premium, tra cui l'aggiunta di un dominio e di utenti, la configurazione dei criteri di sicurezza e altro ancora.
ms.openlocfilehash: 74a98e915577cf86ec32a706bd3b8f558f49db95
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227640"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="d6665-103">Configurare i Microsoft 365 Business Premium nella configurazione guidata</span><span class="sxs-lookup"><span data-stu-id="d6665-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

## <a name="watch-overview-of-microsoft-365-setup"></a><span data-ttu-id="d6665-104">Watch: Overview of Microsoft 365 setup</span><span class="sxs-lookup"><span data-stu-id="d6665-104">Watch: Overview of Microsoft 365 setup</span></span>

<span data-ttu-id="d6665-105">Guarda questo video per una panoramica dell'Microsoft 365 Business Premium configurazione.</span><span class="sxs-lookup"><span data-stu-id="d6665-105">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="d6665-106">Aggiungere il dominio, gli utenti e configurare i criteri</span><span class="sxs-lookup"><span data-stu-id="d6665-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="d6665-107">Quando acquisti Microsoft 365 Business Premium, hai la possibilità di usare un dominio di tua proprietà o acquistarne uno durante [l'iscrizione.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="d6665-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="d6665-108">Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="d6665-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="d6665-109">Aggiungere il proprio dominio per personalizzare l’accesso</span><span class="sxs-lookup"><span data-stu-id="d6665-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="d6665-110">Autenticarsi allì[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le proprie credenziali globali di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d6665-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="d6665-111">Scegliere **Vai alla configurazione** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d6665-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Seleziona Vai alla configurazione.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="d6665-113">Nella pagina **Installa le tue app di Office**, è possibile installare le app sul proprio computer.</span><span class="sxs-lookup"><span data-stu-id="d6665-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="d6665-114">Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d6665-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d6665-p101">Se un dominio è stato acquistato durante l'iscrizione, il passaggio **Aggiungi un dominio** non comparirà. In alternativa, andare a [Aggiungi utenti](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="d6665-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Screenshot della pagina Personalizza l'accesso.](../media/adddomain.png)

    
4. <span data-ttu-id="d6665-118">Seguire i passaggi della procedura guidata per creare record DNS presso qualsiasi provider di [hosting DNS per](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Microsoft 365 che verifica di essere proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="d6665-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="d6665-119">Se si conosce l'host di dominio, vedere anche [Aggiungere un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="d6665-119">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="d6665-120">Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d6665-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="d6665-122">Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="d6665-122">Add users and assign licenses</span></span>

<span data-ttu-id="d6665-123">Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](../admin/add-users/add-users.md) nell’interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d6665-123">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="d6665-124">Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="d6665-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="d6665-125">Aggiungere utenti nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="d6665-125">Add users in the wizard</span></span>

<span data-ttu-id="d6665-126">A tutti gli utenti aggiunti nella procedura guidata viene assegnata automaticamente una Microsoft 365 Business Premium licenza.</span><span class="sxs-lookup"><span data-stu-id="d6665-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Screenshot della pagina Aggiungi nuovi utenti della procedura guidata](../media/addnewuserspage.png)

1. <span data-ttu-id="d6665-128">Se la sottoscrizione Microsoft 365 Business Premium ha utenti esistenti (ad esempio, se hai usato Azure AD Connessione), ottieni un'opzione per assegnare le licenze a loro ora.</span><span class="sxs-lookup"><span data-stu-id="d6665-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="d6665-129">Procedere aggiungendo le licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="d6665-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="d6665-p105">Dopo aver aggiunto gli utenti, sarà disponibile anche un'opzione per la condivisione delle credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="d6665-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="d6665-132">Connettere il proprio dominio</span><span class="sxs-lookup"><span data-stu-id="d6665-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="d6665-133">Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="d6665-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="d6665-134">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="d6665-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="d6665-135">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="d6665-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="d6665-136">In caso contrario, modificare i server dei nomi per [configurare Microsoft 365 con qualsiasi registrar .](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="d6665-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="d6665-137">Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**.</span><span class="sxs-lookup"><span data-stu-id="d6665-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="d6665-138">Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.</span><span class="sxs-lookup"><span data-stu-id="d6665-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="d6665-p108">Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi. Vedere [dati principali domini](/office365/admin/get-help-with-domains/dns-basics) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d6665-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Pagina Attiva record.](../media/activaterecords.png)

2. <span data-ttu-id="d6665-142">Seguire i passaggi della procedura guidata, la posta elettronica e gli altri servizi saranno configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d6665-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="d6665-143">Proteggere l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d6665-143">Protect your organization</span></span> 

<span data-ttu-id="d6665-144">I criteri impostati nella procedura guidata vengono applicati automaticamente a un [gruppo di sicurezza](/office365/admin/create-groups/compare-groups#security-groups) denominato Tutti gli *utenti.*</span><span class="sxs-lookup"><span data-stu-id="d6665-144">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="d6665-145">È inoltre possibile creare gruppi aggiuntivi a cui assegnare criteri nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d6665-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="d6665-146">In Aumentare la protezione dalle minacce **informatiche** avanzate è consigliabile accettare le impostazioni predefinite per consentire a [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) di analizzare file e collegamenti nelle app Office avanzate.</span><span class="sxs-lookup"><span data-stu-id="d6665-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![Screenshot della pagina Aumenta protezione.](../media/increasetreatprotection.png)


2. <span data-ttu-id="d6665-148">Nella pagina **Impedisci** perdite di dati sensibili accettare le impostazioni predefinite per attivare Office 365 Data Loss Prevention (DLP) per tenere traccia dei dati sensibili nelle app di Office e impedire la condivisione accidentale di questi dati all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d6665-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="d6665-149">Nella pagina **Proteggi i dati in Office** per dispositivi mobili, lascia la gestione delle app per dispositivi mobili, espandi le impostazioni e rivedile e quindi seleziona Crea criteri di gestione delle app per dispositivi **mobili.**</span><span class="sxs-lookup"><span data-stu-id="d6665-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Screenshot of Protect data in Office for mobile page.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="d6665-151">Proteggere i PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="d6665-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="d6665-152">Nel riquadro di spostamento sinistro selezionare **Installazione** e quindi, **in** Accesso e sicurezza, scegliere Proteggi i Windows 10 **computer.**</span><span class="sxs-lookup"><span data-stu-id="d6665-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="d6665-153">Scegliere **Visualizza** per iniziare.</span><span class="sxs-lookup"><span data-stu-id="d6665-153">Choose **View** to get started.</span></span> <span data-ttu-id="d6665-154">Per [istruzioni complete, vedere proteggere Windows 10 computer.](secure-win-10-pcs.md)</span><span class="sxs-lookup"><span data-stu-id="d6665-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="d6665-155">Distribuire Office 365 client</span><span class="sxs-lookup"><span data-stu-id="d6665-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="d6665-156">Se hai scelto di installare automaticamente le app Office durante la configurazione, le app verranno installate nei dispositivi Windows 10 dopo che gli utenti hanno eseguito l'accesso ad Azure AD dai dispositivi Windows, usando le credenziali di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d6665-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="d6665-157">Per installare Office dispositivi mobili iOS o Android, vedi [Configurare i dispositivi mobili per Microsoft 365 Business Premium utenti.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="d6665-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="d6665-158">È inoltre possibile installare Office singolarmente.</span><span class="sxs-lookup"><span data-stu-id="d6665-158">You can also install Office individually.</span></span> <span data-ttu-id="d6665-159">Vedi [installare Office su un PC o mac per](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d6665-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="related-content"></a><span data-ttu-id="d6665-160">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="d6665-160">Related content</span></span>

<span data-ttu-id="d6665-161">[Video di formazione su Microsoft 365 per le aziende](../business-video/index.yml) (pagina collegamento)</span><span class="sxs-lookup"><span data-stu-id="d6665-161">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
