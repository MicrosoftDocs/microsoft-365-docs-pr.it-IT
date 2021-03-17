---
title: Creare una raccolta di bozze
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Una bozza di raccolta è una ricerca eDiscovery di origini dati depositario e non depositario in un caso advanced eDiscovery che restituisce una stima di ricerca corrispondente alla query di ricerca della raccolta. È possibile esaminare le statistiche di ricerca, visualizzare in anteprima un campionamento di elementi e rivedere ed eseguire di nuovo la raccolta prima di confermare i risultati in un set di revisione.
ms.openlocfilehash: 18f018a5e00f355c3f320a963135e76ecc51f086
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838895"
---
# <a name="create-a-draft-collection-in-advanced-ediscovery"></a>Creare una bozza di raccolta in Advanced eDiscovery

Dopo aver identificato i custodi e qualsiasi origine dati non depositario per il caso, sei pronto per identificare e individuare un set di documenti rilevanti. A tale scopo, utilizzare lo strumento Raccolte per cercare contenuto pertinente nelle origini dati. A tale scopo, creare una raccolta che esegue la ricerca di contenuto corrispondente ai criteri di ricerca specificati nelle origini dati specificate. È possibile creare una bozza di *raccolta,* che è una stima degli elementi trovati oppure è possibile creare una raccolta che aggiunge automaticamente gli elementi a un insieme di recensioni. Quando si crea una bozza di raccolta, è possibile visualizzare informazioni sui risultati stimati corrispondenti alla query di ricerca, ad esempio il numero totale e le dimensioni degli elementi trovati, le diverse origini dati in cui sono stati trovati e le statistiche relative alla query di ricerca. È inoltre possibile visualizzare in anteprima un esempio di elementi restituiti dall'insieme. Utilizzando queste statistiche, è possibile modificare la query di ricerca ed eseguire di nuovo la bozza di raccolta per limitare i risultati. Dopo aver soddisfatto i risultati della raccolta, puoi confermare la raccolta in un set di revisione. Quando si esegue il commit di una bozza di raccolta, gli elementi restituiti dalla raccolta vengono aggiunti a un insieme di revisione per la revisione, l'analisi e l'esportazione.

## <a name="before-you-create-a-draft-collection"></a>Prima di creare una raccolta bozze

- Aggiungere i custodi e le origini dati non depositario al caso prima di creare una bozza di raccolta. Questa operazione è necessaria per poter selezionare le origini dati quando si crea una raccolta di bozze. Per altre informazioni, vedere:

  - [Aggiungere responsabili a un caso](add-custodians-to-case.md)

  - [Aggiungere origini dati non correlate ai responsabili a un caso](non-custodial-data-sources.md)

- È possibile cercare in una raccolta di bozze altre origini dati(quelle che non sono state aggiunte al caso come posizioni di custodia o non depositario) per trovare contenuti che potrebbero essere rilevanti per il caso. Queste origini dati possono includere cassette postali, siti di SharePoint e Teams. Se questa situazione è applicabile al caso, compilare un elenco di queste origini dati in modo da poterle aggiungere alla raccolta.

## <a name="create-a-draft-collection"></a>Creare una raccolta di bozze

1. Nel Centro conformità Microsoft 365 aprire il caso Advanced eDiscovery e quindi selezionare la **scheda** Raccolte.

2. Nella pagina **Raccolte** selezionare **Nuovo insieme**  >  **Standard.**

3. Digitare un nome (obbligatorio) e una descrizione (facoltativo) per la raccolta. Dopo aver creato la raccolta, non è possibile modificare il nome, ma è possibile modificare la descrizione.

4. Nella pagina **Origini dati di** custodia eseguire una delle operazioni seguenti per identificare le origini dati di custodia da cui raccogliere il contenuto:

   - Fare **clic su Seleziona i** custodi per cercare i custodi specifici che sono stati aggiunti al caso. Se si utilizza questa opzione, viene visualizzato un elenco dei custodi del caso. Selezionare uno o più custodi. Dopo aver selezionato e aggiunto i custodi, è anche possibile selezionare le origini dati specifiche per cercare ogni responsabile. Queste origini dati visualizzate sono state specificate quando il responsabile è stato aggiunto al caso.

   - Fare clic **sull'interruttore** Seleziona tutto per cercare tutti i custodi aggiunti al caso. Quando si seleziona questa opzione, vengono cercate tutte le origini dati per tutti i custodi.

5. Nella pagina **Origini** dati non di custodia eseguire una delle operazioni seguenti per identificare le origini dati non di tipo non depositario da cui raccogliere il contenuto:

   - Fare **clic su Seleziona** origini dati non di custodia per selezionare origini dati non di custodia specifiche aggiunte al caso. Se si utilizza questa opzione, verrà visualizzato un elenco di origini dati. Selezionare una o più di queste origini dati.

   - Fare clic **sull'interruttore** Seleziona tutto per selezionare tutte le origini dati non di custodia aggiunte al caso.

6. Nella pagina **Origini dati aggiuntive** è possibile selezionare altre cassette postali e siti in cui eseguire la ricerca nell'ambito della raccolta. Questi tipi di origini dati non sono stati aggiunti come posizioni di dati depositario o non depositario nel caso. Sono inoltre disponibili due opzioni per la ricerca di origini dati aggiuntive:

   - Per cercare in tutti i percorsi di contenuto un servizio specifico (cassette postali di Exchange, siti di SharePoint e OneDrive o cartelle pubbliche di Exchange), fare clic sull'interruttore **Seleziona** tutto corrispondente nella **colonna** Stato. Questa opzione consente di cercare tutti i percorsi di contenuto nel servizio selezionato.

   - Per cercare un percorso di contenuto  specifico per un  servizio, fare clic sull'interruttore Seleziona tutto  corrispondente nella colonna Stato e quindi fare clic su **Utenti,** gruppi o team (per le cassette postali di Exchange) o Scegli siti per (siti di SharePoint e OneDrive) per cercare percorsi di contenuto specifici.

7. Nella pagina **Condizioni** è possibile creare la query di ricerca utilizzata per raccogliere gli elementi dalle origini dati identificate nelle pagine precedenti della procedura guidata. Puoi cercare parole chiave, coppie property:value o usare un elenco di parole chiave. È inoltre possibile aggiungere diverse condizioni di ricerca per restringere l'ambito della raccolta. Per ulteriori informazioni, vedere [Creare query di ricerca per raccolte.](building-search-queries.md)

8. Nella pagina **Salva come bozza o aggiungi a revisione set** selezionare Salva raccolta come **bozza.**

   > [!NOTE]
   > L'altra opzione in questa pagina ti consente di raccogliere elementi e aggiungerli direttamente a un set di recensioni. Invece di creare una bozza di raccolta per cui è possibile esaminare le statistiche e visualizzare in anteprima un campione dei risultati della raccolta, questa opzione ignora tale processo e aggiunge automaticamente la raccolta a un set di recensioni. Se si seleziona la seconda opzione per aggiungere la raccolta a un set di revisione, sono disponibili ulteriori impostazioni da configurare, ad esempio la raccolta di interi thread di conversazione di chat in Microsoft Teams e Yammer e la raccolta di allegati cloud (denominati anche allegati *moderni).* Per ulteriori informazioni su queste impostazioni, vedere [Commit a draft collection to a review set](commit-draft-collection.md).

9. Nella pagina **Rivedi raccolta** è possibile esaminare e aggiornare le impostazioni di raccolta configurate nelle pagine precedenti.

   - **Scheda** Riepilogo: esaminare e modificare il nome e la descrizione della raccolta, i criteri di ricerca della raccolta, i percorsi di dati aggiuntivi e il tipo di raccolta.

   - **Scheda** Origini: esaminare e modificare le origini dati di custodia e non di custodia per la raccolta.

10. Fare **clic su** Invia per creare la raccolta bozze. Viene visualizzata una pagina che conferma la creazione della raccolta.

## <a name="what-happens-after-you-create-a-draft-collection"></a>Cosa succede dopo aver creato una raccolta di bozze

Dopo aver creato una raccolta di  bozze, questa viene elencata nella pagina Raccolte nel caso e lo stato indica che è in corso. Un processo denominato **Preparazione dell'anteprima della** ricerca e delle stime viene inoltre creato e visualizzato nella **pagina** Processi nel caso.

Durante il processo di raccolta delle bozze, Advanced eDiscovery esegue una stima della ricerca utilizzando i criteri di ricerca e le origini dati specificati nella raccolta. Advanced eDiscovery prepara anche un campionamento di elementi che è possibile visualizzare in anteprima. Al termine dell'insieme, vengono aggiornate le colonne seguenti e i valori corrispondenti nella **pagina** Raccolta:

![Stati di stato per una bozza di raccolta](../media/DraftCollectionStatus.png)

- **Status**: indica lo stato e il tipo di raccolta. Il valore **Stimato indica** che una bozza di raccolta è stata completata. Questo stesso valore indica anche che la raccolta è una raccolta di bozze e che non è stata aggiunta a un insieme di recensioni. Il valore **Committed** nella **colonna Status** indica che la raccolta è stata aggiunta a un set di revisioni.

- **Stato stima:** indica lo stato dei risultati della ricerca stimati e indica se le stime e le statistiche della ricerca sono pronte per la revisione. Il valore **Successful** indica che i risultati della bozza di raccolta sono pronti per la revisione. Dopo aver inviato per la prima volta una bozza di raccolta, viene visualizzato il valore **In** corso per indicare che la raccolta è ancora in esecuzione

- **Stato anteprima**: Indica lo stato degli elementi di esempio che è possibile visualizzare in anteprima. Il valore **Successful indica** che gli elementi sono pronti per l'anteprima. Dopo aver inviato per la prima volta una bozza di raccolta, viene visualizzato il valore **In** corso per indicare che la raccolta è ancora in esecuzione.

## <a name="next-steps-after-a-draft-collection-is-complete"></a>Passaggi successivi al completamento di una raccolta di bozze

Al termine della raccolta delle bozze, è possibile eseguire diverse attività. Per eseguire la maggior parte di queste attività, è sufficiente passare alla **scheda Raccolte** e fare clic sul nome della raccolta bozze per visualizzare la pagina a comparsa.

![Pagina a comparsa per una raccolta di bozze](../media/DraftCollectionFlyoutPage.png)

Ecco un elenco di operazioni che puoi eseguire dalla pagina del riquadro a comparsa della raccolta:

- Selezionare la **scheda Riepilogo** per visualizzare le informazioni di riepilogo sulla raccolta e i risultati di ricerca stimati restituiti dalla raccolta. Ciò include il numero totale di elementi e le dimensioni dei risultati di ricerca stimati, il numero di cassette postali e siti che contenevano risultati di ricerca e le condizioni di ricerca (se utilizzate) utilizzate per l'ambito della raccolta.

- Selezionare la **scheda Origini** dati per visualizzare un elenco dei custodi e delle origini dati non depositario) che sono stati cercati nella raccolta. Eventuali percorsi di contenuto aggiuntivi in cui è stata ricercata sono elencati in **Percorsi** nella **scheda** Riepilogo.

- Selezionare la **scheda Statistiche di** ricerca per visualizzare le statistiche sulla raccolta. Sono inclusi il numero totale e le dimensioni degli elementi trovati in ogni servizio (ad esempio, cassette postali di Exchange o siti di SharePoint) e un report di condizione che visualizza le statistiche sul numero di elementi restituiti dai diversi componenti della query di ricerca utilizzata dalla raccolta. Per ulteriori informazioni, vedere [Statistiche e report di raccolta.](collection-statistics-reports.md)

- Fai **clic su** Rivedi esempio nella parte inferiore della pagina a comparsa per visualizzare un'anteprima di un esempio degli elementi restituiti dalla raccolta.

- Eseguire il commit della raccolta bozze in un set di revisione (facendo clic **su**  >  **Azioni Modifica raccolta).** Ciò significa che esegui di nuovo la raccolta (usando le impostazioni correnti) e aggiungi gli elementi restituiti dalla raccolta a un set di revisione. Come spiegato in precedenza, puoi anche configurare impostazioni aggiuntive (ad esempio il threading delle conversazioni e gli allegati basati sul cloud) quando aggiungi la raccolta a un set di recensioni. Per ulteriori informazioni e istruzioni dettagliate, vedere [Commit a draft collection to a review set](commit-draft-collection.md).

## <a name="manage-a-draft-collection"></a>Gestire una raccolta di bozze

È possibile utilizzare le opzioni del menu **Azioni** nella pagina a comparsa di una bozza di raccolta per eseguire diverse attività di gestione.

![Opzioni del menu Azioni per la raccolta delle bozze](../media/DraftCollectionActionsMenu.png)

Ecco le descrizioni delle opzioni di gestione.

- **Modifica raccolta:** modificare le impostazioni della raccolta bozze. Dopo aver apportato le modifiche, è possibile rieseguire la raccolta e aggiornare le stime e le statistiche della ricerca. Come spiegato in precedenza, questa opzione viene utilizzata per confermare una bozza di raccolta in un set di revisione.  

- **Elimina raccolta:** elimina una raccolta di bozze. Si noti che dopo il commit di una raccolta di bozze in un set di revisioni, non può essere eliminata.

- **Stime di aggiornamento:** eseguire di nuovo la query (rispetto alle origini dati) specificata nella raccolta bozza per aggiornare le stime e le statistiche della ricerca.

- **Esporta come report**: esporta le informazioni sulla raccolta di bozze in un file CSV che è possibile scaricare nel computer locale. Il report di esportazione contiene le informazioni seguenti:

  - Identità di ogni percorso di contenuto contenente elementi che corrispondono alla query di ricerca nella raccolta bozze. Questi percorsi sono in genere cassette postali o siti.
  
  - Numero totale di elementi in ogni percorso di contenuto.
  
  - Dimensione totale, in byte, degli elementi in ogni percorso di contenuto.

  - Servizio (ad esempio Exchange o SharePoint) in cui si trova il percorso del contenuto.

- **Copia raccolta:** crea una nuova raccolta di bozze copiando le impostazioni da una raccolta esistente. È necessario utilizzare un nome diverso per la nuova raccolta. È inoltre possibile modificare le impostazioni prima di inviare la nuova raccolta. Dopo l'invio, viene eseguita la query di ricerca e vengono generate nuove stime e statistiche. È un buon modo per creare rapidamente ulteriori bozze di raccolta e quindi modificare le impostazioni selezionate in base alle esigenze conservando comunque le informazioni nella raccolta originale. In questo modo puoi anche confrontare facilmente i risultati di due raccolte simili.

> [!NOTE]
> Dopo il commit di una bozza di raccolta in un set di revisione, è possibile copiare solo la raccolta ed esportare un report.
