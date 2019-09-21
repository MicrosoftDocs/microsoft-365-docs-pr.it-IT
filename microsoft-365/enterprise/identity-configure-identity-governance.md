---
title: 'Passaggio 7: Configurare Identity Governance'
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
ms.openlocfilehash: 7ba54db29335f4f8f6eefff0cafbdefe3c522d7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084213"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="33558-103">Passaggio 7: Configurare Identity Governance</span><span class="sxs-lookup"><span data-stu-id="33558-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="33558-104">Identity Governance consente di proteggere, monitorare e controllare l'accesso alle risorse più importanti e garantire la produttività dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="33558-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="33558-105">Ad esempio, con Identity Governance è possibile fare in modo che gli utenti giusti abbiano diritto di accesso alle risorse giuste e determinare se l'accesso cambia nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="33558-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="33558-106">Vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) per maggiori informazioni su Identity Governance per Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="33558-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="33558-107">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="33558-107">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="33558-108">Impostare le verifiche di accesso di Azure AD</span><span class="sxs-lookup"><span data-stu-id="33558-108">Set up Azure AD access reviews</span></span>

<span data-ttu-id="33558-109">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="33558-109">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="33558-110">In questo passaggio verranno configurate le verifiche di accesso di Azure AD, che consentono di verificare l'accesso di un utente per garantire che solo le persone giuste dispongano di un accesso continuo.</span><span class="sxs-lookup"><span data-stu-id="33558-110">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="33558-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="33558-111">For example:</span></span>

- <span data-ttu-id="33558-112">Quando un nuovo dipendente si unisce all'organizzazione, è necessario assicurarsi che disponga dell'accesso giusto per essere produttivo.</span><span class="sxs-lookup"><span data-stu-id="33558-112">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="33558-113">Quando questo dipendente si sposta in altri team, posizioni o dipartimenti, è necessario assicurarsi che l'accesso ai team, alle posizioni o ai dipartimenti precedenti venga rimosso se necessario.</span><span class="sxs-lookup"><span data-stu-id="33558-113">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="33558-114">Se il dipendente o un ospite lascia l'organizzazione, è necessario assicurarsi che l'accesso venga rimosso.</span><span class="sxs-lookup"><span data-stu-id="33558-114">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="33558-115">Questo è particolarmente importante se l'organizzazione è soggetta a controlli di sicurezza per determinare se gli account utente hanno un accesso troppo esteso, il che potrebbe comportare sanzioni pecuniarie in caso di violazione delle normative di settore o regionali.</span><span class="sxs-lookup"><span data-stu-id="33558-115">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="33558-116">Vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) per maggiori informazioni sulle verifiche di accesso di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="33558-116">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="33558-117">Azure AD Privileged Identity Management (PIM) fornisce controlli aggiuntivi mirati alla protezione dei diritti di accesso alle risorse in Azure AD, Azure e altri servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="33558-117">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="33558-118">Azure AD PIM fornisce un set completo di controlli di governance che agevolano la protezione delle risorse aziendali, ad esempio ruoli delle directory, di Office 365 e delle risorse di Azure.</span><span class="sxs-lookup"><span data-stu-id="33558-118">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="33558-119">Come con altre forme di accesso, le organizzazioni possono usare le verifiche di accesso per configurare la ricertificazione ricorrente dell'accesso per tutti gli utenti con ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="33558-119">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="33558-120">Azure AD PIM è disponibile solo con la versione E5 di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="33558-120">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="33558-121">Vedere questi articoli per configurare tipi diversi di verifica di accesso:</span><span class="sxs-lookup"><span data-stu-id="33558-121">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="33558-122">Gruppi e app</span><span class="sxs-lookup"><span data-stu-id="33558-122">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="33558-123">Ruoli di Azure AD</span><span class="sxs-lookup"><span data-stu-id="33558-123">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="33558-124">Ruoli delle risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="33558-124">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="33558-125">Come checkpoint provvisorio, è possibile vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-access-reviews) per questa sezione.</span><span class="sxs-lookup"><span data-stu-id="33558-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="33558-126">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="33558-126">Next step</span></span>

[<span data-ttu-id="33558-127">Criteri uscita dell'infrastruttura di identità</span><span class="sxs-lookup"><span data-stu-id="33558-127">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

