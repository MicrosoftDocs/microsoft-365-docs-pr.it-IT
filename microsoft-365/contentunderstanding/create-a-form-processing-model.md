---
title: Creare un modello di elaborazione dei moduli (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Creare un modello di elaborazione dei moduli in Project Cortex.
ms.openlocfilehash: d3ca64ff5923e95704b72fd748884549a18624a3
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540143"
---
# <a name="create-a-form-processing-model-preview"></a>Creare un modello di elaborazione dei moduli (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

Utilizzo di [ai Builder](https://docs.microsoft.com/ai-builder/overview) -caratteristica di Microsoft PowerApps-Project Cortex gli utenti possono creare un [modello di elaborazione dei moduli](form-processing-overview.md) direttamente da una raccolta documenti di SharePoint. 

La creazione di un modello di elaborazione dei moduli comporta quanto segue:
 - Passaggio 1: creare il modello di elaborazione da per creare il tipo di contenuto
 - Passaggio 2: aggiungere e analizzare file di esempio
 - Passaggio 3: selezionare i campi del modulo
 - Passaggio 4: formare e testare il modello
 - Passaggio 5: pubblicare il modello
 - Passaggio 6: utilizzare il modello


## <a name="requirements"></a>Requisiti

È possibile creare un modello di elaborazione dei moduli solo nelle raccolte documenti di SharePoint in cui è abilitata. Se l'elaborazione dei moduli è abilitata, sarà possibile visualizzare il **Generatore di ai** **"creare un modello di elaborazione dei moduli"** nel menu **automatizza** nella raccolta documenti.  Se è necessario l'elaborazione abilitata nella raccolta documenti, contattare l'amministratore.

 ![Creare un modello AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a>Passaggio 1: creare un modello di elaborazione dei moduli

Il primo passaggio per la creazione di un modello di elaborazione dei moduli consiste nel denominarlo per creare il nuovo tipo di contenuto e creare una nuova visualizzazione della raccolta documenti.

1. Nella raccolta documenti, selezionare il menu **automatizza** , selezionare Generatore di **ai**e quindi fare clic su **Crea modello di elaborazione del modulo**.

    ![Creare un modello AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>
2. Nel riquadro **nuovo modello di elaborazione del modulo** , nel campo **nome** , digitare un nome per il modello (ad esempio, *ordini di acquisto*).

    ![Nuovo modello di elaborazione dei moduli](../media/content-understanding/new-form-model.png)</br> 

3. Quando si crea un modello di elaborazione del modulo, si crea un nuovo tipo di contenuto di SharePoint. Un tipo di contenuto di SharePoint rappresenta una categoria di documenti con caratteristiche comuni e la condivisione di una raccolta di colonne o proprietà dei metadati per il contenuto specifico. I tipi di contenuto di SharePoint vengono gestiti tramite la [raccolta tipi di contenuto]().

    Selezionare **Impostazioni avanzate** se si desidera eseguire il mapping di questo modello a un tipo di contenuto esistente nella raccolta tipi di contenuto di SharePoint per utilizzarne lo schema. 

4. Il modello creerà una nuova visualizzazione nella raccolta documenti per i dati estratti. Se non si desidera che venga visualizzata la visualizzazione predefinita, deselezionare **imposta la visualizzazione come predefinita**.
5. Selezionare **Crea**.


## <a name="step-2-add-and-analyze-documents"></a>Passaggio 2: aggiungere e analizzare documenti

Dopo aver creato il nuovo modello di elaborazione del modulo, nel browser verrà aperta una nuova pagina del modello di elaborazione moduli di PowerApps AI Builder. In questa pagina è possibile aggiungere e analizzare i documenti di esempio. </br>

> [!Note]
> Quando si cercano file di esempio da utilizzare, vedere il [modello di elaborazione dei moduli di input e suggerimenti](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)per l'ottimizzazione. 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. Fare clic su **Aggiungi documenti** per iniziare ad aggiungere documenti di esempio analizzati per determinare le coppie di valori denominabili che è possibile estrarre. È possibile scegliere **carica da archiviazione locale**, **SharePoint**o **archiviazione BLOB di Azure**. Sarà necessario utilizzare almeno cinque file per la formazione.
2. Dopo aver aggiunto i file, selezionare **Analyze** per controllare che tutte le informazioni comuni siano tutti i file. Tenere presente che potrebbero essere necessari alcuni minuti per il completamento.</br> 
 
    ![Analizzare i file](../media/content-understanding/analyze.png)</br> 

3. Una volta analizzati, nella pagina **selezionare i campi del modulo che si desidera salvare** fare clic sul file per visualizzare i campi rilevati.</br>

    ![Seleziona campi modulo](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Passaggio 3: selezionare i campi del modulo

Dopo aver analizzato i documenti per i campi, è ora possibile vedere quali campi sono stati trovati e quali si desidera salvare. I campi salvati verranno visualizzati come colonne nella visualizzazione raccolta documenti del modello e verranno visualizzati i valori estratti da ogni documento.

1. Nella pagina successiva verrà visualizzato uno dei file di esempio e verranno evidenziati tutti i campi comuni che sono stati rilevati automaticamente dal sistema. </br>

    ![Seleziona campi modulo](../media/content-understanding/select-fields-page.png)</br> 

2. Selezionare i campi che si desidera salvare e selezionare la casella di controllo per confermare la selezione. Ad esempio, nel modello ordine di acquisto è possibile scegliere di selezionare i campi *Data*, *po*e *totale* .  Si noti che è anche possibile scegliere di rinominare un campo se si sceglie. </br>

    ![Seleziona PO #](../media/content-understanding/po.png)</br> 

3. Se un campo non è stato rilevato dall'analisi, è comunque possibile scegliere di aggiungerlo. Evidenziare le informazioni che si desidera estrarre e nella casella nome digitare il nome che si desidera assegnare. Selezionare quindi la casella di controllo. Tenere presente che è necessario confermare i campi non rilevati nei file di esempio rimanenti.
4. Dopo aver selezionato i campi che si desidera salvare, fare clic su **Conferma campi** . </br>
 
    ![Conferma campi](../media/content-understanding/confirm-fields.png)</br> 
 
5. Nella pagina **selezionare i campi del modulo che si desidera salvare** , verrà visualizzato il numero di campi selezionati. Scegliere **Fine**.

## <a name="step-4-train-and-test-your-model"></a>Passaggio 4: formare e testare il modello

Dopo aver selezionato i campi che si desidera salvare, la pagina di **Riepilogo del modello** consentirà di formare e testare il modello.

1. Nella pagina **Riepilogo modello** verranno visualizzati i campi salvati nella sezione **campi selezionati** . Selezionare **treno** per iniziare a eseguire la formazione sui file di esempio. Tenere presente che potrebbero essere necessari alcuni minuti per il completamento.</br>
    ![Conferma campi](../media/content-understanding/select-fields-train.png)</br> 
2. Quando viene visualizzata la notifica che la formazione è stata completata, selezionare **Vai alla pagina dei dettagli**. 
3. Nella pagina **Dettagli modello** è possibile scegliere di testare il funzionamento del modello selezionando **test rapido**. In questo modo è possibile trascinare i file nella pagina e verificare se i campi sono stati rilevati.

## <a name="step-5-publish-your-model"></a>Passaggio 5: pubblicare il modello



1. Se si è soddisfatti dei risultati del modello selezionato, fare clic su **pubblica** per renderlo disponibile per l'utilizzo.
2. Dopo la pubblicazione del modello, selezionare **Usa modello**. In questo modo viene creato un flusso PowerAutomate che verrà eseguito nella raccolta documenti di SharePoint e verranno estratti i campi che sono stati identificati nel modello. Selezionare **Crea flusso**.  
3. Al termine, verrà visualizzato il messaggio che il **flusso è stato creato correttamente**.
 
 
## <a name="step-6-use-your-model"></a>Passaggio 6: utilizzare il modello

Dopo la pubblicazione del modello e la creazione del flusso di PowerAutomate, è possibile utilizzare il modello nella raccolta documenti di SharePoint.

1. Dopo aver pubblicato il modello, selezionare **Vai a SharePoint** per andare alla raccolta documenti.
2. Nella visualizzazione modello raccolta documenti, tenere presente che i campi selezionati vengono visualizzati come colonne.</br>

    ![Raccolta documenti con modello applicato](../media/content-understanding/doc-lib-view.png)</br> 

    Si noti inoltre che il collegamento alle informazioni accanto a **documenti** noterà che un modello di elaborazione dei moduli viene applicato a questa raccolta documenti.

    ![Estratto](../media/content-understanding/info-button.png)</br>  

3. Caricare i file nella raccolta documenti. Tutti i file identificati dal modello come tipo di contenuto consentiranno di elencare i file nella visualizzazione e verranno visualizzati i dati estratti nelle colonne.</br>

    ![Estratto](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a>Vedere anche
  
[Documentazione su Power automatizzate](https://docs.microsoft.com/power-automate/)</br>
[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




