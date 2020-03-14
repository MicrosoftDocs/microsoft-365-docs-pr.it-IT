---
title: Ricerca contenuto in Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Usare lo strumento Ricerca contenuto nel centro conformità di Office 365 o Microsoft 365 per cercare contenuto in cassette postali, siti di SharePoint Online, account di OneDrive, Microsoft Teams, gruppi di Office 365, gruppi di Yammer e conversazioni di Skype for Business. È possibile usare query di ricerca con parole chiave e condizioni di ricerca per limitare i risultati della ricerca. È quindi possibile visualizzare in anteprima ed esportare i risultati della ricerca. La Ricerca contenuto è anche uno strumento efficace per cercare contenuto correlato a una richiesta dell’interessato GDPR.
ms.openlocfilehash: d9fdf5359538209d0793211632979fae1b332d13
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634444"
---
# <a name="content-search-in-office-365"></a>Ricerca contenuto in Office 365

È possibile usare lo strumento Ricerca contenuto di eDiscovery nel centro conformità di Office 365 o Microsoft 365 per cercare elementi sul posto, come messaggi di posta elettronica, documenti e conversazioni di messaggistica istantanea nell'organizzazione di Office 365. Usare questo strumento per cercare elementi in questi servizi di Office 365:
  
- Cassette postali e cartelle pubbliche in Exchange Online
    
- Siti di SharePoint Online e account di OneDrive for Business
    
- Conversazioni Skype for Business
    
- Microsoft Teams 

- Gruppi di Office 365

- Gruppi di Yammer 
    
Dopo aver eseguito una Ricerca contenuto, il numero di percorsi dei contenuti e il numero stimato dei risultati della ricerca vengono visualizzati nelle statistiche della ricerca. È anche possibile visualizzare rapidamente le statistiche, come i percorsi di contenuto che contengono la maggior parte degli elementi corrispondenti alla query di ricerca. Dopo l'esecuzione di una ricerca, è possibile visualizzare in anteprima i risultati o esportarli in un computer locale.

## <a name="create-a-search"></a>Creare una ricerca

Per potere accedere alla pagina **Ricerca contenuto**, eseguire ricerche contenuto e visualizzare l'anteprima dei risultati della ricerca, un amministratore, un responsabile della conformità o un responsabile di eDiscovery deve essere membro del gruppo di ruoli Responsabile di eDiscovery nel Centro sicurezza e conformità. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'indirizzo di posta elettronica e la password di Office 365.
    
2. Fare clic su **Ricerca**\>**Ricerca contenuto**.
    
3. Nella pagina **Ricerca** fare clic sulla freccia accanto a ![Icona Aggiungi](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Nuova ricerca**. 
    
    ![Elenco a discesa Nuova ricerca](../media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    È possibile scegliere una delle seguenti opzioni:
    
    - **Ricerca guidata:** questa opzione avvia una procedura guidata che consente di creare la ricerca. Le interfacce utente per selezionare i percorsi di contenuto e creare la query di ricerca sono identiche a quelle dell’opzione **Nuova ricerca**. 
    
    - **Nuova ricerca**: questa opzione visualizza un'interfaccia utente aggiornata per creare una ricerca. Questa è l'opzione predefinita se si fa clic su **Nuova ricerca**.
    
    - **Cerca per elenco ID**: questa opzione consente di cercare messaggi di posta elettronica specifici e altri elementi della cassetta postale tramite un elenco di ID di Exchange. Per creare una ricerca per elenco ID, anche chiamata una ricerca mirata, è necessario inviare un file con valori delimitati da virgole (CSV) che identifica gli elementi della cassetta postale specifici da cercare. Per istruzioni, vedere [Preparare un file CSV per un elenco ID di Ricerca contenuto in Office 365](csv-file-for-an-id-list-content-search.md).
    
    Il resto dei passaggi descritti in questa procedura segue il flusso di lavoro di nuova ricerca predefinito.
    
4. Fare clic su **Nuova ricerca** nell'elenco a discesa. 
    
5. In **Query di ricerca** specificare gli elementi seguenti:
    
    ![Specificare parole chiave, condizioni e posizioni in cui eseguire la ricerca](../media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - **Parole chiave da cercare**: digitare una query di ricerca nella casella **Parole chiave**. È possibile specificare parole chiave, proprietà dei messaggi come le date di invio o ricezione o proprietà dei documenti come il nome file o la data dell'ultima modifica apportata. È anche possibile usare query più complesse che usano un operatore booleano, ad esempio **AND**, **OR**, **NOT** o **NEAR**. È inoltre possibile cercare informazioni sensibili (ad esempio numeri di codice fiscale) nei documenti o cercare documenti condivisi esternamente. Se si lascia vuota la casella delle parole chiave, nei risultati della ricerca verrà incluso tutto il contenuto disponibile nelle posizioni specificate.
    
      È anche possibile fare clic sulla casella di controllo **Mostra elenco di parole chiave** e digitare una parola chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono collegate da un operatore logico (**c:s**) con funzionalità simili all’operatore **OR** nella query di ricerca creata. 
    
      Perché usare l'elenco di parole chiave? È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave. Questo è utile per identificare rapidamente le parole chiave più e meno efficaci. È possibile usare anche una frase chiave, racchiusa tra parentesi, in una riga. Per altre informazioni sulle statistiche di ricerca, vedere [Visualizzare statistiche delle parole chiave per i risultati di Ricerca contenuto](view-keyword-statistics-for-content-search.md).

     > [!NOTE]
     > Per ridurre i problemi causati dai grandi elenchi di parole chiave, è ora consentito un massimo di 20 righe nell'elenco di parole chiave.
    
    - **Condizioni**: è possibile aggiungere delle condizioni di ricerca per circoscrivere una ricerca e ottenere un insieme di risultati più preciso. Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca. Una condizione è collegata logicamente alla query con parole chiave, specificata nell'apposita casella, dall'operatore logico (**c:c**) che ha funzionalità simili all’operatore **AND**. Ciò significa che, per essere inclusi nei risultati, gli elementi devono soddisfare sia la query con parola chiave, sia una o più condizioni. Ecco in che modo le condizioni aiutano a limitare i risultati. Per un elenco e una descrizione delle condizioni che possono essere usate in una query di ricerca, vedere la sezione "Condizioni di ricerca" in [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md#search-conditions).
    
       - **Percorsi**: scegliere i percorsi di contenuti in cui eseguire la ricerca.
    
      - **Tutti i percorsi**: selezionare questa opzione per cercare in tutti i percorsi di contenuto dell'organizzazione. Ciò include i messaggi di posta elettronica in tutte le cassette postali di Exchange, incluse tutte le cassette postali inattive, le cassette postali per tutti i gruppi di Yammer, i gruppi di Office 365 e Microsoft Teams, tutte le conversazioni Skype for Business, tutti i siti di SharePoint e OneDrive for Business, inclusi i siti per tutti i gruppi di Yammer, i gruppi di Office 365 e Microsoft Teams, e gli elementi in tutte le cartelle pubbliche di Exchange.
    
      - **Percorsi specifici**: usare questa opzione per eseguire ricerche in percorsi di contenuto specifici. È possibile eseguire una ricerca in tutti i percorsi di contenuto per un servizio Office 365 specifico, ad esempio in tutte le cassette postali di Exchange o in tutti i siti di SharePoint, oppure eseguire una ricerca dei contenuti in percorsi specifici inclusi nei servizi di Office 365 visualizzati. 
    
        ![Interfaccia utente per scegliere i percorsi di contenuti in cui eseguire la ricerca](../media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         È inoltre possibile aggiungere gruppi di distribuzione all'elenco di cassette postali di Exchange in cui eseguire la ricerca. Per i gruppi di distribuzione, la ricerca viene eseguita nelle cassette postali dei membri del gruppo. Non sono supportati i gruppi di distribuzione dinamici.
    
       > [!NOTE]
       > Se si esegue una ricerca in tutti i percorsi di cassette postali o solo in cassette postali specifiche, i dati provenienti da altre applicazioni di Office 365 salvati nelle cassette postali degli utenti sono inclusi quando si esportano i risultati di una Ricerca contenuto. I dati non vengono inclusi nei risultati della ricerca stimati e non vengono visualizzati in anteprima. Vengono inclusi quando si esportano e si scaricano i risultati della ricerca. Per ulteriori informazioni, vedere [Contenuto archiviato nelle cassette postali di Exchange Online](what-is-stored-in-exo-mailbox.md).
   
6. Dopo aver configurato la query di ricerca, fare clic su **Salva ed esegui**.
    
7. Nella pagina **Salva ricerca** digitare il nome della ricerca e una descrizione facoltativa che consenta di identificare la ricerca. Il nome della ricerca deve essere univoco nell'organizzazione. 
    
8. Per avviare la ricerca, fare clic su **Salva**. 
    
    Dopo il salvataggio e l'esecuzione della ricerca, nel riquadro risultati verranno visualizzati tutti i risultati restituiti dalla ricerca. A seconda di come sono state configurate le impostazioni di anteprima, i risultati della ricerca vengono visualizzati oppure è necessario fare clic su **Anteprima risultati** per visualizzarli. Per informazioni dettagliate, vedere la sezione successiva. 
    
Per accedere nuovamente alla ricerca contenuto o accedere ad altre ricerche contenuto elencate nella pagina **Ricerca contenuto**, selezionare la ricerca e quindi fare clic su **Apri**. 
  
Per cancellare i risultati o creare un'altra ricerca, fare clic su ![Icona Aggiungi](../media/O365-MDM-CreatePolicy-AddIcon.gif) **Nuova ricerca**. 
  
## <a name="preview-search-results"></a>Visualizza in anteprima i risultati della ricerca

Sono disponibili due impostazioni di configurazione per l'anteprima dei risultati della ricerca. Dopo aver eseguito una nuova ricerca o aperto una ricerca esistente, fare clic su **Singoli risultati** per visualizzare le impostazioni di anteprima seguenti: 
  
![Impostazioni di visualizzazione dell'anteprima risultati della ricerca](../media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **Visualizzare l'anteprima risultati automaticamente**: questa opzione visualizza i risultati della ricerca dopo l'esecuzione di una ricerca.
    
2. **Visualizzare l'anteprima risultati manualmente**: questa impostazione visualizza i segnaposto nel riquadro dei risultati della ricerca e mostra il pulsante **Anteprima risultati** su cui è necessario fare clic per visualizzare i risultati della ricerca. Questa è l'impostazione predefinita. Consente di migliorare le prestazioni della ricerca evitando di visualizzare automaticamente i risultati della ricerca quando si apre una ricerca esistente. 
    
Sono previsti limiti per il numero di elementi che è possibile visualizzare in anteprima. Per ulteriori informazioni, vedere [Limiti per la Ricerca contenuto](limits-for-content-search.md). 
  
Per un elenco dei tipi di file supportati che è possibile visualizzare in anteprima, vedere [Visualizzare in anteprima i risultati della ricerca](#previewing-search-results) nella sezione "Altre informazioni sulla Ricerca contenuto". Se un tipo di file non è supportato per l'anteprima o per il download di una copia del documento, è possibile fare clic su **Scarica file originale** per scaricarlo nel computer locale. Nelle pagine Web ASPX l'URL della pagina è incluso, anche se l'utente potrebbe non avere le autorizzazioni per accedere alla pagina. 
  
Tenere inoltre presente che gli elementi non indicizzati non sono disponibili per la visualizzazione in anteprima.
  
## <a name="view-information-and-statistics-about-a-search"></a>Visualizzare informazioni e statistiche su una ricerca

Dopo aver creato ed eseguito una ricerca di contenuto, è possibile visualizzare statistiche relative ai risultati della ricerca stimati. Questo include un riepilogo dei risultati della ricerca, statistiche sulle query, ad esempio il numero di percorsi di contenuto con elementi che corrispondono alla query di ricerca, e il nome dei percorsi di contenuto che contengono più elementi corrispondenti. È possibile visualizzare statistiche per una o più ricerche di contenuto. In questo modo si possono confrontare rapidamente i risultati di più ricerche e prendere decisioni in merito all'efficacia delle query di ricerca.
  
È anche possibile scaricare le statistiche di ricerca e delle parole chiave in un file CSV. Questo consente di usare le funzionalità di filtro e ordinamento di Excel per confrontare i risultati e preparare report per i risultati della ricerca.
  
Per visualizzare le statistiche della ricerca:
  
1. Nella pagina **Ricerca contenuto** fare clic su **Apri** e quindi fare clic sulla ricerca di cui si vuole visualizzare la statistica. 
    
2. Nella pagina a comparsa fare clic su **Apri query**. 
    
3. Nell'elenco a discesa **Singoli risultati** fare clic su **Statistiche ricerca**.
    
4. Nell'elenco a discesa **Tipo** fare clic su una delle opzioni seguenti in base alle statistiche di ricerca che si vogliono visualizzare. 
    
  - **Riepilogo**: visualizza le statistiche per ogni tipo di percorso di contenuto cercato. Include il numero di percorsi di contenuto che contengono elementi che corrispondono alla query di ricerca e il numero totale e le dimensioni degli elementi dei risultati della ricerca. Questa è l'impostazione predefinita.
    
  - **Query**: questa pagina visualizza le statistiche sulla query di ricerca. Include il tipo di percorso di contenuto a cui si applicano le statistiche di query, la parte della query di ricerca a cui si applicano le statistiche (tenere presente che **Principale** indica l'intera query di ricerca), il numero dei percorsi di contenuto che contengono elementi che corrispondono alla query di ricerca e il numero totale e le dimensioni e gli elementi trovati (nel percorso di contenuto specificato) che corrispondono alla query di ricerca. Vengono visualizzate anche le statistiche relative agli elementi non indicizzati, detti anche *elementi parzialmente indicizzati*. Tuttavia, nelle statistiche sono inclusi solo gli elementi parzialmente indicizzati provenienti dalle cassette postali. Gli elementi parzialmente indicizzati di SharePoint e OneDrive non vengono inclusi nelle statistiche.
    
  - **Percorsi principali**: questa pagina visualizza le statistiche relative al numero di elementi corrispondenti alla query di ricerca presenti in ogni percorso di contenuto. Vengono visualizzati i primi 1.000 percorsi.
    
Per altre informazioni dettagliate sulle statistiche di ricerca, vedere [Visualizzare statistiche delle parole chiave per i risultati di Ricerca contenuto](view-keyword-statistics-for-content-search.md).
  
  
## <a name="export-search-results"></a>Esportare i risultati della ricerca

Dopo aver completato una ricerca, è possibile esportarne i risultati su un computer locale. Quando si esportano i risultati di posta elettronica, questi possono essere scaricati nel computer sotto forma di file PST o di singoli messaggi (file MSG). Quando si esportano contenuti dai siti di SharePoint e OneDrive, vengono esportate anche le copie dei documenti Office originali. Nei risultati di ricerca esportati sono presenti anche altri documenti e report. È inoltre possibile esportare il report dei risultati della ricerca e non gli elementi effettivi.
  
Per esportare i risultati della ricerca:
  
1. Nella pagina **Ricerca contenuto**, fare clic sulla ricerca per la quale si desidera esportare i risultati. 
    
2. Nella pagina a comparsa fare clic su ![Icona Esporta risultati ricerca](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**Altro** e quindi fare clic su **Esporta risultati**. Si può anche esportare un report dei risultati della ricerca.
    
3. Completare le sezioni nella pagina a comparsa **Esporta risultati**. Assicurarsi di usare la barra di scorrimento per visualizzare tutte le opzioni di esportazione. 
    
Per istruzioni più dettagliate e suggerimenti per la risoluzione dei problemi, vedere:
  
- [Esportare i risultati della Ricerca contenuto](export-search-results.md)
    
- [Esportare il rapporto della Ricerca contenuto](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a>Altre informazioni sulla Ricerca contenuto

Per ulteriori informazioni sulle ricerche di contenuto, vedere le sezioni seguenti.
  
[Limiti di Ricerca contenuto](#content-search-limits)
  
[Creare una query di ricerca](#building-a-search-query)
  
[Eseguire una ricerca negli account di OneDrive](#searching-onedrive-accounts)
  
[Eseguire una ricerca nei Gruppi di Office 365 e Microsoft Teams](#searching-microsoft-teams-and-office-365-groups)

[Eseguire una ricerca nei gruppi di Yammer](#searching-yammer-groups)
  
[Eseguire una ricerca in una cassetta postale inattiva](#searching-inactive-mailboxes)
  
[Eseguire una ricerca in cassette postali disconnesse o con licenza rimossa](#searching-disconnected-or-de-licensed-mailboxes)

[Visualizzare l'anteprima risultati della ricerca](#previewing-search-results)
  
[Elementi parzialmente indicizzati](#partially-indexed-items)

[Ricerca di contenuto in un ambiente SharePoint Multi-Geo](#searching-for-content-in-a-sharepoint-multi-geo-environment)
  
### <a name="content-search-limits"></a>Limiti di Ricerca contenuto

- Per una descrizione dei limiti applicati alla funzionalità di Ricerca contenuto, vedere [Limiti per la Ricerca contenuto](limits-for-content-search.md).
    
- Microsoft raccoglie informazioni sulle prestazioni per le ricerche contenuto eseguite da tutte le organizzazioni di Office 365. Sebbene la complessità della query di ricerca possa influire sui tempi di ricerca, il fattore principale che influisce sul tempo necessario per una ricerca è il numero di cassette postali in cui la ricerca viene eseguita. Sebbene Microsoft non fornisca un contratto di servizio per i tempi di ricerca, la tabella seguente elenca i tempi di ricerca medi per un'operazione di Ricerca contenuto in base al numero di cassette postali incluse nella ricerca.
    
|**Numero di cassette postali**|**Tempo medio di ricerca**|
|:-----|:-----|
|100  <br/> |30 secondi  <br/> |
|1.000  <br/> |45 secondi  <br/> |
|10.000  <br/> |4 minuti  <br/> |
|25.000  <br/> |10 minuti  <br/> |
|50.000  <br/> |20 minuti  <br/> |
|100.000  <br/> |25 minuti  <br/> |
  
### <a name="building-a-search-query"></a>Creare una query di ricerca

Per informazioni dettagliate sulla creazione di una query di ricerca, l'uso di operatori di ricerca booleani e di condizioni di ricerca e la ricerca di tipi di informazioni riservate e contenuti condivisi con utenti esterni all'organizzazione, vedere [Query con parole chiave e condizioni di ricerca per Ricerca contenuto](keyword-queries-and-search-conditions.md).
  
Tenere presente quanto segue quando si usa l'elenco di parole chiave per creare una query di ricerca.
  
- È necessario selezionare la casella di controllo **Mostra elenco di parole chiave** e digitare le singole parole chiave in righe separate per creare una query di ricerca in cui le parole o le frasi chiave di ogni riga siano collegate dall'operatore **OR**. Se si incolla un elenco di parole chiave nella casella delle parole chiave oppure si preme **INVIO** dopo aver digitato una parola chiave, l'operatore **OR** non eseguirà il collegamento. Ecco un esempio non valido e uno valido di come aggiungere un elenco di parole chiave. 
    
    **Non valido**
    
    ![Modo non valido per formattare un elenco di parole chiave (incollando l'elenco nella casella delle parole chiave)](../media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Valido**
    
    ![Modo valido per formattare un elenco di parole chiave (selezionando la casella di controllo e quindi incollando l'elenco)](../media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- È anche possibile preparare un elenco di parole o frasi chiave in un file di Excel o in un file di testo normale, quindi copiare e incollare l'elenco nell'elenco di parole chiave. A questo scopo, è necessario selezionare la casella di controllo **Mostra elenco di parole chiave**. Quindi, fare clic sulla prima riga dell'elenco di parole chiave e incollare l'elenco. Ogni riga del file di testo o di Excel verrà incollata in righe separate nell'elenco di parole chiave. 
    
- Dopo aver creato una query con l'elenco di parole chiave, è consigliabile verificare la sintassi della query di ricerca per verificare che la query di ricerca sia quella prevista. Nella query di ricerca visualizzata in **Query** nel riquadro dei dettagli, le parole chiave sono separate dal testo **(c:s)**. Questo indica che le parole chiave sono connesse da un operatore logico con funzionalità simili all'operatore **OR**. Analogamente, se la query di ricerca include condizioni, le parole chiave e le condizioni sono separate dal testo **(c:c)**. Questo indica che le parole chiave sono connesse alle condizioni da un operatore logico con funzionalità simili all'operatore **AND**. Ecco un esempio della query di ricerca, visualizzata nel riquadro dei dettagli, restituita quando si usa l'elenco di parole chiave e una condizione. 
    
    ![Esempio della query creata quando si usa l'elenco di parole chiave e una condizione](../media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- Durante l'esecuzione di una ricerca di contenuto, Office 365 controlla automaticamente la query di ricerca per individuare caratteri non supportati e operatori booleani che potrebbero non essere scritti in maiuscolo. I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o la restituzione di risultati indesiderati. Per altre informazioni sui caratteri non supportati controllati, vedere [Verificare la presenza di errori nella query Ricerca contenuto](check-your-content-search-query-for-errors.md).
    
- Se si dispone di una query di ricerca che contiene parole chiave per i caratteri non italiani (come i caratteri cinesi), è possibile fare clic su **Lingua - paese/area geografica della query**![Icona Lingua - paese/area geografica della query Ricerca contenuto](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selezionare un valore di codice per la lingua - paese per la ricerca. La lingua/area geografica predefinita è neutrale. Come è possibile stabilire se è necessario cambiare l'impostazione della lingua per una ricerca contenuto? Se si è certi che i percorsi di contenuto contengano i caratteri non italiani che si stanno cercando, ma la ricerca non restituisce risultati, l'impostazione della lingua potrebbe essere la causa. 
  
### <a name="searching-onedrive-accounts"></a>Eseguire una ricerca negli account di OneDrive

- Per ottenere un elenco degli URL dei siti di OneDrive nell'organizzazione, vedere [Creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Lo script in questo articolo crea un file di testo che contiene un elenco di tutti i siti di OneDrive. Per eseguire questo script, è necessario installare e usare SharePoint Online Management Shell. Assicurarsi di aggiungere l'URL del dominio MySite dell'organizzazione a ogni sito OneDrive che si desidera includere nella ricerca. Si tratta del dominio che contiene tutti i siti di OneDrive, ad esempio, `https://contoso-my.sharepoint.com`. Di seguito viene riportato un esempio di sito OneDrive di un utente: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    
    Nei rari casi in cui il nome dell'entità utente (UPN) di una persona viene modificato, l'URL per il relativo percorso OneDrive viene modificato in modo da incorporare il nuovo UPN. Se ciò si verifica, è necessario modificare la ricerca contenuto aggiungendo il nuovo URL di OneDrive dell'utente e rimuovendo quello precedente.
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>Eseguire una ricerca nei Gruppi di Office 365 e Microsoft Teams

È anche possibile eseguire una ricerca nella cassetta postale associata a un gruppo di Office 365 o a Microsoft Teams. Poiché Microsoft Teams è basato su Gruppi di Office 365, la ricerca è simile. In entrambi i casi, la ricerca viene eseguita solo nella cassetta postale del gruppo o del team. La ricerca non verrà eseguita nelle cassette postali dei membri del gruppo o del team. Per cercare in queste cassette postali, è necessario aggiungerle specificamente alla ricerca.
  
Tenere presente quanto segue quando si cerca contenuto in Microsoft Teams e nei Gruppi di Office 365.
  
- Per cercare contenuti in Teams e nei Gruppi di Office 365, è necessario specificare la cassetta postale e il sito di SharePoint associati a un gruppo o a un team.
    
- Eseguire il cmdlet **Get-UnifiedGroup** in Exchange Online per visualizzare le proprietà di un team o di un gruppo di Office 365. È un buon modo per ottenere l'URL del sito associato a un gruppo o a un team. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Office 365 denominato Senior Leadership Team: 
    
  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroup**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura. 
  
- Quando viene eseguita la ricerca in una cassetta postale dell'utente, qualsiasi team o gruppo di Office 365 di cui fa parte l'utente viene escluso dalla ricerca. Analogamente, quando si esegue una ricerca in un team o in un gruppo di Office 365, la ricerca viene eseguita solo nella cassetta postale e nel sito del gruppo specificati. La ricerca non viene effettuata nelle cassette postali e negli account di OneDrive for Business dei membri del gruppo, a meno che non li si aggiunga esplicitamente alla ricerca.
    
- Per ottenere un elenco dei membri di un gruppo di Office 365 o di un team, è possibile visualizzare le proprietà nella pagina **Home \>Gruppi** nell’interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile eseguire il comando seguente in PowerShell di Exchange Online: 
    
  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura. 
  
- Le conversazioni che fanno parte di un canale di Teams vengono archiviate nella cassetta postale associata al team. Allo stesso modo, i file che i membri del team condividono in un canale vengono archiviati nel sito di SharePoint del team. È quindi necessario aggiungere la cassetta postale del team e il sito di SharePoint come percorso di contenuto per cercare le conversazioni e i file in un canale.
    
- In alternativa, le conversazioni che fanno parte dell'elenco di chat in Teams vengono archiviate nella cassetta postale di Exchange Online degli utenti che partecipano alla chat, mentre i file che un utente condivide nelle conversazioni via chat vengono archiviati nell’account di OneDrive for Business dell'utente stesso. È quindi necessario aggiungere le singole cassette postali utente e gli account di OneDrive for Business come percorsi di contenuto per cercare le conversazioni e i file nell'elenco di chat.
    
    > [!NOTE]
    > In una distribuzione ibrida di Exchange, gli utenti con una cassetta postale locale potrebbero partecipare a conversazioni che fanno parte dell'elenco di chat in Teams. In questo caso, anche il contenuto di queste conversazioni è disponibile per la ricerca, perché viene salvato in un'area di archiviazione basata sul cloud, chiamata *cassetta postale basata sul cloud per gli utenti locali*, per gli utenti che dispongono di una cassetta postale locale. Per altre informazioni, vedere [Ricerca in cassette postali basate sul cloud per gli utenti locali in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).
  
- Ogni team o canale del team contiene un Wiki per la creazione di note e la collaborazione. Il contenuto Wiki viene salvato automaticamente in un file con formato MHT. Il file è archiviato nella raccolta documenti di dati Wiki di Teams nel sito di SharePoint del team. È possibile usare lo strumento Ricerca contenuto per eseguire ricerche nel Wiki specificando il sito di SharePoint del team come percorso di contenuto in cui eseguire la ricerca. 
    
    > [!NOTE]
    > La possibilità di eseguire ricerche nel Wiki di un team o di un canale, quando si esegue una ricerca nel sito di SharePoint del team, è stata rilasciata il 22 giugno 2017. Le pagine Wiki salvate o aggiornate in tale data o in seguito sono disponibili per la ricerca. Le pagine Wiki salvate o aggiornate prima di questa data non sono disponibili per la ricerca. 
 
- Anche le informazioni di riepilogo per le riunioni e le chiamate in un canale di Teams vengono archiviate nelle cassette postali degli utenti che hanno partecipato alla riunione o alla chiamata. Ciò significa che è possibile usare Ricerca contenuto per eseguire ricerche nei record di riepilogo. Tali informazioni di riepilogo includono: 
  
  - Data, ora di inizio, ora di fine e durata di una riunione o una chiamata

  - La data e l'ora in cui ogni partecipante si è unito a o ha lasciato la riunione o la chiamata

  - Chiamate inviate alla casella vocale

  - Chiamate senza risposta o perse

  - Trasferimenti di chiamate, rappresentati come due chiamate separate

  Possono essere necessarie fino a 8 ore di tempo prima che la ricerca nei record di riepilogo di riunioni e chiamate sia disponibile.

  Nei risultati della ricerca, i riepiloghi delle riunioni vengono identificati come **Riunione** nel **campo Tipo** e i riepiloghi delle chiamate vengono identificati come **Chiamata**. Inoltre, le conversazioni che fanno parte di un canale di Teams e le chat di 1xN vengono identificate come **Messaggistica istantanea** nel campo **Tipo**.
  
  ![Le riunioni di Teams, le chiamate e le chat di 1xN sono identificate nel campo Tipo](../media/O365-ContentSearch-Teams-MessageKind.png)

- È possibile usare la proprietà di posta elettronica **Tipologia** o la condizione di ricerca **Tipo di messaggio** per la ricerca specifica di contenuto in Teams. 
  
  - Per usare la proprietà **Tipologia** come parte della query di ricerca con parole chiave, nella casella **Parole chiave** di una query di ricerca, digitare `kind:microsoftteams`.

    ![Usare kind:microsoftteams nella casella delle parole chiave](../media/O365-ContentSearch-Teams-Keywords.png)
  
  - Per usare una condizione di ricerca, aggiungere la condizione **Tipo di messaggio** e usare il valore `microsoftteams`. 

    ![Utilizzare la condizione Tipo di messaggio con il valore microsoftteams.](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

Le condizioni sono connesse logicamente alla query con parole chiave dall'operatore **AND**. Ciò significa che un elemento deve corrispondere sia alla query con parole chiave che alle condizioni di ricerca che devono essere restituite nei risultati della ricerca. Per altre informazioni, vedere la sezione Linee guida per l’uso di condizioni” in [Query con parole chiave e condizioni di ricerca per Ricerca contenuto](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions).
  
### <a name="searching-yammer-groups"></a>Eseguire una ricerca nei gruppi di Yammer

È possibile usare la proprietà di posta elettronica **ItemClass** o la condizione di ricerca **Tipo** per la ricerca specifica di elementi della conversazione nei gruppi di Yammer.

  - Per usare la proprietà **ItemClass** come parte della query di ricerca con parole chiave, nella casella **Parole chiave** di una query di ricerca, digitare una o tutte le seguenti coppie property:value:

     - ItemClass:IPM.Yammer.message
     - ItemClass:IPM.Yammer.poll
     - ItemClass:IPM.Yammer.praise
     - ItemClass:IPM.Yammer.question
  
    È ad esempio possibile usare la query di ricerca seguente per ottenere messaggi e complimenti di Yammer:

    ![Usare la proprietà ItemClass per cercare elementi di Yammer](../media/YammerContentSearch1.png)
  
  - In alternativa, è possibile usare la condizione di posta elettronica **Tipo** e selezionare **Messaggi di Yammer** per ottenere elementi di Yammer. Ad esempio, la query di ricerca seguente restituirà tutti gli elementi della conversazione di Yammer che contengono la parola chiave "riservato". 

    ![Usare la scheda condizione Tipo per cercare elementi della conversazione di Yammer](../media/YammerContentSearch2.png)

### <a name="searching-inactive-mailboxes"></a>Eseguire una ricerca in una cassetta postale inattiva

È possibile eseguire ricerche nelle cassette postali inattive in una ricerca contenuto. Per ottenere un elenco delle cassette postali inattive nell'organizzazione, eseguire il comando `Get-Mailbox -InactiveMailboxOnly` in PowerShell di Exchange Online. In alternativa, è possibile passare a **Governance delle informazioni**\>**Conservazione** nel Centro sicurezza e conformità e quindi fare clic su **Altro**![Puntini di sospensione della barra di spostamento](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)\>**Cassette postali inattive**.
  
Ecco alcuni aspetti da tenere presenti quando si eseguono ricerche nelle cassette postali inattive.

- Se una ricerca di contenuto esistente include una cassetta postale dell'utente che viene resa inattiva, quando si esegue nuovamente la ricerca, questa continuerà a venire eseguita nella cassetta postale inattiva.
    
- A volte un utente potrebbe avere una cassetta postale attiva e una cassetta postale inattiva con lo stesso indirizzo SMTP. In questo caso, la ricerca verrà eseguita solo nella cassetta postale selezionata come percorso per una ricerca di contenuto. In altre parole, se si aggiunge una cassetta postale di un utente a una ricerca, non è possibile supporre che la ricerca venga eseguita sia nella cassetta postale attiva che in quella inattiva. La ricerca viene eseguita solo nella cassetta postale aggiunta esplicitamente alla ricerca.
    
- Per creare una ricerca contenuto per eseguire ricerche in una cassetta postale inattiva, è possibile usare PowerShell nel Centro sicurezza e conformità. A tal fine, è necessario pre-accodare un punto ( . ) all'indirizzo di posta elettronica della cassetta postale inattiva. Ad esempio, il comando seguente crea una ricerca di contenuto che esegue la ricerca in una cassetta postale inattiva con l'indirizzo di posta elettronica pavelb@contoso.onmicrosoft.com:

   ``` 
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- È consigliabile evitare di avere una cassetta postale attiva e una cassetta postale inattiva con lo stesso indirizzo SMTP. Se è necessario riutilizzare l'indirizzo SMTP assegnato a una cassetta postale inattiva, è consigliabile ripristinare la cassetta postale inattiva o ripristinarne il contenuto in una cassetta postale attiva, o nell'archivio della cassetta postale attiva, quindi eliminare la cassetta postale inattiva. Per ulteriori informazioni, vedere uno degli argomenti seguenti:
    
  - [Recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md)
    
  - [Ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md)
    
  - [Eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md)

### <a name="searching-disconnected-or-de-licensed-mailboxes"></a>Eseguire una ricerca in cassette postali disconnesse o con licenza rimossa

Se la licenza di Exchange Online, o l'intera licenza di Office 365, viene rimossa da un account utente di Office 365 o di Azure Active Directory, la cassetta postale dell'utente diventa una *cassetta postale disconnessa*. Ciò significa che la cassetta postale non è più associata all'account utente. Ecco cosa succede quando si eseguono ricerche nelle cassette postali disconnesse:

- Se la licenza viene rimossa da una cassetta postale, la cassetta postale non è più disponibile per la ricerca. 

- Se una ricerca contenuto esistente include una cassetta postale in cui è stata rimossa la licenza, non verranno restituiti risultati della ricerca dalla cassetta postale disconnessa se si esegue di nuovo la ricerca contenuto.

- Se si usa il cmdlet **New-ComplianceSearch** per creare una ricerca contenuto e si specifica una cassetta postale disconnessa come percorso di contenuto di Exchange in cui eseguire la ricerca, la ricerca contenuto non restituirà risultati della ricerca dalla cassetta postale disconnessa.

Se è necessario conservare i dati in una cassetta postale disconnessa in modo che sia disponibile per la ricerca, è necessario applicare un blocco alla cassetta postale prima di rimuovere la licenza. In questo modo i dati vengono mantenuti e le cassette postali disconnesse sono disponibili per la ricerca finché non viene rimosso il blocco. Per altre informazioni sui blocchi, vedere [Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

### <a name="previewing-search-results"></a>Visualizzare l'anteprima risultati della ricerca

È possibile visualizzare l'anteprima dei tipi di file supportati nel riquadro di anteprima. Se un tipo di file non è supportato, è necessario scaricare una copia del file nel computer locale per visualizzarlo. I tipi di file seguenti sono supportati e possono essere visualizzati in anteprima nel riquadro risultati della ricerca.
  
- .txt, .html, .mhtml
    
- .eml
    
- .doc, .docx, .docm
    
- .pptm, .pptx
    
- .pdf
    
Sono supportati anche i seguenti tipi di contenitori di file. È possibile visualizzare l'elenco di file nel contenitore nel riquadro di anteprima.
  
- .zip
    
- .gzip
    
### <a name="partially-indexed-items"></a>Elementi parzialmente indicizzati

- Come descritto in precedenza, gli elementi parzialmente indicizzati nelle cassette postali sono inclusi nei risultati della ricerca stimati. Gli elementi parzialmente indicizzati di SharePoint e OneDrive non vengono inclusi nei risultati della ricerca stimati. 
    
- Se un elemento parzialmente indicizzato corrisponde alla query di ricerca, perché altre proprietà del messaggio o del documento soddisfano i criteri di ricerca, non verrà incluso nel numero stimato di elementi non indicizzati. Se un elemento parzialmente indicizzato è escluso dai criteri di ricerca, non verrà incluso nel numero stimato di elementi non indicizzati. Per altre informazioni, vedere [Elementi parzialmente indicizzati in Ricerca contenuto in Office 365](partially-indexed-items-in-content-search.md).

### <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a>Ricerca di contenuto in un ambiente SharePoint Multi-Geo

Se un manager di eDiscovery deve cercare contenuto in aree diverse in SharePoint e OneDrive in un [ambiente SharePoint Multi-Geo](https://go.microsoft.com/fwlink/?linkid=860840), è necessario eseguire le operazioni seguenti:
   
1. Creare un account utente distinto per ogni posizione geografica satellite i cui il manager di eDiscovery deve eseguire la ricerca. Per cercare contenuto in siti in tale posizione geografica, il manager di eDiscovery deve accedere all'account creato per la posizione e quindi eseguire una ricerca di contenuto.

2. Creare un filtro delle autorizzazioni di ricerca per ogni posizione geografica satellite (e l'account utente corrispondente) in cui il manager di eDiscovery deve eseguire la ricerca. Ognuno di questi filtri delle autorizzazioni di ricerca limita l'ambito della ricerca di contenuto a una specifica posizione geografica quando il manager di eDiscovery è connesso all'account utente associato a quella posizione.
 
> [!TIP]
> Quando si usa lo strumento di ricerca in [Advanced eDiscovery](overview-ediscovery-20.md), non è necessario usare questa strategia. Il motivo è che quando si esegue una ricerca in siti di SharePoint e account di OneDrive in Advanced eDiscovery, la ricerca viene eseguita in tutti i data center. È necessario usare questa strategia basata sugli account utente specifici dell'area geografica e sui filtri delle autorizzazioni di ricerca solo quando si usa lo strumento Ricerca contenuto e si eseguono ricerche associate a [casi di eDiscovery](ediscovery-cases.md). 


Si supponga, ad esempio, che un manager di eDiscovery debba cercare contenuto di SharePoint e OneDrive in posizioni satellite del Nord America, dell’Europa e dell’Asia Pacifico. Il primo passaggio consiste nel creare tre account utente, uno per ogni posizione. Il passaggio successivo consiste nel creare tre filtri delle autorizzazioni di ricerca, uno per ogni posizione *e* account utente corrispondente. Ecco alcuni esempi dei tre filtri delle autorizzazioni di ricerca per questo scenario. In ognuno di questi esempi il parametro **Area** specifica la posizione del datacenter di SharePoint per quell'area geografica e il parametro **Utenti** specifica l'account utente corrispondente. 

**Nord America**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

**Europa**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

**Asia Pacifico**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

Tenere presente quanto segue quando si usano i filtri delle autorizzazioni di ricerca per cercare contenuto in ambienti Multi-Geo:

- Il parametro **Area** indirizza le ricerche alla posizione satellite specificata. Se un manager di eDiscovery esegue la ricerca solo in siti di SharePoint e OneDrive esterni all'area geografica specificata nel filtro delle autorizzazioni di ricerca, non viene restituito alcun risultato della ricerca. 

- Il parametro **Area** non controlla le ricerche nelle cassette postali di Exchange. Quando eseguono ricerche nelle cassette postali, la ricerca viene estesa a tutti i datacenter. 
    
Per altre informazioni sull'uso dei filtri delle autorizzazioni di ricerca in un ambiente Multi-Geo, vedere la sezione "Ricerca ed esportazione di contenuto in ambienti Multi-Geo" in [Impostare i limiti di conformità per le indagini eDiscovery](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).
