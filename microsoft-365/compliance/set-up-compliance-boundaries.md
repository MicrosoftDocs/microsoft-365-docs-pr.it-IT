---
title: Configurare i limiti di conformità per le indagini di eDiscovery
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Informazioni su come utilizzare i limiti di conformità per creare limiti logici che controllano le posizioni del contenuto degli utenti in cui un responsabile di eDiscovery può eseguire ricerche in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 23ff50b9cd0ab0178962f7be9f1cedfbd6a7a1f7
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022343"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Configurare i limiti di conformità per le indagini di eDiscovery

Le indicazioni in questo articolo possono essere applicate quando si utilizza Core eDiscovery o Advanced eDiscovery per gestire le indagini.

I limiti di conformità creano limiti logici all'interno di un'organizzazione che controllano le posizioni del contenuto degli utenti (ad esempio cassette postali, account OneDrive e siti SharePoint) in cui i responsabili di eDiscovery possono eseguire ricerche. Inoltre, i limiti di conformità controllano chi può accedere ai casi di eDiscovery utilizzati per gestire le indagini legali, umane o di altro tipo all'interno dell'organizzazione. La necessità di limiti di conformità è spesso necessaria per le società multinazionali che devono rispettare i consigli di amministrazione e le normative geografiche e per i governi, spesso suddivisi in agenzie diverse. In Microsoft 365, i limiti di conformità consentono di soddisfare questi requisiti quando si eseguono ricerche di contenuto e si gestiscono indagini con i casi di eDiscovery.
  
Usiamo l'esempio nella figura seguente per spiegare come funzionano i limiti di conformità.
  
![I limiti di conformità sono costituiti da filtri delle autorizzazioni di ricerca che controllano l'accesso alle agenzie e ai gruppi di ruoli di amministratore che controllano l'accesso ai casi di eDiscovery](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
In questo esempio, Contoso LTD è un'organizzazione costituita da due filiali, Fourth Coffee e Coho Winery. L'azienda richiede che i manager e gli investigatori di eDiscovery possano eseguire ricerche solo nelle cassette postali di Exchange, negli account OneDrive e nei siti SharePoint nell'agenzia. Inoltre, i responsabili e gli investigatori di eDiscovery possono visualizzare solo i casi di eDiscovery nell'agenzia e possono accedere solo ai casi di cui sono membri. Inoltre, in questo scenario, gli investigatori non possono mettere in attesa i percorsi di contenuto o esportare il contenuto da un caso. Ecco come i limiti di conformità soddisfano questi requisiti.
  
- La funzionalità di filtro delle autorizzazioni di ricerca in Ricerca contenuto controlla i percorsi di contenuto in cui i responsabili e gli investigatori di eDiscovery possono eseguire ricerche. Ciò significa che investigatori e manager di eDiscovery nell'agenza Fourth Coffee possono cercare solo i percorsi dei contenuti nella filiale Fourth Coffee. La stessa limitazione vale per la filiale di Coho Winery.

- [I gruppi di](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) ruoli forniscono le funzioni seguenti per i limiti di conformità:

  - Controllare chi può visualizzare i casi di eDiscovery nella Centro conformità Microsoft 365. Ciò significa che investigatori e manager di eDiscovery possono visualizzare solo i casi eDiscovery nella propria agenzia.

  - Controllare chi può assegnare membri a un caso di eDiscovery. Ciò significa che investigatori e manager di eDiscovery possono assegnare membri solo ai casi di cui loro stessi sono membri.

  - Controllare le attività correlate a eDiscovery che i membri possono eseguire aggiungendo o rimuovendo ruoli che assegnano autorizzazioni specifiche.

Ecco il processo per la configurazione dei limiti di conformità:
  
[Passaggio 1: identificare un attributo utente per definire le agenzie](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Passaggio 2: Creare un gruppo di ruoli per ogni agenzia](#step-2-create-a-role-group-for-each-agency)

[Passaggio 3: Creare un filtro delle autorizzazioni di ricerca per applicare il limite di conformità](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Passaggio 4: Creare un caso di eDiscovery per indagini intra-agency](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Prima di configurare i limiti di conformità

- Agli utenti deve essere assegnata una Exchange Online licenza. Per verificarlo, utilizzare il cmdlet [Get-User](/powershell/module/exchange/get-user) in Exchange Online PowerShell.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Passaggio 1: identificare un attributo utente per definire le agenzie

Il primo passaggio consiste nel scegliere un attributo da usare per definire le agenzie. Questo attributo viene utilizzato per creare il filtro delle autorizzazioni di ricerca che limita un responsabile di eDiscovery a cercare solo i percorsi di contenuto degli utenti a cui è assegnato un valore specifico per questo attributo. Si supponga ad esempio che Contoso decida di utilizzare **l'attributo Department.** Il valore di questo attributo per gli utenti della filiale Fourth Coffee sarebbe e il valore per gli utenti della filiale  `FourthCoffee`  Coho Winery sarebbe `CohoWinery` . Nel passaggio 3 questa coppia viene utilizzata, ad esempio  `attribute:value` *Department:FourthCoffee,* per limitare le posizioni di contenuto degli utenti in cui i responsabili di eDiscovery possono eseguire ricerche. 
  
Ecco alcuni esempi di attributi utente che puoi usare per i limiti di conformità:
  
- Company

- CustomAttribute1 - CustomAttribute15

- Reparto

- Ufficio

- CountryOrRegion (codice paese a due lettere)

Per un elenco completo, vedere l'elenco completo dei filtri delle [cassette postali supportati.](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)

## <a name="step-2-create-a-role-group-for-each-agency"></a>Passaggio 2: Creare un gruppo di ruoli per ogni agenzia

Il passaggio successivo consiste nel creare i gruppi di ruoli nel Centro sicurezza & conformità che verranno allineati con le agenzie. Consigliamo di creare un gruppo di ruoli copiando il gruppo Manager di eDiscovery integrato, aggiungendo i membri adatti e rimuovendo i ruoli che potrebbero non essere applicabili alle proprie esigenze. Per ulteriori informazioni sui ruoli correlati a eDiscovery, vedere [Assign eDiscovery permissions](assign-ediscovery-permissions.md).
  
Per creare gruppi di ruoli, accedere alla pagina **Autorizzazioni** nel Centro sicurezza e conformità e creare un gruppo di ruoli per ogni team in ogni agenzia che utilizzerà limiti di conformità e casi di eDiscovery per gestire le indagini.
  
Utilizzando lo scenario Dei limiti di conformità di Contoso, è necessario creare quattro gruppi di ruoli e aggiungere i membri appropriati a ognuno di essi.
  
- Manager di eDiscovery di Fourth Coffee

- Investigatori di Fourth Coffee

- Manager di eDiscovery di Coho Winery

- Investigatori di Coho Winery
  
Per soddisfare i requisiti dello scenario dei limiti di  conformità  di Contoso, è inoltre necessario rimuovere i ruoli di archiviazione ed esportazione dai gruppi di ruoli degli investigatori per impedire agli investigatori di inserire blocchi nelle posizioni dei contenuti ed esportare il contenuto da un caso.

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Passaggio 3: Creare un filtro delle autorizzazioni di ricerca per applicare il limite di conformità

Dopo aver creato i gruppi di ruoli per ogni agenzia, il passaggio successivo consiste nel creare i filtri delle autorizzazioni di ricerca che associano ogni gruppo di ruoli all'agenzia specifica e definiscono il limite di conformità stesso. È necessario creare un filtro delle autorizzazioni di ricerca per ogni agenzia. Per ulteriori informazioni sulla creazione di filtri per le autorizzazioni di sicurezza, vedere [Configure permissions filtering for Content Search.](permissions-filtering-for-content-search.md)
  
Ecco la sintassi utilizzata per creare un filtro delle autorizzazioni di ricerca usato per i limiti di conformità.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

Ecco una descrizione di ogni parametro nel comando:
  
- `FilterName`: specifica il nome del filtro. Utilizzare un nome che descriva o identifichi l'agenzia in cui viene utilizzato il filtro.

- `Users`: specifica gli utenti o i gruppi a cui viene applicato questo filtro alle azioni di ricerca che eseguono. Per i limiti di conformità, questo parametro specifica i gruppi di ruoli (creati nel passaggio 3) nell'agenzia per cui si sta creando il filtro. Si noti che si tratta di un parametro multivalore che consente di includere uno o più gruppi di ruoli, separati da virgole.

- `Filters`: specifica i criteri di ricerca per il filtro. Per i limiti di conformità, definire i filtri seguenti. Ognuno di essi si applica a un percorso di contenuto.

    - `Mailbox`: specifica le cassette postali o gli OneDrive in cui i gruppi di ruoli definiti nel parametro possono `Users` eseguire la ricerca. Questo filtro consente ai membri del gruppo di ruoli di cercare solo le cassette postali o OneDrive account in un'agenzia specifica. ad `"Mailbox_Department -eq 'FourthCoffee'"` esempio.

    - `Site_Path`: specifica la SharePoint siti in cui i gruppi di ruoli definiti nel parametro possono `Users` eseguire ricerche. *SharePointURL specifica* i siti dell'agenzia in cui i membri del gruppo di ruoli possono eseguire ricerche. Ad esempio,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Si noti `Site` che i filtri e sono connessi da un `Site_Path` **operatore -or.**

     > [!NOTE]
     > La sintassi per il `Filters` parametro include un elenco di *filtri*. Un elenco di filtri è un filtro che include un filtro cassetta postale e un filtro percorso sito separati da una virgola. Nell'esempio precedente, si noti che una virgola separa Mailbox_MailboxPropertyName **e** **Site_Path**: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"` . Quando questo filtro viene elaborato durante l'esecuzione di una ricerca di contenuto, vengono creati due filtri delle autorizzazioni di ricerca dall'elenco dei filtri: un filtro cassetta postale e SharePoint filtro. Un'alternativa all'utilizzo di un elenco di filtri consiste nel creare due filtri separati per le autorizzazioni di ricerca per ogni agenzia: un filtro delle autorizzazioni di ricerca per l'attributo della cassetta postale e un filtro per gli attributi del sito SharePoint di ricerca. In entrambi i casi, i risultati saranno gli stessi. L'utilizzo di un elenco di filtri o la creazione di filtri separati per le autorizzazioni di ricerca è una questione di preferenza.

- `Action`: specifica il tipo di azione di ricerca a cui viene applicato il filtro. Ad esempio, il filtro viene applicato solo quando i membri del gruppo di ruoli  `-Action Search` definito nel `Users` parametro eseguono una ricerca. In questo caso, il filtro non verrà applicato durante l'esportazione dei risultati della ricerca. Per i limiti di conformità, utilizzare  `-Action All` in modo che il filtro si applii a tutte le azioni di ricerca. 

    Per un elenco delle azioni di ricerca, vedere la sezione "New-ComplianceSecurityFilter" in [Configure permissions filtering for Content Search.](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)

Ecco gli esempi dei due filtri di ricerca delle autorizzazioni che verrebbero creati per supportare lo scenario dei limiti di conformità di Contoso. Entrambi questi esempi includono un elenco di filtri separati da virgole, in cui i filtri relativi a cassetta postale e sito sono inclusi nello stesso filtro di ricerca delle autorizzazioni e sono separati da una virgola.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>Passaggio 4: Creare un caso di eDiscovery per indagini intra-agency

Il passaggio finale consiste nel creare un caso di Core eDiscovery o un caso di Advanced eDiscovery nel Centro conformità Microsoft 365 e quindi aggiungere il gruppo di ruoli creato nel passaggio 2 come membro del caso. Ciò comporta due caratteristiche importanti dell'utilizzo dei limiti di conformità:
  
- Solo i membri del gruppo di ruoli aggiunto al caso potranno visualizzare e accedere al caso nel Centro sicurezza & conformità. Ad esempio, se il gruppo di ruoli Fourth Coffee Investigators è l'unico membro di un caso, i membri del gruppo di ruoli Fourth Coffee eDiscovery Managers (o i membri di qualsiasi altro gruppo di ruoli) non saranno in grado di visualizzare o accedere al caso.

- Quando un membro del gruppo di ruoli assegnato a un caso esegue una ricerca associata al caso, sarà in grado di cercare solo i percorsi di contenuto all'interno dell'agenzia (definito dal filtro delle autorizzazioni di ricerca creato nel passaggio 3).

Per creare un caso e assegnare membri:

1. Passare alla **pagina Core eDiscovery** **o Advanced eDiscovery** nel Centro conformità Microsoft 365 e creare un caso.

2. Nell'elenco dei casi fare clic sul nome del caso creato.

3. Aggiungere gruppi di ruoli come membri al caso. Per istruzioni, vedere uno degli articoli seguenti:

   - [Aggiungere membri a un caso di eDiscovery di base](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [Aggiungere membri a un Advanced eDiscovery caso](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> Quando si aggiunge un gruppo di ruoli a un caso, è possibile aggiungere solo i gruppi di ruoli di cui si è membri.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Ricerca ed esportazione di contenuto in ambienti Multi-Geo

I filtri delle autorizzazioni di ricerca consentono inoltre di controllare dove viene instradato il contenuto per l'esportazione e in quale datacenter è possibile eseguire ricerche durante la ricerca di percorsi di contenuto in [un SharePoint Multi-Geo locale.](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)
  
- **Esportare i risultati della ricerca:** È possibile esportare i risultati della ricerca da Exchange cassette postali, SharePoint siti e OneDrive da un datacenter specifico. Ciò significa che è possibile specificare il percorso del datacenter da cui verranno esportati i risultati della ricerca.

    Utilizzare il **parametro Region** per i cmdlet **New-ComplianceSecurityFilter** o **Set-ComplianceSecurityFilter** per creare o modificare il datacenter attraverso cui verrà instradata l'esportazione.
  
    |**Valore parametro**|**Posizione del data center**|
    |:-----|:-----|
    |NAM  <br/> |Nord America (data center negli Stati Uniti)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asia Pacifico  <br/> |
    |CAN <br/> |Canada|
    |||

- **Instradare le ricerche di contenuto:** È possibile instradare le ricerche di contenuto di SharePoint siti e OneDrive a un datacenter satellite. Ciò significa che è possibile specificare la posizione del datacenter in cui verranno eseguite le ricerche.

    Utilizzare uno dei valori seguenti per il parametro **Region** per controllare la posizione del datacenter in cui verranno eseguite le ricerche durante la ricerca SharePoint siti e OneDrive account. 
  
    |**Valore parametro**|**Posizioni di routing del datacenter per SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |Stati Uniti  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asia Pacifico  <br/> |
    |CAN  <br/> |Stati Uniti  <br/> |
    |AUS  <br/> |Asia Pacifico  <br/> |
    |KOR  <br/> |Datacenter predefinito dell'organizzazione  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Asia Pacifico  <br/> |
    |IND  <br/> |Asia Pacifico  <br/> |
    |LAM  <br/> |Stati Uniti  <br/> |
    |NOR  <br/> |Europa |
    |BRA  <br/> |Datacenter nordamericani |
    |||

   Se non si specifica il parametro **Region** per un filtro delle autorizzazioni di ricerca, verrà cercata l'area SharePoint principale dell'organizzazione. I risultati della ricerca vengono esportati nel datacenter più vicino.

   Per semplificare il concetto, il **parametro Region** controlla il datacenter utilizzato per cercare contenuto in SharePoint e OneDrive. Ciò non si applica alla ricerca di contenuto in Exchange perché Exchange non sono vincolate dalla posizione geografica dei datacenter. Inoltre, lo stesso **valore del parametro Region** può anche dettare il datacenter attraverso cui vengono instradati le esportazioni. Questo è spesso necessario per controllare lo spostamento dei dati tra le schede geografiche.

> [!NOTE]
> Se si usa Advanced eDiscovery, il **parametro Region** non controlla l'area da cui vengono esportati i dati. I dati vengono esportati dal datacenter principale dell'organizzazione. Inoltre, la ricerca di contenuto in SharePoint e OneDrive non è associata alla posizione geografica dei datacenter. Viene ricercata in tutti i data center. Per ulteriori informazioni su Advanced eDiscovery, vedere [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).

Ecco alcuni esempi di utilizzo del **parametro Region** durante la creazione di filtri di autorizzazione di ricerca per i limiti di conformità. Ciò presuppone che la filiale Fourth Coffee si trovi in Nord America e che Coho Winery sia in Europa. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Tenere presente quanto segue durante la ricerca e l'esportazione di contenuto in ambienti multi-geografici.
  
- Il parametro **Area** non controlla le ricerche nelle cassette postali di Exchange. Tutti i data center verranno cercati quando si esegue la ricerca nelle cassette postali. Per limitare l'ambito di ricerca Exchange cassette postali, utilizzare il parametro **Filters** durante la creazione o la modifica di un filtro delle autorizzazioni di ricerca.

- Se è necessario che un responsabile di eDiscovery eserviti la ricerca in più aree di SharePoint, è necessario creare un account utente diverso da utilizzare nel filtro delle autorizzazioni di ricerca per specificare l'area in cui si trovano i siti di SharePoint o gli account OneDrive. Per ulteriori informazioni sulla configurazione di questa impostazione, vedere la sezione "Ricerca di contenuto in un ambiente SharePoint Multi-Geo" in [Ricerca contenuto.](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- Durante la ricerca di contenuto in SharePoint e OneDrive, il parametro **Region** indirizza le ricerche alla posizione principale o satellite in cui il responsabile di eDiscovery condurrà le indagini di eDiscovery. Se un responsabile di eDiscovery SharePoint e OneDrive siti esterni all'area specificata nel filtro delle autorizzazioni di ricerca, non viene restituito alcun risultato della ricerca.

- Quando si esportano i risultati della ricerca, il contenuto di tutti i percorsi di contenuto (inclusi Exchange, Skype for Business, SharePoint, OneDrive e altri servizi che è possibile cercare utilizzando lo strumento Ricerca contenuto) viene caricato nella posizione di Archiviazione di Azure nel datacenter specificato dal parametro **Region.** Ciò consente alle organizzazioni di mantenere la conformità non consentendo l'esportazione del contenuto oltre i confini controllati. Se non viene specificata alcuna area nel filtro delle autorizzazioni di ricerca, il contenuto viene caricato nel datacenter principale dell'organizzazione.

- È possibile modificare un filtro delle autorizzazioni di ricerca esistente per aggiungere o modificare l'area eseguendo il comando seguente:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Utilizzo dei limiti di conformità per SharePoint hub

[SharePoint siti hub spesso si](/sharepoint/dev/features/hub-site/hub-site-overview) allineano con gli stessi confini geografici o di agenzia che seguono i limiti di conformità di eDiscovery. Ciò significa che è possibile utilizzare la proprietà ID sito del sito hub per creare un limite di conformità. A tale scopo, utilizzare il cmdlet [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) in PowerShell di SharePoint Online per ottenere siteId per il sito hub e quindi utilizzare questo valore per la proprietà ID reparto per creare un filtro delle autorizzazioni di ricerca.

Utilizzare la sintassi seguente per creare un filtro delle autorizzazioni di ricerca per un SharePoint hub:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Ecco un esempio di creazione di un filtro delle autorizzazioni di ricerca per un sito hub per l'agenzia Coho Winery:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Limitazioni dei limiti di conformità

Tenere presenti le limitazioni seguenti quando si gestiscono casi eDiscovery e indagini che utilizzano i limiti di conformità.
  
- Quando si crea e si esegue una ricerca, è possibile selezionare i percorsi dei contenuti che si trovano all'esterno dell'agenzia. Tuttavia, a causa del filtro di ricerca delle autorizzazioni, i contenuti di tali posizioni non vengono inclusi nei risultati della ricerca.

- I limiti di conformità non si applicano ai blocchi nei casi di eDiscovery. Ciò significa che un manager di eDiscovery di un'agenzia può bloccare un utente in un'altra agenzia. Tuttavia, i limiti di conformità verranno applicati se il manager di eDiscovery cerca le posizioni dei contenuti dell'utente che è stato bloccato. Ciò significa che il manager di eDiscovery non potrà cercare le posizioni dei contenuti dell'utente, anche se è stato in grado di bloccare l'utente.

    Inoltre, le statistiche dei blocchi si applicheranno solo alle posizioni dei contenuti nell'agenzia.

- Se è stato assegnato un filtro delle autorizzazioni di ricerca (una cassetta postale o un filtro sito) e si tenta di esportare gli elementi non indicizzati per una ricerca che include tutti i siti SharePoint nell'organizzazione, verrà visualizzato il seguente messaggio di errore: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` . Se è stato assegnato un filtro delle autorizzazioni di ricerca e si desidera esportare gli elementi non indicizzati da SharePoint, sarà necessario eseguire di nuovo la ricerca e includere siti SharePoint specifici per la ricerca. In caso contrario, sarà possibile esportare solo gli elementi indicizzati da una ricerca che include tutti SharePoint siti. Per ulteriori informazioni sulle opzioni per l'esportazione dei risultati della ricerca, vedere [Export Content search results](export-search-results.md#step-1-prepare-search-results-for-export).

- I filtri di ricerca delle autorizzazioni non vengono applicati alle cartelle pubbliche di Exchange.

## <a name="more-information"></a>Ulteriori informazioni

- Se una cassetta postale è senza licenza o viene eliminata in modo recinto, l'utente non verrà più considerato entro il limite di conformità. Se un blocco è stato applicato alla cassetta postale al momento dell'eliminazione, il contenuto conservato nella cassetta postale è ancora soggetto a un limite di conformità o a un filtro delle autorizzazioni di ricerca.

- Se per un utente vengono implementati limiti di conformità e filtri per le autorizzazioni di ricerca, è consigliabile non eliminare la cassetta postale di un utente e non il OneDrive account. In altre parole, se si elimina la cassetta postale di un utente, è consigliabile rimuovere anche l'account OneDrive dell'utente poiché mailbox_RecipientFilter viene utilizzato per applicare il filtro delle autorizzazioni di ricerca per OneDrive.

- I limiti di conformità e i filtri delle autorizzazioni di ricerca dipendono dagli attributi contrassegnati sul contenuto in Exchange, OneDrive e SharePoint e dalla successiva indicizzazione di questo contenuto contrassegnato.

- Non è consigliabile usare filtri di esclusione (ad esempio in un filtro delle autorizzazioni di ricerca) per un limite di conformità `-not()` basato sul contenuto. L'utilizzo di un filtro di esclusione può avere risultati imprevisti se il contenuto con attributi aggiornati di recente non è stato indicizzato.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Chi può creare e gestire filtri per le autorizzazioni di ricerca (utilizzando New-ComplianceSecurityFilter e Set-ComplianceSecurityFilter cmdlet)?**
  
Per creare, visualizzare e modificare i filtri delle autorizzazioni di ricerca, è necessario essere membri del gruppo di ruoli Gestione organizzazione nel Centro conformità Microsoft 365.
  
**Se un manager di eDiscovery viene assegnato a più di un gruppo di ruoli che si estende su più agenzie, come cerca il contenuto in un'agenzia o nell'altra?**
  
Il manager di eDiscovery può aggiungere parametri alla query di ricerca che limitano la ricerca a un'agenzia specifica. Ad esempio, se un'organizzazione ha specificato la proprietà **CustomAttribute10** per differenziare le agenzie, può aggiungere quanto segue alla query di ricerca per cercare le cassette postali e gli account di OneDrive in un'agenzia specifica:  `CustomAttribute10:<value>` .
  
**Cosa succede se il valore dell'attributo utilizzato come attributo di conformità in un filtro delle autorizzazioni di ricerca viene modificato?**
  
Un filtro delle autorizzazioni di ricerca richiede fino a tre giorni per applicare il limite di conformità se il valore dell'attributo utilizzato nel filtro viene modificato. Ad esempio, nello scenario Contoso si supponga che un utente dell'agenzia Fourth Coffee sia trasferito all'agenzia Coho Winery. Di conseguenza, il valore dell'attributo **Department** dell'oggetto utente viene modificato da *FourthCoffee* a *CohoWinery.* In questo caso, Fourth Coffee eDiscovery e gli investitori otterrà i risultati della ricerca per tale utente per un massimo di tre giorni dopo la modifica dell'attributo. Analogamente, sono necessari fino a tre giorni prima che i responsabili e gli investigatori di Coho Winery eDiscovery osno ottenere risultati di ricerca per l'utente.
  
**Un responsabile di eDiscovery può visualizzare il contenuto da due limiti di conformità distinti?**
  
Sì, questa operazione può essere eseguita durante la ricerca nelle cassette postali di Exchange aggiungendo il manager di eDiscovery ai gruppi di ruoli che hanno visibilità per entrambe le agenzie. Tuttavia, quando si esegue una ricerca nei siti di SharePoint e negli account oneDrive, un responsabile di eDiscovery può cercare contenuto in limiti di conformità diversi solo se le agenzie si collocano nella stessa area geografica o nella stessa area geografica. **Nota:** Questa limitazione per i siti non si applica in Advanced eDiscovery perché la ricerca di contenuto in SharePoint e OneDrive non è vincolata dalla posizione geografica.
  
**I filtri delle autorizzazioni di ricerca funzionano per i blocchi dei casi di eDiscovery, i criteri di conservazione di Microsoft 365 o DLP?**
  
No, non al momento.
  
**Se si specifica un'area per controllare dove esportare il contenuto, ma non si dispone di un'organizzazione di SharePoint in tale area, è comunque possibile eseguire ricerche in SharePoint?**
  
Se l'area specificata nel filtro delle autorizzazioni di ricerca non esiste nell'organizzazione, verrà cercata l'area predefinita.
  
**Qual è il numero massimo di filtri delle autorizzazioni di ricerca che è possibile creare in un'organizzazione?**
  
Non esiste alcun limite al numero di filtri delle autorizzazioni di ricerca che è possibile creare in un'organizzazione. Tuttavia, le prestazioni della ricerca saranno influenzate quando sono presenti più di 100 filtri per le autorizzazioni di ricerca. Per mantenere il più piccolo possibile il numero di filtri per le autorizzazioni di ricerca nell'organizzazione, creare filtri che combinano le regole per Exchange, SharePoint e OneDrive in un singolo filtro delle autorizzazioni di ricerca quando possibile.
