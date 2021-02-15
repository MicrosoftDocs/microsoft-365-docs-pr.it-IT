---
title: Roadmap del tenant per Microsoft 365
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
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948398"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="cc69a-103">Roadmap del tenant per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc69a-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="cc69a-104">Il tenant di Microsoft 365 è il set di servizi assegnati all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc69a-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="cc69a-105">In genere, questo tenant è associato a uno o più nomi di dominio DNS pubblici e funge da contenitore centrale e isolato per sottoscrizioni diverse e le licenze al loro interno assegnate agli account utente.</span><span class="sxs-lookup"><span data-stu-id="cc69a-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="cc69a-106">Per ulteriori informazioni, vedere [Sottoscrizioni, licenze, account](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)e tenant per le offerte cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc69a-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="cc69a-107">Quando si crea un tenant di Microsoft 365, questo viene assegnato a una posizione geografica specifica.</span><span class="sxs-lookup"><span data-stu-id="cc69a-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="cc69a-108">È inoltre possibile avere un tenant con più posizioni geografiche e spostare il tenant da una posizione all'altra.</span><span class="sxs-lookup"><span data-stu-id="cc69a-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="cc69a-109">Per prepararsi al tenant per utenti, gruppi, licenze e app cloud, è fondamentale pianificare ed eseguire con attenzione la configurazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="cc69a-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="cc69a-110">Configurare il tenant di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc69a-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="cc69a-111">Dopo aver garantito che la rete sia ottimizzata per l'accesso a Microsoft 365 sia per i lavoratori locali che per i lavoratori remoti, le prossime grandi attività sono la pianificazione e la configurazione del tenant di Microsoft 365 per i nomi di dominio DNS, i servizi comuni e per l'infrastruttura di gestione delle identità che supporta l'accesso degli utenti protetti.</span><span class="sxs-lookup"><span data-stu-id="cc69a-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="cc69a-112">Piano</span><span class="sxs-lookup"><span data-stu-id="cc69a-112">Plan</span></span>

<span data-ttu-id="cc69a-113">Per pianificare l'implementazione del tenant:</span><span class="sxs-lookup"><span data-stu-id="cc69a-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="cc69a-114">Informazioni su sottoscrizioni, licenze e tenant di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="cc69a-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="cc69a-115">Informazioni su come utilizzare certificati SSL di terze parti</span><span class="sxs-lookup"><span data-stu-id="cc69a-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="cc69a-116">Comprendere i modi in cui un tenant di Microsoft 365 è integrato con i servizi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc69a-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="cc69a-117">Pianificare il supporto delle app client</span><span class="sxs-lookup"><span data-stu-id="cc69a-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="cc69a-118">Determinare come utilizzare l'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="cc69a-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="cc69a-119">Pianificare gli aggiornamenti di Office 2007 e Office 2010</span><span class="sxs-lookup"><span data-stu-id="cc69a-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="cc69a-120">Comprendere l'isolamento del tenant</span><span class="sxs-lookup"><span data-stu-id="cc69a-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="cc69a-121">Distribuire</span><span class="sxs-lookup"><span data-stu-id="cc69a-121">Deploy</span></span>

<span data-ttu-id="cc69a-122">Per distribuire il tenant:</span><span class="sxs-lookup"><span data-stu-id="cc69a-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="cc69a-123">Aggiungere i [domini DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc69a-123">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="cc69a-124">Usare le [guide alla configurazione nell'interfaccia di amministrazione di Microsoft 365.](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="cc69a-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="cc69a-125">Creare [l'infrastruttura di gestione delle](identity-roadmap-microsoft-365.md) identità e proteggere gli account di accesso degli [utenti.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="cc69a-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="cc69a-126">Spostare le posizioni geografiche di un tenant</span><span class="sxs-lookup"><span data-stu-id="cc69a-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="cc69a-127">Microsoft continua ad aprire nuove posizioni geografiche del datacenter (geo) per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc69a-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="cc69a-128">Questi nuovi centri dati geografici aggiungono capacità e risorse di calcolo per supportare la domanda dei clienti e la crescita dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="cc69a-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="cc69a-129">Inoltre, le nuove posizioni geografiche del datacenter offrono la residenza dei dati in-geo per i dati principali dei clienti.</span><span class="sxs-lookup"><span data-stu-id="cc69a-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="cc69a-130">Per ulteriori informazioni, vedere Spostamento dei dati di base in nuove posizioni geografiche del [datacenter di Microsoft 365.](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="cc69a-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="cc69a-131">Distribuire Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="cc69a-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="cc69a-132">Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="cc69a-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="cc69a-133">Per ulteriori informazioni, vedere [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="cc69a-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="cc69a-134">Gestire più tenant di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc69a-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="cc69a-135">Anche se è ideale disporre di un singolo tenant per l'oganizzazione, è possibile che tu sia una delle molte organizzazioni con più tenant.</span><span class="sxs-lookup"><span data-stu-id="cc69a-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="cc69a-136">I motivi possono includere fusioni e acquisizioni, l'isolamento amministrativo o l'it decentralizzato.</span><span class="sxs-lookup"><span data-stu-id="cc69a-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="cc69a-137">Se si dispone di più tenant di Microsoft 365, vedere questi articoli per ulteriori informazioni su:</span><span class="sxs-lookup"><span data-stu-id="cc69a-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="cc69a-138">Collaborazione tra tenant</span><span class="sxs-lookup"><span data-stu-id="cc69a-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="cc69a-139">Migrazione delle cassette postali tra tenant</span><span class="sxs-lookup"><span data-stu-id="cc69a-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="cc69a-140">Migrazioni da tenant a tenant</span><span class="sxs-lookup"><span data-stu-id="cc69a-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="cc69a-141">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="cc69a-141">Next step</span></span>

<span data-ttu-id="cc69a-142">Iniziare la pianificazione del tenant [con sottoscrizioni, licenze, account e tenant.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="cc69a-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
