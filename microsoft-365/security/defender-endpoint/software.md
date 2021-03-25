---
title: Proprietà e metodi software
description: Recupera gli avvisi recenti principali.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187200"
---
# <a name="software-resource-type"></a><span data-ttu-id="61dfa-104">Tipo di risorsa software</span><span class="sxs-lookup"><span data-stu-id="61dfa-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61dfa-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="61dfa-105">**Applies to:**</span></span>
- [<span data-ttu-id="61dfa-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="61dfa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="61dfa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61dfa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="61dfa-108">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="61dfa-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="61dfa-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="61dfa-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="61dfa-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="61dfa-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="61dfa-111">Metodi</span><span class="sxs-lookup"><span data-stu-id="61dfa-111">Methods</span></span>

<span data-ttu-id="61dfa-112">Metodo</span><span class="sxs-lookup"><span data-stu-id="61dfa-112">Method</span></span> |<span data-ttu-id="61dfa-113">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="61dfa-113">Return Type</span></span> |<span data-ttu-id="61dfa-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61dfa-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="61dfa-115">Software elenco</span><span class="sxs-lookup"><span data-stu-id="61dfa-115">List software</span></span>](get-software.md) | <span data-ttu-id="61dfa-116">Raccolta software</span><span class="sxs-lookup"><span data-stu-id="61dfa-116">Software collection</span></span> | <span data-ttu-id="61dfa-117">Elencare l'inventario software dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="61dfa-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="61dfa-118">Ottenere il software in base all'ID</span><span class="sxs-lookup"><span data-stu-id="61dfa-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="61dfa-119">Software</span><span class="sxs-lookup"><span data-stu-id="61dfa-119">Software</span></span> | <span data-ttu-id="61dfa-120">Ottenere un software specifico in base al relativo ID software.</span><span class="sxs-lookup"><span data-stu-id="61dfa-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="61dfa-121">List software version distribution</span><span class="sxs-lookup"><span data-stu-id="61dfa-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="61dfa-122">Raccolta di distribuzione</span><span class="sxs-lookup"><span data-stu-id="61dfa-122">Distribution collection</span></span> | <span data-ttu-id="61dfa-123">Elencare la distribuzione delle versioni software in base all'ID software.</span><span class="sxs-lookup"><span data-stu-id="61dfa-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="61dfa-124">Elencare i computer in base al software</span><span class="sxs-lookup"><span data-stu-id="61dfa-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="61dfa-125">Insieme MachineRef</span><span class="sxs-lookup"><span data-stu-id="61dfa-125">MachineRef collection</span></span> | <span data-ttu-id="61dfa-126">Recupera un elenco di dispositivi associati all'ID software.</span><span class="sxs-lookup"><span data-stu-id="61dfa-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="61dfa-127">Elencare le vulnerabilità in base al software</span><span class="sxs-lookup"><span data-stu-id="61dfa-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="61dfa-128">[Raccolta di vulnerabilità](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="61dfa-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="61dfa-129">Recuperare un elenco di vulnerabilità associate all'ID software.</span><span class="sxs-lookup"><span data-stu-id="61dfa-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="61dfa-130">Ottenere gli indicatori KPI mancanti</span><span class="sxs-lookup"><span data-stu-id="61dfa-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="61dfa-131">Raccolta KB</span><span class="sxs-lookup"><span data-stu-id="61dfa-131">KB collection</span></span> | <span data-ttu-id="61dfa-132">Ottenere un elenco di indicatori KPI mancanti associati all'ID software</span><span class="sxs-lookup"><span data-stu-id="61dfa-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="61dfa-133">Proprietà</span><span class="sxs-lookup"><span data-stu-id="61dfa-133">Properties</span></span>

<span data-ttu-id="61dfa-134">Proprietà</span><span class="sxs-lookup"><span data-stu-id="61dfa-134">Property</span></span> |   <span data-ttu-id="61dfa-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="61dfa-135">Type</span></span>   |   <span data-ttu-id="61dfa-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61dfa-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="61dfa-137">id</span><span class="sxs-lookup"><span data-stu-id="61dfa-137">id</span></span> | <span data-ttu-id="61dfa-138">Stringa</span><span class="sxs-lookup"><span data-stu-id="61dfa-138">String</span></span> | <span data-ttu-id="61dfa-139">Software ID</span><span class="sxs-lookup"><span data-stu-id="61dfa-139">Software ID</span></span>
<span data-ttu-id="61dfa-140">Nome</span><span class="sxs-lookup"><span data-stu-id="61dfa-140">Name</span></span> | <span data-ttu-id="61dfa-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="61dfa-141">String</span></span> | <span data-ttu-id="61dfa-142">Nome software</span><span class="sxs-lookup"><span data-stu-id="61dfa-142">Software name</span></span>
<span data-ttu-id="61dfa-143">Fornitore</span><span class="sxs-lookup"><span data-stu-id="61dfa-143">Vendor</span></span> | <span data-ttu-id="61dfa-144">Stringa</span><span class="sxs-lookup"><span data-stu-id="61dfa-144">String</span></span> | <span data-ttu-id="61dfa-145">Nome fornitore software</span><span class="sxs-lookup"><span data-stu-id="61dfa-145">Software vendor name</span></span>
<span data-ttu-id="61dfa-146">Punti deboli</span><span class="sxs-lookup"><span data-stu-id="61dfa-146">Weaknesses</span></span> | <span data-ttu-id="61dfa-147">Long</span><span class="sxs-lookup"><span data-stu-id="61dfa-147">Long</span></span> | <span data-ttu-id="61dfa-148">Numero di vulnerabilità individuate</span><span class="sxs-lookup"><span data-stu-id="61dfa-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="61dfa-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="61dfa-149">publicExploit</span></span> | <span data-ttu-id="61dfa-150">Booleano</span><span class="sxs-lookup"><span data-stu-id="61dfa-150">Boolean</span></span> | <span data-ttu-id="61dfa-151">Esiste un exploit pubblico per alcune delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="61dfa-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="61dfa-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="61dfa-152">activeAlert</span></span> | <span data-ttu-id="61dfa-153">Booleano</span><span class="sxs-lookup"><span data-stu-id="61dfa-153">Boolean</span></span> | <span data-ttu-id="61dfa-154">L'avviso attivo è associato a questo software</span><span class="sxs-lookup"><span data-stu-id="61dfa-154">Active alert is associated with this software</span></span>
<span data-ttu-id="61dfa-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="61dfa-155">exposedMachines</span></span> | <span data-ttu-id="61dfa-156">Long</span><span class="sxs-lookup"><span data-stu-id="61dfa-156">Long</span></span> | <span data-ttu-id="61dfa-157">Numero di dispositivi esposti</span><span class="sxs-lookup"><span data-stu-id="61dfa-157">Number of exposed devices</span></span>
<span data-ttu-id="61dfa-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="61dfa-158">impactScore</span></span> | <span data-ttu-id="61dfa-159">Double</span><span class="sxs-lookup"><span data-stu-id="61dfa-159">Double</span></span> | <span data-ttu-id="61dfa-160">Impatto del punteggio di esposizione di questo software</span><span class="sxs-lookup"><span data-stu-id="61dfa-160">Exposure score impact of this software</span></span>
