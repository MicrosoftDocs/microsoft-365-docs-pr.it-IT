---
title: Crea un modello
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
description: Usa l'API REST per creare un modello e il tipo di contenuto associato.
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904223"
---
# <a name="create-model"></a><span data-ttu-id="3d051-103">Crea un modello</span><span class="sxs-lookup"><span data-stu-id="3d051-103">Create model</span></span>

<span data-ttu-id="3d051-104">Crea un modello e il tipo di contenuto associato.</span><span class="sxs-lookup"><span data-stu-id="3d051-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="3d051-105">Nota che in questo modo viene creato solo il modello.</span><span class="sxs-lookup"><span data-stu-id="3d051-105">Note that this only creates the model.</span></span> <span data-ttu-id="3d051-106">Dovrà comunque essere qualificato nel centro contenuti (vedi [esempio](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="3d051-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="3d051-107">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="3d051-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="3d051-108">Parametri URI</span><span class="sxs-lookup"><span data-stu-id="3d051-108">URI Parameters</span></span>

<span data-ttu-id="3d051-109">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3d051-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="3d051-110">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="3d051-110">Request headers</span></span>

| <span data-ttu-id="3d051-111">Intestazione</span><span class="sxs-lookup"><span data-stu-id="3d051-111">Header</span></span> | <span data-ttu-id="3d051-112">Valore</span><span class="sxs-lookup"><span data-stu-id="3d051-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="3d051-113">Accetta</span><span class="sxs-lookup"><span data-stu-id="3d051-113">Accept</span></span>|<span data-ttu-id="3d051-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="3d051-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="3d051-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3d051-115">Content-Type</span></span>|<span data-ttu-id="3d051-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="3d051-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="3d051-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="3d051-117">x-requestdigest</span></span>|<span data-ttu-id="3d051-118">Riepilogo appropriato per il sito corrente</span><span class="sxs-lookup"><span data-stu-id="3d051-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="3d051-119">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="3d051-119">Request body</span></span>

|<span data-ttu-id="3d051-120">Nome</span><span class="sxs-lookup"><span data-stu-id="3d051-120">Name</span></span>    |<span data-ttu-id="3d051-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="3d051-121">Type</span></span>   |<span data-ttu-id="3d051-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d051-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="3d051-123">_metadati</span><span class="sxs-lookup"><span data-stu-id="3d051-123">_metadata</span></span>|  |<span data-ttu-id="3d051-124">Imposta i metadati dell'oggetto in SPO.</span><span class="sxs-lookup"><span data-stu-id="3d051-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="3d051-125">Usa sempre il valore: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="3d051-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="3d051-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="3d051-126">ContentTypeGroup</span></span>|<span data-ttu-id="3d051-127">stringa</span><span class="sxs-lookup"><span data-stu-id="3d051-127">string</span></span>|<span data-ttu-id="3d051-128">Gruppo di tipi di contenuto associato al modello.</span><span class="sxs-lookup"><span data-stu-id="3d051-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="3d051-129">Per impostazione predefinita, "Tipi di contenuto dei documenti intelligenti".</span><span class="sxs-lookup"><span data-stu-id="3d051-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="3d051-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="3d051-130">ContentTypeName</span></span>|<span data-ttu-id="3d051-131">stringa</span><span class="sxs-lookup"><span data-stu-id="3d051-131">string</span></span>|<span data-ttu-id="3d051-132">Nome tipo di contenuto associato.</span><span class="sxs-lookup"><span data-stu-id="3d051-132">The associated content type name.</span></span> <span data-ttu-id="3d051-133">Il file del modello creato avrà lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="3d051-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="3d051-134">Risposte</span><span class="sxs-lookup"><span data-stu-id="3d051-134">Responses</span></span>

| <span data-ttu-id="3d051-135">Nome</span><span class="sxs-lookup"><span data-stu-id="3d051-135">Name</span></span>   | <span data-ttu-id="3d051-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="3d051-136">Type</span></span>  | <span data-ttu-id="3d051-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d051-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="3d051-138">201 Created</span><span class="sxs-lookup"><span data-stu-id="3d051-138">201 Created</span></span>| |<span data-ttu-id="3d051-139">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="3d051-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="3d051-140">Esempi</span><span class="sxs-lookup"><span data-stu-id="3d051-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="3d051-141">Crea un nuovo modello di analisi dei documenti denominato "Contratto Contoso"</span><span class="sxs-lookup"><span data-stu-id="3d051-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="3d051-142">Richiesta di esempio</span><span class="sxs-lookup"><span data-stu-id="3d051-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a><span data-ttu-id="3d051-143">Risposta di esempio</span><span class="sxs-lookup"><span data-stu-id="3d051-143">Sample response</span></span>

<span data-ttu-id="3d051-144">**Codice di stato:** 201</span><span class="sxs-lookup"><span data-stu-id="3d051-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="3d051-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d051-145">See also</span></span>

[<span data-ttu-id="3d051-146">API REST del modello di analisi dei documenti di Syntex</span><span class="sxs-lookup"><span data-stu-id="3d051-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
