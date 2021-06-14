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
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904229"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="c00e5-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="c00e5-103">UpdateModelSettings</span></span>

<span data-ttu-id="c00e5-104">Aggiorna le impostazioni dei modelli disponibili (etichetta di conservazione associata e descrizione del modello) per un modello di analisi dei documenti di SharePoint Syntex (vedere l'[esempio](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="c00e5-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="c00e5-105">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="c00e5-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="c00e5-106">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="c00e5-106">URI parameters</span></span>

<span data-ttu-id="c00e5-107">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c00e5-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="c00e5-108">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="c00e5-108">Request headers</span></span>

| <span data-ttu-id="c00e5-109">Intestazione</span><span class="sxs-lookup"><span data-stu-id="c00e5-109">Header</span></span> | <span data-ttu-id="c00e5-110">Valore</span><span class="sxs-lookup"><span data-stu-id="c00e5-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="c00e5-111">Accept</span><span class="sxs-lookup"><span data-stu-id="c00e5-111">Accept</span></span>|<span data-ttu-id="c00e5-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="c00e5-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="c00e5-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c00e5-113">Content-Type</span></span>|<span data-ttu-id="c00e5-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="c00e5-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="c00e5-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="c00e5-115">x-requestdigest</span></span>|<span data-ttu-id="c00e5-116">Digest appropriato per il sito corrente.</span><span class="sxs-lookup"><span data-stu-id="c00e5-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="c00e5-117">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="c00e5-117">Request body</span></span>

|<span data-ttu-id="c00e5-118">Nome</span><span class="sxs-lookup"><span data-stu-id="c00e5-118">Name</span></span>    |<span data-ttu-id="c00e5-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="c00e5-119">Type</span></span>   |<span data-ttu-id="c00e5-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c00e5-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="c00e5-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="c00e5-121">ModelSettings</span></span>|<span data-ttu-id="c00e5-122">stringa</span><span class="sxs-lookup"><span data-stu-id="c00e5-122">string</span></span>|<span data-ttu-id="c00e5-123">JSON delle impostazioni modello.</span><span class="sxs-lookup"><span data-stu-id="c00e5-123">JSON of model settings.</span></span>|
|<span data-ttu-id="c00e5-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c00e5-124">Description</span></span>|<span data-ttu-id="c00e5-125">stringa</span><span class="sxs-lookup"><span data-stu-id="c00e5-125">string</span></span>|<span data-ttu-id="c00e5-126">Descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="c00e5-126">The model description.</span></span>|
|<span data-ttu-id="c00e5-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="c00e5-127">RetentionLabel</span></span>| |<span data-ttu-id="c00e5-128">Informazioni per l'etichetta associata (ID etichetta e nome).</span><span class="sxs-lookup"><span data-stu-id="c00e5-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="c00e5-129">Risposte</span><span class="sxs-lookup"><span data-stu-id="c00e5-129">Responses</span></span>

| <span data-ttu-id="c00e5-130">Nome</span><span class="sxs-lookup"><span data-stu-id="c00e5-130">Name</span></span>   | <span data-ttu-id="c00e5-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="c00e5-131">Type</span></span>  | <span data-ttu-id="c00e5-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c00e5-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="c00e5-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="c00e5-133">200 OK</span></span>| |<span data-ttu-id="c00e5-134">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="c00e5-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="c00e5-135">Esempi</span><span class="sxs-lookup"><span data-stu-id="c00e5-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="c00e5-136">Aggiornare le impostazioni del modello per Contoso Contract</span><span class="sxs-lookup"><span data-stu-id="c00e5-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="c00e5-137">In questo esempio la descrizione del modello e l'etichetta di conservazione "Standard Hold" vengono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="c00e5-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="c00e5-138">L'ID dell'etichetta di conservazione è `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="c00e5-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="c00e5-139">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="c00e5-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="c00e5-140">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="c00e5-140">Sample response</span></span>

<span data-ttu-id="c00e5-141">**Codice di stato:** 200</span><span class="sxs-lookup"><span data-stu-id="c00e5-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="c00e5-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c00e5-142">See also</span></span>

[<span data-ttu-id="c00e5-143">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="c00e5-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
