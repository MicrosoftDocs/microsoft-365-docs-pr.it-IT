---
title: "Passaggio 10: semplificare l'accesso utente"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare l'accesso Single Sign-On facile ad Azure AD (SSO facile).
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868822"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="b21bb-103">Passaggio 10: semplificare l'accesso utente</span><span class="sxs-lookup"><span data-stu-id="b21bb-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="b21bb-104">*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b21bb-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="b21bb-p101">In questo passaggio, viene configurato l'accesso Single Sign-On facile (SSO facile di Azure Active Directory) per consentire agli utenti di accedere ai servizi che usano gli account utente di Azure Active Directory senza dover digitare la password e in molti casi, i propri nomi utente. In questo modo, gli utenti possono accedere sempre facilmente alle applicazioni basate sul cloud, come Office 365, senza componenti aggiuntivi in locale, quali ad esempio i server di federazione delle identità.</span><span class="sxs-lookup"><span data-stu-id="b21bb-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="b21bb-107">L'accesso SSO facile di Azure AD viene configurato con lo strumento Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="b21bb-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="b21bb-108">Vedere le [istruzioni per configurare l'accesso SSO facile ad Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="b21bb-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b21bb-110">Guida del laboratorio di testing: accesso SSO facile di Azure AD</span><span class="sxs-lookup"><span data-stu-id="b21bb-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="b21bb-111">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-sso) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b21bb-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b21bb-112">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b21bb-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="b21bb-113">Personalizzare la pagina di accesso a Office 365</span><span class="sxs-lookup"><span data-stu-id="b21bb-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

