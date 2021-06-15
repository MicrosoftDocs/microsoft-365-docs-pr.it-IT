---
title: API REST del modello di analisi dei documenti di SharePoint Syntex
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
description: Panoramica dell’API REST del modello di analisi dei documenti di SharePoint Syntex.
ms.openlocfilehash: 279c624bb818e5d8d33b476f997290269ff634cb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904235"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>API REST del modello di analisi dei documenti di SharePoint Syntex

È possibile usare l'interfaccia REST di SharePoint per creare un modello di analisi dei documenti, applicare il modello a una o più raccolte o rimuoverlo e ottenere o aggiornare le informazioni sul modello. 

Il servizio REST di SharePoint Online (e SharePoint 2016 e versioni successive locali) supporta la combinazione di più richieste in una singola chiamata al servizio tramite l'opzione di query $batch di OData. 

Per informazioni dettagliate e collegamenti a esempi di codice, vedere [Effettuare richieste di batch con l'API REST](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, è indispensabile conoscere e avere dimestichezza con quanto segue:

- [Informazioni sul servizio REST di SharePoint](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [Completare le operazioni di base usando gli endpoint REST di SharePoint](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a>Comandi REST

I comandi REST seguenti sono disponibili per l'uso con i modelli di analisi dei documenti Syntex:

- [Crea un modello](rest-createmodel-method.md): crea un modello e il tipo di contenuto associato.
- [GetByUniqueId](rest-getbyuniqueid-method.md): ottiene o aggiorna le informazioni su un modello di analisi dei documenti di SharePoint Syntex.
- [GetByTitle](rest-getbytitle-method.md): ottiene o aggiorna le informazioni su un modello di analisi dei documenti di SharePoint Syntex usando il titolo del modello.
- [Applica modello](rest-applymodel-method.md): applica (o sincronizza) un modello di analisi dei documenti sottoposto a training a una o più raccolte.
- [Ottieni informazioni su modelli e raccolte](rest-getmodelandlibraryinfo.md): ottiene informazioni su un modello e sulla raccolta in cui è stato applicato.
- [UpdateModelSettings](rest-updatemodelsettings-method.md): aggiorna le impostazioni dei modelli disponibili (etichetta di conservazione associata e descrizione del modello) per un modello di analisi dei documenti di SharePoint Syntex.
- [BatchDelete](rest-batchdelete-method.md): rimuove un modello di analisi dei documenti applicato da una o più raccolte.
- [Crea una richiesta di classificazione](rest-createclassificationrequest.md): crea una richiesta per classificare uno o più file specificati usando il modello applicato.

## <a name="scenarios"></a>Scenari

Si noti che gli esempi di scenari seguenti non sono intuitivi dal nome del metodo. Per altre informazioni, vedere ciascun articolo.

Il metodo di creazione modello crea solo l'oggetto modello e il tipo di contenuto associato. Prima di poterlo applicare a una raccolta, è necessario eseguire il training del modello nel Centro contenuti.

Il metodo di applicazione del modello viene usato per configurare il modello nella raccolta di destinazione per classificare i documenti e, facoltativamente, estrarre informazioni aggiuntive. Questa API supporta anche l'applicazione in batch del modello a più raccolte.

Il metodo di rimozione del modello rimuove semplicemente il modello da una o più raccolte in cui è stato applicato in precedenza. Per eliminare il modello, è necessario prima di tutto rimuoverlo da tutte le raccolte in cui è stato applicato.


## <a name="see-also"></a>Vedere anche

[Panoramica sull’analisi dei documenti](../document-understanding-overview.md)

