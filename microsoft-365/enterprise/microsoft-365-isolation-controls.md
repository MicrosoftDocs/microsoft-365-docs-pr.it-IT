---
title: Controlli di isolamento di Microsoft 365
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
description: Informazioni sul funzionamento dei controlli di isolamento in Microsoft 365, consentendo ai servizi di operare o rimanere autonomi in base alle esigenze.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb0989f19002267ab92bf184a12a4076f753580e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332377"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="b800d-103">Controlli di isolamento di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b800d-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="b800d-104">Microsoft lavora continuamente per garantire che l'architettura multi-tenant di Microsoft 365 supporti gli standard di sicurezza, riservatezza, privacy, integrità, locale, internazionale e disponibilità a [livello aziendale.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)</span><span class="sxs-lookup"><span data-stu-id="b800d-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="b800d-105">La scalabilità e l'ambito dei servizi forniti da Microsoft rendono difficile e non economico gestire Microsoft 365 con un'interazione umana significativa.</span><span class="sxs-lookup"><span data-stu-id="b800d-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="b800d-106">I servizi di Microsoft 365 vengono forniti tramite più data center distribuiti a livello globale, ognuno altamente automatizzato con poche operazioni che richiedono un tocco umano o qualsiasi accesso ai contenuti dei clienti.</span><span class="sxs-lookup"><span data-stu-id="b800d-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="b800d-107">Il nostro personale supporta questi servizi e data center utilizzando strumenti automatizzati e accesso remoto altamente sicuro.</span><span class="sxs-lookup"><span data-stu-id="b800d-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="b800d-108">Microsoft 365 è composto da più servizi che forniscono importanti funzionalità aziendali e contribuiscono all'intera esperienza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b800d-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="b800d-109">Ognuno di questi servizi è autonomo e progettato per l'integrazione tra loro.</span><span class="sxs-lookup"><span data-stu-id="b800d-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="b800d-110">Microsoft 365 è progettato con i principi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b800d-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="b800d-111">**[Architettura orientata ai servizi:](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10))** progettazione e sviluppo di software sotto forma di servizi interoperabili che forniscono funzionalità aziendali ben definite.</span><span class="sxs-lookup"><span data-stu-id="b800d-111">**[Service-Oriented Architecture](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="b800d-112">**[Garanzia](https://www.microsoft.com/download/details.aspx?id=40872)** di sicurezza operativa : un framework che incorpora le conoscenze acquisite tramite varie funzionalità uniche di Microsoft, tra cui Microsoft [Security Development Lifecycle,](https://www.microsoft.com/sdl/default.aspx) [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)e una conoscenza approfondita del panorama delle minacce alla sicurezza informatica.</span><span class="sxs-lookup"><span data-stu-id="b800d-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="b800d-113">I servizi di Microsoft 365 operano tra loro, ma sono progettati e implementati in modo che possano essere distribuiti e gestiti come servizi autonomi, indipendentemente l'uno dall'altro.</span><span class="sxs-lookup"><span data-stu-id="b800d-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="b800d-114">Microsoft separa i compiti e le aree di responsabilità per Microsoft 365 per ridurre le opportunità di modifica non autorizzata o involontaria o uso improprio delle risorse dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b800d-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="b800d-115">I team di Microsoft 365 hanno ruoli definiti come parte di un meccanismo completo di controllo degli accessi basato sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="b800d-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="b800d-116">Isolamento del contenuto del cliente</span><span class="sxs-lookup"><span data-stu-id="b800d-116">Customer content isolation</span></span>

<span data-ttu-id="b800d-117">Tutto il contenuto dei clienti in un tenant è isolato dagli altri tenant e dai dati relativi alle operazioni e ai sistemi utilizzati nella gestione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b800d-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="b800d-118">In Microsoft 365 vengono implementate più forme di protezione per ridurre al minimo il rischio di compromissione di qualsiasi servizio o applicazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b800d-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="b800d-119">Più forme di protezione impediscono anche l'accesso non autorizzato alle informazioni dei tenant o del sistema Microsoft 365 stesso.</span><span class="sxs-lookup"><span data-stu-id="b800d-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="b800d-120">Per informazioni su come Microsoft implementa l'isolamento logico dei dati del tenant in Microsoft 365, vedere [Isolamento del tenant in Microsoft 365.](microsoft-365-tenant-isolation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b800d-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>
