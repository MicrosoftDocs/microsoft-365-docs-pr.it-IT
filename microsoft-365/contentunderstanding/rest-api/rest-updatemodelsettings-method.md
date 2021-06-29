---
title: UpdateModelSettings
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Usare l'API REST per aggiornare le impostazioni dei modelli disponibili per un modello di analisi dei documenti di SharePoint Syntex.
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177166"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="44a4a-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="44a4a-103">UpdateModelSettings</span></span>

<span data-ttu-id="44a4a-104">Aggiorna le impostazioni dei modelli disponibili (etichetta di conservazione associata e descrizione del modello) per un modello di analisi dei documenti di SharePoint Syntex (vedere l'[esempio](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="44a4a-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="44a4a-105">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="44a4a-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="44a4a-106">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="44a4a-106">URI parameters</span></span>

|<span data-ttu-id="44a4a-107">Nome</span><span class="sxs-lookup"><span data-stu-id="44a4a-107">Name</span></span> |<span data-ttu-id="44a4a-108">In</span><span class="sxs-lookup"><span data-stu-id="44a4a-108">In</span></span> |<span data-ttu-id="44a4a-109">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="44a4a-109">Required</span></span>|<span data-ttu-id="44a4a-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="44a4a-110">Type</span></span>|<span data-ttu-id="44a4a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a4a-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="44a4a-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="44a4a-112">modelFileName</span></span>|<span data-ttu-id="44a4a-113">query</span><span class="sxs-lookup"><span data-stu-id="44a4a-113">query</span></span>|<span data-ttu-id="44a4a-114">True</span><span class="sxs-lookup"><span data-stu-id="44a4a-114">True</span></span>|<span data-ttu-id="44a4a-115">stringa</span><span class="sxs-lookup"><span data-stu-id="44a4a-115">string</span></span>|<span data-ttu-id="44a4a-116">Nome del file di modello di Syntex.</span><span class="sxs-lookup"><span data-stu-id="44a4a-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="44a4a-117">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="44a4a-117">Request headers</span></span>

| <span data-ttu-id="44a4a-118">Intestazione</span><span class="sxs-lookup"><span data-stu-id="44a4a-118">Header</span></span> | <span data-ttu-id="44a4a-119">Valore</span><span class="sxs-lookup"><span data-stu-id="44a4a-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="44a4a-120">Accept</span><span class="sxs-lookup"><span data-stu-id="44a4a-120">Accept</span></span>|<span data-ttu-id="44a4a-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="44a4a-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="44a4a-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="44a4a-122">Content-Type</span></span>|<span data-ttu-id="44a4a-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="44a4a-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="44a4a-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="44a4a-124">x-requestdigest</span></span>|<span data-ttu-id="44a4a-125">Digest appropriato per il sito corrente.</span><span class="sxs-lookup"><span data-stu-id="44a4a-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="44a4a-126">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="44a4a-126">Request body</span></span>

|<span data-ttu-id="44a4a-127">Nome</span><span class="sxs-lookup"><span data-stu-id="44a4a-127">Name</span></span>    |<span data-ttu-id="44a4a-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="44a4a-128">Type</span></span>   |<span data-ttu-id="44a4a-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a4a-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="44a4a-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="44a4a-130">ModelSettings</span></span>|<span data-ttu-id="44a4a-131">stringa</span><span class="sxs-lookup"><span data-stu-id="44a4a-131">string</span></span>|<span data-ttu-id="44a4a-132">JSON delle impostazioni modello.</span><span class="sxs-lookup"><span data-stu-id="44a4a-132">JSON of model settings.</span></span>|
|<span data-ttu-id="44a4a-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a4a-133">Description</span></span>|<span data-ttu-id="44a4a-134">stringa</span><span class="sxs-lookup"><span data-stu-id="44a4a-134">string</span></span>|<span data-ttu-id="44a4a-135">Descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="44a4a-135">The model description.</span></span>|
|<span data-ttu-id="44a4a-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="44a4a-136">RetentionLabel</span></span>| |<span data-ttu-id="44a4a-137">Informazioni per l'etichetta associata (ID etichetta e nome).</span><span class="sxs-lookup"><span data-stu-id="44a4a-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="44a4a-138">Risposte</span><span class="sxs-lookup"><span data-stu-id="44a4a-138">Responses</span></span>

| <span data-ttu-id="44a4a-139">Nome</span><span class="sxs-lookup"><span data-stu-id="44a4a-139">Name</span></span>   | <span data-ttu-id="44a4a-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="44a4a-140">Type</span></span>  | <span data-ttu-id="44a4a-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a4a-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="44a4a-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="44a4a-142">200 OK</span></span>| |<span data-ttu-id="44a4a-143">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="44a4a-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="44a4a-144">Esempi</span><span class="sxs-lookup"><span data-stu-id="44a4a-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="44a4a-145">Aggiornare le impostazioni del modello per Contoso Contract</span><span class="sxs-lookup"><span data-stu-id="44a4a-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="44a4a-146">In questo esempio la descrizione del modello e l'etichetta di conservazione "Standard Hold" vengono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="44a4a-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="44a4a-147">L'ID dell'etichetta di conservazione è `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="44a4a-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="44a4a-148">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="44a4a-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="44a4a-149">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="44a4a-149">Sample response</span></span>

<span data-ttu-id="44a4a-150">**Codice di stato:** 200</span><span class="sxs-lookup"><span data-stu-id="44a4a-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="44a4a-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44a4a-151">See also</span></span>

[<span data-ttu-id="44a4a-152">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="44a4a-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
