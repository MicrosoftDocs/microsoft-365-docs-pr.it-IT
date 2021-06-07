---
title: Metodi e proprietà di software
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771406"
---
# <a name="software-resource-type"></a><span data-ttu-id="1bb92-104">Tipo di risorsa software</span><span class="sxs-lookup"><span data-stu-id="1bb92-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1bb92-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1bb92-105">**Applies to:**</span></span>
- [<span data-ttu-id="1bb92-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1bb92-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1bb92-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bb92-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1bb92-108">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1bb92-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1bb92-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1bb92-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1bb92-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1bb92-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="1bb92-111">Metodi</span><span class="sxs-lookup"><span data-stu-id="1bb92-111">Methods</span></span>

<span data-ttu-id="1bb92-112">Metodo</span><span class="sxs-lookup"><span data-stu-id="1bb92-112">Method</span></span> |<span data-ttu-id="1bb92-113">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="1bb92-113">Return Type</span></span> |<span data-ttu-id="1bb92-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bb92-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="1bb92-115">Elencare il software</span><span class="sxs-lookup"><span data-stu-id="1bb92-115">List software</span></span>](get-software.md) | <span data-ttu-id="1bb92-116">Raccolta software</span><span class="sxs-lookup"><span data-stu-id="1bb92-116">Software collection</span></span> | <span data-ttu-id="1bb92-117">Elencare l'inventario software dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1bb92-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="1bb92-118">Ottenere il software per Id</span><span class="sxs-lookup"><span data-stu-id="1bb92-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="1bb92-119">Software</span><span class="sxs-lookup"><span data-stu-id="1bb92-119">Software</span></span> | <span data-ttu-id="1bb92-120">Ottenere un software specifico in base al relativo ID software.</span><span class="sxs-lookup"><span data-stu-id="1bb92-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="1bb92-121">Elencare distribuzione versione software</span><span class="sxs-lookup"><span data-stu-id="1bb92-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="1bb92-122">Raccolta di distribuzione</span><span class="sxs-lookup"><span data-stu-id="1bb92-122">Distribution collection</span></span> | <span data-ttu-id="1bb92-123">Elencare la distribuzione delle versioni software in base all'ID software.</span><span class="sxs-lookup"><span data-stu-id="1bb92-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="1bb92-124">Elencare i computer per software</span><span class="sxs-lookup"><span data-stu-id="1bb92-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="1bb92-125">Insieme MachineRef</span><span class="sxs-lookup"><span data-stu-id="1bb92-125">MachineRef collection</span></span> | <span data-ttu-id="1bb92-126">Recupera un elenco di dispositivi associati all'ID software.</span><span class="sxs-lookup"><span data-stu-id="1bb92-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="1bb92-127">Elencare le vulnerabilità per software</span><span class="sxs-lookup"><span data-stu-id="1bb92-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="1bb92-128">[Raccolta di vulnerabilità](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="1bb92-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="1bb92-129">Recuperare un elenco di vulnerabilità associate all'ID software.</span><span class="sxs-lookup"><span data-stu-id="1bb92-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="1bb92-130">Recuperare i KB mancanti</span><span class="sxs-lookup"><span data-stu-id="1bb92-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="1bb92-131">Raccolta KB</span><span class="sxs-lookup"><span data-stu-id="1bb92-131">KB collection</span></span> | <span data-ttu-id="1bb92-132">Ottenere un elenco di indicatori KPI mancanti associati all'ID software</span><span class="sxs-lookup"><span data-stu-id="1bb92-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="1bb92-133">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1bb92-133">Properties</span></span>

<span data-ttu-id="1bb92-134">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1bb92-134">Property</span></span> |   <span data-ttu-id="1bb92-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="1bb92-135">Type</span></span>   |   <span data-ttu-id="1bb92-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bb92-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="1bb92-137">id</span><span class="sxs-lookup"><span data-stu-id="1bb92-137">id</span></span> | <span data-ttu-id="1bb92-138">Stringa</span><span class="sxs-lookup"><span data-stu-id="1bb92-138">String</span></span> | <span data-ttu-id="1bb92-139">Software ID</span><span class="sxs-lookup"><span data-stu-id="1bb92-139">Software ID</span></span>
<span data-ttu-id="1bb92-140">Nome</span><span class="sxs-lookup"><span data-stu-id="1bb92-140">Name</span></span> | <span data-ttu-id="1bb92-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="1bb92-141">String</span></span> | <span data-ttu-id="1bb92-142">Nome software</span><span class="sxs-lookup"><span data-stu-id="1bb92-142">Software name</span></span>
<span data-ttu-id="1bb92-143">Fornitore</span><span class="sxs-lookup"><span data-stu-id="1bb92-143">Vendor</span></span> | <span data-ttu-id="1bb92-144">Stringa</span><span class="sxs-lookup"><span data-stu-id="1bb92-144">String</span></span> | <span data-ttu-id="1bb92-145">Nome fornitore software</span><span class="sxs-lookup"><span data-stu-id="1bb92-145">Software vendor name</span></span>
<span data-ttu-id="1bb92-146">Punti deboli</span><span class="sxs-lookup"><span data-stu-id="1bb92-146">Weaknesses</span></span> | <span data-ttu-id="1bb92-147">Long</span><span class="sxs-lookup"><span data-stu-id="1bb92-147">Long</span></span> | <span data-ttu-id="1bb92-148">Numero di vulnerabilità individuate</span><span class="sxs-lookup"><span data-stu-id="1bb92-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="1bb92-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="1bb92-149">publicExploit</span></span> | <span data-ttu-id="1bb92-150">Booleano</span><span class="sxs-lookup"><span data-stu-id="1bb92-150">Boolean</span></span> | <span data-ttu-id="1bb92-151">Esiste un exploit pubblico per alcune delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="1bb92-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="1bb92-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="1bb92-152">activeAlert</span></span> | <span data-ttu-id="1bb92-153">Booleano</span><span class="sxs-lookup"><span data-stu-id="1bb92-153">Boolean</span></span> | <span data-ttu-id="1bb92-154">L'avviso attivo è associato a questo software</span><span class="sxs-lookup"><span data-stu-id="1bb92-154">Active alert is associated with this software</span></span>
<span data-ttu-id="1bb92-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="1bb92-155">exposedMachines</span></span> | <span data-ttu-id="1bb92-156">Long</span><span class="sxs-lookup"><span data-stu-id="1bb92-156">Long</span></span> | <span data-ttu-id="1bb92-157">Numero di dispositivi esposti</span><span class="sxs-lookup"><span data-stu-id="1bb92-157">Number of exposed devices</span></span>
<span data-ttu-id="1bb92-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="1bb92-158">impactScore</span></span> | <span data-ttu-id="1bb92-159">Double</span><span class="sxs-lookup"><span data-stu-id="1bb92-159">Double</span></span> | <span data-ttu-id="1bb92-160">Impatto del punteggio di esposizione di questo software</span><span class="sxs-lookup"><span data-stu-id="1bb92-160">Exposure score impact of this software</span></span>
