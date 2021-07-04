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
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288648"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="cd99e-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="cd99e-103">UpdateModelSettings</span></span>

<span data-ttu-id="cd99e-104">Aggiorna le impostazioni dei modelli disponibili (etichetta di conservazione associata e descrizione del modello) per un modello di analisi dei documenti di SharePoint Syntex (vedere l'[esempio](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="cd99e-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="cd99e-105">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="cd99e-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="cd99e-106">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="cd99e-106">URI parameters</span></span>

|<span data-ttu-id="cd99e-107">Nome</span><span class="sxs-lookup"><span data-stu-id="cd99e-107">Name</span></span> |<span data-ttu-id="cd99e-108">In</span><span class="sxs-lookup"><span data-stu-id="cd99e-108">In</span></span> |<span data-ttu-id="cd99e-109">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="cd99e-109">Required</span></span>|<span data-ttu-id="cd99e-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="cd99e-110">Type</span></span>|<span data-ttu-id="cd99e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd99e-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="cd99e-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="cd99e-112">modelFileName</span></span>|<span data-ttu-id="cd99e-113">query</span><span class="sxs-lookup"><span data-stu-id="cd99e-113">query</span></span>|<span data-ttu-id="cd99e-114">True</span><span class="sxs-lookup"><span data-stu-id="cd99e-114">True</span></span>|<span data-ttu-id="cd99e-115">stringa</span><span class="sxs-lookup"><span data-stu-id="cd99e-115">string</span></span>|<span data-ttu-id="cd99e-116">Nome del file di modello di Syntex.</span><span class="sxs-lookup"><span data-stu-id="cd99e-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="cd99e-117">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="cd99e-117">Request headers</span></span>

| <span data-ttu-id="cd99e-118">Intestazione</span><span class="sxs-lookup"><span data-stu-id="cd99e-118">Header</span></span> | <span data-ttu-id="cd99e-119">Valore</span><span class="sxs-lookup"><span data-stu-id="cd99e-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="cd99e-120">Accept</span><span class="sxs-lookup"><span data-stu-id="cd99e-120">Accept</span></span>|<span data-ttu-id="cd99e-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="cd99e-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="cd99e-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cd99e-122">Content-Type</span></span>|<span data-ttu-id="cd99e-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="cd99e-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="cd99e-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="cd99e-124">x-requestdigest</span></span>|<span data-ttu-id="cd99e-125">Digest appropriato per il sito corrente.</span><span class="sxs-lookup"><span data-stu-id="cd99e-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="cd99e-126">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="cd99e-126">Request body</span></span>

|<span data-ttu-id="cd99e-127">Nome</span><span class="sxs-lookup"><span data-stu-id="cd99e-127">Name</span></span>    |<span data-ttu-id="cd99e-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="cd99e-128">Type</span></span>   |<span data-ttu-id="cd99e-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd99e-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="cd99e-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="cd99e-130">ModelSettings</span></span>|<span data-ttu-id="cd99e-131">stringa</span><span class="sxs-lookup"><span data-stu-id="cd99e-131">string</span></span>|<span data-ttu-id="cd99e-132">JSON delle impostazioni modello.</span><span class="sxs-lookup"><span data-stu-id="cd99e-132">JSON of model settings.</span></span>|
|<span data-ttu-id="cd99e-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd99e-133">Description</span></span>|<span data-ttu-id="cd99e-134">stringa</span><span class="sxs-lookup"><span data-stu-id="cd99e-134">string</span></span>|<span data-ttu-id="cd99e-135">Descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="cd99e-135">The model description.</span></span>|
|<span data-ttu-id="cd99e-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="cd99e-136">RetentionLabel</span></span>| |<span data-ttu-id="cd99e-137">Informazioni per l'etichetta associata (ID etichetta e nome).</span><span class="sxs-lookup"><span data-stu-id="cd99e-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="cd99e-138">Risposte</span><span class="sxs-lookup"><span data-stu-id="cd99e-138">Responses</span></span>

| <span data-ttu-id="cd99e-139">Nome</span><span class="sxs-lookup"><span data-stu-id="cd99e-139">Name</span></span>   | <span data-ttu-id="cd99e-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="cd99e-140">Type</span></span>  | <span data-ttu-id="cd99e-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd99e-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="cd99e-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="cd99e-142">200 OK</span></span>| |<span data-ttu-id="cd99e-143">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="cd99e-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="cd99e-144">Esempi</span><span class="sxs-lookup"><span data-stu-id="cd99e-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="cd99e-145">Aggiornare le impostazioni del modello per Contoso Contract</span><span class="sxs-lookup"><span data-stu-id="cd99e-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="cd99e-146">In questo esempio la descrizione del modello e l'etichetta di conservazione "Standard Hold" vengono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="cd99e-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="cd99e-147">L'ID dell'etichetta di conservazione è `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="cd99e-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="cd99e-148">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="cd99e-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="cd99e-149">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="cd99e-149">Sample response</span></span>

<span data-ttu-id="cd99e-150">**Codice di stato:** 200</span><span class="sxs-lookup"><span data-stu-id="cd99e-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="cd99e-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd99e-151">See also</span></span>

[<span data-ttu-id="cd99e-152">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="cd99e-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
