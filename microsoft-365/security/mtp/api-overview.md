---
title: Informazioni generali su Microsoft 365 Defender APIs
description: Informazioni sulle API disponibili in Microsoft 365 Defender
keywords: API, API, panoramica, incidenti, incidenti, caccia alle minacce
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
ms.openlocfilehash: 75a5853e7128667420819c84fbc3c50b07d669b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845012"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="e9c33-104">Informazioni generali su Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="e9c33-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e9c33-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e9c33-105">**Applies to:**</span></span>
- <span data-ttu-id="e9c33-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9c33-106">Microsoft 365 Defender</span></span>


>[!IMPORTANT] 
><span data-ttu-id="e9c33-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="e9c33-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e9c33-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e9c33-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e9c33-109">La soluzione Microsoft 365 Defender è basata su una piattaforma di integrazione pronta.</span><span class="sxs-lookup"><span data-stu-id="e9c33-109">Microsoft 365 Defender solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="e9c33-110">Le API di Microsoft 365 Defender di Lop Level consentiranno di automatizzare i flussi di lavoro in base alle tabelle degli incidenti condivisi e di ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="e9c33-110">The lop-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="e9c33-111">**Coda di incidenti combinati** : consente ai professionisti della sicurezza di concentrarsi su ciò che è critico.</span><span class="sxs-lookup"><span data-stu-id="e9c33-111">**Combined incidents queue** - Helps security professionals focus on what's critical.</span></span> <span data-ttu-id="e9c33-112">Consente di verificare che l'ambito di attacco completo e le risorse interessate siano raggruppati e riemersi in modo tempestivo nell'ambito dell'API Incident.</span><span class="sxs-lookup"><span data-stu-id="e9c33-112">Helps to ensure that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="e9c33-113">**Cross-product Threat Hunting** -i team di sicurezza possono sfruttare le proprie conoscenze organizzative esclusive per cercare segni di compromesso creando query personalizzate tramite API sui dati non elaborati raccolti dai vari prodotti di protezione.</span><span class="sxs-lookup"><span data-stu-id="e9c33-113">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="e9c33-114">Oltre a questi set di API, ognuno dei diversi prodotti di protezione espone altre API che consentono di innovare in base alle funzionalità di ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="e9c33-114">In addition to these set of APIs, each of the various protection products expose additional APIs to help you innovate based on each product capability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e9c33-115">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e9c33-115">Related topics</span></span>
- [<span data-ttu-id="e9c33-116">Accedere alle API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e9c33-116">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="e9c33-117">Altre risorse API</span><span class="sxs-lookup"><span data-stu-id="e9c33-117">Other API resources</span></span>](api-articles.md)
