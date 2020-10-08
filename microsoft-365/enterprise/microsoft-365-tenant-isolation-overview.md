---
title: Isolamento tenant in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Questo articolo contiene un riepilogo del modo in cui Microsoft impone l'isolamento dei tenant nei servizi cloud come Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384933"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="bfd8a-103">Isolamento tenant in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bfd8a-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="bfd8a-104">Uno dei vantaggi principali del cloud computing è il concetto di un'infrastruttura comune condivisa tra i numerosi clienti contemporaneamente, che porta a economie di scala.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="bfd8a-105">Questo concetto è denominato *multi-tenant*.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="bfd8a-106">Microsoft funziona continuamente per garantire che le architetture multi-tenant dei servizi cloud supportino la sicurezza a livello aziendale, la riservatezza, la privacy, l'integrità e gli standard di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="bfd8a-107">In base ai significativi investimenti e all'esperienza ottenuti dall' [elaborazione affidabile](https://www.microsoft.com/trust-center) e dal ciclo di vita [dello sviluppo della sicurezza](https://www.microsoft.com/securityengineering/sdl/), i servizi cloud Microsoft sono stati concepiti con l'ipotesi che tutti i tenant siano potenzialmente ostili a tutti gli altri tenant e che siano state implementate misure di sicurezza per impedire che le azioni di un tenant influiscano sulla sicurezza o sul servizio di un altro tenant o sull'accesso al</span><span class="sxs-lookup"><span data-stu-id="bfd8a-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="bfd8a-108">I due obiettivi principali per mantenere l'isolamento del tenant in un ambiente multi-tenant sono:</span><span class="sxs-lookup"><span data-stu-id="bfd8a-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="bfd8a-109">Impedire la fuoriuscita o l'accesso non autorizzato al contenuto dei clienti tra i tenant; e</span><span class="sxs-lookup"><span data-stu-id="bfd8a-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="bfd8a-110">Impedire alle azioni di un tenant di influenzare negativamente il servizio per un altro tenant</span><span class="sxs-lookup"><span data-stu-id="bfd8a-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="bfd8a-111">Sono state implementate più forme di protezione in Microsoft 365 per impedire ai clienti di compromettere i servizi o le applicazioni di Microsoft 365 o di ottenere un accesso non autorizzato alle informazioni di altri tenant o del sistema Microsoft 365 stesso, tra cui:</span><span class="sxs-lookup"><span data-stu-id="bfd8a-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="bfd8a-112">L'isolamento logico del contenuto dei clienti all'interno di ogni tenant per i servizi Microsoft 365 viene ottenuto tramite l'autorizzazione di Azure Active Directory e il controllo di accesso basato sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="bfd8a-113">SharePoint Online fornisce meccanismi di isolamento dei dati a livello di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="bfd8a-114">Microsoft utilizza la sicurezza fisica rigorosa, lo screening di sfondo e una strategia di crittografia a più livelli per proteggere la riservatezza e l'integrità del contenuto dei clienti.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="bfd8a-115">Tutti i datacenter Microsoft 365 dispongono di controlli di accesso biometrici, con la maggior parte delle stampe Palm che richiedono l'accesso fisico.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="bfd8a-116">Inoltre, tutti i dipendenti Microsoft basati su Stati Uniti sono necessari per completare correttamente un controllo di sfondo standard come parte del processo di assunzione.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="bfd8a-117">Per ulteriori informazioni sui controlli utilizzati per l'accesso amministrativo in Microsoft 365, vedere [controlli di accesso amministrativo di microsoft 365](microsoft-365-administrative-access-controls-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bfd8a-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="bfd8a-118">Microsoft 365 utilizza tecnologie sul fianco del servizio che crittografano il contenuto dei clienti a riposo e in transito, tra cui BitLocker, crittografia per file, TLS (Transport Layer Security) e IPsec (Internet Protocol Security).</span><span class="sxs-lookup"><span data-stu-id="bfd8a-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="bfd8a-119">Per informazioni specifiche sulla crittografia in Microsoft 365, vedere [Data Encryption Technologies in microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bfd8a-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="bfd8a-120">Insieme, le protezioni elencate di seguito offrono robusti controlli di isolamento logico che forniscono protezione dalle minacce e una mitigazione equivalente a quella fornita solo dall'isolamento fisico.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="bfd8a-121">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="bfd8a-121">Related Links</span></span>

- [<span data-ttu-id="bfd8a-122">Isolamento e controllo di accesso in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bfd8a-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="bfd8a-123">Isolamento del tenant in Office Graph e Delve</span><span class="sxs-lookup"><span data-stu-id="bfd8a-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="bfd8a-124">Isolamento del tenant per la funzionalità di ricerca di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bfd8a-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="bfd8a-125">Isolamento del tenant in Office 365 Video</span><span class="sxs-lookup"><span data-stu-id="bfd8a-125">Tenant Isolation in Office 365 Video</span></span>](microsoft-365-isolation-in-microsoft-365-video.md)
- [<span data-ttu-id="bfd8a-126">Limiti della risorsa</span><span class="sxs-lookup"><span data-stu-id="bfd8a-126">Resource Limits</span></span>](microsoft-365-resource-limits.md)
- [<span data-ttu-id="bfd8a-127">Monitoraggio e verifica dei limiti del tenant</span><span class="sxs-lookup"><span data-stu-id="bfd8a-127">Monitoring and Testing Tenant Boundaries</span></span>](microsoft-365-monitoring-and-testing.md)
- [<span data-ttu-id="bfd8a-128">Isolamento e controllo di accesso in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bfd8a-128">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)
