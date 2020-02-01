---
title: Monitorare l'analisi della pertinenza in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Informazioni su come visualizzare e interpretare lo stato e i risultati della formazione sulla pertinenza per i problemi di caso in Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 5fa9fe49f1a644f2a64321c1ec106b11c487c885
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601403"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a>Monitorare l'analisi della pertinenza in Office 365 Advanced eDiscovery

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In Advanced eDiscovery, la scheda della pista di pertinenza Visualizza la validità calcolata dell'allenamento di pertinenza eseguito nella scheda Tag e indica il passaggio successivo da eseguire nel processo di formazione iterativo in rilevanza. 
  
## <a name="tracking-relevance-training-status"></a>Verifica dello stato di formazione per pertinenza

1. Visualizzare i dettagli seguenti in base alla pertinenza per i problemi di caso, come illustrato nell'esempio seguente di una finestra di dialogo **nome problema** . 
    
  - **Valutazione**: questo indicatore di stato indica in quale misura la formazione sulla pertinenza eseguita a questo punto ha raggiunto l'obiettivo di valutazione in termini di margine di errore. Viene visualizzata anche la ricchezza dei risultati della formazione di pertinenza. 
    
  - **Training**: questo indicatore di stato con codice a colori e la visualizzazione della descrizione comandi indicano la stabilità dei risultati di formazione e una scala numerica che mostra il numero di esempi di formazione sulla pertinenza contrassegnati per ogni problema. L'esperto monitora lo stato di avanzamento del processo di formazione per la pertinenza iterativa. 
    
  - **Calcolo batch**: questo indicatore di stato fornisce informazioni sul completamento del calcolo batch.
    
  - **Passaggio successivo**: Visualizza la raccomandazione per il passaggio successivo da eseguire. 
    
    In questo esempio viene mostrata una valutazione completata correttamente per un problema, indicata dall'indicatore di stato dei colori completato e dal segno di spunta. Il tagging è in corso, ma il caso è ancora considerato instabile (stato di stabilità mostrato anche in un suggerimento per gli strumenti). La raccomandazione per il passaggio successivo è "formazione". 
    
    ![Fase 1 del corso di formazione sulla traccia di pertinenza](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    La visualizzazione espansa Visualizza ulteriori informazioni e opzioni. Il margine di errore corrente visualizzato è il margine di errore del richiamo nello stato corrente di valutazione, in base ai file di valutazione esistenti (già contrassegnati).
    
    > [!NOTE]
    >  La fase di valutazione può essere ignorata deselezionando la casella di controllo **valutazione** per ogni problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non saranno disponibili statistiche per questo problema. > deselezionando la casella di controllo **valutazione** può essere eseguita solo prima di eseguire la valutazione. Se in un caso esistono più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema. 
  
    Quando la valutazione non viene completata con il primo set di file di esempio, la valutazione potrebbe essere il passaggio successivo per la codifica di altri file. 
    
    In **pista** **pertinenza** \> , l'indicatore di avanzamento della formazione e il suggerimento per gli strumenti indicano il numero stimato di esempi aggiuntivi necessari per raggiungere la stabilità. Questa stima fornisce una guida di riferimento per l'addestramento supplementare necessario.
    
    ![Corso di formazione sulla traccia di pertinenza](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Dopo aver completato il tagging e, se è necessario continuare l'allenamento, fare clic su **formazione**. Un altro set di file di esempio viene generato dal set di file caricati per una formazione aggiuntiva. Viene quindi restituito alla scheda Tag per contrassegnare e formare più file.
    
### <a name="reaching-stable-training-levels"></a>Raggiungimento di livelli di formazione stabili

Dopo che i file di valutazione hanno raggiunto un livello di formazione stabile, Advanced eDiscovery è pronto per il calcolo in batch.
  
> [!NOTE]
> In genere, dopo tre esempi di formazione stabili, il passaggio successivo è "calcolo batch". Possono verificarsi eccezioni, ad esempio, quando sono state apportate modifiche al tagging dei file da esempi precedenti o quando sono stati aggiunti file di seeding. 
  
### <a name="performing-batch-calculation"></a>Esecuzione del calcolo batch

Il calcolo batch viene eseguito come passaggio successivo dopo che l'allenamento è stato completato correttamente (quando uno stato di formazione stabile è visualizzato dall'indicatore di stato, un segno di spunta e uno stato stabile nella descrizione comando.) Il calcolo in batch applica le conoscenze acquisite durante la formazione di pertinenza all'intera popolazione dei file, per valutare la pertinenza dei file e assegnare punteggi di pertinenza.
  
In caso di più di un problema, il calcolo del batch viene effettuato per ogni problema. Durante il calcolo batch, durante l'elaborazione di tutti i file viene monitorato lo stato di avanzamento. 
  
In questo caso, il passaggio successivo consigliato è "None", che indica che a questo punto non sono necessari ulteriori corsi di rilevanza iterativa. La fase successiva è la scheda **rilevanza \> decidere** . 
  
Se si desidera importare nuovi file dopo il calcolo del batch, l'amministratore può aggiungere i file importati a un nuovo carico.
  
> [!NOTE]
> Se si fa clic su **Annulla** durante il calcolo batch, il processo Salva ciò che è già stato eseguito. Se si esegue di nuovo il calcolo batch, il processo continuerà dall'ultimo punto eseguito. 
  
### <a name="assessing-tagging-consistency"></a>Valutazione della coerenza di tagging

Se sono presenti incoerenze nel tagging dei file, può influire sull'analisi. Il processo di coerenza tagging avanzato di eDiscovery può essere utilizzato quando i risultati non sono ottimali o la coerenza è in dubbio. Viene restituito un elenco dei possibili file contrassegnati con incoerenza, che possono essere esaminati e contrassegnati nuovamente, se necessario.
  
> [!NOTE]
> Dopo sette o più turni di allenamento dopo la valutazione, la coerenza di tagging può essere visualizzata in caso di **rilevanza** \> **** \> **** \> **dei risultati** \> dettagliati **avanzamento della formazione**. Questa revisione viene fatta per un problema alla volta. 
  
1. Nella ** \> colonna pertinenza**espandere la riga di un problema.
    
2. A destra del **passaggio successivo**, fare clic su **modifica**.
    
3. Selezionare **incoerenze dei tag** come opzione del **passaggio successivo** , dopo sette esempi di formazione e fare clic su **OK**.
    
4. Selezionare **incoerenze Tag**. La scheda **tag** apre la visualizzazione di un elenco delle incoerenze da ricontrassegnare in base alle esigenze. 
    
5. Fare clic su **Calcola** per inviare le modifiche. Il passaggio successivo dopo la codifica delle incoerenze è "formazione". 
    
## <a name="viewing-and-using-relevance-results"></a>Visualizzazione e utilizzo dei risultati di pertinenza

Nella scheda ** \> rilevamento pertinenza** espandere la riga di un problema e, accanto a **risultati dettagliati**, fare clic su **Visualizza**. Vengono visualizzati i riquadri dei risultati dettagliati, come illustrato di seguito.
  
![Risultati dettagliati della formazione sulla pertinenza](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Riepilogo di tagging

 Nell'esempio riportato di seguito, il **Riepilogo di tagging** Visualizza i totali per ogni processo di valutazione, formazione e recupero dei file di tagging. 
  
![Riepilogo tagging della traccia di pertinenza](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Parole chiave

Una parola chiave è una stringa univoca, una parola, una frase o una sequenza di parole in un file identificato da Advanced eDiscovery come un indicatore significativo del fatto che un file sia pertinente. La parola chiave di elenco "Includi" colonne e pesi nei file contrassegnati come rilevanti e le colonne "Escludi" elenca le parole chiave e i pesi nei file contrassegnati come non rilevanti.
  
Advanced eDiscovery assegna valori di peso a parole chiave negative o positive. Maggiore è il peso, maggiore è la probabilità che a un file in cui viene visualizzata la parola chiave sia assegnato un punteggio di pertinenza maggiore durante il calcolo in batch. 
  
L'elenco avanzato di parole chiave di eDiscovery può essere utilizzato per completare un elenco compilato da un esperto o come verifica di integrità indiretta in qualsiasi punto del processo di revisione dei file.
  
### <a name="training-progress"></a>Avanzamento della formazione

Nel riquadro **avanzamento formazione** è incluso un grafico dello stato di avanzamento della formazione e un indicatore di qualità, come illustrato nell'esempio seguente. 
  
![Stato di avanzamento del corso di formazione sulla traccia di pertinenza](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 **Indicatore qualità formazione**: Visualizza la classificazione della coerenza di tagging come indicato di seguito:
  
- **Good**: i file vengono contrassegnati in modo coerente. (Luce verde visualizzata)
    
- **Medium**: alcuni file possono essere contrassegnati in maniera incoerente. (Indicatore luminoso giallo visualizzato)
    
- **Avviso**: molti file possono essere contrassegnati in maniera incoerente. (Luce rossa visualizzata)
    
 **Grafico Progress Training**: indica il grado di stabilità della formazione di pertinenza dopo un certo numero di cicli di formazione rilevanza rispetto al valore della misura F. Quando si passa da sinistra a destra all'interno del grafico, l'intervallo di confidenza si restringe e viene utilizzato, insieme alla misura F, dalla pertinenza avanzata di eDiscovery per determinare la stabilità quando i risultati della formazione sulla pertinenza sono ottimizzati.
  
> [!NOTE]
> La pertinenza utilizza F2, una metrica di misura F in cui il richiamo riceve il doppio del peso di precisione. Per i casi con elevata ricchezza (oltre il 25%), la pertinenza utilizza la F1 (rapporto 1:1). Il rapporto di misura F può essere configurato in \> **Impostazioni avanzate**per l' **installazione di pertinenza** . 
  
### <a name="batch-calculation-results"></a>Risultati del calcolo batch

Nel riquadro dei **risultati del calcolo batch** è incluso il numero di file che sono stati segnati per pertinenza, come indicato di seguito: 
  
- **Success**
    
- **Empty**: non contiene testo, ad esempio solo spazi/tabulazioni
    
- **Errore**: a causa delle dimensioni eccessive o non è stato possibile leggerlo
    
- **Ignorato**: a causa delle dimensioni eccessive
    
- **Nebuloso**: contiene testo privo di significato o caratteristiche rilevanti per il problema
    
> [!NOTE]
> Empty, failed, ignorato o nebuloso riceverà un punteggio di pertinenza pari a-1. 
  
### <a name="training-statistics"></a>Statistiche sulla formazione

Nel riquadro **statistiche formazione** vengono visualizzate statistiche e grafici basati sui risultati di una formazione di pertinenza avanzata di eDiscovery. 
  
![Statistiche del corso di formazione sulla traccia di pertinenza](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Questa visualizzazione Mostra gli elementi seguenti:
  
- **Rapporto Revisione-richiamo**: confronto dei risultati in base ai punteggi di rilevanza in una revisione ipotetica lineare. Il richiamo è stimato in base al set di dimensioni del set di revisione.
    
- **Parametri**: statistiche calcolate cumulative relative al set di riesame in relazione alla popolazione dei file per l'intero caso.
    
- **Recensione**: percentuale di file da esaminare in base a questo cutoff.
    
- **Richiamo**: percentuale dei file rilevanti nel set di revisione. 
    
- **Distribuzione per Punteggio di pertinenza**: i file nel display grigio scuro a sinistra sono al di sotto del Punteggio di taglio. Un suggerimento per gli strumenti Visualizza il Punteggio di pertinenza e la percentuale relativa di file nel set di file di revisione in relazione ai file totali.
    
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione in rilevanza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Esecuzione e revisione della valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Esecuzione della formazione sulla pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Prendere decisioni in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Verifica dell'analisi della pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

