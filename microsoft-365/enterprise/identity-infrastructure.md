---
title: 'Fase 2: identità'
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
description: La procedura per distribuire l'infrastruttura delle identità di Microsoft 365 Enterprise.
ms.openlocfilehash: 6f237f779df16f2a2a03eab29af78a89c5f7a5ae
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371419"
---
# <a name="phase-2-identity"></a><span data-ttu-id="36c87-103">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="36c87-103">Phase 2: Identity</span></span>

![Fase 2: identità](../media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="36c87-105">In Microsoft 365 Enterprise, un'infrastruttura di gestione delle identità ben pianificata ed eseguita permette una maggiore sicurezza e l'accesso ai carichi di lavoro di produttività e ai relativi dati solo da parte di utenti e dispositivi autenticati.</span><span class="sxs-lookup"><span data-stu-id="36c87-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="36c87-106">Guardare questo video per una panoramica dei modelli di identità e dell'autenticazione per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36c87-106">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="36c87-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="36c87-107"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="36c87-108">Se è stata già implementata un'infrastruttura di gestione delle identità, vedere i [criteri uscita delle identità](identity-exit-criteria.md) per assicurarsi che soddisfino le condizioni facoltative e obbligatorie di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36c87-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="36c87-109">Per le funzionalità di gestione delle identità di ogni piano di Microsoft 365 Enterprise, il ruolo di Azure Active Directory (Azure ad), i componenti locali e basati sul cloud e le configurazioni di autenticazione più comuni, vedere il [poster dell'infrastruttura di gestione delle identità](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="36c87-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="36c87-110">[![Poster dell'infrastruttura di gestione delle identità](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="36c87-110">[![The Identity Infrastructure poster](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="36c87-111">Questo poster di due pagine rappresenta un modo rapido per apprendere le configurazioni e i concetti relativi alle identità per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36c87-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="36c87-112">È anche possibile [scaricare il poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).</span><span class="sxs-lookup"><span data-stu-id="36c87-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="36c87-113">Pianificare e distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36c87-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="36c87-p101">Utilizzare la seguente procedura per pianificare e distribuire la nuova infrastruttura di gestione delle identità nel cloud. È inoltre possibile usare tale procedura per adattare l'infrastruttura di gestione delle identità ibrida o locale esistente da utilizzare con Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36c87-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![Passaggio 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="36c87-117">Creare e proteggere gli account di amministratore globale</span><span class="sxs-lookup"><span data-stu-id="36c87-117">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![Passaggio 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="36c87-119">Proteggere le password</span><span class="sxs-lookup"><span data-stu-id="36c87-119">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![Passaggio 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="36c87-121">Proteggere e gestire gli accessi degli utenti</span><span class="sxs-lookup"><span data-stu-id="36c87-121">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![Passaggio 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="36c87-123">Aggiungere gli account utente</span><span class="sxs-lookup"><span data-stu-id="36c87-123">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![Passaggio 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="36c87-125">Usare i gruppi per la gestione</span><span class="sxs-lookup"><span data-stu-id="36c87-125">Use groups for management</span></span>](identity-use-group-management.md) |
|![Passaggio 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="36c87-127">Configurare Identity Governance</span><span class="sxs-lookup"><span data-stu-id="36c87-127">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="36c87-128">Dopo aver completato questi passaggi, passare ai [criteri di uscita](identity-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per le identità di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36c87-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise identity.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="36c87-129">Consigli sull’identità e sull’accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="36c87-129">Identity and device access recommendations</span></span>

<span data-ttu-id="36c87-p102">Microsoft offre un set di consigli per [l’identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l’identità, usare i suggerimenti e le impostazioni degli articoli seguenti insieme alla procedura descritta in questa fase:</span><span class="sxs-lookup"><span data-stu-id="36c87-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="36c87-132">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="36c87-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="36c87-133">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="36c87-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="36c87-134">Come Microsoft esegue Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36c87-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="36c87-135">Informazioni su come gli esperti IT di Microsoft [gestiscono le identità e l'accesso sicuro](https://www.microsoft.com/it-IT/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span><span class="sxs-lookup"><span data-stu-id="36c87-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/it-IT/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span></span>

>[!Note]
><span data-ttu-id="36c87-136">Questa risorsa IT Showcase è disponibile solo in inglese.</span><span class="sxs-lookup"><span data-stu-id="36c87-136">This IT Showcase resource is only available in English.</span></span>
>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="36c87-137">Come ha agito Contoso con Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36c87-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="36c87-138">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito un’infrastruttura di identità ibrida](contoso-identity.md) per i servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36c87-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="36c87-140">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="36c87-140">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="36c87-142">Creare e proteggere gli account di amministratore globale</span><span class="sxs-lookup"><span data-stu-id="36c87-142">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
