---
title: 'Passaggio 2: proteggere le password'
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
description: È necessario rendere le password complesse e gestibili all'interno dell'organizzazione.
ms.openlocfilehash: c0ad9e2ad86cb803484e3d350fe112580610f509
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067283"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="cbb60-103">Passaggio 2: proteggere le password</span><span class="sxs-lookup"><span data-stu-id="cbb60-103">Step 2: Secure your passwords</span></span>

![Fase 2: identità](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="cbb60-105">Impedire l'uso di password non consentite</span><span class="sxs-lookup"><span data-stu-id="cbb60-105">Prevent bad passwords</span></span>

<span data-ttu-id="cbb60-106">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="cbb60-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="cbb60-107">Per creare le password degli account utente, tutti gli utenti devono attenersi alla [Guida alle password di Microsoft](https://www.microsoft.com/research/publication/password-guidance/).</span><span class="sxs-lookup"><span data-stu-id="cbb60-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="cbb60-108">Per impedire agli utenti di creare password facilmente determinabili, usare la protezione password di Azure Active Directory, che usa sia un elenco di password non consentite globale che un elenco facoltativo di password non consentite personalizzato, specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cbb60-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="cbb60-109">Ad esempio, è possibile specificare condizioni specifiche per l'organizzazione, come:</span><span class="sxs-lookup"><span data-stu-id="cbb60-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="cbb60-110">Nomi di marchio</span><span class="sxs-lookup"><span data-stu-id="cbb60-110">Brand names</span></span>
- <span data-ttu-id="cbb60-111">Nomi di prodotto</span><span class="sxs-lookup"><span data-stu-id="cbb60-111">Product names</span></span>
- <span data-ttu-id="cbb60-112">Posizioni, ad esempio la sede centrale aziendale</span><span class="sxs-lookup"><span data-stu-id="cbb60-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="cbb60-113">Termini interni specifici della società</span><span class="sxs-lookup"><span data-stu-id="cbb60-113">Company-specific internal terms</span></span>
- <span data-ttu-id="cbb60-114">Abbreviazioni con significato aziendale specifico</span><span class="sxs-lookup"><span data-stu-id="cbb60-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="cbb60-115">È possibile bloccare le password non consentite [nel cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e per [Active Directory Domain Services (AD DS) locale](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="cbb60-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="cbb60-116">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-password-prot) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="cbb60-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="cbb60-117">Semplificare le reimpostazioni delle password</span><span class="sxs-lookup"><span data-stu-id="cbb60-117">Simplify password resets</span></span>

<span data-ttu-id="cbb60-118">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="cbb60-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="cbb60-119">In questa sezione viene abilitata la reimpostazione della password self-service per consentire agli utenti di reimpostare o sbloccare le password o gli account.</span><span class="sxs-lookup"><span data-stu-id="cbb60-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="cbb60-120">Per segnalare abusi o usi impropri è possibile utilizzare la reportistica dettagliata, che tiene traccia degli accessi degli utenti al sistema, insieme alle notifiche.</span><span class="sxs-lookup"><span data-stu-id="cbb60-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="cbb60-121">È necessario attivare il writeback della password prima di implementare le reimpostazioni delle password.</span><span class="sxs-lookup"><span data-stu-id="cbb60-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="cbb60-122">Vedere le [istruzioni per implementare la reimpostazione della password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="cbb60-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="cbb60-124">Guida al lab di test: reimpostazione della password</span><span class="sxs-lookup"><span data-stu-id="cbb60-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="cbb60-125">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-pw-reset) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="cbb60-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="cbb60-126">Semplificare l'accesso utente</span><span class="sxs-lookup"><span data-stu-id="cbb60-126">Simplify user sign-in</span></span>

<span data-ttu-id="cbb60-127">*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="cbb60-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="cbb60-128">In questa sezione verrà impostato l’Accesso Single Sign-On (SSO) facile di Azure Active Directory, che funziona con la Sincronizzazione dell'hash delle password (PHS) e l’Autenticazione pass-through (PTA), per consentire agli utenti di accedere ai servizi che usano gli account utenti di Azure AD senza dover digitare la password e, in molti casi, il nome utente.</span><span class="sxs-lookup"><span data-stu-id="cbb60-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="cbb60-129">In questo modo gli utenti possono facilmente accedere alle applicazioni basate su cloud come Office 365, senza aver bisogno di componenti aggiuntivi in loco quali ad esempio server federativi di identità.</span><span class="sxs-lookup"><span data-stu-id="cbb60-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="cbb60-130">L'accesso SSO facile di Azure AD viene configurato con lo strumento Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="cbb60-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="cbb60-131">Vedere le [istruzioni per configurare l'accesso SSO facile ad Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="cbb60-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="cbb60-133">Guida del laboratorio di testing: accesso SSO facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="cbb60-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="cbb60-134">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-sso) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="cbb60-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="cbb60-135">Personalizzare la pagina di accesso a Office 365</span><span class="sxs-lookup"><span data-stu-id="cbb60-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="cbb60-136">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="cbb60-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="cbb60-137">In questo passaggio si aggiunge il nome dell'azienda, il logo e altri elementi familiari alla pagina di accesso dell'organizzazione per renderla più riconoscibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cbb60-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="cbb60-138">Con Microsoft 365 Enterprise, è possibile personalizzare l'aspetto delle pagine di accesso e del Riquadro di accesso affinché includano il logo e colori dell'azienda e informazioni sull'utente personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cbb60-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="cbb60-139">Per ulteriori informazioni, vedere [Aggiungere il marchio dell'organizzazione alla pagina di accesso di Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="cbb60-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="cbb60-140">Per istruzioni sulla configurazione, vedere [Aggiungere il marchio dell'organizzazione alle pagine di accesso e Riquadro di accesso](https://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="cbb60-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="cbb60-141">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-custom-sign-in) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="cbb60-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="cbb60-142">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="cbb60-142">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="cbb60-144">Proteggere e gestire gli accessi degli utenti</span><span class="sxs-lookup"><span data-stu-id="cbb60-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
