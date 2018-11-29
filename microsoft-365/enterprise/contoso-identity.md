---
title: Identità per Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Come Contoso sfrutta l’identità come servizio (IDaaS) e fornisce l'autenticazione basata su cloud per i dipendenti e l'autenticazione federata per i partner e clienti.
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868748"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="570ca-103">Identità per Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="570ca-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="570ca-104">**Riepilogo:** Come Contoso sfrutta l’identità come servizio (IDaaS) e fornisce l'autenticazione basata su cloud per i dipendenti e l'autenticazione federata per i partner e clienti.</span><span class="sxs-lookup"><span data-stu-id="570ca-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="570ca-p101">Microsoft fornisce un'identità come servizio (IDaaS) tra le offerte cloud con Azure Active Directory (AD). Per adottare Microsoft 365 Enterprise, la soluzione IDaaS di Contoso doveva sfruttare i provider di identità locali e includere l’autenticazione federata con i provider di identità di terze parti esistenti e attendibili.</span><span class="sxs-lookup"><span data-stu-id="570ca-p101">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-windows-server-ad-forest"></a><span data-ttu-id="570ca-107">Foresta di Windows Server AD di Contoso</span><span class="sxs-lookup"><span data-stu-id="570ca-107">Contoso's Windows Server AD forest</span></span>

<span data-ttu-id="570ca-p102">Contoso utilizza una singola foresta Windows Server Active Directory (AD) per contoso.com con sette sottodomini, uno per ogni area geografica del mondo. Sede centrale, hub regionali e uffici secondari contengono controller di dominio per l'autenticazione e l'autorizzazione locale.</span><span class="sxs-lookup"><span data-stu-id="570ca-p102">Contoso uses a single Windows Server Active Directory (AD) forest for contoso.com with seven sub-domains, one for each region of the world. The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="570ca-110">Nella figura 1 viene mostrata la foresta di Contoso con domini regionali per le varie parti del mondo in cui sono presenti sedi centrali regionali.</span><span class="sxs-lookup"><span data-stu-id="570ca-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="570ca-111">**Figura 1: foresta di Contoso e domini a livello mondiale**</span><span class="sxs-lookup"><span data-stu-id="570ca-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="570ca-112">Contoso desidera utilizzare gli account e i gruppi della foresta contoso.com per l'autenticazione e l'autorizzazione per le app basate su cloud e per i carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="570ca-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="570ca-113">Infrastruttura di autenticazione federata di Contoso</span><span class="sxs-lookup"><span data-stu-id="570ca-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="570ca-114">Contoso consente:</span><span class="sxs-lookup"><span data-stu-id="570ca-114">Contoso allows:</span></span>

- <span data-ttu-id="570ca-115">Ai clienti di usare il proprio account Microsoft, Facebook o Google Mail per accedere al proprio sito Web pubblico.</span><span class="sxs-lookup"><span data-stu-id="570ca-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="570ca-116">Ai fornitori e ai partner di usare il proprio account LinkedIn, Salesforce o Google Mail per accedere all’extranet dei partner.</span><span class="sxs-lookup"><span data-stu-id="570ca-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="570ca-p103">Nella figura 2 viene mostrata la rete perimetrale di Contoso contenente un sito Web pubblico, una rete extranet partner e un set di server Active Directory Federation Service (AD FS). La rete perimetrale è connessa alla rete Internet che contiene clienti, partner e servizi Internet.</span><span class="sxs-lookup"><span data-stu-id="570ca-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="570ca-119">**Figura 2: Supporto di Contoso per l'autenticazione federata di clienti e partner**</span><span class="sxs-lookup"><span data-stu-id="570ca-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="570ca-120">I server AD FS nella DMZ autenticano le credenziali dei clienti per l'accesso al sito Web pubblico e le credenziali dei partner per l'accesso all’extranet dei partner.</span><span class="sxs-lookup"><span data-stu-id="570ca-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="570ca-p104">Contoso ha deciso di mantenere questa infrastruttura e dedicarla alle autenticazioni di clienti e partner. I tecnici dell’identità di Contoso stanno studiando la conversione di questa infrastruttura alle soluzioni [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="570ca-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a><span data-ttu-id="570ca-123">Identità ibrida con autenticazione pass-through per l'autenticazione basata su cloud</span><span class="sxs-lookup"><span data-stu-id="570ca-123">Hybrid identity with pass-through authentication for cloud-based authentication</span></span>

<span data-ttu-id="570ca-p105">Contoso desiderava sfruttare la foresta di Windows Server AD locale per l'autenticazione alle risorse del cloud di Microsoft 365. Ha scelto l’autenticazione pass-through (PTA) con la sincronizzazione hash delle password (PHS).</span><span class="sxs-lookup"><span data-stu-id="570ca-p105">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span>

### <a name="pta-authentication"></a><span data-ttu-id="570ca-126">Autenticazione PTA</span><span class="sxs-lookup"><span data-stu-id="570ca-126">PTA authentication</span></span>

<span data-ttu-id="570ca-p106">Per l'autenticazione delle credenziali dell'utente, Contoso usa PTA. Quando un utente di Contoso accede a una risorsa basata sul cloud, le credenziali inviate vengono trasmesse da Azure AD a un server che esegue un agente di autenticazione nel datacenter della sede centrale di Contoso. Uno di questi server agente di autenticazione convalida le credenziali utente per conto di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="570ca-p106">For authentication of user credentials, Contoso is using PTA. When a Contoso user accesses a cloud-based resources, the credentials it sends are passed by Azure AD to a server running an Authentication Agent in the Contoso headquarters datacenter. One of these Authentication Agent servers validates the user credentials on behalf of Azure AD.</span></span>

<span data-ttu-id="570ca-130">La Figura 3 mostra un set di server nella sede centrale di Contoso che eseguono l'agente di autenticazione e che elaborano le richieste di autenticazione trasmesse da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="570ca-130">Figure 3 shows a set of servers in the Contoso headquarters running the Authentication Agent, which process authentication requests passed to it from Azure AD.</span></span> 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
<span data-ttu-id="570ca-131">**Figura 3: infrastruttura di autenticazione pass-through di Contoso**</span><span class="sxs-lookup"><span data-stu-id="570ca-131">**Figure 3: Contoso's pass-through authentication infrastructure**</span></span>

<span data-ttu-id="570ca-132">Contoso ha scelto PTA per soddisfare i requisiti di sicurezza che richiedono tutti i tentativi di autenticazione siano valutati per controllare modifiche immediate agli stati dell'account utente, ai criteri per le password e alle ore di accesso apportate alla foresta di Windows Server AD locale.</span><span class="sxs-lookup"><span data-stu-id="570ca-132">Contoso chose PTA to fulfill its security requirement that all authentication attempts be evaluated for immediate changes to user account states, password policies, and sign-in hours made to the on-premises Windows Server AD forest.</span></span>

### <a name="phs"></a><span data-ttu-id="570ca-133">PHS</span><span class="sxs-lookup"><span data-stu-id="570ca-133">PHS</span></span>

<span data-ttu-id="570ca-p107">PHS sincronizza la foresta di Windows Server AD locale con il tenant Azure AD dell’abbonamento a Microsoft 365 Enterprise, copiando gli account utente e gruppo e una versione sottoposta a hashing della password dell'account utente. Contoso ha deciso che PHS fornirà un metodo alternativo per l'autenticazione direttamente con il tenant Azure AD nel caso in cui l’autenticazione PTA non sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="570ca-p107">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span>

<span data-ttu-id="570ca-p108">Per eseguire la sincronizzazione della directory in corso, Contoso ha distribuito lo strumento Azure AD Connect in un server nel suo datacenter di Parigi. La Figura 4 mostra il server che esegue Azure AD Connect mentre sonda la foresta di Windows Server AD di Contoso alla ricerca di modifiche e quindi sincronizza le stesse modifiche con il tenant Azure AD.</span><span class="sxs-lookup"><span data-stu-id="570ca-p108">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="570ca-138">**Figura 4: infrastruttura di sincronizzazione della directory PHS di Contoso**</span><span class="sxs-lookup"><span data-stu-id="570ca-138">**Figure 4: Contoso's PHS directory synchronization infrastructure**</span></span>

## <a name="conditional-access-policies-for-identity"></a><span data-ttu-id="570ca-139">Criteri di accesso condizionale per l’identità</span><span class="sxs-lookup"><span data-stu-id="570ca-139">Conditional access policies for identity</span></span>

<span data-ttu-id="570ca-140">Contoso ha creato un set di [criteri di accesso condizionale](identity-access-policies.md) di Azure AD per garantire l’applicazione dell’autenticazione a più fattori e delle modifiche delle password quando Azure AD determina che c’è un rischio di accesso per una richiesta di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="570ca-140">Contoso created a set of Azure AD [conditional access policies](identity-access-policies.md) to ensure that multi-factor authentication and password changes are enforced when Azure AD determines there is sign-in risk for an authentication request.</span></span>

<span data-ttu-id="570ca-141">La figura 5 mostra il set risultante di criteri di accesso condizionale per l’identità.</span><span class="sxs-lookup"><span data-stu-id="570ca-141">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="570ca-142">**Figura 5: i criteri di accesso condizionale basato sull'identità di Contoso**</span><span class="sxs-lookup"><span data-stu-id="570ca-142">**Figure 5: Contoso’s identity-based conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="570ca-143">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="570ca-143">Next step</span></span>

<span data-ttu-id="570ca-144">[Informazioni su](contoso-win10.md) come Contoso si avvale dell'infrastruttura di System Center Configuration Manager per distribuire e mantenere Windows 10 Enterprise nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="570ca-144">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="570ca-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="570ca-145">See also</span></span>

[<span data-ttu-id="570ca-146">Identità per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="570ca-146">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="570ca-147">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="570ca-147">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="570ca-148">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="570ca-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
