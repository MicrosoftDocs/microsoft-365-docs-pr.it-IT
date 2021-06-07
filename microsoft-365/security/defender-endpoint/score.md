---
title: Metodi e proprietà di punteggio
description: Recupera il punteggio di esposizione dell'organizzazione, il punteggio di sicurezza del dispositivo e il punteggio di esposizione per gruppo di dispositivi
keywords: api, api del grafico, api supportate, punteggio, punteggio di esposizione, punteggio sicuro del dispositivo, punteggio di esposizione per gruppo di dispositivi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771430"
---
# <a name="score-resource-type"></a><span data-ttu-id="a08fb-104">Tipo di risorsa punteggio</span><span class="sxs-lookup"><span data-stu-id="a08fb-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a08fb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a08fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="a08fb-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a08fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a08fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a08fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a08fb-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a08fb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a08fb-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a08fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="a08fb-110">Metodi</span><span class="sxs-lookup"><span data-stu-id="a08fb-110">Methods</span></span>

<span data-ttu-id="a08fb-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="a08fb-111">Method</span></span> |<span data-ttu-id="a08fb-112">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="a08fb-112">Return Type</span></span> |<span data-ttu-id="a08fb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a08fb-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="a08fb-114">Ottenere punteggio di esposizione</span><span class="sxs-lookup"><span data-stu-id="a08fb-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="a08fb-115">Punteggio</span><span class="sxs-lookup"><span data-stu-id="a08fb-115">Score</span></span>](score.md) | <span data-ttu-id="a08fb-116">Ottenere il punteggio di esposizione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a08fb-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="a08fb-117">Ottenere punteggio di sicurezza dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="a08fb-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="a08fb-118">Punteggio</span><span class="sxs-lookup"><span data-stu-id="a08fb-118">Score</span></span>](score.md) | <span data-ttu-id="a08fb-119">Ottenere il punteggio di sicurezza del dispositivo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a08fb-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="a08fb-120">Elencare il punteggio di esposizione per gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="a08fb-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="a08fb-121">Punteggio</span><span class="sxs-lookup"><span data-stu-id="a08fb-121">Score</span></span>](score.md) | <span data-ttu-id="a08fb-122">Elencare i punteggi per gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a08fb-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="a08fb-123">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a08fb-123">Properties</span></span>

<span data-ttu-id="a08fb-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a08fb-124">Property</span></span> |  <span data-ttu-id="a08fb-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="a08fb-125">Type</span></span>    |   <span data-ttu-id="a08fb-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a08fb-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="a08fb-127">Punteggio</span><span class="sxs-lookup"><span data-stu-id="a08fb-127">Score</span></span> | <span data-ttu-id="a08fb-128">Double</span><span class="sxs-lookup"><span data-stu-id="a08fb-128">Double</span></span> | <span data-ttu-id="a08fb-129">Punteggio corrente.</span><span class="sxs-lookup"><span data-stu-id="a08fb-129">The current score.</span></span>
<span data-ttu-id="a08fb-130">Ora</span><span class="sxs-lookup"><span data-stu-id="a08fb-130">Time</span></span> | <span data-ttu-id="a08fb-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="a08fb-131">DateTime</span></span> | <span data-ttu-id="a08fb-132">Data e ora in cui è stata effettuata la chiamata per questa API.</span><span class="sxs-lookup"><span data-stu-id="a08fb-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="a08fb-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="a08fb-133">RbacGroupName</span></span> | <span data-ttu-id="a08fb-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="a08fb-134">String</span></span> | <span data-ttu-id="a08fb-135">Nome del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a08fb-135">The device group name.</span></span>
