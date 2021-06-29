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
# <a name="updatemodelsettings"></a>UpdateModelSettings

Aggiorna le impostazioni dei modelli disponibili (etichetta di conservazione associata e descrizione del modello) per un modello di analisi dei documenti di SharePoint Syntex (vedere l'[esempio](rest-updatemodelsettings-method.md#examples)).

## <a name="http-request"></a>Richiesta HTTP

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>Parametri URI

|Nome |In |Obbligatorio|Tipo|Descrizione|
|-----|---|--------|----|-----------|
|modelFileName|query|True|stringa|Nome del file di modello di Syntex.|

## <a name="request-headers"></a>Intestazioni di richiesta

| Intestazione | Valore |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Digest appropriato per il sito corrente.|

## <a name="request-body"></a>Corpo della richiesta

|Nome    |Tipo   |Descrizione |
|--------|-------|-------|
|ModelSettings|stringa|JSON delle impostazioni modello.|
|Descrizione|stringa|Descrizione del modello.|
|RetentionLabel| |Informazioni per l'etichetta associata (ID etichetta e nome).|

## <a name="responses"></a>Risposte

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|200 OK| |Operazione completata|

## <a name="examples"></a>Esempi

### <a name="update-model-settings-for-contoso-contract"></a>Aggiornare le impostazioni del modello per Contoso Contract

In questo esempio la descrizione del modello e l'etichetta di conservazione "Standard Hold" vengono aggiornate. L'ID dell'etichetta di conservazione è `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.

#### <a name="sample-request"></a>Richiesta di esempio

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>Risposta di esempio

**Codice di stato:** 200

## <a name="see-also"></a>Vedere anche

[API REST del modello di analisi dei documenti di Syntex](syntex-model-rest-api.md)
