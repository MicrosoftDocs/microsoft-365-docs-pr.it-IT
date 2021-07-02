---
title: Riferimento funzionalità per Ricerca contenuto
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
ms.custom:
- seo-marvel-apr2020
description: Questo articolo contiene informazioni di riferimento sullo strumento eDiscovery della Ricerca contenuto nel Centro conformità Microsoft 365 per scoprire i dettagli relativi alla Ricerca contenuto.
ms.openlocfilehash: c66ef036e7a44e64a4e4e99aec3c81da287590d0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227272"
---
# <a name="feature-reference-for-content-search"></a>Riferimento funzionalità per Ricerca contenuto

Questo articolo descrive funzionalità e funzioni di Ricerca contenuto.

## <a name="content-search-limits"></a>Limiti di Ricerca contenuto

Per una descrizione dei limiti applicati a Ricerca contenuto, vedere [Limiti per Ricerca contenuto](limits-for-content-search.md).

## <a name="building-a-search-query"></a>Creare una query di ricerca

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

- Durante l'esecuzione di una ricerca di contenuto, Microsoft 365 controlla automaticamente la query di ricerca per individuare caratteri non supportati e operatori booleani che potrebbero non essere scritti in maiuscolo. I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o la restituzione di risultati indesiderati. Per altre informazioni sui caratteri non supportati controllati, vedere [Verificare la presenza di errori nella query Ricerca contenuto](check-your-content-search-query-for-errors.md).

- Se si dispone di una query di ricerca che contiene parole chiave per i caratteri non italiani (come i caratteri cinesi), è possibile fare clic su **Lingua - paese/area geografica della query**![Icona Lingua - paese/area geografica della query Ricerca contenuto](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selezionare un valore di codice per la lingua - paese per la ricerca. La lingua/area geografica predefinita è neutrale. Come è possibile stabilire se è necessario cambiare l'impostazione della lingua per una ricerca contenuto? Se si è certi che i percorsi di contenuto contengano i caratteri non italiani che si stanno cercando, ma la ricerca non restituisce risultati, l'impostazione della lingua potrebbe essere la causa.

## <a name="partially-indexed-items"></a>Elementi parzialmente indicizzati

- Gli elementi parzialmente indicizzati nelle cassette postali sono inclusi nei risultati della ricerca stimati. Gli elementi parzialmente indicizzati di SharePoint e OneDrive non vengono inclusi nei risultati della ricerca stimati. Per altre informazioni, vedere [Elementi parzialmente indicizzati in eDiscovery](partially-indexed-items-in-content-search.md).

## <a name="searching-onedrive-accounts"></a>Eseguire una ricerca negli account di OneDrive

- Per ottenere un elenco degli URL dei siti di OneDrive nell'organizzazione, vedere [Creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](/onedrive/list-onedrive-urls). Lo script in questo articolo crea un file di testo che contiene un elenco di tutti i siti di OneDrive. Per eseguire questo script, è necessario installare e usare SharePoint Online Management Shell. Assicurarsi di aggiungere l'URL del dominio MySite dell'organizzazione a ogni sito OneDrive che si desidera includere nella ricerca. Si tratta del dominio che contiene tutti i siti di OneDrive, ad esempio, `https://contoso-my.sharepoint.com`. Di seguito viene riportato un esempio di sito OneDrive di un utente: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

    Nei rari casi in cui il nome dell'entità utente (UPN) di una persona viene modificato, l'URL per il relativo percorso OneDrive viene modificato in modo da incorporare il nuovo UPN. Se ciò si verifica, è necessario modificare la ricerca contenuto aggiungendo il nuovo URL di OneDrive dell'utente e rimuovendo quello precedente. Per altre informazioni, vedere [Come le modifiche UPN influiscono sull'URL di OneDrive](/onedrive/upn-changes).

## <a name="searching-microsoft-teams-and-microsoft-365-groups"></a>Eseguire una ricerca nei Gruppi di Microsoft 365 e Microsoft Teams

È anche possibile eseguire una ricerca nella cassetta postale associata a un team di Microsoft Teams o a un gruppo di Microsoft 365. Poiché Microsoft Teams è basato su Gruppi di Microsoft 365, la ricerca è simile. In entrambi i casi, la ricerca viene eseguita solo nella cassetta postale del gruppo o del team. La ricerca non verrà eseguita nelle cassette postali dei membri del gruppo o del team. Per cercare in queste cassette postali, è necessario aggiungerle specificamente alla ricerca.

Tenere presente quanto segue quando si cerca contenuto in Microsoft Teams e nei Gruppi di Microsoft 365.

- Per cercare contenuti in Teams e nei Gruppi di Microsoft 365, è necessario specificare la cassetta postale e il sito di SharePoint associati a un gruppo o a un team.

- Il contenuto dei canali privati è archiviato nella cassetta postale di ogni utente, non nella cassetta postale del team. Per cercare contenuto nei canali privati, vedere [eDiscovery di canali privati](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels).

- Eseguire il cmdlet **Get-UnifiedGroup** in Exchange Online per visualizzare le proprietà di un team o di un gruppo di Microsoft 365. È un buon modo per ottenere l'URL del sito associato a un team o a un gruppo. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Microsoft 365 denominato Senior Leadership Team:

  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroup**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

- Quando viene eseguita la ricerca in una cassetta postale dell'utente, qualsiasi team o gruppo di Microsoft 365 di cui fa parte l'utente viene escluso dalla ricerca. Analogamente, quando si esegue una ricerca in un team o in un gruppo di Microsoft 365, la ricerca viene eseguita solo nella cassetta postale e nel sito del gruppo specificati. La ricerca non viene effettuata nelle cassette postali e negli account di OneDrive for Business dei membri del gruppo, a meno che non li si aggiunga esplicitamente alla ricerca.

- Per ottenere un elenco dei membri di un gruppo di Microsoft 365 o di un team, è possibile visualizzare le proprietà nella pagina **Home \>Gruppi** nell'interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
  ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

- Le conversazioni che fanno parte di un canale di Teams vengono archiviate nella cassetta postale associata al team. Allo stesso modo, i file che i membri del team condividono in un canale vengono archiviati nel sito di SharePoint del team. È quindi necessario aggiungere la cassetta postale del team e il sito di SharePoint come percorso di contenuto per cercare le conversazioni e i file in un canale.

- In alternativa, le conversazioni che fanno parte dell'elenco di chat in Teams vengono archiviate nella cassetta postale di Exchange Online degli utenti che partecipano alla chat, mentre i file che un utente condivide nelle conversazioni via chat vengono archiviati nell’account di OneDrive for Business dell'utente stesso. È quindi necessario aggiungere le singole cassette postali utente e gli account di OneDrive for Business come percorsi di contenuto per cercare le conversazioni e i file nell'elenco di chat.

    > [!NOTE]
    > In una distribuzione ibrida di Exchange, gli utenti con una cassetta postale locale potrebbero partecipare a conversazioni che fanno parte dell'elenco di chat in Teams. In questo caso, anche il contenuto di queste conversazioni è disponibile per la ricerca, perché viene salvato in un'area di archiviazione basata sul cloud, chiamata *cassetta postale basata sul cloud per gli utenti locali*, per gli utenti che dispongono di una cassetta postale locale. Per altre informazioni, vedere [Cercare i dati delle chat di Teams degli utenti locali](search-cloud-based-mailboxes-for-on-premises-users.md).

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

   Per altre informazioni, vedere [Microsoft Teams lancia eDiscovery per chiamate e riunioni](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947).

- Il contenuto della scheda generato dalle app nei canali di Teams, nelle chat tra due persone e nelle chat 1xN viene archiviato nelle cassette postali e può fare l’oggetto di una ricerca. Una *scheda* è un contenitore di interfaccia utente per piccole parti di contenuto. Le schede possono avere più proprietà e allegati e possono includere pulsanti per attivare azioni della scheda. Per altre informazioni, vedere [Schede](/microsoftteams/platform/task-modules-and-cards/what-are-cards).

  Come nel caso di altri contenuti di Teams, il luogo di archiviazione del contenuto delle schede dipende da dove è stata usata la scheda. Il contenuto delle schede usate in un canale di Teams viene archiviato nella cassetta postale di gruppo di Teams. Il contenuto delle schede per chat tra due persone e 1xN viene archiviato nelle cassette postali dei partecipanti alla chat.

  Per cercare contenuti delle schede, è possibile usare le condizioni di ricerca `kind:microsoftteams` o `itemclass:IPM.SkypeTeams.Message`. Quando si esaminano i risultati della ricerca, la proprietà di posta elettronica **Mittente/Autore** del contenuto della scheda generato da bot in un canale di Teams è `<appname>@teams.microsoft.com`, dove `appname` è il nome dell’app che ha generato il contenuto della scheda. Se il contenuto della scheda è stato generato da un utente, il valore di **Mittente/Autore** identifica l'utente.

  Quando si visualizza il contenuto della scheda nei risultati della Ricerca contenuto, questo appare come allegato al messaggio. L’allegato è denominato `appname.html`, dove `appname` è il nome dell’app che ha generato il contenuto della scheda. Gli screenshot seguenti mostrano come viene visualizzato il contenuto della scheda (per un’app chiamata Asana) in Teams e nei risultati di una ricerca.

  **Contenuto della scheda in Teams**

  ![Contenuto della scheda in un messaggio di canale di Teams](../media/CardContentTeams.png)

  **Contenuto della scheda nei risultati della ricerca**

  ![Lo stesso contenuto della scheda nei risultati di una Ricerca contenuto](../media/CardContentEdiscoverySearchResults.png)

  > [!NOTE]
  > Per visualizzare immagini del contenuto della scheda nei risultati della ricerca a questo punto (ad esempio i segni di spunta nella schermata precedente), è necessario essere connessi a Teams (in https://teams.microsoft.com) in una scheda diversa all’interno della stessa sessione del browser utilizzata per visualizzare i risultati della ricerca. In caso contrario, verranno visualizzati dei segnaposti per le immagini.

- È possibile usare la proprietà di posta elettronica **Tipologia** o la condizione di ricerca **Tipo di messaggio** per la ricerca specifica di contenuto in Teams.

  - Per usare la proprietà **Tipologia** come parte della query di ricerca con parole chiave, nella casella **Parole chiave** di una query di ricerca, digitare `kind:microsoftteams`.

    ![Usare kind:microsoftteams nella casella delle parole chiave](../media/O365-ContentSearch-Teams-Keywords.png)

  - Per usare una condizione di ricerca, aggiungere la condizione **Tipo di messaggio** e usare il valore `microsoftteams`.

    ![Utilizzare la condizione Tipo di messaggio con il valore microsoftteams.](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

   Le condizioni sono connesse logicamente alla query con parole chiave dall'operatore **AND**. Ciò significa che un elemento deve corrispondere sia alla query con parole chiave che alle condizioni di ricerca che devono essere restituite nei risultati della ricerca. Per altre informazioni, vedere la sezione Linee guida per l’uso di condizioni” in [Query con parole chiave e condizioni di ricerca per Ricerca contenuto](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions).

## <a name="searching-yammer-groups"></a>Eseguire una ricerca nei gruppi di Yammer

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

## <a name="searching-inactive-mailboxes"></a>Eseguire una ricerca in una cassetta postale inattiva

È possibile eseguire ricerche nelle cassette postali inattive in una ricerca contenuto. Per ottenere un elenco delle cassette postali inattive nell'organizzazione, eseguire il comando `Get-Mailbox -InactiveMailboxOnly` in PowerShell di Exchange Online. In alternativa, è possibile passare a **Governance delle informazioni**\>**Conservazione** nel Centro sicurezza e conformità e quindi fare clic su **Altro**![Puntini di sospensione della barra di spostamento](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)\>**Cassette postali inattive**.

Ecco alcuni aspetti da tenere presenti quando si eseguono ricerche nelle cassette postali inattive.

- Se una ricerca di contenuto esistente include una cassetta postale dell'utente che viene resa inattiva, quando si esegue nuovamente la ricerca, questa continuerà a venire eseguita nella cassetta postale inattiva.

- A volte un utente potrebbe avere una cassetta postale attiva e una cassetta postale inattiva con lo stesso indirizzo SMTP. In questo caso, la ricerca verrà eseguita solo nella cassetta postale selezionata come percorso per una ricerca di contenuto. In altre parole, se si aggiunge una cassetta postale di un utente a una ricerca, non è possibile supporre che la ricerca venga eseguita sia nella cassetta postale attiva che in quella inattiva. La ricerca viene eseguita solo nella cassetta postale aggiunta esplicitamente alla ricerca.

- Per creare una ricerca contenuto per eseguire ricerche in una cassetta postale inattiva, è possibile usare PowerShell nel Centro sicurezza e conformità. A tal fine, è necessario pre-accodare un punto ( . ) all'indirizzo di posta elettronica della cassetta postale inattiva. Ad esempio, il comando seguente crea una ricerca di contenuto che esegue la ricerca in una cassetta postale inattiva con l'indirizzo di posta elettronica pavelb@contoso.onmicrosoft.com:

   ```powershell
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- È consigliabile evitare di avere una cassetta postale attiva e una cassetta postale inattiva con lo stesso indirizzo SMTP. Se è necessario riutilizzare l'indirizzo SMTP assegnato a una cassetta postale inattiva, è consigliabile ripristinare la cassetta postale inattiva o ripristinarne il contenuto in una cassetta postale attiva, o nell'archivio della cassetta postale attiva, quindi eliminare la cassetta postale inattiva. Per ulteriori informazioni, vedere uno degli argomenti seguenti:

  - [Recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md)

  - [Ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md)

  - [Eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md)

## <a name="searching-disconnected-or-de-licensed-mailboxes"></a>Eseguire una ricerca in cassette postali disconnesse o con licenza rimossa

Se la licenza di Exchange Online, o l'intera licenza di Microsoft 365, viene rimossa da un account utente o in Azure Active Directory, la cassetta postale dell'utente diventa una *cassetta postale disconnessa*. Ciò significa che la cassetta postale non è più associata all'account utente. Ecco cosa succede quando si eseguono ricerche nelle cassette postali disconnesse:

- Se la licenza viene rimossa da una cassetta postale, la cassetta postale non è più disponibile per la ricerca.

- Se una ricerca contenuto esistente include una cassetta postale in cui è stata rimossa la licenza, non verranno restituiti risultati della ricerca dalla cassetta postale disconnessa se si esegue di nuovo la ricerca contenuto.

- Se si usa il cmdlet **New-ComplianceSearch** per creare una ricerca contenuto e si specifica una cassetta postale disconnessa come percorso di contenuto di Exchange in cui eseguire la ricerca, la ricerca contenuto non restituirà risultati della ricerca dalla cassetta postale disconnessa.

Se è necessario conservare i dati in una cassetta postale disconnessa in modo che sia disponibile per la ricerca, è necessario applicare un blocco alla cassetta postale prima di rimuovere la licenza. In questo modo i dati vengono mantenuti e le cassette postali disconnesse sono disponibili per la ricerca finché non viene rimosso il blocco. Per altre informazioni sui blocchi, vedere [Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

## <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a>Ricerca di contenuto in un ambiente SharePoint Multi-Geo

Se un manager di eDiscovery deve cercare contenuto in aree diverse in SharePoint e OneDrive in un [ambiente SharePoint Multi-Geo](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md), è necessario eseguire le operazioni seguenti:

1. Creare un account utente distinto per ogni posizione geografica satellite i cui il manager di eDiscovery deve eseguire la ricerca. Per cercare contenuto in siti in tale posizione geografica, il manager di eDiscovery deve accedere all'account creato per la posizione e quindi eseguire una ricerca di contenuto.

2. Creare un filtro delle autorizzazioni di ricerca per ogni posizione geografica satellite (e l'account utente corrispondente) in cui il manager di eDiscovery deve eseguire la ricerca. Ognuno di questi filtri delle autorizzazioni di ricerca limita l'ambito della ricerca di contenuto a una specifica posizione geografica quando il manager di eDiscovery è connesso all'account utente associato a quella posizione.

> [!TIP]
> Quando si usa lo strumento di ricerca in [Advanced eDiscovery](overview-ediscovery-20.md), non è necessario usare questa strategia. Il motivo è che quando si esegue una ricerca in siti di SharePoint e account di OneDrive in Advanced eDiscovery, la ricerca viene eseguita in tutti i data center. È necessario usare questa strategia basata sugli account utente specifici dell'area geografica e sui filtri delle autorizzazioni di ricerca solo quando si usa lo strumento Ricerca contenuto e si eseguono ricerche associate a [casi di eDiscovery](./get-started-core-ediscovery.md).

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
