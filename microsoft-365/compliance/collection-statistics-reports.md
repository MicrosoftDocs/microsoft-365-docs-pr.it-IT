---
title: Statistiche e report di raccolta
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come accedere e utilizzare statistiche e report per bozze di raccolte e raccolte che sono state impegnate in un set di revisione in Advanced eDiscovery.
ms.openlocfilehash: 5edbd4a3b7212e027c777ed6ce5284f4e9cf595c
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838930"
---
# <a name="collection-statistics-and-reports-in-advanced-ediscovery"></a>Statistiche e report di raccolta in Advanced eDiscovery

Dopo aver creato una bozza di raccolta, è possibile visualizzare le statistiche sugli elementi recuperati, ad esempio le posizioni del contenuto che contengono la maggior parte degli elementi corrispondenti ai criteri di ricerca e il numero di elementi restituiti dalla query di ricerca. È inoltre possibile visualizzare un'anteprima di un sottoinsieme dei risultati.

Dopo aver identificato il set di documenti che si desidera esaminare ulteriormente, è possibile aggiungere i risultati della ricerca a un set di revisione da raccogliere ed elaborare.

## <a name="statistics-and-reports-for-draft-collections"></a>Statistiche e report per le bozze di raccolte

In questa sezione vengono descritte le statistiche disponibili per le bozze delle raccolte. Queste statistiche sono disponibili nella scheda **Statistiche** di ricerca nella pagina a comparsa di una bozza di raccolta.

### <a name="collection-estimates"></a>Stime di raccolta

In questa sezione viene visualizzato un riepilogo grafico degli elementi stimati restituiti dall'insieme. Indica il numero di elementi che soddisfano i criteri di ricerca dell'insieme. Queste informazioni danno un'idea del numero stimato di elementi restituiti dall'insieme.

![Stime di raccolta per una bozza di raccolta](../media/AeDCollectionEstimates.png)

- **Elementi stimati in base alle** posizioni : numero totale di elementi stimati restituiti dall'insieme. Viene inoltre visualizzato il numero specifico di elementi presenti nelle cassette postali e nei siti.

- **Posizioni stimate con riscontri**: numero totale di percorsi di contenuto che contengono elementi restituiti dalla raccolta. Viene inoltre visualizzato il numero specifico di posizioni di cassette postali e siti.

- **Volume di dati per posizione (in MB):** dimensione totale di tutti gli elementi stimati restituiti dalla raccolta. Vengono inoltre visualizzate le dimensioni specifiche degli elementi delle cassette postali e degli elementi del sito.

### <a name="condition-report"></a>Rapporto condizioni

In questa sezione vengono visualizzate le statistiche relative alla query di ricerca di raccolta e al numero di elementi stimati corrispondenti a parti diverse della query di ricerca. È possibile utilizzare queste statistiche per analizzare il numero di elementi che corrispondono a ogni componente della query di ricerca. In questo modo è possibile perfezionare i criteri di ricerca per la raccolta e, se necessario, limitare l'ambito della raccolta.

- **Tipo di percorso**: Tipo di percorso del contenuto a cui sono applicabili le statistiche della query. Il valore di **Exchange indica** la posizione di una cassetta postale. il valore **SharePoint indica** la posizione di un sito.

- **Parte**: parte della query di ricerca a cui sono applicabili le statistiche. **Primary** indica l'intera query di ricerca. **Keyword** indica che le statistiche nella riga sono relative a una parola chiave specifica. Se si utilizza un elenco di parole chiave per la query di ricerca nell'insieme, le statistiche per ogni componente della query vengono incluse in questa tabella.

- **Condition**: Componente effettivo (parola chiave o condizione) della query di ricerca eseguita per la raccolta draft che ha restituito le statistiche visualizzate nella riga corrispondente.

- **Posizioni con risultati**: Numero delle posizioni  del contenuto (specificate dalla colonna Tipo percorso) che contengono gli elementi che corrispondono alla query principale o parola chiave elencata nella **colonna** Condizione.

- **Elementi**: numero di elementi (dal percorso di contenuto specificato) che corrispondono alla query elencata nella **colonna** Condizione. Come spiegato in precedenza, se un elemento contiene più istanze di una parola chiave in fase di ricerca, viene conteggiato una sola volta in questa colonna.

- **Dimensione (MB):** dimensione totale di tutti gli elementi trovati (nel percorso di contenuto specificato) che corrispondono alla query di ricerca nella **colonna** Condizione.

### <a name="top-locations"></a>Posizioni principali

In questa sezione vengono visualizzate le statistiche relative ai percorsi di contenuto specifici con la maggior parte degli elementi restituiti dalla raccolta.

- Nome del nome della posizione (l'indirizzo di posta elettronica delle cassette postali e l'URL per i siti).

- Tipo di posizione (una cassetta postale o un sito).

- Numero stimato di elementi nel percorso del contenuto restituito dalla raccolta.

- Dimensione totale degli elementi stimati in ogni percorso di contenuto.

## <a name="statistics-and-reports-for-committed-collections"></a>Statistiche e report per le raccolte di cui è stato eseguito il commit

In questa sezione vengono descritte le statistiche disponibili dopo il commit di una raccolta in un set di recensioni, incluso il numero effettivo di elementi aggiunti al set di recensioni. Queste statistiche, oltre alle informazioni sul set di caricamento, forniscono informazioni cronologiche sul contenuto aggiunto a un caso.

Dopo aver eseguito il commit di una raccolta in un set di revisione, nella pagina a comparsa della connessione di cui è stato eseguito il commit vengono visualizzate le schede seguenti. Ognuna di queste schede contiene diversi tipi di informazioni sull'insieme.

![Schede nella pagina a comparsa della raccolta di cui è stato eseguito il commit](../media/CommittedCollectionFlyoutPage.png)

### <a name="collection-contents"></a>Contenuto della raccolta

Questa sezione della **scheda Riepilogo** contiene statistiche e altre informazioni sugli elementi raccolti dalle origini dati nella raccolta e aggiunti al set di revisioni.

- **Totale elementi estratti**. Numero totale di elementi aggiunti al set di revisioni. Questo numero indica la somma degli elementi padre e figlio aggiunti al set di revisioni.

  > [!TIP]
  > Posizionare il puntatore del mouse sulle barre degli elementi padre o figlio per visualizzare il numero totale di elementi padre o figlio.

- **Elementi padre**. Numero di elementi restituiti dall'insieme utilizzati per raccogliere gli elementi aggiunti al set di revisione. Questo numero corrisponde (ed è uguale al) numero stimato di elementi visualizzato nella **sezione Parametri raccolta.** Numero di elementi padre che raccoglie le informazioni utilizzate per raccogliere gli elementi aggiunti al set di revisioni.
 
   Un elemento padre può contenere più elementi figlio. Ad esempio, un messaggio di posta elettronica è un elemento padre se contiene un file allegato o ha un allegato cloud. In questo caso, il file allegato o la destinazione dell'allegato cloud sono considerati elementi figlio. Quando si esegue il commit di una raccolta, gli elementi padre e gli elementi figlio corrispondenti vengono aggiunti al set di revisione come singoli elementi o file.

- **Elementi figlio**. Numero di elementi figlio aggiunti al set di revisioni. Gli elementi figlio sono allegati o altre parti di un elemento padre. Gli elementi figlio includono file allegati, allegati cloud, immagini e firme di posta elettronica. Quando si esegue il commit di una raccolta in un set di revisione, gli elementi figlio vengono estratti, indicizzati e aggiunti al set di revisione come singoli file.

- **Elementi univoci**. Numero di elementi univoci aggiunti al set di revisioni. Gli elementi univoci sono univoci per il set di recensioni. Tutti gli elementi sono univoci quando la prima raccolta viene aggiunta a un nuovo set di revisioni perché non sono presenti elementi precedenti nel set di recensioni.

- **Elementi duplicati identificati**. Numero di elementi della raccolta che non sono stati aggiunti al set di revisioni perché lo stesso elemento esiste già nel set di revisione. Le statistiche sugli elementi duplicati consentono di spiegare le differenze tra il numero di elementi stimati di una raccolta di bozze e il numero effettivo di elementi aggiunti al set di recensioni.

### <a name="indexing"></a>Indicizzazione

La **sezione Indicizzazione** nella scheda Riepilogo **di** un set di revisioni di cui è stato eseguito il commit contiene informazioni di indicizzazione sugli elementi aggiunti al set di revisione.

**Nuovi elementi indicizzati**. Numero di elementi appena indicizzati prima di essere aggiunti al set di revisioni. Un esempio di elemento appena indicizzato sono gli elementi figlio estratti da un elemento padre e quindi indicizzati prima di essere aggiunti al set di revisioni. Inoltre, gli elementi che non si trovano nelle origini dati di  archiviazione e nei percorsi di contenuto non depositario elencati nella scheda Origini dati nel caso vengono indicizzati prima di essere aggiunti alla revisione. Ad esempio, i nuovi elementi indicizzati includerebbero gli elementi raccolti da posizioni aggiuntive.

**Elementi indicizzati aggiornati**. Numero di elementi parzialmente indicizzati correttamente indicizzati e aggiunti al set di revisioni. In questo modo, gli elementi parzialmente indicizzati da  posizioni di contenuto di tipo depositario e non depositario vengono indicizzati correttamente quando è stato eseguito il commit della raccolta nel set di revisioni.

**Errori di indicizzazione**. Numero di elementi parzialmente indicizzati che non è stato possibile indicizzare prima di essere aggiunti al set di revisioni. Questi elementi potrebbero richiedere la correzione degli errori.

### <a name="collection-parameters"></a>Parametri di raccolta

In questa sezione vengono visualizzate le informazioni sulla raccolta utilizzate per raccogliere gli elementi aggiunti al set di revisioni. In questa scheda vengono visualizzate informazioni simili a quelle della **scheda Statistiche di** ricerca. In questa sezione viene fornita una rapida panoramica della query di ricerca utilizzata dalla raccolta, dei percorsi di contenuto in cui è stata eseguita la ricerca e dei risultati stimati della raccolta. Come spiegato in precedenza, il numero di elementi stimati in questa sezione sarà uguale al numero di elementi padre visualizzati nella **sezione Contenuto raccolta.**

### <a name="search-statistics-tab"></a>Scheda Statistiche di ricerca

Le statistiche visualizzate nella scheda **Statistiche** di ricerca sono le stesse dell'ultima volta che è stata eseguita una bozza di raccolta. Sono incluse le stime di raccolta, il report delle condizioni e le posizioni principali. Queste informazioni vengono conservate dalla raccolta di bozze per riferimento cronologico e possono essere confrontate con la raccolta effettiva di cui è stato eseguito il commit nel set di revisione.

## <a name="differences-between-draft-collection-estimates-and-the-actual-committed-collection"></a>Differenze tra le stime di raccolta bozze e la raccolta di cui è stato eseguito il commit effettivo

Quando si esegue una bozza di raccolta, nella scheda Riepilogo e nella sezione Stime raccolta della  scheda Statistiche di  ricerca viene visualizzata una stima del numero di elementi (e delle relative dimensioni totali) che soddisfano i criteri di raccolta.  Dopo aver eseguito il commit di una raccolta di bozze in un set di recensioni, il numero effettivo di elementi (e le relative dimensioni totali) aggiunti al set di recensioni è spesso diverso dalle stime. Nella maggior parte dei casi, al set di revisioni vengono aggiunti più elementi di quelli stimati dalla raccolta delle bozze. Nell'elenco seguente vengono descritti i motivi più comuni per queste differenze e i suggerimenti per identificarle:

- **Elementi figlio**. Elementi figlio estratti dagli elementi padre e aggiunti come singoli file. Il numero di elementi figlio può aumentare in modo significativo il numero di elementi effettivamente aggiunti al set di revisioni. In generale, il numero di  elementi padre identificati  nella sezione Contenuto raccolta nella scheda Riepilogo di una raccolta di cui è stato eseguito il commit deve essere uguale al numero di elementi stimati della raccolta bozza.

- **Elementi duplicati**. Gli elementi della raccolta di bozze già aggiunti al set di recensioni in una raccolta precedente non verranno aggiunti. Come spiegato in precedenza, il numero di elementi duplicati nell'insieme viene visualizzato nella **sezione Contenuto** raccolta della **scheda** Riepilogo.

- **Opzioni di configurazione della raccolta**. Quando si esegue il commit di una raccolta di bozze in un insieme di revisioni, è necessario scegliere di includere thread di conversazione, allegati cloud e versioni di documenti. Uno di questi elementi aggiunti al set di revisione non è incluso nelle stime della raccolta di bozze. Vengono identificati e raccolti solo quando si esegue il commit della raccolta. La selezione di queste opzioni probabilmente aumenterà il numero di elementi aggiunti al set di recensioni. 

    Ad esempio, più versioni dei documenti di SharePoint non sono incluse nella stima per la raccolta bozze. Tuttavia, se si seleziona l'opzione per includere tutte le versioni dei documenti quando si esportano i risultati della ricerca, il numero effettivo (e la dimensione totale) degli elementi aggiunti al set di revisioni aumenta. 

    Per ulteriori informazioni su queste opzioni, vedere [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery). 

Ecco altri motivi per cui i risultati stimati di una bozza di raccolta possono essere diversi rispetto ai risultati effettivi di cui è stato eseguito il commit.

- **Il modo in cui i risultati vengono stimati per le bozze delle raccolte**. Una stima dei risultati della ricerca restituiti da una bozza di raccolta è semplicemente una stima (e non un conteggio effettivo) degli elementi che soddisfano i criteri di query di raccolta. Per compilare la stima degli elementi di posta elettronica, dal database di Exchange viene richiesto un elenco degli ID dei messaggi che soddisfano i criteri di ricerca. Tuttavia, quando si esegue il commit della raccolta in un insieme di revisione, la raccolta viene rieseguita e i messaggi effettivi vengono recuperati dal database di Exchange. Di conseguenza, le differenze potrebbero derivare dal modo in cui vengono determinati il numero stimato di elementi e il numero effettivo di elementi.

- **Modifiche che si verificano tra il momento in cui si esegue la stima e il commit delle raccolte di bozze.** Quando si esegue il commit di una bozza di raccolta in un set di revisione, la ricerca viene rieseguita per raccogliere gli elementi più recenti nell'indice di ricerca che soddisfano i criteri di ricerca. È possibile che altri elementi sono stati creati, inviati o eliminati che soddisfano i criteri di ricerca nel periodo compreso tra l'ultima esecuzione della raccolta bozze e il commit della raccolta bozze in un set di revisione. È inoltre possibile che gli elementi presenti nell'indice di ricerca quando sono stati stimati i risultati della bozza della raccolta non siano più presenti perché sono stati eliminati da un'origine dati prima di eseguire il commit della raccolta. Un modo per ovviare a questo problema è specificare un intervallo di date per una raccolta. Un altro modo è quello di conservare i percorsi del contenuto in modo che gli elementi siano conservati e non possano essere eliminati.

- **Elementi non indicizzati**. Se la raccolta di bozze includeva la ricerca in tutte le cassette postali di Exchange o in tutti i siti di SharePoint, solo gli elementi non indicizzati delle posizioni di contenuto contenenti elementi che soddisfano i criteri di raccolta verranno aggiunti al set di revisione. In altre parole, se non vengono trovati risultati in una cassetta postale o in un sito, gli eventuali elementi non indicizzati in tale cassetta postale o sito non verranno aggiunti al set di revisione. Tuttavia, gli elementi non indicizzati da tutti i percorsi di contenuto (anche quelli che non contengono elementi che corrispondono alla query di raccolta) verranno inclusi nei risultati stimati della raccolta.

    In alternativa, se la raccolta di bozze include percorsi di contenuto  specifici (ovvero cassette postali o siti specifici in cui è specificato nella pagina Percorsi aggiuntivi nella procedura guidata di raccolta delle bozze), verranno esportati gli elementi non indicizzati (non esclusi dai criteri di raccolta) dai percorsi di contenuto specificati nella ricerca. In questo caso, il numero stimato di elementi non indicizzati e il numero di elementi non indicizzati aggiunti al set di revisioni devono essere uguali.
