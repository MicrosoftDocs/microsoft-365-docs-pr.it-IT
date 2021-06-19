---
title: Panoramica delle API Microsoft 365 Defender
description: Informazioni sulle API disponibili in Microsoft 365 Defender
keywords: api, api, panoramica, incidente, incidenti, ricerca delle minacce, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1ddb6da49e5e9f23aacf73caaeb91302ac9c19c9
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028968"
---
# <a name="overview-of-microsoft-365-defender-apis"></a><span data-ttu-id="e14f4-104">Panoramica delle API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e14f4-104">Overview of Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e14f4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e14f4-105">**Applies to:**</span></span>

- <span data-ttu-id="e14f4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e14f4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e14f4-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="e14f4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e14f4-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="e14f4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e14f4-109">Microsoft 365 Defender è basato su una piattaforma pronta per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="e14f4-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="e14f4-110">Usa le API Microsoft 365 Defender per automatizzare i flussi di lavoro in base alle tabelle di ricerca avanzate e degli eventi imprevisti condivisi.</span><span class="sxs-lookup"><span data-stu-id="e14f4-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="e14f4-111">**[Coda degli eventi imprevisti combinati:](api-incident.md)** concentrarsi su ciò che è critico raggruppando l'ambito di attacco completo e tutti gli asset influenzati insieme nell'API degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="e14f4-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="e14f4-112">**[Ricerca delle](api-advanced-hunting.md)** minacce tra prodotti - Sfruttare le conoscenze organizzative del team di sicurezza per cercare segni di compromissione, creando query personalizzate per setacciare i dati non elaborati raccolti tra più prodotti di protezione.</span><span class="sxs-lookup"><span data-stu-id="e14f4-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="e14f4-113">Usa [l'API di streaming](../defender-endpoint/raw-data-export.md) per spedire gli eventi e gli avvisi in tempo reale dalle istanze quando si verificano all'interno di un singolo flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="e14f4-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>


<span data-ttu-id="e14f4-114">Insieme a queste API Microsoft 365 Defender specifiche, ognuno dei nostri altri [](api-articles.md) prodotti di sicurezza espone API aggiuntive per aiutarti a sfruttare le loro funzionalità uniche.</span><span class="sxs-lookup"><span data-stu-id="e14f4-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="e14f4-115">La transizione al portale unificato non deve influire sui dashboard di PowerBi basati sulle API di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e14f4-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="e14f4-116">Puoi continuare a usare le API esistenti indipendentemente dalla transizione interattiva del portale.</span><span class="sxs-lookup"><span data-stu-id="e14f4-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="e14f4-117">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e14f4-117">Learn more</span></span>

| <span data-ttu-id="e14f4-118">**Informazioni su come accedere alle API**</span><span class="sxs-lookup"><span data-stu-id="e14f4-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="e14f4-119">Informazioni sulle quote API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="e14f4-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="e14f4-120">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e14f4-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="e14f4-121">**Creare app**</span><span class="sxs-lookup"><span data-stu-id="e14f4-121">**Build apps**</span></span> |
| [<span data-ttu-id="e14f4-122">Creare un'app "Hello world"</span><span class="sxs-lookup"><span data-stu-id="e14f4-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="e14f4-123">Creare un'app per accedere Microsoft 365 Defender API per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="e14f4-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="e14f4-124">Creare un'app per accedere Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="e14f4-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="e14f4-125">Creare un'app con accesso partner multi-tenant Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="e14f4-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="e14f4-126">**Risolvere i problemi e gestire le app**</span><span class="sxs-lookup"><span data-stu-id="e14f4-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="e14f4-127">Informazioni su codici di errore API</span><span class="sxs-lookup"><span data-stu-id="e14f4-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="e14f4-128">Gestire i segreti nelle app con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="e14f4-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="e14f4-129">Implementare l'autorizzazione OAuth 2.0 per l'accesso utente</span><span class="sxs-lookup"><span data-stu-id="e14f4-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |