---
title: Informazioni generali su Microsoft 365 Defender APIs
description: Informazioni sulle API disponibili in Microsoft 365 Defender
keywords: API, API, panoramica, incidenti, incidenti, minacce di caccia, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719191"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="b298f-104">Informazioni generali su Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="b298f-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b298f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b298f-105">**Applies to:**</span></span>

- <span data-ttu-id="b298f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b298f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b298f-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="b298f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b298f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b298f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b298f-109">Microsoft 365 Defender è basato su una piattaforma di integrazione pronta.</span><span class="sxs-lookup"><span data-stu-id="b298f-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="b298f-110">Utilizzare le API di Microsoft 365 Defender per automatizzare i flussi di lavoro in base alle tabelle degli incidenti condivisi e di ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="b298f-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="b298f-111">**[Coda degli incidenti combinati](api-incident.md)** -concentrarsi su ciò che è critico raggruppando l'ambito di attacco completo e tutte le risorse interessate insieme nell'API Incident.</span><span class="sxs-lookup"><span data-stu-id="b298f-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="b298f-112">**[Caccia ai rischi tra prodotti](api-advanced-hunting.md)** -sfruttare le conoscenze organizzative del team di sicurezza per la ricerca di segnali di compromesso, creando query personalizzate per setacciare i dati non elaborati raccolti su più prodotti di protezione.</span><span class="sxs-lookup"><span data-stu-id="b298f-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="b298f-113">Insieme a queste API Microsoft 365 Defender specifiche, ognuno degli altri prodotti di sicurezza espone altre [API](api-articles.md) che consentono di sfruttare le loro funzionalità esclusive.</span><span class="sxs-lookup"><span data-stu-id="b298f-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="b298f-114">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b298f-114">Learn more</span></span>

| <span data-ttu-id="b298f-115">**Informazioni su come accedere alle API**</span><span class="sxs-lookup"><span data-stu-id="b298f-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="b298f-116">Informazioni sulle quote e sulle licenze per l'API</span><span class="sxs-lookup"><span data-stu-id="b298f-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="b298f-117">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b298f-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="b298f-118">**Creare app**</span><span class="sxs-lookup"><span data-stu-id="b298f-118">**Build apps**</span></span> |
| [<span data-ttu-id="b298f-119">Creare un'app ' Hello World '</span><span class="sxs-lookup"><span data-stu-id="b298f-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="b298f-120">Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="b298f-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="b298f-121">Creare un'app per accedere a Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="b298f-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="b298f-122">Creare un'app con accesso partner multi-tenant a Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="b298f-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="b298f-123">**Risoluzione dei problemi e gestione delle app**</span><span class="sxs-lookup"><span data-stu-id="b298f-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="b298f-124">Informazioni sui codici di errore dell'API</span><span class="sxs-lookup"><span data-stu-id="b298f-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="b298f-125">Gestione dei segreti nelle app con il Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="b298f-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="b298f-126">Implementazione dell'autorizzazione OAuth 2,0 per l'accesso dell'utente</span><span class="sxs-lookup"><span data-stu-id="b298f-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
