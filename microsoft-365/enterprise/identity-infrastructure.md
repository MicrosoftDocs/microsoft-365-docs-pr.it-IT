---
title: 'Fase 2: identità'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise.
ms.openlocfilehash: 932b6fb2cfeb86edcf708bdfdea55cdd8b580838
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288738"
---
# <a name="phase-2-identity"></a><span data-ttu-id="c3adc-103">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="c3adc-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="c3adc-104">In Microsoft 365 Enterprise, un'infrastruttura di gestione delle identità ben pianificata ed eseguita permette una maggiore sicurezza e l'accesso ai carichi di lavoro di produttività e ai relativi dati solo da parte di utenti e dispositivi autenticati.</span><span class="sxs-lookup"><span data-stu-id="c3adc-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="c3adc-105">Se è stata già implementata un'infrastruttura di gestione delle identità, vedere i [criteri uscita delle identità](identity-exit-criteria.md) per assicurarsi che soddisfino le condizioni facoltative e obbligatorie di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c3adc-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="c3adc-106">Pianificare e distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c3adc-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="c3adc-107">Prima di iniziare, guardare questo video che illustra i modelli di identità e l'autenticazione per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3adc-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="c3adc-p101">Utilizzare la seguente procedura per pianificare e distribuire la nuova infrastruttura di gestione delle identità nel cloud. È inoltre possibile usare tale procedura per adattare l'infrastruttura di gestione delle identità ibrida o locale esistente da utilizzare con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c3adc-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="c3adc-110">Pianificare utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="c3adc-110">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="c3adc-111">Protezione delle identità con privilegi</span><span class="sxs-lookup"><span data-stu-id="c3adc-111">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="c3adc-112">Configurare identità ibrida</span><span class="sxs-lookup"><span data-stu-id="c3adc-112">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="c3adc-113">Configurare autenticazione utente protetto</span><span class="sxs-lookup"><span data-stu-id="c3adc-113">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="c3adc-114">Semplificare l'accesso per gli utenti</span><span class="sxs-lookup"><span data-stu-id="c3adc-114">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="c3adc-115">Usare i gruppi per facilitare la gestione</span><span class="sxs-lookup"><span data-stu-id="c3adc-115">Use groups for easier management</span></span>](identity-self-service-group-management.md) |

<span data-ttu-id="c3adc-116">Dopo aver completato questi passaggi, passare ai [criteri uscita](identity-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c3adc-116">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="c3adc-117">Consigli sull’identità e sull’accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c3adc-117">Identity and device access recommendations</span></span>

<span data-ttu-id="c3adc-p102">Microsoft offre un set di consigli per [l’identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l’identità, usare i suggerimenti e le impostazioni degli articoli seguenti insieme alla procedura descritta in questa fase:</span><span class="sxs-lookup"><span data-stu-id="c3adc-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="c3adc-120">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c3adc-120">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="c3adc-121">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c3adc-121">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c3adc-122">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c3adc-122">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c3adc-123">Informazioni su come gli esperti IT di Microsoft hanno pianificato e implementato le funzionalità di identità di Microsoft 365 Enterprise con queste risorse:</span><span class="sxs-lookup"><span data-stu-id="c3adc-123">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="c3adc-124">Gestione delle identità degli utenti e accesso protetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="c3adc-124">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="c3adc-125">Utilizzo di Azure AD Privileged Identity Management per l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="c3adc-125">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="c3adc-126">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c3adc-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c3adc-127">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito un’infrastruttura di identità ibrida](contoso-identity.md) per i servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3adc-127">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="c3adc-128">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c3adc-128">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="c3adc-129">Pianificare utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="c3adc-129">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
