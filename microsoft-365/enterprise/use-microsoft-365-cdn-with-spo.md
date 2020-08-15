---
title: Utilizzare la rete di distribuzione dei contenuti (CDN) di Office 365 con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Informazioni su come utilizzare la rete di distribuzione dei contenuti (CDN) di Office 365 per velocizzare il recapito delle risorse di SharePoint Online.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690975"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online

È possibile usare la rete per la distribuzione di contenuti di Office 365 predefinita per ospitare risorse statiche e migliorare le prestazioni delle pagine di SharePoint Online. La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza. Inoltre, la rete CDN di Office 365 utilizza il [protocollo http/2](https://en.wikipedia.org/wiki/HTTP/2) per migliorare la compressione e il pipelining HTTP. Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

> [!NOTE]
> La rete CDN di Office 365 è disponibile solo per i tenant nel cloud di **produzione** (tutto il mondo). Gli inquilini del governo degli Stati Uniti, le nuvole cinesi e tedesche attualmente non supportano la rete CDN di Office 365.

La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità. In base al tipo di contenuto che si vuole ospitare nella rete per la distribuzione di contenuti di Office 365, è possibile aggiungere origini **pubbliche**, origini **private** o entrambi. Per ulteriori informazioni sulla differenza tra origini pubbliche e private, vedere [scegliere se ogni origine deve essere pubblica o privata](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) .

![Diagramma concettuale della rete CDN di Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagramma concettuale della rete CDN di Office 365")

Se si ha già familiarità con la modalità di funzionamento di reti CDN, è necessario completare solo alcuni passaggi per abilitare la rete CDN di Office 365 per il tenant. In questo argomento viene descritto come. Leggere per informazioni su come iniziare a ospitare le risorse statiche.

> [!TIP]
> Sono disponibili altri reti CDN ospitati da Microsoft che possono essere utilizzati con Office 365 per scenari di utilizzo specializzati, ma non sono descritti in questo argomento perché non rientrano nell'ambito della rete CDN di Office 365. Per ulteriori informazioni, vedere [other Microsoft reti CDN](content-delivery-networks.md#other-microsoft-cdns).

 **Tornare a [pianificazione della rete e ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune).**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Panoramica dell'utilizzo della rete CDN di Office 365 in SharePoint Online

Per configurare la rete CDN di Office 365 per l'organizzazione, attenersi alla procedura di base riportata di seguito:

+ [Pianificare la distribuzione della rete CDN di Office 365](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Determinare quali risorse statiche si desidera ospitare sulla rete CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).
  + [Determinare la posizione in cui si desidera archiviare i cespiti](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets). Questo percorso può essere un sito, una raccolta o una cartella di SharePoint ed è denominato _origine_.
  + [Scegliere se ogni origine deve essere pubblica o privata](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate). È possibile aggiungere origini multiple di tipi pubblici e privati.

+ Impostare e configurare la rete CDN, utilizzando PowerShell o la CLI di SharePoint Online

  + [Impostare e configurare la rete CDN tramite SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Impostare e configurare la rete CDN tramite PowerShell PnP](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Impostare e configurare la rete CDN tramite la CLI di Office 365](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Al termine di questo passaggio, si avranno le seguenti operazioni:

  + Abilitato la rete CDN per la propria organizzazione.
  + Sono state aggiunte le origini, identificando ogni origine come pubblico o privato.

Dopo aver completato l'installazione, è possibile [gestire la rete CDN di Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) nel tempo:
  
+ Aggiunta, aggiornamento e rimozione di risorse
+ Aggiunta e rimozione di origini
+ Configurazione di criteri CDN
+ Se necessario, disabilitando la rete CDN

Infine, vedere [utilizzo delle risorse](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) della rete CDN per informazioni sull'accesso alle risorse della rete CDN sia dall'origine pubblica che da quella privata.

Consultare [risoluzione dei problemi relativi alla rete CDN di Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) per indicazioni sulla risoluzione di problemi comuni.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Pianificare la distribuzione della rete CDN di Office 365

Prima di distribuire la rete CDN di Office 365 per il tenant di Office 365, è necessario tenere in considerazione i fattori seguenti nell'ambito del processo di pianificazione.

  + [Determinare quali risorse statiche si desidera ospitare nella rete CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Determinare la posizione in cui si desidera archiviare le risorse](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Scegliere se ogni origine deve essere pubblica o privata](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Determinare quali risorse statiche si desidera ospitare nella rete CDN

In generale, reti CDN è più efficace per ospitare _risorse statiche_o risorse che non cambiano molto spesso. Una buona regola empirica consiste nell'identificare i file che soddisfano alcune o tutte queste condizioni:

+ File statici incorporati in una pagina (come script e immagini) che potrebbero avere un impatto incrementale significativo sui tempi di caricamento delle pagine
+ File di grandi dimensioni come eseguibili e file di installazione
+ Raccolte di risorse che supportano il codice sul retro del client

Ad esempio, i file di piccole dimensioni ripetutamente richiesti come le immagini e gli script del sito possono migliorare significativamente le prestazioni di rendering dei siti e ridurre in modo incrementale il carico nei siti di SharePoint Online quando vengono aggiunti a un'origine CDN. I file di grandi dimensioni, ad esempio gli eseguibili di installazione, possono essere scaricati dalla rete CDN, garantendo un impatto positivo sulle prestazioni e una conseguente riduzione del carico sul sito di SharePoint Online, anche se non è possibile accedervi con la frequenza.

Il miglioramento delle prestazioni in base ai file dipende da molti fattori, tra cui la vicinanza del client all'endpoint CDN più vicino, le condizioni transitorie sulla rete locale e così via. Molti file statici sono piuttosto ridotti e possono essere scaricati da Office 365 in meno di un secondo. Tuttavia, una pagina Web può contenere molti file incorporati con un tempo di download cumulativo di alcuni secondi. La gestione di questi file dalla rete CDN può ridurre significativamente il tempo complessivo di caricamento delle pagine. Per un esempio, vedere [quali guadagni di prestazioni fornisce una rete CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Determinare la posizione in cui si desidera archiviare le risorse

La rete CDN recupera le risorse da una posizione denominata _Origin_. Un'origine può essere un sito di SharePoint, una raccolta documenti o una cartella accessibile da un URL. Si dispone di una grande flessibilità quando si specificano le origini per l'organizzazione. Ad esempio, è possibile specificare più origini o una singola origine in cui si desidera inserire tutte le risorse della rete CDN. È possibile scegliere di avere origini sia pubbliche che private per la propria organizzazione. La maggior parte delle organizzazioni sceglie di implementare una combinazione dei due.

È possibile creare un nuovo contenitore per le origini, ad esempio le cartelle o le raccolte documenti, e aggiungere i file che si desidera rendere disponibili dalla rete CDN. Questo è un buon approccio se si dispone di un insieme specifico di risorse che si desidera rendere disponibili dalla rete CDN e si desidera limitare il set di risorse della rete CDN solo ai file presenti nel contenitore.

È inoltre possibile configurare una raccolta siti, un sito, una raccolta o una cartella esistente come origine, in modo da rendere tutte le risorse idonee nel contenitore disponibili dalla rete CDN. Prima di aggiungere un contenitore esistente come origine, è importante assicurarsi di essere a conoscenza del contenuto e delle autorizzazioni in modo da non esporre inavvertitamente le risorse all'accesso anonimo o agli utenti non autorizzati.

È possibile definire i criteri della rete _CDN_ per escludere il contenuto nelle origini dalla rete CDN. I criteri della rete CDN escludono le risorse in origine pubblica o privata per attributi quali _tipo di file_ e _classificazione dei siti_e vengono applicati a tutte le origini del CdnType (privato o pubblico) specificato nel criterio. Ad esempio, se si aggiunge un'origine privata costituita da un sito contenente più siti secondari, è possibile definire un criterio per escludere i siti contrassegnati come **riservati** in modo che il contenuto proveniente da siti con tale classificazione applicato non venga utilizzato dalla rete CDN. Il criterio si applica ai contenuti di _tutte_ le origini private che sono state aggiunte alla rete CDN.
  
Tenere presente che maggiore è il numero di origini, maggiore è l'impatto sul tempo impiegato dal servizio CDN per l'elaborazione delle richieste. Si consiglia di limitare il più possibile il numero di origini.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Scegliere se ogni origine deve essere pubblica o privata

Quando si identifica un'origine, è necessario specificare se deve essere reso _pubblico_ o _privato_. L'accesso alle risorse della rete CDN nelle origini pubbliche è anonimo e il contenuto della rete CDN in origine privata è protetto da token generati dinamicamente per una maggiore sicurezza. Indipendentemente dall'opzione scelta, Microsoft esegue tutte le operazioni di sollevamento dei carichi pesanti quando si tratta di amministrazione della rete CDN stessa. Inoltre, è possibile modificare la propria mente in un secondo momento, dopo aver configurato la rete CDN e aver individuato le origini.

Entrambe le opzioni pubblico e privato offrono guadagni di prestazioni simili, ma ognuno ha attributi e vantaggi univoci.

Le origini **pubbliche** all'interno della rete CDN di Office 365 sono accessibili in modo anonimo e le risorse ospitate possono essere accessibili da tutti gli utenti che hanno l'URL del cespite. Dal momento che l'accesso al contenuto in origini pubbliche è anonimo, è consigliabile usarle solo per memorizzare nella cache contenuti generici non riservati, ad esempio file JavaScript, script, icone e immagini.

Le origini **private** all'interno della rete CDN di Office 365 offrono accesso privato ai contenuti degli utenti, ad esempio raccolte documenti di SharePoint Online, siti e immagini proprietarie. L'accesso al contenuto in origini private è protetto da token generati dinamicamente, in modo che sia possibile accedervi solo dagli utenti che dispongono delle autorizzazioni per la raccolta documenti originale o il percorso di archiviazione. L'origine privata nella rete CDN di Office 365 può essere utilizzata solo per il contenuto di SharePoint Online ed è possibile accedere solo alle risorse in origine privata tramite il reindirizzamento dal tenant di SharePoint Online.

Per ulteriori informazioni, vedere come l'accesso della rete CDN ai cespiti in un'origine privata funziona [utilizzando risorse in origine privata](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Attributi e vantaggi dell'hosting di risorse in origini pubbliche
  
+ Le risorse esposte in un'origine pubblica sono accessibili da tutti in modo anonimo.
    > [!IMPORTANT]
    > Non è consigliabile inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.
+ Se si rimuove una risorsa da un'origine pubblica, il cespite potrebbe continuare a essere disponibile per un massimo di 30 giorni dalla cache. Tuttavia, verranno invalidati i collegamenti al cespite nella rete CDN entro 15 minuti.
+ Quando si ospitano fogli di stile (file CSS) in un'origine pubblica, è possibile utilizzare i percorsi e gli URI relativi all'interno del codice. Questo significa che è possibile fare riferimento alla posizione delle immagini di sfondo e di altri oggetti rispetto alla posizione del cespite che lo chiama.
+ Anche se è possibile eseguire il codice rigido di un URL di origine pubblica, questo non è consigliato. Il motivo è che se l'accesso alla rete CDN non è disponibile, l'URL non si risolverà automaticamente nell'organizzazione in SharePoint Online e potrebbe causare collegamenti interrotti e altri errori.
+ I tipi di file predefiniti inclusi per le origini pubbliche sono. CSS,. EOT,. gif,. ico,. jpeg,. jpg,. js,. map,. png,. svg,. ttf,. WOFF e. woff2. È possibile specificare ulteriori tipi di file.
+ È possibile configurare un criterio per escludere le risorse che sono state identificate dalle classificazioni dei siti specificate. Ad esempio, è possibile scegliere di escludere tutte le risorse contrassegnate come "riservate" o "limitate" anche se si tratta di un tipo di file consentito e che si trovano in un'origine pubblica.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Attributi e vantaggi dell'hosting di risorse in origini private

+ L'origine privata può essere utilizzata solo per le risorse di SharePoint Online.
+ Gli utenti possono accedere alle risorse solo da un'origine privata se dispongono delle autorizzazioni per accedere al contenitore. L'accesso anonimo a tali risorse è impedito.
+ Le risorse in origine privata devono essere denominate dal tenant di SharePoint Online. L'accesso diretto alle risorse della rete CDN privata non funziona.
+ Se si rimuove una risorsa dall'origine privata, il bene può continuare a essere disponibile per un massimo di un'ora dalla cache; Tuttavia, verranno invalidati i collegamenti al cespite nella rete CDN entro 15 minuti dalla rimozione del cespite.
+ I tipi di file predefiniti inclusi per le origini private sono. gif,. ico,. jpeg,. jpg,. js e. png. È possibile specificare ulteriori tipi di file.
+ Analogamente alle origini pubbliche, è possibile configurare un criterio per escludere le risorse che sono state identificate dalle classificazioni dei siti specificate anche se si utilizzano caratteri jolly per includere tutte le risorse all'interno di una cartella o di una raccolta documenti.

Per ulteriori informazioni sui motivi per utilizzare la rete CDN di Office 365, i concetti generali di CDN e altre reti CDN di Microsoft che è possibile utilizzare con il tenant di Office 365, vedere [Content Delivery Networks](content-delivery-networks.md).

### <a name="default-cdn-origins"></a>Origini della rete CDN predefinite

Se non si specifica altrimenti, Office 365 configura alcune origini predefinite quando si Abilita la rete CDN di Office 365. Se inizialmente si sceglie di non eseguire il provisioning, è possibile aggiungere queste origini dopo aver completato l'installazione. A meno che non si comprendano le conseguenze della possibilità di ignorare la configurazione delle origini predefinite e che si disponga di un motivo specifico, è consigliabile consentirne la creazione quando si Abilita la rete CDN.
  
Origini private CDN predefinite:
  
+ \*/userphoto.aspx
+ \*/siteassets

Origini di CDN pubbliche predefinite:
  
+ \*/masterpage
+ \*raccolta/Style
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ è un'origine pubblica predefinita aggiunta al servizio CDN di Office 365 nel dicembre 2017. Questa origine deve essere presente nell'ordine in cui le soluzioni di SharePoint Framework nella rete CDN funzionino. Se è stata abilitata la rete CDN di Office 365 prima del dicembre 2017 o se è stata ignorata la configurazione delle origini predefinite quando è stata abilitata la rete CDN, è possibile aggiungere manualmente questa origine. Per ulteriori informazioni, vedere [la Web part sul lato client o la soluzione di SharePoint Framework non funziona](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Impostare e configurare la rete CDN di Office 365 tramite SharePoint Online Management Shell

Le procedure descritte in questa sezione richiedono l'utilizzo di SharePoint Online Management Shell per la connessione a SharePoint Online. Per istruzioni, vedere [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

Completare questa procedura per impostare e configurare la rete CDN per ospitare le risorse in SharePoint Online tramite SharePoint Online Management Shell.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Abilitazione dell'organizzazione all'utilizzo della rete CDN di Office 365

Prima di apportare modifiche alle impostazioni della rete CDN del tenant, è necessario recuperare lo stato corrente della configurazione della rete CDN privata nel tenant di Office 365. Connettersi al tenant tramite SharePoint Online Management Shell:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

A questo punto, utilizzare il cmdlet **Get-SPOTenantCdnEnabled** per recuperare le impostazioni di stato della rete CDN dal tenant:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Lo stato della rete CDN per l'oggetto CdnType specificato verrà restituito allo schermo.

Utilizzare il cmdlet **set-SPOTenantCdnEnabled** per consentire all'organizzazione di utilizzare la rete CDN di Office 365. È possibile consentire all'organizzazione di utilizzare origini pubbliche, origini private o entrambe contemporaneamente. È inoltre possibile configurare la rete CDN per ignorare la configurazione delle origini predefinite quando viene abilitata. È sempre possibile aggiungere queste origini in un secondo momento, come descritto in questo argomento.
  
In Windows PowerShell per SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Ad esempio, per consentire all'organizzazione di utilizzare origini pubbliche e private, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Per consentire all'organizzazione di utilizzare origini sia pubbliche che private, ma non impostare le origini predefinite, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Per informazioni sulle origini di cui è possibile eseguire il provisioning per impostazione predefinita, vedere origini della rete [CDN predefinite](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) quando si Abilita la rete CDN di Office 365 e l'impatto potenziale di ignorare la configurazione delle origini predefinite.

Per consentire all'organizzazione di utilizzare le origini pubbliche, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Per ulteriori informazioni su questo cmdlet, vedere [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Modificare l'elenco dei tipi di file da includere nella rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si definiscono i tipi di file utilizzando il cmdlet **set-SPOTenantCdnPolicy** , si sovrascrive l'elenco attualmente definito. Se si desidera aggiungere ulteriori tipi di file all'elenco, utilizzare il cmdlet First per scoprire quali tipi di file sono già consentiti e includerli nell'elenco insieme a quelli nuovi.
  
Utilizzare il cmdlet **set-SPOTenantCdnPolicy** per definire i tipi di file statici che possono essere ospitati da origini pubbliche e private nella rete CDN. Per impostazione predefinita, sono consentiti tipi di attività comuni, ad esempio CSS, gif, jpg e js.

In Windows PowerShell per SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Ad esempio, per abilitare la rete CDN per ospitare i file. CSS e. png, è necessario immettere il comando:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Per sapere quali tipi di file sono attualmente consentiti dalla rete CDN, utilizzare il cmdlet **Get-SPOTenantCdnPolicies** :

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Per ulteriori informazioni su questi cmdlet, vedere [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) e [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Modificare l'elenco di classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si escludono le classificazioni dei siti utilizzando il cmdlet **set-SPOTenantCdnPolicy** , si sovrascrive l'elenco attualmente definito. Se si desidera escludere altre classificazioni dei siti, utilizzare il cmdlet First per scoprire quali classificazioni sono già state escluse e quindi aggiungerle insieme a quelle nuove.

Utilizzare il cmdlet **set-SPOTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili tramite la rete CDN. Per impostazione predefinita, non sono escluse le classificazioni dei siti.

In Windows PowerShell per SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Per sapere quali classificazioni dei siti sono attualmente limitate, utilizzare il cmdlet **Get-SPOTenantCdnPolicies** :

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Le proprietà che verranno restituite sono _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ e _ExcludeIfNoScriptDisabled_.

La proprietà _IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno servite dalla rete CDN.

> [!NOTE]
> Le estensioni di file predefinite sono diverse tra pubblico e privato.

La proprietà _ExcludeRestrictedSiteClassifications_ contiene le classificazioni del sito che si desidera escludere dalla rete CDN. Ad esempio, è possibile escludere i siti contrassegnati come **riservati** in modo che il contenuto proveniente da siti con tale classificazione applicato non venga servito dalla rete CDN.

La proprietà _ExcludeIfNoScriptDisabled_ esclude il contenuto dalla rete CDN in base alle impostazioni degli attributi _noscript_ a livello di sito. Per impostazione predefinita, l'attributo _noscript_ è impostato su **abilitato** per i siti _moderni_ e **disabilitato** per i siti _classici_ . Questo dipende dalle impostazioni del tenant.

Per ulteriori informazioni su questi cmdlet, vedere [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) e [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Aggiungere un'origine per le risorse

Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire un'origine. È possibile definire origini multiple. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint che contiene le risorse che si desidera ospitare dalla rete CDN.
  
> [!IMPORTANT]
> Non è consigliabile inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Il valore di _path_ è il percorso relativo alla raccolta o alla cartella che contiene le risorse. È possibile utilizzare i caratteri jolly oltre ai percorsi relativi. Origins supporta i caratteri jolly anteposti all'URL. In questo modo è possibile creare origini che si estendono su più siti. Ad esempio, per includere tutti i cespiti nella cartella masterpages per tutti i siti come origine pubblica all'interno della rete CDN, digitare il comando seguente:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Il modificatore di caratteri jolly * **/** può essere utilizzato solo all'inizio del percorso e deve corrispondere a tutti i segmenti di URL sotto l'URL specificato.
+ Il percorso può puntare a una raccolta documenti, una cartella o un sito. Ad esempio, il percorso _*/site1_ corrisponderà a tutte le raccolte documenti del sito.

È possibile aggiungere un'origine con un percorso relativo specifico. Non è possibile aggiungere un'origine utilizzando il percorso completo.

In questo esempio viene aggiunta un'origine privata della raccolta siteassets in un sito specifico:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In questo esempio viene aggiunta un'origine privata della cartella _folder1_ nella raccolta di risorse del sito dell'insieme di siti:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Se è presente uno spazio nel percorso, è possibile racchiuderlo tra virgolette doppie o sostituire lo spazio con la codifica URL %20. Negli esempi riportati di seguito viene aggiunta un'origine privata della cartella _Folder 1_ nella raccolta di risorse del sito dell'insieme di siti:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

> [!NOTE]
> In origine privata, le risorse condivise da un'origine devono avere una versione principale pubblicata prima che sia possibile accedervi dalla rete CDN.
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione all'interno del datacenter. Questo può richiedere fino a 15 minuti.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Esempio: configurare un'origine pubblica per le pagine master e per la libreria di stili per SharePoint Online

In genere, queste origini sono configurate per l'utente per impostazione predefinita quando si Abilita la rete CDN di Office 365. Tuttavia, se si desidera abilitarli manualmente, attenersi alla seguente procedura.
  
+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la raccolta di stili come origine pubblica.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire le pagine master come origine pubblica.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

Dopo aver eseguito il comando, il sistema sincronizza la configurazione all'interno del datacenter. Questo può richiedere fino a 15 minuti.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Esempio: configurare un'origine privata per le risorse del sito, le pagine del sito e le immagini di pubblicazione per SharePoint Online

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella asset del sito come origine privata.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella pagine del sito come origine privata.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle immagini di pubblicazione come origine privata.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

Dopo aver eseguito il comando, il sistema sincronizza la configurazione all'interno del datacenter. Questo può richiedere fino a 15 minuti.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Esempio: configurare un'origine privata per una raccolta siti per SharePoint Online

Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire una raccolta siti come origine privata. Ad esempio:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione all'interno del datacenter. È possibile che venga visualizzato un messaggio di _configurazione in sospeso_ che è previsto quando il tenant di SharePoint Online si connette al servizio CDN. Questo può richiedere fino a 15 minuti.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Gestire la rete CDN di Office 365

Dopo aver configurato la rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle modifiche apportate alle esigenze, come descritto in questa sezione.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Aggiungere, aggiornare o rimuovere risorse dalla rete CDN di Office 365

Dopo aver completato la procedura di installazione, è possibile aggiungere nuove risorse e aggiornare o rimuovere le risorse esistenti ogni volta che si desidera. È sufficiente apportare le modifiche apportate alle risorse nella cartella o nella raccolta di SharePoint identificate come origine. Se si aggiunge un nuovo asset, è possibile utilizzarlo immediatamente tramite la rete CDN. Tuttavia, se si aggiorna la risorsa, saranno necessari fino a 15 minuti affinché la nuova copia venga propagata e diventi disponibile nella rete CDN.
  
Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-SPOTenantCdnOrigins** . Per informazioni sull'utilizzo di questo cmdlet, vedere [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Rimuovere un'origine dalla rete CDN di Office 365

È possibile rimuovere l'accesso a una cartella o a una raccolta di SharePoint identificata come origine. A tale scopo, utilizzare il cmdlet **Remove-SPOTenantCdnOrigin** .

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Per informazioni sull'utilizzo di questo cmdlet, vedere [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificare un'origine nella rete CDN di Office 365

Non è possibile modificare un'origine creata. Rimuovere invece l'origine e quindi aggiungerne una nuova. Per ulteriori informazioni, vedere [per rimuovere un'origine dalla rete CDN di Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) e [per aggiungere un'origine per le risorse](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Utilizzare il cmdlet **set-SPOTenantCdnEnabled** per disabilitare la rete CDN per l'organizzazione. Se sono abilitate sia le origini pubbliche che quelle private per la rete CDN, è necessario eseguire il cmdlet due volte come illustrato negli esempi riportati di seguito.
  
Per disabilitare l'utilizzo delle origini pubbliche nella rete CDN, immettere il seguente comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Per disabilitare l'utilizzo delle origini private nella rete CDN, immettere il seguente comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Per ulteriori informazioni su questo cmdlet, vedere [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Impostare e configurare la rete CDN di Office 365 mediante l'utilizzo di PowerShell PnP

Le procedure descritte in questa sezione richiedono l'utilizzo di PowerShell PnP per la connessione a SharePoint Online. Per istruzioni, vedere [Guida introduttiva a PowerShell PNP](https://github.com/SharePoint/PnP-PowerShell#getting-started).

Completare questa procedura per impostare e configurare la rete CDN per ospitare le risorse in SharePoint Online tramite la configurazione di PowerShell PnP.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Abilitazione dell'organizzazione all'utilizzo della rete CDN di Office 365

Prima di apportare modifiche alle impostazioni della rete CDN del tenant, è necessario recuperare lo stato corrente della configurazione della rete CDN privata nel tenant di Office 365. Connettersi al tenant utilizzando PowerShell PnP:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

A questo punto, utilizzare il cmdlet **Get-PnPTenantCdnEnabled** per recuperare le impostazioni di stato della rete CDN dal tenant:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Lo stato della rete CDN per l'oggetto CdnType specificato verrà restituito allo schermo.

Utilizzare il cmdlet **set-PnPTenantCdnEnabled** per consentire all'organizzazione di utilizzare la rete CDN di Office 365. È possibile consentire all'organizzazione di utilizzare origini pubbliche, origini private o entrambe contemporaneamente. È inoltre possibile configurare la rete CDN per ignorare la configurazione delle origini predefinite quando viene abilitata. È sempre possibile aggiungere queste origini in un secondo momento, come descritto in questo argomento.
  
In PowerShell PnP:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Ad esempio, per consentire all'organizzazione di utilizzare origini pubbliche e private, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Per consentire all'organizzazione di utilizzare origini sia pubbliche che private, ma non impostare le origini predefinite, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Per informazioni sulle origini di cui è possibile eseguire il provisioning per impostazione predefinita, vedere origini della rete [CDN predefinite](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) quando si Abilita la rete CDN di Office 365 e l'impatto potenziale di ignorare la configurazione delle origini predefinite.

Per consentire all'organizzazione di utilizzare le origini pubbliche, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Per ulteriori informazioni su questo cmdlet, vedere [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Modificare l'elenco dei tipi di file da includere nella rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si definiscono i tipi di file utilizzando il cmdlet **set-PnPTenantCdnPolicy** , si sovrascrive l'elenco attualmente definito. Se si desidera aggiungere ulteriori tipi di file all'elenco, utilizzare il cmdlet First per scoprire quali tipi di file sono già consentiti e includerli nell'elenco insieme a quelli nuovi.
  
Utilizzare il cmdlet **set-PnPTenantCdnPolicy** per definire i tipi di file statici che possono essere ospitati da origini pubbliche e private nella rete CDN. Per impostazione predefinita, sono consentiti tipi di attività comuni, ad esempio CSS, gif, jpg e js.

In PowerShell PnP:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Ad esempio, per abilitare la rete CDN per ospitare i file. CSS e. png, è necessario immettere il comando:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Per sapere quali tipi di file sono attualmente consentiti dalla rete CDN, utilizzare il cmdlet **Get-PnPTenantCdnPolicies** :

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Per ulteriori informazioni su questi cmdlet, vedere [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Modificare l'elenco di classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si escludono le classificazioni dei siti utilizzando il cmdlet **set-PnPTenantCdnPolicy** , si sovrascrive l'elenco attualmente definito. Se si desidera escludere altre classificazioni dei siti, utilizzare il cmdlet First per scoprire quali classificazioni sono già state escluse e quindi aggiungerle insieme a quelle nuove.

Utilizzare il cmdlet **set-PnPTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili tramite la rete CDN. Per impostazione predefinita, non sono escluse le classificazioni dei siti.

In PowerShell PnP:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Per sapere quali classificazioni dei siti sono attualmente limitate, utilizzare il cmdlet **Get-PnPTenantCdnPolicies** :

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Le proprietà che verranno restituite sono _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ e _ExcludeIfNoScriptDisabled_.

La proprietà _IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno servite dalla rete CDN.

> [!NOTE]
> Le estensioni di file predefinite sono diverse tra pubblico e privato.

La proprietà _ExcludeRestrictedSiteClassifications_ contiene le classificazioni del sito che si desidera escludere dalla rete CDN. Ad esempio, è possibile escludere i siti contrassegnati come **riservati** in modo che il contenuto proveniente da siti con tale classificazione applicato non venga servito dalla rete CDN.

La proprietà _ExcludeIfNoScriptDisabled_ esclude il contenuto dalla rete CDN in base alle impostazioni degli attributi _noscript_ a livello di sito. Per impostazione predefinita, l'attributo _noscript_ è impostato su **abilitato** per i siti _moderni_ e **disabilitato** per i siti _classici_ . Questo dipende dalle impostazioni del tenant.

Per ulteriori informazioni su questi cmdlet, vedere [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Aggiungere un'origine per le risorse

Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire un'origine. È possibile definire origini multiple. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint che contiene le risorse che si desidera ospitare dalla rete CDN.
  
> [!IMPORTANT]
> Non è consigliabile inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Il valore di _path_ è il percorso relativo alla raccolta o alla cartella che contiene le risorse. È possibile utilizzare i caratteri jolly oltre ai percorsi relativi. Origins supporta i caratteri jolly anteposti all'URL. In questo modo è possibile creare origini che si estendono su più siti. Ad esempio, per includere tutti i cespiti nella cartella masterpages per tutti i siti come origine pubblica all'interno della rete CDN, digitare il comando seguente:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Il modificatore di caratteri jolly * **/** può essere utilizzato solo all'inizio del percorso e deve corrispondere a tutti i segmenti di URL sotto l'URL specificato.
+ Il percorso può puntare a una raccolta documenti, una cartella o un sito. Ad esempio, il percorso _*/site1_ corrisponderà a tutte le raccolte documenti del sito.

È possibile aggiungere un'origine con un percorso relativo specifico. Non è possibile aggiungere un'origine utilizzando il percorso completo.

In questo esempio viene aggiunta un'origine privata della raccolta di risorse del sito in un sito specifico:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In questo esempio viene aggiunta un'origine privata della cartella _folder1_ nella raccolta di risorse del sito dell'insieme di siti:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Se è presente uno spazio nel percorso, è possibile racchiuderlo tra virgolette doppie o sostituire lo spazio con la codifica URL %20. Negli esempi riportati di seguito viene aggiunta un'origine privata della cartella _Folder 1_ nella raccolta di risorse del sito dell'insieme di siti:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> In origine privata, le risorse condivise da un'origine devono avere una versione principale pubblicata prima che sia possibile accedervi dalla rete CDN.
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione all'interno del datacenter. Questo può richiedere fino a 15 minuti.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Esempio: configurare un'origine pubblica per le pagine master e per la libreria di stili per SharePoint Online

In genere, queste origini sono configurate per l'utente per impostazione predefinita quando si Abilita la rete CDN di Office 365. Tuttavia, se si desidera abilitarli manualmente, attenersi alla seguente procedura.
  
+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la raccolta di stili come origine pubblica.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire le pagine master come origine pubblica.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Dopo aver eseguito il comando, il sistema sincronizza la configurazione all'interno del datacenter. Questo può richiedere fino a 15 minuti.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Esempio: configurare un'origine privata per le risorse del sito, le pagine del sito e le immagini di pubblicazione per SharePoint Online

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella asset del sito come origine privata.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella pagine del sito come origine privata.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle immagini di pubblicazione come origine privata.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Dopo aver eseguito il comando, il sistema sincronizza la configurazione all'interno del datacenter. Questo può richiedere fino a 15 minuti.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Esempio: configurare un'origine privata per una raccolta siti per SharePoint Online

Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire una raccolta siti come origine privata. Ad esempio:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione all'interno del datacenter. È possibile che venga visualizzato un messaggio di _configurazione in sospeso_ che è previsto quando il tenant di SharePoint Online si connette al servizio CDN. Questo può richiedere fino a 15 minuti.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Gestire la rete CDN di Office 365

Dopo aver configurato la rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle modifiche apportate alle esigenze, come descritto in questa sezione.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Aggiungere, aggiornare o rimuovere risorse dalla rete CDN di Office 365

Dopo aver completato la procedura di installazione, è possibile aggiungere nuove risorse e aggiornare o rimuovere le risorse esistenti ogni volta che si desidera. È sufficiente apportare le modifiche apportate alle risorse nella cartella o nella raccolta di SharePoint identificate come origine. Se si aggiunge un nuovo asset, è possibile utilizzarlo immediatamente tramite la rete CDN. Tuttavia, se si aggiorna la risorsa, saranno necessari fino a 15 minuti affinché la nuova copia venga propagata e diventi disponibile nella rete CDN.
  
Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-PnPTenantCdnOrigin** . Per informazioni sull'utilizzo di questo cmdlet, vedere [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Rimuovere un'origine dalla rete CDN di Office 365

È possibile rimuovere l'accesso a una cartella o a una raccolta di SharePoint identificata come origine. A tale scopo, utilizzare il cmdlet **Remove-PnPTenantCdnOrigin** .

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Per informazioni sull'utilizzo di questo cmdlet, vedere [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificare un'origine nella rete CDN di Office 365

Non è possibile modificare un'origine creata. Rimuovere invece l'origine e quindi aggiungerne una nuova. Per ulteriori informazioni, vedere [per rimuovere un'origine dalla rete CDN di Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) e [per aggiungere un'origine per le risorse](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Utilizzare il cmdlet **set-PnPTenantCdnEnabled** per disabilitare la rete CDN per l'organizzazione. Se sono abilitate sia le origini pubbliche che quelle private per la rete CDN, è necessario eseguire il cmdlet due volte come illustrato negli esempi riportati di seguito.
  
Per disabilitare l'utilizzo delle origini pubbliche nella rete CDN, immettere il seguente comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Per disabilitare l'utilizzo delle origini private nella rete CDN, immettere il seguente comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Per ulteriori informazioni su questo cmdlet, vedere [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Impostare e configurare la rete CDN di Office 365 tramite la CLI di Office 365

Le procedure descritte in questa sezione richiedono l'installazione di [Office 365 CLI](https://aka.ms/o365cli). Successivamente, connettersi al tenant di Office 365 utilizzando il comando [login](https://pnp.github.io/office365-cli/cmd/login/) .

Completare questa procedura per impostare e configurare la rete CDN per ospitare le risorse in SharePoint Online utilizzando la CLI di Office 365.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-the-office-365-cdn"></a>Abilitare la rete CDN di Office 365

È possibile gestire lo stato della rete CDN di Office 365 nel tenant usando il comando [set CDN di SPO](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) .

Per abilitare la rete CDN pubblica di Office 365 nel tenant, eseguire le operazioni seguenti:

```sh
spo cdn set --type Public --enabled true
```

Per abilitare la rete CDN di Office 365 SharePoint, eseguire le operazioni seguenti:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Visualizzare lo stato corrente della rete CDN di Office 365

Per verificare se il tipo specifico di rete CDN di Office 365 è abilitato o disabilitato, utilizzare il comando per ottenere la rete [CDN](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) .

Per verificare se la rete CDN pubblica di Office 365 è abilitata, eseguire:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Visualizzare le origini della rete CDN di Office 365

Per visualizzare l'origine della rete CDN pubblica di Office 365 correntemente configurata, eseguire:

```sh
spo cdn origin list --type Public
```

Per informazioni sulle origini di cui è possibile eseguire il provisioning per impostazione predefinita, vedere origini della rete [CDN predefinite](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) quando si Abilita la rete CDN di Office 365.

### <a name="add-an-office-365-cdn-origin"></a>Aggiungere un'origine della rete CDN di Office 365

> [!IMPORTANT]
> Non è consigliabile inserire mai risorse considerate sensibili all'organizzazione in una raccolta documenti di SharePoint configurata come origine pubblica.

Utilizzare il comando [Aggiungi origine](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) della rete CDN per definire un'origine della rete CDN. È possibile definire origini multiple. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint che contiene le risorse che si desidera ospitare dalla rete CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Dove `path` è il percorso relativo alla cartella che contiene le risorse. È possibile utilizzare i caratteri jolly oltre ai percorsi relativi.

Per includere tutte le risorse nella **raccolta pagine master** di tutti i siti come origine pubblica, eseguire le operazioni seguenti:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Per configurare un'origine privata per una raccolta siti specifica, eseguire:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Dopo aver aggiunto un'origine CDN, potrebbero essere necessari fino a 15 minuti affinché sia possibile recuperare i file tramite il servizio CDN. È possibile verificare se l'origine specifica è già stata abilitata utilizzando il comando dell' [elenco di origine](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) della rete CDN.

### <a name="remove-an-office-365-cdn-origin"></a>Rimozione di un'origine CDN di Office 365

Utilizzare il comando [Rimuovi origine rete CDN](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) per rimuovere un'origine CDN per il tipo di rete CDN specificato.

Per rimuovere un'origine pubblica dalla configurazione della rete CDN, eseguire le operazioni seguenti:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> La rimozione di un'origine CDN non influisce sui file archiviati in una raccolta documenti corrispondente all'origine. Se tali risorse sono state referenziate utilizzando l'URL di SharePoint, SharePoint passerà automaticamente all'URL originale che punta alla raccolta documenti. Se, tuttavia, le risorse sono state referenziate con un URL pubblico della rete CDN, la rimozione dell'Origine interromperà il collegamento e sarà necessario modificarle manualmente.

### <a name="modify-an-office-365-cdn-origin"></a>Modificare un'origine della rete CDN di Office 365

Non è possibile modificare un'origine CDN esistente. Al contrario, è necessario rimuovere l'origine della rete CDN precedentemente definita usando il `spo cdn origin remove` comando e aggiungerne una nuova utilizzando il `spo cdn origin add` comando.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Modificare i tipi di file da includere nella rete CDN di Office 365

Per impostazione predefinita, i seguenti tipi di file sono inclusi nella rete CDN: _. CSS,. EOT,. gif,. ico,. jpeg,. jpg,. js,. map,. png,. svg,. ttf,. WOFF e. woff2_. Se è necessario includere altri tipi di file nella rete CDN, è possibile modificare la configurazione della rete CDN utilizzando il comando [set di criteri](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) della rete CDN.

> [!NOTE]
> Quando si modifica l'elenco dei tipi di file, è necessario sovrascrivere l'elenco correntemente definito. Se si desidera includere altri tipi di file, utilizzare innanzitutto il comando dell' [elenco dei criteri](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) della rete CDN per individuare i tipi di file attualmente configurati.

Per aggiungere il tipo di file _JSON_ all'elenco predefinito dei tipi di file inclusi nella rete CDN pubblica, eseguire le operazioni seguenti:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Modificare l'elenco di classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365

Utilizzare il comando [set di criteri](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) della rete CDN per escludere le classificazioni dei siti che non si desidera rendere disponibili tramite la rete CDN. Per impostazione predefinita, non sono escluse le classificazioni dei siti.

> [!NOTE]
> Quando si modifica l'elenco di classificazioni dei siti esclusi, è necessario sovrascrivere l'elenco attualmente definito. Se si desidera escludere altre classificazioni, utilizzare innanzitutto il comando dell' [elenco dei criteri](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) della rete CDN per scoprire quali classificazioni sono attualmente configurate.

Per escludere i siti classificati come _le_ dalla rete CDN pubblica, eseguire

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Per disabilitare la rete CDN di Office 365 `spo cdn set` , utilizzare il comando, ad esempio:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Utilizzo delle risorse della rete CDN

Dopo aver abilitato la rete CDN e le origini e i criteri configurati, è possibile iniziare a utilizzare le risorse della rete CDN.

In questa sezione vengono fornite informazioni su come utilizzare gli URL della rete CDN nelle pagine e nel contenuto di SharePoint in modo che SharePoint reindirizza le richieste di risorse in origine pubblica e privata alla rete CDN.

+ [Aggiornamento di collegamenti alle risorse della rete CDN](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Utilizzo delle risorse in origini pubbliche](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Utilizzo delle risorse in origine privata](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Per informazioni su come utilizzare la rete CDN per l'hosting di Web part sul lato client, vedere l'argomento [host your web part sul lato client da Office 365 CDN (Hello World Part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).

> [!NOTE]
> Se si aggiunge la cartella _ClientSideAssets_ all'elenco delle origini della rete CDN **privata** , non verrà eseguito il rendering delle web part personalizzate di CDN ospitate. I file utilizzati dalle web part di SPFX possono utilizzare solo la rete CDN pubblica e la cartella ClientSideAssets è un'origine predefinita per la CDN pubblica. 

### <a name="updating-links-to-cdn-assets"></a>Aggiornamento di collegamenti alle risorse della rete CDN

Per utilizzare le risorse aggiunte a un'origine, è sufficiente aggiornare i collegamenti al file originale con il percorso del file nell'origine.

+ Modificare la pagina o il contenuto che contiene collegamenti a risorse che sono state aggiunte a un'origine. È inoltre possibile utilizzare uno dei numerosi metodi per cercare e sostituire globalmente i collegamenti tra un sito o una raccolta siti per l'aggiornamento, se si desidera aggiornare il collegamento a un determinato cespite ovunque venga visualizzato.
+ Per ogni collegamento a una risorsa di origine, sostituire il percorso con il percorso del file nell'origine della rete CDN. È possibile utilizzare i percorsi relativi.
+ Salvare la pagina o il contenuto.

Si consideri, ad esempio, l'immagine _/site/SiteAssets/images/image.png_, che è stata copiata nella cartella della raccolta documenti _/site/CDN_origins/public/_. Per utilizzare l'asset della rete CDN, sostituire il percorso originale nel percorso del file di immagine con il percorso dell'origine per rendere il nuovo URL _/site/CDN_origins/public/image.png_.

Se si desidera utilizzare l'URL completo del cespite anziché un percorso relativo, creare il collegamento in questo modo:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> In generale, non è necessario impostare come hardcoded gli URL direttamente nelle risorse della rete CDN. Tuttavia, è possibile creare manualmente gli URL per le risorse in pubblico Origins se necessario. Per ulteriori informazioni, vedere [hardcoded degli URL della rete CDN per le risorse pubbliche](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).

Per informazioni su come verificare che le risorse vengano servite dalla rete CDN, vedere [come si conferma che le risorse vengono servite dalla rete CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) nella sezione [risoluzione dei problemi relativi alla rete cdn di Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .

### <a name="using-assets-in-public-origins"></a>Utilizzo delle risorse in origini pubbliche

La **caratteristica di pubblicazione** in SharePoint Online riscrive automaticamente gli URL delle risorse archiviate nelle origini pubbliche nei rispettivi EQUIVALEnti CDN in modo che le risorse vengano servite dal servizio CDN invece che da SharePoint.

Se l'origine è in un sito in cui è abilitata la caratteristica di pubblicazione e gli asset che si desidera scaricare nella rete CDN sono presenti in una delle categorie seguenti, SharePoint riscriverà automaticamente gli URL per le risorse nell'origine, purché il cespite non sia stato escluso da un criterio CDN.

Di seguito è riportata una panoramica dei collegamenti che vengono automaticamente riscritti dalla caratteristica di pubblicazione di SharePoint:

+ URL IMG/LINK/CSS nella pagina di pubblicazione classica risposte HTML
  + Sono incluse le immagini aggiunte dagli autori all'interno del contenuto HTML di una pagina
+ Raccolta immagini presentazione WebPart URL di immagini
+ Campi immagine nei risultati dell'API REST di SPList (RenderListDataAsStream)
  + Utilizzare la nuova proprietà _ImageFieldsToTryRewriteToCdnUrls_ per fornire un elenco di campi separati da virgole
  + Supporta campi collegamento ipertestuale e campi PublishingImage
+ Copie trasformate di immagini di SharePoint

Nel diagramma seguente viene illustrato il flusso di lavoro quando SharePoint riceve una richiesta per una pagina contenente risorse provenienti da un'origine pubblica.

![Diagramma del flusso di lavoro: recupero delle risorse di Office 365 CDN da un'origine pubblica](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Flusso di lavoro: recupero delle risorse della rete CDN di Office 365 da un'origine pubblica")

> [!TIP]
> Se si desidera disabilitare la riscrittura automatica per URL specifici in una pagina, è possibile estrarre la pagina e aggiungere il parametro della stringa di query **? NoAutoReWrites = true** alla fine di ogni collegamento che si desidera disabilitare.

#### <a name="hardcoding-cdn-urls-for-public-assets"></a>Hardcoded degli URL della rete CDN per le risorse pubbliche

Se la caratteristica di _pubblicazione_ non è abilitata per un'origine pubblica o se la risorsa non è uno dei tipi di collegamento supportati dalla caratteristica di riscrittura automatica del servizio CDN, è possibile creare manualmente gli URL nel percorso CDN delle risorse e utilizzare tali URL nel contenuto.

> [!NOTE]
> Non è possibile impostare come hardcoded gli URL della rete CDN per le risorse in un'origine privata perché il token di accesso necessario che forma l'ultima sezione dell'URL viene generato al momento della richiesta della risorsa.

Per le risorse della rete CDN pubblica, il formato dell'URL avrà un aspetto analogo al seguente:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Sostituire **TenantHostName** con il nome del tenant. Esempio:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a>Utilizzo delle risorse in origine privata

Non è necessaria alcuna configurazione aggiuntiva per l'utilizzo di risorse in origine privata. SharePoint Online riscrive automaticamente gli URL per le risorse in origine privata in modo che le richieste per tali risorse vengano sempre servite dalla rete CDN. Non è possibile creare manualmente gli URL per le risorse della rete CDN in origine privata, poiché tali URL contengono token che devono essere generati automaticamente da SharePoint Online al momento della richiesta del cespite.

L'accesso alle risorse in origine privata è protetto da token generati dinamicamente in base alle autorizzazioni utente per l'origine, con gli avvertimenti descritti nelle sezioni seguenti. Gli utenti devono disporre almeno dell'accesso in **lettura** alle origini per la rete CDN per il rendering del contenuto.

Nel diagramma seguente viene illustrato il flusso di lavoro quando SharePoint riceve una richiesta per una pagina contenente risorse provenienti da un'origine privata.

![Diagramma del flusso di lavoro: recupero delle risorse della rete CDN di Office 365 da un'origine privata](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Flusso di lavoro: recupero delle risorse della rete CDN di Office 365 da un'origine privata")

#### <a name="token-based-authorization-in-private-origins"></a>Autorizzazione basata su token in origini private

L'accesso alle risorse in origine privata nella rete CDN di Office 365 è concesso dai token generati da SharePoint Online. Gli utenti che dispongono già dell'autorizzazione per l'accesso alla cartella o alla raccolta designata dall'origine vengono assegnati automaticamente i token che consentono all'utente di accedere al file in base al livello di autorizzazione. Questi token di accesso sono validi da 30 a 90 minuti dopo la loro generazione per impedire attacchi di riproduzione di token.

Dopo la generazione del token di accesso, SharePoint Online restituisce un URI personalizzato al client contenente due parametri di autorizzazione _eat_ (token di autorizzazione Edge) e _OAT_ (token di autorizzazione di origine). La struttura di ogni token è _<' data di scadenza nel formato tempo Epoch ' >__< >' firma sicura ' _. Ad esempio:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Tutti gli utenti in possesso del token possono accedere alla risorsa nella rete CDN. Tuttavia, gli URL che contengono questi token di accesso vengono condivisi solo su HTTPS, quindi, a meno che l'URL non venga condiviso in modo esplicito da un utente finale prima della scadenza del token, il bene non sarà accessibile agli utenti non autorizzati.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Le autorizzazioni a livello di elemento non sono supportate per le risorse in origine privata

È importante tenere presente che SharePoint Online non supporta le autorizzazioni a livello di elemento per le risorse in origine privata. Ad esempio, per un file in `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` cui gli utenti hanno accesso effettivo al file, date le condizioni seguenti:

|Utente  |Autorizzazioni  |Accesso efficace  |
|---------|---------|---------|
|Utente 1     |Ha accesso a Folder1         |Possibile accedere a image1.jpg dalla rete CDN         |
|Utente 2     |Non dispone dell'accesso a Folder1         |Non è possibile accedere image1.jpg dalla rete CDN         |
|Utente 3     |Non dispone dell'accesso a Folder1, ma viene concessa l'autorizzazione esplicita per l'accesso image1.jpg in SharePoint Online         |Possibile accedere alla image1.jpg di risorse direttamente da SharePoint Online, ma non dalla rete CDN         |
|Utente 4     |Ha accesso a Folder1, ma è stato negato in modo esplicito l'accesso ai image1.jpg in SharePoint Online         |Non è possibile accedere al cespite da SharePoint Online, ma è possibile accedere alla risorsa dalla rete CDN nonostante venga negato l'accesso al file in SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Risoluzione dei problemi relativi alla rete CDN di Office 365

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Come si conferma che le risorse vengono servite dalla rete CDN?

Dopo aver aggiunto collegamenti alle risorse della rete CDN a una pagina, è possibile verificare che il bene sia stato servito dalla rete CDN esplorando la pagina, facendo clic con il pulsante destro del mouse sull'immagine dopo aver eseguito il rendering e esaminando l'URL dell'immagine.

È inoltre possibile utilizzare gli strumenti di sviluppo del browser per visualizzare l'URL di ogni risorsa in una pagina o utilizzare uno strumento di traccia di rete di terze parti.

> [!NOTE]
> Se si utilizza uno strumento di rete, ad esempio Fiddler, per testare le risorse all'esterno del rendering del cespite da una pagina di SharePoint, è necessario aggiungere manualmente l'intestazione Referer "Referer: `https://yourdomain.sharepoint.com` " alla richiesta GET, in cui l'URL è l'URL radice del tenant di SharePoint Online.

Non è possibile testare gli URL della rete CDN direttamente in un Web browser perché è necessario disporre di un Referer proveniente da SharePoint Online. Tuttavia, se si aggiunge l'URL delle risorse della rete CDN a una pagina di SharePoint e quindi si apre la pagina in un browser, verrà visualizzata la risorsa della rete CDN di cui è stato eseguito il rendering nella pagina.

Per ulteriori informazioni sull'utilizzo degli strumenti di sviluppo nel browser Microsoft Edge, vedere [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).

Per guardare un breve video ospitato nei [modelli di sviluppo di SharePoint e nelle pratiche del canale YouTube](https://aka.ms/sppnp-videos) che dimostra come verificare che la rete CDN funzioni correttamente, vedere [verifying your CDN Usage and assicuration Optimal Network Connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Perché le risorse di una nuova origine non sono disponibili?
Le risorse in nuove origini non saranno immediatamente disponibili per l'utilizzo, poiché richiede tempo affinché la registrazione venga propagata attraverso la rete CDN e che le risorse vengano caricate dall'origine all'archiviazione CDN. Il tempo necessario per la disponibilità delle risorse nella rete CDN dipende dal numero di risorse e delle dimensioni dei file.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>La Web part sul lato client o la soluzione di SharePoint Framework non funziona

Quando si Abilita la rete CDN di Office 365 per le origini pubbliche, il servizio CDN crea automaticamente queste origini predefinite:

+ */MASTERPAGE
+ * LIBRERIA/STYLE
+ */CLIENTSIDEASSETS

Se l'origine */clientsideassets è mancante, le soluzioni di SharePoint Framework avranno esito negativo e non verranno generati messaggi di avviso o di errore. Questa origine potrebbe non essere presente perché la rete CDN è stata abilitata con il parametro _-NoDefaultOrigins_ impostato su **$true**oppure perché l'origine è stata eliminata manualmente.

È possibile controllare quali origini sono presenti con il seguente comando di PowerShell:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

In alternativa, è possibile verificare con Office 365 CLI:

``` powershell
spo cdn origin list
```

Per aggiungere l'origine in PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Per aggiungere l'origine nella CLI di Office 365:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Quali moduli di PowerShell e shell CLI è necessario utilizzare con la rete CDN di Office 365?

È possibile scegliere di utilizzare la rete CDN di Office 365 utilizzando il modulo di PowerShell di **SharePoint Online Management Shell** o **Office 365 CLI**.

+ [Guida introduttiva a SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Installazione di Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Vedere anche

[Reti per la distribuzione di contenuti](https://aka.ms/o365cdns)

[Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune)

[Serie di prestazioni di SharePoint-serie di video della rete CDN di Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
