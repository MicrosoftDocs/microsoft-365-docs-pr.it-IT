---
title: Applicare un modello di comprensione del documento a una raccolta documenti
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
description: Informazioni su come applicare un modello pubblicato a una raccolta documenti di SharePoint
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295491"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Applicazione di un modello di comprensione del documento in Microsoft SharePoint Syntex

Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Dopo aver pubblicato il modello di conoscenza del documento, è possibile applicarlo a una raccolta documenti di SharePoint nel tenant Microsoft 365.

> [!NOTE]
> È possibile applicare il modello solo alle raccolte documenti a cui è possibile accedere.


## <a name="apply-your-model-to-a-document-library"></a>Applicare il modello a una raccolta documenti.

Per applicare il modello a una raccolta documenti di SharePoint:

1. Nella Home page del modello fare clic su **Pubblica modello**nella sezione **Applica modello a raccolte** . In alternativa, è possibile selezionare  **+ Aggiungi raccolta** nella sezione **raccolte con questo modello** . </br>

    ![Aggiungere un modello alla raccolta](../media/content-understanding/apply-to-library.png)</br>

2. Selezionare il sito di SharePoint che contiene la raccolta documenti a cui si desidera applicare il modello. Se il sito non viene visualizzato nell'elenco, utilizzare la casella di ricerca per individuarlo.</br>

    ![Selezionare un sito](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > È necessario disporre delle autorizzazioni *Gestisci elenco* o *modifica* diritti per la raccolta documenti a cui si sta applicando il modello.</br>

3. Dopo aver selezionato il sito, selezionare la raccolta documenti in cui si desidera applicare il modello. Nell'esempio, selezionare la raccolta *documenti* del documento dal sito di *Verifica dei casi di Contoso* .</br>

    ![Selezionare una raccolta documenti](../media/content-understanding/select-doc-library.png)</br>

4. Poiché il modello è associato a un tipo di contenuto, quando viene applicato alla raccolta viene creata una visualizzazione per il tipo di contenuto con le etichette estratte come colonne. Questa visualizzazione è la visualizzazione predefinita della raccolta per impostazione predefinita, ma è possibile scegliere di non averlo come visualizzazione predefinita selezionando **Impostazioni avanzate** e deselezionando **imposta questa nuova visualizzazione come predefinita**.</br>

    ![Visualizzazione libreria](../media/content-understanding/library-view.png)</br>

5. Selezionare **Aggiungi** per applicare il modello alla raccolta. 
6. Nella Home page del modello, nella sezione **raccolte con questo modello** , dovrebbe essere visualizzato l'URL del sito di SharePoint elencato.</br>

    ![Raccolta selezionata](../media/content-understanding/selected-library.png)</br>

7. Passare alla raccolta documenti e verificare di trovarsi nella visualizzazione della raccolta documenti del modello. Si noti che se si seleziona il pulsante informazioni accanto al nome della raccolta documenti, un messaggio noterà che il modello è stato applicato alla raccolta documenti.

    ![Visualizzazione delle informazioni](../media/content-understanding/info-du.png)</br> 


Dopo aver applicato il modello alla raccolta documenti, è possibile iniziare a caricare i documenti nel sito e visualizzare i risultati.

Il modello identifica i file con il tipo di contenuto associato del modello e li elenca nella visualizzazione. Se nel modello sono presenti estrattori, la visualizzazione Visualizza le colonne per i dati che si stanno estraendo da ogni file.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Applicazione del modello ai file già presenti nella raccolta documenti

Mentre un modello applicato elabora tutti i file caricati nella raccolta documenti dopo l'applicazione, è inoltre possibile eseguire le operazioni seguenti per l'esecuzione del modello nei file già esistenti nella raccolta documenti prima del modello applicato:

1. Nella raccolta documenti selezionare i file che si desidera vengano elaborati dal modello.
2. Dopo aver selezionato i file, **classificare ed estrarre** verranno visualizzati nella barra multifunzione della raccolta documenti. Selezionare **classifica ed Estrai**.
3. I file selezionati verranno aggiunti alla coda per l'elaborazione.

      ![Classificare ed estrarre](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)</br>
[Creare un estrattore](create-an-extractor.md)</br>
[Panoramica della comprensione del documento](document-understanding-overview.md)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)  
