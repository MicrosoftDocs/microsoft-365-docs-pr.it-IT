---
title: Visualizzare le statistiche per i risultati della ricerca eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Informazioni su come utilizzare la funzionalità delle statistiche di ricerca per visualizzare le statistiche per le ricerche di contenuto e le ricerche associate a un caso di eDiscovery di base nel Centro Microsoft 365 conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311114"
---
# <a name="view-statistics-for-ediscovery-search-results"></a>Visualizzare le statistiche per i risultati della ricerca eDiscovery

Dopo aver creato ed eseguito una ricerca contenuto o una ricerca associata a un caso di eDiscovery di base, è possibile visualizzare le statistiche sui risultati della ricerca stimati. Include un riepilogo dei risultati della ricerca (simile al riepilogo dei risultati di ricerca stimati visualizzati nella pagina del riquadro a comparsa di ricerca), le statistiche delle query, ad esempio il numero di percorsi di contenuto con elementi che corrispondono alla query di ricerca e l'identità dei percorsi di contenuto con il maggior numero di elementi corrispondenti.
  
È inoltre possibile utilizzare l'elenco delle parole chiave per configurare una ricerca in modo da restituire statistiche per ogni parola chiave in una query di ricerca. In questo modo è possibile confrontare il numero di risultati restituiti da ogni parola chiave in una query.
  
È inoltre possibile scaricare le statistiche di ricerca in un file CSV. Questo consente di usare le funzionalità di filtro e ordinamento di Excel per confrontare i risultati e preparare report per i risultati della ricerca.
  
## <a name="get-statistics-for-searches"></a>Ottenere statistiche per le ricerche

Per visualizzare le statistiche per una ricerca contenuto o una ricerca associata a un caso di eDiscovery di base.
  
1. Nel Centro Microsoft 365 conformità fare clic **su Mostra tutto** e quindi eseguire una delle operazioni seguenti:

   - Fare **clic su Ricerca** contenuto e quindi selezionare una ricerca per visualizzare la pagina a comparsa.

     OPPURE

   - Fare **clic su eDiscovery** Core, selezionare un caso e quindi selezionare una ricerca nella  >   **scheda** Ricerche per visualizzare la pagina a comparsa.

2. Nella pagina a comparsa della ricerca selezionata fare clic sulla **scheda Statistiche di** ricerca.
  
   ![Scheda Statistiche di ricerca](../media/SearchStatistics1.png)

La **scheda Statistiche** di ricerca contiene le sezioni seguenti che contengono diversi tipi di statistiche sulla ricerca.

### <a name="search-content"></a>Ricerca contenuto

In questa sezione viene visualizzato un riepilogo grafico degli elementi stimati restituiti dalla ricerca. Indica il numero di elementi che soddisfano i criteri di ricerca. Queste informazioni danno un'idea del numero stimato di elementi restituiti dalla ricerca.

![Stime di ricerca per una ricerca](../media/SearchContentReport.png)

- **Elementi stimati in base alle** posizioni : numero totale di elementi stimati restituiti dalla ricerca. Viene inoltre visualizzato il numero specifico di elementi presenti nelle cassette postali e nei siti.

- **Posizioni stimate con risultati**: numero totale di percorsi di contenuto che contengono elementi restituiti dalla ricerca. Viene inoltre visualizzato il numero specifico di posizioni di cassette postali e siti.

- **Volume di dati per posizione (in MB):** dimensione totale di tutti gli elementi stimati restituiti dalla ricerca. Vengono inoltre visualizzate le dimensioni specifiche degli elementi delle cassette postali e degli elementi del sito.

### <a name="condition-report"></a>Rapporto condizioni

In questa sezione vengono visualizzate statistiche sulla query di ricerca e sul numero di elementi stimati corrispondenti a parti diverse della query di ricerca. È possibile utilizzare queste statistiche per analizzare il numero di elementi che corrispondono a ogni componente della query di ricerca. In questo modo è possibile perfezionare i criteri di ricerca e, se necessario, limitare l'ambito dell'ambito. È inoltre possibile scaricare una copia di questo report in formato CSV.

![Rapporto condizioni](../media/SearchContentReportNoKeywordList.png)

- **Tipo di percorso**: Tipo di percorso del contenuto a cui sono applicabili le statistiche della query. Il valore di **Exchange** indica la posizione di una cassetta postale; il valore **SharePoint** indica la posizione di un sito.

- **Parte**: parte della query di ricerca a cui sono applicabili le statistiche. **Primary** indica l'intera query di ricerca. **Keyword** indica che le statistiche nella riga sono relative a una parola chiave specifica. Se si utilizza un elenco di parole chiave per la query di ricerca, le statistiche per ogni componente della query vengono incluse in questa tabella. Per ulteriori informazioni, vedere [Get keyword statistics for searches](#get-keyword-statistics-for-searches).

- **Condizione**: Componente effettivo (parola chiave o condizione) della query di ricerca che ha restituito le statistiche visualizzate nella riga corrispondente.

- **Posizioni con risultati**: Numero delle posizioni  del contenuto (specificate dalla colonna Tipo percorso) che contengono gli elementi che corrispondono alla query principale o parola chiave elencata nella **colonna** Condizione.

- **Elementi**: numero di elementi (dal percorso di contenuto specificato) che corrispondono alla query elencata nella **colonna** Condizione. Come spiegato in precedenza, se un elemento contiene più istanze di una parola chiave in fase di ricerca, viene conteggiato una sola volta in questa colonna.

- **Dimensione (MB):** dimensione totale di tutti gli elementi trovati (nel percorso di contenuto specificato) che corrispondono alla query di ricerca nella **colonna** Condizione.

### <a name="top-locations"></a>Posizioni principali

In questa sezione vengono visualizzate le statistiche relative alle posizioni di contenuto specifiche con la maggior parte degli elementi restituiti dalla ricerca. Vengono visualizzati i primi 1.000 percorsi. È inoltre possibile scaricare una copia di questo report in formato CSV.

- Nome del nome della posizione (l'indirizzo di posta elettronica delle cassette postali e l'URL per i siti).

- Tipo di posizione (una cassetta postale o un sito).

- Numero stimato di elementi nel percorso del contenuto restituito dalla ricerca.

- Dimensione totale degli elementi stimati in ogni percorso di contenuto.

## <a name="get-keyword-statistics-for-searches"></a>Ottenere statistiche sulle parole chiave per le ricerche

Come spiegato in precedenza, nella sezione **Rapporto** condizione vengono mostrati la query di ricerca e il numero (e le dimensioni) degli elementi che corrispondono alla query. Se si utilizza un elenco di parole chiave quando si crea o si modifica una query di ricerca, è possibile ottenere statistiche avanzate che mostrano quanti elementi corrispondono a ogni parola chiave o frase chiave. Ciò consente di identificare rapidamente quali parti della query sono più (e meno) efficaci. Ad esempio, se una parola chiave restituisce un numero elevato di elementi, è possibile scegliere di perfezionare la query con parole chiave per restringere i risultati della ricerca.

Per creare un elenco di parole chiave e visualizzare le statistiche delle parole chiave per una ricerca:
  
1. Nel Centro Microsoft 365 conformità creare una nuova ricerca contenuto o una ricerca associata a un caso di eDiscovery di base.

2. Nella pagina **Condizioni** della procedura guidata di ricerca. selezionare la **casella di controllo Mostra elenco parole chiave.**

   ![Casella di controllo Mostra elenco parole chiave](../media/SearchKeywordsList1.png)

3. Digitare una parola chiave o una fase di parola chiave in una riga della tabella delle parole chiave. Ad esempio, digitare **budget** nella prima riga, digitare **sicurezza** nella seconda riga e **FY2021** nella terza riga.

   ![Digitare fino a 20 parole chiave o frasi chiave nell'elenco](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > Per ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, è possibile utilizzare un massimo di 20 righe nell'elenco di parole chiave di una query di ricerca.

4. Dopo aver aggiunto le parole chiave all'elenco per cui si desidera cercare e ottenere statistiche, eseguire la ricerca.

5. Al termine della ricerca, selezionarla per visualizzare la pagina a comparsa.

6. Nella scheda **Statistiche di** ricerca fare clic sul report **Condizione per** visualizzare le statistiche delle parole chiave per la ricerca.

    ![Vengono visualizzate le statistiche per ogni parola chiave](../media/SearchKeywordsList3.png)
  
    Come mostrato nella schermata precedente, vengono visualizzate le statistiche per ogni parola chiave. ciò include:

    - Statistiche delle parole chiave per ogni tipo di percorso di contenuto incluso nella ricerca.

    - Numero di elementi della cassetta postale non indicizzati.

    - Query di ricerca effettiva e risultati per ogni parola chiave (identificata come **Parola** chiave nella **colonna Part),** che include tutte le condizioni della query di ricerca.

    - La query di ricerca completa (identificata come **Primaria** nella **colonna Part)** e le statistiche per la query completa per ogni tipo di posizione. Si noti che si tratta delle stesse statistiche visualizzate nella **scheda** Riepilogo.
