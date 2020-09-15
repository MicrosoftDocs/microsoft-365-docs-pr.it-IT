---
title: Tipo di risorsa Incident nell'API di Microsoft Threat Protection
description: Informazioni sui metodi e le proprietà del tipo di risorsa Incident in Microsoft Threat Protection
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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650372"
---
# <a name="incident-resource-type"></a><span data-ttu-id="158fa-104">Tipo di risorsa Incident</span><span class="sxs-lookup"><span data-stu-id="158fa-104">Incident resource type</span></span>

<span data-ttu-id="158fa-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="158fa-105">**Applies to:**</span></span>
- <span data-ttu-id="158fa-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="158fa-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="158fa-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="158fa-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="158fa-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="158fa-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="158fa-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="158fa-109">Methods</span></span>

<span data-ttu-id="158fa-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="158fa-110">Method</span></span> |<span data-ttu-id="158fa-111">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="158fa-111">Return Type</span></span> |<span data-ttu-id="158fa-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="158fa-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="158fa-113">Incidenti di elenco</span><span class="sxs-lookup"><span data-stu-id="158fa-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="158fa-114">Elenco [eventi](api-incident.md) non consentiti</span><span class="sxs-lookup"><span data-stu-id="158fa-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="158fa-115">Ottenere un elenco di eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="158fa-115">Get a list of incidents.</span></span>
[<span data-ttu-id="158fa-116">Update Incident</span><span class="sxs-lookup"><span data-stu-id="158fa-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="158fa-117">Operazioni non consentite</span><span class="sxs-lookup"><span data-stu-id="158fa-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="158fa-118">Update specific Incident.</span><span class="sxs-lookup"><span data-stu-id="158fa-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="158fa-119">Proprietà</span><span class="sxs-lookup"><span data-stu-id="158fa-119">Properties</span></span>

<span data-ttu-id="158fa-120">Proprietà</span><span class="sxs-lookup"><span data-stu-id="158fa-120">Property</span></span> |    <span data-ttu-id="158fa-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="158fa-121">Type</span></span>    |    <span data-ttu-id="158fa-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="158fa-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="158fa-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="158fa-123">incidentId</span></span> | <span data-ttu-id="158fa-124">long</span><span class="sxs-lookup"><span data-stu-id="158fa-124">long</span></span> | <span data-ttu-id="158fa-125">ID univoco per gli incidenti.</span><span class="sxs-lookup"><span data-stu-id="158fa-125">Incident unique ID.</span></span>
<span data-ttu-id="158fa-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="158fa-126">redirectIncidentId</span></span> | <span data-ttu-id="158fa-127">Long Nullable</span><span class="sxs-lookup"><span data-stu-id="158fa-127">nullable long</span></span> | <span data-ttu-id="158fa-128">ID di incidente in cui è stato unito l'evento Incident corrente.</span><span class="sxs-lookup"><span data-stu-id="158fa-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="158fa-129">evento incidentname</span><span class="sxs-lookup"><span data-stu-id="158fa-129">incidentName</span></span> | <span data-ttu-id="158fa-130">stringa</span><span class="sxs-lookup"><span data-stu-id="158fa-130">string</span></span> | <span data-ttu-id="158fa-131">Nome dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="158fa-131">The name of the Incident.</span></span>
<span data-ttu-id="158fa-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="158fa-132">createdTime</span></span> | <span data-ttu-id="158fa-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="158fa-133">DateTimeOffset</span></span> | <span data-ttu-id="158fa-134">La data e l'ora (in formato UTC) dell'evento Incident è stato creato.</span><span class="sxs-lookup"><span data-stu-id="158fa-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="158fa-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="158fa-135">lastUpdateTime</span></span> | <span data-ttu-id="158fa-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="158fa-136">DateTimeOffset</span></span> | <span data-ttu-id="158fa-137">La data e l'ora (in formato UTC) dell'ultimo aggiornamento dell'evento.</span><span class="sxs-lookup"><span data-stu-id="158fa-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="158fa-138">AssegnatoA</span><span class="sxs-lookup"><span data-stu-id="158fa-138">assignedTo</span></span> | <span data-ttu-id="158fa-139">stringa</span><span class="sxs-lookup"><span data-stu-id="158fa-139">string</span></span> | <span data-ttu-id="158fa-140">Proprietario dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="158fa-140">Owner of the Incident.</span></span>
<span data-ttu-id="158fa-141">gravità</span><span class="sxs-lookup"><span data-stu-id="158fa-141">severity</span></span> | <span data-ttu-id="158fa-142">Enum</span><span class="sxs-lookup"><span data-stu-id="158fa-142">Enum</span></span> | <span data-ttu-id="158fa-143">Gravità dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="158fa-143">Severity of the Incident.</span></span> <span data-ttu-id="158fa-144">I valori possibili sono: ```UnSpecified``` ,, ```Informational``` ```Low``` ```Medium``` e ```High``` .</span><span class="sxs-lookup"><span data-stu-id="158fa-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="158fa-145">stato</span><span class="sxs-lookup"><span data-stu-id="158fa-145">status</span></span> | <span data-ttu-id="158fa-146">Enum</span><span class="sxs-lookup"><span data-stu-id="158fa-146">Enum</span></span> | <span data-ttu-id="158fa-147">Specifica lo stato corrente dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="158fa-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="158fa-148">I valori possibili sono ```Active``` : ```Resolved``` e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="158fa-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="158fa-149">classificazione</span><span class="sxs-lookup"><span data-stu-id="158fa-149">classification</span></span> | <span data-ttu-id="158fa-150">Enum</span><span class="sxs-lookup"><span data-stu-id="158fa-150">Enum</span></span> | <span data-ttu-id="158fa-151">Specifica dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="158fa-151">Specification of the incident.</span></span> <span data-ttu-id="158fa-152">I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="158fa-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="158fa-153">determinazione</span><span class="sxs-lookup"><span data-stu-id="158fa-153">determination</span></span> | <span data-ttu-id="158fa-154">Enum</span><span class="sxs-lookup"><span data-stu-id="158fa-154">Enum</span></span> | <span data-ttu-id="158fa-155">Specifica la determinazione dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="158fa-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="158fa-156">I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="158fa-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="158fa-157">Tag</span><span class="sxs-lookup"><span data-stu-id="158fa-157">tags</span></span> | <span data-ttu-id="158fa-158">Elenco di stringhe</span><span class="sxs-lookup"><span data-stu-id="158fa-158">string List</span></span> | <span data-ttu-id="158fa-159">Elenco dei tag Incident.</span><span class="sxs-lookup"><span data-stu-id="158fa-159">List of Incident tags.</span></span>
<span data-ttu-id="158fa-160">avvisi</span><span class="sxs-lookup"><span data-stu-id="158fa-160">alerts</span></span> | <span data-ttu-id="158fa-161">Elenco avvisi</span><span class="sxs-lookup"><span data-stu-id="158fa-161">Alert List</span></span> | <span data-ttu-id="158fa-162">Elenco di avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="158fa-162">List of related alerts.</span></span> <span data-ttu-id="158fa-163">Vedere esempi di documentazione sull'API degli [incidenti di elenco](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="158fa-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>