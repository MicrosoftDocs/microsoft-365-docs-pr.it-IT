---
title: Microsoft 365 migrazioni da tenant a tenant
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Informazioni su come eseguire la migrazione Microsoft 365 tenant.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819715"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="0755e-103">Microsoft 365 migrazioni da tenant a tenant</span><span class="sxs-lookup"><span data-stu-id="0755e-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="0755e-104">Esistono diversi approcci di architettura per fusioni, acquisizioni, cessioni e altri scenari che potrebbero portare a eseguire la migrazione di un tenant Microsoft 365 esistente a un nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="0755e-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="0755e-105">La maggior parte dei clienti collabora con Microsoft Consulting Services o con un partner Microsoft per eseguire la migrazione dei tenant, incluso l'utilizzo di strumenti di terze parti per eseguire la migrazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0755e-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="0755e-106">Usare il [modello di architettura](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) di migrazione da tenant a tenant per comprendere come pianificare le migrazioni da tenant Microsoft 365 tenant a tenant e i passaggi di una migrazione.</span><span class="sxs-lookup"><span data-stu-id="0755e-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="0755e-107">[![Modello di migrazione da tenant a tenant](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="0755e-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="0755e-108">È possibile scaricare questo modello in [formato PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) e stamparlo su carta formato lettera, legale o tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="0755e-108">You download this model in [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="0755e-109">Questo modello fornisce indicazioni e un punto di partenza per la pianificazione con sezioni su:</span><span class="sxs-lookup"><span data-stu-id="0755e-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="0755e-110">Mapping degli scenari aziendali con gli approcci dell'architettura</span><span class="sxs-lookup"><span data-stu-id="0755e-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="0755e-111">Considerazioni sulla progettazione</span><span class="sxs-lookup"><span data-stu-id="0755e-111">Design considerations</span></span>

<span data-ttu-id="0755e-112">Questo modello contiene anche esempi dettagliati di:</span><span class="sxs-lookup"><span data-stu-id="0755e-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="0755e-113">Flusso di migrazione di un singolo evento</span><span class="sxs-lookup"><span data-stu-id="0755e-113">A single event migration flow</span></span>
- <span data-ttu-id="0755e-114">Flusso di migrazione in fasi</span><span class="sxs-lookup"><span data-stu-id="0755e-114">A phased migration flow</span></span>
- <span data-ttu-id="0755e-115">Spostamento tenant o flusso diviso</span><span class="sxs-lookup"><span data-stu-id="0755e-115">A tenant move or split flow</span></span>
