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
- M365initiative-coredeploy
ms.custom: it-pro
description: La Guida di orientamento per la configurazione dei tenant per Microsoft 365.
ms.openlocfilehash: e4b2af9143070caa1ebd8fd66ef9f367f85d3bb9
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357911"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="4bfea-103">Guida di orientamento tenant per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4bfea-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="4bfea-104">Il tenant Microsoft 365 è l'insieme di servizi assegnati alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4bfea-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="4bfea-105">In genere, questo tenant è associato a uno o più nomi di dominio DNS e funge da contenitore centrale per sottoscrizioni diverse e licenze all'interno delle quali viene assegnato agli account utente.</span><span class="sxs-lookup"><span data-stu-id="4bfea-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="4bfea-106">Quando si crea un tenant di Microsoft 365, è possibile assegnarlo a una specifica posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="4bfea-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="4bfea-107">È inoltre possibile disporre di un tenant con più posizioni geografiche e spostare il tenant da una posizione a un'altra.</span><span class="sxs-lookup"><span data-stu-id="4bfea-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="4bfea-108">Per ottenere il tenant pronto per i servizi di base della rete e dell'identità, è importante pianificare attentamente ed eseguire la configurazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="4bfea-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="4bfea-109">Piano</span><span class="sxs-lookup"><span data-stu-id="4bfea-109">Plan</span></span>

<span data-ttu-id="4bfea-110">Per pianificare l'implementazione del tenant:</span><span class="sxs-lookup"><span data-stu-id="4bfea-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="4bfea-111">Comprendere gli abbonamenti, le licenze e i tenant di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="4bfea-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="4bfea-112">Informazioni su come utilizzare i certificati SSL di terze parti</span><span class="sxs-lookup"><span data-stu-id="4bfea-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="4bfea-113">Comprendere i modi in cui un tenant Microsoft 365 è integrato con i servizi di Azure AD</span><span class="sxs-lookup"><span data-stu-id="4bfea-113">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="4bfea-114">Pianificare il supporto delle app client</span><span class="sxs-lookup"><span data-stu-id="4bfea-114">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="4bfea-115">Determinare la modalità di utilizzo dell'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="4bfea-115">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="4bfea-116">Pianificare gli aggiornamenti di Office 2007 e Office 2010</span><span class="sxs-lookup"><span data-stu-id="4bfea-116">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="4bfea-117">Comprendere l'isolamento del tenant</span><span class="sxs-lookup"><span data-stu-id="4bfea-117">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="4bfea-118">Ottenere i dettagli su Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="4bfea-118">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="4bfea-119">Distribuire</span><span class="sxs-lookup"><span data-stu-id="4bfea-119">Deploy</span></span>

<span data-ttu-id="4bfea-120">Per distribuire il tenant, [aggiungere i domini DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) per l'organizzazione e utilizzare le [guide all'installazione nell'interfaccia di amministrazione di Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="4bfea-120">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization and use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="4bfea-121">Tenant con più posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="4bfea-121">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="4bfea-122">Con Microsoft 365 Multi-Geo l'organizzazione può espandere la presenza di Microsoft 365 a più paesi/aree geografiche all'interno del tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="4bfea-122">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="4bfea-123">Per informazioni su Microsoft 365 multi-Geo, inclusa la pianificazione, la configurazione e l'amministrazione, [iniziare da qui](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="4bfea-123">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="4bfea-124">Spostare le posizioni geografiche di un tenant</span><span class="sxs-lookup"><span data-stu-id="4bfea-124">Move a tenant's geographic locations</span></span>

<span data-ttu-id="4bfea-125">Microsoft continua ad aprire nuove aree geografiche di datacenter (GEOS) per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bfea-125">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="4bfea-126">Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti.</span><span class="sxs-lookup"><span data-stu-id="4bfea-126">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="4bfea-127">Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.</span><span class="sxs-lookup"><span data-stu-id="4bfea-127">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="4bfea-128">Per informazioni su Microsoft 365 datacenter Geo, incluso il modo in cui richiedere una mossa di geo data, [iniziare da qui](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="4bfea-128">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="4bfea-129">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4bfea-129">Next step</span></span>

<span data-ttu-id="4bfea-130">Avviare la pianificazione del tenant con [abbonamenti, licenze, account e tenant](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="4bfea-130">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

