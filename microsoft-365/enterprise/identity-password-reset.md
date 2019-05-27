---
title: "Passaggio 5: Semplificare l'accesso per gli utenti"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare la reimpostazione della password self-service (SSPR) per Azure AD.
ms.openlocfilehash: 98118a5891ea8224843faa638b52a421d96e8a0b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287062"
---
# <a name="step-5-simplify-access-for-users"></a><span data-ttu-id="3cef3-103">Passaggio 5: Semplificare l'accesso per gli utenti</span><span class="sxs-lookup"><span data-stu-id="3cef3-103">Step 5: Simplify access for users</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="3cef3-104">Semplificare gli aggiornamenti delle password</span><span class="sxs-lookup"><span data-stu-id="3cef3-104">Simplify password updates</span></span>

<span data-ttu-id="3cef3-105">*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3cef3-105">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3cef3-106">In questa sezione verrà consentito agli utenti di reimpostare la password con Azure Active Directory (Azure AD), che è poi replicata nei servizi di Dominio di Active Directory (AD DS) locali.</span><span class="sxs-lookup"><span data-stu-id="3cef3-106">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3cef3-107">Questo processo è noto come writeback delle password.</span><span class="sxs-lookup"><span data-stu-id="3cef3-107">This process is known as password writeback.</span></span> <span data-ttu-id="3cef3-108">Con il writeback delle password gli utenti non hanno bisogno di aggiornare le password tramite Active Directory Domain Services (AD DS) in cui vengono archiviati gli account utente e i relativi attributi.</span><span class="sxs-lookup"><span data-stu-id="3cef3-108">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="3cef3-109">Questo risulta particolarmente utile per gli utenti remoti o mobili che non dispongono di una connessione remota alla rete locale.</span><span class="sxs-lookup"><span data-stu-id="3cef3-109">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="3cef3-110">Il writeback delle password è necessario per utilizzare al meglio le funzioni di Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui sia stato rilevato un alto rischio di violazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="3cef3-110">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="3cef3-111">Per ulteriori informazioni e istruzioni di configurazione, vedere [Reimpostazione password self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="3cef3-111">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="3cef3-p102">Eseguire l'aggiornamento all'ultima versione di Azure AD Connect per poter usufruire della migliore esperienza possibile e delle nuove caratteristiche appena rilasciate. Per ulteriori informazioni, vedere [Istallazione personalizzata di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="3cef3-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3cef3-115">Guida al lab di test: writeback della password</span><span class="sxs-lookup"><span data-stu-id="3cef3-115">Test Lab Guide: Password reset</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="3cef3-116">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-pw-writeback) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3cef3-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="3cef3-117">Semplificare le reimpostazioni delle password</span><span class="sxs-lookup"><span data-stu-id="3cef3-117">Simplify password resets</span></span>

<span data-ttu-id="3cef3-118">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3cef3-118">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3cef3-119">In questa sezione viene abilitata la reimpostazione della password self-service per consentire agli utenti di reimpostare o sbloccare le password o gli account.</span><span class="sxs-lookup"><span data-stu-id="3cef3-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="3cef3-120">Per segnalare abusi o usi impropri è possibile utilizzare la reportistica dettagliata, che tiene traccia degli accessi degli utenti al sistema, insieme alle notifiche.</span><span class="sxs-lookup"><span data-stu-id="3cef3-120">In this step, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts. To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="3cef3-121">È necessario attivare il writeback della password prima di implementare le reimpostazioni delle password.</span><span class="sxs-lookup"><span data-stu-id="3cef3-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="3cef3-122">Vedere le [istruzioni per implementare la reimpostazione della password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="3cef3-122">See the [instructions to enable password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3cef3-124">Guida al lab di test: reimpostazione della password</span><span class="sxs-lookup"><span data-stu-id="3cef3-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="3cef3-125">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-pw-reset) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3cef3-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this step.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="3cef3-126">Semplificare l'accesso utente</span><span class="sxs-lookup"><span data-stu-id="3cef3-126">Simplify user sign-in</span></span>

<span data-ttu-id="3cef3-127">*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3cef3-127">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3cef3-128">In questa sezione si imposterà Accesso Single Sign-On (SSO) facile di Azure Active Directory per consentire agli utenti di accedere ai servizi che usano gli account utenti di Azure AD senza dover digitare la password e, in molti casi, il nome utente.</span><span class="sxs-lookup"><span data-stu-id="3cef3-128">In this step, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span> <span data-ttu-id="3cef3-129">In questo modo gli utenti possono facilmente accedere alle applicazioni basate su cloud come Office 365, senza aver bisogno di componenti aggiuntivi in loco quali ad esempio server federativi di identità.</span><span class="sxs-lookup"><span data-stu-id="3cef3-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="3cef3-130">L'accesso SSO facile di Azure AD viene configurato con lo strumento Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="3cef3-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="3cef3-131">Vedere le [istruzioni per configurare l'accesso SSO facile ad Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="3cef3-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3cef3-133">Guida del laboratorio di testing: accesso SSO facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="3cef3-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="3cef3-134">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-sso) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3cef3-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="3cef3-135">Personalizzare la pagina di accesso a Office 365</span><span class="sxs-lookup"><span data-stu-id="3cef3-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="3cef3-136">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3cef3-136">*This step is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3cef3-137">In questo passaggio si aggiunge il nome dell'azienda, il logo e altri elementi familiari alla pagina di accesso dell'organizzazione per renderla più riconoscibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3cef3-137">In this step, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="3cef3-138">Con Microsoft 365 Enterprise, è possibile personalizzare l'aspetto delle pagine di accesso e del Riquadro di accesso affinché includano il logo e colori dell'azienda e informazioni sull'utente personalizzate.</span><span class="sxs-lookup"><span data-stu-id="3cef3-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="3cef3-139">Quando un utente prova ad accedere da un dispositivo, vede qualcosa simile a quanto mostrato nell'esempio seguente nella pagina di accesso di Office 365 *prima della personalizzazione*.</span><span class="sxs-lookup"><span data-stu-id="3cef3-139">When a user attempts to sign in from a device, they see something like the following example on the Office 365 sign-in page *before customization*.</span></span>

![Esempio di pagina di accesso di Office 365 prima della personalizzazione](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

<span data-ttu-id="3cef3-141">Ed ecco cosa vedrà lo stesso utente di Contoso Corporation *dopo la personalizzazione*.</span><span class="sxs-lookup"><span data-stu-id="3cef3-141">And here is what the same user of the Contoso Corporation would see *after customization*.</span></span>

![Esempio di pagina di accesso di Office 365 dopo la personalizzazione](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

<span data-ttu-id="3cef3-143">Per ulteriori informazioni, vedere [Aggiungere il marchio dell'organizzazione alla pagina di accesso di Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="3cef3-143">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="3cef3-144">Per istruzioni sulla configurazione, vedere [Aggiungere il marchio dell'organizzazione alle pagine di accesso e Riquadro di accesso](http://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="3cef3-144">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="3cef3-145">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-custom-sign-in) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3cef3-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="3cef3-146">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3cef3-146">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="3cef3-147">Usare i gruppi per facilitare la gestione</span><span class="sxs-lookup"><span data-stu-id="3cef3-147">Use groups for easier management</span></span>](identity-self-service-group-management.md) |


