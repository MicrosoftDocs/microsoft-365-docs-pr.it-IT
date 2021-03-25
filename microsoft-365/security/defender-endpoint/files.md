---
title: Tipo di risorsa file
description: Recuperare gli avvisi recenti di Microsoft Defender for Endpoint relativi ai file.
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
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199982"
---
# <a name="file-resource-type"></a><span data-ttu-id="dcc9c-104">Tipo di risorsa file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dcc9c-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dcc9c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="dcc9c-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="dcc9c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dcc9c-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="dcc9c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="dcc9c-108">Rappresenta un'entità file in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="dcc9c-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="dcc9c-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="dcc9c-109">Methods</span></span>
<span data-ttu-id="dcc9c-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="dcc9c-110">Method</span></span>|<span data-ttu-id="dcc9c-111">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="dcc9c-111">Return Type</span></span> |<span data-ttu-id="dcc9c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dcc9c-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="dcc9c-113">Ottenere il file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="dcc9c-114">file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-114">file</span></span>](files.md) | <span data-ttu-id="dcc9c-115">Ottenere un singolo file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-115">Get a single file</span></span> 
[<span data-ttu-id="dcc9c-116">Avvisi correlati ai file di elenco</span><span class="sxs-lookup"><span data-stu-id="dcc9c-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="dcc9c-117">[raccolta avvisi](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="dcc9c-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="dcc9c-118">Ottenere [le entità](alerts.md) di avviso associate al file.</span><span class="sxs-lookup"><span data-stu-id="dcc9c-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="dcc9c-119">Elencare i computer correlati ai file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="dcc9c-120">[raccolta computer](machine.md)</span><span class="sxs-lookup"><span data-stu-id="dcc9c-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="dcc9c-121">Ottenere le [entità](machine.md) computer associate all'avviso.</span><span class="sxs-lookup"><span data-stu-id="dcc9c-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="dcc9c-122">statistiche file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="dcc9c-123">Riepilogo statistiche</span><span class="sxs-lookup"><span data-stu-id="dcc9c-123">Statistics summary</span></span> | <span data-ttu-id="dcc9c-124">Recupera la diffusione per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="dcc9c-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="dcc9c-125">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dcc9c-125">Properties</span></span>
|<span data-ttu-id="dcc9c-126">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dcc9c-126">Property</span></span> | <span data-ttu-id="dcc9c-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="dcc9c-127">Type</span></span>    |   <span data-ttu-id="dcc9c-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dcc9c-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="dcc9c-129">sha1</span><span class="sxs-lookup"><span data-stu-id="dcc9c-129">sha1</span></span> | <span data-ttu-id="dcc9c-130">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-130">String</span></span> | <span data-ttu-id="dcc9c-131">Hash Sha1 del contenuto del file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="dcc9c-132">sha256</span><span class="sxs-lookup"><span data-stu-id="dcc9c-132">sha256</span></span> | <span data-ttu-id="dcc9c-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-133">String</span></span> | <span data-ttu-id="dcc9c-134">Hash Sha256 del contenuto del file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="dcc9c-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="dcc9c-135">globalPrevalence</span></span> | <span data-ttu-id="dcc9c-136">Nullable long</span><span class="sxs-lookup"><span data-stu-id="dcc9c-136">Nullable long</span></span> | <span data-ttu-id="dcc9c-137">Diffusione dei file nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="dcc9c-137">File prevalence across organization</span></span> |
|<span data-ttu-id="dcc9c-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="dcc9c-138">globalFirstObserved</span></span> | <span data-ttu-id="dcc9c-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="dcc9c-139">DateTimeOffset</span></span> | <span data-ttu-id="dcc9c-140">Prima osservazione del file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-140">First time the file was observed</span></span> |
|<span data-ttu-id="dcc9c-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="dcc9c-141">globalLastObserved</span></span> | <span data-ttu-id="dcc9c-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="dcc9c-142">DateTimeOffset</span></span> | <span data-ttu-id="dcc9c-143">Data e ora dell'ultima osservazione del file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-143">Last time the file was observed</span></span> |
|<span data-ttu-id="dcc9c-144">size</span><span class="sxs-lookup"><span data-stu-id="dcc9c-144">size</span></span> | <span data-ttu-id="dcc9c-145">Nullable long</span><span class="sxs-lookup"><span data-stu-id="dcc9c-145">Nullable long</span></span> | <span data-ttu-id="dcc9c-146">Dimensioni del file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-146">Size of the file</span></span> |
|<span data-ttu-id="dcc9c-147">fileType</span><span class="sxs-lookup"><span data-stu-id="dcc9c-147">fileType</span></span> | <span data-ttu-id="dcc9c-148">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-148">String</span></span> | <span data-ttu-id="dcc9c-149">Tipo di file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-149">Type of the file</span></span> |
|<span data-ttu-id="dcc9c-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="dcc9c-150">isPeFile</span></span> | <span data-ttu-id="dcc9c-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="dcc9c-151">Boolean</span></span> | <span data-ttu-id="dcc9c-152">true se il file è eseguibile portabile ,ad esempio "DLL", "EXE" e così via.</span><span class="sxs-lookup"><span data-stu-id="dcc9c-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="dcc9c-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="dcc9c-153">filePublisher</span></span> | <span data-ttu-id="dcc9c-154">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-154">String</span></span> | <span data-ttu-id="dcc9c-155">Autore file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-155">File publisher</span></span> |
|<span data-ttu-id="dcc9c-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="dcc9c-156">fileProductName</span></span> | <span data-ttu-id="dcc9c-157">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-157">String</span></span> | <span data-ttu-id="dcc9c-158">Nome del prodotto</span><span class="sxs-lookup"><span data-stu-id="dcc9c-158">Product name</span></span> |
|<span data-ttu-id="dcc9c-159">firmatario</span><span class="sxs-lookup"><span data-stu-id="dcc9c-159">signer</span></span> | <span data-ttu-id="dcc9c-160">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-160">String</span></span> | <span data-ttu-id="dcc9c-161">Firmatario file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-161">File signer</span></span> |
|<span data-ttu-id="dcc9c-162">autorità emittente</span><span class="sxs-lookup"><span data-stu-id="dcc9c-162">issuer</span></span> | <span data-ttu-id="dcc9c-163">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-163">String</span></span> | <span data-ttu-id="dcc9c-164">Autorità emittente file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-164">File issuer</span></span> |
|<span data-ttu-id="dcc9c-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="dcc9c-165">signerHash</span></span> | <span data-ttu-id="dcc9c-166">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-166">String</span></span> | <span data-ttu-id="dcc9c-167">Hash del certificato di firma</span><span class="sxs-lookup"><span data-stu-id="dcc9c-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="dcc9c-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="dcc9c-168">isValidCertificate</span></span> | <span data-ttu-id="dcc9c-169">Booleano</span><span class="sxs-lookup"><span data-stu-id="dcc9c-169">Boolean</span></span> | <span data-ttu-id="dcc9c-170">La firma del certificato è stata verificata correttamente da Microsoft Defender per l'agente endpoint</span><span class="sxs-lookup"><span data-stu-id="dcc9c-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="dcc9c-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="dcc9c-171">determinationType</span></span> | <span data-ttu-id="dcc9c-172">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-172">String</span></span> | <span data-ttu-id="dcc9c-173">Tipo di determinazione del file</span><span class="sxs-lookup"><span data-stu-id="dcc9c-173">The determination type of the file</span></span> |
|<span data-ttu-id="dcc9c-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="dcc9c-174">determinationValue</span></span> | <span data-ttu-id="dcc9c-175">Stringa</span><span class="sxs-lookup"><span data-stu-id="dcc9c-175">String</span></span> | <span data-ttu-id="dcc9c-176">Valore di determinazione</span><span class="sxs-lookup"><span data-stu-id="dcc9c-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="dcc9c-177">Rappresentazione Json</span><span class="sxs-lookup"><span data-stu-id="dcc9c-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
