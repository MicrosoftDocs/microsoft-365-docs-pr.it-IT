---
title: Panoramica sull'analisi dei documenti
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Ottenere una panoramica dell'analisi dei documenti in Microsoft SharePoint Syntex.
ms.openlocfilehash: 5dd44a119dff6f5d194861c381fa28f76a6f0da7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701108"
---
# <a name="document-understanding-overview"></a>Panoramica sull'analisi dei documenti


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

L’analisi dei documenti utilizza modelli di intelligenza artificiale (AI) per automatizzare la classificazione dei file e l'estrazione delle informazioni. Funziona meglio con documenti non strutturati, ad esempio lettere o contratti. Questi documenti devono contenere un testo che possa essere identificato in base a frasi o schemi. Il testo identificato designa sia il tipo di file (la classificazione) che l'elemento che si vuole estrarre (l’estrattore).

> [!NOTE]
> Per altri esempi sull’analisi dei documenti, vedere[Adozione di SharePoint Syntex: guida introduttiva](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).

I modelli di analisi dei documenti vengono creati e gestiti in un tipo di sito di SharePoint denominato *centro contenuti*. Se applicato a una raccolta documenti di SharePoint, il modello è associato a un tipo di contenuto con colonne in cui archiviare le informazioni estratte. Il tipo di contenuto creato è archiviato nella raccolta tipi di contenuto di SharePoint. È anche possibile scegliere di usare i tipi di contenuto esistenti per usare il loro schema.

> [!NOTE]
> I tipi di contenuto in sola lettura o bloccati non possono essere aggiornati, quindi non possono essere usati in un modello.

Aggiungere *classificatori* ed *estrattori* ai modelli di analisi dei documento per eseguire le seguenti operazioni: 

- I classificatori vengono usati per identificare e classificare i documenti caricati nella raccolta documenti. Ad esempio, un classificatore può essere "addestrato" per identificare tutto i documenti di *rinnovo del contratto* caricati nella raccolta. Il tipo di contenuto per il rinnovo del contratto viene definito dall'utente quando si crea il classificatore.

- Gli estrattori estraggono informazioni da questi documenti. Ad esempio, per tutti i documenti di rinnovo del contratto identificati nella raccolta documenti, nella visualizzazione ci sono delle colonne che mostrano anche la *Data di inizio servizio* e il *Cliente* per ogni documento di rinnovo del contratto. 

È possibile usare i file di esempio per formare e testare i classificatori e gli estrattori nel modello. I file di esempio forniscono esempi di modelli su cosa cercare quando si prova a identificare ed estrarre dati da file. Ad esempio, è necessario formare i classificatori e gli estrattori del rinnovo del contratto con esempi di documenti di rinnovo del contratto con cui lavora l’azienda. È anche possibile usare i file di esempio per testare l'efficacia del modello.

> [!NOTE]
> Se si usa la tecnologia di riconoscimento ottico dei caratteri (OCR) per digitalizzare i documenti, Syntex ha un limite di 15 pagine per il training del modello.

Dopo aver pubblicato il modello, usare il centro contenuto per applicarlo a qualsiasi raccolta documenti di SharePoint a cui si ha accesso.  

## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)

[Creare un estrattore](create-an-extractor.md)

[Creare un centro contenuti](create-a-content-center.md)

[Creare un modello di elaborazione moduli](create-a-form-processing-model.md)

[Applicare un modello](apply-a-model.md)   

[Differenza tra un modello di analisi dei documenti e dell’elaborazione dei moduli](difference-between-document-understanding-and-form-processing-model.md)
  
[Panoramica sull'elaborazione dei moduli](form-processing-overview.md)
