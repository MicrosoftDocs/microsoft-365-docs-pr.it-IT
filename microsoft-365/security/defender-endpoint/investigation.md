---
title: Tipo di risorsa di indagine
description: Entità Microsoft Defender ATP Investigation.
keywords: api, api del grafico, api supportate, ottenere, avvisi, indagini
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 36adf0fa5c0de79fe0616f1216118a98ba2005a4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187248"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="98908-104">Tipo di risorsa di indagine</span><span class="sxs-lookup"><span data-stu-id="98908-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98908-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="98908-105">**Applies to:**</span></span>
- [<span data-ttu-id="98908-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="98908-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98908-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98908-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="98908-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="98908-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98908-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="98908-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="98908-110">Rappresenta un'entità di indagine automatizzata in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="98908-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="98908-111">Per [ulteriori informazioni, vedere](automated-investigations.md) Panoramica delle indagini automatizzate.</span><span class="sxs-lookup"><span data-stu-id="98908-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="98908-112">Metodi</span><span class="sxs-lookup"><span data-stu-id="98908-112">Methods</span></span>
<span data-ttu-id="98908-113">Metodo</span><span class="sxs-lookup"><span data-stu-id="98908-113">Method</span></span>|<span data-ttu-id="98908-114">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="98908-114">Return Type</span></span> |<span data-ttu-id="98908-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98908-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="98908-116">Indagini elenco</span><span class="sxs-lookup"><span data-stu-id="98908-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="98908-117">Raccolta di indagini</span><span class="sxs-lookup"><span data-stu-id="98908-117">Investigation collection</span></span> | <span data-ttu-id="98908-118">Ottenere la raccolta di indagini</span><span class="sxs-lookup"><span data-stu-id="98908-118">Get collection of Investigation</span></span>
[<span data-ttu-id="98908-119">Ottenere un'indagine singola</span><span class="sxs-lookup"><span data-stu-id="98908-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="98908-120">Entità di indagine</span><span class="sxs-lookup"><span data-stu-id="98908-120">Investigation entity</span></span> | <span data-ttu-id="98908-121">Ottiene una singola entità Investigation.</span><span class="sxs-lookup"><span data-stu-id="98908-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="98908-122">Avviare l'indagine</span><span class="sxs-lookup"><span data-stu-id="98908-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="98908-123">Entità di indagine</span><span class="sxs-lookup"><span data-stu-id="98908-123">Investigation entity</span></span> | <span data-ttu-id="98908-124">Avvia l'analisi in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98908-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="98908-125">Proprietà</span><span class="sxs-lookup"><span data-stu-id="98908-125">Properties</span></span>
<span data-ttu-id="98908-126">Proprietà</span><span class="sxs-lookup"><span data-stu-id="98908-126">Property</span></span> |  <span data-ttu-id="98908-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="98908-127">Type</span></span>    |   <span data-ttu-id="98908-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98908-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="98908-129">id</span><span class="sxs-lookup"><span data-stu-id="98908-129">id</span></span> | <span data-ttu-id="98908-130">Stringa</span><span class="sxs-lookup"><span data-stu-id="98908-130">String</span></span> | <span data-ttu-id="98908-131">Identità dell'entità di indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="98908-132">startTime</span><span class="sxs-lookup"><span data-stu-id="98908-132">startTime</span></span> | <span data-ttu-id="98908-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="98908-133">DateTime Nullable</span></span> | <span data-ttu-id="98908-134">Data e ora di creazione dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="98908-135">endTime</span><span class="sxs-lookup"><span data-stu-id="98908-135">endTime</span></span> | <span data-ttu-id="98908-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="98908-136">DateTime Nullable</span></span> | <span data-ttu-id="98908-137">Data e ora di completamento dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="98908-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="98908-138">cancelledBy</span></span> | <span data-ttu-id="98908-139">Stringa</span><span class="sxs-lookup"><span data-stu-id="98908-139">String</span></span> | <span data-ttu-id="98908-140">ID dell'utente/applicazione che ha annullato l'indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="98908-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="98908-141">investigationState</span></span> | <span data-ttu-id="98908-142">Enum</span><span class="sxs-lookup"><span data-stu-id="98908-142">Enum</span></span> | <span data-ttu-id="98908-143">Stato corrente dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-143">The current state of the investigation.</span></span> <span data-ttu-id="98908-144">I valori possibili sono: "Unknown", "Terminated", 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="98908-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="98908-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="98908-145">statusDetails</span></span> | <span data-ttu-id="98908-146">Stringa</span><span class="sxs-lookup"><span data-stu-id="98908-146">String</span></span> | <span data-ttu-id="98908-147">Ulteriori informazioni sullo stato dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="98908-148">machineId</span><span class="sxs-lookup"><span data-stu-id="98908-148">machineId</span></span> | <span data-ttu-id="98908-149">Stringa</span><span class="sxs-lookup"><span data-stu-id="98908-149">String</span></span> | <span data-ttu-id="98908-150">ID del dispositivo in cui viene eseguita l'indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="98908-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="98908-151">computerDnsName</span></span> | <span data-ttu-id="98908-152">Stringa</span><span class="sxs-lookup"><span data-stu-id="98908-152">String</span></span> | <span data-ttu-id="98908-153">Nome del dispositivo in cui viene eseguita l'indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="98908-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="98908-154">triggeringAlertId</span></span> | <span data-ttu-id="98908-155">Stringa</span><span class="sxs-lookup"><span data-stu-id="98908-155">String</span></span> | <span data-ttu-id="98908-156">ID dell'avviso che ha attivato l'indagine.</span><span class="sxs-lookup"><span data-stu-id="98908-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="98908-157">Rappresentazione Json</span><span class="sxs-lookup"><span data-stu-id="98908-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```