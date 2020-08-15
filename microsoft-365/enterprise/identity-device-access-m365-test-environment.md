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
ms.openlocfilehash: c5bc0fbbb3ae3839cb7aa71e8c840784ae4a4cad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685855"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b54dd-103">L’identità e l’accesso dei dispositivi per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b54dd-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b54dd-104">*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*</span><span class="sxs-lookup"><span data-stu-id="b54dd-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b54dd-105">Le [configurazioni di accesso a identità e dispositivi](microsoft-365-policies-configurations.md) sono un insieme di funzionalità e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="b54dd-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="b54dd-106">Per creare un ambiente di testing che disponga dell’applicazione di questi criteri:</span><span class="sxs-lookup"><span data-stu-id="b54dd-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="b54dd-107">Configurare l'ambiente di testing con le funzionalità essenziali di identità e sicurezza in base alle scelte dell’utente del modello di identità e metodo di autenticazione:</span><span class="sxs-lookup"><span data-stu-id="b54dd-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="b54dd-108">Solo cloud</span><span class="sxs-lookup"><span data-stu-id="b54dd-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="b54dd-109">Sincronizzazione dell'hash delle password</span><span class="sxs-lookup"><span data-stu-id="b54dd-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="b54dd-110">Autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="b54dd-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="b54dd-111">Usare i [criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e testare la protezione di identità e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b54dd-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="b54dd-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b54dd-112">See also</span></span>

[<span data-ttu-id="b54dd-113">Guide al lab di test per identità aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b54dd-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="b54dd-114">Roadmap dell'identità</span><span class="sxs-lookup"><span data-stu-id="b54dd-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="b54dd-115">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="b54dd-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b54dd-116">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="b54dd-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b54dd-117">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b54dd-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
