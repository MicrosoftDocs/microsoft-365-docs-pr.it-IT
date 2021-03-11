---
title: Differenza tra i modelli di analisi dei documenti e dell’elaborazione dei moduli
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Descrive la differenza principale tra i modelli di analisi dei documenti e dell’elaborazione dei moduli
ms.openlocfilehash: 555dfa7d76335a3b943e860e5f41ed64c9d3e874
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596981"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Differenza tra i modelli di analisi dei documenti e dell’elaborazione dei moduli 


La comprensione dei contenuti in Microsoft SharePoint Syntex consente di identificare e classificare i documenti caricati nelle raccolte documenti di SharePoint, nonché di estrarre informazioni pertinenti da ogni file.  Ad esempio, quando i file vengono caricati in una raccolta documenti di SharePoint, tutti i file identificati come *Ordini di acquisto* vengono classificati come tali e quindi mostrati in una visualizzazione raccolta documenti personalizzata. È inoltre possibile recuperare informazioni specifiche da ogni file, ad esempio *Numero ordine di acquisto* e *Totale*, e visualizzarlo come colonna nella visualizzazione della raccolta documenti. 

La comprensione dei contenuti permette di creare *modelli* per identificare ed estrarre le informazioni di cui si ha bisogna. I modelli consentono di risolvere i problemi aziendali relativa alla ricerca, i processi aziendali, la conformità e altro.

Sono disponibili due tipi di modello che è possibile usare:

- [Modelli di analisi dei documenti](document-understanding-overview.md)
- [Modelli di elaborazione dei moduli](form-processing-overview.md)

Anche se vengono usati in genere per lo stesso scopo, le differenze principali elencate di seguito influiscono sulle opzioni che è possibile usare.

> [!NOTE]
> Per altri esempi sugli scenari dell’elaborazione dei moduli e sull’analisi dei documenti, vedere[Adozione di SharePoint Syntex: guida introduttiva](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Contenuti strutturati contro non strutturati e semi-strutturati

Usare i modelli di analisi dei documenti per identificare ed estrarre dati da documenti non strutturati, ad esempio lettere o contratti, in cui le entità di testo che si vogliono estrarre sono presenti in frasi o specifiche aree del documento. Ad esempio, un documento non strutturato potrebbe essere una lettera di rinnovo contrattuale che può essere scritta in modi diversi. Tuttavia, le informazioni esistono in modo coerente nel corpo di ogni documento di rinnovo del contratto, come la stringa di testo *Data di inizio servizio* seguita da una data effettiva.

Usare i modelli di elaborazione moduli per identificare i file ed estrarre dati da documenti strutturati o semistrutturati, ad esempio moduli o fatture. I modelli di elaborazione dei moduli sono strutturati in modo da comprendere il layout del modulo da documenti di esempio e imparare a cercare i dati che è necessario estrarre da posizioni simili. I moduli hanno in genere un layout più strutturato in cui le entità si trovano nella stessa posizione, ad esempio un numero di previdenza sociale in un modulo fiscale.

> [!NOTE]
> È necessario avere accesso a un sito del centro contenuti per creare un modello di comprensione del documento o per applicarne uno a una raccolta documenti di SharePoint. 


## <a name="where-models-are-created"></a>Dove vengono creati i modelli

I modelli di analisi dei documenti vengono creati e gestiti in un sito del centro contenuti di SharePoint. 

> [!NOTE]
> Per altre informazioni sui documenti di input, vedere [Requisiti e limitazioni dei modelli di elaborazione dei moduli](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

I modelli di elaborazione dei moduli vengono creati in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), ma la creazione viene avviata direttamente da una raccolta documenti di SharePoint. È necessario abilitare la creazione dei modelli di elaborazione dei moduli nella raccolta documenti per consentire a un utente di creare un modello di elaborazione dei moduli. Gli amministratori possono abilitare la creazione dei modelli di elaborazione dei moduli nelle impostazioni di amministrazione della comprensione dei contenuti. I modelli di elaborazione dei moduli usano i flussi PowerAutomate per elaborare i file quando vengono caricati nella raccolta documenti.

Durante la creazione di un modello di informazioni sulla creazione di un documento, è possibile creare un nuovo [tipo di contenuto SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) salvato nella raccolta Tipi di contenuto di SharePoint. In alternativa, è possibile usare tipi di contenuto esistenti per definire il modello, se necessario.

È anche possibile creare nuovi [Tipi di contenuto SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) e sono anche archiviati nella raccolta Tipi di contenuto di SharePoint.

## <a name="where-they-can-be-applied"></a>Quando è possibile applicarli

È possibile applicare i modelli di analisi dei documenti alle raccolte documenti di SharePoint a cui si ha accesso. Usare il centro contenuti per creare un modello di informazioni sul documento e applicarlo a diverse raccolte documenti. Il centro contenuti offre un controllo più centralizzato su come vengono utilizzati i modelli di analisi dei documenti e dove vengono applicati. Da tenere presente che queste informazioni devono essere riportate in un centro contenuti.

I modelli di elaborazione dei moduli possono essere applicati solo alla raccolta documenti di SharePoint da cui sono stati creati. Questo consente agli utenti con licenza con accesso al sito di creare un modello di elaborazione dei moduli. Tenere presente che un amministratore deve abilitare l'elaborazione dei moduli in una raccolta documenti di SharePoint in modo che sia disponibile per gli utenti con licenza.

## <a name="comparison-of-forms-processing-and-document-understanding"></a>Confronto tra l'elaborazione dei moduli e l'analisi dei documenti

Usare la tabella seguente per comprendere quando usare l'elaborazione dei moduli e quando usare l'analisi dei documenti:

| Funzionalità | Elaborazione dei moduli | Analisi dei documenti |
| ------- | ------- | ------- |
| Tipo di modello: quando usare ciascuno | Usato per i formati file semistrutturati, ad esempio i documenti di Office in cui sono presenti differenze nel layout ma comunque informazioni simili da estrarre. | Usato per formati di file non strutturati, ad esempio PDF per i contenuti dei moduli come fatture o ordini di acquisto in cui il layout e la formattazione sono simili. |
| Creazione di modelli | I modelli creati in AI Builder con accesso semplice alla raccolta documenti di SharePoint.| Modello creato in un'interfaccia nativa incorporata nel Centro contenuti di SharePoint.|
| Tipi di classificazione| Classificatore impostabile in cui viene usato l'insegnamento automatico per fornire indicazioni al sistema sui dati da estrarre.| Classificatore sottoponibile a training con estrattori facoltativi che usano l'insegnamento automatico per assegnare la posizione del documento dal quale estrarre i dati.|
| Posizioni | Limitato a una singola raccolta documenti, a meno che non si usi Power Platform per il recupero da CDS.| Può essere applicato a più raccolte.|
| Tipi di file supportati| Formazione su formati PDF, JPG e PNG, un totale di 50 MB e 500 pagine.| Formazione su 5-10 file PDF, Office o di posta elettronica, inclusi gli esempi negativi.<br>I file di Office sono troncati a 64.000 caratteri. I file analizzati con OCR hanno un limite di 20 pagine.|
| Integrazione con i metadati gestiti | No | Sì, tramite impostazione delle colonne della raccolta documenti prima di eseguire il training sul modello.|
| Integrazione delle funzionalità di conformità quando Microsoft Information Protection è abilitato | Impostare le etichette di conservazione.<br>L'impostazione delle etichette di riservatezza sarà disponibile a breve. | Impostare le etichette di conservazione.<br>L'impostazione delle etichette di riservatezza sarà disponibile a breve. |
| Aree geografiche supportate| L'elaborazione dei moduli si basa su Power Platform. Per informazioni sulla disponibilità globale di Power Platform e AI Builder, vedere [Disponibilità di Power Platform](https://dynamics.microsoft.com/geographic-availability/). | Disponibile in tutte le aree geografiche.|
| Costo transazionale | Usa crediti di AI Builder.<br>I crediti possono essere acquistati in batch da 1 milione.<br>Con l'acquisto di più di 300 licenze Syntex di SharePoint, viene incluso 1 milione di crediti.<br>1 milione di crediti consentirà l'elaborazione di 2000 pagine di file.| N/D |
| Capacità | Predisposto per l'ambiente di servizio dati comune predefinito.| Nessuna limitazione delle capacità.|
| Lingue supportate| Inglese <br>Disponibili nel 2021: spagnolo, tedesco, francese, italiano| I modelli funzionano in tutte le lingue con alfabeto latino. Oltre all'inglese: tedesco, svedese, francese, spagnolo, italiano e portoghese.|

## <a name="see-also"></a>Vedere anche
[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Panoramica sull’analisi dei documenti](document-understanding-overview.md)

[Panoramica sull'elaborazione dei moduli](form-processing-overview.md)

[Introduzione a SharePoint Syntex](index.md)
