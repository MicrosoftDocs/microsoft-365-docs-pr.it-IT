---
title: Creare un estrattore
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
description: Informazioni su come creare un estrattore in Microsoft SharePoint Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295457"
---
# <a name="create-an-extractor-preview"></a>Creare un estrattore (anteprima)

Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Prima o dopo la creazione di un modello di classificazione per automatizzare l'identificazione e la classificazione di tipi di documento specifici, è possibile scegliere di aggiungere estrattori al modello per estrarre informazioni specifiche da tali documenti. Ad esempio, è possibile che il modello non solo identifichi tutti i documenti di *rinnovo del contratto* aggiunti alla raccolta documenti, ma anche per visualizzare la data di *inizio del servizio* per ogni documento come colonna nella raccolta documenti.

È necessario creare un estrattore per ogni entità del documento che si desidera estrarre. Nell'esempio, si desidera estrarre la data di *inizio del servizio* per ogni documento di *rinnovo del contratto* identificato dal modello. Questa operazione deve essere eseguita quando si desidera visualizzare una visualizzazione nella raccolta documenti di tutti i documenti di *rinnovo del contratto* con una colonna che mostra il valore della data di inizio del servizio per ogni documento.

> [!NOTE]
> Prima di creare un estrattore, è necessario [aggiungere i file di esempio](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) per agevolare il training del modello per identificare le informazioni che si desidera estrarre. Utilizzare gli stessi file di esempio utilizzati per creare il classificatore.

## <a name="name-your-extractor"></a>Assegnare un nome all'estrattore

1. Nella sezione **Crea e addestra estrattori** della Home page del modello fare clic su **Train Extractor**.
2. Nella schermata **nuovo estrattore di entità** , digitare il nome dell'estrattore nel campo **nuovo nome estrattore** . Ad esempio, denominarlo **Data di inizio del servizio** se si desidera estrarre la data di inizio del servizio da ogni documento di rinnovo del contratto.
3. Fare clic su **Crea**.

## <a name="add-a-label"></a>Aggiungere un'etichetta

Il passaggio successivo consiste nell'assegnare un'etichetta alle informazioni che si desidera estrarre nei file di addestramento di esempio.

La creazione dell'estrattore apre la pagina estrattore. Di seguito viene mostrato un elenco dei file di esempio, con il primo file nell'elenco visualizzato nel visualizzatore.

1. Dal Visualizzatore selezionare i dati che si desidera estrarre dai file. Ad esempio, se si desidera estrarre la *Data di inizio del servizio*, è necessario evidenziare il valore data nel primo file (*lunedì 14 ottobre 2019*). e quindi fare clic su **Salva**.  Nella colonna **Label** dovrebbe essere visualizzato il valore visualizzato nel file nell'elenco degli esempi etichettati.
2. Selezionare il **file successivo** per il salvataggio automatico e aprire il file successivo nell'elenco nel visualizzatore. Oppure seleziona **Salva** e quindi seleziona un altro file dall'elenco degli **esempi etichettati** .
3. Nel Visualizzatore, ripetere i passaggi 1 e 2, quindi ripetere fino a quando non è stata salvata l'etichetta in tutti e cinque i file.

    ![Impostazioni avanzate](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a>Aggiungere un esempio negativo

Analogamente alla modalità di aggiunta di un file di esempio negativo durante la creazione di un classificatore, è necessario aggiungere un campione negativo per l'estrattore. Dovrebbe essere un file che non contiene un valore di data di inizio del servizio.

1. Nell'elenco **esempi etichettati** selezionare un esempio negativo.
2. Nel Visualizzatore all'inizio dell'articolo selezionare **Nessuna etichetta presente**.
3. Fare clic su **Salva**.
 
Dopo aver identificato cinque file, viene visualizzato un banner di notifica che informa di passare all'allenamento. È possibile scegliere di visualizzare più documenti o passare all'allenamento. 

## <a name="add-an-explanation"></a>Aggiungere una spiegazione

In questo esempio viene creata una spiegazione che fornisce un suggerimento relativo al formato di entità stesso e alle varianti che può avere nei documenti di esempio. Ad esempio, un valore date può essere in un certo numero di formati diversi, come:
- 10/14/2019
- 14 ottobre 2019
- Lunedì 14 ottobre 2019
 

Per identificare la *Data di inizio del servizio* , è possibile creare una spiegazione del modello.

1. Nella sezione spiegazione selezionare **nuovo** e digitare un nome, ad esempio *Data*.
2. Per tipo, selezionare **elenco modelli**.
3. Per valore, specificare la variazione di data come viene visualizzata nei file di esempio. Ad esempio, se si dispone di formati di data visualizzati come 0/00/0000, si immettono tutte le varianti presenti nei documenti, quali:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Selezionare **Salva**.

### <a name="use-the-explanation-library"></a>Utilizzare la raccolta di spiegazioni

Per la creazione di spiegazioni per gli elementi, ad esempio le date, è più facile usare la libreria delle spiegazioni piuttosto che immettere manualmente tutte le varianti. La raccolta di spiegazioni è un insieme di spiegazioni di modelli e frasi predefinite. La raccolta fornisce tutti i formati per gli elenchi di frasi o schemi comuni, ad esempio le date, i numeri di telefono, il CAP e così via. 

Per l'esempio di *Data di inizio del servizio* , è più efficiente utilizzare la spiegazione predefinita per la *Data* nella raccolta di spiegazioni:

1. Nella **sezione spiegazione**selezionare **nuovo**e quindi fare clic su **dalla raccolta delle spiegazioni**.
2. Nella raccolta delle spiegazioni selezionare **Data**. È possibile visualizzare tutte le varianti di data riconosciute.
3. Selezionare **Aggiungi**.</br>

    ![Raccolta di spiegazioni](../media/content-understanding/explanation-library.png) 

4. Nella pagina **Crea una spiegazione** le informazioni relative alla *Data* della raccolta delle spiegazioni vengono riempite automaticamente dai campi. Selezionare **Salva**.</br>

    ![Data](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a>Addestramento del modello 

Salvataggio delle spiegazioni avviare la formazione. Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, verranno visualizzati tutti i file contrassegnati con la **corrispondenza**.  

![Match](../media/content-understanding/match2.png) 

Se la spiegazione non contiene informazioni sufficienti per individuare i dati che si desidera estrarre, ogni file verrà etichettato con la **mancata corrispondenza**. È possibile fare clic sui file non **corrispondenti** per visualizzare altre informazioni sul motivo della mancata corrispondenza.


## <a name="add-another-explanation"></a>Aggiungere un'altra spiegazione

Spesso la mancata corrispondenza indica che la spiegazione fornita non ha fornito informazioni sufficienti per estrarre il valore della data di inizio del servizio in modo che corrisponda ai file etichettati. Potrebbe essere necessario modificarlo oppure aggiungere un'altra spiegazione.

Per l'esempio, si noti che la *Data di inizio del servizio della stringa di* testo precede sempre il valore effettivo. Per identificare la data di inizio del servizio, è necessario creare una spiegazione per la frase.

1. Nella sezione spiegazione selezionare **nuovo**e quindi digitare un nome, ad esempio *stringa di prefisso*.
2. Per il tipo selezionare l' **elenco delle frasi**.
3. Utilizzare la *Data di inizio del servizio* come valore.
4. Selezionare **Salva**.

    ![Stringa di prefisso](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a>Eseguire di nuovo il training del modello

Salvando la spiegazione viene riavviata la formazione, questa volta utilizzando entrambe le spiegazioni del campione. Se il modello contiene informazioni sufficienti per estrarre i dati dai file di esempio etichettati, è possibile visualizzare ogni file con l'etichetta **corrispondente**. 

Se si riceve di nuovo una **mancata corrispondenza** nei file etichettati, è probabile che sia necessario creare un'altra spiegazione per fornire al modello ulteriori informazioni per identificare il tipo di documento oppure prendere in considerazione le modifiche apportate al modello di esempio.

## <a name="test-your-model"></a>Testare il modello

Se si riceve una corrispondenza nei file di esempio etichettati, è ora possibile testare il modello nei file di esempio senza etichetta rimanenti.

1. Nella Home page del modello fare clic sulla scheda **test** .  Questo esegue il modello nei file di esempio senza etichetta.
2. Nell'elenco **file di test** , i file di esempio vengono visualizzati per mostrare se il modello è in grado di estrarre le informazioni necessarie. Utilizzare queste informazioni per determinare l'efficacia del classificatore per identificare i documenti.

    ![Test sui file](../media/content-understanding/test-filies-extractor.png) 
