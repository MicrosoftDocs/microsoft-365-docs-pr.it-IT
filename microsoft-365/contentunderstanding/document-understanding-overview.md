---
title: Panoramica sull'analisi dei documenti
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Ottenere una panoramica dell'analisi dei documenti in Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683824"
---
# <a name="document-understanding-overview"></a>Panoramica sull'analisi dei documenti


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

L’analisi dei documenti utilizza modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni. Funziona meglio con documenti non strutturati, ad esempio lettere o contratti. Questi documenti devono contenere un testo che possa essere identificato in base a frasi o schemi. Il testo identificato designa sia il tipo di file (la classificazione) che l'elemento che si vuole estrarre (l’estrattore).

> [!NOTE]
> Per altri esempi sull’analisi dei documenti, vedere[Adozione di SharePoint Syntex: guida introduttiva](./adoption-getstarted.md).

I modelli di analisi dei documenti vengono creati e gestiti in un tipo di sito di SharePoint denominato *centro contenuti*. Se applicato a una raccolta documenti di SharePoint, il modello è associato a un tipo di contenuto con colonne in cui archiviare le informazioni estratte. Il tipo di contenuto creato è archiviato nella raccolta tipi di contenuto di SharePoint. È anche possibile scegliere di usare i tipi di contenuto esistenti per usare il loro schema.

> [!NOTE]
> I tipi di contenuto in sola lettura o sigillati non possono essere aggiornati, quindi non possono essere usati in un modello.

Aggiungere *classificatori* ed *estrattori* ai modelli di analisi dei documento per eseguire le seguenti operazioni: 

- I classificatori vengono usati per identificare e classificare i documenti caricati nella raccolta documenti. Ad esempio, un classificatore può essere "addestrato" per identificare tutto i documenti di *rinnovo del contratto* caricati nella raccolta. Il tipo di contenuto per il rinnovo del contratto viene definito dall'utente quando si crea il classificatore.

- Gli estrattori estraggono informazioni da questi documenti. Ad esempio, per tutti i documenti di rinnovo del contratto identificati nella raccolta documenti, nella visualizzazione ci sono delle colonne che mostrano anche la *Data di inizio servizio* e il *Cliente* per ogni documento di rinnovo del contratto. 

È possibile usare i file di esempio per formare e testare i classificatori e gli estrattori nel modello. I file di esempio forniscono esempi di modelli su cosa cercare quando si prova a identificare ed estrarre dati da file. Ad esempio, è necessario formare i classificatori e gli estrattori del rinnovo del contratto con esempi di documenti di rinnovo del contratto con cui lavora l’azienda. È anche possibile usare i file di esempio per testare l'efficacia del modello.

Dopo aver pubblicato il modello, usare il centro contenuto per applicarlo a qualsiasi raccolta documenti di SharePoint a cui si ha accesso.  

## <a name="file-limitations"></a>Limitazioni relative ai file

I modelli di analisi dei documenti usano la tecnologia di riconoscimento ottico dei caratteri (OCR) per analizzare file PDF, immagini e file TIFF, sia quando si esegue il training di un modello con file di esempio, sia quando si esegue il modello sui file di una raccolta documenti.

Notare le differenze seguenti per quanto riguarda i file basati su testo di Microsoft Office e i file digitalizzati con OCR (PDF, immagini o TIFF):

- File di Office: troncati a 64.000 caratteri (durante il training e se eseguito sui file in una raccolta documenti).

- File digitalizzati con OCR: è previsto un limite di 20 pagine.  

### <a name="requirements"></a>Requisiti

L'elaborazione OCR funziona meglio su documenti che soddisfano i requisiti seguenti:

- Formato JPG, PNG o PDF (testo o digitalizzato). I PDF con testo incorporato sono migliori, perché non si verificheranno errori nell'estrazione e nella posizione dei caratteri.

- Se i PDF sono protetti da password, è necessario rimuovere il blocco prima di inviarli.

- Le dimensioni combinate dei file di documenti usati per il training non devono superare i 50 MB per ogni raccolta e i documenti PDF non devono avere più di 500 pagine.

- Per le immagini, le dimensioni devono essere comprese tra 50 × 50 e 10.000 × 10.000 pixel.
   > [!NOTE]
   > Le immagini con dimensioni molto ampie o particolari, ad esempio le planimetrie dei piani, possono risultare troncate nel processo OCR e perdere l'accuratezza.
 
- Per i file PDF, le dimensioni devono essere al massimo di 43 x 43 cm, corrispondente al formato carta legale o A3 o dimensioni inferiori.

- Se si esegue la digitalizzazione da documenti cartacei, le scansioni devono essere immagini di alta qualità.

- Occorre usare l'alfabeto latino (caratteri inglesi).

> [!NOTE]
> AI Builder al momento non supporta i tipi di dati di input per l'elaborazione di moduli seguenti:<br>- Caselle di controllo o pulsanti di opzione<br>- Firme<br>- PDF compilabili

### <a name="supported-file-types"></a>Tipi di file supportati

I modelli di analisi dei documenti supportano i tipi di file seguenti:

- doc
- docx
- eml
- heic
- heif
- htm
- html
- jpeg
- jpg
- markdown
- md
- msg
- pdf
- png
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx



## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)

[Creare un estrattore](create-an-extractor.md)

[Creare un centro contenuti](create-a-content-center.md)

[Creare un modello di elaborazione moduli](create-a-form-processing-model.md)

[Applicare un modello](apply-a-model.md)   

[Differenza tra un modello di analisi dei documenti e dell’elaborazione dei moduli](difference-between-document-understanding-and-form-processing-model.md)
  
[Panoramica sull'elaborazione dei moduli](form-processing-overview.md)

[Modalità di accessibilità di SharePoint Syntex](accessibility-mode.md)