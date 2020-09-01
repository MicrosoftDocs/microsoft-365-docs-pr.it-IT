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
ms.collection: M365-subscription-management
ms.custom: it-pro
description: La Guida di orientamento per la configurazione dei tenant per Microsoft 365.
ms.openlocfilehash: 540d1bc53ac06b85d22a8a60a62e51761e10339c
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315754"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="a67ed-103">Guida di orientamento tenant per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a67ed-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="a67ed-104">Il tenant Microsoft 365 è l'insieme di servizi assegnati alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a67ed-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="a67ed-105">Questo tenant è in genere associato a uno o più nomi di dominio DNS e funge da contenitore centrale per sottoscrizioni diverse e licenze all'interno delle quali viene assegnato agli account utente.</span><span class="sxs-lookup"><span data-stu-id="a67ed-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="a67ed-106">Quando si crea un tenant di Microsoft 365, è possibile assegnarlo a una specifica posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="a67ed-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="a67ed-107">È inoltre possibile disporre di un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.</span><span class="sxs-lookup"><span data-stu-id="a67ed-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="a67ed-108">Una configurazione del tenant ben pianificata e eseguita è fondamentale per prepararla per i servizi di base della rete e dell'identità.</span><span class="sxs-lookup"><span data-stu-id="a67ed-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="a67ed-109">Piano</span><span class="sxs-lookup"><span data-stu-id="a67ed-109">Plan</span></span>

<span data-ttu-id="a67ed-110">Per pianificare l'implementazione del tenant:</span><span class="sxs-lookup"><span data-stu-id="a67ed-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="a67ed-111">Comprendere gli abbonamenti, le licenze e i tenant di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a67ed-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="a67ed-112">Informazioni su come utilizzare i certificati SSL di terze parti</span><span class="sxs-lookup"><span data-stu-id="a67ed-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="a67ed-113">Guide all'installazione di Access nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a67ed-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="a67ed-114">Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="a67ed-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="a67ed-115">Pianificare il supporto delle app client</span><span class="sxs-lookup"><span data-stu-id="a67ed-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="a67ed-116">Determinare la modalità di utilizzo dell'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="a67ed-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="a67ed-117">Pianificare gli aggiornamenti di Office 2007 e Office 2010</span><span class="sxs-lookup"><span data-stu-id="a67ed-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="a67ed-118">Comprendere l'isolamento del tenant</span><span class="sxs-lookup"><span data-stu-id="a67ed-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="a67ed-119">Ottenere i dettagli su Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="a67ed-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="a67ed-120">Distribuire</span><span class="sxs-lookup"><span data-stu-id="a67ed-120">Deploy</span></span>

<span data-ttu-id="a67ed-121">Per distribuire il tenant, [aggiungere i domini DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a67ed-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="a67ed-122">Tenant con più posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="a67ed-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="a67ed-123">Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="a67ed-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="a67ed-124">[Introduzione](microsoft-365-multi-geo.md) a Understanding, Planning, Configuring e then Administering with Microsoft 365 multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="a67ed-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="a67ed-125">Spostare le posizioni geografiche di un tenant</span><span class="sxs-lookup"><span data-stu-id="a67ed-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="a67ed-126">Microsoft continua ad aprire nuove aree geografiche di datacenter (GEOS) per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a67ed-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="a67ed-127">Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti.</span><span class="sxs-lookup"><span data-stu-id="a67ed-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="a67ed-128">Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.</span><span class="sxs-lookup"><span data-stu-id="a67ed-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="a67ed-129">Informazioni introduttive sulla comprensione e la richiesta di spostamento di dati geo con lo [spostamento di dati di base in un nuovo datacenter geografico Microsoft 365](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="a67ed-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="a67ed-130">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a67ed-130">Next step</span></span>

<span data-ttu-id="a67ed-131">Avviare la pianificazione del tenant con [abbonamenti, licenze, account e tenant](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="a67ed-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

