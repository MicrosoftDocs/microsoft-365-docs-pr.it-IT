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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Come Contoso sfrutta l’identità come servizio (IDaaS) e fornisce l'autenticazione basata su cloud per i dipendenti e l'autenticazione federata per i partner e clienti.
ms.openlocfilehash: 77c90740fd39080ccc204552bc8407aa107e354a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068457"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="fb782-103">Identità per Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="fb782-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="fb782-104">Microsoft fornisce un'identità come servizio (IDaaS) per le offerte cloud con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="fb782-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="fb782-105">Per adottare Microsoft 365 Enterprise, la soluzione IDaaS di Contoso deve sfruttare i provider di identità locali e includere l'autenticazione federata con i provider di identità di terze parti esistenti e attendibili.</span><span class="sxs-lookup"><span data-stu-id="fb782-105">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="fb782-106">Foresta di Servizi di dominio di Active Directory di Contoso</span><span class="sxs-lookup"><span data-stu-id="fb782-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="fb782-107">Contoso usa una foresta di Servizi di dominio di Active Directory (AD DS) singola per contoso.com con sette sottodomini, uno per ogni area geografica del mondo.</span><span class="sxs-lookup"><span data-stu-id="fb782-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="fb782-108">La sede principale, le sedi centrali regionali e le filiali contengono controller di dominio per l'autorizzazione e l'autenticazione locali.</span><span class="sxs-lookup"><span data-stu-id="fb782-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="fb782-109">Di seguito viene mostrata la foresta di Contoso con domini regionali per le varie parti del mondo in cui sono presenti sedi centrali regionali.</span><span class="sxs-lookup"><span data-stu-id="fb782-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Foresta di Contoso e domini a livello mondiale](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="fb782-111">Contoso ha voluto utilizzare gli account e i gruppi della foresta contoso.com per l'autenticazione e l'autorizzazione per i servizi e i carichi di lavoro su Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb782-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="fb782-112">Infrastruttura di autenticazione federata di Contoso</span><span class="sxs-lookup"><span data-stu-id="fb782-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="fb782-113">Contoso consente:</span><span class="sxs-lookup"><span data-stu-id="fb782-113">Contoso allows:</span></span>

- <span data-ttu-id="fb782-114">Ai clienti di usare il proprio account Microsoft, Facebook o Google Mail per accedere al proprio sito Web pubblico.</span><span class="sxs-lookup"><span data-stu-id="fb782-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="fb782-115">Ai fornitori e ai partner di usare il proprio account LinkedIn, Salesforce o Google Mail per accedere all’extranet dei partner.</span><span class="sxs-lookup"><span data-stu-id="fb782-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="fb782-p103">Di seguito viene mostrata la rete perimetrale di Contoso contenente un sito Web pubblico, una rete extranet partner e un set di server Active Directory Federation Services (AD FS). La rete perimetrale è connessa alla rete Internet che contiene clienti, partner e servizi Internet.</span><span class="sxs-lookup"><span data-stu-id="fb782-p103">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Supporto di Contoso per l'autenticazione federata di clienti e partner](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="fb782-119">I server AD FS nella DMZ semplificano l'autenticazione delle credenziali dei clienti da parte dei relativi provider di identità per l'accesso al sito Web pubblico e delle credenziali dei partner per l'accesso alla Extranet dei partner.</span><span class="sxs-lookup"><span data-stu-id="fb782-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="fb782-p104">Contoso ha deciso di mantenere questa infrastruttura e dedicarla alle autenticazioni di clienti e partner. Gli architetti dell’identità di Contoso stanno studiando la conversione di questa infrastruttura alle soluzioni [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fb782-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="fb782-122">Identità ibrida con sincronizzazione dell'hash delle password per l'autenticazione basata su cloud</span><span class="sxs-lookup"><span data-stu-id="fb782-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="fb782-123">Contoso ha voluto sfruttare la foresta AD DS locale per l'autenticazione alle risorse cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb782-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="fb782-124">Ha deciso per la sincronizzazione dell'hash delle password (PHS).</span><span class="sxs-lookup"><span data-stu-id="fb782-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="fb782-125">PHS sincronizza la foresta locale di Active Directory con il tenant Azure AD dell'abbonamento a Microsoft 365 Enterprise, copiando gli account utente e gruppo e una versione hash della password dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="fb782-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="fb782-126">Per eseguire la sincronizzazione delle directory in corso, Contoso ha distribuito lo strumento Azure AD Connect in un server nel Data Center di Parigi.</span><span class="sxs-lookup"><span data-stu-id="fb782-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="fb782-127">Di seguito viene mostrato il server che esegue Azure AD Connect mentre sonda la foresta AD DS di Contoso per le modifiche e quindi sincronizza le modifiche apportate con il tenant Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fb782-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infrastruttura di sincronizzazione della directory PHS di Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="fb782-129">Criteri di accesso condizionale per l’identità e l’accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="fb782-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="fb782-130">Contoso ha creato un insieme di [criteri di accesso condizionale](identity-access-policies.md) per Azure AD e Intune per tre livelli di protezione:</span><span class="sxs-lookup"><span data-stu-id="fb782-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="fb782-131">**Base** le protezioni si applicano a tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="fb782-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="fb782-132">**Riservate** le protezioni si applicano a dirigenti senior e staff esecutivo</span><span class="sxs-lookup"><span data-stu-id="fb782-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="fb782-133">Le protezioni di**Riservatezza elevata** si applicano a utenti specifici nei dipartimenti finanziario, legale e di ricerca che hanno accesso a dati altamente riservati</span><span class="sxs-lookup"><span data-stu-id="fb782-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="fb782-134">Di seguito viene mostrato l’insieme di risultati dei criteri di accesso condizionale di identità e dispositivi di Contoso.</span><span class="sxs-lookup"><span data-stu-id="fb782-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Criteri di accesso condizionale di identità e dispositivi di Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="fb782-136">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="fb782-136">Next step</span></span>

<span data-ttu-id="fb782-137">[Informazioni su](contoso-win10.md) come Contoso si avvale dell'infrastruttura di Microsoft Endpoint Configuration Manager per distribuire e mantenere aggiornato Windows 10 Enterprise nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb782-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb782-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb782-138">See also</span></span>

[<span data-ttu-id="fb782-139">Identità per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fb782-139">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="fb782-140">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="fb782-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fb782-141">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="fb782-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
