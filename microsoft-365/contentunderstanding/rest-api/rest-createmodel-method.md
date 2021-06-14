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
# <a name="create-model"></a>Crea un modello

Crea un modello e il tipo di contenuto associato. Nota che in questo modo viene creato solo il modello. Dovrà comunque essere qualificato nel centro contenuti (vedi [esempio](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>Richiesta HTTP

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a>Parametri URI

Nessuno

## <a name="request-headers"></a>Intestazioni di richiesta

| Intestazione | Valore |
|--------|-------|
|Accetta|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Riepilogo appropriato per il sito corrente|

## <a name="request-body"></a>Corpo della richiesta

|Nome    |Tipo   |Descrizione |
|--------|-------|------------|
|_metadati|  |Imposta i metadati dell'oggetto in SPO. Usa sempre il valore: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|stringa|Gruppo di tipi di contenuto associato al modello. Per impostazione predefinita, "Tipi di contenuto dei documenti intelligenti".|
|ContentTypeName|stringa|Nome tipo di contenuto associato. Il file del modello creato avrà lo stesso nome.|

## <a name="responses"></a>Risposte

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|201 Created| |Operazione completata|

## <a name="examples"></a>Esempi

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Crea un nuovo modello di analisi dei documenti denominato "Contratto Contoso"

#### <a name="sample-request"></a>Richiesta di esempio

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a>Risposta di esempio

**Codice di stato:** 201

## <a name="see-also"></a>Vedere anche

[API REST del modello di analisi dei documenti di Syntex](syntex-model-rest-api.md)
