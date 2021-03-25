---
title: Tipo di risorsa utente
description: Recuperare gli avvisi recenti di Microsoft Defender for Endpoint relativi agli utenti.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197958"
---
# <a name="user-resource-type"></a><span data-ttu-id="baa1a-104">Tipo di risorsa utente</span><span class="sxs-lookup"><span data-stu-id="baa1a-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="baa1a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="baa1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="baa1a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="baa1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="baa1a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="baa1a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="baa1a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="baa1a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="baa1a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="baa1a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="baa1a-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="baa1a-110">Method</span></span>|<span data-ttu-id="baa1a-111">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="baa1a-111">Return Type</span></span> |<span data-ttu-id="baa1a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="baa1a-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="baa1a-113">Elenco Avvisi correlati agli utenti</span><span class="sxs-lookup"><span data-stu-id="baa1a-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="baa1a-114">[raccolta avvisi](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="baa1a-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="baa1a-115">Elencare tutti gli avvisi associati a un [utente](user.md).</span><span class="sxs-lookup"><span data-stu-id="baa1a-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="baa1a-116">Elenco Dispositivi correlati agli utenti</span><span class="sxs-lookup"><span data-stu-id="baa1a-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="baa1a-117">[raccolta computer](machine.md)</span><span class="sxs-lookup"><span data-stu-id="baa1a-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="baa1a-118">Elencare tutti i dispositivi connessi da un [utente.](user.md)</span><span class="sxs-lookup"><span data-stu-id="baa1a-118">List all the devices that were logged on by a [user](user.md).</span></span>
