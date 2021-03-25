---
title: Proprietà e metodi di punteggio
description: Recupera il punteggio di esposizione dell'organizzazione, il punteggio di sicurezza del dispositivo e il punteggio di esposizione per gruppo di dispositivi
keywords: api, api del grafico, api supportate, punteggio, punteggio di esposizione, punteggio sicuro del dispositivo, punteggio di esposizione per gruppo di dispositivi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200162"
---
# <a name="score-resource-type"></a><span data-ttu-id="468ba-104">Tipo di risorsa punteggio</span><span class="sxs-lookup"><span data-stu-id="468ba-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="468ba-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="468ba-105">**Applies to:**</span></span>
- [<span data-ttu-id="468ba-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="468ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="468ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="468ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="468ba-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="468ba-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="468ba-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="468ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="468ba-110">Metodi</span><span class="sxs-lookup"><span data-stu-id="468ba-110">Methods</span></span>

<span data-ttu-id="468ba-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="468ba-111">Method</span></span> |<span data-ttu-id="468ba-112">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="468ba-112">Return Type</span></span> |<span data-ttu-id="468ba-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="468ba-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="468ba-114">Ottenere il punteggio di esposizione</span><span class="sxs-lookup"><span data-stu-id="468ba-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="468ba-115">Punteggio</span><span class="sxs-lookup"><span data-stu-id="468ba-115">Score</span></span>](score.md) | <span data-ttu-id="468ba-116">Ottenere il punteggio di esposizione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="468ba-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="468ba-117">Ottenere il punteggio sicuro del dispositivo</span><span class="sxs-lookup"><span data-stu-id="468ba-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="468ba-118">Punteggio</span><span class="sxs-lookup"><span data-stu-id="468ba-118">Score</span></span>](score.md) | <span data-ttu-id="468ba-119">Ottenere il punteggio di sicurezza del dispositivo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="468ba-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="468ba-120">Elencare il punteggio di esposizione per gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="468ba-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="468ba-121">Punteggio</span><span class="sxs-lookup"><span data-stu-id="468ba-121">Score</span></span>](score.md) | <span data-ttu-id="468ba-122">Elencare i punteggi per gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="468ba-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="468ba-123">Proprietà</span><span class="sxs-lookup"><span data-stu-id="468ba-123">Properties</span></span>

<span data-ttu-id="468ba-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="468ba-124">Property</span></span> |  <span data-ttu-id="468ba-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="468ba-125">Type</span></span>    |   <span data-ttu-id="468ba-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="468ba-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="468ba-127">Punteggio</span><span class="sxs-lookup"><span data-stu-id="468ba-127">Score</span></span> | <span data-ttu-id="468ba-128">Double</span><span class="sxs-lookup"><span data-stu-id="468ba-128">Double</span></span> | <span data-ttu-id="468ba-129">Punteggio corrente.</span><span class="sxs-lookup"><span data-stu-id="468ba-129">The current score.</span></span>
<span data-ttu-id="468ba-130">Ora</span><span class="sxs-lookup"><span data-stu-id="468ba-130">Time</span></span> | <span data-ttu-id="468ba-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="468ba-131">DateTime</span></span> | <span data-ttu-id="468ba-132">Data e ora in cui è stata effettuata la chiamata per questa API.</span><span class="sxs-lookup"><span data-stu-id="468ba-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="468ba-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="468ba-133">RbacGroupName</span></span> | <span data-ttu-id="468ba-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="468ba-134">String</span></span> | <span data-ttu-id="468ba-135">Nome del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="468ba-135">The device group name.</span></span>
