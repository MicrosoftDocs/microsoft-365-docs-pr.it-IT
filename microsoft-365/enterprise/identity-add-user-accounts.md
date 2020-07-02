---
title: 'Passaggio 4: Aggiungere gli account utente'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Aggiungere account utente e gruppi direttamente nel cloud o sincronizzandoli con la directory locale.
ms.openlocfilehash: 2a54044737f5b924bd619d5a6c7c72091dc7a0d1
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005835"
---
# <a name="step-4-add-your-user-accounts"></a><span data-ttu-id="1c3f0-103">Passaggio 4: Aggiungere gli account utente</span><span class="sxs-lookup"><span data-stu-id="1c3f0-103">Step 4: Add your user accounts</span></span>

![Fase 2 - Identità](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a><span data-ttu-id="1c3f0-105">Creare gli account utente per l'identità solo cloud</span><span class="sxs-lookup"><span data-stu-id="1c3f0-105">Create your user accounts for cloud-only identity</span></span>

<span data-ttu-id="1c3f0-106">Per l'identità solo cloud, creare gli utenti e i gruppi in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1c3f0-106">For cloud-only identity, create your users and groups in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="1c3f0-107">È possibile usare:</span><span class="sxs-lookup"><span data-stu-id="1c3f0-107">You can use:</span></span>

- <span data-ttu-id="1c3f0-108">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1c3f0-108">The Microsoft 365 admin center</span></span>
- <span data-ttu-id="1c3f0-109">Il portale di Azure</span><span class="sxs-lookup"><span data-stu-id="1c3f0-109">The Azure portal</span></span>
- <span data-ttu-id="1c3f0-110">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c3f0-110">Azure PowerShell</span></span>

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a><span data-ttu-id="1c3f0-111">Sincronizzare le identità per l'identità ibrida</span><span class="sxs-lookup"><span data-stu-id="1c3f0-111">Synchronize identities for hybrid identity</span></span>

<span data-ttu-id="1c3f0-112">*Questo passaggio è obbligatorio per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1c3f0-112">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="1c3f0-113">In questa sezione si sincronizzerà l'ambiente Active Directory Domain Services (AD DS) locale con il tenant di Azure AD usato da Office 365, Microsoft Intune e altri servizi basati sul cloud inclusi in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-113">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure AD tenant used by Office 365, Microsoft Intune, and other cloud-based services included with Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="1c3f0-114">Azure AD Connect è lo strumento Microsoft supportato che guida gli amministratori nel processo di sincronizzazione delle sole identità realmente necessarie degli ambienti Azure AD DS con una o più foreste con il proprio tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-114">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="1c3f0-115">La figura seguente mostra il processo di base per la sincronizzazione di Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-115">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Come Azure AD Connect sincronizza la directory locale con Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. <span data-ttu-id="1c3f0-117">Quando Azure AD Connect viene avviato in un server, comunica con AD DS per rilevare le modifiche apportate ad account, gruppi e contatti.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-117">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="1c3f0-118">Quindi Azure AD Connect invia le modifiche al tenant di Azure AD dell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-118">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="1c3f0-119">The first decision in your hybrid identity solution is your authentication requirement.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-119">The first decision in your hybrid identity solution is your authentication requirement.</span></span> <span data-ttu-id="1c3f0-120">The following options are options:</span><span class="sxs-lookup"><span data-stu-id="1c3f0-120">The following options are options:</span></span>

- <span data-ttu-id="1c3f0-121">With **managed authentication**, Azure AD handles the authentication process for user sign-in.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-121">With **managed authentication**, Azure AD handles the authentication process for user sign-in.</span></span> <span data-ttu-id="1c3f0-122">There are two methods for managed authentication:</span><span class="sxs-lookup"><span data-stu-id="1c3f0-122">There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="1c3f0-123">**Sincronizzazione dell'hash delle password** [Opzione consigliata e obbligatoria per alcune funzionalità Premium].</span><span class="sxs-lookup"><span data-stu-id="1c3f0-123">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="1c3f0-124">Questo è il modo più semplice per abilitare l'autenticazione per gli oggetti directory locali in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-124">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="1c3f0-125">Azure AD Connect estrae la password con hash da Active Directory Domain Services, esegue ulteriori procedure di sicurezza sull'hash della password e la sincronizza con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-125">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password hash, and synchronizes it to Azure AD.</span></span> <span data-ttu-id="1c3f0-126">Per altre informazioni, vedere [Implementare la sincronizzazione dell'hash delle password con il servizio di sincronizzazione Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="1c3f0-126">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="1c3f0-127">L'**autenticazione pass-through di Azure AD** offre una soluzione di convalida delle password semplice per i servizi basati su Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-127">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="1c3f0-128">Usa un agente in esecuzione in uno o più server locali per convalidare le autenticazioni utente direttamente con Active Directory Domain Services locale.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-128">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="1c3f0-129">Per altre informazioni, vedere [Accesso utente con l'autenticazione pass-through di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="1c3f0-129">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="1c3f0-130">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-130">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in.</span></span> <span data-ttu-id="1c3f0-131">The identity provider can provide additional authentication methods, such as smartcard-based authentication.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-131">The identity provider can provide additional authentication methods, such as smartcard-based authentication.</span></span> <span data-ttu-id="1c3f0-132">For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).</span><span class="sxs-lookup"><span data-stu-id="1c3f0-132">For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).</span></span>

<span data-ttu-id="1c3f0-133">Guardare questo video per una panoramica dei modelli di identità e dell'autenticazione per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-133">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="1c3f0-134"><p> </p></span><span class="sxs-lookup"><span data-stu-id="1c3f0-134"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="1c3f0-135">Una volta determinata la soluzione per le identità ibride, scaricare ed eseguire lo [Strumento IdFix DirSync Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) per analizzare Active Directory Domain Services e cercare eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-135">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="1c3f0-136">Dopo aver risolto tutti i problemi identificati tramite lo strumento IdFix, vedere [Implementare la sincronizzazione dell'hash delle password](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) per installare lo strumento Azure AD Connect e configurare la sincronizzazione delle directory tra Active Directory Domain Services locale e il tenant di Azure AD per l’abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-136">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="1c3f0-137">Dopo l'inizio della sincronizzazione, sarà possibile mantenere gli account utente e i gruppi con il provider di identità locale, come Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-137">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="1c3f0-138">Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-138">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="1c3f0-139">Per i requisiti consigliati per gli ambienti ibridi, vedere la colonna **Active Directory con sincronizzazione delle password hash** in [Prerequisiti](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="1c3f0-139">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="1c3f0-140">Per i requisiti consigliati per gli ambienti solo cloud, vedere la colonna **Solo cloud** in [Prerequisiti](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="1c3f0-140">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="1c3f0-141">Quando gli utenti e i gruppi locali sono presenti in Azure AD, è possibile iniziare ad assegnare le licenze e a usare carichi di lavoro di produttività, ad esempio OneDrive for Business e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-141">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using productivity workloads such as OneDrive for Business and Exchange Online.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="1c3f0-143">Guida del laboratorio di testing: sincronizzazione hash delle password</span><span class="sxs-lookup"><span data-stu-id="1c3f0-143">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="1c3f0-144">Guida del laboratorio di testing: autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="1c3f0-144">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="1c3f0-145">Come checkpoint provvisorio, vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-sync) relativi a questa sezione.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="1c3f0-146">Monitorare l'integrità della sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="1c3f0-146">Monitor synchronization health</span></span>

<span data-ttu-id="1c3f0-147">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="1c3f0-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="1c3f0-148">In questa sezione verrà installato un agente di Azure AD Connect Health in ogni controller di dominio AD DS locale per monitorare l'infrastruttura di gestione delle identità e i servizi di sincronizzazione forniti da Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-148">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="1c3f0-149">Le informazioni sul monitoraggio vengono rese disponibili nel portale di Azure AD Connect Health, dove è possibile visualizzare avvisi, il monitoraggio delle prestazioni, analisi sull'utilizzo e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-149">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Componenti di Azure AD Connect Health](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

<span data-ttu-id="1c3f0-151">La decisione di progettazione chiave su come usare Azure AD Connect Health si basa sul modo in cui si utilizza Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="1c3f0-151">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="1c3f0-152">Se si usa l'opzione **autenticazione gestita** iniziare con [Uso di Azure AD Connect Health con la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) per comprendere e configurare Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-152">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="1c3f0-153">Se si stanno sincronizzando soli i nomi di account e gruppi tramite l'**autenticazione federata** con Active Directory Federation Services (AD FS), iniziare con [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) per comprendere e configurare Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-153">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="1c3f0-154">Dopo aver completato questa sezione:</span><span class="sxs-lookup"><span data-stu-id="1c3f0-154">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="1c3f0-155">L'agente di Azure AD Connect Health è installato su ciascuno dei server del provider di identità locale.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-155">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="1c3f0-156">Il portale di Azure AD Connect Health mostra lo stato corrente dell'infrastruttura locale e delle attività di sincronizzazione con il tenant di Azure AD per l’abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-156">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

<span data-ttu-id="1c3f0-157">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-sync-health) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-157">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="1c3f0-158">Semplificare gli aggiornamenti delle password</span><span class="sxs-lookup"><span data-stu-id="1c3f0-158">Simplify password updates</span></span>

<span data-ttu-id="1c3f0-159">*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1c3f0-159">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="1c3f0-160">In questa sezione verrà consentito agli utenti di reimpostare la password con Azure Active Directory (Azure AD), che è poi replicata nei servizi di Dominio di Active Directory (AD DS) locali.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-160">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="1c3f0-161">Questo processo è noto come writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-161">This process is known as password writeback.</span></span> <span data-ttu-id="1c3f0-162">Con il writeback delle password gli utenti non hanno bisogno di aggiornare le password tramite Active Directory Domain Services locale in cui vengono archiviati gli account utente e i relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-162">With password writeback, users don’t need to update their passwords through the on-premises AD DS where user accounts and their attributes are stored.</span></span> <span data-ttu-id="1c3f0-163">Questo risulta particolarmente utile per gli utenti remoti o mobili che non dispongono di una connessione remota alla rete locale.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-163">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="1c3f0-164">Il writeback delle password è necessario per utilizzare al meglio le capacità di Azure AD Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui sia stato rilevato un alto rischio di violazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-164">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="1c3f0-165">Per ulteriori informazioni e istruzioni di configurazione, vedere [Reimpostazione password self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="1c3f0-165">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="1c3f0-166">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-166">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="1c3f0-167">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="1c3f0-167">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="1c3f0-169">Guida al lab di test: writeback della password</span><span class="sxs-lookup"><span data-stu-id="1c3f0-169">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="1c3f0-170">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pw-writeback) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="1c3f0-170">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

|||
|:-------|:-----|
|![Passaggio 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="1c3f0-172">Usare i gruppi per la gestione</span><span class="sxs-lookup"><span data-stu-id="1c3f0-172">Use groups for management</span></span>](identity-use-group-management.md) |
