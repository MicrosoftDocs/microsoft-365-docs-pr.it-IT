---
title: Differenza tra la comprensione dei documenti e i modelli di elaborazione dei moduli
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Descrive la differenza fondamentale tra i modelli di elaborazione dei documenti e dei moduli
ms.openlocfilehash: 268a2fa4a0381e5822c17e5df22566c931d37f3c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294749"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Differenza tra la comprensione dei documenti e i modelli di elaborazione dei moduli 

Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

La comprensione del contenuto in Project Cortex consente di identificare e classificare i documenti caricati nelle raccolte documenti di SharePoint, nonché di estrarre informazioni rilevanti da ogni file.  Ad esempio, quando i file vengono caricati in una raccolta documenti di SharePoint, tutti i file identificati come *ordini di acquisto* sono classificati come tali e quindi visualizzati in una visualizzazione raccolta documenti personalizzata. È inoltre possibile estrarre informazioni specifiche da ogni file, ad esempio numero di *ordine di acquisto* e *totale*, e visualizzarlo come colonna nella visualizzazione raccolta documenti. 

Content Understanding consente di creare *modelli* per identificare ed estrarre le informazioni necessarie. Si tratta di due tipi di modello che è possibile utilizzare:

- [Informazioni sui modelli di documento](document-understanding-overview.md)
- [Modelli di elaborazione dei moduli](form-processing-overview.md)

Anche se entrambi i modelli vengono in genere utilizzati per lo stesso scopo, le differenze principali elencate di seguito influiscono sulle altre che è possibile utilizzare.

## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Contenuto strutturato e non strutturato e semistrutturato

Utilizzare i modelli di conoscenza dei documenti per identificare ed estrarre dati da documenti non strutturati, ad esempio lettere o contratti, in cui le entità di testo che si desidera estrarre risiedono in frasi o aree specifiche del documento. Ad esempio, un documento non strutturato potrebbe essere una lettera di rinnovo del contratto che può essere scritta in modi diversi. Tuttavia, le informazioni esistono in modo coerente nel corpo di ogni documento di rinnovo del contratto, ad esempio la stringa di testo "data di inizio del servizio" seguita da una data effettiva.   

Utilizzare i modelli di elaborazione dei moduli per identificare i file ed estrarre dati da documenti strutturati o semistrutturati, ad esempio moduli o fatture. Tali documenti devono avere coppie chiave-valore chiare (ad esempio *Data: 10/1/2020*) * o dati tabella. Ad esempio, un buon candidato per l'elaborazione dei moduli è una richiesta di ordine di una società che i client devono fornire informazioni per campi specifici che si trovano nella stessa area del layout di documento, ad esempio *nome*, *numero di telefono*, *costo totale*e così via.  Un modulo fiscale è un buon esempio di un documento strutturato. 

## <a name="where-they-are-created"></a>La posizione in cui vengono creati

I modelli di comprensione dei documenti vengono creati e gestiti in un sito del centro di contenuto di SharePoint. 

> [!NOTE]
> È necessario disporre dell'accesso a un sito Centro contenuto per creare un modello di comprensione del documento o per applicarne uno a una raccolta documenti di SharePoint. 

I modelli di elaborazione dei moduli vengono creati in PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview), ma la creazione viene avviata direttamente da una raccolta documenti di SharePoint. La creazione di un modello di elaborazione del modulo deve essere abilitata nella raccolta documenti affinché un utente possa creare un modello di elaborazione dei moduli e un amministratore può eseguire tale operazione nelle impostazioni di amministrazione di Content Understanding. I modelli di elaborazione dei moduli utilizzano flussi di PowerAutomate per elaborare i file quando vengono caricati nella raccolta documenti.

Quando si crea un modello di conoscenza del documento, viene creato un nuovo [tipo di contenuto di SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) che viene salvato nella raccolta tipi di contenuto di SharePoint. In alternativa, è possibile utilizzare i tipi di contenuto esistenti per definire il modello, se necessario.

I modelli di elaborazione dei moduli vengono creati in PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview), ma la creazione viene avviata direttamente da una raccolta documenti di SharePoint. La creazione del modello di elaborazione dei moduli deve essere abilitata nella raccolta documenti per un utente per creare un modello di elaborazione del modulo. Oppure un amministratore può eseguire questa operazione nelle impostazioni di amministrazione del contenuto. I modelli di elaborazione dei moduli utilizzano flussi di PowerAutomate per elaborare i file quando vengono caricati nella raccolta documenti.

I modelli di elaborazione dei moduli creano inoltre nuovi [tipi di contenuto di SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)e vengono archiviati anche nella raccolta tipi di contenuto di SharePoint.

## <a name="where-they-can-be-applied"></a>Dove possono essere applicati

È possibile applicare i modelli di comprensione del documento alle raccolte documenti di SharePoint a cui si ha accesso. Utilizzare il centro contenuto per creare un modello di conoscenza del documento e applicarlo a diverse raccolte documenti. Il Centro contenuti fornisce un controllo più centrale per la modalità di utilizzo dei modelli di comprensione dei documenti e per l'applicazione. Nota queste informazioni devono essere riportate anche a un centro di contenuto.

I modelli di elaborazione dei moduli possono essere attualmente applicati solo alla raccolta documenti di SharePoint da cui sono stati creati. In questo modo gli utenti con licenza con accesso al sito potranno creare un modello di elaborazione dei moduli.

 ## <a name="see-also"></a>Vedere anche
[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Creare un classificatore](create-a-classifier.md)</br>
[Creare un estrattore](create-an-extractor.md)</br>
[Applicazione di un modello di comprensione del documento](apply-a-model.md)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</br>
