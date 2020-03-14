---
title: 'Passaggio 7: Configurare Identity Governance'
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
description: Informazioni su Identity Governance per il tenant di Azure AD e su come configurarlo.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633584"
---
# <a name="step-6-configure-identity-governance"></a><span data-ttu-id="125f7-103">Passaggio 6: Configurare Identity Governance</span><span class="sxs-lookup"><span data-stu-id="125f7-103">Step 6: Configure identity governance</span></span>

![Fase 2: identità](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="125f7-105">Identity Governance consente di proteggere, monitorare e controllare l'accesso alle risorse strategiche e garantire la produttività dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="125f7-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="125f7-106">Ad esempio, con Identity Governance è possibile fare in modo che gli utenti giusti abbiano diritto di accesso alle risorse giuste e determinare se l'accesso cambia nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="125f7-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="125f7-107">Vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) per maggiori informazioni su Identity Governance per Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="125f7-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="125f7-108">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="125f7-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="125f7-109">Impostare le verifiche di accesso di Azure AD</span><span class="sxs-lookup"><span data-stu-id="125f7-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="125f7-110">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="125f7-110">*This is optional and only applies to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="125f7-111">In questo passaggio verranno configurate le verifiche di accesso di Azure AD, che consentono di verificare l'accesso di un utente per garantire che solo le persone giuste dispongano di un accesso continuo.</span><span class="sxs-lookup"><span data-stu-id="125f7-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="125f7-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="125f7-112">For example:</span></span>

- <span data-ttu-id="125f7-113">Quando un nuovo dipendente si unisce all'organizzazione, è necessario assicurarsi che disponga dell'accesso giusto per essere produttivo.</span><span class="sxs-lookup"><span data-stu-id="125f7-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="125f7-114">Quando questo dipendente si sposta in altri team, posizioni o dipartimenti, è necessario assicurarsi che l'accesso ai team, alle posizioni o ai dipartimenti precedenti venga rimosso se necessario.</span><span class="sxs-lookup"><span data-stu-id="125f7-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="125f7-115">Se il dipendente o un ospite lascia l'organizzazione, è necessario assicurarsi che l'accesso venga rimosso.</span><span class="sxs-lookup"><span data-stu-id="125f7-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="125f7-116">Questo è particolarmente importante se l'organizzazione è soggetta a controlli di sicurezza per determinare se gli account utente hanno un accesso troppo esteso, il che potrebbe comportare sanzioni pecuniarie in caso di violazione delle normative di settore o regionali.</span><span class="sxs-lookup"><span data-stu-id="125f7-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="125f7-117">Vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) per maggiori informazioni sulle verifiche di accesso di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="125f7-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="125f7-118">Azure AD Privileged Identity Management (PIM) fornisce controlli aggiuntivi mirati alla protezione dei diritti di accesso alle risorse in Azure AD, Azure e altri servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="125f7-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="125f7-119">Azure AD PIM fornisce un set completo di controlli di governance che agevolano la protezione delle risorse aziendali, ad esempio ruoli delle directory, di Office 365 e delle risorse di Azure.</span><span class="sxs-lookup"><span data-stu-id="125f7-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="125f7-120">Come con altre forme di accesso, le organizzazioni possono usare le verifiche di accesso per configurare la ricertificazione ricorrente dell'accesso per tutti gli utenti con ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="125f7-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="125f7-121">Azure AD PIM è disponibile solo con la versione E5 di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="125f7-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="125f7-122">Vedere questi articoli per configurare tipi diversi di verifica di accesso:</span><span class="sxs-lookup"><span data-stu-id="125f7-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="125f7-123">Gruppi e app</span><span class="sxs-lookup"><span data-stu-id="125f7-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="125f7-124">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="125f7-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="125f7-125">Ruoli delle risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="125f7-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="125f7-126">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-access-reviews) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="125f7-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="125f7-127">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="125f7-127">Next step</span></span>

[<span data-ttu-id="125f7-128">Criteri uscita dell'infrastruttura di identità</span><span class="sxs-lookup"><span data-stu-id="125f7-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

