---
title: Ottieni informazioni su modelli e raccolte
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
description: Usa l'API REST per ottenere informazioni su un modello e sulla raccolta in cui è stato applicato.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904224"
---
# <a name="get-model-and-library-information"></a>Ottieni informazioni su modelli e raccolte

Ottiene informazioni su un modello e sulla raccolta in cui è stato applicato (vedi [esempio](rest-getmodelandlibraryinfo.md#examples)).

## <a name="http-request"></a>Richiesta HTTP

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a>Parametri URI

| Nome | In | Obbligatoria | Tipo | Descrizione |
|--------|-------|--------|------------|
|ModelUniqueId|query|Vero|GUID|ID univoco del file di modello.|

## <a name="request-headers"></a>Intestazioni di richiesta

| Intestazione | Valore |
|--------|-------|
|Accetta|application/json;odata=verbose|


## <a name="request-body"></a>Corpo della richiesta

| Nome | Obbligatorio | Tipo | Descrizione |
|--------|-------|--------|------------|
|ModelUniqueId|sì|stringa|ID univoco del file di modello.|
|TargetSiteUrl|sì|stringa|URL completo del sito della raccolta di destinazione.|
|TargetWebServerRelativeUrl|sì|stringa|URL relativo al server Web per la raccolta di destinazione.|
|TargetLibraryServerRelativeUrl|sì|stringa|URL relativo al server per la raccolta di destinazione.|
|TargetLibraryRemoved|sì|int|Il contrassegno che indica se la raccolta di destinazione è stata rimossa o meno.|

## <a name="response"></a>Risposta

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|200 OK| |Operazione completata|
|201 Created| |Nota che poiché questa API supporta l'applicazione del modello a più raccolte, è possibile che sia restituito 201 anche se si verifica un errore nell'applicazione del modello a una delle raccolte. <br>Controlla il corpo della risposta per determinare se il modello è stato applicato correttamente a tutte le raccolte specificate. Per informazioni dettagliate, vedi [Corpo della richiesta](rest-getmodelandlibraryinfo.md#request-body).|

## <a name="examples"></a>Esempi

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a>Ottieni informazioni sul modello di contratti e sulla raccolta documenti primed nel sito del repository

In questo esempio, l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Richiesta di esempio

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a>Risposta di esempio

**Codice di stato:** 200

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a>Vedere anche

[API REST del modello di analisi dei documenti di Syntex](syntex-model-rest-api.md)
