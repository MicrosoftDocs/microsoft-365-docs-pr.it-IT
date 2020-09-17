---
title: Creare un estrattore (anteprima)
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
description: Informazioni su come creare un estrattore
ms.openlocfilehash: 7219726fb385d0b67f7ee0614f5075ba226140ab
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950085"
---
# <a name="create-an-extractor-preview"></a>Creare un estrattore (anteprima)
> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Prima o dopo aver creato un modello di classificazione per automatizzare l'identificazione e la classifica dei tipi di documento specifici, è possibile scegliere di aggiungere estrattori al modello per estrarre informazioni specifiche da tali documenti. Ad esempio, è possibile che il modello non solo identifichi tutti i documenti di *rinnovo del contratto* aggiunti alla raccolta documenti, ma visualizzi anche la data di *inizio del servizio* per ogni documento come colonna nella raccolta documenti.

È necessario creare un estrattore per ogni entità del documento che si desidera estrarre. In questo esempio, si desidera estrarre la *Data di inizio del servizio* per ogni documento di rinnovo del *contratto* identificato dal modello. Si desidera essere in grado di visualizzare una visualizzazione nella raccolta documenti di tutti i documenti di *rinnovo del contratto* , con una colonna che Visualizza il valore di data di inizio del servizio di ogni documento.

> [!Note]
> Prima di creare un estrattore, è necessario [aggiungere i file di esempio](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) necessari per addestrare il modello per identificare le informazioni che si desidera estrarre. Utilizzare gli stessi file di esempio utilizzati per creare il classificatore.


## <a name="name-your-extractor"></a>Assegnare un nome all'estrattore

1. Nella sezione **Crea e addestra estrattori** della Home page del modello fare clic su **Train Extractor**.
2. Nella schermata **nuovo estrattore di entità** , digitare il nome dell'estrattore nel campo **nuovo nome estrattore** . Ad esempio, è possibile denominarlo **Data di inizio del servizio** se si desidera estrarre la data di inizio del servizio da ogni documento di rinnovo del contratto.
3. Fare clic su **Crea**.

## <a name="add-a-label"></a>Aggiungere un'etichetta

Il passaggio successivo consiste nell'assegnare un'etichetta alle informazioni che si desidera estrarre nei file di training di esempio.

Se si crea l'estrattore, verrà aperta la pagina estrattore in cui verrà visualizzato un elenco dei file di esempio, con il primo file nell'elenco mostrato nel visualizzatore.

1. Nel Visualizzatore selezionare i dati che si desidera estrarre dai file. Ad esempio, se si desidera estrarre la *Data di inizio del servizio*, si evidenzierà il valore della data per il primo file (*lunedì 14 ottobre 2019*). Fare quindi clic su **Salva**.  Verrà visualizzata la visualizzazione del valore per il file nell'elenco degli esempi etichettati sotto la colonna **etichetta** .
2. Selezionare il **file successivo** per il salvataggio automatico e aprire il file successivo nell'elenco nel Visualizzatore oppure è possibile selezionare **Salva** e selezionare un altro file nell'elenco **esempi etichettati** .
3. Nel Visualizzatore, ripetere i passaggi 1 e 2 e procedere fino a quando non è stata salvata l'etichetta in cinque file.

    ![Impostazioni avanzate](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a>Aggiungere un esempio negativo

Analogamente alla modalità di aggiunta di un file di esempio negativo durante la creazione di un classificatore, è necessario aggiungere un esempio negativo per l'estrattore. Ad esempio, dovrebbe trattarsi di un file che non contiene un valore di data di inizio del servizio.

1. Nell'elenco **esempi etichettati** selezionare un esempio negativo.
2. Nel Visualizzatore, nella parte superiore dell'articolo, selezionare **no label present**.
3. Fare clic su **Salva**.
 
Dopo aver identificato cinque file, verrà visualizzato un banner di notifica che informa di passare all'allenamento. È possibile scegliere di visualizzare più documenti o passare all'allenamento. 

## <a name="add-an-explanation"></a>Aggiungere una spiegazione

Ad esempio, viene creata una spiegazione che fornisce un suggerimento relativo al formato di entità e alle varianti che può avere nei documenti di esempio. Ad esempio, un valore date può essere in un certo numero di formati diversi, come:
- 10/14/2019
- 14 ottobre 2019
- Lunedì 14 ottobre 2019
 

Per identificare la *Data di inizio del servizio* , è possibile creare una descrizione del modello.

1. Nella sezione spiegazione selezionare **nuovo**e quindi digitare un nome, ad esempio *Data*.
2. Per il tipo, selezionare **elenco modelli**.
3. Per il valore, è necessario fornire la variazione di data come vengono visualizzati nei file di esempio. Ad esempio, se si dispone di formati di data visualizzati come 0/00/0000, è necessario immettere qualsiasi variante che potrebbe essere visualizzata nei documenti, come:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Seleziona **Salva**.


### <a name="use-the-explanation-library"></a>Utilizzare la raccolta di spiegazioni

Per la creazione di spiegazioni per elementi quali date, è molto più facile usare la libreria delle spiegazioni piuttosto che immettere manualmente tutte le varianti. La raccolta di spiegazioni è un insieme di spiegazioni di modelli e frasi predefinite. La raccolta cerca di fornire tutti i formati per gli elenchi di frasi o schemi comuni, ad esempio date, numeri di telefono, CAP e molti altri. 

Per l'esempio di *Data di inizio del servizio* , è più efficiente utilizzare la spiegazione predefinita per la *Data* nella raccolta di spiegazioni:

1. Nella **sezione spiegazione**, * * selezionare **nuovo**e quindi selezionare **dalla raccolta di spiegazioni**.
2. Nella raccolta delle spiegazioni selezionare **Data**. È possibile visualizzare tutte le varianti di data che verranno riconosciute.
3. Selezionare **Aggiungi**.</br>

    ![Raccolta di spiegazioni](../media/content-understanding/explanation-library.png) 

4. Nella pagina **Crea una spiegazione** le informazioni relative alla *Data* della raccolta delle spiegazioni verranno riempite automaticamente nei campi. Seleziona **Salva**.</br>

    ![Raccolta di spiegazioni](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a>Addestramento del modello 

Il salvataggio delle spiegazioni inizierà la formazione. Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, verranno visualizzati tutti i file contrassegnati con la **corrispondenza**.  

![Raccolta di spiegazioni](../media/content-understanding/match2.png) 

Se la spiegazione non contiene informazioni sufficienti per individuare i dati che si desidera estrarre, ogni file verrà etichettato con la **mancata corrispondenza**. È possibile fare clic sui file non corrispondenti per visualizzare altre informazioni sul motivo della mancata corrispondenza.


## <a name="add-another-explanation"></a>Aggiungere un'altra spiegazione

Spesso la mancata corrispondenza indica che la spiegazione fornita non ha fornito informazioni sufficienti per estrarre il valore della data di inizio del servizio in modo che corrisponda ai file etichettati. Potrebbe essere necessario modificarlo oppure aggiungere un'altra spiegazione.

Ad esempio, si noti che la stringa di testo *inizia la data di servizio di* sempre precede il valore effettivo. Per identificare la data di inizio del servizio, è possibile creare una spiegazione delle frasi.

1. Nella sezione spiegazione selezionare **nuovo**e quindi digitare un nome, ad esempio *stringa di prefisso*.
2. Per il tipo selezionare l' **elenco delle frasi**.
3. Utilizzare la *Data di inizio del servizio* come valore.
4. Seleziona **Salva**.

    ![Raccolta di spiegazioni](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a>Addestramento del modello

Se si salva la spiegazione, la formazione verrà riavviata, questa volta utilizzando entrambe le spiegazioni in questo esempio. Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, verranno visualizzati tutti i file contrassegnati con la **corrispondenza**. 

Se si riceve di nuovo una **mancata corrispondenza** nei file contrassegnati, potrebbe essere necessario creare un'altra spiegazione per fornire al modello ulteriori informazioni per identificare il tipo di documento oppure esaminare le modifiche apportate a quelle esistenti.

## <a name="test-your-model"></a>Testare il modello

Se è stata ricevuta una corrispondenza nei file di esempio contrassegnati, è ora possibile testare il modello nei file di esempio senza etichetta rimanenti.

1. Nella Home page del modello fare clic sulla scheda **test** .  Verrà eseguito il modello nei file di esempio senza etichetta.
2. Nell'elenco **file di test** , i file di esempio verranno visualizzati e mostreranno se il modello è in grado di estrarre le informazioni necessarie. È possibile utilizzare queste informazioni per determinare l'efficacia del classificatore per identificare i documenti.

    ![Test sui file](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a>Vedere anche
  




