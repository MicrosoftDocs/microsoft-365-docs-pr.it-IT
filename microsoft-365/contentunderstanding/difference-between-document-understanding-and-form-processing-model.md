---
title: Differenza tra i modelli di analisi dei documenti e dell’elaborazione dei moduli
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Descrive la differenza principale tra i modelli di analisi dei documenti e dell’elaborazione dei moduli
ms.openlocfilehash: c5d60753e84cb55dc088b79f90fe841b50da1836
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338596"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Differenza tra i modelli di analisi dei documenti e dell’elaborazione dei moduli 


La comprensione dei contenuti in Microsoft SharePoint Syntex consente di identificare e classificare i documenti caricati nelle raccolte documenti di SharePoint, nonché di estrarre informazioni rilevanti da ogni file.  Ad esempio, quando i file vengono caricati in una raccolta documenti di SharePoint, tutti i file identificati come *Ordini di acquisto* vengono classificati come tali e quindi mostrati in una visualizzazione raccolta documenti personalizzata. È inoltre possibile recuperare informazioni specifiche da ogni file, ad esempio *Numero ordine di acquisto* e *Totale*, e visualizzarlo come colonna nella visualizzazione della raccolta documenti. 

La comprensione dei contenuti permette di creare *modelli* per identificare ed estrarre le informazioni di cui si ha bisogna. I modelli consentono di risolvere i problemi aziendali relativa alla ricerca, i processi aziendali, la conformità e altro.

Sono disponibili due tipi di modello che è possibile usare:

- [Modelli di analisi dei documenti](document-understanding-overview.md)
- [Modelli di elaborazione dei moduli](form-processing-overview.md)

Anche se vengono usati in genere per lo stesso scopo, le differenze principali elencate di seguito influiscono sulle opzioni che è possibile usare.

> [!NOTE]
> Per altri esempi sugli scenari dell’elaborazione dei moduli e sull’analisi dei documenti, vedere[Adozione di SharePoint Syntex: guida introduttiva](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Contenuti strutturati contro non strutturati e semi-strutturati

Usare i modelli di analisi dei documenti per identificare ed estrarre dati da documenti non strutturati, ad esempio lettere o contratti, in cui le entità di testo che si vogliono estrarre risiedono nelle frasi o in specifiche aree del documento. Ad esempio, un documento non strutturato potrebbe essere una lettera di rinnovo contrattuale che può essere scritta in modi diversi. Tuttavia, le informazioni esistono in modo coerente nel corpo di ogni documento di rinnovo del contratto, come la stringa di testo *Data di inizio servizio* seguita da una data effettiva.   

Usare i modelli di elaborazione moduli per identificare i file ed estrarre dati da documenti strutturati o semistrutturati, ad esempio moduli o fatture. I modelli di elaborazione dei moduli vengono formati per comprendere il layout del modulo dai documenti di esempio e apprendere a cercare i dati che è necessario estrarre da posizioni simili, poiché i moduli hanno un layout più strutturato in cui le entità si trovano nella stessa posizione (ad esempio, un numero di previdenza sociale in un modulo fiscale). 

> [!NOTE]
> È necessario avere accesso a un sito del centro contenuti per creare un modello di comprensione del documento o per applicarne uno a una raccolta documenti di SharePoint. 


## <a name="where-they-are-created"></a>Sono vengono creati

I modelli di analisi dei documenti vengono creati e gestiti in un sito del centro contenuti di SharePoint. 

> [!NOTE]
> Per altre informazioni sui documenti di input, vedere [Requisiti e limitazioni dei modelli di elaborazione dei moduli](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

I modelli di elaborazione moduli vengono creati in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), ma la creazione viene avviata direttamente da una raccolta documenti di SharePoint. È necessario abilitare la creazione del modello di elaborazione del modulo nella raccolta documenti, per consentire a un utente di creare un modello di elaborazione del modulo e un amministratore può farlo nelle impostazioni di amministrazione della comprensione dei contenuti. I modelli di elaborazione dei moduli utilizzano i flussi PowerAutomate per elaborare i file quando vengono caricati nella raccolta documenti.

Durante la creazione di un modello di informazioni sulla creazione di un documento, è possibile creare un nuovo [tipo di contenuto SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) salvato nella raccolta Tipi di contenuto di SharePoint. In alternativa, è possibile usare tipi di contenuto esistenti per definire il modello, se necessario.

I modelli di elaborazione moduli vengono creati in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), ma la creazione viene avviata direttamente da una raccolta documenti di SharePoint. È necessario abilitare la creazione del modello di elaborazione dei moduli nella raccolta documenti affinché un utente possa creare un modello di elaborazione dei moduli. In alternativa, un amministratore può farlo nelle impostazioni di amministrazione della comprensione dei contenuti. I modelli di elaborazione dei moduli utilizzano i flussi PowerAutomate per elaborare i file quando vengono caricati nella raccolta documenti.

È anche possibile creare nuovi [Tipi di contenuto SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) e sono anche archiviati nella raccolta Tipi di contenuto di SharePoint.

## <a name="where-they-can-be-applied"></a>Quando è possibile applicarli

È possibile applicare i modelli di analisi dei documenti alle raccolte documenti di SharePoint a cui si ha accesso. Usare il centro contenuti per creare un modello di informazioni sul documento e applicarlo a diverse raccolte documenti. Il centro contenuti offre un controllo più centralizzato su come vengono utilizzati i modelli di analisi dei documenti e dove vengono applicati. Da tenere presente che queste informazioni devono essere riportate in un centro contenuti.

I modelli di elaborazione dei moduli possono essere applicati solo alla raccolta documenti di SharePoint da cui sono stati creati. Questo consente agli utenti con licenza con accesso al sito di poter creare un modello di elaborazione dei moduli. Tenere presente che l'amministratore deve abilitare l'elaborazione dei moduli in una raccolta documenti di SharePoint in modo che sia disponibile per gli utenti con licenza.

 ## <a name="see-also"></a>Vedere anche
[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Panoramica sull’analisi dei documenti](document-understanding-overview.md)

[Panoramica sull'elaborazione dei moduli](form-processing-overview.md)

[Introduzione a SharePoint Syntex](index.md)
