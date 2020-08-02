---
title: Differenza tra la comprensione dei documenti e i modelli di elaborazione dei moduli (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Descrive la differenza fondamentale tra la comprensione dei documenti e i modelli di elaborazione dei moduli.
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537436"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>Differenza tra la comprensione dei documenti e i modelli di elaborazione dei moduli (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

La comprensione del contenuto in Project Cortex consente di identificare e classificare i documenti caricati nelle raccolte documenti di SharePoint, nonché di estrarre informazioni rilevanti da ogni file.  Ad esempio, quando i file vengono caricati in una raccolta documenti di SharePoint, tutti i file identificati come *ordini di acquisto* vengono classificati come tali e visualizzati in una visualizzazione raccolta documenti personalizzata in cui vengono visualizzati. È inoltre possibile estrarre informazioni specifiche da ogni file, ad esempio numero di *ordine di acquisto* e *totale*, e visualizzarle in una colonna della visualizzazione raccolta documenti. 


Content Understanding consente di creare *modelli* per identificare ed estrarre le informazioni necessarie.  Sono disponibili due tipi di modelli che è possibile utilizzare:

- [Informazioni sui modelli di documento](document-understanding-overview.md)
- [Modelli di elaborazione dei moduli](form-processing-overview.md)

Sebbene entrambi i modelli vengano utilizzati in genere per lo stesso scopo, sono presenti differenze chiave che interessano quelle che è possibile scegliere di utilizzare.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Contenuto strutturato e non strutturato e semistrutturato

Utilizzare i modelli di conoscenza dei documenti per identificare ed estrarre dati da documenti non strutturati, ad esempio lettere o contratti, in cui le entità di testo che si desidera estrarre risiedono in frasi o aree specifiche del documento. Ad esempio, un documento non strutturato potrebbe essere una lettera di rinnovo del contratto che può essere scritta in modi diversi. Tuttavia, esistono informazioni che si verificano in modo coerente nel corpo di ogni documento di rinnovo del contratto, ad esempio la stringa di testo "data di inizio del servizio" seguita da una data effettiva.   

Utilizzare i modelli di elaborazione dei moduli per identificare i file ed estrarre i dati da documenti strutturati o semistrutturati, ad esempio maschere o fatture, in cui sono presenti coppie chiave-valore chiare (come *Data: 10/1/2020*) * o dati tabella. Ad esempio, un buon candidato per l'elaborazione dei moduli potrebbe essere un modulo di richiesta di ordine della società in cui i client devono fornire le proprie informazioni per i campi specifici che si trovano nella stessa area del layout di documento, ad esempio *nome*, *numero di telefono*, *costo totale*e così via.  Un modulo fiscale è un buon esempio di un documento strutturato. 

## <a name="where-they-are-created"></a>La posizione in cui vengono creati

I modelli di comprensione dei documenti vengono creati e gestiti in un sito del centro di contenuto di SharePoint. È necessario disporre dell'accesso a un sito Centro contenuto per creare un modello di comprensione del documento o per applicarne uno a una raccolta documenti di SharePoint. 

Quando si crea un modello di conoscenza del documento, viene creato un nuovo [tipo di contenuto di SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) che viene salvato nella raccolta tipi di contenuto di SharePoint. Se necessario, è possibile utilizzare i tipi di contenuto esistenti per definire il modello.

I modelli di elaborazione dei moduli vengono creati in PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview), ma la creazione viene avviata direttamente da una raccolta documenti di SharePoint. La creazione di un modello di elaborazione del modulo deve essere abilitata nella raccolta documenti affinché un utente possa creare un modello di elaborazione dei moduli e un amministratore può eseguire tale operazione nelle impostazioni di amministrazione di Content Understanding. I modelli di elaborazione dei moduli utilizzano flussi di PowerAutomate per elaborare i file quando vengono caricati nella raccolta documenti.

I modelli di elaborazione dei moduli creano inoltre nuovi [tipi di contenuto di SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), che sono archiviati anche nella raccolta tipi di contenuto di SharePoint.

## <a name="where-they-can-be-applied"></a>Dove possono essere applicati

I modelli di conoscenza del documento possono essere applicati a diverse raccolte documenti di SharePoint a cui è possibile accedere. È possibile utilizzare il centro contenuto per creare non solo un modello di conoscenza del documento, ma anche per applicarlo a raccolte documenti diverse. Il centro contenuto fornisce un controllo più centralizzato del modo in cui vengono utilizzati i modelli di comprensione dei documenti e in cui vengono applicati, poiché queste informazioni devono essere riportate a un centro di contenuto.

I modelli di elaborazione dei moduli possono essere attualmente applicati solo alla raccolta documenti di SharePoint da cui sono stati creati. Ciò consente a qualsiasi utente con licenza che abbia accesso al sito di creare un modello di elaborazione dei moduli.




 ## <a name="see-also"></a>Vedere anche
[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Creare un classificatore](create-a-classifier.md)</br>
[Creare un estrattore](create-an-extractor.md)</br>
[Applicazione di un modello di comprensione del documento](apply-a-model.md)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</br>



  
  



