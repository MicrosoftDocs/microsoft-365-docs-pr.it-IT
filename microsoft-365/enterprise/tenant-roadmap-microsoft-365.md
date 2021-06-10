---
title: Roadmap tenant per Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: La roadmap per configurare i tenant per Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909455"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="b79d9-103">Roadmap tenant per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b79d9-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="b79d9-104">Il Microsoft 365 tenant è il set di servizi assegnati all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b79d9-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="b79d9-105">In genere, questo tenant è associato a uno o più nomi di dominio DNS pubblici e funge da contenitore centrale e isolato per sottoscrizioni diverse e le licenze in essi assegnate agli account utente.</span><span class="sxs-lookup"><span data-stu-id="b79d9-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="b79d9-106">Per ulteriori informazioni, vedere [Sottoscrizioni, licenze, account](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)e tenant per le offerte cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b79d9-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="b79d9-107">Quando si crea un tenant Microsoft 365, lo si assegna a una posizione geografica specifica.</span><span class="sxs-lookup"><span data-stu-id="b79d9-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="b79d9-108">È inoltre possibile avere un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.</span><span class="sxs-lookup"><span data-stu-id="b79d9-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="b79d9-109">Per preparare il tenant per utenti, gruppi, licenze e app cloud, è fondamentale pianificare ed eseguire con attenzione la configurazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="b79d9-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="b79d9-110">Configurare il tenant Microsoft 365 tenant</span><span class="sxs-lookup"><span data-stu-id="b79d9-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="b79d9-111">Dopo aver garantito che la rete sia ottimizzata per l'accesso a Microsoft 365 sia per i lavoratori locali che per i lavoratori remoti, le attività più importanti sono la pianificazione e la configurazione del tenant di Microsoft 365 per i nomi di dominio DNS, i servizi comuni e per l'infrastruttura di identità che supporta l'accesso utente sicuro.</span><span class="sxs-lookup"><span data-stu-id="b79d9-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="b79d9-112">Pianificare</span><span class="sxs-lookup"><span data-stu-id="b79d9-112">Plan</span></span>

<span data-ttu-id="b79d9-113">Per pianificare l'implementazione del tenant:</span><span class="sxs-lookup"><span data-stu-id="b79d9-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="b79d9-114">Informazioni su sottoscrizioni, licenze e tenant Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b79d9-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="b79d9-115">Informazioni su come usare certificati SSL di terze parti</span><span class="sxs-lookup"><span data-stu-id="b79d9-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="b79d9-116">Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="b79d9-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="b79d9-117">Pianificare il supporto delle app client</span><span class="sxs-lookup"><span data-stu-id="b79d9-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="b79d9-118">Determinare come usare l'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="b79d9-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="b79d9-119">Pianificare gli Office 2007 e Office 2010</span><span class="sxs-lookup"><span data-stu-id="b79d9-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="b79d9-120">Comprendere l'isolamento del tenant</span><span class="sxs-lookup"><span data-stu-id="b79d9-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="b79d9-121">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="b79d9-121">Deploy</span></span>

<span data-ttu-id="b79d9-122">Per distribuire il tenant:</span><span class="sxs-lookup"><span data-stu-id="b79d9-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="b79d9-123">Aggiungere i [domini DNS](../admin/setup/add-domain.md) per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b79d9-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="b79d9-124">Usare le [guide alla configurazione nell'Microsoft 365 di amministrazione.](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="b79d9-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="b79d9-125">Creare [l'infrastruttura di identità](identity-roadmap-microsoft-365.md) e proteggere gli account di accesso degli [utenti.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="b79d9-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="b79d9-126">Spostare le posizioni geografiche di un tenant</span><span class="sxs-lookup"><span data-stu-id="b79d9-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="b79d9-127">Microsoft continua ad aprire nuove posizioni geografiche del datacenter (geo) per Microsoft 365 servizi.</span><span class="sxs-lookup"><span data-stu-id="b79d9-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="b79d9-128">Questi nuovi geo datacenter aggiungono capacità e risorse di calcolo per supportare la domanda dei clienti e la crescita dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="b79d9-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="b79d9-129">Inoltre, i nuovi dati geografici del datacenter offrono la residenza dei dati in-geo per i dati principali dei clienti.</span><span class="sxs-lookup"><span data-stu-id="b79d9-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="b79d9-130">Per ulteriori informazioni, vedere [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="b79d9-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="b79d9-131">Distribuire Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="b79d9-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="b79d9-132">Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="b79d9-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="b79d9-133">Per ulteriori informazioni, vedere [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="b79d9-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="b79d9-134">Gestire più Microsoft 365 tenant</span><span class="sxs-lookup"><span data-stu-id="b79d9-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="b79d9-135">Anche se avere un singolo tenant per la tua oganizzazione è ideale, potresti essere una delle molte organizzazioni che hanno più tenant.</span><span class="sxs-lookup"><span data-stu-id="b79d9-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="b79d9-136">I motivi possono includere fusioni e acquisizioni, si desidera l'isolamento amministrativo o si dispone di un'IT decentralizzata.</span><span class="sxs-lookup"><span data-stu-id="b79d9-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="b79d9-137">Se si dispone di Microsoft 365 tenant, vedere questi articoli per ulteriori informazioni su:</span><span class="sxs-lookup"><span data-stu-id="b79d9-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="b79d9-138">Collaborazione tra tenant</span><span class="sxs-lookup"><span data-stu-id="b79d9-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="b79d9-139">Migrazione delle cassette postali tra tenant</span><span class="sxs-lookup"><span data-stu-id="b79d9-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="b79d9-140">Migrazioni da tenant a tenant</span><span class="sxs-lookup"><span data-stu-id="b79d9-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="b79d9-141">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b79d9-141">Next step</span></span>

<span data-ttu-id="b79d9-142">Iniziare la pianificazione del tenant [con Sottoscrizioni, licenze, account e tenant.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="b79d9-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>