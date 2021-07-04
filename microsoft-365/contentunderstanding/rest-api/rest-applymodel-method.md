---
title: Modello di applicazione batch
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
description: Usare l'API REST per applicare un modello di analisi dei documenti a una o più raccolte.
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286538"
---
# <a name="batch-apply-model"></a>Modello di Applicazione Batch

Applica (o sincronizza) un modello di analisi dei documenti sottoposto a training a una o più raccolte (vedere l'[esempio](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>Richiesta HTTP

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
|__metadata|sì|stringa|Imposta i metadati dell'oggetto in SPO. Usare sempre il valore: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.|
|Pubblicazioni|sì|MachineLearningPublicationEntityData[]|Raccolta di MachineLearningPublicationEntityData, ognuno dei quali specifica il modello e la raccolta documenti di destinazione.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Nome | Obbligatorio | Tipo | Descrizione |
|--------|-------|--------|------------|
|ModelUniqueId|sì|stringa|ID univoco del file di modello.|
|TargetSiteUrl|sì|stringa|URL completo del sito della raccolta di destinazione.|
|TargetWebServerRelativeUrl|sì|stringa|URL relativo al server Web per la raccolta di destinazione.|
|TargetLibraryServerRelativeUrl|sì|stringa|URL relativo al server per la raccolta di destinazione.|
|ViewOption|no|stringa|Specifica se impostare la nuova visualizzazione modello come predefinita per la raccolta.|

## <a name="response"></a>Risposta

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|201 Created||Si tratta di un'API personalizzata per supportare l'applicazione di un modello a una raccolta di più documenti. In caso di esito positivo parziale, è comunque possibile che venga restituito il 201 creato e il chiamante deve controllare il corpo della risposta per capire se il modello è stato applicato correttamente a una raccolta documenti.|

## <a name="response-body"></a>Corpo della risposta

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|TotalSuccesses|int|Numero totale di un modello applicato correttamente a una raccolta documenti.|
|TotalFailures|int|Numero totale di un modello non applicato a una raccolta documenti.|
|Dettagli|MachineLearningPublicationResult[]|Raccolta di MachineLearningPublicationResult, ognuno dei quali specifica il risultato dettagliato dell'applicazione del modello alla raccolta documenti.|

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

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>Applicare un modello alla raccolta documenti dei contratti nel sito repository

In questo esempio l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Richiesta di esempio

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>Risposta di esempio

Nella risposta, TotalFailures e TotalSuccesses fanno riferimento al numero di errori e successi nell'applicazione del modello alle raccolte specificate.

**Codice di stato:** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Vedere anche

[API REST del modello di analisi dei documenti di Syntex](syntex-model-rest-api.md)
