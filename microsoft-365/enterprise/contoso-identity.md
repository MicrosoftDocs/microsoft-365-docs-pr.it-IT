---
title: Identità per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Come Contoso sfrutta l’identità come servizio (IDaaS) e fornisce l'autenticazione basata su cloud per i dipendenti e l'autenticazione federata per i partner e clienti.
ms.openlocfilehash: 10db0a35024595c4dba9a33ad83ae75bcad3870c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637248"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="dbeb4-103">Identità per Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="dbeb4-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="dbeb4-104">Microsoft fornisce l'identità come servizio (IDaaS) tra le offerte cloud tramite Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="dbeb4-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="dbeb4-105">Per adottare Microsoft 365 per Enterprise, la soluzione Contoso IDaaS deve utilizzare il provider di identità locale e includere l'autenticazione federata con i provider di identità di terze parti attendibili esistenti.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="dbeb4-106">La foresta di servizi di dominio contoso Active Directory</span><span class="sxs-lookup"><span data-stu-id="dbeb4-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="dbeb4-107">Contoso utilizza una singola foresta di servizi di dominio Active Directory per Contoso \. com con sette sottodomini, uno per ogni area del mondo.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="dbeb4-108">La sede principale, le sedi centrali regionali e le filiali contengono controller di dominio per l'autorizzazione e l'autenticazione locali.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="dbeb4-109">Ecco la foresta Contoso con domini regionali per le diverse parti del mondo che contengono hub regionali.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Foresta di Contoso e domini a livello mondiale](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="dbeb4-111">Contoso ha deciso di utilizzare gli account e i gruppi nella \. foresta com contoso per l'autenticazione e l'autorizzazione per i carichi di lavoro e i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="dbeb4-112">L'infrastruttura di autenticazione federata contoso</span><span class="sxs-lookup"><span data-stu-id="dbeb4-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="dbeb4-113">Contoso consente:</span><span class="sxs-lookup"><span data-stu-id="dbeb4-113">Contoso allows:</span></span>

- <span data-ttu-id="dbeb4-114">I clienti possono utilizzare gli account Microsoft, Facebook o Google mail per accedere al sito Web pubblico della società.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="dbeb4-115">Fornitori e partner per l'utilizzo dei propri account LinkedIn, Salesforce o Google mail per accedere all'Extranet dei partner della società.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="dbeb4-p103">Ecco la DMZ di Contoso contenente un sito Web pubblico, un'Extranet di partner e un set di server AD FS. La DMZ è connessa a Internet che contiene clienti, partner e servizi Internet.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-p103">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of AD FS servers. The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Supporto di Contoso per l'autenticazione federata per clienti e partner](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="dbeb4-119">I server AD FS nella DMZ facilitano l'autenticazione delle credenziali del cliente dai rispettivi provider di identità per accedere al sito Web pubblico e le credenziali dei partner per l'accesso all'Extranet dei partner.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="dbeb4-p104">Contoso ha deciso di mantenere questa infrastruttura e di dedicarla all'autenticazione dei clienti e dei partner. Gli architetti dell'identità contoso stanno studiando la conversione di questa infrastruttura nelle soluzioni di Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) .</span><span class="sxs-lookup"><span data-stu-id="dbeb4-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="dbeb4-122">Identità ibrida con sincronizzazione dell'hash delle password per l'autenticazione basata su cloud</span><span class="sxs-lookup"><span data-stu-id="dbeb4-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="dbeb4-123">Contoso desiderava utilizzare la foresta di servizi di dominio Active Directory locale per l'autenticazione nelle risorse cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="dbeb4-124">Ha deciso di utilizzare la sincronizzazione degli hash delle password (pH).</span><span class="sxs-lookup"><span data-stu-id="dbeb4-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="dbeb4-125">PH sincronizza la foresta di servizi di dominio Active Directory locale con il tenant di Azure AD della sottoscrizione Microsoft 365 per Enterprise, copiando gli account utente e di gruppo e una versione con hash delle password degli account utente.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="dbeb4-126">Per eseguire la sincronizzazione della directory, Contoso ha distribuito lo strumento Azure AD Connect su un server nel datacenter di Parigi.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="dbeb4-127">Di seguito è indicato il server che esegue Azure AD Connect polling della foresta contoso AD DS per le modifiche e quindi la sincronizzazione delle modifiche con il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infrastruttura di sincronizzazione della directory pH contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="dbeb4-129">Criteri di accesso condizionale per l’identità e l’accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="dbeb4-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="dbeb4-130">Contoso ha creato un insieme di [criteri di accesso condizionale](identity-access-policies.md) per Azure AD e Intune per tre livelli di protezione:</span><span class="sxs-lookup"><span data-stu-id="dbeb4-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="dbeb4-131">Le protezioni di *base* si applicano a tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="dbeb4-132">Le protezioni *sensibili* sono valide per i dirigenti e gli addetti ai vertici.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="dbeb4-133">Le protezioni *altamente regolamentate* si applicano agli utenti specifici nei reparti finanziari, legali e di ricerca che hanno accesso a dati fortemente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="dbeb4-134">Di seguito viene indicato l'insieme risultante dei criteri di accesso condizionale per l'identità e il dispositivo contoso.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Criteri di accesso condizionale di identità e dispositivi di Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="dbeb4-136">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="dbeb4-136">Next step</span></span>

<span data-ttu-id="dbeb4-137">[Informazioni](contoso-win10.md) su come Contoso utilizza l'infrastruttura di Microsoft endpoint Configuration Manager per distribuire e mantenere l'attuale Windows 10 Enterprise all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dbeb4-137">[Learn](contoso-win10.md) how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbeb4-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbeb4-138">See also</span></span>

[<span data-ttu-id="dbeb4-139">Roadmap delle identità per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dbeb4-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="dbeb4-140">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="dbeb4-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="dbeb4-141">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="dbeb4-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
