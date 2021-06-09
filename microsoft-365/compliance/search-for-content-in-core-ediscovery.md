---
title: Cercare contenuto in un caso di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Cercare contenuto che potrebbe essere rilevante per un caso di eDiscovery di base.
ms.openlocfilehash: 8d2e2a20135312a8f111a071abbe77b03b8e8363
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311778"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Cercare contenuto in un caso di eDiscovery di base

Dopo aver creato un caso di eDiscovery di base e messo in attesa le persone di interesse nel caso, è possibile creare ed eseguire una o più ricerche di contenuto pertinenti al caso. Le ricerche associate a un caso di  eDiscovery di base non sono elencate nella pagina Ricerca contenuto nel Centro Microsoft 365 conformità. Queste ricerche sono elencate nella **pagina Ricerche** del caso Core eDiscover a cui sono associate le ricerche. Ciò significa anche che le ricerche associate a un caso possono essere accessibili solo dai membri del caso.

Per creare una ricerca eDiscovery di base:
  
1. Accedere a e accedere utilizzando le credenziali per l'account utente a cui sono state assegnate le autorizzazioni eDiscovery appropriate ed <https://compliance.microsoft.com> è membro del caso.

2. Nel riquadro di spostamento sinistro del Centro Microsoft 365 conformità fare clic su **Mostra** tutto e quindi su **eDiscovery > Core**.

3. Nella pagina **Core eDiscovery** selezionare il caso in cui si desidera creare una ricerca associata e quindi fare clic **su Apri caso.**

4. Nella **home** page del caso fare clic sulla **scheda Ricerche** e quindi su **Nuova ricerca.**

   ![Fare clic su Nuova ricerca per creare una ricerca eDiscovery di base](../media/CoreeDiscoverySearch1.png)

   > [!NOTE]
   > L’opzione **Cerca per elenco ID** consente di cercare messaggi di posta elettronica specifici e altri elementi della cassetta postale tramite un elenco di ID di Exchange. Per creare un elenco ID di ricerca, è necessario inviare un file con valori delimitati da virgole (CSV) che identifica gli elementi della cassetta postale specifici da cercare. Per istruzioni, vedere [Preparare un file CSV per un elenco ID di ricerca](csv-file-for-an-id-list-content-search.md).

5. Nella procedura **guidata Nuova ricerca** digitare un nome per la ricerca e una descrizione facoltativa che consente di identificare la ricerca. Il nome della ricerca deve essere univoco nell'organizzazione.

6. Nella pagina **Posizioni** scegliere le posizioni di contenuto in cui eseguire la ricerca. È possibile cercare cassette postali, siti e cartelle pubbliche.

    ![Scegliere le posizioni dei contenuti da mettere in attesa](../media/ContentSearchLocations.png)
  
   1. **Cassette postali di Exchange**: impostare l'interruttore su **Attivato** e quindi fare clic su **Scegliere utenti, gruppi o team** per specificare le cassette postali da mettere in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione da mettere in attesa (per mettere in attesa le cassette postali dei membri del gruppo). È anche possibile eseguire ricerche nella cassetta postale associata a un team di Microsoft Team (per i messaggi di canale), al gruppo di Office 365 e al gruppo di Yammer. Per altre informazioni sui dati dell'applicazione archiviati nelle cassette postali, vedere [contenuto archiviato nelle cassette postali per eDiscovery](what-is-stored-in-exo-mailbox.md).

   2. **Siti di SharePoint**: impostare l'interruttore su **Attivato** quindi fare clic su **Scegli siti** per specificare i siti di SharePoint e gli account di OneDrive da mettere in blocco. Digitare l'URL per ogni sito che si desidera mettere in blocco. È anche possibile aggiungere l'URL del sito di SharePoint per un team di Microsoft Team, un gruppo di Office 365 o un gruppo di Yammer.
  
   3. **Cartelle pubbliche di Exchange**: impostare l'interruttore su **attivato** per mettere in stato di blocco tutte le cartelle pubbliche nell'organizzazione di Exchange Online. Non è possibile scegliere cartelle pubbliche specifiche da mettere in blocco. Lasciare l'interruttore disattivato se non si vuole impostare un blocco sulle cartelle pubbliche.
  
   4. Mantenere selezionata questa casella di controllo per cercare contenuto di Teams per gli utenti locali. Ad esempio, se si esegue una ricerca in tutte le cassette postali di Exchange nell'organizzazione e si seleziona questa casella di controllo, la risorsa di archiviazione basata sul cloud usata per archiviare i dati chat di Teams per gli utenti locali verrà inclusa nell'ambito della ricerca. Per altre informazioni, vedere [Cercare i dati delle chat di Teams degli utenti locali](search-cloud-based-mailboxes-for-on-premises-users.md).

7. Nella pagina **Definisci le tue condizioni di ricerca** digitare una query con parole chiave e, se necessario, aggiungere condizioni alla query di ricerca.

   ![Configurare la query di ricerca](../media/ContentSearchQuery.png)

   1. È possibile specificare parole chiave, proprietà dei messaggi come le date di invio o ricezione o proprietà dei documenti come il nome file o la data dell'ultima modifica apportata. È anche possibile usare query più complesse che usano un operatore booleano, come ad esempio **AND**, **OR**, **NOT** o **NEAR**. Se si lascia vuota la casella delle parole chiave, nei risultati della ricerca verrà incluso tutto il contenuto disponibile nelle posizioni specificate. Per altre informazioni, vedere [Query con parola chiave e condizioni di ricerca per eDiscovery](keyword-queries-and-search-conditions.md).

   2. È anche possibile fare clic sulla casella di controllo **Mostra elenco di parole chiave** e digitare una parola chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono collegate da un operatore logico (**c:s**) con funzionalità simili all’operatore **OR** nella query di ricerca creata.

      Perché usare l'elenco di parole chiave? È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave. Questo è utile per identificare rapidamente le parole chiave più e meno efficaci. È possibile usare anche una frase chiave, racchiusa tra parentesi, in una riga. Per altre informazioni sulla lista delle parole chiave e sulle statistiche di ricerca, vedere [Visualizzare statistiche delle parole chiave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Per ridurre i problemi causati dai grandi elenchi di parole chiave, è consentito un massimo di 20 righe nell'elenco di parole chiave.

   3. È possibile aggiungere delle condizioni di ricerca per circoscrivere una ricerca e ottenere un insieme di risultati più preciso. Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca. Una condizione è collegata logicamente alla query con parole chiave, specificata nell'apposita casella, dall'operatore logico (**c:c**) che ha funzionalità simili all’operatore **AND**. Ciò significa che, per essere inclusi nei risultati, gli elementi devono soddisfare sia la query con parola chiave, sia una o più condizioni. Ecco in che modo le condizioni aiutano a limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile usare in una query di ricerca, vedere [Condizioni di ricerca](keyword-queries-and-search-conditions.md#search-conditions).

8. Esaminare le impostazioni di ricerca (e modificarle se necessario) e quindi inviare la ricerca per avviarla.

Una volta completata la ricerca, è possibile visualizzare in anteprima i risultati della ricerca. Se necessario, fare **clic su** Aggiorna nella **pagina Ricerche** per visualizzare la ricerca creata.

## <a name="more-information-about-searching-content-locations"></a>Ulteriori informazioni sulla ricerca di percorsi di contenuto

- Quando si fa **clic su Scegli utenti, gruppi** o team per specificare le cassette postali in cui eseguire la ricerca, la selezione delle cassette postali visualizzata è vuota. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere destinatari all'elenco, fare clic su Scegli utenti, gruppi o **team,** digitare un nome (almeno tre caratteri) nella casella di ricerca, selezionare la casella di controllo accanto al nome e quindi fare clic su **Scegli**.

- È possibile aggiungere cassette postali inattive, Microsoft Teams, Yammer, Office 365 e gruppi di distribuzione all'elenco delle cassette postali in cui eseguire la ricerca. Non sono supportati i gruppi di distribuzione dinamici. Se si aggiungono Microsoft Teams, Yammer gruppi o Office 365 gruppo, viene ricercata la cassetta postale del gruppo o del team. le cassette postali dei membri del gruppo non vengono cercate.

- Per aggiungere siti alla ricerca, attivare l'interruttore e quindi fare clic **su Scegli siti.** Digitare l'URL di ogni sito in cui si desidera eseguire la ricerca. È inoltre possibile aggiungere l'URL per il sito SharePoint per un team Microsoft, un Yammer gruppo o un Office 365 gruppo.
