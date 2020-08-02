---
title: Panoramica delle informazioni sui documenti (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Ottenere una panoramica della comprensione del documento in Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537401"
---
# <a name="document-understanding-overview-preview"></a>Panoramica delle informazioni sui documenti (anteprima)
> [!Note] 
> La corteccia del progetto è attualmente in anteprima. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Informazioni sui documenti vengono utilizzati i modelli AI per automatizzare la classificazione dei file e l'estrazione delle informazioni. Funziona meglio con documenti non strutturati, come lettere o contratti. I documenti devono avere testo che può essere identificato in base a frasi o modelli. Il testo identificato può indicare sia il tipo di file che è (la classificazione) che quello che si desidera estrarre (gli estrattori).

I modelli di comprensione dei documenti vengono creati e gestiti in un tipo di sito di SharePoint denominato Content Center. Quando viene applicato a una raccolta documenti di SharePoint, il modello è associato a un tipo di contenuto che include colonne per archiviare le informazioni estratte. Il tipo di contenuto creato è archiviato nella raccolta tipi di contenuto di SharePoint. È inoltre possibile scegliere di utilizzare i tipi di contenuto esistenti per utilizzarne lo schema.

È possibile aggiungere *classificatori* ed *estrattori* al documento per comprendere i modelli per eseguire le operazioni seguenti: 

- I classificatori vengono utilizzati per identificare e classificare i documenti caricati nella raccolta documenti. Ad esempio, un classificatore può essere "addestrato" per identificare tutti i documenti di *rinnovo del contratto* caricati nella raccolta. Il tipo di contenuto relativo al rinnovo del contratto è definito dall'utente quando si crea il classificatore.

- Estrazioni estrarre informazioni da questi documenti. Ad esempio, per tutti i documenti di rinnovo del contratto identificati nella raccolta documenti, le colonne verranno visualizzate nella visualizzazione che mostrerà anche la *Data di inizio del servizio* e il *client* per ogni documento di rinnovo del contratto. 

È possibile utilizzare file di esempio per formare e testare i classificatori e gli estrattori nel modello. Nei file di esempio vengono forniti esempi del modello di elementi da cercare quando si tenta di identificare ed estrarre dati dai file. Ad esempio, è consigliabile formare i classificatori e gli estrattori del rinnovo del contratto con esempi di documenti di rinnovo del contratto che la società utilizza. È inoltre possibile utilizzare i file di esempio per testare l'efficacia del modello.

Dopo aver pubblicato il modello, utilizzare il centro contenuto per applicarlo a qualsiasi raccolta documenti di SharePoint a cui si ha accesso.  


## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)</br>
[Creare un estrattore](create-an-extractor.md)</br>
[Creare un centro contenuto](create-a-content-center.md) 
 [Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</br>
[Applicazione di un modello](apply-a-model.md)   
[Differenza tra una comprensione del documento e un modello di elaborazione dei moduli](difference-between-document-understanding-and-form-processing-model.md)  
[Panoramica dell'elaborazione dei moduli](form-processing-overview.md)




