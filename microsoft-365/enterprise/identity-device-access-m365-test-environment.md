---
title: L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente di Microsoft 365 per testare l’identità e l’accesso dei dispositivi.
ms.openlocfilehash: c8d7aed1422f9d0c5891157e6fb7d3d30d976c4a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981897"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="294fd-103">L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="294fd-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="294fd-104">Le [configurazioni di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md) sono un set di funzionalità e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD), tra cui Office 365 e Microsoft Intune in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="294fd-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="294fd-105">Per creare un ambiente di testing che disponga dell’applicazione di questi criteri:</span><span class="sxs-lookup"><span data-stu-id="294fd-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="294fd-106">Configurare l'ambiente di testing con le funzionalità essenziali di identità e sicurezza in base alle scelte dell’utente del modello di identità e metodo di autenticazione:</span><span class="sxs-lookup"><span data-stu-id="294fd-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="294fd-107">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="294fd-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="294fd-108">Sincronizzazione dell'hash delle password</span><span class="sxs-lookup"><span data-stu-id="294fd-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="294fd-109">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="294fd-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="294fd-110">Usare i [criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e testare la protezione di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="294fd-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="294fd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="294fd-111">See also</span></span>

[<span data-ttu-id="294fd-112">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="294fd-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="294fd-113">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="294fd-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="294fd-114">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="294fd-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="294fd-115">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="294fd-115">[Microsoft 365 Enterprise deployment](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="294fd-116">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="294fd-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
