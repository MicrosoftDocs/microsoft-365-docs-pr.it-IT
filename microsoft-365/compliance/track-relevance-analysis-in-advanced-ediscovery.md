---
title: Tenere traccia dell'analisi di pertinenza in Advanced eDiscovery
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
description: Informazioni su come visualizzare e interpretare lo stato di formazione sulla rilevanza e i risultati per i problemi relativi ai casi in Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769181"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a>Tenere traccia dell'analisi di pertinenza in Advanced eDiscovery
  
In Advanced eDiscovery, nella scheda Traccia di pertinenza viene visualizzata la validità calcolata del training per pertinenza eseguito nella scheda Tag e viene indicato il passaggio successivo da eseguire nel processo di formazione iterativa in Rilevanza. 
  
## <a name="tracking-relevance-training-status"></a>Tenere traccia dello stato di formazione sulla rilevanza

1. Visualizzare i dettagli seguenti nella traccia di pertinenza per i problemi relativi ai casi, come illustrato nell'esempio seguente di una finestra di dialogo **Nome** problema riportata di seguito.

   - **Valutazione:** questo indicatore di stato mostra in che misura il training di pertinenza eseguito fino a questo punto ha raggiunto l'obiettivo di valutazione in termini di margine di errore. Viene inoltre visualizzata la descrizione dei risultati del training per la rilevanza.

   - **Formazione:** questo indicatore di stato con codice a colori e la descrizione comando indicano la stabilità dei risultati del training per la rilevanza e una scala numerica che mostra il numero di esempi di training per la rilevanza contrassegnati per ogni problema. L'esperto monitora lo stato del processo iterativo di formazione sulla rilevanza. 
  
   - **Calcolo batch:** questo indicatore di stato fornisce informazioni sul completamento del calcolo batch.
  
   - **Passaggio successivo:** visualizza il suggerimento per il passaggio successivo da eseguire. 
  
    Nell'esempio viene visualizzata una valutazione completata correttamente per un problema, indicata dall'indicatore di stato del colore completato e dal segno di spunta. Il tagging è in corso, ma il caso è ancora considerato instabile (lo stato di stabilità è visualizzato anche in una descrizione comando). Il passaggio successivo consigliato è "Formazione". 
  
    ![Fase 1 del corso di formazione sulla traccia di pertinenza](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    Nella visualizzazione espansa vengono visualizzate informazioni e opzioni aggiuntive. Il margine di errore corrente visualizzato è il margine di errore del richiamo nello stato corrente della valutazione, in base ai file di valutazione esistenti (già contrassegnati).
  
    > [!NOTE]
    >  La fase di valutazione può essere  ignorata deselezionando la casella di controllo Valutazione per ogni problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non ci saranno statistiche per questo problema. > la casella di controllo **Valutazione** può essere deselezionata solo prima dell'esecuzione della valutazione. In caso di più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema 
  
    Quando la valutazione non viene completata con il primo set di file di esempio, la valutazione potrebbe essere il passaggio successivo per contrassegnare più file.
  
    Nella **traccia di rilevanza,** l'indicatore di avanzamento del training e la descrizione comando indicano il numero stimato di campioni aggiuntivi necessari per \> raggiungere la stabilità. Questa stima fornisce una linea guida per la formazione aggiuntiva necessaria.
  
    ![Corso di formazione sulla traccia di pertinenza](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Al termine dell'aggiunta di tag e se è necessario continuare la formazione, fare clic su **Formazione.** Un altro set di file di esempio viene generato dal set di file caricato per corsi di formazione aggiuntivi. Viene quindi restituita la scheda Tag per aggiungere tag e formare altri file.

### <a name="reaching-stable-training-levels"></a>Raggiungere livelli di formazione stabili

Dopo che i file di valutazione hanno raggiunto un livello stabile di formazione, Advanced eDiscovery è pronto per il calcolo batch.
  
> [!NOTE]
> In genere, dopo tre esempi di formazione stabili, il passaggio successivo è "Calcolo batch". Potrebbero esserci eccezioni, ad esempio, quando sono state apportate modifiche al tagging dei file di esempi precedenti o quando sono stati aggiunti file di seeding. 
  
### <a name="performing-batch-calculation"></a>Esecuzione del calcolo batch

Il calcolo in batch viene eseguito come passaggio successivo dopo il completamento del training (quando viene visualizzato uno stato di formazione stabile dalla barra di stato, un segno di spunta e uno stato stabile nella descrizione comando). Il calcolo batch applica le conoscenze acquisite durante il training della rilevanza all'intera popolazione di file, per valutare la pertinenza dei file e assegnare i punteggi di rilevanza.
  
Quando si verifica più di un problema, il calcolo batch viene eseguito per ogni problema. Durante il calcolo in batch, lo stato viene monitorato durante l'elaborazione di tutti i file. 
  
In questo caso, il passaggio successivo consigliato è "Nessuno", che indica che non è necessario un ulteriore training iterativo per la rilevanza a questo punto. La fase successiva è la **scheda Decidi \> per pertinenza.** 
  
Se si desidera importare nuovi file dopo il calcolo batch, l'amministratore può aggiungere i file importati a un nuovo carico.
  
> [!NOTE]
> Se si fa **clic su Annulla** durante il calcolo in batch, il processo salva ciò che è già stato eseguito. Se si esegue di nuovo il calcolo batch, il processo continuerà dall'ultimo punto di esecuzione. 
  
### <a name="assessing-tagging-consistency"></a>Valutazione della coerenza dei tag

In caso di incoerenze nel tagging dei file, può influire sull'analisi. Il processo di coerenza dei tag di Advanced eDiscovery può essere utilizzato quando i risultati non sono ottimali o la coerenza è in dubbio. Viene restituito un elenco dei possibili file contrassegnati in modo incoerente e possono essere esaminati e ritardati, se necessario.
  
> [!NOTE]
> Dopo sette o più round di formazione dopo la valutazione, è possibile visualizzare la coerenza dei tag in **Risultati** dettagliati relativi alla traccia di rilevanza \>  \>  \>  \> **Avanzamento del training.** Questa revisione viene eseguita per un problema alla volta.
  
1. In **Traccia di \> pertinenza** espandere la riga di un problema.
  
2. A destra del **passaggio successivo, fare** clic su **Modifica.**
  
3. Seleziona **Contrassegna le incoerenze** come opzione Passaggio **successivo,** dopo sette esempi di formazione e fai clic su **OK.**
  
4. Selezionare **Incoerenze tag.** Verrà **visualizzata** la scheda Tag con un elenco delle incoerenze da ritagare in base alle esigenze.
  
5. Fare **clic su** Calcola per inviare le modifiche. Il passaggio successivo dopo l'aggiunta di tag alle incoerenze è "Training". 
  
## <a name="viewing-and-using-relevance-results"></a>Visualizzazione e utilizzo dei risultati di pertinenza

Nella scheda **Traccia di \> pertinenza** espandere la riga di un problema e accanto a Risultati **dettagliati** fare clic su **Visualizza.** Vengono visualizzati i riquadri dei risultati dettagliati, come illustrato e descritto di seguito.
  
![Risultati dettagliati della formazione sulla pertinenza](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Riepilogo dei tag

 Nell'esempio riportato di seguito, nel riepilogo di **tagging** vengono visualizzati i totali per ogni processo di tagging dei file di valutazione, formazione e di aggiornamento.
  
![Riepilogo tagging della traccia di pertinenza](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Parole chiave

Una parola chiave è una stringa, una parola, una frase o una sequenza univoca di parole in un file identificato da Advanced eDiscovery come indicatore significativo della pertinenza di un file. La parola chiave dell'elenco "Includi" colonne e i pesi nei file contrassegnati come rilevanti, mentre le colonne "Escludi" elencano parole chiave e pesi nei file contrassegnati come non rilevanti.
  
Advanced eDiscovery assegna valori di peso delle parole chiave negativi o positivi. Maggiore è il peso, maggiore è la probabilità che a un file in cui viene visualizzata la parola chiave venga assegnato un punteggio di pertinenza più alto durante il calcolo del batch.
  
L'elenco di parole chiave di Advanced eDiscovery può essere utilizzato per integrare un elenco creato da un esperto o come controllo di sanità mentale indiretta in qualsiasi momento del processo di revisione dei file.
  
### <a name="training-progress"></a>Avanzamento della formazione

Il **riquadro Avanzamento formazione** include un grafico dello stato di avanzamento del training e la visualizzazione degli indicatori di qualità, come illustrato nell'esempio seguente.
  
![Stato di avanzamento del corso di formazione sulla traccia di pertinenza](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
**Indicatore di qualità del training**: visualizza la valutazione della coerenza dei tag nel modo seguente:
  
- **Buona:** i file sono contrassegnati in modo coerente. (Luce verde visualizzata)
  
- **Media:** alcuni file potrebbero essere contrassegnati in modo incoerente. (Luce gialla visualizzata)

- **Avviso:** molti file potrebbero essere contrassegnati in modo incoerente. (Semaforo rosso visualizzato)

**Grafico dello stato di** avanzamento della formazione: mostra il grado di stabilità del training della rilevanza dopo molti cicli di formazione per la rilevanza rispetto al valore di misura F. Quando ci spostiamo da sinistra a destra nel grafico, l'intervallo di confidenza si restringe e viene usato, insieme alla misura F, da Rilevanza di Advanced eDiscovery per determinare la stabilità quando i risultati del training per la rilevanza sono ottimizzati.
  
> [!NOTE]
> La pertinenza usa F2, una metrica di misura F in cui Richiamo riceve il doppio del peso della precisione. Per i casi con una ricca qualità elevata (oltre il 25%), la rilevanza usa F1 (rapporto 1:1). Il rapporto di misurazione F può essere configurato in **Impostazioni avanzate per la pertinenza.** \> 
  
### <a name="batch-calculation-results"></a>Risultati del calcolo in batch

Il **riquadro dei risultati del calcolo** batch include il numero di file che sono stati classificati per pertinenza, come indicato di seguito: 
  
- **Operazione completata**
  
- **Vuoto**: non contiene testo, ad esempio solo spazi o tabulazioni
  
- **Failed**: A causa di dimensioni eccessive o non è stato possibile leggere
  
- **Ignorato:** a causa di dimensioni eccessive
  
- **Nebuloso:** contiene testo senza significato o nessuna funzionalità rilevante per il problema
  
> [!NOTE]
> Vuoto, Non riuscito, Ignorato o Nebuloso riceverà un punteggio di pertinenza pari a -1.
  
### <a name="training-statistics"></a>Statistiche di formazione

Nel **riquadro Statistiche** formazione vengono visualizzate statistiche e grafici basati sui risultati della formazione sulla rilevanza di Advanced eDiscovery. 
  
![Statistiche del corso di formazione sulla traccia di pertinenza](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Questa visualizzazione mostra quanto segue:
  
- **Rapporto revisione-richiamo**: confronto dei risultati in base ai punteggi di pertinenza in una revisione ipoteticamente lineare. Il richiamo è stimato in base al set di dimensioni impostato per la revisione.
  
- **Parametri:** statistiche calcolate cumulative relative alla revisione impostata in relazione alla popolazione di file per l'intero caso.
  
- **Review:** percentuale di file da esaminare in base a questa riduzione.
  
- **Richiamo:** percentuale di file rilevanti nel set da rivedere. 
  
- **Distribuzione in base al punteggio di** pertinenza: i file nella visualizzazione grigio scuro a sinistra sono al di sotto del punteggio di pertinenza. Una descrizione comando visualizza il punteggio di pertinenza e la percentuale correlata di file nel set di file da rivedere in relazione al totale dei file.
