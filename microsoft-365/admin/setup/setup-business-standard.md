---
title: Configurare Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Quando si acquista Microsoft 365 Business Standard, si può scegliere di usare un dominio di cui si è proprietari o di acquistarne uno al momento dell'iscrizione.
ms.openlocfilehash: 861a9e38f10f0cd654e2b10c1879811cd668bc1f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393812"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="0a88e-103">Configurare Microsoft Business Standard</span><span class="sxs-lookup"><span data-stu-id="0a88e-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="0a88e-104">Aggiungere il proprio dominio per personalizzare l’accesso</span><span class="sxs-lookup"><span data-stu-id="0a88e-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="0a88e-105">Quando si acquista Microsoft 365 Business Standard, si può scegliere di usare un dominio di cui si è proprietari o di acquistarne uno durante l’iscrizione.</span><span class="sxs-lookup"><span data-stu-id="0a88e-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="0a88e-106">Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="0a88e-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="0a88e-107">Autenticarsi allì[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le proprie credenziali globali di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0a88e-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="0a88e-108">Scegliere **Vai alla configurazione** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="0a88e-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="0a88e-109">Nella pagina **Installa le tue app di Office**, è possibile installare le app sul proprio computer.</span><span class="sxs-lookup"><span data-stu-id="0a88e-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="0a88e-110">Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0a88e-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0a88e-p101">Se un dominio è stato acquistato durante l'iscrizione, il passaggio **Aggiungi un dominio** non comparirà. In alternativa, andare a [Aggiungi utenti](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="0a88e-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="0a88e-113">Seguire i passaggi della procedura guidata per [creare record DNS presso un provider DNS per Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="0a88e-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="0a88e-114">Se si conosce l'host del dominio, vedere anche [Aggiungere un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="0a88e-114">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="0a88e-115">Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.</span><span class="sxs-lookup"><span data-stu-id="0a88e-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="0a88e-117">Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="0a88e-117">Add users and assign licenses</span></span>

<span data-ttu-id="0a88e-118">Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](../add-users/add-users.md) nell’interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0a88e-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="0a88e-119">Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="0a88e-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="0a88e-120">Aggiungere utenti nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="0a88e-120">Add users in the wizard</span></span>

<span data-ttu-id="0a88e-121">A tutti gli utenti aggiunti nella procedura guidata viene assegnata automaticamente una licenza di Microsoft 365 Business Standard.</span><span class="sxs-lookup"><span data-stu-id="0a88e-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="0a88e-p104">Se l'abbonamento a Microsoft 365 Business Standard include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un’opzione per assegnare le licenze a questi utenti.</span><span class="sxs-lookup"><span data-stu-id="0a88e-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="0a88e-p105">Dopo aver aggiunto gli utenti, sarà disponibile anche un'opzione per la condivisione delle credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="0a88e-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="0a88e-126">Connettere il proprio dominio</span><span class="sxs-lookup"><span data-stu-id="0a88e-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="0a88e-127">Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="0a88e-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="0a88e-128">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="0a88e-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="0a88e-129">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="0a88e-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="0a88e-130">Se ciò non si verifica, [Modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="0a88e-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="0a88e-131">Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**.</span><span class="sxs-lookup"><span data-stu-id="0a88e-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="0a88e-132">Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.</span><span class="sxs-lookup"><span data-stu-id="0a88e-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="0a88e-p108">Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi. Vedere [dati principali domini](/office365/admin/get-help-with-domains/dns-basics) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0a88e-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="0a88e-135">Seguire i passaggi della procedura guidata, la posta elettronica e gli altri servizi saranno configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0a88e-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="0a88e-136">Una volta completato il processo di iscrizione, si verrà reindirizzati all'interfaccia di amministrazione, in cui si seguirà una procedura guidata per l'installazione delle app di Office, l'aggiunta del dominio, l'aggiunta degli utenti e l'assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="0a88e-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="0a88e-137">Dopo aver completato la configurazione iniziale, è possibile usare la pagina **Configurazione** dell'interfaccia di amministrazione per continuare a configurare i servizi disponibili con gli abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="0a88e-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="0a88e-138">Per altre informazioni sulla configurazione guidata e sulla pagina **Configurazione** dell'interfaccia di amministrazione, vedere [Differenze tra la configurazione guidata e la pagina Configurazione](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="0a88e-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="0a88e-139">Completare la configurazione</span><span class="sxs-lookup"><span data-stu-id="0a88e-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="0a88e-140">Configurare Outlook per la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0a88e-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="0a88e-141">Nel menu Start di Windows cercare Outlook e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="0a88e-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="0a88e-142">Se si usa un Mac, aprire Outlook dalla barra degli strumenti o cercarlo con il Finder.</span><span class="sxs-lookup"><span data-stu-id="0a88e-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="0a88e-143">Se Outlook è già stato installato, nella pagina di benvenuto selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0a88e-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="0a88e-144">Scegliere **File** \> **Informazioni** \> **Aggiungi account**.</span><span class="sxs-lookup"><span data-stu-id="0a88e-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="0a88e-145">Immettere il proprio indirizzo di posta elettronica Microsoft e selezionare **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="0a88e-145">Enter your Microsoft email address and select **Connect**.</span></span>

## <a name="watch-set-up-outlook-for-email"></a><span data-ttu-id="0a88e-146">Video: Configurare Outlook per la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0a88e-146">Watch: Set up Outlook for email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="0a88e-147">Per altre informazioni, vedere [Configurare Outlook per la posta elettronica](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="0a88e-147">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="0a88e-148">Importare la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0a88e-148">Import email</span></span>

<span data-ttu-id="0a88e-149">Se si stava usando Outlook con un altro account di posta elettronica, è possibile importare i messaggi, il calendario e i contatti precedenti nel nuovo account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0a88e-149">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="0a88e-150">**Esportare i vecchi messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="0a88e-150">**Export your old email**</span></span>

    <span data-ttu-id="0a88e-151">In Outlook scegliere **File** \> **Apri ed esporta&amp;** \> **Importa/Esporta**.</span><span class="sxs-lookup"><span data-stu-id="0a88e-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="0a88e-152">Selezionare **Esporta in un file** e quindi seguire le istruzioni per esportare il file di dati di Outlook (pst) e le eventuali sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="0a88e-152">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="0a88e-153">**Importare i vecchi messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="0a88e-153">**Import your old email**</span></span>

    <span data-ttu-id="0a88e-154">In Outlook scegliere **File** \> **Apri ed&amp; esporta** \> **Importa/Esporta**.</span><span class="sxs-lookup"><span data-stu-id="0a88e-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="0a88e-155">Questa volta, selezionare **Importa dati da altri programmi o file** e seguire le istruzioni per importare il file di backup creato al momento dell'esportazione dei vecchi messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0a88e-155">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

## <a name="watch-import-and-redirect-email"></a><span data-ttu-id="0a88e-156">Video: Importare e reindirizzare la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0a88e-156">Watch: Import and redirect email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="0a88e-157">Per altre informazioni, vedere [Importare la posta elettronica con Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="0a88e-157">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="0a88e-158">È anche possibile usare l’interfaccia di amministrazione di Exchange per importare la posta elettronica di tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0a88e-158">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="0a88e-159">Per altre informazioni, vedere [Migrazione di account multipli di posta elettronica](/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="0a88e-159">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="0a88e-160">Usare un sito Web pubblico</span><span class="sxs-lookup"><span data-stu-id="0a88e-160">Use a public website</span></span>

<span data-ttu-id="0a88e-161">Microsoft 365 non include un sito Web pubblico che possa essere usato dall'azienda.</span><span class="sxs-lookup"><span data-stu-id="0a88e-161">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="0a88e-162">Se si vuole configurarne uno, è consigliabile usare un partner Microsoft, come GoDaddy o WIX.</span><span class="sxs-lookup"><span data-stu-id="0a88e-162">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="0a88e-163">Nell'interfaccia di amministrazione passare a **Risorse** e quindi selezionare **Sito Web pubblico**.</span><span class="sxs-lookup"><span data-stu-id="0a88e-163">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="0a88e-164">Selezionare **Altre informazioni** sotto una delle opzioni, quindi effettuare l'iscrizione con un partner di siti Web e usare i suoi strumenti per configurare e progettare il sito.</span><span class="sxs-lookup"><span data-stu-id="0a88e-164">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

## <a name="watch-create-your-business-website"></a><span data-ttu-id="0a88e-165">Video: Creare il sito Web dell'azienda</span><span class="sxs-lookup"><span data-stu-id="0a88e-165">Watch: Create your business website</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a><span data-ttu-id="0a88e-166">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="0a88e-166">Related content</span></span>

<span data-ttu-id="0a88e-167">[Creare un sito Web](../../business-video/create-web-site.md) (video)</span><span class="sxs-lookup"><span data-stu-id="0a88e-167">[Create a website](../../business-video/create-web-site.md) (video)</span></span>\
<span data-ttu-id="0a88e-168">[Microsoft 365 per l'azienda](../../business-video/index.yml) (collegamento alla pagina)</span><span class="sxs-lookup"><span data-stu-id="0a88e-168">[Microsoft 365 for your business](../../business-video/index.yml) (link page)</span></span>
