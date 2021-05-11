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
   > **L'opzione Cerca in base all'ID** consente di cercare messaggi di posta elettronica specifici e altri elementi della cassetta postale utilizzando un elenco Exchange ID. Per creare un elenco ID di ricerca, è necessario inviare un file con valori delimitati da virgole (CSV) che identifica gli elementi della cassetta postale specifici da cercare. Per istruzioni, vedere [Preparare un file CSV per un elenco ID di ricerca](csv-file-for-an-id-list-content-search.md).

5. Nella procedura **guidata Nuova ricerca** digitare un nome per la ricerca e una descrizione facoltativa che consente di identificare la ricerca. Il nome della ricerca deve essere univoco nell'organizzazione.

6. Nella pagina **Percorsi** scegliere i percorsi di contenuto in cui si desidera eseguire la ricerca. È possibile eseguire ricerche nelle cassette postali, nei siti e nelle cartelle pubbliche.

    ![Scegliere i percorsi dei contenuti da mettere in attesa](../media/ContentSearchLocations.png)
  
   1. **Exchange:** impostare l'interruttore su **Attivato** e quindi fare clic su **Scegli utenti,** gruppi o team per specificare le cassette postali da mettere in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione (per mettere un blocco sulle cassette postali dei membri del gruppo) da mettere in attesa. È inoltre possibile cercare nella cassetta postale associata a un team Microsoft (per i messaggi di canale), Office 365 gruppo e Yammer gruppo. Per ulteriori informazioni sui dati dell'applicazione archiviati nelle cassette postali, vedere [Content stored in mailboxes for eDiscovery](what-is-stored-in-exo-mailbox.md).

   2. **SharePoint siti:** impostare l'interruttore su  **Attivato** e quindi fare clic su Scegli siti per specificare SharePoint siti e OneDrive account da mettere in attesa. Digitare l'URL per ogni sito che si desidera conservare. È inoltre possibile aggiungere l'URL per il sito SharePoint per un team Microsoft, Office 365 gruppo o Yammer gruppo.
  
   3. **Exchange pubbliche**: impostare l'interruttore su **Attivato** per mettere in attesa tutte le cartelle pubbliche nell'Exchange Online organizzazione. Non è possibile scegliere cartelle pubbliche specifiche da mettere in attesa. Lasciare disattivata l'opzione di attivazione/disattivazione se non si desidera attivare un'esenzione per le cartelle pubbliche.
  
   4. Mantenere selezionata questa casella di controllo per cercare Teams contenuto per gli utenti locali. Ad esempio, se si ricercano tutte le cassette postali di Exchange nell'organizzazione e questa casella di controllo è selezionata, l'archiviazione basata su cloud utilizzata per archiviare i dati di chat di Teams per gli utenti locali verrà inclusa nell'ambito della ricerca. Per altre informazioni, vedere [Cercare i dati delle chat di Teams degli utenti locali](search-cloud-based-mailboxes-for-on-premises-users.md).

7. Nella pagina **Definire le condizioni di ricerca** digitare una query con parole chiave e aggiungere condizioni alla query di ricerca, se necessario.

   ![Configurare la query di ricerca](../media/ContentSearchQuery.png)

   1. Specificare le parole chiave, le proprietà dei messaggi, ad esempio le date di invio e ricezione, oppure le proprietà del documento, ad esempio i nomi di file o la data dell'ultima modifica di un documento. È anche possibile usare query più complesse che usano un operatore booleano, ad esempio **AND**, **OR**, **NOT** o **NEAR**. Se si lascia vuota la casella delle parole chiave, nei risultati della ricerca verrà incluso tutto il contenuto disponibile nelle posizioni specificate. Per ulteriori informazioni, vedere [Query con parole chiave e condizioni di ricerca per eDiscovery.](keyword-queries-and-search-conditions.md)

   2. È anche possibile fare clic sulla casella di controllo **Mostra elenco di parole chiave** e digitare una parola chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono collegate da un operatore logico (**c:s**) con funzionalità simili all’operatore **OR** nella query di ricerca creata.

      Perché usare l'elenco di parole chiave? È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave. Questo è utile per identificare rapidamente le parole chiave più e meno efficaci. È possibile usare anche una frase chiave, racchiusa tra parentesi, in una riga. Per ulteriori informazioni sull'elenco di parole chiave e sulle statistiche di ricerca, vedere [Get keyword statistics for searches.](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)

      > [!NOTE]
      > Per ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, l'elenco di parole chiave può essere limitato a un massimo di 20 righe.

   3. È possibile aggiungere condizioni di ricerca per restringere una ricerca e restituire un set di risultati più perfezionato. Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca. Una condizione è collegata logicamente alla query con parole chiave, specificata nell'apposita casella, dall'operatore logico (**c:c**) che ha funzionalità simili all’operatore **AND**. Ciò significa che, per essere inclusi nei risultati, gli elementi devono soddisfare sia la query con parola chiave, sia una o più condizioni. Ecco in che modo le condizioni aiutano a limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere [Condizioni di ricerca](keyword-queries-and-search-conditions.md#search-conditions).

8. Esaminare le impostazioni di ricerca (e modificarle se necessario), quindi inviare la ricerca per avviarla.

Una volta completata la ricerca, è possibile visualizzare in anteprima i risultati della ricerca. Se necessario, fare **clic su** Aggiorna nella **pagina Ricerche** per visualizzare la ricerca creata.

## <a name="more-information-about-searching-content-locations"></a>Ulteriori informazioni sulla ricerca di percorsi di contenuto

- Quando si fa **clic su Scegli utenti, gruppi** o team per specificare le cassette postali in cui eseguire la ricerca, la selezione delle cassette postali visualizzata è vuota. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere destinatari all'elenco, fare clic su Scegli utenti, gruppi o **team,** digitare un nome (almeno tre caratteri) nella casella di ricerca, selezionare la casella di controllo accanto al nome e quindi fare clic su **Scegli**.

- È possibile aggiungere cassette postali inattive, Microsoft Teams, Yammer, Office 365 e gruppi di distribuzione all'elenco delle cassette postali in cui eseguire la ricerca. Non sono supportati i gruppi di distribuzione dinamici. Se si aggiungono Microsoft Teams, Yammer gruppi o Office 365 gruppo, viene ricercata la cassetta postale del gruppo o del team. le cassette postali dei membri del gruppo non vengono cercate.

- Per aggiungere siti alla ricerca, attivare l'interruttore e quindi fare clic **su Scegli siti.** Digitare l'URL di ogni sito in cui si desidera eseguire la ricerca. È inoltre possibile aggiungere l'URL per il sito SharePoint per un team Microsoft, un Yammer gruppo o un Office 365 gruppo.
