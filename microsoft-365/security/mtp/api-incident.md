---
title: Tipo di risorsa Incident nell'API Microsoft 365 Defender
description: Informazioni sui metodi e le proprietà del tipo di risorsa Incident in Microsoft 365 Defender
keywords: eventi incidentati, incidenti, API
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844021"
---
# <a name="incident-resource-type"></a><span data-ttu-id="695a7-104">Tipo di risorsa Incident</span><span class="sxs-lookup"><span data-stu-id="695a7-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="695a7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="695a7-105">**Applies to:**</span></span>
- <span data-ttu-id="695a7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="695a7-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="695a7-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="695a7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="695a7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="695a7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="695a7-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="695a7-109">Methods</span></span>

<span data-ttu-id="695a7-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="695a7-110">Method</span></span> |<span data-ttu-id="695a7-111">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="695a7-111">Return Type</span></span> |<span data-ttu-id="695a7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="695a7-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="695a7-113">Elencare incidenti</span><span class="sxs-lookup"><span data-stu-id="695a7-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="695a7-114">Elenco [eventi](api-incident.md) non consentiti</span><span class="sxs-lookup"><span data-stu-id="695a7-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="695a7-115">Ottenere un elenco di eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="695a7-115">Get a list of incidents.</span></span>
[<span data-ttu-id="695a7-116">Aggiornare incidente</span><span class="sxs-lookup"><span data-stu-id="695a7-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="695a7-117">Operazioni non consentite</span><span class="sxs-lookup"><span data-stu-id="695a7-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="695a7-118">Update specific Incident.</span><span class="sxs-lookup"><span data-stu-id="695a7-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="695a7-119">Proprietà</span><span class="sxs-lookup"><span data-stu-id="695a7-119">Properties</span></span>

<span data-ttu-id="695a7-120">Proprietà</span><span class="sxs-lookup"><span data-stu-id="695a7-120">Property</span></span> |    <span data-ttu-id="695a7-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="695a7-121">Type</span></span>    |    <span data-ttu-id="695a7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="695a7-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="695a7-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="695a7-123">incidentId</span></span> | <span data-ttu-id="695a7-124">long</span><span class="sxs-lookup"><span data-stu-id="695a7-124">long</span></span> | <span data-ttu-id="695a7-125">ID univoco per gli incidenti.</span><span class="sxs-lookup"><span data-stu-id="695a7-125">Incident unique ID.</span></span>
<span data-ttu-id="695a7-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="695a7-126">redirectIncidentId</span></span> | <span data-ttu-id="695a7-127">Long Nullable</span><span class="sxs-lookup"><span data-stu-id="695a7-127">nullable long</span></span> | <span data-ttu-id="695a7-128">ID di incidente in cui è stato unito l'evento Incident corrente.</span><span class="sxs-lookup"><span data-stu-id="695a7-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="695a7-129">evento incidentname</span><span class="sxs-lookup"><span data-stu-id="695a7-129">incidentName</span></span> | <span data-ttu-id="695a7-130">stringa</span><span class="sxs-lookup"><span data-stu-id="695a7-130">string</span></span> | <span data-ttu-id="695a7-131">Nome dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="695a7-131">The name of the Incident.</span></span>
<span data-ttu-id="695a7-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="695a7-132">createdTime</span></span> | <span data-ttu-id="695a7-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="695a7-133">DateTimeOffset</span></span> | <span data-ttu-id="695a7-134">La data e l'ora (in formato UTC) dell'evento Incident è stato creato.</span><span class="sxs-lookup"><span data-stu-id="695a7-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="695a7-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="695a7-135">lastUpdateTime</span></span> | <span data-ttu-id="695a7-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="695a7-136">DateTimeOffset</span></span> | <span data-ttu-id="695a7-137">La data e l'ora (in formato UTC) dell'ultimo aggiornamento dell'evento.</span><span class="sxs-lookup"><span data-stu-id="695a7-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="695a7-138">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="695a7-138">assignedTo</span></span> | <span data-ttu-id="695a7-139">stringa</span><span class="sxs-lookup"><span data-stu-id="695a7-139">string</span></span> | <span data-ttu-id="695a7-140">Proprietario dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="695a7-140">Owner of the Incident.</span></span>
<span data-ttu-id="695a7-141">gravità</span><span class="sxs-lookup"><span data-stu-id="695a7-141">severity</span></span> | <span data-ttu-id="695a7-142">Enum</span><span class="sxs-lookup"><span data-stu-id="695a7-142">Enum</span></span> | <span data-ttu-id="695a7-143">Gravità dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="695a7-143">Severity of the Incident.</span></span> <span data-ttu-id="695a7-144">I valori possibili sono: ```UnSpecified``` ,, ```Informational``` ```Low``` ```Medium``` e ```High``` .</span><span class="sxs-lookup"><span data-stu-id="695a7-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="695a7-145">stato</span><span class="sxs-lookup"><span data-stu-id="695a7-145">status</span></span> | <span data-ttu-id="695a7-146">Enum</span><span class="sxs-lookup"><span data-stu-id="695a7-146">Enum</span></span> | <span data-ttu-id="695a7-147">Specifica lo stato corrente dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="695a7-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="695a7-148">I valori possibili sono ```Active``` : ```Resolved``` e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="695a7-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="695a7-149">classificazione</span><span class="sxs-lookup"><span data-stu-id="695a7-149">classification</span></span> | <span data-ttu-id="695a7-150">Enum</span><span class="sxs-lookup"><span data-stu-id="695a7-150">Enum</span></span> | <span data-ttu-id="695a7-151">Specifica dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="695a7-151">Specification of the incident.</span></span> <span data-ttu-id="695a7-152">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="695a7-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="695a7-153">determinazione</span><span class="sxs-lookup"><span data-stu-id="695a7-153">determination</span></span> | <span data-ttu-id="695a7-154">Enum</span><span class="sxs-lookup"><span data-stu-id="695a7-154">Enum</span></span> | <span data-ttu-id="695a7-155">Specifica la determinazione dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="695a7-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="695a7-156">I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="695a7-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="695a7-157">Tag</span><span class="sxs-lookup"><span data-stu-id="695a7-157">tags</span></span> | <span data-ttu-id="695a7-158">Elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="695a7-158">string List</span></span> | <span data-ttu-id="695a7-159">Elenco dei tag Incident.</span><span class="sxs-lookup"><span data-stu-id="695a7-159">List of Incident tags.</span></span>
<span data-ttu-id="695a7-160">avvisi</span><span class="sxs-lookup"><span data-stu-id="695a7-160">alerts</span></span> | <span data-ttu-id="695a7-161">Elenco avvisi</span><span class="sxs-lookup"><span data-stu-id="695a7-161">Alert List</span></span> | <span data-ttu-id="695a7-162">Elenco di avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="695a7-162">List of related alerts.</span></span> <span data-ttu-id="695a7-163">Vedere esempi di documentazione sull'API degli [incidenti di elenco](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="695a7-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
