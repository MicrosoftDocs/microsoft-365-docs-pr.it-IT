---
title: L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente di Microsoft 365 per testare l’identità e l’accesso dei dispositivi.
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327808"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7b435-103">L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b435-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7b435-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="7b435-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7b435-105">Le [configurazioni di accesso a identità e dispositivi](microsoft-365-policies-configurations.md) sono un insieme di funzionalità e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="7b435-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="7b435-106">Per creare un ambiente di testing con le configurazioni di accesso ai dispositivi e le identità comuni sul posto:</span><span class="sxs-lookup"><span data-stu-id="7b435-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="7b435-107">Configurare l'ambiente di testing con le funzionalità essenziali di identità e sicurezza in base alle scelte dell’utente del modello di identità e metodo di autenticazione:</span><span class="sxs-lookup"><span data-stu-id="7b435-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="7b435-108">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="7b435-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="7b435-109">Sincronizzazione dell'hash delle password (PHS)</span><span class="sxs-lookup"><span data-stu-id="7b435-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="7b435-110">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="7b435-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="7b435-111">Utilizzare [criteri comuni di accesso a identità e](identity-access-policies.md) dispositivi per configurare i criteri che si basano sui prerequisiti configurati per l'ambiente di testing ed esplorare e verificare la protezione per identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7b435-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b435-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b435-112">See also</span></span>

[<span data-ttu-id="7b435-113">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b435-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="7b435-114">Roadmap dell'identità</span><span class="sxs-lookup"><span data-stu-id="7b435-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7b435-115">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="7b435-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7b435-116">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="7b435-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7b435-117">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7b435-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
