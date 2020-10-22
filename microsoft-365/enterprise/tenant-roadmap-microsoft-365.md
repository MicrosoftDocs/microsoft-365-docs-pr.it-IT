---
title: Guida di orientamento tenant per Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: La Guida di orientamento per la configurazione dei tenant per Microsoft 365.
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656008"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="55cf3-103">Guida di orientamento tenant per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55cf3-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="55cf3-104">Il tenant Microsoft 365 è l'insieme di servizi assegnati alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55cf3-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="55cf3-105">In genere, questo tenant è associato a uno o più nomi di dominio DNS e funge da contenitore centrale per sottoscrizioni diverse e licenze all'interno delle quali viene assegnato agli account utente.</span><span class="sxs-lookup"><span data-stu-id="55cf3-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="55cf3-106">Per ulteriori informazioni, vedere [abbonamenti, licenze, account e tenant per offerte cloud di Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="55cf3-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="55cf3-107">Quando si crea un tenant di Microsoft 365, è possibile assegnarlo a una specifica posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="55cf3-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="55cf3-108">È inoltre possibile disporre di un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.</span><span class="sxs-lookup"><span data-stu-id="55cf3-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="55cf3-109">Per ottenere il tenant pronto per l'identità, è importante pianificare attentamente ed eseguire la configurazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="55cf3-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="55cf3-110">Configurare il tenant di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55cf3-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="55cf3-111">Dopo aver verificato che la rete sia stata ottimizzata per l'accesso a Microsoft 365 sia per gli addetti locali che per i dipendenti remoti, le attività importanti successive stanno pianificando e configurando il tenant di Microsoft 365 per i nomi di dominio DNS, i servizi comuni e l'infrastruttura di identità che supporta l'accesso sicuro degli utenti.</span><span class="sxs-lookup"><span data-stu-id="55cf3-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="55cf3-112">Piano</span><span class="sxs-lookup"><span data-stu-id="55cf3-112">Plan</span></span>

<span data-ttu-id="55cf3-113">Per pianificare l'implementazione del tenant:</span><span class="sxs-lookup"><span data-stu-id="55cf3-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="55cf3-114">Comprendere gli abbonamenti, le licenze e i tenant di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="55cf3-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="55cf3-115">Informazioni su come utilizzare i certificati SSL di terze parti</span><span class="sxs-lookup"><span data-stu-id="55cf3-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="55cf3-116">Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="55cf3-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="55cf3-117">Pianificare il supporto delle app client</span><span class="sxs-lookup"><span data-stu-id="55cf3-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="55cf3-118">Determinare la modalità di utilizzo dell'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="55cf3-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="55cf3-119">Pianificare gli aggiornamenti di Office 2007 e Office 2010</span><span class="sxs-lookup"><span data-stu-id="55cf3-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="55cf3-120">Comprendere l'isolamento del tenant</span><span class="sxs-lookup"><span data-stu-id="55cf3-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="55cf3-121">Ottenere i dettagli su Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="55cf3-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="55cf3-122">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="55cf3-122">Deploy</span></span>

<span data-ttu-id="55cf3-123">Per distribuire il tenant:</span><span class="sxs-lookup"><span data-stu-id="55cf3-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="55cf3-124">Aggiungere i [domini DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55cf3-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="55cf3-125">Utilizzare le [guide all'installazione nell'interfaccia di amministrazione di Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="55cf3-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="55cf3-126">Creare l' [infrastruttura di identità](identity-roadmap-microsoft-365.md) e [proteggere gli accessi degli utenti](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="55cf3-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="55cf3-127">Spostare le posizioni geografiche di un tenant</span><span class="sxs-lookup"><span data-stu-id="55cf3-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="55cf3-128">Microsoft continua ad aprire nuove aree geografiche di datacenter (GEOS) per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55cf3-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="55cf3-129">Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti.</span><span class="sxs-lookup"><span data-stu-id="55cf3-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="55cf3-130">Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.</span><span class="sxs-lookup"><span data-stu-id="55cf3-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="55cf3-131">Per ulteriori informazioni, vedere [Moving core data to New Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="55cf3-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="55cf3-132">Distribuire Microsoft 365 multi-Geo</span><span class="sxs-lookup"><span data-stu-id="55cf3-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="55cf3-133">Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="55cf3-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="55cf3-134">Per ulteriori informazioni, vedere [Microsoft 365 multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="55cf3-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="55cf3-135">Gestire più Microsoft 365 locazione</span><span class="sxs-lookup"><span data-stu-id="55cf3-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="55cf3-136">Anche se l'utilizzo di un singolo tenant per il Oganization è ideale, potrebbe essere una delle numerose organizzazioni con più locazione.</span><span class="sxs-lookup"><span data-stu-id="55cf3-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="55cf3-137">Per motivi multipli di locazione è possibile includere fusioni e acquisizioni, si desidera l'isolamento amministrativo o si dispone di una decentralizzata.</span><span class="sxs-lookup"><span data-stu-id="55cf3-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="55cf3-138">Se si dispone di più di Microsoft 365 locazione, vedere questi articoli per ulteriori informazioni su:</span><span class="sxs-lookup"><span data-stu-id="55cf3-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="55cf3-139">Collaborazione tra tenant</span><span class="sxs-lookup"><span data-stu-id="55cf3-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="55cf3-140">Migrazione delle cassette postali tra tenant</span><span class="sxs-lookup"><span data-stu-id="55cf3-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="55cf3-141">Migrazioni da tenant a tenant</span><span class="sxs-lookup"><span data-stu-id="55cf3-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="55cf3-142">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="55cf3-142">Next step</span></span>

<span data-ttu-id="55cf3-143">Avviare la pianificazione del tenant con [abbonamenti, licenze, account e tenant](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="55cf3-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
