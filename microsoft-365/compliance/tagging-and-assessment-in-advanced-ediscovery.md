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
description: Esaminare i passaggi per eseguire la formazione sulla valutazione, inclusi i file di tagging e i risultati della valutazione in Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769191"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Tagging e valutazione nel modulo Pertinenza in Advanced eDiscovery
  
In questa sezione viene descritta la procedura per la valutazione nel modulo Rilevanza in Advanced eDiscovery.
  
## <a name="performing-assessment-training-and-analysis"></a>Esecuzione della formazione e dell'analisi della valutazione

1. Nella scheda **Traccia di \> pertinenza** fare clic su **Valutazione** per avviare la valutazione del caso.

    Ad esempio, in questa procedura viene creato un set di valutazione di esempio di 500 file e viene visualizzata la scheda **Tag,** che contiene il pannello Tagging, il contenuto dei file visualizzati e altre opzioni di tagging. 

    ![Scheda Tag pertinenza per la valutazione](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Esaminare ogni file dell'esempio, determinare la pertinenza del file per ogni problema di caso e contrassegnare il file usando i pulsanti Rilevanza (R), Non rilevante (NR) e Ignora nel riquadro del pannello **Tagging.** 

    > [!NOTE]
    >  La valutazione richiede 500 file con tag. Se i file vengono "ignorati", riceverai più file da contrassegnare. 
  
3. Dopo aver contrassegnato tutti i file nell'esempio, fare clic su **Calcola.**

    Il margine di errore corrente della valutazione e la sua efficacia vengono calcolati e visualizzati nella scheda **Traccia** di pertinenza, con dettagli espansi per problema, come illustrato di seguito. Ulteriori dettagli su questa finestra di dialogo sono descritti nella sezione [Revisione dei risultati della](#reviewing-assessment-results) valutazione.

    ![Traccia di pertinenza: valutazione](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > Per impostazione predefinita, è consigliabile procedere al passaggio successivo predefinito al termine dell'indicatore di stato della valutazione per il problema, a indicare che l'esempio di valutazione è stato esaminato e che sono stati contrassegnati file pertinenti sufficienti. > In caso contrario, se si  desidera visualizzare i risultati della scheda Traccia  e controllare il margine di errore e il passaggio successivo, fare clic su Modifica accanto a Passaggio **successivo,** selezionare Continua valutazione e quindi fare clic su **OK.**
  
4. Fare **clic su** Modifica a destra della casella di controllo Valutazione per visualizzare e specificare i parametri di valutazione per ogni problema.  Viene **visualizzata una** finestra di dialogo del livello di valutazione per ogni problema, come illustrato nell'esempio seguente: 

    ![Problema relativo al livello di valutazione per il caso](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    I parametri seguenti per il problema vengono calcolati e visualizzati nella finestra di dialogo **del livello di** valutazione: 

    **Margine di errore di destinazione per le** stime di richiamo: in base a questo valore, viene calcolato il numero stimato di file aggiuntivi necessari per la revisione. Il margine utilizzato per il richiamo è maggiore del 75% e con un livello di probabilità del 95%.

    **File di valutazione aggiuntivi necessari:** indica quanti altri file sono necessari se non sono stati soddisfatti i requisiti del margine di errore corrente. 

5. Per regolare il margine di errore corrente e vedere l'effetto di margini di errore diversi (per problema):

6. **Nell'elenco Seleziona problema** selezionare un problema. 

7. In **Margine di errore obiettivo per le stime di richiamo** immettere un nuovo valore.

8. Fare **clic su Aggiorna valori** per visualizzare l'impatto delle rettifiche. 

9. Fare **clic su** Avanzate nella finestra di **dialogo** Del livello di valutazione per visualizzare i parametri e i dettagli aggiuntivi seguenti: 

    ![Visualizzazione avanzata dei problemi relativi al livello di valutazione per il caso](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - **Richness stimata:** valore stimato in base ai risultati della valutazione corrente

    - **Per il richiamo presupposto:** per impostazione predefinita, il margine di errore di destinazione si applica al richiamo superiore al 75%. Fare **clic su** Modifica se si desidera modificare questo parametro e controllare il margine di errore su un intervallo diverso di valori di richiamo. 

    - **Livello di confidenza:** per impostazione predefinita, il margine di errore consigliato per la probabilità è 95%. Fare **clic su** Modifica se si desidera modificare questo parametro.

    - **Margine di errore di richness** previsto: dati i valori aggiornati, questo è il margine di errore previsto della richness, dopo la revisione di tutti i file di valutazione aggiuntivi.

    - **File di valutazione aggiuntivi necessari:** dati i valori aggiornati, il numero di file di valutazione aggiuntivi che devono essere esaminati per raggiungere l'obiettivo.

    - **Totale file di valutazione necessari:** dati i valori aggiornati, totale dei file di valutazione necessari per la revisione.

    - **Numero previsto di file pertinenti nella** valutazione: dati i valori aggiornati, il numero previsto di file pertinenti nell'intera valutazione dopo la revisione di tutti i file di valutazione aggiuntivi.

10. Fare **clic su Ricalcola valori** se i parametri vengono modificati. Al termine, se si verifica un problema, fare clic  su **OK** per salvare le modifiche oppure su Avanti quando si verificano più problemi da esaminare o modificare e quindi **su Fine.** 

    In caso di più problemi, dopo che tutti  i problemi sono stati esaminati o modificati, viene visualizzata una finestra di dialogo di riepilogo del livello di valutazione, come illustrato nell'esempio seguente. 

    ![Riepilogo del livello di valutazione](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Al completamento corretto della valutazione, passare alla fase successiva della formazione sulla rilevanza.

## <a name="reviewing-assessment-results"></a>Revisione dei risultati della valutazione

Dopo aver contrassegnato un campione di valutazione, i risultati della valutazione vengono calcolati e visualizzati nella scheda Traccia di pertinenza.
  
Nella visualizzazione delle tracce espansa vengono visualizzati i risultati seguenti:
  
- Valutazione del margine di errore corrente per le stime di richiamo

- Richness stimata

- File di valutazione aggiuntivi necessari (per la revisione)

Il margine di errore corrente della valutazione è il margine di errore consigliato da Advanced eDiscovery. Il numero visualizzato per i "File di valutazione aggiuntivi necessari" corrisponde a tale suggerimento.
  
L'indicatore di stato della valutazione mostra il livello di completamento della valutazione, in base al margine di errore corrente. Quando è in corso la valutazione, l'utente contrassegnerà un altro esempio di valutazione.
  
Quando l'indicatore di stato della valutazione mostra che la valutazione è stata completata, significa che la revisione dell'esempio di valutazione è stata completata e che sono stati contrassegnati file pertinenti sufficienti. 
  
La visualizzazione della traccia espansa mostra il passaggio successivo consigliato, le statistiche di valutazione e l'accesso ai risultati dettagliati.
  
Quando la quantità di dati è molto bassa, il numero di file di valutazione aggiuntivi necessari per raggiungere un numero minimo di file rilevanti per produrre statistiche utili è molto elevato. Advanced eDiscovery consiglia quindi di passare alla formazione. L'indicatore di stato della valutazione sarà ombreggiato e non saranno disponibili statistiche.
  
In assenza di stabilizzazione statisticamente basata, verranno restituiti risultati con un livello di accuratezza e confidenza inferiore. Tuttavia, questi risultati possono essere utilizzati per trovare i file pertinenti quando non è necessario conoscere la percentuale di file pertinenti trovati. Analogamente, questo stato può essere usato per formare i problemi con scarsa qualità, in cui i punteggi di pertinenza possono accelerare l'accesso ai file rilevanti per un problema specifico.
  
> [!TIP]
> Nella scheda **Traccia di \> pertinenza,** visualizzazione dei problemi espansi, sono disponibili le opzioni di visualizzazione seguenti: 
> 
> Il passaggio successivo consigliato, ad esempio Passaggio **successivo:** Aggiunta di tag  può essere ignorato (per problema) facendo clic sul pulsante Modifica a destra e quindi selezionando un passaggio diverso nel **passaggio successivo.** Quando l'indicatore di stato della valutazione non è stato completato, la valutazione sarà l'opzione consigliata successiva per contrassegnare più file di valutazione e aumentare l'accuratezza delle statistiche. 
> 
> È possibile modificare il margine di errore e valutarne l'impatto, facendo clic su Modifica e nella finestra di dialogo Livello di **valutazione,** modificando il margine di errore target per le stime di richiamo e facendo clic su **Aggiorna valori.** In questa finestra di dialogo è inoltre possibile visualizzare le opzioni avanzate facendo clic su **Avanzate.** 
> 
> È possibile visualizzare ulteriori statistiche del livello di valutazione e il relativo impatto facendo clic su **Visualizza.** Nella finestra di dialogo Dei risultati dettagliati visualizzata, le statistiche sono disponibili per ogni problema, quando sono presenti almeno 500 file di valutazione contrassegnati e almeno 18 file sono contrassegnati come rilevanti per il problema. 
