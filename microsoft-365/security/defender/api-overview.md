---
title: Panoramica delle API di Microsoft 365 Defender
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
ms.openlocfilehash: 14553f3891fd81a672b62fa0575f6c253fbb0224
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060810"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="5272b-104">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5272b-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5272b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5272b-105">**Applies to:**</span></span>

- <span data-ttu-id="5272b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5272b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5272b-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="5272b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5272b-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="5272b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5272b-109">Microsoft 365 Defender si basa su una piattaforma pronta per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="5272b-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="5272b-110">Usa le API di Microsoft 365 Defender per automatizzare i flussi di lavoro in base all'evento imprevisto condiviso e alle tabelle di ricerca avanzate.</span><span class="sxs-lookup"><span data-stu-id="5272b-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="5272b-111">**[Coda degli eventi imprevisti combinati:](api-incident.md)** concentrarsi su ciò che è critico raggruppando l'ambito di attacco completo e tutti gli asset influenzati insieme nell'API degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="5272b-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="5272b-112">**[Ricerca delle](api-advanced-hunting.md)** minacce tra prodotti - Sfruttare le conoscenze organizzative del team di sicurezza per cercare segni di compromissione, creando query personalizzate per setacciare i dati non elaborati raccolti tra più prodotti di protezione.</span><span class="sxs-lookup"><span data-stu-id="5272b-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="5272b-113">Insieme a queste API specifiche di Microsoft 365 Defender, [](api-articles.md) ognuno dei nostri altri prodotti di sicurezza espone API aggiuntive per aiutarti a sfruttare le loro funzionalità uniche.</span><span class="sxs-lookup"><span data-stu-id="5272b-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="5272b-114">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="5272b-114">Learn more</span></span>

| <span data-ttu-id="5272b-115">**Informazioni su come accedere alle API**</span><span class="sxs-lookup"><span data-stu-id="5272b-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="5272b-116">Informazioni sulle quote API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="5272b-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="5272b-117">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5272b-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="5272b-118">**Creare app**</span><span class="sxs-lookup"><span data-stu-id="5272b-118">**Build apps**</span></span> |
| [<span data-ttu-id="5272b-119">Creare un'app "Hello world"</span><span class="sxs-lookup"><span data-stu-id="5272b-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="5272b-120">Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="5272b-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="5272b-121">Creare un'app per accedere a Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="5272b-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="5272b-122">Creare un'app con accesso partner multi-tenant alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5272b-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="5272b-123">**Risolvere i problemi e gestire le app**</span><span class="sxs-lookup"><span data-stu-id="5272b-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="5272b-124">Informazioni su codici di errore API</span><span class="sxs-lookup"><span data-stu-id="5272b-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="5272b-125">Gestire i segreti nelle app con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="5272b-125">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="5272b-126">Implementare l'autorizzazione OAuth 2.0 per l'accesso utente</span><span class="sxs-lookup"><span data-stu-id="5272b-126">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |