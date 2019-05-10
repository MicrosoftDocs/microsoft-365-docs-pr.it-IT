---
title: Configurare Microsoft 365 Business
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
description: Informazioni su come configurare Microsoft 365 business.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660820"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="1bd26-103">Configurare Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="1bd26-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="1bd26-104">Prima di iniziare, vedere [Get Microsoft 365 business](get-microsoft-365-business.md) for sign-up details.</span><span class="sxs-lookup"><span data-stu-id="1bd26-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="1bd26-105">Guardare un [breve video su come configurare Microsoft 365 business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) tramite la configurazione guidata e quando non si dispone di un Active Directory locale</span><span class="sxs-lookup"><span data-stu-id="1bd26-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="1bd26-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="1bd26-106">Overview</span></span>

<span data-ttu-id="1bd26-107">La maggior parte dei passaggi di configurazione può essere effettuata nell'installazione guidata, ma anche le altre opzioni sono elencate.</span><span class="sxs-lookup"><span data-stu-id="1bd26-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="1bd26-108">[Aggiungere il dominio](#add-your-domain-to-personalize-sign-in) Se il dominio è stato acquistato durante l' [iscrizione](sign-up.md), questo passaggio è già stato fatto.</span><span class="sxs-lookup"><span data-stu-id="1bd26-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="1bd26-109">Aggiungere utenti.</span><span class="sxs-lookup"><span data-stu-id="1bd26-109">Add users.</span></span> <span data-ttu-id="1bd26-110">È possibile eseguire questa operazione in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bd26-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="1bd26-111">Nell' [installazione guidata](#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="1bd26-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="1bd26-112">Utilizzare la sincronizzazione della directory per [aggiungere utenti utilizzando Azure ad Connect](#add-users-by-using-azure-ad-connect) se si dispone di Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="1bd26-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="1bd26-113">È inoltre possibile [aggiungere gli utenti in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1bd26-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="1bd26-114">Impostare i criteri di sicurezza e configurare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1bd26-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="1bd26-115">È possibile eseguire questa operazione in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bd26-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="1bd26-116">Nell' [installazione guidata](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="1bd26-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="1bd26-117">Nell'interfaccia di [Amministrazione](#modify-or-add-policies-in-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="1bd26-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="1bd26-118">Nell'interfaccia di [amministrazione di Intune](https://docs.microsoft.com/intune/what-is-device-management).</span><span class="sxs-lookup"><span data-stu-id="1bd26-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="1bd26-119">Configurare e gestire i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1bd26-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="1bd26-120">Quando si aggiunge un dispositivo WIndows 10 ad Azure AD, tutti i criteri vengono applicati a esso.</span><span class="sxs-lookup"><span data-stu-id="1bd26-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="1bd26-121">Configurare le configurazioni dei dispositivi Windows 10 nell' [installazione guidata](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="1bd26-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="1bd26-122">Aggiungere un [nuovo dispositivo Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) AD Azure ad.</span><span class="sxs-lookup"><span data-stu-id="1bd26-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="1bd26-123">Aggiungere un [dispositivo Windows 10 esistente](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) AD Azure ad.</span><span class="sxs-lookup"><span data-stu-id="1bd26-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="1bd26-124">Installare Office 365 business.</span><span class="sxs-lookup"><span data-stu-id="1bd26-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="1bd26-125">È possibile installare automaticamente Office nei dispositivi Windows utilizzando l' [installazione guidata](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="1bd26-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="1bd26-126">[Installare automaticamente Office](auto-install-or-uninstall-office.md) dall'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1bd26-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="1bd26-127">Consente agli utenti di [installare le app di Office](https://docs.microsoft.com/office365/admin/setup/install-applications) per Windows e i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1bd26-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="1bd26-128">Configurare una sicurezza aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="1bd26-128">Set up additional security.</span></span>
    - <span data-ttu-id="1bd26-129">L'installazione guidata aggiunge criteri per proteggere i dispositivi, ma è anche possibile avvalersi delle funzionalità di [sicurezza aggiuntive](#additional-security-settings) per garantire la protezione dei dati, degli account e dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1bd26-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="1bd26-130">Aggiungere il dominio, gli utenti e i criteri di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bd26-130">Add your domain, users and set up policies</span></span>

![Banner che puntano https://aka.ms/aboutM365previewa.](media/m365admincenterchanging.png)

<span data-ttu-id="1bd26-132">Quando si acquista Microsoft 365 business, si ha la possibilità di utilizzare un dominio che si è proprietari o di acquistarne uno durante l' [iscrizione](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="1bd26-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="1bd26-133">Se si è acquistato un nuovo dominio al momento dell'iscrizione, il dominio è tutto configurato ed è possibile spostarsi per [aggiungere utenti e assegnare licenze](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1bd26-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="1bd26-134">Aggiungere il dominio per personalizzare l'accesso</span><span class="sxs-lookup"><span data-stu-id="1bd26-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="1bd26-135">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1bd26-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="1bd26-136">Fare clic su **Aggiungi un dominio** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1bd26-136">Choose **Add a domain** to start the wizard.</span></span>

    ![Selezionare Aggiungi un dominio.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="1bd26-138">Nella procedura guidata, immettere il nome di dominio che si desidera utilizzare (come contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1bd26-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Schermata della pagina Personalizza il tuo accesso.](media/personalizesignin.png)

    
4. <span data-ttu-id="1bd26-140">Seguire i passaggi della procedura guidata per [creare record DNS presso un provider di hosting DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) che verifica che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="1bd26-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="1bd26-141">Se si conosce l'host di dominio, vedere anche le [istruzioni specifiche dell'host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="1bd26-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="1bd26-142">Se il provider di hosting è GoDaddy, il processo è semplice e verrà automaticamente chiesto di accedere e di consentire a Microsoft di eseguire l'autenticazione per conto di:</span><span class="sxs-lookup"><span data-stu-id="1bd26-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Nella pagina Conferma accesso GoDaddy selezionare autorizza.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="1bd26-144">Aggiungere utenti e assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="1bd26-144">Add users and assign licenses</span></span>

<span data-ttu-id="1bd26-145">È possibile aggiungere utenti nella procedura guidata, ma è anche possibile aggiungerli in un [secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1bd26-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="1bd26-146">Inoltre, se si dispone di un controller di dominio locale, è possibile aggiungere utenti con [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="1bd26-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="1bd26-147">Aggiungere gli utenti nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="1bd26-147">Add users in the wizard</span></span>

<span data-ttu-id="1bd26-148">Tutti gli utenti aggiunti nella procedura guidata vengono assegnati automaticamente a una licenza aziendale Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bd26-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="1bd26-149">Se si dispone di un controller di dominio locale e si utilizza Active Directory, vedere [How to ddd Users by using Azure ad Connect](#add-users-by-using-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="1bd26-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![Schermata della pagina Aggiungi nuovi utenti nella procedura guidata](media/addnewuserspage.png)

1. <span data-ttu-id="1bd26-p106">Se l'abbonamento a Microsoft 365 Business include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un'opzione per l'assegnazione di licenze a questi utenti. Procedere con l'aggiunta di licenze anche per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="1bd26-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="1bd26-153">Dopo aver aggiunto gli utenti, si otterrà anche un'opzione per condividere le credenziali con i nuovi utenti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="1bd26-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="1bd26-154">È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.</span><span class="sxs-lookup"><span data-stu-id="1bd26-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="1bd26-155">Ignorare il passaggio relativo alla migrazione dei messaggi di posta elettronica e scegliere **Avanti** nella pagina **Esegui la migrazione dei messaggi di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="1bd26-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="1bd26-156">Se si sta passando da un altro provider di posta elettronica e si desidera copiare i dati in un secondo momento, è possibile [eseguire la migrazione di posta elettronica e contatti a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="1bd26-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="1bd26-157">Aggiungere utenti tramite Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="1bd26-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="1bd26-158">Se si dispone di un controller di dominio locale con Active Directory, è possibile sincronizzare gli utenti con Microsoft 365 business tramite [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="1bd26-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="1bd26-159">Completare questa procedura prima di avviare l'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="1bd26-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="1bd26-160">È possibile scaricarlo nell'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="1bd26-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="1bd26-161">Passare a \*\*\*\* \> utenti **attivi**, selezionare i puntini di controllo nella parte superiore della pagina e quindi selezionare **sincronizzazione directory** per scaricare Azure ad Connect.</span><span class="sxs-lookup"><span data-stu-id="1bd26-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![Nella pagina utenti attivi selezionare ellissi > directory snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="1bd26-163">Se si creano gli utenti in questo modo, sarà comunque necessario assegnare loro le licenze nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1bd26-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="1bd26-164">Continuare a accedere alle app e ai dispositivi associati a un dominio</span><span class="sxs-lookup"><span data-stu-id="1bd26-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="1bd26-165">Se si desidera continuare ad accedere alle app e ai dispositivi associati a un dominio, leggere gli articoli seguenti per due diversi modi per abilitare:</span><span class="sxs-lookup"><span data-stu-id="1bd26-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="1bd26-166">Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="1bd26-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="1bd26-167">Questo è il modo consigliato.</span><span class="sxs-lookup"><span data-stu-id="1bd26-167">This is the recommended way.</span></span>

- [<span data-ttu-id="1bd26-168">Accedere alle risorse locali da un dispositivo di Azure AD-join in Microsoft 365 business</span><span class="sxs-lookup"><span data-stu-id="1bd26-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="1bd26-169">Connettere il dominio</span><span class="sxs-lookup"><span data-stu-id="1bd26-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="1bd26-170">Se si è scelto di utilizzare il dominio. onmicrosoft o di Azure AD Connect per configurare gli utenti, questo passaggio non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="1bd26-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="1bd26-171">Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.</span><span class="sxs-lookup"><span data-stu-id="1bd26-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="1bd26-172">La configurazione guidata rileva in genere il registrar e offre un collegamento a istruzioni dettagliate per l'aggiornamento dei record NS presso il suo sito Web.</span><span class="sxs-lookup"><span data-stu-id="1bd26-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="1bd26-173">In caso contrario, [modificare i server dei nomi per configurare Office 365 con qualsiasi registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="1bd26-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="1bd26-174">Se si dispone di record DNS esistenti, ad esempio un sito Web esistente, sarà necessario gestire i propri record DNS per assicurarsi che i servizi esistenti siano connessi.</span><span class="sxs-lookup"><span data-stu-id="1bd26-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="1bd26-175">Per altre informazioni, vedere [Domain nozioni di base](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="1bd26-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Connect Your Domain Page con i ' ll manage my own DNS Records.](media/connectyourdomainpage.png)

2. <span data-ttu-id="1bd26-177">Seguire i passaggi della procedura guidata e la posta elettronica e altri servizi verranno configurati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1bd26-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="1bd26-178">Impostare i criteri di sicurezza e le configurazioni dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="1bd26-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="1bd26-179">Questi criteri si applicano a tutti gli utenti a cui si assegna una licenza o a un gruppo di utenti, se si decide di assegnare criteri diversi a un set di utenti.</span><span class="sxs-lookup"><span data-stu-id="1bd26-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="1bd26-180">Impostare i criteri nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="1bd26-180">Set up policies in the wizard</span></span>

<span data-ttu-id="1bd26-181">I criteri configurati nella procedura guidata vengono applicati automaticamente a un [gruppo di sicurezza](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) denominato *tutti gli utenti*.</span><span class="sxs-lookup"><span data-stu-id="1bd26-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="1bd26-182">Nella pagina **Proteggi i file di lavoro nei dispositivi mobili** , l'opzione Proteggi i **file di lavoro quando i dispositivi vengono persi o rubati** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1bd26-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="1bd26-183">È possibile abilitare la gestione del modo in cui **gli utenti accedono ai file di Office nei dispositivi mobili**e questo è consigliato.</span><span class="sxs-lookup"><span data-stu-id="1bd26-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Schermata della pagina Proteggi file di lavoro su dispositivi mobili.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="1bd26-185">Se si espande la **protezione dei file di lavoro quando i dispositivi vengono persi o rubati**, i [valori predefiniti](protect-work-files-on-lost-or-stolen-device.md) sono preselezionati:</span><span class="sxs-lookup"><span data-stu-id="1bd26-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![Screenshot dei valori predefiniti per la protezione di file su dispositivi persi.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="1bd26-187">Se si seleziona **Gestisci la modalità di accesso degli utenti ai file di Office nei dispositivi mobili** ed è possibile espanderla, verranno visualizzati i [valori predefiniti](manage-user-access-on-mobile-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="1bd26-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="1bd26-188">È consigliabile accettare i valori predefiniti durante l'installazione per creare criteri di applicazione per Android, iOS e Windows 10 applicabili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1bd26-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="1bd26-189">È possibile creare altri criteri al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="1bd26-189">You can create more policies after setup completes.</span></span>

        ![Schermata delle impostazioni di protezione per i file di Office su dispositivi mobili.](media/useraccessonmobile.png)

2. <span data-ttu-id="1bd26-191">L'ultimo passaggio su Protect data and Devices consente di configurare i criteri per proteggere i dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1bd26-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="1bd26-192">Queste impostazioni vengono applicate automaticamente quando un utente di Windows 10 si connette all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1bd26-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="1bd26-193">È possibile espandere i **dispositivi Windows 10 sicuri** per visualizzare e modificare i [valori predefiniti](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="1bd26-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="1bd26-194">È inoltre possibile scegliere di [installare automaticamente Office](install-office-on-windows-10-during-setup.md) nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1bd26-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Schermata della pagina Imposta configurazione dispositivo Windows 10.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="1bd26-196">Modificare o aggiungere criteri nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="1bd26-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="1bd26-197">Vedere [gestire Microsoft 365 business](manage.md) per i collegamenti agli argomenti su come visualizzare e modificare i criteri di protezione di dispositivi e app e su come rimuovere i dati da o reimpostare i dispositivi utente.</span><span class="sxs-lookup"><span data-stu-id="1bd26-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="1bd26-198">Distribuire e gestire Windows 10</span><span class="sxs-lookup"><span data-stu-id="1bd26-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="1bd26-199">Vedere [configurare i dispositivi Windows per gli utenti di Microsoft 365 business](set-up-windows-devices.md) per connettersi manualmente AD Azure ad, durante l'installazione dei nuovi computer o modificando il profilo di accesso per i computer esistenti.</span><span class="sxs-lookup"><span data-stu-id="1bd26-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="1bd26-200">Utilizzare Autopilot per configurare nuovi dispositivi</span><span class="sxs-lookup"><span data-stu-id="1bd26-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="1bd26-201">È possibile usare [Windows Autopilot](add-autopilot-devices-and-profile.md) per preconfigurare automaticamente i **nuovi** dispositivi Windows 10 per un utente, ma potrebbe essere più facile ottenere un [partner](https://www.microsoft.com/solution-providers/search) che può eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="1bd26-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="1bd26-202">È inoltre possibile accedere a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) e chiedere a un esperto di tecnologia cloud di configurare nuovi dispositivi acquistati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1bd26-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="1bd26-203">Accedere alle risorse locali</span><span class="sxs-lookup"><span data-stu-id="1bd26-203">Access on-premises resources</span></span>

<span data-ttu-id="1bd26-204">Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.</span><span class="sxs-lookup"><span data-stu-id="1bd26-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="1bd26-205">Seguire la procedura descritta in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 business](manage-windows-devices.md) to set this up.</span><span class="sxs-lookup"><span data-stu-id="1bd26-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="1bd26-206">Questo è il metodo preferito e i dispositivi in questo stato sono denominati dispositivi ibridi di Azure AD Uniti.</span><span class="sxs-lookup"><span data-stu-id="1bd26-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="1bd26-207">Se l'azienda dispone di un Active Directory locale che contiene alcune risorse locali, ad esempio condivisioni di file e stampanti, è possibile consentire ai dispositivi di Azure AD-join di accedere a tali risorse attenendosi alla procedura seguente: [accesso alle risorse locali da un Dispositivo di Azure AD-joined in Microsoft 365 business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="1bd26-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="1bd26-208">Distribuire le app client di Office 365</span><span class="sxs-lookup"><span data-stu-id="1bd26-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="1bd26-209">Se si è scelto di installare automaticamente le app di Office durante la configurazione, le app verranno installate nei dispositivi Windows 10 dopo che gli utenti hanno effettuato l'accesso a Azure AD dai propri dispositivi Windows con le credenziali di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1bd26-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="1bd26-210">Per installare Office su dispositivi mobili iOS o Android, vedere [configurare i dispositivi mobili per gli utenti aziendali di Microsoft 365](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="1bd26-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="1bd26-211">È anche possibile installare Office individualmente.</span><span class="sxs-lookup"><span data-stu-id="1bd26-211">You can also install Office individually.</span></span> <span data-ttu-id="1bd26-212">Per istruzioni, vedere [installare Office in un PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) .</span><span class="sxs-lookup"><span data-stu-id="1bd26-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="1bd26-213">Impostazioni di sicurezza aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1bd26-213">Additional security settings</span></span>

<span data-ttu-id="1bd26-214">Oltre all'impostazione sicurezza e conformità nell'installazione guidata, è anche possibile configurare le seguenti impostazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="1bd26-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="1bd26-215">**Protezione antimalware per la posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="1bd26-215">**Email malware protection**</span></span>
- <span data-ttu-id="1bd26-216">**Allegati sicuri di Advanced Threat Protection (ATP)**</span><span class="sxs-lookup"><span data-stu-id="1bd26-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="1bd26-217">**Collegamenti sicuri di ATP**</span><span class="sxs-lookup"><span data-stu-id="1bd26-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="1bd26-218">**Anti-phishing APT**</span><span class="sxs-lookup"><span data-stu-id="1bd26-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="1bd26-219">**Archiviazione Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="1bd26-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="1bd26-220">**Prevenzione della perdita di dati (DLP)**</span><span class="sxs-lookup"><span data-stu-id="1bd26-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="1bd26-221">**Protezione delle informazioni di Azure** (Piano 1)</span><span class="sxs-lookup"><span data-stu-id="1bd26-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="1bd26-222">**Disponibilità del portale di Intune**</span><span class="sxs-lookup"><span data-stu-id="1bd26-222">**Intune portal availability**</span></span>

<span data-ttu-id="1bd26-223">Per iniziare, vedere, [impostare i criteri di sicurezza avanzati](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="1bd26-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="1bd26-224">Vedere anche [i primi 10 modi per proteggere l'azienda Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) per una roadmap delle migliori procedure di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1bd26-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>