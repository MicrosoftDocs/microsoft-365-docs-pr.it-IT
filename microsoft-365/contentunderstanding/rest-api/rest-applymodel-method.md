---
title: Applica modello
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904267"
---
# <a name="apply-model"></a>Applica modello

Applica (o sincronizza) un modello di analisi dei documenti sottoposto a training a una o più raccolte (vedere l'[esempio](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>Richiesta HTTP

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a>Parametri URI

Nessuno

## <a name="request-headers"></a>Intestazioni di richiesta

| Intestazione | Valore |
|--------|-------|
|Accept|application/json;odata=verbose|
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
|201 Created| |Si noti che poiché questa API supporta l'applicazione del modello a più raccolte, è possibile che sia restituito 201 anche se si verifica un errore nell'applicazione del modello a una delle raccolte. <br>Controllare il corpo della risposta per determinare se il modello è stato applicato correttamente a tutte le raccolte specificate. Per informazioni dettagliate, vedere [Corpo della richiesta](rest-applymodel-method.md#request-body).|

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
