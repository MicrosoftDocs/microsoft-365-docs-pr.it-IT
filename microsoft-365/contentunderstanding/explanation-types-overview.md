---
title: Tipi di spiegazione
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni sui tipi di spiegazione in Microsoft SharePoint Syntex
ms.openlocfilehash: 43272504912451e4690cb8b7fe351462371bb252
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350304"
---
# <a name="introduction-to-explanation-types"></a>Introduzione ai tipi di spiegazione

Le spiegazioni vengono usate per definire meglio le informazioni da etichettare ed estrarre nei modelli di analisi dei documenti in Microsoft SharePoint Syntex. Quando si crea una spiegazione, è necessario selezionare un tipo di spiegazione. Questo articolo contiene informazioni utili per comprendere meglio i diversi tipi di spiegazione e come vengono usati. 

   ![Tipi di spiegazione](../media/content-understanding/explanation-types.png) 
   
Sono disponibili questi tipi di spiegazione:

- **Elenco frasi**: elenco di parole, frasi, numeri o altri caratteri che è possibile usare nel documento o nelle informazioni che si stanno estraendo. Ad esempio, la stringa di testo **Medico richiedente** è inclusa in tutti i documenti di richiesta di visita specialistica che si stanno identificando.</br>

- **Elenco criteri**: elenco di criteri di numeri, lettere o altri caratteri usati per identificare le informazioni che si stanno estraendo. Ad esempio, è possibile estrarre il **numero di telefono** del medico richiedente da tutti i documenti di richiesta di visita specialistica che si stanno identificando.</br>

- **Prossimità**: descrive la relazione di prossimità tra le spiegazioni. Ad esempio, un elenco criteri *numero civico* precede immediatamente l'elenco di frasi *nome della via*, senza token intermedi (i token verranno illustrati più avanti in questo articolo). Se si usa il tipo di prossimità, il modello deve includere almeno due spiegazioni, altrimenti l'opzione verrà disabilitata. 
 
## <a name="phrase-list"></a>Elenco frasi

Il tipo di spiegazione elenco frasi viene usato generalmente per identificare e classificare un documento tramite il modello. Come descritto nell'esempio di etichetta *Medico richiedente*, si tratta di una stringa di parole, frasi, numeri o caratteri presente costantemente nei documenti che si stanno identificando.

Anche se non è necessario, la spiegazione risulta più efficace se la frase acquisita si trova in una posizione ricorrente nel documento. Ad esempio, l'etichetta *Medico richiedente* potrebbe essere situata sempre nel primo paragrafo del documento.

Se la distinzione tra maiuscole e minuscole è un requisito per identificare l'etichetta, il tipo elenco frasi consente di specificarlo nella spiegazione selezionando la casella di controllo **Solo le maiuscole esatte**.

   ![Distinzione tra maiuscole e minuscole](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Elenchi di criteri

Il tipo elenco criteri risulta particolarmente utile quando si crea una spiegazione che identifica ed estrae informazioni da un documento. Generalmente viene presentato in vari formati, come date, numeri di telefono o numeri di carte di credito. Ad esempio, una data può essere visualizzata in diversi formati (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 gen 2020 e così via). La definizione di un elenco di criteri rende più efficace la spiegazione attraverso l'acquisizione di tutte le possibili varianti nei dati che si sta provando a identificare ed estrarre. 

Per l'esempio relativo al **numero di telefono**, estrarre il numero di telefono per ogni medico richiedente da tutti i documenti di richiesta di visita specialistica identificati dal modello. Quando si crea la spiegazione, selezionare il tipo Elenco criteri affinché vengano restituiti i vari formati previsti.

   ![Elenco criteri numero di telefono](../media/content-understanding/pattern-list.png)

Per questo esempio, selezionare la casella di controllo **Qualsiasi cifra da 0 a 9**. Se si seleziona questa opzione, ogni valore "0" usato nell'elenco di criteri verrà riconosciuto come qualsiasi cifra compresa tra 0 e 9.

   ![Qualsiasi cifra da 0 a 9](../media/content-understanding/digit-identity.png)

Analogamente, se si crea un elenco di criteri che include caratteri di testo, selezionare la casella di controllo **Qualsiasi lettera dalla a alla z**. Se si seleziona questa opzione, ogni carattere "a" usato nell'elenco di criteri verrà riconosciuto come qualsiasi carattere dalla "a" alla "z".

Ad esempio, se si crea un elenco di criteri **Data** e si vuole fare in modo che venga riconosciuto un formato di data come *1 gen 2020*, è necessario:
- Aggiungere *0 aaa 0000* e *00 aaa 0000* all'elenco criteri.
- Assicurarsi che sia selezionata anche l'opzione **Qualsiasi lettera dalla a alla z**.

   ![Qualsiasi lettera dalla a alla z](../media/content-understanding/any-letter.png)

Inoltre, se l'elenco criteri prevede requisiti per le maiuscole, è possibile selezionare la casella di controllo **Solo le maiuscole esatte**. Per l'esempio relativo alla data, se il mese deve avere l'iniziale minuscola, è necessario:

- Aggiungere *0 aaa 0000* e *00 aaa 0000* all'elenco criteri.
- Assicurarsi che sia selezionata anche l'opzione **Solo le maiuscole esatte**.

   ![Solo le maiuscole esatte](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Anziché creare manualmente una spiegazione elenco criteri, usare la [raccolta spiegazioni](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) per usare modelli di elenchi di criteri predefiniti per elenchi di criteri comuni, quali *data*, *numero di telefono*, *numero di carta di credito* e così via. 

## <a name="proximity"></a>Prossimità 

Il tipo di spiegazione prossimità consente al modello di identificare i dati definendo il rapporto di prossimità rispetto ad altri dati. Nel modello, ad esempio, sono state definite due spiegazioni che etichettano il *Numero civico* e il *Numero di telefono* del cliente. 

Si nota anche che i numeri di telefono del cliente vengono sempre visualizzati sempre prima del numero civico. 

Davide Milano<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Usare la spiegazione di prossimità per definire quanto è lontana la spiegazione del numero di telefono, per identificare meglio il numero civico nei documenti.

   ![Spiegazione di prossimità](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Che cosa sono i token?

Per usare il tipo di spiegazione di prossimità, è necessario comprendere che cos'è un token perché il numero di token è il sistema usato dalla spiegazione di prossimità per misurare la distanza tra una spiegazione e l'altra.  

Un token è una serie continua di lettere e numeri, senza spazi o punteggiatura. Uno spazio NON è un token. Ogni segno di punteggiatura è un token. Nella tabella seguente sono illustrati alcuni esempi per determinare il numero di token in una frase.

|Frase|Numero di token|Spiegazione|
|--|--|--|
|`Dog`|1|Una singola parola senza punteggiatura o spazi.|
|`RMT33W`|1|Un numero di localizzazione record. Può contenere numeri e lettere, ma non include segni di punteggiatura.|
|`425-555-5555`|5|Un numero di telefono. Ogni segno di punteggiatura è un token, quindi `425-555-5555` corrisponderebbe a 5 token:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Configurare il tipo di spiegazione di prossimità

Per l'esempio, configurare l'impostazione di prossimità in modo da poter definire l'intervallo del numero di token di distanza tra la spiegazione *Numero di telefono* e la spiegazione *Numero civico*.

L'intervallo minimo dovrebbe risultare "0" perché non c'è nessun token tra il numero di telefono e il numero civico.

Dopo alcuni numeri di telefono nei documenti di esempio, invece, è presente la dicitura *(cellulare)*.

Luca Udinesi<br>
111-111-1111 (cellulare)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

In *(cellulare)* sono presenti tre token:

|Frase|Numero di token|
|--|--|
|(|1|
|cellulare|2|
|)|3|

Configurare l'impostazione di prossimità su un intervallo compreso tra 0 e 3.

   ![Esempio di prossimità](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a>Usare modelli di spiegazione

Anche se è possibile aggiungere manualmente vari valori dell'elenco di criteri per la spiegazione, può essere molto più semplice usare i modelli predefiniti disponibili nella raccolta di spiegazioni.

Ad esempio, invece di aggiungere manualmente tutte le varianti per *Data*, è possibile usare il modello di elenco pattern per *Data*, che include già molti valori di elenchi di criteri:</br>

   ![Raccolta di spiegazioni](../media/content-understanding/explanation-template.png)</br>
 
La raccolta di spiegazioni include una serie di spiegazioni elenco di criteri di uso comune, tra cui:</br>

- Data</br>
- Data (numerico)</br>
- Ora</br>
- Numero</br>
- Numero di telefono</br>
- CAP</br>
- Prima parola della frase</br>
- Carta di credito</br>
- Numero di previdenza sociale</br>

Si noti che la raccolta di spiegazioni include anche modelli per le spiegazioni elenco di frasi, tra cui:
- Fine della frase
- Valuta

#### <a name="to-use-a-template-from-the-explanation-library"></a>Per usare un modello dalla raccolta di spiegazioni

1. Nella sezione **Spiegazioni** della pagina **Avvia training** del modello selezionare **Nuovo**, quindi **Da un modello**.</br>

   ![Crea da modello](../media/content-understanding/from-template.png)</br>

2.  Nella pagina **Modelli di spiegazione** selezionare la spiegazione da usare, quindi selezionare **Aggiungi**.</br>

       ![Selezionare un modello](../media/content-understanding/phone-template.png)</br>

3. Le informazioni relative al modello selezionato verranno visualizzate nella pagina **Crea spiegazione**. Se necessario, modificare il nome della spiegazione e aggiungere o rimuovere voci nell'elenco criteri. </br> 

   ![Modifica modello](../media/content-understanding/phone-template-live.png)</br>

4. Al termine, selezionare **Salva**.
