---
title: 'Fase 2: identità'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise.
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981952"
---
# <a name="phase-2-identity"></a><span data-ttu-id="290ba-103">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="290ba-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="290ba-104">In Microsoft 365 Enterprise, un'infrastruttura di gestione delle identità ben pianificata ed eseguita permette una maggiore sicurezza e l'accesso ai carichi di lavoro di produttività e ai relativi dati solo da parte di utenti e dispositivi autenticati.</span><span class="sxs-lookup"><span data-stu-id="290ba-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="290ba-105">Guardare questo video per una panoramica dei modelli di identità e dell'autenticazione per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="290ba-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="290ba-106">Se è stata già implementata un'infrastruttura di gestione delle identità, vedere i [criteri uscita delle identità](identity-exit-criteria.md) per assicurarsi che soddisfino le condizioni facoltative e obbligatorie di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="290ba-106">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="290ba-107">Per le funzionalità di gestione delle identità di ogni piano di Microsoft 365 Enterprise, il ruolo di Azure Active Directory (Azure ad), i componenti locali e basati sul cloud e le configurazioni di autenticazione più comuni, vedere il [poster dell'infrastruttura di gestione delle identità](media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="290ba-107">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="290ba-108">[![Poster dell'infrastruttura di gestione delle identità](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="290ba-108">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="290ba-109">Questo poster di due pagine rappresenta un modo rapido per apprendere le configurazioni e i concetti relativi alle identità per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="290ba-109">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="290ba-110">È anche possibile [scaricare il poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).</span><span class="sxs-lookup"><span data-stu-id="290ba-110">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="290ba-111">Pianificare e distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="290ba-111">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="290ba-p101">Utilizzare la seguente procedura per pianificare e distribuire la nuova infrastruttura di gestione delle identità nel cloud. È inoltre possibile usare tale procedura per adattare l'infrastruttura di gestione delle identità ibrida o locale esistente da utilizzare con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="290ba-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="290ba-114">Pianificare utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="290ba-114">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="290ba-115">Protezione delle identità con privilegi</span><span class="sxs-lookup"><span data-stu-id="290ba-115">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="290ba-116">Configurare identità ibrida</span><span class="sxs-lookup"><span data-stu-id="290ba-116">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="290ba-117">Configurare autenticazione utente protetto</span><span class="sxs-lookup"><span data-stu-id="290ba-117">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="290ba-118">Semplificare l'accesso per gli utenti</span><span class="sxs-lookup"><span data-stu-id="290ba-118">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="290ba-119">Usare i gruppi per facilitare la gestione</span><span class="sxs-lookup"><span data-stu-id="290ba-119">Use groups for easier management</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="290ba-120">Configurare la governance delle identità</span><span class="sxs-lookup"><span data-stu-id="290ba-120">Configure identity governance</span></span>](identity-governance.md) |

<span data-ttu-id="290ba-121">Dopo aver completato questi passaggi, passare ai [criteri di uscita](identity-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per le identità di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="290ba-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="290ba-122">Consigli sull’identità e sull’accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="290ba-122">Identity and device access recommendations</span></span>

<span data-ttu-id="290ba-p102">Microsoft offre un set di consigli per [l’identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l’identità, usare i suggerimenti e le impostazioni degli articoli seguenti insieme alla procedura descritta in questa fase:</span><span class="sxs-lookup"><span data-stu-id="290ba-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="290ba-125">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="290ba-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="290ba-126">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="290ba-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="290ba-127">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="290ba-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="290ba-128">Informazioni su come gli esperti IT di Microsoft [gestiscono le identità e l'accesso sicuro](https://www.microsoft.com/it-IT/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span><span class="sxs-lookup"><span data-stu-id="290ba-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/it-IT/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="290ba-129">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="290ba-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="290ba-130">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito un’infrastruttura di identità ibrida](contoso-identity.md) per i servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="290ba-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="290ba-131">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="290ba-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="290ba-132">Pianificare utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="290ba-132">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
