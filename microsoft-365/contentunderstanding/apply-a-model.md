---
title: Applicare un modello di comprensione del documento a una raccolta documenti (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come applicare un modello pubblicato a una raccolta documenti di SharePoint.
ms.openlocfilehash: 8a4931f4b7a936caeb99d7f8c07deefdac62919b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950249"
---
# <a name="apply-a-document-understanding-model-preview"></a>Applicazione di un modello di comprensione del documento (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Dopo aver pubblicato il modello di conoscenza del documento, è possibile applicarlo a una raccolta documenti di SharePoint nel tenant Microsoft 365.

> [!Note]
> Sarà possibile applicare il modello solo alle raccolte documenti a cui è possibile accedere.


## <a name="apply-your-model-to-a-document-library"></a>Applicare il modello a una raccolta documenti.

Per applicare il modello a una raccolta documenti di SharePoint:

1. Nella Home page del modello fare clic su **Pubblica modello**nella sezione **Applica modello a raccolte** . In alternativa, è possibile selezionare  **+ Aggiungi raccolta** nella sezione **raccolte con questo modello** . </br>

    ![Aggiungere un modello alla raccolta](../media/content-understanding/apply-to-library.png)</br>

2. È quindi possibile selezionare il sito di SharePoint contenente la raccolta documenti a cui si desidera applicare il modello. Se il sito non viene visualizzato nell'elenco, utilizzare la casella di ricerca per individuarlo.</br>

    ![Selezionare un sito](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > È necessario disporre delle autorizzazioni *Gestisci elenco* o *modifica* diritti per la raccolta documenti a cui si sta applicando il modello.</br>

3. Dopo aver selezionato il sito, è necessario selezionare la raccolta documenti in cui si desidera applicare il modello. In questo esempio viene selezionata la raccolta *documenti* del documento dal sito di *Verifica dei casi di Contoso* .</br>

    ![Selezionare una raccolta documenti](../media/content-understanding/select-doc-library.png)</br>

4. Poiché il modello è associato a un tipo di contenuto, quando lo si applica alla raccolta, viene creata una visualizzazione per il tipo di contenuto con le etichette estratte come colonne. Questa visualizzazione sarà la visualizzazione predefinita della raccolta per impostazione predefinita, ma è possibile scegliere di non averlo come visualizzazione predefinita selezionando **Impostazioni avanzate** e deselezionando **imposta questa nuova visualizzazione come predefinita**.</br>

    ![Visualizzazione libreria](../media/content-understanding/library-view.png)</br>

5. Selezionare **Aggiungi** per applicare il modello alla raccolta. 
6. Nella sezione **raccolte con questo modello** della Home page del modello verrà visualizzato l'URL del sito di SharePoint elencato.</br>

    ![Visualizzazione libreria](../media/content-understanding/selected-library.png)</br>

7. Passare alla raccolta documenti e verificare di trovarsi nella visualizzazione della raccolta documenti del modello. Se si seleziona il pulsante informazioni accanto al nome della raccolta documenti, verrà visualizzato un messaggio che indica che il modello è stato applicato alla raccolta documenti.

    ![Visualizzazione libreria](../media/content-understanding/info-du.png)</br> 


Dopo aver applicato il modello alla raccolta documenti, è possibile iniziare a caricare i documenti nel sito e visualizzare i risultati.

Il modello identificherà tutti i file con il tipo di contenuto associato del modello e li visualizzerà nella visualizzazione. Se nel modello sono presenti estrattori, la visualizzazione visualizzerà le colonne per i dati da estrarre da ogni file.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Applicazione del modello ai file già presenti nella raccolta documenti

Mentre un modello applicato elaborerà tutti i file caricati nella raccolta documenti dopo l'applicazione, è anche possibile eseguire le operazioni seguenti per l'esecuzione del modello nei file già esistenti nella raccolta documenti prima del modello applicato:

1. Nella raccolta documenti selezionare i file che si desidera vengano elaborati dal modello.
2. Dopo aver selezionato i file, **classificare ed estrarre** verranno visualizzati nella barra multifunzione della raccolta documenti. Selezionare **classifica ed Estrai**.
3. I file selezionati verranno aggiunti alla coda per l'elaborazione.

      ![Classificare ed estrarre](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)</br>
[Creare un estrattore](create-an-extractor.md)</br>
[Panoramica della comprensione del documento](document-understanding-overview.md)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)  




