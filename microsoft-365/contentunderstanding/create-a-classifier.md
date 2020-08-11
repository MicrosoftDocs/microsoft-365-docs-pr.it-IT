---
title: Creare un classificatore (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come creare un classificatore
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612609"
---
# <a name="create-a-classifier-preview"></a>Creare un classificatore (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Un classificatore è un tipo di modello che automatizza l'identificazione e la classificazione di un tipo di documento. Ad esempio, è possibile identificare tutti i documenti di *rinnovo del contratto* che vengono aggiunti alla raccolta documenti, come quelli riportati di seguito.

![Documento di rinnovo del contratto](../media/content-understanding/contract-renewal.png)

La creazione di un classificatore creerà un nuovo [tipo di contenuto di SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) che verrà associato al modello.

Quando si crea il classificatore, è necessario creare *spiegazioni* che consentano di definire il modello osservando i dati comuni che si prevede di trovare in modo coerente per questo tipo di documento. 

È possibile utilizzare esempi del tipo di documento ("file di esempio") per facilitare la formazione del modello per identificare i file con lo stesso tipo di contenuto.

Per creare un classificatore, è necessario eseguire le operazioni seguenti:
1. Assegnare un nome al modello
2. Aggiungere i file di esempio
3. Contrassegnare i file di esempio
4. Creare una spiegazione
5. Testare il modello 

> [!Note]
> Mentre un classificatore viene utilizzato dal modello per identificare e classificare i tipi di documenti, è anche possibile scegliere di estrarre informazioni specifiche da ogni file identificato dal modello. A tale scopo, è possibile creare un **estrattore** da aggiungere al modello e questo viene descritto in [creare un estrattore](create-an-extractor.md).

## <a name="name-your-model"></a>Assegnare un nome al modello

Il primo passaggio consiste nel creare il modello nel centro di contenuto assegnando un nome:

1. Nel centro contenuto fare clic su **nuovo**e quindi su **Crea un modello**.
2. Nel riquadro **nuovo modello di informazioni sul documento** , nel campo **nome** , digitare il nome del modello. Ad esempio, se si desidera identificare i documenti di rinnovo del contratto, è possibile assegnare un nome al *rinnovo del contratto*del modello.
3. Fare clic su **Crea**. Verrà creata una Home page per il modello.</br>

    ![Home page del modello di classificazione](../media/content-understanding/model-home.png)

Quando si crea un modello, si crea un nuovo tipo di contenuto di SharePoint. Un tipo di contenuto di SharePoint rappresenta una categoria di documenti con caratteristiche comuni e la condivisione di una raccolta di colonne o proprietà dei metadati per il contenuto specifico. I tipi di contenuto di SharePoint vengono gestiti tramite la [raccolta tipi di contenuto](). Ad esempio, quando si crea il modello, verrà creato un nuovo tipo di contenuto per il *rinnovo del contratto* .

Selezionare **Impostazioni avanzate** se si desidera eseguire il mapping di questo modello a un tipo di contenuto esistente nella raccolta tipi di contenuto di SharePoint per utilizzarne lo schema. Si noti che, sebbene sia possibile utilizzare un tipo di contenuto esistente per sfruttare il relativo schema per facilitare l'identificazione e la classificazione, sarà comunque necessario addestrare il modello per estrarre informazioni dai file identificati.</br>

![Impostazioni avanzate](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Aggiungere i file di esempio

Nella Home page del modello è possibile aggiungere i file degli esempi necessari per la formazione del modello per identificare il tipo di documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> Gli stessi file devono essere utilizzati sia per i corsi di classificazione che per gli [estrattori](create-an-extractor.md). Si ha sempre la possibilità di aggiungere altre versioni successive, ma in genere è necessario aggiungere un set completo di file di esempio. Sarà necessario etichettarne alcuni per formare il modello e testare quelli restanti senza etichetta per valutare la forma fisica del modello. 

Per il set di formazione, è consigliabile utilizzare esempi positivi e esempi negativi:
- Esempio positivo: documenti che rappresentano il tipo di documento. Contengono stringhe e informazioni che sarebbero sempre presenti in questo tipo di documento.
- Esempio negativo: documenti che non rappresentano il tipo di documento.  Si tratta di stringhe mancanti e di informazioni che devono essere presenti in questo tipo di documento.

Sarà necessario utilizzare almeno cinque esempi positivi e un esempio negativo per la formazione del modello.  Dopo l'allenamento, è necessario avere altre informazioni per testare il modello.

Per aggiungere file di esempio:

1. Nella Home page del modello fare clic su **Aggiungi file**nel riquadro della **raccolta di esempi di compilazione** .
2. Nella pagina **selezionare** i file di esempio della pagina del modello selezionare i file degli esempi dalla libreria file di esempio nel centro contenuto. Se non li hai già caricati, puoi scegliere di caricarli subito facendo clic su **carica** per spostarli nella raccolta file di esempio.
3. Dopo aver selezionato i file di esempio da utilizzare per la formazione del modello, fare clic su **Aggiungi**.

    ![Selezionare i file di esempio](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Contrassegnare i file di esempio

Dopo aver aggiunto i file di esempio, è necessario etichettarli come esempi positivi o esempi negativi.

1. Nella Home page del modello fare clic su **classificazione**dei **file e sull'esecuzione** del riquadro di addestramento.
   Verrà visualizzata la pagina etichetta che mostra un elenco dei file di esempio, con il primo file visibile nel visualizzatore.
2. Nel Visualizzatore, nella parte superiore del primo file di esempio, verrà visualizzato un messaggio in cui viene chiesto se il file è un esempio del modello appena creato. Se si tratta di un esempio positivo, selezionare **Sì**. Se si tratta di un esempio negativo, selezionare **No**.
3. Nell'elenco degli **esempi etichettati** a sinistra, selezionare altri file che si desidera utilizzare come esempi ed etichettarli. 

    ![Home page del modello di classificazione](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> Etichettare almeno cinque esempi positivi e un esempio negativo. 

## <a name="create-an-explanation"></a>Creare una spiegazione

Il passaggio successivo consiste nel creare una spiegazione sulla pagina del treno.  Una spiegazione è un suggerimento o un indizio per aiutare il modello a capire come riconoscere questo documento. Ad esempio, i documenti di rinnovo del contratto contengono sempre una *richiesta per una stringa di testo di divulgazione aggiuntiva* .

> [!Note]
> Se utilizzato con gli estrattori, viene utilizzata una spiegazione per identificare la stringa che si desidera estrarre dal documento. 

Per creare una spiegazione:

1. Nella Home page del modello fare clic sulla scheda **treno** per andare alla pagina del treno.
2. Nella sezione **file addestrati** della pagina del treno verrà visualizzato un elenco dei file di esempio precedentemente etichettati. Selezionare uno dei file positivi dall'elenco, che verrà visualizzato nel visualizzatore.
3. Nella sezione spiegazione fare clic su **nuovo**e quindi su **vuoto**.
4. Nella pagina **Crea una spiegazione** :</br>
    a. Digitare il **nome** (ad esempio, "blocco di disclosure").</br>
    b. Selezionare il **tipo**. In questo esempio, si selezionerà l' **elenco delle frasi**, poiché si aggiunge una stringa di testo.</br>
    c. Nella casella **digitare qui** Digitare la stringa.  In questo esempio, verrà aggiunta la richiesta di informazioni aggiuntive. È **possibile selezionare maiuscole/minuscole** se la stringa deve essere distinzione tra maiuscole e minuscole.</br>
    d. Fare clic su **Salva**.

    ![Creare una spiegazione](../media/content-understanding/explanation.png) 
    
 
5.  Il modello controllerà ora se la spiegazione creata è stata sufficiente per identificare correttamente i file di esempio con etichetta rimanenti come esempi positivi e negativi. Nella sezione file addestrati selezionare la colonna **valutazione** dopo aver completato il training per visualizzare i risultati.  I file visualizzeranno un valore **corrispondente** se la spiegazione creata è sufficiente per soddisfare le etichette come (positive o negative).

    ![Creare una spiegazione](../media/content-understanding/match.png) 

Se si riceve una **mancata corrispondenza** nei file etichettati, potrebbe essere necessario creare una spiegazione aggiuntiva per fornire al modello ulteriori informazioni per identificare il tipo di documento. È possibile fare clic sul file per ottenere ulteriori informazioni sul motivo per cui è stata eseguita la mancata corrispondenza.

## <a name="test-your-model"></a>Testare il modello

Se è stata ricevuta una corrispondenza nei file di esempio contrassegnati, è ora possibile testare il modello nei file di esempio senza etichetta rimanenti.

1. Nella Home page del modello fare clic sulla scheda **test** .  Verrà eseguito il modello nei file di esempio senza etichetta.
2. Nell'elenco **file di test** , i file di esempio verranno visualizzati e mostreranno se il modello ha previsto che siano esempi positivi o negativi. È possibile utilizzare queste informazioni per determinare l'efficacia del classificatore per identificare i documenti.

    ![Test dei file senza etichetta](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a>Vedere anche
[Creare un estrattore](create-an-extractor.md)</br>
[Panoramica della comprensione del documento](document-understanding-overview.md)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</br>
[Applicazione di un modello](apply-a-model.md) 




