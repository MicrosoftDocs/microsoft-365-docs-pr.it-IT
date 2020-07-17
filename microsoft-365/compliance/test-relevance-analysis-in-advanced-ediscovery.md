---
title: Analisi della pertinenza del test in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: Informazioni su come utilizzare la scheda test dopo il calcolo batch in Advanced eDiscovery per testare, confrontare e convalidare la qualità complessiva dell'elaborazione.
ms.openlocfilehash: c5a885b3483b9ce319fffefa55037c0c2c8f3c85
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936209"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery-classic"></a>Analisi della pertinenza del test in Advanced eDiscovery (Classic)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
La scheda test in Advanced eDiscovery consente di testare, confrontare e convalidare la qualità complessiva dell'elaborazione. Questi test vengono eseguiti dopo il calcolo in batch. Contrassegnando i file della raccolta, un esperto rende il giudizio finale sul fatto che ogni file contrassegnato è effettivamente pertinente per il caso. 
  
In scenari con problemi singoli e multipli i test vengono in genere eseguiti per ogni problema. I risultati possono essere visualizzati dopo ogni test e i risultati dei test possono essere rielaborati con i file di test di esempio specificati.
  
## <a name="testing-the-rest"></a>Verifica del resto

Il test "test the rest" viene utilizzato per convalidare le decisioni di eliminazione, ad esempio per esaminare solo i file al di sopra di un punteggio di taglio di rilevanza specifico in base ai risultati avanzati di eDiscovery. L'esperto esamina un campione di file con un punteggio di taglio selezionato per valutare il numero di file rilevanti all'interno di tale set.
  
Questo test fornisce statistiche e un confronto tra il set di revisione e il test del popolamento Rest. I risultati del set di revisione sono quelli calcolati per pertinenza durante l'allenamento. I risultati includono calcoli, in base alle impostazioni e ai parametri di input, ad esempio:
  
- Testare le statistiche di esempio del numero di file in un esempio e identificare i file rilevanti. 
    
- Confronto tabulare dei parametri di popolazione del set di revisione e del resto, ad esempio, il numero di file, il numero stimato di file rilevanti, la ricchezza stimata e il costo medio per la ricerca di un altro file pertinente. Le impostazioni dei parametri di costo possono essere impostate dall'amministratore.
    
1. Aprire la scheda ** \> test pertinenza** . 
    
2. Nella scheda **test** fare clic su **nuovo test**. Viene visualizzata la finestra di dialogo **Crea test** , come illustrato nell'esempio seguente. 
    
    ![Risultati del test sull'inattività di pertinenza](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. In **nome test**e **Descrizione**digitare il nome e la descrizione.
    
4. Nell'elenco **tipo di test** , selezionare **test the rest**
    
5. Nell'elenco **problema/categoria** selezionare il nome del problema. 
    
6. Nell'elenco **carico** selezionare il carico. 
    
7. In **lettura%**, accettare il valore predefinito o selezionare un valore per il Punteggio di pertinenza del cutoff. 
    
8. In **Dimensioni set**oppure accettare il valore predefinito. Si noti che le icone di ripristino ripristineranno i valori predefiniti.
    
9. Fare clic su **Avvia tagging**. Viene generato un esempio di test.
    
10. Esaminare e contrassegnare ognuno dei file nella scheda ** \> tag pertinenza** e, al termine, fare clic su **Calcola**.
    
11. Nella scheda test è possibile fare clic su **Visualizza risultati** per visualizzare i risultati dei test. Un esempio è illustrato nella figura seguente. 
    
    ![Risultati del test sull'inattività](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
Nella figura precedente la sezione **parametri di esempio** della tabella contiene informazioni dettagliate sul numero di file nell'esempio contrassegnati dall'esperto e sul numero di file rilevanti presenti in tale esempio. 
  
La sezione relativa ai **parametri di popolamento** della tabella contiene i risultati dei test, tra cui la popolazione del set di riesame di file con un punteggio al di sotto del cutoff selezionato e la popolazione di file con un punteggio sopra il taglio selezionato. Per ogni popolazione, vengono visualizzati i risultati seguenti: 
  
- Include i file con il cutoff lettura%-dichiarato
    
- Il numero totale di file 
    
- Il numero stimato di file rilevanti 
    
- La ricchezza stimata 
    
- Il costo di revisione medio per la ricerca di un altro file pertinente
    
## <a name="testing-the-slice"></a>Test della sezione

Il test "test Slice" esegue test analogo al test "test the rest", ma a un segmento del set di file specificato dalla pertinenza lettura%.
  
1. Aprire la scheda ** \> test pertinenza** . 
    
2. Nella scheda **test** fare clic su **nuovo test**. Viene visualizzata la finestra di dialogo **Crea test** . 
    
3. In **nome** e **Descrizione**del test, digitare le informazioni.
    
4. Nell'elenco **tipo di test** selezionare **Verifica la sezione**.
    
5. Nell'elenco **problema** selezionare il nome del problema. 
    
6. Nell'elenco **carico** selezionare il carico. 
    
7. In **lettura% tra**, accettare i valori predefiniti di intervallo basso e alto o selezionare i valori per i punteggi di rilevanza del cutoff. 
    
8. In **Dimensioni set**selezionare un valore o accettare il valore predefinito.
    
    Le icone di ripristino ripristineranno il valore predefinito.
    
9. Fare clic su **Avvia tagging**. Viene generato un esempio di test.
    
10. Esaminare e contrassegnare ognuno dei file nella scheda ** \> tag pertinenza** e, al termine, fare clic su **Calcola**. 
    
11. Nella scheda test è possibile fare clic su **Visualizza risultati** per visualizzare i risultati dei test. 
    
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione in rilevanza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Formazione di tagging e pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Verifica dell'analisi della pertinenza](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidere in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)

