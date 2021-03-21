---
title: Usare La rete per la distribuzione di contenuti (CDN) di Office 365 con SharePoint Online
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
description: Informazioni su come usare la rete CDN (Content Delivery Network) di Office 365 per velocizzare la distribuzione degli asset di SharePoint Online.
ms.openlocfilehash: 6b740fc1429613627e0597dc6ecf2e150c015989
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924817"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online

È possibile usare la rete per la distribuzione di contenuti di Office 365 predefinita per ospitare risorse statiche e migliorare le prestazioni delle pagine di SharePoint Online. La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza. Inoltre, la rete CDN di Office 365 usa il [protocollo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) per migliorare la compressione e il pipelining HTTP. Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

> [!NOTE]
> La rete CDN di Office 365 è disponibile solo per i tenant **nel** cloud di produzione (in tutto il mondo). I tenant nel cloud del governo degli Stati Uniti, della Cina e della Germania non supportano attualmente la rete CDN di Office 365.

La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità. In base al tipo di contenuto che si vuole ospitare nella rete per la distribuzione di contenuti di Office 365, è possibile aggiungere origini **pubbliche**, origini **private** o entrambi. Per ulteriori informazioni sulla differenza tra origini pubbliche e [private,](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) vedere Scegliere se ogni origine deve essere pubblica o privata.

![Diagramma concettuale della rete CDN di Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagramma concettuale della rete CDN di Office 365")

Se si ha già familiarità con il funzionamento delle reti CDN, è necessario eseguire solo alcuni passaggi per abilitare la rete CDN di Office 365 per il tenant. In questo argomento viene descritto come. Continua a leggere per informazioni su come iniziare a ospitare gli asset statici.

> [!TIP]
> Esistono altre reti CDN ospitate da Microsoft che possono essere usate con Office 365 per scenari di utilizzo specializzati, ma non sono descritte in questo argomento perché non rientrano nell'ambito della rete CDN di Office 365. Per ulteriori informazioni, vedere [Other Microsoft CDN](content-delivery-networks.md#other-microsoft-cdns).

 **Tornare a [Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](./network-planning-and-performance.md).**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Panoramica dell'utilizzo della rete CDN di Office 365 in SharePoint Online

Per configurare la rete CDN di Office 365 per l'organizzazione, eseguire la procedura di base seguente:

+ [Pianificare la distribuzione della rete CDN di Office 365](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Determinare quali asset statici si desidera ospitare nella rete CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).
  + [Determinare dove archiviare gli asset.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Questo percorso può essere un sito, una raccolta o una cartella di SharePoint ed è denominato _origine._
  + [Scegliere se ogni origine deve essere pubblica o privata.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) È possibile aggiungere più origini di tipi pubblici e privati.

+ Configurare la rete CDN utilizzando PowerShell o l'interfaccia della riga di comando di SharePoint Online

  + [Configurare e configurare la rete CDN tramite SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Configurare e configurare la rete CDN tramite PowerShell PnP](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Configurare e configurare la rete CDN tramite l'interfaccia della riga di comando di Office 365](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Al termine di questo passaggio, si avranno:

  + Abilitata la rete CDN per l'organizzazione.
  + Sono state aggiunte le origini, identificando ogni origine come pubblica o privata.

Al termine dell'installazione, è possibile gestire la rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) nel tempo:
  
+ Aggiunta, aggiornamento e rimozione di asset
+ Aggiunta e rimozione di origini
+ Configurazione dei criteri CDN
+ Se necessario, disabilitando la rete CDN

Infine, vedi [Uso delle risorse CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) per informazioni sull'accesso alle risorse CDN sia da origini pubbliche che private.

Per istruzioni sulla risoluzione dei problemi comuni, vedere Risoluzione dei problemi della rete CDN di [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Pianificare la distribuzione della rete CDN di Office 365

Prima di distribuire la rete CDN di Office 365 per il tenant di Office 365, è necessario considerare i fattori seguenti come parte del processo di pianificazione.

  + [Determinare quali asset statici si desidera ospitare nella rete CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Determinare dove archiviare gli asset](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Scegliere se ogni origine deve essere pubblica o privata](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Determinare quali asset statici si desidera ospitare nella rete CDN

In generale, le reti CDN sono più efficaci per ospitare asset _statici_ o asset che non cambiano molto spesso. Una buona regola generale è identificare i file che soddisfano alcune o tutte queste condizioni:

+ File statici incorporati in una pagina (ad esempio script e immagini) che possono avere un impatto incrementale significativo sui tempi di caricamento delle pagine
+ File di grandi dimensioni come file eseguibili e file di installazione
+ Librerie di risorse che supportano il codice sul lato client

Ad esempio, file di piccole dimensioni che vengono ripetutamente richiesti come immagini e script del sito possono migliorare in modo significativo le prestazioni di rendering del sito e ridurre in modo incrementale il carico sui siti di SharePoint Online quando vengono aggiunti a un'origine CDN. I file di dimensioni maggiori, ad esempio i file eseguibili di installazione, possono essere scaricati dalla rete CDN, con un impatto positivo sulle prestazioni e una conseguente riduzione del carico sul sito di SharePoint Online, anche se non vi si accede con la frequenza più frequente.

Il miglioramento delle prestazioni in base al file dipende da molti fattori, tra cui la prossimità del client all'endpoint CDN più vicino, le condizioni temporanee sulla rete locale e così via. Molti file statici sono piuttosto piccoli e possono essere scaricati da Office 365 in meno di un secondo. Tuttavia, una pagina Web può contenere molti file incorporati con un tempo di download cumulativo di diversi secondi. La pubblicazione di questi file dalla rete CDN può ridurre in modo significativo il tempo di caricamento complessivo delle pagine. Per un esempio, vedere Quali miglioramenti delle prestazioni offre una [rete CDN.](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Determinare dove archiviare gli asset

La rete CDN recupera gli asset da una posizione denominata _origine._ Un'origine può essere un sito di SharePoint, una raccolta documenti o una cartella accessibile da un URL. Si ha una grande flessibilità quando si specificano le origini per l'organizzazione. Ad esempio, puoi specificare più origini o una singola origine in cui vuoi inserire tutti gli asset della rete CDN. È possibile scegliere di avere origini pubbliche o private per l'organizzazione. La maggior parte delle organizzazioni sceglie di implementare una combinazione dei due.

È possibile creare un nuovo contenitore per le origini, ad esempio cartelle o raccolte documenti, e aggiungere i file che si desidera rendere disponibili dalla rete CDN. Si tratta di un buon approccio se si dispone di un set specifico di asset che si desidera essere disponibili dalla rete CDN e si desidera limitare il set di asset CDN solo a tali file nel contenitore.

È inoltre possibile configurare una raccolta siti, un sito, una raccolta o una cartella esistente come origine, in modo da rendere disponibili dalla rete CDN tutte le risorse idonee nel contenitore. Prima di aggiungere un contenitore esistente come origine, è importante assicurarsi di conoscerne il contenuto e le autorizzazioni, in modo da non esporre inavvertitamente le risorse agli utenti non autorizzati o agli accessi anonimi.

È possibile definire _criteri cdn_ per escludere il contenuto nelle origini dalla rete CDN. I criteri CDN escludono gli asset nelle origini pubbliche o private in base ad attributi quali il tipo di _file_ e la classificazione del sito e vengono applicati a tutte le origini di CdnType (private o pubbliche) specificate nel criterio. Se ad esempio si aggiunge un'origine privata costituita da un sito contenente più siti  secondari, è possibile definire un criterio per escludere i siti contrassegnati come Riservati in modo che il contenuto dei siti a cui è applicata tale classificazione non sia servito dalla rete CDN. Il criterio verrà applicato al contenuto _di_ tutte le origini private aggiunte alla rete CDN.
  
Tenere presente che maggiore è il numero di origini, maggiore sarà l'impatto sul tempo necessario al servizio CDN per elaborare le richieste. Ti consigliamo di limitare il più possibile il numero di origini.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Scegliere se ogni origine deve essere pubblica o privata

Quando si identifica un'origine, è necessario specificare se deve essere resa _pubblica_ o _privata._ L'accesso alle risorse CDN di origini pubbliche è anonimo e il contenuto della rete CDN in origini private è protetto da token generati dinamicamente per una maggiore sicurezza. Indipendentemente dall'opzione scelta, Microsoft fa tutto il lavoro pesante per l'utente quando si tratta di amministrazione della rete CDN stessa. Inoltre, puoi cambiare idea in un secondo momento, dopo aver configurato la rete CDN e identificato le origini.

Entrambe le opzioni pubbliche e private offrono prestazioni simili, ma ognuna ha attributi e vantaggi univoci.

**Le** origini pubbliche all'interno della rete CDN di Office 365 sono accessibili in modo anonimo e gli asset ospitati sono accessibili da chiunque abbia l'URL dell'asset. Dal momento che l'accesso al contenuto in origini pubbliche è anonimo, è consigliabile usarle solo per memorizzare nella cache contenuti generici non riservati, ad esempio file JavaScript, script, icone e immagini.

**Le** origini private all'interno della rete CDN di Office 365 forniscono l'accesso privato al contenuto degli utenti, ad esempio raccolte documenti, siti e immagini proprietarie di SharePoint Online. L'accesso al contenuto in origini private è protetto da token generati dinamicamente in modo che sia accessibile solo agli utenti con autorizzazioni per la raccolta documenti originale o il percorso di archiviazione. Le origini private nella rete CDN di Office 365 possono essere usate solo per il contenuto di SharePoint Online ed è possibile accedere solo alle risorse di origini private tramite il reindirizzamento dal tenant di SharePoint Online.

Per altre informazioni sul funzionamento dell'accesso della rete CDN alle risorse in un'origine privata, vedere [Utilizzo di risorse in origini private](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Attributi e vantaggi dell'hosting di asset in origini pubbliche
  
+ Gli asset esposti in un'origine pubblica sono accessibili da tutti in modo anonimo.
    > [!IMPORTANT]
    > Non inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.
+ Se si rimuove un asset da un'origine pubblica, l'asset potrebbe continuare a essere disponibile per un massimo di 30 giorni dalla cache. Tuttavia, verranno invalidati i collegamenti all'asset nella rete CDN entro 15 minuti.
+ Quando si ospitano fogli di stile (file CSS) in un'origine pubblica, è possibile utilizzare percorsi relativi e URI all'interno del codice. Ciò significa che puoi fare riferimento alla posizione delle immagini di sfondo e di altri oggetti rispetto alla posizione dell'asset che la chiama.
+ Sebbene sia possibile creare l'URL di un'origine pubblica, è consigliabile procedere con cautela e assicurarsi di utilizzare la proprietà di contesto della pagina e seguire le indicazioni per eseguire questa operazione. Il motivo è che se l'accesso alla rete CDN diventa non disponibile, l'URL non verrà risolto automaticamente nell'organizzazione in SharePoint Online e potrebbe causare collegamenti interrotti e altri errori. Anche l'URL è soggetto a modifiche, perché non deve essere solo hard coded al valore corrente.
+ I tipi di file predefiniti inclusi per le origini pubbliche sono .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2. È possibile specificare tipi di file aggiuntivi.
+ È possibile configurare un criterio per escludere gli asset identificati dalle classificazioni del sito specificate. Ad esempio, è possibile scegliere di escludere tutti gli asset contrassegnati come "riservati" o "limitati" anche se sono un tipo di file consentito e si trovano in un'origine pubblica.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Attributi e vantaggi dell'hosting di asset in origini private

+ Le origini private possono essere utilizzate solo per gli asset di SharePoint Online.
+ Gli utenti possono accedere agli asset da un'origine privata solo se dispongono delle autorizzazioni per accedere al contenitore. L'accesso anonimo a questi asset non è consentito.
+ Gli asset di origini private devono essere indicati dal tenant di SharePoint Online. L'accesso diretto alle risorse CDN private non funziona.
+ Se si rimuove un asset dall'origine privata, l'asset potrebbe continuare a essere disponibile fino a un'ora dalla cache. Tuttavia, i collegamenti all'asset nella rete CDN verranno invalidati entro 15 minuti dalla rimozione dell'asset.
+ I tipi di file predefiniti inclusi per le origini private sono .gif, .ico, .jpeg, .jpg, .js e .png. È possibile specificare tipi di file aggiuntivi.
+ Analogamente alle origini pubbliche, è possibile configurare un criterio per escludere le risorse identificate dalle classificazioni dei siti specificate anche se si utilizzano caratteri jolly per includere tutte le risorse all'interno di una cartella o di una raccolta documenti.

Per ulteriori informazioni sul motivo per cui usare la rete CDN di Office 365, i concetti generali della rete CDN e altre reti CDN Microsoft che è possibile usare con il tenant di Office 365, vedere Reti per la distribuzione di [contenuti](content-delivery-networks.md).

### <a name="default-cdn-origins"></a>Origini cdN predefinite

Se non diversamente specificato, Office 365 configura automaticamente alcune origini predefinite quando si abilita la rete CDN di Office 365. Se inizialmente scegli di non effettuare il provisioning, puoi aggiungere queste origini dopo aver completato l'installazione. A meno che non si comprenda le conseguenze di ignorare la configurazione delle origini predefinite e di avere un motivo specifico per farlo, è consigliabile consentirne la creazione quando si abilita la rete CDN.
  
Origini cdN private predefinite:
  
+ \*/userphoto.aspx
+ \*/siteassets

Origini predefinite della rete CDN pubblica:
  
+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ è un'origine pubblica predefinita aggiunta al servizio CDN di Office 365 a dicembre 2017. Questa origine deve essere presente perché le soluzioni SharePoint Framework nella rete CDN funzionino. Se è stata abilitata la rete CDN di Office 365 prima di dicembre 2017 o se è stata ignorata la configurazione delle origini predefinite quando è stata abilitata la rete CDN, è possibile aggiungere manualmente questa origine. Per ulteriori informazioni, vedere [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Configurare e configurare la rete CDN di Office 365 tramite SharePoint Online Management Shell

Le procedure descritte in questa sezione richiedono l'utilizzo di SharePoint Online Management Shell per connettersi a SharePoint Online. Per istruzioni, vedere [Connect to SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

Completare questi passaggi per configurare la rete CDN per ospitare gli asset in SharePoint Online tramite SharePoint Online Management Shell.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Consentire all'organizzazione di usare la rete CDN di Office 365

Prima di apportare modifiche alle impostazioni della rete CDN tenant, è consigliabile recuperare lo stato corrente della configurazione della rete CDN privata nel tenant di Office 365. Connettersi al tenant tramite SharePoint Online Management Shell:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Utilizzare ora il cmdlet **Get-SPOTenantCdnEnabled** per recuperare le impostazioni di stato della rete CDN dal tenant:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Lo stato della rete CDN per l'oggetto CdnType specificato verrà visualizzato sullo schermo.

Utilizzare il cmdlet **Set-SPOTenantCdnEnabled** per consentire all'organizzazione di utilizzare la rete CDN di Office 365. È possibile consentire all'organizzazione di utilizzare origini pubbliche, origini private o entrambe contemporaneamente. Puoi anche configurare la rete CDN in modo da ignorare l'impostazione delle origini predefinite quando la abiliti. È sempre possibile aggiungere queste origini in un secondo momento, come descritto in questo argomento.
  
In Windows Powershell per SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Ad esempio, per consentire all'organizzazione di utilizzare sia origini pubbliche che private, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Per consentire all'organizzazione di utilizzare sia origini pubbliche che private ma ignorare la configurazione delle origini predefinite, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Vedere [Origini della rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinita per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365 e sul potenziale impatto di ignorare la configurazione delle origini predefinite.

Per consentire all'organizzazione di utilizzare origini pubbliche, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Per ulteriori informazioni su questo cmdlet, vedere [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Modificare l'elenco dei tipi di file da includere nella rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si definiscono i tipi di file utilizzando il cmdlet **Set-SPOTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito. Se si desidera aggiungere ulteriori tipi di file all'elenco, utilizzare innanzitutto il cmdlet per individuare i tipi di file già consentiti e includerli nell'elenco insieme a quelli nuovi.
  
Utilizzare il cmdlet **Set-SPOTenantCdnPolicy** per definire i tipi di file statici che possono essere ospitati da origini pubbliche e private nella rete CDN. Per impostazione predefinita, sono consentiti tipi di asset comuni, ad esempio css, gif, jpg e js.

In Windows PowerShell per SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Ad esempio, per consentire alla rete CDN di ospitare file con estensione css e png, immettere il comando:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Per sapere quali tipi di file sono attualmente consentiti dalla rete CDN, utilizzare il cmdlet **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Per ulteriori informazioni su questi cmdlet, vedere [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) e [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si escludono le classificazioni dei siti utilizzando il cmdlet **Set-SPOTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito. Se si desidera escludere classificazioni di siti aggiuntive, utilizzare innanzitutto il cmdlet per individuare le classificazioni già escluse e quindi aggiungerle insieme a quelle nuove.

Utilizzare il cmdlet **Set-SPOTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili nella rete CDN. Per impostazione predefinita, non vengono escluse classificazioni di siti.

In Windows PowerShell per SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Per sapere quali classificazioni di siti sono attualmente limitate, utilizzare il cmdlet **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Le proprietà che verranno restituite sono _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ _e ExcludeIfNoScriptDisabled._

La _proprietà IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno gestite dalla rete CDN.

> [!NOTE]
> Le estensioni di file predefinite sono diverse tra pubblico e privato.

La _proprietà ExcludeRestrictedSiteClassifications_ contiene le classificazioni dei siti che si desidera escludere dalla rete CDN. Ad esempio, è possibile escludere i siti contrassegnati come **Riservati** in modo che il contenuto dei siti a cui è applicata tale classificazione non sia servito dalla rete CDN.

La _proprietà ExcludeIfNoScriptDisabled_ esclude il contenuto dalla rete CDN in base alle impostazioni dell'attributo _NoScript_ a livello di sito. Per impostazione predefinita, _l'attributo NoScript_ è impostato su **Abilitato** per i _siti_ moderni e **Disabilitato per** _i siti_ classici. Dipende dalle impostazioni del tenant.

Per ulteriori informazioni su questi cmdlet, vedere [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) e [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Aggiungere un'origine per le risorse

Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire un'origine. È possibile definire più origini. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.
  
> [!IMPORTANT]
> Non inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Il valore _di path_ è il percorso relativo alla raccolta o alla cartella che contiene gli asset. Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly. Origins supporta i caratteri jolly anteposti all'URL. In questo modo è possibile creare origini che si estendono su più siti. Ad esempio, per includere tutti gli asset nella cartella masterpages per tutti i siti come origine pubblica all'interno della rete CDN, digitare il comando seguente:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Il modificatore con caratteri jolly * può essere utilizzato solo all'inizio del percorso e corrisponderà a tutti i segmenti **/** di URL nell'URL specificato.
+ Il percorso può puntare a una raccolta documenti, una cartella o un sito. Ad esempio, il percorso _*/site1_ corrisponderà a tutte le raccolte documenti del sito.

È possibile aggiungere un'origine con un percorso relativo specifico. Non è possibile aggiungere un'origine utilizzando il percorso completo.

In questo esempio viene aggiunta un'origine privata della raccolta siti in un sito specifico:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In questo esempio viene aggiunta un'origine privata della _cartella folder1_ nella raccolta risorse sito della raccolta siti:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Se nel percorso è presente uno spazio, è possibile racchiudere il percorso tra virgolette doppie o sostituire lo spazio con la codifica URL %20. Negli esempi seguenti viene aggiunta un'origine privata della cartella _1_ nella raccolta risorse sito della raccolta siti:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

> [!NOTE]
> Nelle origini private, gli asset condivisi da un'origine devono avere una versione principale pubblicata prima di poter essere accessibili dalla rete CDN.
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. L'operazione può richiedere fino a 15 minuti.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Esempio: Configurare un'origine pubblica per le pagine master e per la raccolta stili per SharePoint Online

In genere, queste origini vengono impostate automaticamente quando si abilita la rete CDN di Office 365. Tuttavia, se si desidera abilitarli manualmente, eseguire la procedura seguente.
  
+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la libreria di stili come origine pubblica.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire le pagine master come origine pubblica.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. L'operazione può richiedere fino a 15 minuti.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Esempio: Configurare un'origine privata per le risorse del sito, le pagine del sito e le immagini di pubblicazione per SharePoint Online

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle risorse del sito come origine privata.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle pagine del sito come origine privata.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle immagini di pubblicazione come origine privata.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. L'operazione può richiedere fino a 15 minuti.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Esempio: Configurare un'origine privata per una raccolta siti per SharePoint Online

Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire una raccolta siti come origine privata. Ad esempio:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. È possibile che venga visualizzato _un messaggio_ di configurazione in sospeso previsto quando il tenant di SharePoint Online si connette al servizio CDN. L'operazione può richiedere fino a 15 minuti.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Gestire la rete CDN di Office 365

Dopo aver configurato la rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle esigenze, come descritto in questa sezione.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Aggiungere, aggiornare o rimuovere asset dalla rete CDN di Office 365

Dopo aver completato i passaggi di configurazione, puoi aggiungere nuovi asset e aggiornare o rimuovere gli asset esistenti quando vuoi. È sufficiente apportare le modifiche agli asset nella cartella o nella raccolta di SharePoint identificata come origine. Se aggiungi un nuovo asset, questo sarà immediatamente disponibile tramite la rete CDN. Tuttavia, se si aggiorna l'asset, la propagazione della nuova copia e la disponibilità della nuova copia nella rete CDN saranno fino a 15 minuti.
  
Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-SPOTenantCdnOrigins.** Per informazioni su come utilizzare questo cmdlet, vedere [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Rimuovere un'origine dalla rete CDN di Office 365

È possibile rimuovere l'accesso a una cartella o a una raccolta di SharePoint identificata come origine. A tale scopo, utilizzare il cmdlet **Remove-SPOTenantCdnOrigin.**

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Per informazioni su come utilizzare questo cmdlet, [vedere Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificare un'origine nella rete CDN di Office 365

Non è possibile modificare un'origine creata. Rimuovi invece l'origine e quindi aggiungine una nuova. Per ulteriori informazioni, vedere Per rimuovere un'origine dalla rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) e Per aggiungere un'origine [per gli asset.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Utilizzare il cmdlet **Set-SPOTenantCdnEnabled** per disabilitare la rete CDN per l'organizzazione. Se per la rete CDN sono abilitate sia le origini pubbliche che private, è necessario eseguire il cmdlet due volte, come illustrato negli esempi seguenti.
  
Per disabilitare l'uso delle origini pubbliche nella rete CDN, immettere il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Per disabilitare l'utilizzo delle origini private nella rete CDN, immettere il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Per ulteriori informazioni su questo cmdlet, vedere [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Configurare e configurare la rete CDN di Office 365 tramite PowerShell PnP

Le procedure descritte in questa sezione richiedono l'utilizzo di PowerShell PnP per connettersi a SharePoint Online. Per istruzioni, vedere [Introduzione a PowerShell PnP.](https://github.com/SharePoint/PnP-PowerShell#getting-started)

Completare questi passaggi per configurare la rete CDN per ospitare gli asset in SharePoint Online tramite PowerShell PnP.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Consentire all'organizzazione di usare la rete CDN di Office 365

Prima di apportare modifiche alle impostazioni della rete CDN tenant, è consigliabile recuperare lo stato corrente della configurazione della rete CDN privata nel tenant di Office 365. Connettersi al tenant tramite PowerShell PnP:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

A questo punto, utilizzare il cmdlet **Get-PnPTenantCdnEnabled** per recuperare le impostazioni di stato della rete CDN dal tenant:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Lo stato della rete CDN per l'oggetto CdnType specificato verrà visualizzato sullo schermo.

Utilizzare il cmdlet **Set-PnPTenantCdnEnabled** per consentire all'organizzazione di utilizzare la rete CDN di Office 365. È possibile consentire all'organizzazione di utilizzare origini pubbliche, origini private o entrambe contemporaneamente. Puoi anche configurare la rete CDN in modo da ignorare l'impostazione delle origini predefinite quando la abiliti. È sempre possibile aggiungere queste origini in un secondo momento, come descritto in questo argomento.
  
In PowerShell PnP:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Ad esempio, per consentire all'organizzazione di utilizzare sia origini pubbliche che private, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Per consentire all'organizzazione di utilizzare sia origini pubbliche che private ma ignorare la configurazione delle origini predefinite, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Vedere [Origini della rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinita per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365 e sul potenziale impatto di ignorare la configurazione delle origini predefinite.

Per consentire all'organizzazione di utilizzare origini pubbliche, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Per ulteriori informazioni su questo cmdlet, [vedere Set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Modificare l'elenco dei tipi di file da includere nella rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si definiscono i tipi di file utilizzando il cmdlet **Set-PnPTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito. Se si desidera aggiungere ulteriori tipi di file all'elenco, utilizzare innanzitutto il cmdlet per individuare i tipi di file già consentiti e includerli nell'elenco insieme a quelli nuovi.
  
Utilizzare il cmdlet **Set-PnPTenantCdnPolicy** per definire i tipi di file statici che possono essere ospitati da origini pubbliche e private nella rete CDN. Per impostazione predefinita, sono consentiti tipi di asset comuni, ad esempio css, gif, jpg e js.

In PowerShell PnP:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Ad esempio, per consentire alla rete CDN di ospitare file con estensione css e png, immettere il comando:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Per sapere quali tipi di file sono attualmente consentiti dalla rete CDN, utilizzare il cmdlet **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Per ulteriori informazioni su questi cmdlet, vedere [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies.](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si escludono le classificazioni dei siti utilizzando il cmdlet **Set-PnPTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito. Se si desidera escludere classificazioni di siti aggiuntive, utilizzare innanzitutto il cmdlet per individuare le classificazioni già escluse e quindi aggiungerle insieme a quelle nuove.

Utilizzare il cmdlet **Set-PnPTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili nella rete CDN. Per impostazione predefinita, non vengono escluse classificazioni di siti.

In PowerShell PnP:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Per sapere quali classificazioni di siti sono attualmente limitate, utilizzare il cmdlet **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Le proprietà che verranno restituite sono _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ _e ExcludeIfNoScriptDisabled._

La _proprietà IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno gestite dalla rete CDN.

> [!NOTE]
> Le estensioni di file predefinite sono diverse tra pubblico e privato.

La _proprietà ExcludeRestrictedSiteClassifications_ contiene le classificazioni dei siti che si desidera escludere dalla rete CDN. Ad esempio, è possibile escludere i siti contrassegnati come **Riservati** in modo che il contenuto dei siti a cui è applicata tale classificazione non sia servito dalla rete CDN.

La _proprietà ExcludeIfNoScriptDisabled_ esclude il contenuto dalla rete CDN in base alle impostazioni dell'attributo _NoScript_ a livello di sito. Per impostazione predefinita, _l'attributo NoScript_ è impostato su **Abilitato** per i _siti_ moderni e **Disabilitato per** _i siti_ classici. Dipende dalle impostazioni del tenant.

Per ulteriori informazioni su questi cmdlet, vedere [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies.](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Aggiungere un'origine per le risorse

Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire un'origine. È possibile definire più origini. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.
  
> [!IMPORTANT]
> Non inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Il valore _di path_ è il percorso relativo alla raccolta o alla cartella che contiene gli asset. Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly. Origins supporta i caratteri jolly anteposti all'URL. In questo modo è possibile creare origini che si estendono su più siti. Ad esempio, per includere tutti gli asset nella cartella masterpages per tutti i siti come origine pubblica all'interno della rete CDN, digitare il comando seguente:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Il modificatore con caratteri jolly * può essere utilizzato solo all'inizio del percorso e corrisponderà a tutti i segmenti **/** di URL nell'URL specificato.
+ Il percorso può puntare a una raccolta documenti, una cartella o un sito. Ad esempio, il percorso _*/site1_ corrisponderà a tutte le raccolte documenti del sito.

È possibile aggiungere un'origine con un percorso relativo specifico. Non è possibile aggiungere un'origine utilizzando il percorso completo.

In questo esempio viene aggiunta un'origine privata della raccolta di risorse del sito in un sito specifico:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In questo esempio viene aggiunta un'origine privata della _cartella folder1_ nella raccolta risorse sito della raccolta siti:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Se nel percorso è presente uno spazio, è possibile racchiudere il percorso tra virgolette doppie o sostituire lo spazio con la codifica URL %20. Negli esempi seguenti viene aggiunta un'origine privata della cartella _1_ nella raccolta risorse sito della raccolta siti:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> Nelle origini private, gli asset condivisi da un'origine devono avere una versione principale pubblicata prima di poter essere accessibili dalla rete CDN.
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. L'operazione può richiedere fino a 15 minuti.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Esempio: Configurare un'origine pubblica per le pagine master e per la raccolta stili per SharePoint Online

In genere, queste origini vengono impostate automaticamente quando si abilita la rete CDN di Office 365. Tuttavia, se si desidera abilitarli manualmente, eseguire la procedura seguente.
  
+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la libreria di stili come origine pubblica.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire le pagine master come origine pubblica.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. L'operazione può richiedere fino a 15 minuti.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Esempio: Configurare un'origine privata per le risorse del sito, le pagine del sito e le immagini di pubblicazione per SharePoint Online

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle risorse del sito come origine privata.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle pagine del sito come origine privata.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle immagini di pubblicazione come origine privata.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. L'operazione può richiedere fino a 15 minuti.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Esempio: Configurare un'origine privata per una raccolta siti per SharePoint Online

Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire una raccolta siti come origine privata. Ad esempio:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. È possibile che venga visualizzato _un messaggio_ di configurazione in sospeso previsto quando il tenant di SharePoint Online si connette al servizio CDN. L'operazione può richiedere fino a 15 minuti.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Gestire la rete CDN di Office 365

Dopo aver configurato la rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle esigenze, come descritto in questa sezione.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Aggiungere, aggiornare o rimuovere asset dalla rete CDN di Office 365

Dopo aver completato i passaggi di configurazione, puoi aggiungere nuovi asset e aggiornare o rimuovere gli asset esistenti quando vuoi. È sufficiente apportare le modifiche agli asset nella cartella o nella raccolta di SharePoint identificata come origine. Se aggiungi un nuovo asset, questo sarà immediatamente disponibile tramite la rete CDN. Tuttavia, se si aggiorna l'asset, la propagazione della nuova copia e la disponibilità della nuova copia nella rete CDN saranno fino a 15 minuti.
  
Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-PnPTenantCdnOrigin.** Per informazioni su come utilizzare questo cmdlet, vedere [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Rimuovere un'origine dalla rete CDN di Office 365

È possibile rimuovere l'accesso a una cartella o a una raccolta di SharePoint identificata come origine. A tale scopo, utilizzare il cmdlet **Remove-PnPTenantCdnOrigin.**

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Per informazioni su come utilizzare questo cmdlet, [vedere Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificare un'origine nella rete CDN di Office 365

Non è possibile modificare un'origine creata. Rimuovi invece l'origine e quindi aggiungine una nuova. Per ulteriori informazioni, vedere Per rimuovere un'origine dalla rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) e Per aggiungere un'origine [per gli asset.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Utilizzare il cmdlet **Set-PnPTenantCdnEnabled** per disabilitare la rete CDN per l'organizzazione. Se per la rete CDN sono abilitate sia le origini pubbliche che private, è necessario eseguire il cmdlet due volte, come illustrato negli esempi seguenti.
  
Per disabilitare l'uso delle origini pubbliche nella rete CDN, immettere il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Per disabilitare l'utilizzo delle origini private nella rete CDN, immettere il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Per ulteriori informazioni su questo cmdlet, [vedere Set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Configurare e configurare la rete CDN di Office 365 tramite l'interfaccia della riga di comando di Office 365

Le procedure descritte in questa sezione richiedono l'installazione dell'interfaccia della riga di comando di [Office 365.](https://aka.ms/o365cli) Successivamente, connettersi al tenant di Office 365 usando il [comando di](https://pnp.github.io/office365-cli/cmd/login/) accesso.

Completare questi passaggi per configurare la rete CDN per ospitare gli asset in SharePoint Online tramite l'interfaccia della riga di comando di Office 365.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-the-office-365-cdn"></a>Abilitare la rete CDN di Office 365

È possibile gestire lo stato della rete CDN di Office 365 nel tenant usando il comando [spo cdn set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)

Per abilitare la rete CDN pubblica di Office 365 nel tenant eseguire:

```sh
spo cdn set --type Public --enabled true
```

Per abilitare la rete CDN di Office 365 SharePoint, eseguire:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Visualizzare lo stato corrente della rete CDN di Office 365

Per verificare se il tipo specifico di rete CDN di Office 365 è abilitato o disabilitato, utilizzare il comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)

Per verificare se la rete CDN pubblica di Office 365 è abilitata, eseguire:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Visualizzare le origini della rete CDN di Office 365

Per visualizzare le origini della rete CDN pubblica di Office 365 attualmente configurate, eseguire:

```sh
spo cdn origin list --type Public
```

Vedere [Origini cdN predefinite](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365.

### <a name="add-an-office-365-cdn-origin"></a>Aggiungere un'origine CDN di Office 365

> [!IMPORTANT]
> Non inserire mai risorse considerate riservate all'organizzazione in una raccolta documenti di SharePoint configurata come origine pubblica.

Utilizzare il [comando spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) per definire un'origine CDN. È possibile definire più origini. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Dove `path` è il percorso relativo della cartella che contiene gli asset. Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly.

Per includere tutti gli asset nella raccolta **pagine master** di tutti i siti come origine pubblica, eseguire:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Per configurare un'origine privata per una raccolta siti specifica, eseguire:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Dopo aver aggiunto un'origine CDN, potrebbero essere necessari fino a 15 minuti per poter recuperare i file tramite il servizio CDN. È possibile verificare se la determinata origine è già stata abilitata utilizzando il comando [spo cdn origin list.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/)

### <a name="remove-an-office-365-cdn-origin"></a>Rimuovere un'origine CDN di Office 365

Utilizzare il [comando spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) per rimuovere un'origine CDN per il tipo di rete CDN specificato.

Per rimuovere un'origine pubblica dalla configurazione della rete CDN, eseguire:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> La rimozione di un'origine CDN non influisce sui file archiviati in alcuna raccolta documenti corrispondente a tale origine. Se si fa riferimento a queste risorse utilizzando l'URL di SharePoint, SharePoint torna automaticamente all'URL originale che punta alla raccolta documenti. Se, tuttavia, è stato fatto riferimento agli asset tramite un URL CDN pubblico, la rimozione dell'origine interromperà il collegamento e sarà necessario modificarli manualmente.

### <a name="modify-an-office-365-cdn-origin"></a>Modificare un'origine CDN di Office 365

Non è possibile modificare un'origine CDN esistente. È invece consigliabile rimuovere l'origine CDN definita in precedenza utilizzando il comando e aggiungerne una `spo cdn origin remove` nuova utilizzando il `spo cdn origin add` comando.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Modificare i tipi di file da includere nella rete CDN di Office 365

Per impostazione predefinita, nella rete CDN sono inclusi i seguenti tipi di file: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2._ Se è necessario includere tipi di file aggiuntivi nella rete CDN, è possibile modificare la configurazione della rete CDN utilizzando il comando [spo cdn policy set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)

> [!NOTE]
> Quando si modifica l'elenco dei tipi di file, si sovrascrive l'elenco attualmente definito. Se si desidera includere tipi di file aggiuntivi, utilizzare innanzitutto il comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) per individuare i tipi di file attualmente configurati.

Per aggiungere il tipo di file _JSON_ all'elenco predefinito dei tipi di file inclusi nella rete CDN pubblica, eseguire:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365

Utilizzare il [comando spo cdn policy set per](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) escludere le classificazioni dei siti che non si desidera rendere disponibili nella rete CDN. Per impostazione predefinita, non vengono escluse classificazioni di siti.

> [!NOTE]
> Quando si modifica l'elenco delle classificazioni dei siti escluse, si sovrascrive l'elenco attualmente definito. Se si desidera escludere classificazioni aggiuntive, utilizzare innanzitutto il comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) per individuare le classificazioni attualmente configurate.

Per escludere i siti _classificati come HBI_ dalla rete CDN pubblica, eseguire

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Per disabilitare la rete CDN di Office 365, utilizzare il `spo cdn set` comando, ad esempio:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Uso degli asset CDN

Dopo aver abilitato la rete CDN e aver configurato origini e criteri, puoi iniziare a usare gli asset della rete CDN.

In questa sezione viene illustrato come utilizzare gli URL delle reti CDN nelle pagine e nel contenuto di SharePoint in modo che SharePoint reindirizza le richieste di risorse sia di origine pubblica che privata alla rete CDN.

+ [Aggiornamento dei collegamenti agli asset CDN](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Utilizzo di risorse in origini pubbliche](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Utilizzo di risorse in origini private](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Per informazioni su come usare la rete CDN per ospitare web part sul lato client, vedere l'argomento Ospitare la web part sul lato client dalla rete CDN di [Office 365 (Hello World part 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)

> [!NOTE]
> Se si aggiunge la _cartella ClientSideAssets_ all'elenco delle origini **della** rete CDN privata, il rendering delle web part personalizzate ospitate da CDN non verrà eseguito. I file utilizzati dalle web part SPFX possono utilizzare solo la rete CDN pubblica e la cartella ClientSideAssets è un'origine predefinita per la rete CDN pubblica. 

### <a name="updating-links-to-cdn-assets"></a>Aggiornamento dei collegamenti agli asset CDN

Per usare gli asset aggiunti a un'origine, è sufficiente aggiornare i collegamenti al file originale con il percorso del file nell'origine.

+ Modificare la pagina o il contenuto contenente i collegamenti alle risorse aggiunte a un'origine. È inoltre possibile utilizzare uno dei diversi metodi per cercare e sostituire a livello globale i collegamenti in un sito o in una raccolta siti se si desidera aggiornare il collegamento a una determinata risorsa ovunque venga visualizzato.
+ Per ogni collegamento a un asset in un'origine, sostituire il percorso con il percorso del file nell'origine CDN. È possibile utilizzare percorsi relativi.
+ Salvare la pagina o il contenuto.

Si consideri ad esempio l'immagine _/site/SiteAssets/images/image.png_, copiata nella cartella della raccolta documenti _/site/CDN_origins/public/_. Per utilizzare l'asset CDN, sostituire il percorso originale del file di immagine con il percorso dell'origine per rendere il nuovo URL _/site/CDN_origins/public/image.png_.

Se vuoi usare l'URL completo dell'asset invece di un percorso relativo, crea il collegamento in questo modo:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> In generale, non è consigliabile codificare gli URL direttamente agli asset nella rete CDN. Tuttavia, è possibile creare manualmente URL per gli asset di origini pubbliche, se necessario. Per ulteriori informazioni, vedere [Hardcoding CDN URL for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).

Per informazioni su come verificare che gli asset vengano serviti dalla rete CDN, vedere How [do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) nella sezione Risoluzione dei problemi della rete CDN di Office [365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>Utilizzo di risorse in origini pubbliche

La **funzionalità di** pubblicazione in SharePoint Online riscrive automaticamente gli URL degli asset archiviati in origini pubbliche negli equivalenti della rete CDN in modo che gli asset siano serviti dal servizio CDN anziché da SharePoint.

Se l'origine si trova in un sito con la caratteristica Pubblicazione abilitata e gli asset che si desidera scaricare nella rete CDN si trova in una delle categorie seguenti, SharePoint riscriverà automaticamente gli URL per gli asset nell'origine, a condizione che l'asset non sia stato escluso da un criterio cdn.

Di seguito è riportata una panoramica dei collegamenti riscritti automaticamente dalla caratteristica Pubblicazione SharePoint:

+ URL IMG/LINK/CSS nelle risposte HTML della pagina di pubblicazione classica
  + Sono incluse le immagini aggiunte dagli autori all'interno del contenuto HTML di una pagina
+ URL immagine web part Raccolta immagini SlideShow
+ Campi immagine nei risultati dell'API REST SPList (RenderListDataAsStream)
  + Utilizzare la nuova _proprietà ImageFieldsToTryRewriteToCdnUrls_ per fornire un elenco delimitato da virgole di campi
  + Supporta i campi collegamento ipertestuale e i campi PublishingImage
+ Rendering di immagini di SharePoint

Nel diagramma seguente viene illustrato il flusso di lavoro quando SharePoint riceve una richiesta per una pagina contenente risorse da un'origine pubblica.

![Diagramma del flusso di lavoro: recupero di asset cdN di Office 365 da un'origine pubblica](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Flusso di lavoro: recupero di asset cdN di Office 365 da un'origine pubblica")

> [!TIP]
> Se si desidera disabilitare la riscrittura automatica per URL specifici in una pagina, è possibile estrarre la pagina e aggiungere il parametro della stringa di query **? NoAutoReWrites=true** alla fine di ogni collegamento che si desidera disabilitare.

#### <a name="constructing-cdn-urls-for-public-assets"></a>Creazione di URL CDN per asset pubblici

Se  la caratteristica Pubblicazione non è abilitata per un'origine pubblica o se l'asset non è uno dei tipi di collegamento supportati dalla funzionalità di riscrittura automatica del servizio CDN, è possibile creare manualmente gli URL nel percorso CDN degli asset e utilizzare questi URL nel contenuto.

> [!NOTE]
> Non è possibile hardcoded o costruire URL CDN per gli asset in un'origine privata perché il token di accesso necessario che costituisce l'ultima sezione dell'URL viene generato al momento della richiesta della risorsa. È possibile creare l'URL per la rete CDN pubblica e l'URL non deve essere hard coded perché è soggetto a modifiche.

Per gli asset CDN pubblici, il formato dell'URL sarà simile al seguente:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Sostituire **TenantHostName** con il nome del tenant. Esempio:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```
> [!NOTE]
> La proprietà di contesto della pagina deve essere utilizzata per costruire il prefisso anziché hard coding " https://publiccdn.sharepointonline.com ". L'URL è soggetto a modifiche e non deve essere hard coded. Se si utilizzano modelli di visualizzazione con SharePoint Online classico, è possibile utilizzare la proprietà "window._spPageContextInfo.publicCdnBaseUrl" nel modello di visualizzazione per il prefisso dell'URL. Se si sono web part SPFx per SharePoint moderno e classico, è possibile utilizzare la proprietà "this.context.pageContext.legacyPageContext.publicCdnBaseUrl". In questo modo verrà fornito il prefisso in modo che, se viene modificato, l'implementazione si aggiornerà con esso. Come esempio per SPFx, l'URL può essere creato utilizzando la proprietà "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL per l'elemento". Vedere [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) che fa parte della [serie di prestazioni della prima stagione](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>Utilizzo di risorse in origini private

Non è necessaria alcuna configurazione aggiuntiva per utilizzare gli asset in origini private. SharePoint Online riscrive automaticamente gli URL per gli asset in origini private in modo che le richieste per tali asset siano sempre servite dalla rete CDN. Non è possibile creare manualmente URL per asset CDN in origini private perché questi URL contengono token che devono essere generati automaticamente da SharePoint Online al momento della richiesta dell'asset.

L'accesso agli asset in origini private è protetto da token generati dinamicamente in base alle autorizzazioni utente per l'origine, con le avvertenze descritte nelle sezioni seguenti. Gli utenti devono disporre almeno **dell'accesso in** lettura alle origini per consentire alla rete CDN di eseguire il rendering del contenuto.

Nel diagramma seguente viene illustrato il flusso di lavoro quando SharePoint riceve una richiesta per una pagina contenente risorse da un'origine privata.

![Diagramma del flusso di lavoro: recupero di asset cdN di Office 365 da un'origine privata](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Flusso di lavoro: recupero di asset cdN di Office 365 da un'origine privata")

#### <a name="token-based-authorization-in-private-origins"></a>Autorizzazione basata su token in origini private

L'accesso agli asset in origini private nella rete CDN di Office 365 viene concesso dai token generati da SharePoint Online. Agli utenti che dispongono già dell'autorizzazione di accesso alla cartella o alla raccolta designata dall'origine vengono automaticamente concessi token che consentono all'utente di accedere al file in base al livello di autorizzazione. Questi token di accesso sono validi da 30 a 90 minuti dopo la generazione per evitare attacchi di riesecuzione dei token.

Dopo la generazione del token di accesso, SharePoint Online restituisce un URI personalizzato al client contenente due parametri di autorizzazione _(token_ di autorizzazione edge) e _avena_ (token di autorizzazione di origine). La struttura di ogni token _<'ora_ di scadenza nel formato di data e ora >__< della firma >. Ad esempio:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Chiunque sia in possesso del token può accedere alla risorsa nella rete CDN. Tuttavia, gli URL contenenti questi token di accesso vengono condivisi solo tramite HTTPS, quindi, a meno che l'URL non sia esplicitamente condiviso da un utente finale prima della scadenza del token, l'asset non sarà accessibile agli utenti non autorizzati.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Le autorizzazioni a livello di elemento non sono supportate per gli asset in origini private

È importante notare che SharePoint Online non supporta le autorizzazioni a livello di elemento per gli asset di origini private. Ad esempio, per un file che si trova in , gli utenti hanno `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` accesso effettivo al file in base alle condizioni seguenti:

|Utente  |Autorizzazioni  |Accesso efficace  |
|---------|---------|---------|
|Utente 1     |Ha accesso a folder1         |Può accedere image1.jpg dalla rete CDN         |
|Utente 2     |Non ha accesso a folder1         |Impossibile accedere image1.jpg dalla rete CDN         |
|Utente 3     |Non dispone dell'accesso a folder1, ma viene concessa l'autorizzazione esplicita per accedere image1.jpg in SharePoint Online         |Può accedere alla risorsa image1.jpg direttamente da SharePoint Online, ma non dalla rete CDN         |
|Utente 4     |Ha accesso a folder1, ma è stato esplicitamente negato l'accesso a image1.jpg in SharePoint Online         |Impossibile accedere all'asset da SharePoint Online, ma può accedere all'asset dalla rete CDN nonostante sia stato negato l'accesso al file in SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Risoluzione dei problemi della rete CDN di Office 365

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Come è possibile verificare che gli asset siano serviti dalla rete CDN?

Dopo aver aggiunto i collegamenti agli asset della rete CDN a una pagina, puoi confermare che l'asset viene servito dalla rete CDN visualizzando la pagina, facendo clic con il pulsante destro del mouse sull'immagine dopo aver eseguito il rendering e aver esaminato l'URL dell'immagine.

Puoi anche usare gli strumenti di sviluppo del browser per visualizzare l'URL di ogni risorsa in una pagina o uno strumento di traccia di rete di terze parti.

> [!NOTE]
> Se si utilizza uno strumento di rete come Fiddler per testare gli asset all'esterno del rendering dell'asset da una pagina di SharePoint, è necessario aggiungere manualmente l'intestazione referer "Referer: " alla richiesta GET in cui l'URL è l'URL radice del tenant di `https://yourdomain.sharepoint.com` SharePoint Online.

Non è possibile testare gli URL cdN direttamente in un Web browser perché è necessario disporre di un referer proveniente da SharePoint Online. Tuttavia, se si aggiunge l'URL dell'asset CDN a una pagina di SharePoint e quindi si apre la pagina in un browser, nella pagina verrà visualizzato il rendering dell'asset CDN.

Per ulteriori informazioni sull'uso degli strumenti di sviluppo nel browser Microsoft Edge, vedere [Strumenti di sviluppo di Microsoft Edge.](/microsoft-edge/devtools-guide)

Per guardare un breve video ospitato nel canale [YouTube](https://aka.ms/sppnp-videos) Modelli e procedure per sviluppatori di SharePoint che illustra come verificare il funzionamento della rete CDN, vedere [Verifying your CDN usage](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)and ensuring optimal network connectivity .

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Perché gli asset di una nuova origine non sono disponibili?
Gli asset nelle nuove origini non saranno immediatamente disponibili per l'utilizzo, perché la registrazione richiede tempo per la propagazione della registrazione attraverso la rete CDN e per il caricamento degli asset dall'origine all'archiviazione cdn. Il tempo necessario per la disponibilità degli asset nella rete CDN dipende dal numero di asset e dalle dimensioni dei file.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>La web part sul lato client o la soluzione SharePoint Framework non funziona

Quando si abilita la rete CDN di Office 365 per le origini pubbliche, il servizio CDN crea automaticamente queste origini predefinite:

+ */MASTERPAGE
+ */LIBRERIA DI STILI
+ */CLIENTSIDEASSETS

Se l'origine */clientsideassets non è presente, le soluzioni SharePoint Framework avranno esito negativo e non verranno generati messaggi di avviso o di errore. Questa origine potrebbe non essere presente perché la rete CDN è stata abilitata con il parametro _-NoDefaultOrigins_ impostato **su $true** oppure perché l'origine è stata eliminata manualmente.

È possibile verificare quali origini sono presenti con il seguente comando di PowerShell:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Oppure è possibile verificare con l'interfaccia della riga di comando di Office 365:Or you can check with the Office 365 CLI:

``` powershell
spo cdn origin list
```

Per aggiungere l'origine in PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Per aggiungere l'origine nell'interfaccia della riga di comando di Office 365:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Quali moduli di PowerShell e shell CLI è necessario utilizzare con la rete CDN di Office 365?

È possibile scegliere di utilizzare la rete CDN di Office 365 utilizzando il modulo PowerShell di **SharePoint Online Management Shell** o l'interfaccia della riga di comando di Office **365.**

+ [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Installazione dell'interfaccia della riga di comando di Office 365](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Vedere anche

[Reti per la distribuzione di contenuti](./content-delivery-networks.md)

[Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](./network-planning-and-performance.md)

[Serie di prestazioni di SharePoint - Serie video cdN di Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)