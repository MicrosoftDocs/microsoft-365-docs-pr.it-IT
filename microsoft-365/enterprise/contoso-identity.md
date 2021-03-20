---
title: Identità per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Come Contoso sfrutta l’identità come servizio (IDaaS) e fornisce l'autenticazione basata su cloud per i dipendenti e l'autenticazione federata per i partner e clienti.
ms.openlocfilehash: accd60f6699e7ebf04963213128d1ca1ffc8f7fe
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911073"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="18ce8-103">Identità per Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="18ce8-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="18ce8-104">Microsoft fornisce Identity as a Service (IDaaS) nelle offerte cloud tramite Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="18ce8-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="18ce8-105">Per adottare Microsoft 365 per le aziende, la soluzione Contoso IDaaS doveva utilizzare il proprio provider di identità locale e includere l'autenticazione federata con i provider di identità attendibili di terze parti esistenti.</span><span class="sxs-lookup"><span data-stu-id="18ce8-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="18ce8-106">Foresta di Servizi di dominio Active Directory Contoso</span><span class="sxs-lookup"><span data-stu-id="18ce8-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="18ce8-107">Contoso utilizza una singola foresta di Servizi di dominio Active Directory (AD DS) per contoso com con sette \. sottodomini, uno per ogni area geografica del mondo.</span><span class="sxs-lookup"><span data-stu-id="18ce8-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="18ce8-108">La sede principale, le sedi centrali regionali e le filiali contengono controller di dominio per l'autorizzazione e l'autenticazione locali.</span><span class="sxs-lookup"><span data-stu-id="18ce8-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="18ce8-109">Ecco la foresta contoso con domini regionali per le diverse parti del mondo che contengono hub regionali.</span><span class="sxs-lookup"><span data-stu-id="18ce8-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Foresta di Contoso e domini a livello mondiale](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="18ce8-111">Contoso ha deciso di utilizzare gli account e i gruppi nella foresta contoso com per l'autenticazione e l'autorizzazione per i carichi di lavoro e i servizi di \. Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="18ce8-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="18ce8-112">Infrastruttura di autenticazione federata Contoso</span><span class="sxs-lookup"><span data-stu-id="18ce8-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="18ce8-113">Contoso consente:</span><span class="sxs-lookup"><span data-stu-id="18ce8-113">Contoso allows:</span></span>

- <span data-ttu-id="18ce8-114">I clienti possono usare i propri account Microsoft, Facebook o Google Mail per accedere al sito Web pubblico dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="18ce8-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="18ce8-115">Fornitori e partner per usare i propri account LinkedIn, Salesforce o Google Mail per accedere all'Extranet partner dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="18ce8-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="18ce8-116">Ecco la dmZ contoso contenente un sito Web pubblico, una extranet partner e un set di server Active Directory Federation Services (AD FS).</span><span class="sxs-lookup"><span data-stu-id="18ce8-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="18ce8-117">La rete perimetrale è connessa a Internet che contiene clienti, partner e servizi Internet.</span><span class="sxs-lookup"><span data-stu-id="18ce8-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Supporto di Contoso per l'autenticazione federata per clienti e partner](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="18ce8-119">I server AD FS nella rete perimetrale facilitano l'autenticazione delle credenziali dei clienti da parte dei provider di identità per l'accesso al sito Web pubblico e le credenziali del partner per l'accesso alla extranet del partner.</span><span class="sxs-lookup"><span data-stu-id="18ce8-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="18ce8-120">Contoso ha deciso di mantenere questa infrastruttura e dedicarla all'autenticazione di clienti e partner.</span><span class="sxs-lookup"><span data-stu-id="18ce8-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="18ce8-121">Gli architetti per le identità di Contoso stanno valutando la conversione di questa infrastruttura in soluzioni [B2B](/azure/active-directory/b2b/hybrid-organizations) e [B2C](/azure/active-directory-b2c/solution-articles) di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="18ce8-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) and [B2C](/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="18ce8-122">Identità ibrida con sincronizzazione dell'hash delle password per l'autenticazione basata su cloud</span><span class="sxs-lookup"><span data-stu-id="18ce8-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="18ce8-123">Contoso desiderava utilizzare la foresta di Servizi di dominio Active Directory locale per l'autenticazione alle risorse cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="18ce8-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="18ce8-124">Ha deciso di usare la sincronizzazione dell'hash delle password (PHS).</span><span class="sxs-lookup"><span data-stu-id="18ce8-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="18ce8-125">PHS sincronizza la foresta di Servizi di dominio Active Directory locale con il tenant di Azure AD della sottoscrizione a Microsoft 365 per le aziende, copiando gli account utente e di gruppo e una versione con hash delle password degli account utente.</span><span class="sxs-lookup"><span data-stu-id="18ce8-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="18ce8-126">Per eseguire la sincronizzazione della directory, Contoso ha distribuito lo strumento Azure AD Connect in un server nel datacenter di Parigi.</span><span class="sxs-lookup"><span data-stu-id="18ce8-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="18ce8-127">Ecco il server che esegue Azure AD Connect che esegue il polling della foresta di Contoso AD DS per le modifiche e quindi la sincronizzazione di tali modifiche con il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="18ce8-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infrastruttura di sincronizzazione della directory PHS contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="18ce8-129">Criteri di accesso condizionale per l’identità e l’accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="18ce8-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="18ce8-130">Contoso ha creato un insieme di [criteri di accesso condizionale](../security/office-365-security/identity-access-policies.md) per Azure AD e Intune per tre livelli di protezione:</span><span class="sxs-lookup"><span data-stu-id="18ce8-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](../security/office-365-security/identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="18ce8-131">*Le* protezioni di base si applicano a tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="18ce8-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="18ce8-132">*Le* protezioni sensibili si applicano ai dirigenti e ai dirigenti.</span><span class="sxs-lookup"><span data-stu-id="18ce8-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="18ce8-133">*Le protezioni* altamente regolamentate si applicano a utenti specifici dei reparti finanziari, legali e di ricerca che hanno accesso a dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="18ce8-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="18ce8-134">Ecco il set risultante di criteri di accesso condizionale dell'identità e del dispositivo contoso.</span><span class="sxs-lookup"><span data-stu-id="18ce8-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Criteri di accesso condizionale di identità e dispositivi di Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="18ce8-136">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="18ce8-136">Next step</span></span>

<span data-ttu-id="18ce8-137">Scopri come Contoso usa l'infrastruttura di Microsoft Endpoint Configuration Manager per [distribuire e mantenere Windows 10 Enterprise corrente](contoso-win10.md) all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="18ce8-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="18ce8-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18ce8-138">See also</span></span>

[<span data-ttu-id="18ce8-139">Roadmap delle identità per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="18ce8-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="18ce8-140">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="18ce8-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="18ce8-141">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="18ce8-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)