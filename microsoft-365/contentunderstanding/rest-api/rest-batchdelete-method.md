---
title: BatchDelete
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
description: Usa l'API REST per rimuovere un modello di analisi dei documenti applicato da una o più raccolte.
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287454"
---
# <a name="batchdelete"></a>BatchDelete

Rimuove un modello di analisi dei documenti applicato da una o più raccolte. Nota che un modello deve essere rimosso da tutte le raccolte prima di essere eliminato (vedi [esempio](rest-batchdelete-method.md#examples)).

## <a name="http-request"></a>Richiesta HTTP

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>Parametri URI

Nessuno

## <a name="request-headers"></a>Intestazioni della richiesta

| Intestazione | Valore |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Digest appropriato per il sito corrente.|

## <a name="request-body"></a>Corpo della richiesta

| Nome | Obbligatorio | Tipo | Descrizione |
|--------|-------|--------|------------|
|Pubblicazioni|sì|MachineLearningPublicationEntityData[]|Raccolta di MachineLearningPublicationEntityData, ognuno dei quali specifica il modello e la raccolta documenti di destinazione.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Nome | Obbligatorio | Tipo | Descrizione |
|--------|-------|--------|------------|
|ModelUniqueId|sì|stringa|ID univoco del file di modello.|
|TargetSiteUrl|sì|stringa|URL completo del sito della raccolta di destinazione.|
|TargetWebServerRelativeUrl|sì|stringa|URL relativo al server Web per la raccolta di destinazione.|
|TargetLibraryServerRelativeUrl|sì|stringa|URL relativo al server per la raccolta di destinazione.|

## <a name="response"></a>Risposta

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|200 OK||Si tratta di un'API personalizzata per supportare la rimozione di un modello da una raccolta di più documenti. In caso di esito positivo parziale, potrebbe comunque essere restituito 200 OK e il chiamante deve esaminare il corpo della risposta per capire se il modello è stato rimosso correttamente da una raccolta documenti.|

## <a name="response-body"></a>Corpo della risposta

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|TotalSuccesses|int|Numero totale di modelli rimossi correttamente da una raccolta documenti.|
|TotalFailures|int|Numero totale di modelli che non possono essere rimossi da una raccolta documenti.|
|Dettagli|MachineLearningPublicationResult[]|Raccolta di MachineLearningPublicationResult, ognuno dei quali specifica il risultato dettagliato della rimozione del modello da una raccolta documenti.|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|StatusCode|int|Codice di stato HTTP.|
|ErrorMessage|stringa|Messaggio di errore che indica cosa non va quando si applica il modello alla raccolta documenti.|
|Pubblicazione|MachineLearningPublicationEntityData|Specifica le informazioni sul modello e la raccolta documenti di destinazione.| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Nome | Tipo | Descrizione |
|--------|--------|------------|
|ModelUniqueId|stringa|ID univoco del file di modello.|
|TargetSiteUrl|stringa|URL completo del sito della raccolta di destinazione.|
|TargetWebServerRelativeUrl|stringa|URL relativo al server Web per la raccolta di destinazione.|
|TargetLibraryServerRelativeUrl|stringa|URL relativo al server per la raccolta di destinazione.|

## <a name="examples"></a>Esempi

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Rimuovi un modello dalla raccolta documenti di contratti nel sito repository

In questo esempio, l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Richiesta di esempio

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```

#### <a name="sample-response"></a>Risposta di esempio

Nella risposta, TotalFailures e TotalSuccesses fanno riferimento al numero di errori e di successi del modello rimosso dalle librerie specificate.

**Codice di stato:** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Vedere anche

[API REST del modello di analisi dei documenti di Syntex](syntex-model-rest-api.md)
