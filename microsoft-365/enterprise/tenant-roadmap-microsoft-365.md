---
title: Guida di orientamento tenant per Microsoft 365
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
description: La Guida di orientamento per la configurazione dei tenant per Microsoft 365.
ms.openlocfilehash: 038d9b0d94b84d184f0d9d9b250d0ee4d2c19de9
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753967"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="10872-103">Guida di orientamento tenant per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10872-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="10872-104">Il tenant Microsoft 365 è l'insieme di servizi assegnati alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="10872-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="10872-105">In genere, questo tenant è associato a uno o più nomi di dominio DNS pubblici e funge da contenitore centrale e isolato per sottoscrizioni diverse e licenze all'interno delle quali viene assegnato agli account utente.</span><span class="sxs-lookup"><span data-stu-id="10872-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="10872-106">Per ulteriori informazioni, vedere [abbonamenti, licenze, account e tenant per offerte cloud di Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="10872-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="10872-107">Quando si crea un tenant di Microsoft 365, è possibile assegnarlo a una specifica posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="10872-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="10872-108">È inoltre possibile disporre di un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.</span><span class="sxs-lookup"><span data-stu-id="10872-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="10872-109">Per ottenere il tenant pronto per l'utente, i gruppi, le licenze e le app del cloud, è importante pianificare attentamente ed eseguire la configurazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="10872-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="10872-110">Configurare il tenant di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10872-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="10872-111">Dopo aver verificato che la rete sia stata ottimizzata per l'accesso a Microsoft 365 sia per gli addetti locali che per i dipendenti remoti, le attività importanti successive stanno pianificando e configurando il tenant di Microsoft 365 per i nomi di dominio DNS, i servizi comuni e l'infrastruttura di identità che supporta l'accesso sicuro degli utenti.</span><span class="sxs-lookup"><span data-stu-id="10872-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="10872-112">Piano</span><span class="sxs-lookup"><span data-stu-id="10872-112">Plan</span></span>

<span data-ttu-id="10872-113">Per pianificare l'implementazione del tenant:</span><span class="sxs-lookup"><span data-stu-id="10872-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="10872-114">Comprendere gli abbonamenti, le licenze e i tenant di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="10872-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="10872-115">Informazioni su come utilizzare i certificati SSL di terze parti</span><span class="sxs-lookup"><span data-stu-id="10872-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="10872-116">Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="10872-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="10872-117">Pianificare il supporto delle app client</span><span class="sxs-lookup"><span data-stu-id="10872-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="10872-118">Determinare la modalità di utilizzo dell'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="10872-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="10872-119">Pianificare gli aggiornamenti di Office 2007 e Office 2010</span><span class="sxs-lookup"><span data-stu-id="10872-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="10872-120">Comprendere l'isolamento del tenant</span><span class="sxs-lookup"><span data-stu-id="10872-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="10872-121">Distribuire</span><span class="sxs-lookup"><span data-stu-id="10872-121">Deploy</span></span>

<span data-ttu-id="10872-122">Per distribuire il tenant:</span><span class="sxs-lookup"><span data-stu-id="10872-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="10872-123">Aggiungere i [domini DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="10872-123">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="10872-124">Utilizzare le [guide all'installazione nell'interfaccia di amministrazione di Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="10872-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="10872-125">Creare l' [infrastruttura di identità](identity-roadmap-microsoft-365.md) e [proteggere gli accessi degli utenti](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="10872-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="10872-126">Spostare le posizioni geografiche di un tenant</span><span class="sxs-lookup"><span data-stu-id="10872-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="10872-127">Microsoft continua ad aprire nuove aree geografiche di datacenter (GEOS) per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10872-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="10872-128">Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti.</span><span class="sxs-lookup"><span data-stu-id="10872-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="10872-129">Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.</span><span class="sxs-lookup"><span data-stu-id="10872-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="10872-130">Per ulteriori informazioni, vedere [Moving core data to New Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="10872-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="10872-131">Distribuire Microsoft 365 multi-Geo</span><span class="sxs-lookup"><span data-stu-id="10872-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="10872-132">Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="10872-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="10872-133">Per ulteriori informazioni, vedere [Microsoft 365 multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="10872-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenant"></a><span data-ttu-id="10872-134">Gestire più tenant Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10872-134">Manage multiple Microsoft 365 tenant</span></span> 

<span data-ttu-id="10872-135">Anche se l'utilizzo di un singolo tenant per il Oganization è l'ideale, potrebbe essere una delle numerose organizzazioni con più tenant.</span><span class="sxs-lookup"><span data-stu-id="10872-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenant.</span></span> <span data-ttu-id="10872-136">I motivi possono includere fusioni e acquisizioni, si desidera l'isolamento amministrativo o si dispone di una decentralizzata.</span><span class="sxs-lookup"><span data-stu-id="10872-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="10872-137">Se si dispone di più tenant Microsoft 365, vedere questi articoli per ulteriori informazioni su:</span><span class="sxs-lookup"><span data-stu-id="10872-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="10872-138">Collaborazione tra tenant</span><span class="sxs-lookup"><span data-stu-id="10872-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="10872-139">Migrazione delle cassette postali tra tenant</span><span class="sxs-lookup"><span data-stu-id="10872-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="10872-140">Migrazioni da tenant a tenant</span><span class="sxs-lookup"><span data-stu-id="10872-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="10872-141">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="10872-141">Next step</span></span>

<span data-ttu-id="10872-142">Avviare la pianificazione del tenant con [abbonamenti, licenze, account e tenant](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="10872-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
