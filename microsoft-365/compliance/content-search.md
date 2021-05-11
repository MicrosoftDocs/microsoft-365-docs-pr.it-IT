---
title: Creare ed eseguire una ricerca di contenuto nel Centro conformità Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Usare lo strumento ricerca contenuto eDiscovery nel centro conformità per cercare contenuto nei diversi servizi di Microsoft 365.
ms.openlocfilehash: a058c07d080962723e9f6bc7a150cbfb5074e7db
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311666"
---
# <a name="create-a-content-search"></a>Creare una ricerca contenuto

È possibile usare lo strumento ricerca contenuto di eDiscovery nel Centro conformità Microsoft 365 per cercare elementi sul posto, come messaggi di posta elettronica, documenti e conversazioni di messaggistica istantanea nell'organizzazione. Usare questo strumento per cercare contenuto nelle origini dati di Microsoft 365 seguenti:
  
- Cassette postali di Exchange Online

- Siti di SharePoint Online e account di OneDrive for Business

- Microsoft Teams

- Gruppi di Microsoft 365

- Gruppi di Yammer

Dopo aver eseguito una ricerca, il numero di percorsi dei contenuti e il numero stimato dei risultati della ricerca vengono visualizzati nella pagina con riquadro a comparsa della ricerca. È anche possibile visualizzare rapidamente le statistiche, come i percorsi di contenuto che contengono la maggior parte degli elementi corrispondenti alla query di ricerca. Dopo l'esecuzione di una ricerca, è possibile visualizzare in anteprima i risultati o esportarli in un computer locale.

## <a name="create-and-run-a-search"></a>Creare ed eseguire una ricerca

Per potere accedere alla pagina **Ricerca contenuto** nel Centro conformità Microsoft 365 (per eseguire ricerche, visualizzare in anteprima i risultati ed esportare i risultati), un amministratore, un responsabile della conformità o un responsabile di eDiscovery deve essere membro del gruppo di ruoli Responsabile di eDiscovery nel Centro sicurezza e conformità. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).
  
1. Passare a <https://compliance.microsoft.com> e accedere con le credenziali di un account a cui sono state assegnate le autorizzazioni appropriate.

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365, fare clic su **Mostra tutto**, quindi su **Ricerca contenuto**.

3. Nella pagina **Ricerca contenuto** fare clic su **Nuova ricerca**.

   > [!NOTE]
   > L’opzione **Cerca per elenco ID** consente di cercare messaggi di posta elettronica specifici e altri elementi della cassetta postale tramite un elenco di ID di Exchange. Per creare un elenco ID di ricerca, è necessario inviare un file con valori delimitati da virgole (CSV) che identifica gli elementi della cassetta postale specifici da cercare. Per istruzioni, vedere [Preparare un file CSV per un elenco ID di ricerca](csv-file-for-an-id-list-content-search.md).

4. Digitare un nome per la ricerca, una descrizione facoltativa che aiuta a identificare la ricerca. Il nome della ricerca deve essere univoco nell'organizzazione.

5. Nella pagina **Posizioni** scegliere le posizioni di contenuto in cui eseguire la ricerca. È possibile cercare cassette postali, siti e cartelle pubbliche.

    ![Scegliere le posizioni dei contenuti da mettere in attesa](../media/ContentSearchLocations.png)
  
   1. **Cassette postali di Exchange**: impostare l'interruttore su **Attivato** e quindi fare clic su **Scegliere utenti, gruppi o team** per specificare le cassette postali da mettere in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione da mettere in attesa (per mettere in attesa le cassette postali dei membri del gruppo). È anche possibile eseguire ricerche nella cassetta postale associata a un team di Microsoft Team (per i messaggi di canale), al gruppo di Office 365 e al gruppo di Yammer. Per altre informazioni sui dati dell'applicazione archiviati nelle cassette postali, vedere [contenuto archiviato nelle cassette postali per eDiscovery](what-is-stored-in-exo-mailbox.md).

   2. **Siti di SharePoint**: impostare l'interruttore su **Attivato** quindi fare clic su **Scegli siti** per specificare i siti di SharePoint e gli account di OneDrive da mettere in blocco. Digitare l'URL per ogni sito che si desidera mettere in blocco. È anche possibile aggiungere l'URL del sito di SharePoint per un team di Microsoft Team, un gruppo di Office 365 o un gruppo di Yammer.
  
   3. **Cartelle pubbliche di Exchange**: impostare l'interruttore su **attivato** per mettere in stato di blocco tutte le cartelle pubbliche nell'organizzazione di Exchange Online. Non è possibile scegliere cartelle pubbliche specifiche da mettere in blocco. Lasciare l'interruttore disattivato se non si vuole impostare un blocco sulle cartelle pubbliche.
  
   4. Mantenere selezionata questa casella di controllo per cercare contenuto di Teams per gli utenti locali. Ad esempio, se si esegue una ricerca in tutte le cassette postali di Exchange nell'organizzazione e si seleziona questa casella di controllo, la risorsa di archiviazione basata sul cloud usata per archiviare i dati chat di Teams per gli utenti locali verrà inclusa nell'ambito della ricerca. Per altre informazioni, vedere [Cercare i dati delle chat di Teams degli utenti locali](search-cloud-based-mailboxes-for-on-premises-users.md).

6. Nella pagina **Definisci le tue condizioni di ricerca** digitare una query con parole chiave e, se necessario, aggiungere condizioni alla query di ricerca.

   ![Configurare la query di ricerca](../media/ContentSearchQuery.png)

   1. È possibile specificare parole chiave, proprietà dei messaggi come le date di invio o ricezione o proprietà dei documenti come il nome file o la data dell'ultima modifica apportata. È anche possibile usare query più complesse che usano un operatore booleano, come ad esempio **AND**, **OR**, **NOT** o **NEAR**. Se si lascia vuota la casella delle parole chiave, nei risultati della ricerca verrà incluso tutto il contenuto disponibile nelle posizioni specificate. Per altre informazioni, vedere [Query con parola chiave e condizioni di ricerca per eDiscovery](keyword-queries-and-search-conditions.md).

   2. È anche possibile fare clic sulla casella di controllo **Mostra elenco di parole chiave** e digitare una parola chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono collegate da un operatore logico (**c:s**) con funzionalità simili all’operatore **OR** nella query di ricerca creata.

      Perché usare l'elenco di parole chiave? È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave. Questo è utile per identificare rapidamente le parole chiave più e meno efficaci. È possibile usare anche una frase chiave, racchiusa tra parentesi, in una riga. Per altre informazioni sulla lista delle parole chiave e sulle statistiche di ricerca, vedere [Visualizzare statistiche delle parole chiave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Per ridurre i problemi causati dai grandi elenchi di parole chiave, è consentito un massimo di 20 righe nell'elenco di parole chiave.

   3. È possibile aggiungere delle condizioni di ricerca per circoscrivere una ricerca e ottenere un insieme di risultati più preciso. Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca. Una condizione è collegata logicamente alla query con parole chiave, specificata nell'apposita casella, dall'operatore logico (**c:c**) che ha funzionalità simili all’operatore **AND**. Ciò significa che, per essere inclusi nei risultati, gli elementi devono soddisfare sia la query con parola chiave, sia una o più condizioni. Ecco in che modo le condizioni aiutano a limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile usare in una query di ricerca, vedere [Condizioni di ricerca](keyword-queries-and-search-conditions.md#search-conditions).

7. Esaminare le impostazioni di ricerca (e modificarle se necessario) e quindi inviare la ricerca per avviarla.
  
Per accedere nuovamente alla ricerca contenuto o accedere ad altre ricerche contenuto elencate nella pagina **Ricerca contenuto**, selezionare la ricerca e quindi fare clic su **Apri**.
  
## <a name="next-steps"></a>Passaggi successivi

Ecco un elenco dei passaggi successivi da eseguire dopo la creazione e l'esecuzione di una ricerca contenuto.

- [Visualizzare l'anteprima dei risultati della ricerca](preview-ediscovery-search-results.md)

- [Visualizzare le statistiche per i risultati della ricerca](view-keyword-statistics-for-content-search.md)

- [Esportare i risultati della ricerca](export-search-results.md)

- [Esportare un report sulle ricerche](export-a-content-search-report.md)
