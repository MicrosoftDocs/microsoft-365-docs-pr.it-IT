---
title: Creare un modello
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
ms.openlocfilehash: 1c5bd84c777774edc1aa0c2419181f7b84aa4707
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287246"
---
# <a name="create-model"></a>Creare un modello

Crea un modello e il tipo di contenuto associato. Si noti che in questo modo viene creato solo il modello. Dovrà comunque essere qualificato nel centro contenuti (vedi [esempio](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>Richiesta HTTP

```http
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a>Parametri URI

Nessuno

## <a name="request-headers"></a>Intestazioni della richiesta

| Intestazione | Valore |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Riepilogo appropriato per il sito corrente|

## <a name="request-body"></a>Corpo della richiesta

|Nome    |Tipo   |Descrizione |
|--------|-------|------------|
|_metadata|  |Imposta i metadati dell'oggetto in SPO. Usare sempre il valore: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|stringa|Gruppo di tipi di contenuto associato al modello. Per impostazione predefinita, "Tipi di contenuto dei documenti intelligenti".|
|ContentTypeName|stringa|Nome tipo di contenuto associato. Il file del modello creato avrà lo stesso nome.|

## <a name="responses"></a>Risposte

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|201 Created| |Operazione completata|

## <a name="examples"></a>Esempi

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Creare un nuovo modello di analisi dei documenti denominato "Contratto Contoso"

#### <a name="sample-request"></a>Richiesta di esempio

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a>Risposta di esempio

**Codice di stato:** 201

## <a name="see-also"></a>Vedere anche

[API REST del modello di analisi dei documenti di Syntex](syntex-model-rest-api.md)
