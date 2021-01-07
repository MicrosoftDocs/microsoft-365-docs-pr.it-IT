---
title: Tagging e valutazione in Advanced eDiscovery
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Esaminare i passaggi necessari per eseguire la formazione di valutazione, compresi i file di tagging, e la revisione dei risultati della valutazione in Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769191"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Tagging e valutazione nel modulo pertinenza in Advanced eDiscovery
  
In questa sezione viene descritta la procedura per la valutazione del modulo pertinenza in Advanced eDiscovery.
  
## <a name="performing-assessment-training-and-analysis"></a>Formazione e analisi per l'esecuzione di valutazioni

1. Nella scheda **\> rilevamento pertinenza** fare clic su **valutazione** per avviare la valutazione dei casi.

    Ad esempio, in questa procedura viene creato un set di valutazione di esempio di 500 file e viene visualizzata la scheda **tag** , che contiene il pannello di tagging, il contenuto del file visualizzato e altre opzioni di tagging. 

    ![Scheda Tag pertinenza per la valutazione](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Esaminare ogni file nell'esempio, determinare la pertinenza del file per ogni problema di caso e contrassegnare il file utilizzando i pulsanti pertinenza (R), non rilevanti (NR) e Ignora nel riquadro del **Pannello di tagging** . 

    > [!NOTE]
    >  La valutazione richiede 500 file contrassegnati. Se i file vengono "ignorati", verranno visualizzati altri file da contrassegnare. 
  
3. Dopo aver codificato tutti i file nell'esempio, fare clic su **Calcola**.

    La valutazione del margine e della ricchezza degli errori correnti viene calcolata e visualizzata nella scheda **pertinenza** , con dettagli espansi per ogni problema, come illustrato di seguito. Ulteriori informazioni su questa finestra di dialogo sono descritte nella sezione [revisione dei risultati della valutazione](#reviewing-assessment-results) .

    ![Traccia di pertinenza: valutazione](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > Per impostazione predefinita, si consiglia di procedere con il passaggio successivo predefinito quando l'indicatore di stato di valutazione del problema è stato completato, indicando che il campione di valutazione è stato esaminato e che sono stati contrassegnati i file rilevanti sufficienti. > altrimenti, se si desidera visualizzare i risultati della scheda **pista** e controllare il margine di errore e il passaggio successivo, fare clic su **modifica** adiacente al **passaggio successivo**, selezionare **continua valutazione** e quindi fare clic su **OK**.
  
4. Fare clic su **modifica** a destra della casella di controllo **valutazione** per visualizzare e specificare i parametri di valutazione per ogni problema. Viene visualizzata una finestra di dialogo a **livello di valutazione** per ogni problema, come illustrato nell'esempio seguente: 

    ![Problema relativo al livello di valutazione per il caso](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    I parametri seguenti per il problema vengono calcolati e visualizzati nella finestra di dialogo **livello di valutazione** : 

    **Margine di errore di destinazione per le stime del richiamo**: sulla base di questo valore, viene calcolato il numero stimato di file aggiuntivi necessari per la revisione. Il margine utilizzato per il richiamo è maggiore di 75% e con un livello di confidenza del 95%.

    **File di valutazione aggiuntivi necessari**: indica quanti altri file sono necessari se i requisiti del margine di errore corrente non sono stati soddisfatti. 

5. Per modificare il margine di errore corrente e vedere l'effetto dei diversi margini di errore (per problema):

6. Nell'elenco **selezionare** un problema selezionare un problema. 

7. Nel **margine di errore di destinazione per le stime di richiamo**, immettere un nuovo valore.

8. Fare clic su **Aggiorna valori** per visualizzare l'impatto delle rettifiche. 

9. Fare clic su **Avanzate** nella finestra di dialogo **livello di valutazione** per visualizzare i parametri e i dettagli aggiuntivi seguenti: 

    ![Visualizzazione avanzata dei problemi relativi al livello di valutazione per il caso](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - **Ricchezza stimata**: ricchezza stimata in base ai risultati di valutazione correnti

    - **Per il richiamo assunto**: per impostazione predefinita, il margine di errore di destinazione si applica a richiamo sopra 75%. Fare clic su **modifica** se si desidera modificare questo parametro e controllare il margine di errore su un intervallo diverso di valori di richiamo. 

    - **Livello di confidenza**: per impostazione predefinita, il margine di errore consigliato per la sicurezza è 95%. Se si desidera modificare questo parametro, fare clic su **modifica** .

    - **Margine errore previsto** per la ricchezza: in base ai valori aggiornati, si tratta del margine di errore previsto per la ricchezza, dopo la revisione di tutti i file di valutazione aggiuntivi.

    - **File di valutazione aggiuntivi necessari**: dati i valori aggiornati, il numero di file di valutazione aggiuntivi che devono essere esaminati per raggiungere l'obiettivo.

    - **Totale file di valutazione necessari**: dati i valori aggiornati, i file di valutazione totali necessari per la revisione.

    - **Numero previsto di file rilevanti nella valutazione**: dati i valori aggiornati, il numero previsto di file rilevanti nell'intera valutazione dopo che sono stati esaminati tutti i file di valutazione aggiuntivi.

10. Se si modificano i parametri, fare clic su **Ricalcola valori**. Al termine, se si verifica un problema, fare clic su **OK** per salvare le modifiche o su **Avanti** quando sono presenti più problemi da rivedere o modificare e quindi **terminare**. 

    Quando sono presenti più problemi, dopo che tutti i problemi sono stati esaminati o modificati, viene visualizzato un **livello di valutazione:** viene visualizzata la finestra di riepilogo, come illustrato nell'esempio seguente. 

    ![Riepilogo del livello di valutazione](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Dopo aver completato il processo di valutazione, passare alla fase successiva di formazione per pertinenza.

## <a name="reviewing-assessment-results"></a>Revisione dei risultati della valutazione

Dopo aver aggiunto un campione di valutazione, i risultati della valutazione vengono calcolati e visualizzati nella scheda Tracking pertinenza.
  
I risultati seguenti sono visualizzati nella visualizzazione espansa della pista:
  
- Valutazione del margine di errore corrente per le stime del richiamo

- Ricchezza stimata

- File di valutazione aggiuntivi necessari (per la revisione)

Il margine di errore di valutazione corrente è il margine di errore consigliato da Advanced eDiscovery. Il numero visualizzato per i "file di valutazione aggiuntivi richiesti" corrisponde a tale raccomandazione.
  
L'indicatore di avanzamento della valutazione indica il livello di completamento della valutazione, in base al margine di errore corrente. Quando la valutazione è in corso, l'utente Tag un altro campione di valutazione.
  
Quando l'indicatore di avanzamento della valutazione Visualizza la valutazione come completata, significa che la revisione del campione di valutazione è stata completata e che sono stati contrassegnati i file rilevanti sufficienti. 
  
La visualizzazione estesa della pista Mostra il passaggio successivo consigliato, le statistiche di valutazione e l'accesso ai risultati dettagliati.
  
Quando la ricchezza è molto bassa, il numero di file di valutazione aggiuntivi necessari per raggiungere un numero minimo di file rilevanti per produrre statistiche utili è molto elevato. Advanced eDiscovery consiglia di passare all'allenamento. L'indicatore di avanzamento della valutazione verrà ombreggiato e non saranno disponibili statistiche.
  
In assenza di stabilizzazione basata statisticamente, vi saranno risultati con un livello di precisione e confidenza inferiore. Tuttavia, questi risultati possono essere utilizzati per trovare i file rilevanti quando non è necessario conoscere la percentuale di file rilevanti trovati. Analogamente, questo stato può essere utilizzato per formare problemi con una ricchezza bassa, in cui i punteggi rilevati possono accelerare l'accesso ai file rilevanti per un problema specifico.
  
> [!TIP]
> Nella scheda **\> Tracking pertinenza** , espansione visualizzazione dei problemi, sono disponibili le seguenti opzioni di visualizzazione: 
> 
> Il passaggio successivo consigliato, ad esempio il **passaggio successivo:** la funzionalità di tagging può essere ignorata (per problema) facendo clic sul pulsante **modifica** a destra e quindi selezionando un passaggio diverso nel **passaggio successivo**. Quando l'indicatore di stato di valutazione non è stato completato, la valutazione sarà la successiva opzione consigliata per contrassegnare i file di valutazione e aumentare l'accuratezza delle statistiche. 
> 
> È possibile modificare il margine di errore e valutarne l'impatto, facendo clic su **modifica** e nella **finestra di dialogo livello di valutazione**, modificando il **margine di errore di destinazione per le stime di richiamo** e facendo clic su **Aggiorna valori**. Inoltre, in questa finestra di dialogo, è possibile visualizzare le opzioni avanzate facendo clic su **Avanzate**. 
> 
> È possibile visualizzare le statistiche aggiuntive a livello di valutazione e il relativo impatto facendo clic su **Visualizza**. Nella finestra di dialogo Risultati dettagli visualizzati, le statistiche sono disponibili per ogni problema, quando sono presenti almeno 500 file di valutazione contrassegnati e almeno 18 file sono contrassegnati come rilevanti per il problema. 
