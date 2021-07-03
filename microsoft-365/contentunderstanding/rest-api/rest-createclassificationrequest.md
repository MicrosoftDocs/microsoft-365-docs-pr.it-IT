---
title: Creare una richiesta di classificazione
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
description: Usa l'API REST per creare una richiesta per classificare uno o più file usando un modello di analisi dei documenti qualificato.
ms.openlocfilehash: b1022787d6e11ebe36c88ecd29936a777289dd74
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287234"
---
# <a name="create-classification-request"></a>Creare una richiesta di classificazione

Crea una richiesta per classificare uno o più file usando il modello di analisi dei documenti applicato (vedi [esempio](rest-createclassificationrequest.md#examples)).

Il servizio REST di SharePoint Online (e SharePoint 2016 e versioni successive locali) supporta la combinazione di più richieste. Le richieste vengono combinate in un'unica chiamata al servizio usando l'opzione di query $batch OData. Questo metodo può essere usato per mettere in coda gli elementi di lavoro di classificazione per centinaia di documenti contemporaneamente.

## <a name="http-request"></a>Richiesta HTTP

```http
POST /_api/machinelearning/workItems HTTP/1.1
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
|_metadata|stringa |Imposta i metadati dell'oggetto in SPO. Usare sempre il valore: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}. |
|TargetSiteId|guid|ID del sito in cui si trova il file da classificare.|
|TargetWebId|guid|ID della pagina Web in cui si trova il file da classificare.|
|TargetUniqueId|guid|ID del file da classificare.|

## <a name="responses"></a>Risposte

| Nome   | Tipo  | Descrizione|
|--------|-------|------------|
|201 Created| |Operazione completata|

## <a name="examples"></a>Esempi

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Mettere in coda una richiesta per classificare un file con ID "e6cff8b7-c90c-4564-b5b8-033449090932"

#### <a name="sample-request"></a>Richiesta di esempio

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a>Risposta di esempio

**Codice di stato:** 201

## <a name="see-also"></a>Vedere anche

[API REST del modello di analisi dei documenti di Syntex](syntex-model-rest-api.md)
