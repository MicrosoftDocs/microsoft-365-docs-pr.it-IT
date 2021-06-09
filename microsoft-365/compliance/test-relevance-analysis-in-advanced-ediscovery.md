---
title: Testare l'analisi della rilevanza in Advanced eDiscovery
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come usare la scheda Test dopo il calcolo batch in Advanced eDiscovery per testare, confrontare e convalidare la qualità complessiva dell'elaborazione.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769171"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a>Testare l'analisi della rilevanza in Advanced eDiscovery
  
La scheda Test in Advanced eDiscovery consente di testare, confrontare e convalidare la qualità complessiva dell'elaborazione. Questi test vengono eseguiti dopo il calcolo batch. Contrassegnando i file nella raccolta, un esperto prende il giudizio finale sull'eventuale pertinente caso di ogni file con tag.
  
In scenari a singolo e a più problemi, i test vengono in genere eseguiti per ogni problema. I risultati possono essere visualizzati dopo ogni test e i risultati dei test possono essere rielaborati con i file di test di esempio specificati.
  
## <a name="testing-the-rest"></a>Test del resto

Il test "Test the Rest" viene utilizzato per convalidare le decisioni diculling, ad esempio per esaminare solo i file al di sopra di uno specifico punteggio di pertinenza in base ai risultati Advanced eDiscovery finale. L'esperto esamina un campione di file con un punteggio di cutoff selezionato per valutare il numero di file pertinenti all'interno del set.
  
Questo test fornisce statistiche e un confronto tra l'insieme Review e la popolazione Test the Rest. I risultati del set di revisioni sono quelli calcolati in base alla pertinenza durante la formazione. I risultati includono calcoli basati su impostazioni e parametri di input, ad esempio:
  
- Testare le statistiche di esempio del numero di file in un esempio e identificare i file pertinenti.

- Confronto tabulare dei parametri Population dell'insieme Review e rest, ad esempio, il numero di file, il numero stimato di file pertinenti, la quantità stimata e il costo medio di ricerca di un altro file rilevante. Le impostazioni dei parametri di costo possono essere impostate dall'amministratore.

Per eseguire il test "Test the Rest":

1. Aprire la **scheda Test \> di pertinenza.**

2. Nella scheda **Test** fare clic su **Nuovo test.** Viene **visualizzata la** finestra di dialogo Crea test, come illustrato nell'esempio seguente.

    ![Risultati del test sull'inattività di pertinenza](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. In **Nome test** e **Descrizione** digitare il nome e la descrizione.

4. **Nell'elenco Tipo di** test selezionare Test il **resto**

5. **Nell'elenco Problema/Categoria** selezionare il nome del problema.

6. **Nell'elenco Carica** selezionare il carico. 

7. In **Lettura %** accettare il valore predefinito o selezionare un valore per il punteggio di rilevanza limite. 

8. In **Imposta dimensioni** o accetta il valore predefinito. Le icone di ripristino ripristinano i valori predefiniti.

9. Fare **clic su Avvia tagging**. Viene generato un esempio di test.

10. Esaminare e contrassegnare ogni file nella scheda **Tag \>** di pertinenza e, al termine, fare clic su **Calcola**.

11. Nella scheda Test è possibile fare clic **su Visualizza risultati** per visualizzare i risultati del test. Nella schermata seguente viene mostrato un esempio.

    ![Risultati del test sull'inattività](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
Nello screenshot precedente, la sezione **Parametri** di esempio della tabella contiene informazioni dettagliate sul numero di file nell'esempio contrassegnati dall'esperto e sul numero di file pertinenti trovati nell'esempio.
  
La  sezione Parametri di popolamento della tabella contiene i risultati del test, inclusa la popolazione impostata di revisione dei file con un punteggio al di sotto del limite selezionato e la popolazione "Resto" di file con un punteggio sopra il limite selezionato. Per ogni popolazione vengono visualizzati i risultati seguenti:
  
- Include i file con lettura % - Cutoff dichiarato

- Numero totale di file

- Numero stimato di file pertinenti

- La ricchezza stimata

- Costo medio di revisione della ricerca di un altro file pertinente

## <a name="testing-the-slice"></a>Test della sezione

Il test "Test the Slice" esegue test simili al test "Test the Rest", ma a un segmento del set di file come specificato da Relevance Read %.

Per eseguire il test "Test the Slice":
  
1. Aprire la **scheda Test \> di pertinenza.**

2. Nella scheda **Test** fare clic su **Nuovo test.** Verrà **visualizzata la finestra** di dialogo Crea test.

3. In **Nome test** e **Descrizione** digitare le informazioni.

4. **Nell'elenco Tipo di** test selezionare Testa la **sezione**.

5. **Nell'elenco Problema** selezionare il nome del problema.

6. **Nell'elenco Carica** selezionare il carico.

7. In **Lettura % tra**, accettare i valori di intervallo basso e alto predefiniti o selezionare i valori per i punteggi di rilevanza limite.

8. In **Imposta dimensioni** selezionare un valore o accettare il valore predefinito.

    Le icone di ripristino ripristinano il valore predefinito.

9. Fare **clic su Avvia tagging**. Viene generato un esempio di test.

10. Esaminare e contrassegnare ogni file nella scheda **Tag \>** di pertinenza e, al termine, fare clic su **Calcola**.

11. Nella scheda Test è possibile fare clic **su Visualizza risultati** per visualizzare i risultati del test.
