---
title: L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente di Microsoft 365 per testare l’identità e l’accesso dei dispositivi.
ms.openlocfilehash: 7004a46873e32f39ace672bd955147e2f13ee05d
ms.sourcegitcommit: 2f7791159b715790463c6ce4835fbd9c0b48c047
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2019
ms.locfileid: "33243061"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5be25-103">L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5be25-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5be25-104">[Configurazioni di identità e accesso dei dispositivi](microsoft-365-policies-configurations.md) sono un set di funzionalità e i criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD), tra cui Office 365 ed Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5be25-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="5be25-105">Per creare un ambiente di testing che disponga dell’applicazione di questi criteri:</span><span class="sxs-lookup"><span data-stu-id="5be25-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="5be25-106">Configurare l'ambiente di testing con le funzionalità essenziali di identità e sicurezza in base alle scelte dell’utente del modello di identità e metodo di autenticazione:</span><span class="sxs-lookup"><span data-stu-id="5be25-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="5be25-107">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="5be25-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="5be25-108">Sincronizzazione dell'hash delle password</span><span class="sxs-lookup"><span data-stu-id="5be25-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="5be25-109">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="5be25-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="5be25-110">Usare i [criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e testare la protezione di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5be25-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="5be25-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5be25-111">See also</span></span>

[<span data-ttu-id="5be25-112">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5be25-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="5be25-113">Fase 2: identità</span><span class="sxs-lookup"><span data-stu-id="5be25-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="5be25-114">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5be25-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

<span data-ttu-id="5be25-115">[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="5be25-115">[Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)</span></span>

[<span data-ttu-id="5be25-116">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5be25-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
