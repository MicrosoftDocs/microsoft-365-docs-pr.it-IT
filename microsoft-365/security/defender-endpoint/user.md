---
title: Tipo di risorsa User
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 39b73772bcc626590aa784bb5b21357f66229816
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772138"
---
# <a name="user-resource-type"></a><span data-ttu-id="17f60-104">Tipo di risorsa User</span><span class="sxs-lookup"><span data-stu-id="17f60-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="17f60-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="17f60-105">**Applies to:**</span></span>
- [<span data-ttu-id="17f60-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="17f60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="17f60-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17f60-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="17f60-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="17f60-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="17f60-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="17f60-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="17f60-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="17f60-110">Method</span></span>|<span data-ttu-id="17f60-111">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="17f60-111">Return Type</span></span> |<span data-ttu-id="17f60-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17f60-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="17f60-113">Elenco Avvisi correlati agli utenti</span><span class="sxs-lookup"><span data-stu-id="17f60-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="17f60-114">[raccolta avvisi](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="17f60-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="17f60-115">Elencare tutti gli avvisi associati a un [utente](user.md).</span><span class="sxs-lookup"><span data-stu-id="17f60-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="17f60-116">Elenco Dispositivi correlati agli utenti</span><span class="sxs-lookup"><span data-stu-id="17f60-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="17f60-117">[raccolta computer](machine.md)</span><span class="sxs-lookup"><span data-stu-id="17f60-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="17f60-118">Elencare tutti i dispositivi connessi da un [utente.](user.md)</span><span class="sxs-lookup"><span data-stu-id="17f60-118">List all the devices that were logged on by a [user](user.md).</span></span>
