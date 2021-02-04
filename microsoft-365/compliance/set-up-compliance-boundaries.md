---
title: Configurare i limiti di conformità per le indagini di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
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
description: Informazioni su come usare i limiti di conformità per creare limiti logici che controllano le posizioni dei contenuti degli utenti che un responsabile di eDiscovery può cercare in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe6df03491350c33416021523f276e203a416fc9
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099736"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Configurare i limiti di conformità per le indagini di eDiscovery

Le indicazioni riportate in questo articolo possono essere applicate quando si utilizza Core eDiscovery o Advanced eDiscovery per gestire le indagini.

I limiti di conformità creano limiti logici all'interno di un'organizzazione che controllano le posizioni dei contenuti degli utenti (ad esempio cassette postali, account di OneDrive e siti di SharePoint) che i responsabili di eDiscovery possono cercare. Inoltre, i limiti di conformità controllano chi può accedere ai casi di eDiscovery utilizzati per gestire le indagini legali, umane o di altro tipo all'interno dell'organizzazione. La necessità di rispettare i limiti di conformità è spesso necessaria per le multinazionali che devono rispettare i consiglieri geografici e le normative e per i governi, che spesso sono suddivisi in agenzie diverse. In Microsoft 365, i limiti di conformità consentono di soddisfare questi requisiti quando si eseguono ricerche di contenuto e si gestiscono le indagini con i casi di eDiscovery.
  
L'esempio viene utilizzato nella figura seguente per illustrare il funzionamento dei limiti di conformità.
  
![I limiti di conformità sono costituiti da filtri delle autorizzazioni di ricerca che controllano l'accesso alle agenzie e ai gruppi di ruoli di amministratore che controllano l'accesso ai casi di eDiscovery](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
In questo esempio, Contoso LTD è un'organizzazione costituita da due filiali, Fourth Coffee e Coho Winery. L'azienda richiede che i manager e gli investigatori di eDiscovery possano eseguire ricerche solo nelle cassette postali di Exchange, negli account di OneDrive e nei siti di SharePoint nell'agenzia. Inoltre, i responsabili e gli investigatori di eDiscovery possono vedere solo i casi di eDiscovery nella propria agenzia e possono accedere solo ai casi di cui sono membri. Ecco come i limiti di conformità soddisfano questi requisiti.
  
- La funzionalità di filtro delle autorizzazioni di ricerca in Ricerca contenuto controlla i percorsi di contenuto che i responsabili e gli investigatori di eDiscovery possono cercare. Ciò significa che i responsabili e gli investigatori di eDiscovery dell'agenzia Fourth Coffee possono cercare solo i percorsi dei contenuti nella filiale Fourth Coffee. La stessa restrizione si applica alla filiale Coho Winery.

    I gruppi di ruoli controllano chi può visualizzare i casi di eDiscovery nel Centro sicurezza & conformità. Ciò significa che i responsabili e gli investigatori di eDiscovery possono vedere solo i casi di eDiscovery nella loro agenzia.

- I gruppi di ruoli controllano inoltre chi può assegnare membri a un caso di eDiscovery. Ciò significa che i responsabili e gli investigatori di eDiscovery possono assegnare membri solo ai casi di cui sono membri.

Ecco il processo per la configurazione dei limiti di conformità:
  
[Passaggio 1: identificare un attributo utente per definire le agenzie](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Passaggio 2: sincronizzazione dell'attributo utente con gli account di OneDrive da parte del supporto tecnico Microsoft](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Passaggio 3: Creare un gruppo di ruoli per ogni agenzia](#step-3-create-a-role-group-for-each-agency)

[Passaggio 4: Creare un filtro delle autorizzazioni di ricerca per applicare il limite di conformità](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Passaggio 5: Creare un caso di eDiscovery per un'indagine interna all'agenzia](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Prima di configurare i limiti di conformità

È necessario soddisfare i prerequisiti seguenti prima che l'attributo di Azure Active Directory (Azure AD) identità dell'utente (nel passaggio 1) possa essere sincronizzato correttamente con l'account OneDrive di un utente (nel passaggio 2):

- Agli utenti devono essere assegnate una licenza di Exchange Online e una licenza di SharePoint Online.

- Le cassette postali degli utenti devono avere una dimensione di almeno 10 MB. Se la cassetta postale di un utente è inferiore a 10 MB, l'attributo usato per definire le agenzie non verrà sincronizzato con l'account OneDrive dell'utente.

- I limiti di conformità e gli attributi usati per creare i filtri delle autorizzazioni di ricerca richiedono che gli attributi di Azure Active Directory (Azure AD) siano sincronizzati con le cassette postali degli utenti. Per verificare che gli attributi che si desidera utilizzare siano stati sincronizzati, eseguire il cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) in PowerShell di Exchange Online. L'output di questo cmdlet visualizza gli attributi di Azure AD sincronizzati con Exchange Online.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Passaggio 1: identificare un attributo utente per definire le agenzie

Il primo passaggio consiste nel scegliere un attributo di Azure AD da usare per definire le agenzie. Questo attributo viene utilizzato per creare il filtro delle autorizzazioni di ricerca che limita un responsabile di eDiscovery a cercare solo i percorsi di contenuto degli utenti a cui è assegnato un valore specifico per questo attributo. Si supponga, ad esempio, che Contoso decida di utilizzare **l'attributo Department.** Il valore di questo attributo per gli utenti della filiale Fourth Coffee sarà e il valore per gli utenti della filiale  `FourthCoffee`  Coho Winery sarà `CohoWinery` . Nel passaggio 4 si utilizza questa coppia  `attribute:value`  (ad esempio, *Department:FourthCoffee)* per limitare i percorsi dei contenuti degli utenti che i responsabili di eDiscovery possono cercare. 
  
Ecco un elenco degli attributi utente di Azure AD che puoi usare per i limiti di conformità:
  
- Company

- CustomAttribute1 - CustomAttribute15

- Reparto

- Ufficio

- C (codice paese a due lettere) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> Questo attributo è mappato alla proprietà CountryOrRegion restituita eseguendo il cmdlet **Get-User** in PowerShell di Exchange Online. Il cmdlet restituisce il nome localizzato del paese, che viene convertito dal codice paese di due lettere. Per ulteriori informazioni, vedere la descrizione del parametro CountryOrRegion nell'articolo di riferimento sui cmdlet [Set-User.](https://docs.microsoft.com/powershell/module/exchange/set-user)

Anche se sono disponibili più attributi utente, in particolare per le cassette postali di Exchange, gli attributi elencati in precedenza sono gli unici attualmente supportati da OneDrive.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Passaggio 2: sincronizzazione dell'attributo utente con gli account di OneDrive da parte del supporto tecnico Microsoft

Il passaggio successivo consiste nel sincronizzazione dell'attributo di Azure AD scelto nel passaggio 1 con tutti gli account di OneDrive nell'organizzazione. Dopo la sincronizzazione, l'attributo e il relativo valore scelto nel passaggio 1 verranno mappati a una proprietà gestita nascosta denominata `ComplianceAttribute` . Utilizzare questo attributo per creare il filtro delle autorizzazioni di ricerca per OneDrive nel passaggio 4.
  
Includi le informazioni seguenti quando invii la richiesta al supporto tecnico Microsoft:
  
- Il nome di dominio predefinito dell'organizzazione

- Nome dell'attributo di Azure AD (dal passaggio 1)

- Il seguente titolo o descrizione dello scopo della richiesta di supporto: "Abilitare la sincronizzazione di OneDrive for Business con Azure AD per i filtri di sicurezza di conformità". Ciò consente di instradare la richiesta al team di progettazione di eDiscovery che implementa la richiesta.

Dopo aver apportato la modifica tecnica e aver sincronizzato l'attributo con OneDrive, il supporto tecnico Microsoft ti invierà il numero di build in cui è stata apportata la modifica e una data di distribuzione stimata. Il processo di distribuzione in genere richiede da 4 a 6 settimane dopo l'invio della richiesta di supporto.
  
> [!IMPORTANT]
> È possibile completare i passaggi da 3 a 5 prima della distribuzione di questa modifica dell'attributo. Tuttavia, l'esecuzione di ricerche di contenuto non restituirà i documenti dagli account di OneDrive specificati in un filtro delle autorizzazioni di ricerca fino a quando non viene distribuita la sincronizzazione degli attributi.
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Passaggio 3: Creare un gruppo di ruoli per ogni agenzia

Il passaggio successivo consiste nel creare i gruppi di ruoli nel Centro sicurezza & conformità in linea con le agenzie. È consigliabile creare un gruppo di ruoli copiando il gruppo predefinito Responsabili di eDiscovery, aggiungendo i membri appropriati e rimuovendo i ruoli che potrebbero non essere applicabili alle proprie esigenze. Per ulteriori informazioni sui ruoli correlati a eDiscovery, vedere Assegnare autorizzazioni di eDiscovery nel Centro sicurezza e conformità [& di Office 365.](assign-ediscovery-permissions.md)
  
Per creare i gruppi di  ruoli, passare alla pagina Autorizzazioni nel Centro sicurezza & conformità e creare un gruppo di ruoli per ogni team in ogni agenzia che utilizzerà i limiti di conformità e i casi di eDiscovery per gestire le indagini.
  
Utilizzando lo scenario dei limiti di conformità di Contoso, è necessario creare quattro gruppi di ruoli e aggiungere i membri appropriati a ognuno di essi.
  
- Fourth Coffee eDiscovery Managers

- Fourth Coffee Investigators

- Coho Winery eDiscovery Managers

- Coho Winery Investigators
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Passaggio 4: Creare un filtro delle autorizzazioni di ricerca per applicare il limite di conformità

Dopo aver creato i gruppi di ruoli per ogni agenzia, il passaggio successivo consiste nel creare i filtri delle autorizzazioni di ricerca che associano ogni gruppo di ruoli all'agenzia specifica e definiscono il limite di conformità stesso. È necessario creare un filtro delle autorizzazioni di ricerca per ogni agenzia. Per ulteriori informazioni sulla creazione di filtri per le autorizzazioni di sicurezza, vedere [Configure permissions filtering for Content Search.](permissions-filtering-for-content-search.md)
  
Ecco la sintassi usata per creare un filtro delle autorizzazioni di ricerca usato per i limiti di conformità.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

Ecco una descrizione di ogni parametro nel comando:
  
- `FilterName`: specifica il nome del filtro. Utilizzare un nome che descriva o identifichi l'agenzia in cui viene utilizzato il filtro.

- `Users`: specifica gli utenti o i gruppi che ottengono questo filtro applicato alle azioni di ricerca contenuto che eseguono. Per i limiti di conformità, questo parametro specifica i gruppi di ruoli (creati nel passaggio 3) nell'agenzia per cui si sta creando il filtro. Si noti che si tratta di un parametro multivalore che consente di includere uno o più gruppi di ruoli, separati da virgole.

- `Filters`: specifica i criteri di ricerca per il filtro. Per i limiti di conformità, definire i filtri seguenti. Ognuno di essi si applica a un percorso di contenuto. 

    - `Mailbox`: specifica le cassette postali in cui i gruppi di ruoli definiti nel parametro possono  `Users` eseguire ricerche. Per i limiti di conformità,  *ComplianceAttribute*  è lo stesso attributo identificato nel passaggio 1 e  *AttributeValue*  specifica l'agenzia. Questo filtro consente ai membri del gruppo di ruoli di cercare solo le cassette postali di un'agenzia specifica; ad esempio `"Mailbox_Department -eq 'FourthCoffee'"` . 

    - `Site`: specifica gli account di OneDrive in cui i gruppi di ruoli definiti nel parametro possono `Users` eseguire ricerche. Per il filtro di OneDrive, utilizzare la stringa  `ComplianceAttribute` effettiva. Questo attributo viene mappato allo stesso attributo identificato nel passaggio 1 e sincronizzato con gli account di OneDrive in seguito alla richiesta di supporto inviata nel passaggio 2. *AttributeValue*  specifica l'agenzia. Questo filtro consente ai membri del gruppo di ruoli di cercare solo gli account di OneDrive in un'agenzia specifica; ad esempio  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` .

    - `Site_Path`: specifica i siti di SharePoint in cui i gruppi di ruoli definiti nel parametro possono  `Users` eseguire ricerche. *L'URL di SharePoint* specifica i siti dell'agenzia in cui i membri del gruppo di ruoli possono eseguire ricerche. Ad esempio,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Si noti `Site` che i filtri e sono collegati da un `Site_Path` **operatore -or.**

     > [!NOTE]
     > La sintassi per il `Filters` parametro include un elenco di *filtri.* Un elenco di filtri è un filtro che include un filtro delle cassette postali e un filtro sito separati da una virgola. Nell'esempio precedente si noti che una virgola separa Mailbox_ComplianceAttribute **e** **Site_ComplianceAttribute**: `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` . Quando questo filtro viene elaborato durante l'esecuzione di una ricerca di contenuto, vengono creati due filtri delle autorizzazioni di ricerca dall'elenco dei filtri: un filtro cassetta postale e un filtro sito. Un'alternativa all'utilizzo di un elenco di filtri consiste nel creare due filtri separati per le autorizzazioni di ricerca per ogni agenzia: un filtro delle autorizzazioni di ricerca per l'attributo della cassetta postale e un filtro per gli attributi del sito. In entrambi i casi, i risultati saranno gli stessi. L'uso di un elenco di filtri o la creazione di filtri separati per le autorizzazioni di ricerca è una questione di preferenza.

- `Action`: specifica il tipo di azione di ricerca di conformità a cui viene applicato il filtro. Ad esempio, il filtro viene applicato solo quando i membri del gruppo di ruoli definito nel parametro eseguono  `-Action Search` `Users` una ricerca di contenuto. In questo caso, il filtro non verrà applicato durante l'esportazione dei risultati della ricerca. Per i limiti di conformità, usare  `-Action All` questo filtro per applicare il filtro a tutte le azioni di ricerca. 

    Per un elenco delle azioni di Ricerca contenuto, vedere la sezione "New-ComplianceSecurityFilter" in [Configure permissions filtering for Content Search.](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)

Ecco alcuni esempi dei due filtri delle autorizzazioni di ricerca che verrebbero creati per supportare lo scenario dei limiti di conformità di Contoso. Entrambi questi esempi includono un elenco di filtri delimitati da virgole, in cui i filtri delle cassette postali e dei siti sono inclusi nello stesso filtro delle autorizzazioni di ricerca e sono separati da una virgola.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>Passaggio 5: Creare un caso di eDiscovery per le indagini tra le agenzie

Il passaggio finale consiste nel creare un caso di Core eDiscovery o advanced eDiscovery nel Centro conformità Microsoft 365 e quindi aggiungere il gruppo di ruoli creato nel passaggio 3 come membro del caso. Ciò determina due caratteristiche importanti dell'utilizzo dei limiti di conformità:
  
- Solo i membri del gruppo di ruoli aggiunto al caso potranno visualizzare e accedere al caso nel Centro sicurezza & conformità. Ad esempio, se il gruppo di ruoli Fourth Coffee Investigators è l'unico membro di un caso, i membri del gruppo di ruoli Fourth Coffee eDiscovery Managers (o i membri di qualsiasi altro gruppo di ruoli) non saranno in grado di visualizzare o accedere al caso.

- Quando un membro del gruppo di ruoli assegnato a un caso esegue una ricerca associata al caso, sarà in grado di cercare solo i percorsi dei contenuti all'interno dell'agenzia (definito dal filtro delle autorizzazioni di ricerca creato nel passaggio 4).

Per creare un caso e assegnare membri:

1. Passare alla pagina **Core eDiscovery** o **Advanced eDiscovery** nel Centro conformità Microsoft 365 e creare un caso.

2. Nell'elenco dei casi fare clic sul nome del caso creato.

3. Nella pagina **Gestisci questo caso** a comparsa, in Gestisci gruppi di **ruoli,** fare clic su ![ Aggiungi icona ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Aggiungi.**

    ![Aggiungere un gruppo di ruoli come membro di un caso di eDiscovery](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. Nell'elenco dei gruppi di ruoli, selezionare uno dei gruppi di ruoli creati nel passaggio 3 e fare clic su **Aggiungi**.

5. Fare **clic** su Salva nel **riquadro** a comparsa Gestisci questo caso per salvare la modifica.

> [!NOTE]
Quando si aggiunge un gruppo di ruoli a un caso, è possibile aggiungere solo i gruppi di ruoli di cui si è membri.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Ricerca ed esportazione di contenuto in ambienti Multi-Geo

I filtri delle autorizzazioni di ricerca consentono inoltre di controllare dove viene instradato il contenuto per l'esportazione e in quale datacenter è possibile eseguire ricerche durante la ricerca di percorsi di contenuto in un ambiente [SharePoint Multi-Geo.](https://go.microsoft.com/fwlink/?linkid=860840)
  
- **Esportare i risultati della ricerca:** È possibile esportare i risultati della ricerca dalle cassette postali di Exchange, dai siti di SharePoint e dagli account di OneDrive da un datacenter specifico. Ciò significa che è possibile specificare il percorso del datacenter da cui verranno esportati i risultati della ricerca.

    Utilizzare il **parametro Region** per i cmdlet **New-ComplianceSecurityFilter** o **Set-ComplianceSecurityFilter** per creare o modificare il datacenter attraverso il quale verrà instradata l'esportazione.
  
    |**Valore parametro**|**Posizione del datacenter**|
    |:-----|:-----|
    |NAM  <br/> |Nord America (i datacenter sono negli Stati Uniti)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asia Pacifico  <br/> |
    |CAN <br/> |Canada|
    |||

- **Instradare le ricerche di contenuto:** È possibile instradare le ricerche di contenuto dei siti di SharePoint e degli account di OneDrive a un datacenter satellite. Ciò significa che è possibile specificare la posizione del datacenter in cui verranno eseguite le ricerche.

    Utilizzare uno dei valori seguenti per il parametro **Region** per controllare la posizione del datacenter in cui verranno eseguite le ricerche durante la ricerca di siti di SharePoint e account di OneDrive. 
  
    |**Valore parametro**|**Percorsi di routing del datacenter per SharePoint**|
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
    |BRA  <br/> |Data center nord america |
    |||

   Se non si specifica il parametro **Region** per un filtro delle autorizzazioni di ricerca, verrà cercata l'area di SharePoint principale dell'organizzazione. I risultati della ricerca vengono esportati nel datacenter più vicino.

   Per semplificare il concetto, il parametro **Region** controlla il datacenter utilizzato per cercare contenuto in SharePoint e OneDrive. Ciò non si applica alla ricerca di contenuto in Exchange perché le ricerche di contenuto di Exchange non sono vincolate dalla posizione geografica dei datacenter. Inoltre, lo stesso **valore del** parametro Region può anche indicare il datacenter attraverso cui vengono instradati le esportazioni. Questo è spesso necessario per controllare lo spostamento dei dati tra le aree geografiche.

> [!NOTE]
> Se si utilizza Advanced eDiscovery, il parametro **Region** non controlla l'area da cui vengono esportati i dati. I dati vengono esportati dal datacenter principale dell'organizzazione. Inoltre, la ricerca di contenuto in SharePoint e OneDrive non è vincolata dalla posizione geografica dei datacenter. La ricerca viene esequista in tutti i datacenter. Per ulteriori informazioni su Advanced eDiscovery, vedere [Panoramica della soluzione Advanced eDiscovery in Microsoft 365.](overview-ediscovery-20.md)

Ecco alcuni esempi di utilizzo del parametro **Region** durante la creazione di filtri delle autorizzazioni di ricerca per i limiti di conformità. Si presuppone che la filiale Fourth Coffee si trovi in Nord America e che Coho Winery si trovi in Europa. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Tenere presente quanto segue durante la ricerca e l'esportazione di contenuto in ambienti multi-geografici.
  
- Il parametro **Area** non controlla le ricerche nelle cassette postali di Exchange. Tutti i datacenter verranno cercati quando si esegue una ricerca nelle cassette postali. Per limitare l'ambito di ricerca delle cassette postali di Exchange, utilizzare il parametro **Filters** durante la creazione o la modifica di un filtro delle autorizzazioni di ricerca. 

- Se è necessario che un responsabile di eDiscovery eservi una ricerca in più aree di SharePoint, è necessario creare un account utente diverso da utilizzare nel filtro delle autorizzazioni di ricerca per specificare l'area in cui si trovano i siti di SharePoint o gli account di OneDrive. Per ulteriori informazioni sulla configurazione, vedere la sezione "Ricerca di contenuto in un ambiente SharePoint Multi-Geo" in [Ricerca contenuto.](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- Durante la ricerca di contenuto in SharePoint e OneDrive, il parametro **Region** indirizza le ricerche alla posizione principale o satellite in cui il responsabile di eDiscovery condurrà indagini eDiscovery. Se un responsabile di eDiscovery esegue una ricerca nei siti di SharePoint e OneDrive all'esterno dell'area specificata nel filtro delle autorizzazioni di ricerca, non viene restituito alcun risultato della ricerca.

- Quando si esportano i risultati della ricerca, il contenuto da tutti i percorsi di contenuto (inclusi Exchange, Skype for Business, SharePoint, OneDrive e altri servizi che è possibile cercare utilizzando lo strumento Ricerca contenuto) viene caricato nel percorso di Archiviazione di Azure nel datacenter specificato dal parametro **Region.** Ciò consente alle organizzazioni di rimanere conformi non consentendo l'esportazione del contenuto attraverso confini controllati. Se non viene specificata alcuna area nel filtro delle autorizzazioni di ricerca, il contenuto viene caricato nel datacenter principale dell'organizzazione.

- È possibile modificare un filtro delle autorizzazioni di ricerca esistente per aggiungere o modificare l'area eseguendo il comando seguente:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Utilizzo dei limiti di conformità per i siti hub di SharePoint

[I siti hub di SharePoint](https://docs.microsoft.com/sharepoint/dev/features/hub-site/hub-site-overview) spesso sono allineati con gli stessi confini geografici o di agenzia che seguono i limiti di conformità di eDiscovery. Ciò significa che è possibile utilizzare la proprietà ID sito del sito hub per creare un limite di conformità. A tale scopo, utilizzare il cmdlet [Get-SPOHubSite](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spohubsite#examples) in PowerShell di SharePoint Online per ottenere il SiteId per il sito hub e quindi utilizzare questo valore per la proprietà ID reparto per creare un filtro delle autorizzazioni di ricerca.

Utilizzare la sintassi seguente per creare un filtro delle autorizzazioni di ricerca per un sito hub di SharePoint:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Ecco un esempio di creazione di un filtro delle autorizzazioni di ricerca per un sito hub per l'agenzia Coho Winery:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Limitazioni dei limiti di conformità

Tenere presenti le limitazioni seguenti quando si gestiscono i casi di eDiscovery e le indagini che utilizzano i limiti di conformità.
  
- Quando si crea ed esegue una ricerca, è possibile selezionare percorsi di contenuto esterni all'agenzia. Tuttavia, a causa del filtro delle autorizzazioni di ricerca, il contenuto di tali percorsi non viene incluso nei risultati della ricerca.

- I limiti di conformità non si applicano ai blocchi nei casi di eDiscovery. Ciò significa che un responsabile di eDiscovery in un'agenzia può mettere in attesa un utente in un'agenzia diversa. Tuttavia, il limite di conformità verrà applicato se il responsabile di eDiscovery esegue una ricerca nei percorsi dei contenuti dell'utente che è stato messo in attesa. Ciò significa che il responsabile di eDiscovery non sarà in grado di eseguire ricerche nei percorsi dei contenuti dell'utente, anche se è stato in grado di mettere l'utente in attesa.

    Inoltre, le statistiche sulle esenzioni verranno applicate solo alle posizioni dei contenuti nell'agenzia.

- I filtri delle autorizzazioni di ricerca non vengono applicati alle cartelle pubbliche di Exchange.

## <a name="more-information"></a>Ulteriori informazioni

- Se una cassetta postale viene eliminata in licenza o eliminata in modo recinto, gli attributi di Azure AD non vengono più sincronizzati con la cassetta postale. Se un blocco è stato applicato alla cassetta postale al momento dell'eliminazione, il contenuto conservato nella cassetta postale è ancora soggetto a un limite di conformità o a un filtro delle autorizzazioni di ricerca in base all'ultima sincronizzazione degli attributi di Azure AD prima dell'eliminazione della cassetta postale. 

    Inoltre, la sincronizzazione tra la cassetta postale dell'utente e l'account di OneDrive cesserà se la cassetta postale è senza licenza o eliminata temporaneamente. L'ultimo valore contrassegnato dell'attributo di conformità per l'account di OneDrive rimarrà valido.

- L'attributo di conformità viene sincronizzato dalla cassetta postale di Exchange di un utente al proprio account OneDrive ogni sette giorni. Come indicato in precedenza, questa sincronizzazione si verifica solo quando all'utente viene assegnata una licenza di Exchange Online e SharePoint Online e la cassetta postale dell'utente è di almeno 10 MB.

- Se i limiti di conformità e i filtri delle autorizzazioni di ricerca sono implementati sia per la cassetta postale di un utente che per l'account di OneDrive, è consigliabile non eliminare la cassetta postale di un utente e non il relativo account di OneDrive. In altre parole, se si elimina la cassetta postale di un utente, è necessario rimuovere anche l'account OneDrive dell'utente.

- Esistono situazioni (ad esempio un dipendente che ritorna) in cui un utente potrebbe avere due o più account di OneDrive. In questi casi, verrà sincronizzato solo l'account di OneDrive principale associato all'utente in Azure AD.

- I limiti di conformità e i filtri delle autorizzazioni di ricerca dipendono dagli attributi contrassegnati per il contenuto in Exchange, OneDrive e SharePoint e dalla successiva indicizzazione di questo contenuto contrassegnato. 

- Non è consigliabile usare filtri di esclusione (ad esempio l'uso in un filtro delle autorizzazioni di ricerca) per un limite `-not()` di conformità basato sul contenuto. L'utilizzo di un filtro di esclusione può avere risultati imprevisti se il contenuto con attributi aggiornati di recente non è stato indicizzato. 

## <a name="frequently-asked-questions"></a>Domande frequenti

**Chi può creare e gestire i filtri delle autorizzazioni di ricerca (utilizzando New-ComplianceSecurityFilter e Set-ComplianceSecurityFilter cmdlet)?**
  
Per creare, visualizzare e modificare i filtri delle autorizzazioni di ricerca, è necessario essere membri del gruppo di ruoli Gestione organizzazione nel Centro sicurezza & conformità.
  
**Se un responsabile di eDiscovery viene assegnato a più gruppi di ruoli che si estendono su più agenzie, come cerca contenuto in un'agenzia o nell'altra?**
  
Il responsabile di eDiscovery può aggiungere parametri alla query di ricerca che limitano la ricerca a un'agenzia specifica. Ad esempio, se un'organizzazione ha specificato la proprietà **CustomAttribute10** per differenziare le agenzie, può aggiungere quanto segue alla query di ricerca per cercare le cassette postali e gli account di OneDrive in un'agenzia specifica:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` .
  
**Cosa succede se il valore dell'attributo utilizzato come attributo di conformità in un filtro delle autorizzazioni di ricerca viene modificato?**
  
Sono necessari fino a tre giorni prima che un filtro delle autorizzazioni di ricerca apporti il limite di conformità se il valore dell'attributo usato nel filtro viene modificato. Ad esempio, nello scenario Contoso si supponga che un utente dell'agenzia Fourth Coffee sia trasferito all'agenzia Coho Winery. Di conseguenza, il valore dell'attributo **Department** per l'oggetto utente viene modificato da *FourthCoffee* a *CohoWinery.* In questo caso, Fourth Coffee eDiscovery e gli investitori otterrà risultati di ricerca per quell'utente per un massimo di tre giorni dopo la modifica dell'attributo. Analogamente, sono necessari fino a tre giorni prima che i responsabili e gli investigatori di Coho Winery eDiscovery otterrà i risultati della ricerca per l'utente.
  
**Un responsabile di eDiscovery può visualizzare il contenuto da due limiti di conformità separati?**
  
Sì, questa operazione può essere eseguita quando si esegue una ricerca nelle cassette postali di Exchange aggiungendo il manager di eDiscovery ai gruppi di ruoli che hanno visibilità per entrambe le agenzie. Tuttavia, quando si esegue una ricerca nei siti di SharePoint e negli account di OneDrive, un responsabile di eDiscovery può cercare contenuto in limiti di conformità diversi solo se le agenzie si collocano nella stessa area geografica o area geografica. **Nota:** Questa limitazione per i siti non si applica in Advanced eDiscovery perché la ricerca di contenuto in SharePoint e OneDrive non è vincolata dalla posizione geografica.
  
**I filtri delle autorizzazioni di ricerca funzionano per i blocchi dei casi di eDiscovery, i criteri di conservazione di Microsoft 365 o DLP?**
  
No, non al momento.
  
**Se si specifica un'area per controllare dove esportare il contenuto, ma non si dispone di un'organizzazione di SharePoint in tale area, è comunque possibile eseguire ricerche in SharePoint?**
  
Se l'area specificata nel filtro delle autorizzazioni di ricerca non esiste nell'organizzazione, verrà cercata l'area predefinita.
  
**Qual è il numero massimo di filtri per le autorizzazioni di ricerca che è possibile creare in un'organizzazione?**
  
Non esiste alcun limite al numero di filtri delle autorizzazioni di ricerca che è possibile creare in un'organizzazione. Tuttavia, le prestazioni della ricerca saranno influenzate quando sono presenti più di 100 filtri per le autorizzazioni di ricerca. Per mantenere il numero di filtri delle autorizzazioni di ricerca nell'organizzazione il più piccolo possibile, creare filtri che combinano le regole per Exchange, SharePoint e OneDrive in un singolo filtro delle autorizzazioni di ricerca quando possibile.
