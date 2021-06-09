---
title: Tenere traccia dell'analisi di rilevanza in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come visualizzare e interpretare lo stato di formazione per la pertinenza e i risultati per i problemi relativi ai casi in Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769181"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a>Tenere traccia dell'analisi di rilevanza in Advanced eDiscovery
  
In Advanced eDiscovery, nella scheda Traccia di pertinenza viene visualizzata la validità calcolata del training di pertinenza eseguito nella scheda Tag e viene indicato il passaggio successivo da eseguire nel processo di formazione iterativa in Pertinenza. 
  
## <a name="tracking-relevance-training-status"></a>Monitoraggio dello stato di formazione per la pertinenza

1. Visualizzare i dettagli seguenti in Traccia di pertinenza per i problemi relativi ai casi, come illustrato nell'esempio seguente di una finestra di dialogo Nome **problema** riportata di seguito.

   - **Valutazione**: questo indicatore di stato mostra in che misura il training di pertinenza eseguito fino a questo punto ha raggiunto l'obiettivo di valutazione in termini di margine di errore. Viene inoltre visualizzata la ricchezza dei risultati di formazione per la pertinenza.

   - **Formazione:** questo indicatore di stato con codice a colori e la descrizione comando indicano la stabilità dei risultati del training per la pertinenza e una scala numerica che mostra il numero di esempi di formazione per la pertinenza contrassegnati per ogni problema. L'esperto monitora l'avanzamento del processo iterativo di formazione sulla rilevanza. 
  
   - **Calcolo batch:** questo indicatore di stato fornisce informazioni sul completamento del calcolo batch.
  
   - **Passaggio successivo**: visualizza il suggerimento per il passaggio successivo da eseguire. 
  
    Nell'esempio viene visualizzata una valutazione completata correttamente per un problema, indicata dall'indicatore di stato del colore completato e dal segno di spunta. È in corso il tagging, ma il caso è ancora considerato instabile (lo stato di stabilità viene visualizzato anche in una descrizione comando). Il passaggio successivo è "Training". 
  
    ![Fase 1 del corso di formazione sulla traccia di pertinenza](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    La visualizzazione espansa visualizza informazioni e opzioni aggiuntive. Il margine di errore corrente visualizzato è il margine di errore del richiamo nello stato corrente di valutazione, dati i file di valutazione esistenti (già contrassegnati).
  
    > [!NOTE]
    >  La fase di valutazione può essere ignorata deselezionando la casella **di** controllo Valutazione per ogni problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non ci saranno statistiche per questo problema. > la casella di controllo **Valutazione** può essere eseguita solo prima dell'esecuzione della valutazione. Se in un caso esistono più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema 
  
    Quando la valutazione non viene completata con il primo set di file di esempio, la valutazione potrebbe essere il passaggio successivo per contrassegnare più file.
  
    In **Traccia di rilevanza,** l'indicatore di avanzamento del training e la descrizione comando indicano il numero stimato di campioni aggiuntivi necessari per \> raggiungere la stabilità. Questa stima fornisce una linea guida per la formazione aggiuntiva necessaria.
  
    ![Corso di formazione sulla traccia di pertinenza](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Al termine del tagging e se è necessario continuare la formazione, fare clic su **Formazione**. Un altro set di file di esempio viene generato dal set di file caricato per ulteriore formazione. Viene quindi restituita la scheda Tag per contrassegnare e formare altri file.

### <a name="reaching-stable-training-levels"></a>Raggiungere livelli di formazione stabili

Dopo che i file di valutazione hanno raggiunto un livello stabile di formazione, Advanced eDiscovery è pronto per il calcolo batch.
  
> [!NOTE]
> In genere, dopo tre campioni di formazione stabili, il passaggio successivo è "Calcolo batch". Possono esserci eccezioni, ad esempio, quando sono state apportate modifiche al tagging dei file di esempi precedenti o quando sono stati aggiunti file di seeding. 
  
### <a name="performing-batch-calculation"></a>Esecuzione del calcolo batch

Il calcolo batch viene eseguito come passaggio successivo dopo il completamento dell'addestramento (quando viene visualizzato uno stato di formazione stabile dall'indicatore di stato, un segno di spunta e uno stato stabile nella descrizione comando). Il calcolo batch applica le conoscenze acquisite durante la formazione sulla pertinenza all'intera popolazione di file, per valutare la pertinenza dei file e per assegnare i punteggi di pertinenza.
  
Quando è presente più di un problema, il calcolo batch viene eseguito per ogni problema. Durante il calcolo batch, l'avanzamento viene monitorato durante l'elaborazione di tutti i file. 
  
In questo caso, il passaggio successivo consigliato è "None", che indica che non è necessario un ulteriore training iterativo per la pertinenza a questo punto. La fase successiva è la **scheda \> Pertinenza Decidi.** 
  
Se si desidera importare nuovi file dopo il calcolo batch, l'amministratore può aggiungere i file importati a un nuovo carico.
  
> [!NOTE]
> Se si fa **clic su Annulla** durante il calcolo batch, il processo salva ciò che è già stato eseguito. Se si esegue di nuovo il calcolo batch, il processo continuerà dall'ultimo punto eseguito. 
  
### <a name="assessing-tagging-consistency"></a>Valutazione della coerenza dei tag

Se sono presenti incoerenze nel tagging dei file, può influire sull'analisi. Il Advanced eDiscovery di coerenza dei tag può essere utilizzato quando i risultati non sono ottimali o se la coerenza è in dubbio. Viene restituito un elenco dei possibili file contrassegnati in modo incoerente e possono essere esaminati e ritantati, se necessario.
  
> [!NOTE]
> Dopo sette o più round di formazione dopo la valutazione, la coerenza dei tag può essere visualizzata in **Pertinenza** \> **Track** \> **Issue** \> **Detailed results** Training \> **progress**. Questa revisione viene eseguita per un problema alla volta.
  
1. In **Traccia di \> pertinenza** espandere la riga di un problema.
  
2. A destra di **Passaggio successivo** fare clic su **Modifica.**
  
3. Seleziona **Tag incoerenze** come opzione Passaggio **successivo,** dopo sette esempi di formazione e fai clic su **OK.**
  
4. Selezionare **Incoerenze tag.** Verrà **visualizzata** la scheda Tag con un elenco delle incoerenze da ritagare in base alle esigenze.
  
5. Fare **clic su** Calcola per inviare le modifiche. Il passaggio successivo dopo l'applicazione di tag alle incoerenze è "Formazione". 
  
## <a name="viewing-and-using-relevance-results"></a>Visualizzazione e utilizzo dei risultati di pertinenza

Nella scheda **Traccia di \> pertinenza** espandere la riga di un problema e accanto a **Risultati dettagliati** fare clic su **Visualizza.** Vengono visualizzati i riquadri dei risultati dettagliati, come illustrato e descritto di seguito.
  
![Risultati dettagliati della formazione sulla pertinenza](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Riepilogo tagging

 Nell'esempio riportato di seguito, nel riepilogo **tagging** vengono visualizzati i totali per ogni processo di tagging dei file di valutazione, formazione e di ripristino.
  
![Riepilogo tagging della traccia di pertinenza](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Parole chiave

Una parola chiave è una stringa univoca, una parola, una frase o una sequenza di parole in un file identificato da Advanced eDiscovery come indicatore significativo dell'eventuale pertinente di un file. La parola chiave dell'elenco di colonne "Includi" e i pesi nei file contrassegnati come rilevanti e le colonne "Escludi" elencano parole chiave e pesi nei file contrassegnati come Non rilevante.
  
Advanced eDiscovery assegna valori negativi o positivi del peso delle parole chiave. Maggiore è il peso, maggiore è la probabilità che a un file in cui viene visualizzata la parola chiave venga assegnato un punteggio di rilevanza più alto durante il calcolo batch.
  
L Advanced eDiscovery di parole chiave può essere usato per integrare un elenco creato da un esperto o come controllo di sanità mentale indiretta in qualsiasi momento del processo di revisione dei file.
  
### <a name="training-progress"></a>Avanzamento della formazione

Il **riquadro Avanzamento formazione** include un grafico sullo stato di avanzamento del training e la visualizzazione dell'indicatore di qualità, come illustrato nell'esempio seguente.
  
![Stato di avanzamento del corso di formazione sulla traccia di pertinenza](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
**Indicatore qualità formazione**: Visualizza la classificazione della coerenza di tagging nel modo seguente:
  
- **Buona:** i file sono contrassegnati in modo coerente. (Luce verde visualizzata)
  
- **Medio:** alcuni file potrebbero essere contrassegnati in modo incoerente. (Luce gialla visualizzata)

- **Avviso:** molti file potrebbero essere contrassegnati in modo incoerente. (Luce rossa visualizzata)

**Grafico dello stato di** avanzamento della formazione : mostra il grado di stabilità del training di rilevanza dopo molti cicli di formazione per la pertinenza rispetto al valore di misurazione F. Quando ci spostiamo da sinistra a destra nel grafico, l'intervallo di confidenza si restringe e viene usato, insieme alla misura F, da Advanced eDiscovery Relevance per determinare la stabilità quando i risultati del training per la pertinenza sono ottimizzati.
  
> [!NOTE]
> Per la pertinenza viene utilizzato F2, una metrica di misurazione F in cui il richiamo riceve il doppio del peso della precisione. Per i casi di elevata ricchezza (oltre il 25%), per rilevanza viene utilizzato F1 (rapporto 1:1). Il rapporto di misurazione F può essere configurato in **Configurazione per pertinenza** \> **Impostazioni avanzate.**
  
### <a name="batch-calculation-results"></a>Risultati del calcolo batch

Il **riquadro Risultati calcolo batch** include il numero di file con punteggio per Rilevanza, come indicato di seguito: 
  
- **Esito positivo**
  
- **Vuoto**: non contiene testo, ad esempio solo spazi/tabulazioni
  
- **Failed**: A causa di dimensioni eccessive o non è stato possibile leggere
  
- **Ignorato:** a causa di dimensioni eccessive
  
- **Nebuloso:** contiene testo senza significato o nessuna funzionalità rilevante per il problema
  
> [!NOTE]
> Vuoto, Non riuscito, Ignorato o Nebuloso riceverà un punteggio di pertinenza pari a -1.
  
### <a name="training-statistics"></a>Statistiche di formazione

Nel **riquadro Statistiche formazione** vengono visualizzate statistiche e grafici in base ai risultati Advanced eDiscovery formazione sulla pertinenza. 
  
![Statistiche del corso di formazione sulla traccia di pertinenza](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Questa visualizzazione mostra quanto segue:
  
- **Rapporto revisione-richiamo**: confronto dei risultati in base ai punteggi di pertinenza in una revisione ipoteticamente lineare. Il richiamo viene stimato in base al set di dimensioni impostato per la revisione.
  
- **Parametri**: statistiche calcolate cumulative relative al set di revisione in relazione alla popolazione di file per l'intero caso.
  
- **Review:** percentuale di file da esaminare in base a questo limite.
  
- **Richiamo:** percentuale di file rilevanti nel set di revisioni. 
  
- **Distribuzione in base al punteggio di pertinenza**: i file nella visualizzazione grigio scuro a sinistra sono al di sotto del punteggio di pertinenza. Una descrizione comando visualizza il punteggio di pertinenza e la percentuale correlata di file nel set di file di revisione in relazione al totale dei file.
