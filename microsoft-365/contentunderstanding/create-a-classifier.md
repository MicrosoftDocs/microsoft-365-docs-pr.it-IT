---
title: Creare un classificatore
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni su come creare un classificatore
ms.openlocfilehash: 948ece1a19b7e6049167c373b3200efd316a60cd
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338638"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>Creare un classificatore in Microsoft SharePoint Syntex


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Un classificatore è un tipo di modello che è possibile usare per automatizzare l'identificazione e la classificazione di un tipo di documento. Ad esempio, si può decidere di identificare tutti i documenti *Rinnovo del contratto* aggiunti alla raccolta documenti, come mostrato nella figura seguente.

![Documento Rinnovo del contratto](../media/content-understanding/contract-renewal.png)

La creazione di un classificatore consente di creare un nuovo [tipo di contenuto di SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) che verrà associato al modello.

Quando si crea il classificatore, è necessario creare *spiegazioni* per definire il modello. In questo modo è possibile identificare i dati comuni che si prevede di trovare in modo coerente in questo tipo di documento. 

Usare esempi del tipo di documento ("file di esempio") per "addestrare" il modello a identificare file con lo stesso tipo di contenuto.

Per creare un classificatore, è necessario:
1. Assegnare un nome al modello.
2. Aggiungere file di esempio.
3. Etichettare i file di esempio.
4. Creare una spiegazione.
5. Testare il modello.

> [!NOTE]
> Anche se il modello usa un classificatore per identificare e classificare i tipi di documento, si può anche decidere di estrarre informazioni specifiche da ogni file identificato dal modello. A questo scopo, occorre creare un **estrattore** da aggiungere al modello. Vedere [Creare un estrattore](create-an-extractor.md).

## <a name="name-your-model"></a>Assegnare un nome al modello

Per creare un modello occorre prima di tutto assegnargli un nome:

1. Nel Centro contenuti selezionare **Nuovo** e quindi **Crea un modello**.
2. Nel riquadro **Nuovo modello di comprensione dei documenti** digitare il nome del modello nel campo **Nome**. Ad esempio, se si vogliono identificare i documenti di rinnovo del contratto, è possibile denominare il modello *Rinnovo del contratto*.
3. Scegliere **Crea**. Verrà creata una home page per il modello.</br>

    ![Home page del modello di classificatore](../media/content-understanding/model-home.png)

Quando si crea un modello, viene creato anche un nuovo tipo di contenuto del sito. Un tipo di contenuto rappresenta una categoria di documenti che hanno caratteristiche comuni e condividono una raccolta di colonne o proprietà dei metadati per quel particolare contenuto. I tipi di contenuto di SharePoint vengono gestiti tramite la [Raccolta tipi di contenuto](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f). In questo esempio, quando si crea il modello, si crea un nuovo tipo di contenuto *Rinnovo del contratto*.

Selezionare **Impostazioni avanzate** se si vuole associare questo modello a un tipo di contenuto aziendale esistente nella Raccolta tipi di contenuto di SharePoint per usarne lo schema. I tipi di contenuto aziendale sono archiviati nell'hub del tipo di contenuto nell'interfaccia di amministrazione di SharePoint e vengono diffusi a tutti i siti del tenant. Tenere presente che, anche se è possibile usare un tipo di contenuto esistente per utilizzarne lo schema e agevolare l'identificazione e la classificazione, è comunque necessario addestrare il modello a estrarre le informazioni dai file identificati.</br>

![Impostazioni avanzate](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Aggiungere file di esempio

Nella home page del modello aggiungere i file di esempio necessari per addestrare il modello a identificare il tipo di documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> È consigliabile usare gli stessi file sia per il classificatore che per l'[addestramento dell'estrattore](create-an-extractor.md). È sempre possibile aggiungere altre informazioni in seguito, ma in genere si aggiunge un set completo di file di esempio. Etichettarne alcuni per eseguire il training del modello e testare i file restanti senza etichetta per valutare l'adeguatezza del modello. 

Per il set di training, è bene usare esempi sia positivi sia negativi:
- Esempio positivo: documenti che rappresentano il tipo di documento. Contengono stringhe e informazioni che sono sempre presenti nei documenti di questo tipo.
- Esempio negativo: qualsiasi altro documento che non rappresenta il documento da classificare. 

Usare almeno cinque esempi positivi e almeno un esempio negativo per addestrare il modello.  Dopo il processo di training, è possibile crearne altri per testare il modello.

Per aggiungere file di esempio:

1. Nella home page del modello fare clic su **Aggiungi file** nel riquadro **Aggiungi file di esempio**.
2. Nella pagina **Selezionare i file di esempio per il modello** selezionare i file di esempio nella raccolta di file di training nel centro contenuti. Se non sono ancora stati caricati, scegliere di caricarli subito facendo clic su **Carica** per copiarli nella raccolta di file di training.
3. Dopo aver selezionato i file di esempio da usare per il modello, fare clic su **Aggiungi**.

    ![Selezionare i file di esempio](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Etichettare i file di esempio

Dopo aver aggiunto i file di esempio, è necessario etichettarli come esempi positivi o negativi.

1. Nella home page del modello, fare clic su **Eseguire il training del classificatore** nel riquadro **Classificare i file ed eseguire il training**.
   Verrà visualizzata la pagina dell'etichetta con un elenco dei file di esempio e il primo file mostrato nel visualizzatore.
2. Nel visualizzatore nella parte superiore del primo file di esempio dovrebbe essere presente un testo che chiede se il file è un esempio del modello appena creato. Se è un esempio positivo, selezionare **Sì**. Se è un esempio negativo, selezionare **No**.
3. Nell'elenco **Esempi etichettati** a sinistra selezionare altri file da usare come esempi ed etichettarli. 

    ![Home page del classificatore](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> Etichettare almeno cinque esempi positivi. È anche necessario etichettare almeno un esempio negativo. 

## <a name="create-an-explanation"></a>Creare una spiegazione

Il passaggio successivo consiste nel creare una spiegazione nella pagina Avvia training. Una spiegazione aiuta il modello a comprendere come riconoscere il documento. Ad esempio, i documenti relativi al rinnovo del contratto contengono sempre una stringa di testo *Richiesta di informazioni aggiuntive*.

> [!Note]
> Quando viene usata con gli estrattori, una spiegazione identifica la stringa da estrarre dal documento. 

Per creare una spiegazione:

1. Nella home page del modello selezionare la scheda **Avvia training** per passare alla pagina corrispondente.
2. Nella sezione **File con training** della pagina Avvia training dovrebbe essere presente un elenco dei file di esempio precedentemente etichettati. Selezionare uno dei file positivi nell'elenco. Verrà visualizzato nel visualizzatore.
3. Nella sezione Spiegazione selezionare **Nuovo** e quindi **Vuoto**.
4. Nella pagina **Crea spiegazione**:</br>
    a. Digitare il **Nome**, ad esempio "Blocco divulgazione".</br>
    b. Selezionare il **Tipo**. In questo caso selezionare **Elenco frasi** perché viene aggiunta una stringa di testo.</br>
    c. Digitare la stringa nella casella **Digitare qui**. Per questo esempio, aggiungere "Richiesta di informazioni aggiuntive". È possibile selezionare **Maiuscole/Minuscole** se è necessario distinguere tra maiuscole e minuscole nella stringa.</br>
    d. Fare clic su **Salva**.

    ![Creare una spiegazione](../media/content-understanding/explanation.png) 
    
 
5. A questo punto, il modello verifica se la spiegazione creata consente di identificare correttamente gli altri file di esempio etichettati come esempi positivi e negativi. Al termine del training, controllare la colonna **Valutazione** nella sezione File con training per visualizzare i risultati. I file mostrano il valore **Corrisponde** se le spiegazioni create sono risultate sufficienti per trovare una corrispondenza con ciò che è stato etichettato come positivo o negativo.

    ![Valore Corrisponde](../media/content-understanding/match.png) 

Se i file etichettati risultano **Non corrispondenti**, può essere necessario creare un'ulteriore spiegazione per fornire altre informazioni al modello per identificare il tipo di documento. In questo caso, fare clic sul file per ottenere altre informazioni sul motivo della mancata corrispondenza.

## <a name="test-your-model"></a>Testare il modello

Se è stata rilevata una corrispondenza nei file di esempio etichettati, è possibile testare il modello nei rimanenti file di esempio non etichettati, non ancora esaminati dal modello.  Questo è un passaggio opzionale, ma utile per valutare l'adeguatezza del modello prima di usarlo, testandolo sui file che il modello non ha ancora esaminato.

1. Nella home page del modello selezionare la scheda **Test**. Il modello viene eseguito nei file di esempio non etichettati.
2. Nell'elenco **Testa i file** vengono visualizzati i file di esempio e viene indicato se il modello prevede che siano positivi o negativi. Usare queste informazioni per determinare l'efficacia del classificatore nell'identificazione dei documenti.

    ![Test di file non etichettati](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>Vedere anche
[Creare un estrattore](create-an-extractor.md)

[Panoramica sull'analisi dei documenti](document-understanding-overview.md)

[Tipi di spiegazione](explanation-types-overview.md)

[Applicare un modello](apply-a-model.md) 
