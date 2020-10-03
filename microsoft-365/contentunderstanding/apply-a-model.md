---
title: Applicare un modello di analisi dei documenti a una raccolta documenti
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni su come applicare un modello pubblicato a una raccolta documenti di SharePoint
ms.openlocfilehash: 8b7d6cf21f422ba54933c2d3ac29b4b34171059e
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322154"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Applicare un modello di analisi dei documenti in Microsoft SharePoint Syntex.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Dopo aver pubblicato il modello di analisi dei documenti, è possibile applicarlo a una o più raccolte documenti di SharePoint nel tenant di Microsoft 365.

> [!NOTE]
> È possibile applicare il modello solo alle raccolte documenti a cui si ha accesso.


## <a name="apply-your-model-to-a-document-library"></a>Applicare il modello a una raccolta documenti.

Per applicare il modello a una raccolta documenti di SharePoint:

1. Nella home page del modello, nel riquadro **Applica modello alle raccolte**, selezionare **Pubblica modello**. In alternativa, è possibile selezionare **+Aggiungi raccolta** nella sezione **Raccolte con questo modello**. </br>

    ![Aggiungere un modello a una raccolta](../media/content-understanding/apply-to-library.png)</br>

2. È possibile selezionare il sito di SharePoint che contiene la raccolta a cui si vuole applicare il modello. Se il sito non viene visualizzato nell'elenco, usare la casella di ricerca per trovarlo.</br>

    ![Selezionare un sito](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > È necessario disporre delle autorizzazioni di *Gestione dell'elenco* o dei diritti di *modifica* per la raccolta documenti a cui si sta applicando il modello.</br>

3. Dopo aver selezionato il sito, selezionare la raccolta in cui si vuole applicare il modello. Nell'esempio selezionare la raccolta documenti *Documenti* dal sito *Rilevamento casi di Contoso*.</br>

    ![Selezionare una raccolta documenti](../media/content-understanding/select-doc-library.png)</br>

4. Poiché il modello è associato a un tipo di contenuto, quando viene applicato alla raccolta aggiungerà il tipo di contenuto e la relativa visualizzazione con le etichette estratte come colonne. Questa è la visualizzazione predefinita della raccolta per impostazione predefinita, ma è possibile scegliere facoltativamente di non impostarla come visualizzazione predefinita selezionando **Impostazioni avanzate** e deselezionando **Imposta questa nuova visualizzazione come predefinita**.</br>

    ![Visualizzazione della raccolta](../media/content-understanding/library-view.png)</br>

5. Selezionare **Aggiungi** per applicare il modello alla raccolta. 
6. Nella home page del modello, nella sezione **Raccolte con questo modello**, dovrebbe essere visualizzato l'URL del sito di SharePoint elencato.</br>

    ![Raccolta selezionata](../media/content-understanding/selected-library.png)</br>

7. Passare alla tua raccolta documenti e assicurarsi di essere nella visualizzazione raccolta documenti del modello. Se si seleziona il pulsante informazioni accanto al nome della raccolta documenti, viene visualizzato un messaggio che informa che il modello è stato applicato alla raccolta documenti.

    ![Visualizzazione delle informazioni](../media/content-understanding/info-du.png)</br> 


Dopo aver applicato il modello nella raccolta documenti, è possibile iniziare a caricare documenti nel sito e visualizzare i risultati.

Il modello identifica i file con tipo di contenuto associato al modello e li elenca nella visualizzazione. Se il modello è dotato di estrattori, nella visualizzazione verranno mostrate le colonne dei dati da estrarre da ogni file.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Applicare il modello ai file già presenti nella raccolta documenti

Anche se un modello applicato elabora tutti i file caricati nella raccolta documenti dopo l'applicazione, è possibile eseguire le operazioni seguenti per eseguire il modello sui file già esistenti nella raccolta documenti prima di applicare il modello:

1. Nella raccolta documenti selezionare i file che si vuole far elaborare dal modello.
2. Dopo aver selezionato i file, **Classifica ed estrai** verrà visualizzati nella barra multifunzione della raccolta documenti. Selezionare **Classifica ed estrai**.
3. I file selezionati verranno aggiunti alla coda per essere elaborati.

      ![Classificare ed estrarre](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)

[Creare un estrattore](create-an-extractor.md)

[Panoramica dell'analisi dei documenti](document-understanding-overview.md)

[Creare un modello di elaborazione moduli](create-a-form-processing-model.md)  
