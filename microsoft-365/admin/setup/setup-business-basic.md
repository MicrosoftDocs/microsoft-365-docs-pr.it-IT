---
title: Configurare Microsoft 365 Business Basic
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Informazioni su come configurare la sottoscrizione a Microsoft 365 Business Basic.
ms.openlocfilehash: 9b448db2a6b8c78bb5265b1e80a01e93c9a6c6ca
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778902"
---
# <a name="set-up-microsoft-365-business-basic"></a><span data-ttu-id="a1265-103">Configurare Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="a1265-103">Set up Microsoft 365 Business Basic</span></span>

 <span data-ttu-id="a1265-104">È possibile guardare un breve video sulla configurazione di Microsoft 365 Business Basic.</span><span class="sxs-lookup"><span data-stu-id="a1265-104">Watch a short video about setting up Microsoft 365 Business Basic.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

<span data-ttu-id="a1265-105">Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="a1265-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="a1265-106">Aggiungere il proprio dominio per personalizzare l’accesso</span><span class="sxs-lookup"><span data-stu-id="a1265-106">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="a1265-107">Quando si acquista Microsoft 365 Business Basic, si può scegliere di usare un dominio di cui si è proprietari o di acquistarne uno durante l’iscrizione.</span><span class="sxs-lookup"><span data-stu-id="a1265-107">When you purchase Microsoft 365 Business Basic, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="a1265-108">Se è stato acquistato un nuovo dominio al momento dell’iscrizione, il dominio è già configurato ed è possibile [Aggiungere utenti e assegnare le licenze](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="a1265-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="a1265-109">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="a1265-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a1265-110">Se si usa Office 365 Germany, passare a questa [interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041).</span><span class="sxs-lookup"><span data-stu-id="a1265-110">If you're using Office 365 Germany, go to [this admin center](https://go.microsoft.com/fwlink/p/?linkid=848041).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a1265-111">Se si usa Office 365 gestito da 21Vianet, passare a questa [interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627).</span><span class="sxs-lookup"><span data-stu-id="a1265-111">If you're using Office 365 operated by 21Vianet, go to [this admin center.](https://go.microsoft.com/fwlink/p/?linkid=850627).</span></span>

::: moniker-end 

2. <span data-ttu-id="a1265-112">Scegliere **Vai alla configurazione** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a1265-112">Choose **Go to setup** to start the wizard.</span></span>
    
3. <span data-ttu-id="a1265-113">Nel passaggio **Aggiungi dominio** immettere il nome del dominio che si vuole usare (ad esempio contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a1265-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a1265-114">Se un dominio è stato acquistato durante l’iscrizione, il passaggio **Aggiungi un dominio** non comparirà.</span><span class="sxs-lookup"><span data-stu-id="a1265-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="a1265-115">Proseguire al passaggio [Aggiungi utenti](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="a1265-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="a1265-116">Seguire i passaggi della procedura guidata per [creare record DNS presso un provider DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="a1265-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="a1265-117">Se si conosce l’host del dominio, vedere anche le [istruzioni specifiche dell’host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="a1265-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="a1265-118">Se il proprio provider di hosting è GoDaddy o un altro host abilitato con [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), il processo è semplice e viene richiesto di eseguire l’accesso e lasciare che Microsoft Authenticate completi l’autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a1265-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Nella pagina di conferma dell’accesso di GoDaddy, selezionare Autorizza.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="a1265-120">Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="a1265-120">Add users and assign licenses</span></span>

<span data-ttu-id="a1265-121">Gli utenti possono essere aggiunti nella procedura guidata, ma è anche possibile [aggiungere utenti in seguito](../add-users/add-users.md) nell’interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="a1265-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="a1265-122">Inoltre, se si dispone di un controller di dominio, è possibile aggiungere utenti con [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="a1265-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="a1265-123">Aggiungere utenti nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="a1265-123">Add users in the wizard</span></span>

<span data-ttu-id="a1265-124">A tutti gli utenti aggiunti nella procedura guidata viene assegnata automaticamente una licenza di Microsoft 365 Business Basic.</span><span class="sxs-lookup"><span data-stu-id="a1265-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Basic license.</span></span>

1. <span data-ttu-id="a1265-125">Se la sottoscrizione a Microsoft 365 Business Basic include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un’opzione per assegnare le licenze a questi utenti.</span><span class="sxs-lookup"><span data-stu-id="a1265-125">If your Microsoft 365 Business Basic subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="a1265-126">Procedere aggiungendo le licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="a1265-126">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="a1265-127">Una volta aggiunti gli utenti, sarà disponibile un’opzione per condividere le credenziali con i nuovi utenti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="a1265-127">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="a1265-128">È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="a1265-128">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="a1265-129">Connettere il proprio dominio</span><span class="sxs-lookup"><span data-stu-id="a1265-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="a1265-130">Se si è scelto di usare il dominio .onmicrosoft o se si usa Azure AD Connect per configurare gli utenti, questo passaggio non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="a1265-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="a1265-131">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="a1265-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="a1265-132">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="a1265-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="a1265-133">Se ciò non si verifica, [Modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="a1265-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="a1265-134">Se si dispone di record DNS esistenti, ad esempio un sito Web, ma il proprio host DNS è abilitato per [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), scegliere **Aggiungi record per me**.</span><span class="sxs-lookup"><span data-stu-id="a1265-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="a1265-135">Nella pagina **Scegli i tuoi servizi online**, accettare tutti i predefiniti, scegliere **Successivo**, e scegliere **Autorizza** nella pagina del proprio host DNS.</span><span class="sxs-lookup"><span data-stu-id="a1265-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="a1265-136">Se si dispone di record DNS esistenti con altri host DNS (non abilitati per il protocollo Domain Connect), è possibile gestire i propri record DNS per assicurarsi che i servizi esistenti restino connessi.</span><span class="sxs-lookup"><span data-stu-id="a1265-136">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="a1265-137">Vedere [Informazioni di base sul dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) per maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="a1265-137">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="a1265-138">Seguire i passaggi della procedura guidata, la posta elettronica e gli altri servizi saranno configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a1265-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="a1265-139">Una volta completato il processo di iscrizione si verrà reindirizzati all’interfaccia di amministrazione, dove è possibile aggiungere gli utenti e assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="a1265-139">When the signup process is complete, you'll be directed to the admin center, where you can add users, and assign licenses.</span></span> <span data-ttu-id="a1265-140">Dopo aver completato la configurazione iniziale, è possibile usare la pagina **Configurazione** dell'interfaccia di amministrazione per continuare a configurare i servizi disponibili con gli abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="a1265-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="a1265-141">Per altre informazioni sulla configurazione guidata e sulla pagina **Configurazione** dell'interfaccia di amministrazione, vedere [Differenze tra la configurazione guidata e la pagina Configurazione](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="a1265-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>