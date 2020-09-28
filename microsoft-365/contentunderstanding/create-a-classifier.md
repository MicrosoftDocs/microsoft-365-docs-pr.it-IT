---
title: Creare un classificatore
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
description: Informazioni su come creare un classificatore
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294903"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>Creare un classificatore in Microsoft SharePoint Syntex

Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Un classificatore è un tipo di modello che è possibile utilizzare per automatizzare l'identificazione e la classificazione di un tipo di documento. Ad esempio, è possibile identificare tutti i documenti di *rinnovo del contratto* che vengono aggiunti alla raccolta documenti, come illustrato nella figura seguente.

![Documento di rinnovo del contratto](../media/content-understanding/contract-renewal.png)

La creazione di un classificatore consente di creare un nuovo [tipo di contenuto di SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) che verrà associato al modello.

Quando si crea il classificatore, è necessario creare *spiegazioni* per definire il modello. In questo modo è possibile notare i dati comuni che si prevede di trovare sempre questo tipo di documento. 

Utilizzare esempi del tipo di documento ("file di esempio") per "formare" il modello per identificare i file con lo stesso tipo di contenuto.

Per creare un classificatore, è necessario eseguire le operazioni seguenti:
1. Assegnare un nome al modello.
2. Aggiungere i file di esempio.
3. Contrassegnare i file di esempio.
4. Creare una spiegazione.
5. Eseguire il test del modello.

> [!NOTE]
> Mentre il modello utilizza un classificatore per identificare e classificare i tipi di documenti, è anche possibile scegliere di estrarre informazioni specifiche da ogni file identificato dal modello. A tale scopo, è possibile creare un **estrattore** da aggiungere al modello. Vedere [creare un estrattore](create-an-extractor.md).

## <a name="name-your-model"></a>Assegnare un nome al modello

Il primo passaggio per creare il modello consiste nel assegnargli un nome:

1. Dal centro contenuto, selezionare **nuovo**e quindi **creare un modello**.
2. Nel riquadro **nuovo modello di informazioni sul documento** , nel campo **nome** digitare il nome del modello. Ad esempio, se si desidera identificare i documenti di rinnovo del contratto, è possibile assegnare un nome al modello di *rinnovo del contratto*.
3. 	Selezionare **Crea**. In questo modo viene creata una Home page per il modello.</br>

    ![Home page del modello di classificazione](../media/content-understanding/model-home.png)

Quando si crea un modello, si crea anche un nuovo tipo di contenuto di SharePoint. Un tipo di contenuto di SharePoint rappresenta una categoria di documenti con caratteristiche comuni e la condivisione di una raccolta di colonne o proprietà dei metadati per il contenuto specifico. I tipi di contenuto di SharePoint vengono gestiti tramite la [raccolta tipi di contenuto](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f). In questo esempio, quando si crea il modello, si crea un nuovo tipo di contenuto per il *rinnovo del contratto* .

Selezionare **Impostazioni avanzate** se si desidera eseguire il mapping di questo modello a un tipo di contenuto esistente nella raccolta tipi di contenuto di SharePoint per utilizzarne lo schema. Si noti che, sebbene sia possibile utilizzare un tipo di contenuto esistente per sfruttare il relativo schema per facilitare l'identificazione e la classificazione, è comunque necessario addestrare il modello per estrarre informazioni dai file identificati.</br>

![Impostazioni avanzate](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Aggiungere i file di esempio

Nella Home page del modello aggiungere i file degli esempi necessari per la formazione del modello per identificare il tipo di documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> È consigliabile utilizzare gli stessi file per la formazione del classificatore e dell' [estrattore](create-an-extractor.md). Si ha sempre la possibilità di aggiungere altre versioni successive, ma in genere si aggiunge una serie completa di file di esempio. Etichetta alcuni per formare il modello e testare quelli restanti senza etichetta per valutare la forma fisica del modello. 

Per il set di training, si desidera utilizzare esempi positivi e negativi:
- Esempio positivo: documenti che rappresentano il tipo di documento. Contengono stringhe e informazioni che sarebbero sempre presenti in questo tipo di documento.
- Esempio negativo: documenti che non rappresentano il tipo di documento. Si tratta di stringhe mancanti e di informazioni che devono essere presenti in questo tipo di documento.

Assicurarsi di utilizzare almeno cinque esempi positivi e almeno un esempio negativo per la formazione del modello.  Si desidera crearne di nuovi per testare il modello dopo il processo di formazione.

Per aggiungere file di esempio:

1. Dalla Home page del modello fare clic su **Aggiungi file**nel riquadro della **raccolta di esempi di compilazione** .
2. Nella pagina **selezionare** i file di esempio della pagina del modello selezionare i file degli esempi dalla libreria file di esempio nel centro contenuto. Se non li hai già caricati, scegli di caricarli subito facendo clic su **carica** per spostarli nella raccolta file di esempio.
3. Dopo aver selezionato i file di esempio da utilizzare per la formazione del modello, fare clic su **Aggiungi**.

    ![Selezionare i file di esempio](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Contrassegnare i file di esempio

Dopo aver aggiunto i file di esempio, è necessario etichettarli come esempi positivi o negativi.

1. Nella Home page del modello fare clic su **classificazione**dei **file e quindi eseguire il training** Tile.
   Viene visualizzata la pagina etichetta che mostra un elenco dei file di esempio, con il primo file visibile nel visualizzatore.
2. Nel Visualizzatore nella parte superiore del primo file di esempio, dovrebbe essere visualizzato il testo che chiede se il file è un esempio del modello appena creato. Se si tratta di un esempio positivo, selezionare **Sì**. Se si tratta di un esempio negativo, selezionare **No**.
3. Nell'elenco degli **esempi etichettati** a sinistra, selezionare altri file che si desidera utilizzare come esempi ed etichettarli. 

    ![Home page di classificazione](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> Etichettare almeno cinque esempi positivi e un esempio negativo. 

## <a name="create-an-explanation"></a>Creare una spiegazione

Il passaggio successivo consiste nel creare una spiegazione sulla pagina del treno. Una spiegazione aiuta il modello a comprendere come riconoscere il documento. Ad esempio, i documenti di rinnovo del contratto contengono sempre una *richiesta per una stringa di testo di divulgazione aggiuntiva* .

> [!Note]
> Se utilizzata con gli estrattori, una spiegazione identifica la stringa che si desidera estrarre dal documento. 

Per creare una spiegazione:

1. Nella Home page del modello selezionare la scheda **treno** per andare alla pagina del treno.
2. Nella sezione **file addestrati** della pagina del treno dovrebbe essere visualizzato un elenco dei file di esempio che sono stati precedentemente etichettati. Selezionare uno dei file positivi nell'elenco e visualizzarlo nel visualizzatore.
3. Nella sezione spiegazione selezionare **nuovo** e quindi **vuoto**.
4. Nella pagina **Crea una spiegazione** :</br>
    a. Digitare il **nome** (ad esempio, "blocco di disclosure").</br>
    b. Selezionare il **tipo**. Per l'esempio, selezionare l' **elenco delle frasi**, poiché si aggiunge una stringa di testo.</br>
    c. Nella casella **digitare qui** Digitare la stringa. Per l'esempio, aggiungere "richiesta di ulteriore divulgazione". È **possibile selezionare maiuscole/minuscole** se la stringa deve essere distinzione tra maiuscole e minuscole.</br>
    d. Fare clic su **Salva**.

    ![Creare una spiegazione](../media/content-understanding/explanation.png) 
    
 
5. Il modello ora controlla se la spiegazione creata è stata sufficiente per identificare correttamente i file di esempio con etichetta rimanenti, come esempi positivi e negativi. Nella sezione file addestrati controllare la colonna **valutazione** dopo aver completato il training per visualizzare i risultati. I file mostrano un valore di **corrispondenza**, se le spiegazioni create sono sufficienti per corrispondere a quelle contrassegnate come positive o negative.

    ![Valore di corrispondenza](../media/content-understanding/match.png) 

Se si riceve una **mancata corrispondenza** nei file contrassegnati, potrebbe essere necessario creare una spiegazione aggiuntiva per fornire al modello ulteriori informazioni per identificare il tipo di documento. In questo caso, fare clic sul file per ottenere ulteriori informazioni sul motivo per cui la mancata corrispondenza si è verificata.

## <a name="test-your-model"></a>Testare il modello

Se è stata ricevuta una corrispondenza nei file di esempio etichettati, è ora possibile testare il modello nei file di esempio senza etichetta rimanenti.

1. Nella Home page del modello selezionare la scheda **test** .  Questo esegue il modello nei file di esempio senza etichetta.
2. Nell'elenco **file di test** , i file di esempio vengono visualizzati e mostrati se il modello ha previsto che siano positivi o negativi. Utilizzare queste informazioni per determinare l'efficacia del classificatore per identificare i documenti.

    ![Test dei file senza etichetta](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>Vedere anche
[Creare un estrattore](create-an-extractor.md)</br>
[Panoramica della comprensione del documento](document-understanding-overview.md)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</br>
[Applicazione di un modello](apply-a-model.md) 
