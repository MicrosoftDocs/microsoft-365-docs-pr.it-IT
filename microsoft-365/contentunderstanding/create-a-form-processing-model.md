---
title: Creare un modello di elaborazione dei moduli
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Creare un modello di elaborazione dei moduli in Microsoft SharePoint Syntex.
ms.openlocfilehash: 27e80a7b3626170e45ceaa55f1269e50d8fdab9e
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337266"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Creare un modello di elaborazione dei moduli in Microsoft SharePoint Syntex


Con [AI Builder](https://docs.microsoft.com/ai-builder/overview), una funzionalità di Microsoft PowerApps, gli utenti di SharePoint Syntex possono creare un [modello di elaborazione dei moduli](form-processing-overview.md) direttamente da una raccolta documenti di SharePoint. 

La creazione di un modello di elaborazione dei moduli prevede i passaggi seguenti:
 - Passaggio 1: creare il modello di elaborazione moduli per creare il tipo di contenuto
 - Passaggio 2: aggiungere e analizzare file di esempio
 - Passaggio 3: selezionare i campi del modulo
 - Passaggio 4: eseguire il training e il test del modello
 - Passaggio 5: pubblicare il modello
 - Passaggio 6: usare il modello

## <a name="requirements"></a>Requisiti

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>


È possibile creare un modello di elaborazione dei moduli solo nelle raccolte documenti di SharePoint per le quali è abilitata. Se l'elaborazione dei moduli è abilitata, sarà presente l'opzione **AI Builder** **Crea un modello di elaborazione dei moduli** nel menu **Automatizza** nella raccolta documenti.  Se è necessario abilitare l'elaborazione nella raccolta documenti, contattare l'amministratore di SharePoint.

 ![Creare un modello di AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>Passaggio 1: creare un modello di elaborazione dei moduli

Per creare un modello di elaborazione dei moduli, occorre prima di tutto assegnare un nome al modello, creare e definire il nuovo tipo di contenuto e creare una specifica visualizzazione della raccolta documenti.

1. Nella raccolta documenti scegliere **AI Builder**, dal menu **Automatizza**, quindi selezionare **Crea un modello di elaborazione dei moduli**.

    ![Creare un modello](../media/content-understanding/create-ai-builder-model.png)</br>

2. Nel riquadro **Nuovo modello di elaborazione dei moduli** digitare un nome per il modello nel campo **Nome**, ad esempio *Ordini di acquisto*.

    ![Nuovo modello di elaborazione dei moduli](../media/content-understanding/new-form-model.png)</br> 

3. Quando si crea un modello di elaborazione dei moduli, si crea un nuovo tipo di contenuto di SharePoint. Un tipo di contenuto di SharePoint rappresenta una categoria di documenti che hanno caratteristiche comuni e condividono una raccolta di colonne o proprietà dei metadati per quel particolare contenuto. I tipi di contenuto di SharePoint vengono gestiti tramite la [Raccolta tipi di contenuto]().

    Selezionare **Impostazioni avanzate** se si vuole associare questo modello a un tipo di contenuto esistente nella Raccolta tipi di contenuto di SharePoint per usarne lo schema. 

4. Il modello crea una nuova visualizzazione nella raccolta documenti per i dati estratti. Se non si vuole impostarla come visualizzazione predefinita, deselezionare **Imposta la visualizzazione come predefinita**.

5. Selezionare **Crea**.

## <a name="step-2-add-and-analyze-documents"></a>Passaggio 2: aggiungere e analizzare documenti

Dopo aver creato il nuovo modello di elaborazione dei moduli, nel browser viene aperta una nuova pagina del modello di elaborazione dei moduli di PowerApps AI Builder. In questa pagina è possibile aggiungere e analizzare i documenti di esempio. </br>

> [!NOTE]
> Quando si cercano file di esempio da usare, vedere i [requisiti dei documenti di input per il modello di elaborazione moduli e suggerimenti per l'ottimizzazione](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. Selezionare **Aggiungi documenti** per iniziare ad aggiungere documenti di esempio analizzati per determinare le coppie di valori denominate che è possibile estrarre. È quindi possibile scegliere **Carica dalla risorsa di archiviazione locale**, **SharePoint** o **Archiviazione BLOB di Azure**. È necessario usare almeno cinque file per il training.

2. Dopo aver aggiunto i file, selezionare **Analizza** per verificare se esistono informazioni comuni a tutti i file. Questo processo potrebbe richiedere alcuni minuti.</br> 
 
    ![Analizzare i file](../media/content-understanding/analyze.png)</br> 

3. Terminata l'analisi dei file, nella pagina **Selezionare i campi del modulo da salvare** selezionare il file per visualizzare i campi rilevati.</br>

    ![Selezionare i campi del modulo](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Passaggio 3: selezionare i campi del modulo

Una volta analizzati i documenti per individuare i campi, è possibile vedere i campi rilevati e identificare quelli da salvare. I campi salvati vengono visualizzati come colonne nella visualizzazione della raccolta documenti del modello e mostrano i valori estratti da ogni documento.

1. Nella pagina successiva viene visualizzato uno dei file di esempio e vengono evidenziati tutti i campi comuni che sono stati rilevati automaticamente dal sistema. </br>

    ![Pagina Seleziona campi](../media/content-understanding/select-fields-page.png)</br> 

2. Selezionare i campi a salvare e selezionare la casella di controllo per confermare la selezione. Ad esempio, nel modello di ordine di acquisto selezionare i campi *Data*, *Ordine d'acquisto* e *Totale*.  Se si vuole, è possibile anche decidere di rinominare un campo. </br>

    ![Selezionare il numero dell'ordine d'acquisto](../media/content-understanding/po.png)</br> 

3. Se un campo non è stato rilevato dall'analisi, è comunque possibile scegliere di aggiungerlo. Evidenziare le informazioni da estrarre, quindi immettere il nome desiderato nella casella relativa al nome. Selezionare quindi la casella di controllo. Tenere presente che è necessario confermare i campi non rilevati nei file di esempio rimanenti.

4. Dopo aver selezionato i campi da salvare, fare clic su **Conferma campi**. </br>
 
    ![Conferma campi dopo aver selezionato i campi](../media/content-understanding/confirm-fields.png)</br> 
 
5. Nella pagina **Selezionare i campi del modulo da salvare** viene visualizzato il numero di campi selezionati. Scegliere **Fatto**.

## <a name="step-4-train-and-test-your-model"></a>Passaggio 4: eseguire il training e il test del modello

Dopo aver selezionato i campi da salvare, nella pagina **Riepilogo modelli** è possibile eseguire il training e il test del modello.

1. Nella pagina **Riepilogo modelli** i campi salvati vengono visualizzati nella sezione **Campi selezionati**. Selezionare **Avvia training** per avviare il training sul file di esempio. Tenere presente che questo processo potrebbe richiedere alcuni minuti.</br>

     ![Training dei file selezionati](../media/content-understanding/select-fields-train.png)</br> 

2. Quando viene indicato che il training è terminato, selezionare **Vai alla pagina Dettagli**. 

3. Nella pagina **Dettagli modello** si può decidere di testare il funzionamento del modello selezionando **Test rapido**. Questo consente di trascinare i file nella pagina e verificare se i campi vengono rilevati.

    ![Confermare i campi](../media/content-understanding/select-fields-train.png)</br> 

2. Quando viene indicato che il training è terminato, selezionare **Vai alla pagina Dettagli**. 

3. Nella pagina **Dettagli modello**, scegliere di testare il funzionamento del modello selezionando **Test rapido**. Questo consente di trascinare i file nella pagina e verificare se i campi vengono rilevati.

## <a name="step-5-publish-your-model"></a>Passaggio 5: pubblicare il modello

1. Se i risultati del modello sono soddisfacenti, selezionare **Pubblica** per metterlo a disposizione.

2. Dopo avere pubblicato il modello, selezionare **Usa modello**. In questo modo viene creato un flusso di PowerAutomate che può essere eseguito nella raccolta documenti di SharePoint ed estrae i campi identificati nel modello, quindi selezionare **Crea flusso**.
  
3. Al termine, viene visualizzato il messaggio **Il flusso è stato creato**.
 
## <a name="step-6-use-your-model"></a>Passaggio 6: usare il modello

Dopo aver pubblicato il modello e avere creato il relativo flusso di PowerAutomate, è possibile usare il modello nella raccolta documenti di SharePoint.

1. Dopo la pubblicazione del modello, selezionare **Vai a SharePoint** per passare alla raccolta documenti.

2. Nella visualizzazione modello della raccolta documenti notare che i campi selezionati sono visualizzati in colonne.</br>

    ![Modello della raccolta documenti applicato](../media/content-understanding/doc-lib-view.png)</br> 

3. Il collegamento alle informazioni accanto a **Documenti** indica che alla raccolta documenti è applicato un modello di elaborazione dei moduli.

    ![Pulsante Informazioni](../media/content-understanding/info-button.png)</br>  

4. Caricare i file nella raccolta documenti. Qualsiasi file che il modello identifica come corrispondente al suo tipo di contenuto elenca i file nella visualizzazione e mostra i dati estratti nelle colonne.</br>

    ![Fatto](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>Vedere anche
  
[Documentazione di Power Automate](https://docs.microsoft.com/power-automate/)

[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
