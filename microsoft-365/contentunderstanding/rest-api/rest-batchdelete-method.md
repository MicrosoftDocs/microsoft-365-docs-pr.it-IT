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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904211"
---
# <a name="batchdelete"></a>BatchDelete

Rimuove un modello di analisi dei documenti applicato da una o più raccolte. Nota che un modello deve essere rimosso da tutte le raccolte prima di essere eliminato (vedi [esempio](rest-batchdelete-method.md#examples)).

## <a name="http-request"></a>Richiesta HTTP

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>Parametri URI

Nessuno

## <a name="request-headers"></a>Intestazioni di richiesta

| Intestazione | Valore |
|--------|-------|
|Accetta|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Digest appropriato per il sito corrente.|

## <a name="request-body"></a>Corpo della richiesta

| Nome | Obbligatorio | Tipo | Descrizione |
|--------|-------|--------|------------|
|ModelUniqueId|sì|stringa|ID univoco del file di modello.|
TargetSiteUrl|sì|stringa|URL completo del sito della raccolta di destinazione.|
TargetWebServerRelativeUrl|sì|stringa|URL relativo al server Web per la raccolta di destinazione.|
TargetLibraryServerRelativeUrl|sì|stringa|URL relativo al server per la raccolta di destinazione.|
ViewOption|no|stringa|Specifica se impostare la nuova visualizzazione modello come predefinita per la raccolta.|

## <a name="response"></a>Risposta

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|200 OK| |Operazione completata|


## <a name="examples"></a>Esempi

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Rimuovi un modello dalla raccolta documenti di contratti nel sito repository

In questo esempio, l'ID del modello di analisi dei documenti Contoso Contract è `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

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

Nella risposta, TotalFailures e TotalSuccesses fanno riferimento al numero di errori e successi del modello applicato alle raccolte specificate.

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
