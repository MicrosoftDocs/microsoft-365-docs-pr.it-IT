---
title: Tipi di spiegazione
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Per ulteriori informazioni, vedere tipi di spiegazione in Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295994"
---
# <a name="introduction-to-explanation-types"></a>Introduzione ai tipi di spiegazione

Utilizzare spiegazioni che consentono di definire le informazioni che si desidera etichettare ed estrarre nel documento i modelli di comprensione per Microsoft SharePoint Syntex. Quando si crea una spiegazione, assicurarsi di selezionare un tipo di spiegazione. 

In questo articolo vengono fornite informazioni dettagliate sui diversi tipi di spiegazione e su come vengono utilizzati.

   ![Tipi di spiegazione](../media/content-understanding/explanation-types.png) 
   
Sono disponibili i seguenti tipi di spiegazione:

- **Elenco**delle frasi: elenco di parole, frasi, numeri o altri caratteri che è possibile utilizzare nel documento o nelle informazioni che si stanno estraendo. Ad esempio, la stringa di testo refering **Doctor** è presente in tutti i documenti di rinvio medici che si stanno identificando.</br>

- **Elenco pattern**: elenca i modelli di numeri, lettere o altri caratteri che è possibile utilizzare per identificare le informazioni che si stanno estraendo. Ad esempio, è possibile estrarre il **numero di telefono** del refering Doctor da tutto il documento di riferimento medico che si sta identificando.</br>

- **Prossimità**: in questo articolo viene descritto il modo in cui le spiegazioni sono ravvicinate. Ad esempio, un elenco dei *numeri di strada* viene visualizzato subito prima dell'elenco delle frasi del *nome della via* , senza alcun segno di interferenza (verranno illustrati i token più avanti in questo articolo). 
 
## <a name="phrase-list"></a>Elenco delle frasi

Un tipo di spiegazione per l'elenco delle frasi viene in genere utilizzato per identificare e classificare un documento tramite il modello. Come descritto nell'esempio *relativo* all'etichetta del medico di riferimento, si tratta di una stringa di parole, frasi, numeri o caratteri che è coerente nei documenti che si stanno identificando.

Anche se non è un requisito, è possibile ottenere risultati migliori con la spiegazione se la frase che si sta acquisendo si trova in una posizione coerente nel documento. Ad esempio, l'etichetta del *medico che fa riferimento* può essere posizionata in modo coerente nel primo paragrafo del documento.

Se la distinzione tra maiuscole e minuscole è un requisito per identificare l'etichetta, utilizzando il tipo di elenco delle frasi è possibile specificarlo nella spiegazione selezionando l'unica casella di controllo per la **capitalizzazione esatta** .

   ![Distinzione tra maiuscole e minuscole](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Elenchi di modelli

Un tipo di elenco dei modelli è particolarmente utile quando si crea una spiegazione che identifica ed estrae informazioni da un documento. È in genere presentato in formati diversi, ad esempio date, numeri di telefono o numeri di carta di credito. Ad esempio, è possibile visualizzare una data in vari formati (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, gen 1, 2020 e così via). La definizione di un elenco di modelli rende più efficiente la spiegazione, acquisendo le possibili varianti nei dati che si sta tentando di identificare ed estrarre. 

Per l'esempio di **numero di telefono** , estrarre il numero di telefono di ogni medico che fa riferimento a tutti i documenti di rinvio medici identificati dal modello. Quando si crea la spiegazione, selezionare il tipo di elenco dei modelli per consentire i diversi formati che è possibile prevedere di restituire.

   ![Elenco dei numeri di telefono](../media/content-understanding/pattern-list.png)

Per questo esempio, selezionare la casella **di controllo qualsiasi cifra da 0-9** . Selezionando questa impostazione si riconosce che ogni valore di "0" utilizzato nell'elenco dei modelli è qualsiasi cifra compreso tra 0 e 9.

   ![Qualsiasi cifra da 0-9](../media/content-understanding/digit-identity.png)

Analogamente, se si crea un elenco di modelli che include caratteri di testo, selezionare la casella **di controllo qualsiasi lettera da a-z** . Selezionando questa impostazione, tutti i caratteri "a" utilizzati nell'elenco dei modelli devono essere qualsiasi carattere da "a" a "z".

Ad esempio, se si crea un elenco di modelli di **Data** e si desidera verificare che venga riconosciuto un formato di data come *gen 1, 2020* , è necessario eseguire le operazioni seguenti:
- Aggiungere *AAA 0, 0000* e *AAA 00, 0000* all'elenco dei modelli.
- Verificare che sia selezionata anche **una lettera di a-z** .

   ![Qualsiasi lettera da a-z](../media/content-understanding/any-letter.png)

Inoltre, se nell'elenco dei modelli sono presenti requisiti di capitalizzazione, è possibile selezionare l'unica casella di controllo per la **capitalizzazione esatta** . Per l'esempio di data, se è necessaria la prima lettera del mese per la capitalizzazione, è necessario eseguire le operazioni seguenti:

- Aggiungere *AAA 0, 0000* e *AAA 00, 0000* all'elenco dei modelli.
- Verificare che sia selezionata anche **solo la capitalizzazione esatta** .

   ![Solo lettere maiuscole esatte](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Invece di creare manualmente una spiegazione per l'elenco dei modelli, utilizzare la [raccolta delle spiegazioni]() per utilizzare il modello di elenco schemi precostituito per l'elenco dei pattern comuni, ad esempio *Data*, *numero di telefono*, numero di *carta di credito*e così via. 

## <a name="proximity"></a>Prossimità 

Il tipo di spiegazione di prossimità aiuta il modello a identificare i dati, definendo la modalità di chiusura di un altro elemento di dati. Ad esempio, nel modello sono state definite due spiegazioni che etichettano sia il numero di *Indirizzo* del cliente che il *numero di telefono*. 

Si noti inoltre che i numeri di telefono dei clienti vengono sempre visualizzati prima del numero dell'indirizzo di strada. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Utilizzare la spiegazione di prossimità per definire la distanza tra la spiegazione del numero di telefono per identificare meglio il numero di indirizzo di strada nei documenti.

   ![Spiegazione di prossimità](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Che cosa sono i token?

Per utilizzare il tipo di spiegazione di prossimità, è necessario comprendere il valore di un token, in quanto il numero di token è il modo in cui la spiegazione di prossimità misura la distanza tra una spiegazione e un'altra.  

Un token è un intervallo continuo (senza spazi o segni di punteggiatura) di lettere e numeri. Uno spazio non è un token. Ogni carattere di punteggiatura è un token. Nella tabella seguente sono riportati alcuni esempi di come determinare il numero di token in una frase.

|Frase|Numero di token|Spiegazione|
|--|--|--|
|`Dog`|1 |Una singola parola senza punteggiatura o spazi.|
|`RMT33W`|1 |Numero di localizzatore record. Potrebbe avere numeri e lettere, ma non ha alcun segno di punteggiatura.|
|`425-555-5555`|5 |Un numero di telefono. Ogni segno di punteggiatura è un singolo token, quindi costituito  `425-555-5555` da 5 token:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7 |`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Configurare il tipo di spiegazione di prossimità

Per l'esempio, configurare l'impostazione di prossimità in modo che sia possibile definire l'intervallo del numero di token che la spiegazione del *numero di telefono* è dalla spiegazione del numero di *indirizzo di strada* .

Si dovrebbe vedere che l'intervallo minimo è "0" dato che non ci sono token tra il numero di telefono e l'indirizzo di via.

Tuttavia, alcuni numeri di telefono nei documenti di esempio vengono accodati con *(mobile)*.

Nestor Wilke<br>
111-111-1111 (cellulare)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Sono presenti tre token in *(mobile)*:

|Frase|Conteggio token|
|--|--|
|(|1 |
|Mobile|2 |
|)|3 |

Configurare l'impostazione di prossimità in modo che abbia un intervallo compreso tra 0 e 3.

   ![Esempio di prossimità](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a>Utilizzare la raccolta di spiegazioni

Anche se è possibile aggiungere manualmente vari valori dell'elenco dei modelli per la spiegazione, è molto più facile usare i modelli creati in precedenza nella raccolta di spiegazioni.

Ad esempio, invece di aggiungere manualmente tutte le varianti per *date*, utilizzare il modello di elenco dei modelli per la *Data*, che include già numerosi valori degli elenchi di modelli:</br>

   ![Raccolta di spiegazioni](../media/content-understanding/explanation-template.png)</br>
 
La raccolta di spiegazioni include una serie di spiegazioni di elenco dei modelli di uso comune, tra cui:</br>

- Data</br>
- Data (numerico)</br>
- Ora</br>
- Numero </br>
- Numero di telefono</br>
- CAP</br>
- Prima parola di frase</br>
- Carta di credito</br>
- Codice di previdenza sociale</br>

Si noti che la raccolta di spiegazioni include anche i modelli per le spiegazioni degli elenchi di frasi e, tra cui:
- Fine della frase
- Valuta

#### <a name="to-use-a-template-from-the-explanation-library"></a>Per utilizzare un modello dalla raccolta di spiegazioni

1. Nella sezione **spiegazioni** della pagina del **treno** del modello selezionare **nuovo**e quindi selezionare **da un modello**.</br>

   ![Crea da modello](../media/content-understanding/from-template.png)</br>

2.  Nella pagina **modelli spiegazione** selezionare la spiegazione che si desidera utilizzare e quindi fare clic su **Aggiungi**.</br>

       ![Selezionare un modello](../media/content-understanding/phone-template.png)</br>

3. Le informazioni per il modello selezionato verranno visualizzate nella pagina **Crea una spiegazione** . Se necessario, modificare il nome della spiegazione e aggiungere o rimuovere elementi dall'elenco dei modelli. </br> 

   ![Modifica modello](../media/content-understanding/phone-template-live.png)</br>

4. Al termine, fare clic su **Salva**.
