---
title: Creare un modello di elaborazione dei moduli
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Creare un modello di elaborazione dei moduli in Microsoft SharePoint Syntex.
ms.openlocfilehash: aed918d899fe7c5e3c49b733d2411c178e9b98d0
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087692"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Creare un modello di elaborazione dei moduli in Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

Con [AI Builder](https://docs.microsoft.com/ai-builder/overview), una funzionalità di Microsoft PowerApps, gli utenti di SharePoint Syntex possono creare un [modello di elaborazione dei moduli](form-processing-overview.md) direttamente da una raccolta documenti di SharePoint. 

La creazione di un modello di elaborazione dei moduli prevede i passaggi seguenti:
 - Passaggio 1: creare il modello di elaborazione moduli per creare il tipo di contenuto
 - Passaggio 2: aggiungere e analizzare file di esempio
 - Passaggio 3: selezionare i campi del modulo
 - Passaggio 4: eseguire il training e il test del modello
 - Passaggio 5: pubblicare il modello
 - Passaggio 6: usare il modello

## <a name="requirements"></a>Requisiti

È possibile unicamente creare un modello di elaborazione modulo nelle raccolte documenti di SharePoint per cui è abilitato. Se l'elaborazione modulo è abilitata, è possibile vedere l'**AI Builder** **"Creare un modello di elaborazione modulo"** nel menu **Automatizza** della raccolta documenti. Se desideri abilitare l'elaborazione sulla raccolta documenti, è necessario contattare l'amministratore di SharePoint.

 ![Creare un modello di AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>Passaggio 1: creare un modello di elaborazione dei moduli

Per creare un modello di elaborazione dei moduli, occorre prima di tutto assegnare un nome al modello, creare e definire il nuovo tipo di contenuto e creare una specifica visualizzazione della raccolta documenti.

1. Nella raccolta documenti scegliere **AI Builder**, dal menu **Automatizza**, quindi selezionare **Crea un modello di elaborazione dei moduli**.

    ![Creare un modello](../media/content-understanding/create-ai-builder-model.png)</br>

2. Nel riquadro **Nuovo modello di elaborazione dei moduli** digitare un nome per il modello nel campo **Nome**, ad esempio *Ordini di acquisto*.

    ![Nuovo modello di elaborazione dei moduli](../media/content-understanding/new-form-model.png)</br> 

3. Quando si crea un modello di elaborazione modulo, viene creato un nuovo tipo di contenuto di SharePoint. Un tipo di contenuto di SharePoint rappresenta una categoria di documenti che vantano caratteristiche comuni e condividono una raccolta di colonne o proprietà dei metadati per quel contenuto specifico. I tipi di contenuto di SharePoint vengono gestiti tramite la [galleria dei tipi di contenuto]().

    Selezionare **Impostazioni avanzate** se si desidera associare questo modello a un tipo di contenuto esistente nella Raccolta tipi di contenuto di SharePoint per usarne lo schema. 

4. Il modello crea una nuova visualizzazione nella raccolta documenti per i dati estratti. Se non si desidera impostarla come visualizzazione predefinita, deselezionare **Imposta visualizzazione come predefinita**.

5. Selezionare **Crea**.

## <a name="step-2-add-and-analyze-documents"></a>Passaggio 2: aggiungere e analizzare documenti

Dopo aver creato il nuovo modello di elaborazione modulo, il browser apre una nuova pagina del modello di elaborazione moduli di PowerApps AI Builder. In questa pagina è possibile aggiungere e analizzare i documenti di esempio. </br>

> [!NOTE]
> Quando si cercano file di esempio da usare, vedere i [requisiti dei documenti di input per il modello di elaborazione moduli e suggerimenti per l'ottimizzazione](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. Selezionare **Aggiungi documenti** per iniziare ad aggiungere documenti di esempio analizzati per determinare le coppie di valori denominate che possono essere estratte. È quindi possibile scegliere o **Carica da risorsa di archiviazione locale**, **SharePoint** o **Risorsa di archiviazione Azure Blob**. È necessario usare almeno cinque file per il training.

2. Dopo aver aggiunto i file, selezionare **Analizza** per verificare le informazioni comuni in tutti i file. Il completamento potrebbe richiedere alcuni minuti.</br> 
 
    ![Analizzare i file](../media/content-understanding/analyze.png)</br> 

3. Terminata l'analisi dei file, nella pagina **Selezionare i campi del modulo da salvare** selezionare il file per visualizzare i campi rilevati.</br>

    ![Selezionare i campi del modulo](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Passaggio 3: selezionare i campi del modulo

Dopo aver analizzato i documenti per i campi, è possibile visualizzare i campi trovati e identificare quelli che si desidera salvare. I campi salvati vengono visualizzati come colonne nella visualizzazione della raccolta documenti dei modello e mostrano i valori estratti da ogni documento.

1. Nella pagina successiva viene visualizzato uno dei file di esempio e vengono evidenziati tutti i campi comuni che sono stati rilevati automaticamente dal sistema. </br>

    ![Pagina Seleziona campi](../media/content-understanding/select-fields-page.png)</br> 

2. Selezionare i campi che si desidera salvare, quindi la casella di controllo per confermare la selezione. Ad esempio, nel modello dell'Ordine di acquisto, scegliere di selezionare *Data*, *PO* e *Campi* totali. Si noti che è possibile decidere di rinominare un campo, se del caso.</br>

    ![Selezionare il numero dell'ordine d'acquisto](../media/content-understanding/po.png)</br> 

3. Qualora un campo non venisse rilevato dall'analisi, sarà ancora possibile aggiungerlo. Evidenziare l'informazione che si desidera estrarre e, nel riquadro relativo al nome digitare il nome desiderato. Quindi selezionare la casella di controllo. Si noti che è necessario confermare i campi non rilevati nei file di esempio rimanenti.

4. Dopo aver selezionato i campi da salvare, fare clic su **Conferma campi**. </br>
 
    ![Conferma campi dopo aver selezionato i campi](../media/content-understanding/confirm-fields.png)</br> 
 
5. Nella pagina **Selezionare i campi del modulo che si desidera salvare**, mostrerà il numero di campi selezionati. Selezionare **Fatto**.

## <a name="step-4-train-and-test-your-model"></a>Passaggio 4: eseguire il training e il test del modello

Dopo aver selezionato i campi da salvare, nella pagina **Riepilogo modelli** è possibile eseguire il training e il test del modello.

1. Nella pagina **Riepilogo modello**, i campi salvati verranno visualizzati nella sezione **Campi selezionati**. Selezionare **Eseguire il training** per iniziare il training sui file di esempio. Si noti che il completamento potrebbe richiedere alcuni minuti.</br>

     ![Training dei file selezionati](../media/content-understanding/select-fields-train.png)</br> 

2. Quando viene indicato che il training è terminato, selezionare **Vai alla pagina Dettagli**. 

3. Nella pagina **Dettagli modello** è possibile scegliere di testare il funzionamento del modello selezionando **Test rapido**. Questa operazione consentirà di trascinare i file nella pagina e vedere se vengono rilevati i campi.

    ![Confermare i campi](../media/content-understanding/select-fields-train.png)</br> 

2. Quando viene indicato che il training è terminato, selezionare **Vai alla pagina Dettagli**. 

3. Nella pagina **Dettagli modello** scegliere di testare il funzionamento del modello selezionando **Test rapido**. Questa operazione consentirà di trascinare i file nella pagina e vedere se vengono rilevati i campi.

## <a name="step-5-publish-your-model"></a>Passaggio 5: pubblicare il modello

1. Se i risultati del modello sono soddisfacenti, selezionare **Pubblica** per metterlo a disposizione.

2. Una volta pubblicato il modello, selezionare **Usa modello**. Questa operazione crea un flusso PowerAutomate che può essere eseguito nella raccolta documenti di SharePoint ed estrae i campi che sono stati identificati nel modello, quindi selezionare **Crea flusso**.
  
3. Al termine, viene visualizzato il messaggio **Il flusso è stato creato**.
 
## <a name="step-6-use-your-model"></a>Passaggio 6: usare il modello

Dopo aver pubblicato il modello e avere creato il relativo flusso di PowerAutomate, è possibile usare il modello nella raccolta documenti di SharePoint.

1. Dopo la pubblicazione del modello, selezionare **Vai a SharePoint** per passare alla raccolta documenti.

2. Nella visualizzazione modello della raccolta documenti notare che i campi selezionati sono visualizzati in colonne.</br>

    ![Modello della raccolta documenti applicato](../media/content-understanding/doc-lib-view.png)</br> 

3. Il collegamento alle informazioni accanto a **Documenti** indica che alla raccolta documenti è applicato un modello di elaborazione dei moduli.

    ![Pulsante Informazioni](../media/content-understanding/info-button.png)</br>  

4. Caricare i file nella raccolta documenti. Qualsiasi file identificato dal modello come corrispondente al suo tipo di contenuto elenca i file nella visualizzazione e mostra i dati estratti nelle colonne.</br>

    ![Fatto](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>Vedere anche
  
[Documentazione di Power Automate](https://docs.microsoft.com/power-automate/)

[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
