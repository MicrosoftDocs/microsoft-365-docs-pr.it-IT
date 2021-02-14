---
title: Usare la rete per la distribuzione di contenuti (CDN) di Office 365 con SharePoint Online
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
description: Informazioni su come usare la rete per la distribuzione di contenuti (CDN) di Office 365 per velocizzare la distribuzione delle risorse di SharePoint Online.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690975"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online

È possibile usare la rete per la distribuzione di contenuti di Office 365 predefinita per ospitare risorse statiche e migliorare le prestazioni delle pagine di SharePoint Online. La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza. Inoltre, la rete CDN di Office 365 usa il [protocollo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) per migliorare la compressione e il pipelining HTTP. Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

> [!NOTE]
> La rete CDN di Office 365 è disponibile solo per i tenant nel cloud **di** produzione (internazionale). I tenant nei cloud del governo statunitense, della Cina e della Germania non supportano attualmente la rete CDN di Office 365.

La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità. In base al tipo di contenuto che si vuole ospitare nella rete per la distribuzione di contenuti di Office 365, è possibile aggiungere origini **pubbliche**, origini **private** o entrambi. Per [ulteriori informazioni sulla](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) differenza tra origini pubbliche e private, vedere Scegliere se ogni origine deve essere pubblica o privata.

![Diagramma concettuale della rete CDN di Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagramma concettuale della rete CDN di Office 365")

Se si ha già familiarità con il funzionamento delle reti CDN, è necessario completare solo alcuni passaggi per abilitare la rete CDN di Office 365 per il tenant. In questo argomento viene descritto come. Continua a leggere per informazioni su come iniziare a ospitare gli asset statici.

> [!TIP]
> Esistono altre reti CDN ospitate da Microsoft che possono essere usate con Office 365 per scenari di utilizzo specializzati, ma non sono descritte in questo argomento perché non rientrano nell'ambito della rete CDN di Office 365. Per ulteriori informazioni, vedere [Altre reti CDN Microsoft.](content-delivery-networks.md#other-microsoft-cdns)

 **Tornare alla pianificazione [della rete e all'ottimizzazione delle prestazioni per Office 365.](https://aka.ms/tune)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Panoramica dell'utilizzo della rete CDN di Office 365 in SharePoint Online

Per configurare la rete CDN di Office 365 per l'organizzazione, attenersi alla seguente procedura di base:

+ [Pianificare la distribuzione della rete CDN di Office 365](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Determinare quali risorse statiche si desidera ospitare nella rete CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Determinare dove archiviare le risorse.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Questo percorso può essere un sito, una raccolta o una cartella di SharePoint ed è denominato _origine._
  + [Scegliere se ogni origine deve essere pubblica o privata.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) È possibile aggiungere più origini di tipi pubblici e privati.

+ Configurare la rete CDN tramite PowerShell o l'interfaccia dell'interfaccia utente di SharePoint Online

  + [Configurare la rete CDN tramite SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Configurare la rete CDN tramite PowerShell PnP](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Configurare la rete CDN tramite l'interfaccia cli di Office 365](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Al termine di questo passaggio, si avranno le seguenti informazioni:

  + È stata abilitata la rete CDN per l'organizzazione.
  + Sono state aggiunte le origini, identificando ogni origine come pubblica o privata.

Al termine dell'installazione, è possibile gestire la rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) nel tempo:
  
+ Aggiunta, aggiornamento e rimozione di risorse
+ Aggiunta e rimozione di origini
+ Configurazione dei criteri per la rete CDN
+ Se necessario, disabilitando la rete CDN

Infine, vedi Uso delle risorse della rete [CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) per informazioni sull'accesso alle risorse della rete CDN da origini pubbliche e private.

Per indicazioni sulla risoluzione dei problemi comuni, vedere Risoluzione dei problemi relativi alla rete CDN di [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Pianificare la distribuzione della rete CDN di Office 365

Prima di distribuire la rete CDN di Office 365 per il tenant di Office 365, è necessario considerare i fattori seguenti come parte del processo di pianificazione.

  + [Determinare quali risorse statiche si desidera ospitare nella rete CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Determinare dove archiviare le risorse](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Scegliere se ogni origine deve essere pubblica o privata](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Determinare quali risorse statiche si desidera ospitare nella rete CDN

In generale, le reti CDN sono più efficaci per ospitare asset _statici_ o asset che non cambiano molto spesso. Una buona regola generale è identificare i file che soddisfano alcune o tutte queste condizioni:

+ File statici incorporati in una pagina (ad esempio script e immagini) che possono avere un impatto incrementale significativo sui tempi di caricamento delle pagine
+ File di grandi dimensioni come eseguibili e file di installazione
+ Librerie di risorse che supportano il codice sul lato client

Ad esempio, file di piccole dimensioni richiesti ripetutamente come immagini e script del sito possono migliorare in modo significativo le prestazioni di rendering del sito e ridurre in modo incrementale il carico sui siti di SharePoint Online quando vengono aggiunti a un'origine CDN. File di dimensioni maggiori, ad esempio eseguibili di installazione, possono essere scaricati dalla rete CDN, con un impatto positivo sulle prestazioni e una conseguente riduzione del carico sul sito di SharePoint Online, anche se non vi si accede con la frequenza richiesta.

Il miglioramento delle prestazioni in base ai file dipende da molti fattori, tra cui la prossimità del client all'endpoint della rete CDN più vicino, le condizioni temporanee sulla rete locale e così via. Molti file statici sono piuttosto piccoli e possono essere scaricati da Office 365 in meno di un secondo. Tuttavia, una pagina Web può contenere molti file incorporati con un tempo di download cumulativo di diversi secondi. La pubblicazione di questi file dalla rete CDN può ridurre in modo significativo il tempo di caricamento complessivo delle pagine. Vedere [Quali miglioramenti delle prestazioni offre una rete CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) Per un esempio.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Determinare dove archiviare le risorse

La rete CDN recupera le risorse da una posizione denominata _origine._ Un'origine può essere un sito di SharePoint, una raccolta documenti o una cartella accessibile da un URL. Quando si specificano le origini per l'organizzazione, è possibile disporre di una notevole flessibilità. Ad esempio, è possibile specificare più origini o una singola origine in cui inserire tutti gli asset della rete CDN. È possibile scegliere di avere origini pubbliche o private per l'organizzazione. La maggior parte delle organizzazioni sceglie di implementare una combinazione di queste due soluzioni.

È possibile creare un nuovo contenitore per le origini, ad esempio cartelle o raccolte documenti, e aggiungere i file che si desidera rendere disponibili dalla rete CDN. Si tratta di un approccio utile se si dispone di un set specifico di risorse che si desidera essere disponibili dalla rete CDN e si desidera limitare il set di asset della rete CDN solo a tali file nel contenitore.

È inoltre possibile configurare una raccolta siti, un sito, una raccolta o una cartella esistente come origine, in modo da rendere tutti gli asset idonei nel contenitore disponibili dalla rete CDN. Prima di aggiungere un contenitore esistente come origine, è importante assicurarsi di conoscere il contenuto e le autorizzazioni in modo da non esporre inavvertitamente le risorse agli utenti anonimi o non autorizzati.

È possibile definire _criteri per la rete CDN_ per escludere il contenuto delle origini dalla rete CDN. I criteri cdn escludono le risorse in origini pubbliche o private da attributi quali il tipo di _file_ e la classificazione del sito e vengono applicati a tutte le origini di CdnType (privato o pubblico) specificato nei criteri. Ad esempio, se si aggiunge un'origine privata costituita da un sito contenente più siti  secondari, è possibile definire un criterio per escludere i siti contrassegnati come Riservati in modo che il contenuto dei siti a cui è applicata la classificazione non sia servito dalla rete CDN. Il criterio verrà applicato al contenuto _di_ tutte le origini private aggiunte alla rete CDN.
  
Tenere presente che maggiore è il numero di origini, maggiore sarà l'impatto sul tempo necessario al servizio CDN per elaborare le richieste. È consigliabile limitare il più possibile il numero di origini.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Scegliere se ogni origine deve essere pubblica o privata

Quando si identifica un'origine, è necessario specificare se deve essere resa _pubblica_ o _privata._ L'accesso alle risorse cdn in origini pubbliche è anonimo e il contenuto della rete CDN in origini private è protetto da token generati dinamicamente per una maggiore sicurezza. Indipendentemente dall'opzione scelta, Microsoft fa tutto il lavoro necessario per l'amministrazione della rete CDN stessa. Inoltre, è possibile cambiare idea in un secondo momento, dopo aver configurato la rete CDN e identificato le origini.

Entrambe le opzioni pubbliche e private offrono prestazioni simili, ma ognuna presenta attributi e vantaggi univoci.

**Le** origini pubbliche all'interno della rete CDN di Office 365 sono accessibili in modo anonimo ed è possibile accedere alle risorse ospitate da chiunque abbia l'URL dell'asset. Dal momento che l'accesso al contenuto in origini pubbliche è anonimo, è consigliabile usarle solo per memorizzare nella cache contenuti generici non riservati, ad esempio file JavaScript, script, icone e immagini.

**Le** origini private all'interno della rete CDN di Office 365 forniscono accesso privato al contenuto degli utenti, ad esempio raccolte documenti, siti e immagini proprietarie di SharePoint Online. L'accesso al contenuto in origini private è protetto da token generati dinamicamente in modo che sia accessibile solo agli utenti con autorizzazioni per la raccolta documenti originale o il percorso di archiviazione. Le origini private nella rete CDN di Office 365 possono essere usate solo per il contenuto di SharePoint Online ed è possibile accedere alle risorse in origini private solo tramite il reindirizzamento dal tenant di SharePoint Online.

Per altre informazioni sul funzionamento dell'accesso della rete CDN alle risorse in un'origine privata, vedere [Uso di risorse in origini private.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Attributi e vantaggi dell'hosting di risorse in origini pubbliche
  
+ Gli asset esposti in un'origine pubblica sono accessibili da tutti in modo anonimo.
    > [!IMPORTANT]
    > Non inserire mai risorse che contengono informazioni sull'utente o che sono considerate sensibili all'organizzazione in un'origine pubblica.
+ Se si rimuove un asset da un'origine pubblica, l'asset potrebbe continuare a essere disponibile per un massimo di 30 giorni dalla cache. Tuttavia, i collegamenti all'asset nella rete CDN verranno invalidati entro 15 minuti.
+ Quando si ospitano fogli di stile (file CSS) in un'origine pubblica, è possibile utilizzare percorsi e URI relativi all'interno del codice. Ciò significa che puoi fare riferimento alla posizione delle immagini di sfondo e di altri oggetti rispetto alla posizione dell'asset che la chiama.
+ Sebbene sia possibile codificare a livello di codice l'URL di un'origine pubblica, questa operazione non è consigliata. Il motivo è che se l'accesso alla rete CDN diventa non disponibile, l'URL non verrà risolto automaticamente nell'organizzazione in SharePoint Online e potrebbe causare collegamenti interrotti e altri errori.
+ I tipi di file predefiniti inclusi per le origini pubbliche sono .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2. È possibile specificare tipi di file aggiuntivi.
+ È possibile configurare un criterio per escludere le risorse identificate dalle classificazioni del sito specificate. Ad esempio, è possibile scegliere di escludere tutte le risorse contrassegnate come "riservate" o "limitate" anche se sono un tipo di file consentito e si trovano in un'origine pubblica.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Attributi e vantaggi dell'hosting di risorse in origini private

+ Le origini private possono essere utilizzate solo per le risorse di SharePoint Online.
+ Gli utenti possono accedere alle risorse da un'origine privata solo se dispongono delle autorizzazioni per accedere al contenitore. L'accesso anonimo a queste risorse non è consentito.
+ Le risorse di origini private devono essere indicate dal tenant di SharePoint Online. L'accesso diretto alle risorse della rete CDN privata non funziona.
+ Se si rimuove un asset dall'origine privata, l'asset potrebbe continuare a essere disponibile fino a un'ora dalla cache. Tuttavia, i collegamenti all'asset nella rete CDN verranno invalidati entro 15 minuti dalla rimozione dell'asset.
+ I tipi di file predefiniti inclusi per le origini private sono .gif, .ico, .jpeg, .jpg, .js e .png. È possibile specificare tipi di file aggiuntivi.
+ Analogamente alle origini pubbliche, è possibile configurare un criterio per escludere le risorse identificate dalle classificazioni dei siti specificate anche se si utilizzano caratteri jolly per includere tutte le risorse all'interno di una cartella o di una raccolta documenti.

Per ulteriori informazioni sul motivo per cui usare la rete CDN di Office 365, i concetti generali della rete CDN e altre reti CDN Microsoft che è possibile usare con il tenant di Office 365, vedere Reti per la distribuzione di [contenuti.](content-delivery-networks.md)

### <a name="default-cdn-origins"></a>Origini predefinite della rete CDN

Se non diversamente specificato, Office 365 configura automaticamente alcune origini predefinite quando si abilita la rete CDN di Office 365. Se inizialmente scegli di non eseguirle, puoi aggiungere queste origini dopo aver completato la configurazione. A meno che non si comprenda le conseguenze del saltare la configurazione delle origini predefinite e non si abbia un motivo specifico per farlo, è consigliabile consentirne la creazione quando si abilita la rete CDN.
  
Origini predefinite della rete CDN privata:
  
+ \*/userphoto.aspx
+ \*/siteassets

Origini predefinite della rete CDN pubblica:
  
+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ è un'origine pubblica predefinita aggiunta al servizio CDN di Office 365 a dicembre 2017. Questa origine deve essere presente perché le soluzioni SharePoint Framework nella rete CDN funzionino. Se la rete CDN di Office 365 è stata abilitata prima di dicembre 2017 o se è stata ignorata la configurazione delle origini predefinite quando è stata abilitata la rete CDN, è possibile aggiungere manualmente questa origine. Per ulteriori informazioni, vedere La web part sul lato client o la soluzione [SharePoint Framework non funziona.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Configurare la rete CDN di Office 365 tramite SharePoint Online Management Shell

Le procedure descritte in questa sezione richiedono l'utilizzo di SharePoint Online Management Shell per connettersi a SharePoint Online. Per istruzioni, vedere [Connettersi a PowerShell di SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

Completare questi passaggi per configurare la rete CDN per ospitare le risorse in SharePoint Online tramite SharePoint Online Management Shell.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Abilitare l'organizzazione a usare la rete CDN di Office 365

Prima di apportare modifiche alle impostazioni della rete CDN del tenant, è necessario recuperare lo stato corrente della configurazione della rete CDN privata nel tenant di Office 365. Connettersi al tenant tramite SharePoint Online Management Shell:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

A questo punto, utilizzare il cmdlet **Get-SPOTenantCdnEnabled** per recuperare le impostazioni di stato della rete CDN dal tenant:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Lo stato della rete CDN per l'oggetto CdnType specificato verrà visualizzato sullo schermo.

Utilizzare il cmdlet **Set-SPOTenantCdnEnabled** per consentire all'organizzazione di utilizzare la rete CDN di Office 365. È possibile consentire all'organizzazione di usare origini pubbliche, origini private o entrambe contemporaneamente. Puoi anche configurare la rete CDN in modo da ignorare la configurazione delle origini predefinite quando la abiliti. È sempre possibile aggiungere queste origini più avanti, come descritto in questo argomento.
  
In Windows PowerShell per SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Ad esempio, per consentire all'organizzazione di utilizzare sia origini pubbliche che private, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Per consentire all'organizzazione di utilizzare origini pubbliche e private ma ignorare la configurazione delle origini predefinite, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Vedere [Origini della rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinita per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365 e il potenziale impatto di ignorare la configurazione delle origini predefinite.

Per consentire all'organizzazione di utilizzare origini pubbliche, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Per ulteriori informazioni su questo cmdlet, vedere [Set-SPOTenantCdnEnabled.](https://technet.microsoft.com/library/mt790765.aspx)

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

Per visualizzare i tipi di file attualmente consentiti dalla rete CDN, utilizzare il cmdlet **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Per ulteriori informazioni su questi cmdlet, vedere [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) e [Get-SPOTenantCdnPolicies.](https://technet.microsoft.com/library/mt800838.aspx)

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si escludono le classificazioni dei siti utilizzando il cmdlet **Set-SPOTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito. Se si desidera escludere ulteriori classificazioni del sito, utilizzare prima il cmdlet per individuare le classificazioni già escluse e quindi aggiungerle insieme alle nuove.

Utilizzare il cmdlet **Set-SPOTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili sulla rete CDN. Per impostazione predefinita, non vengono escluse classificazioni di siti.

In Windows PowerShell per SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Per sapere quali classificazioni di siti sono attualmente limitate, utilizzare il cmdlet **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Le proprietà che verranno restituite _sono IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ _e ExcludeIfNoScriptDisabled._

La _proprietà IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno gestite dalla rete CDN.

> [!NOTE]
> Le estensioni di file predefinite sono diverse tra pubblico e privato.

La _proprietà ExcludeRestrictedSiteClassifications_ contiene le classificazioni dei siti che si desidera escludere dalla rete CDN. Ad esempio, è possibile  escludere i siti contrassegnati come Riservati in modo che il contenuto dei siti a cui è applicata tale classificazione non verrà servito dalla rete CDN.

La _proprietà ExcludeIfNoScriptDisabled_ esclude il contenuto dalla rete CDN in base alle impostazioni dell'attributo _NoScript_ a livello di sito. Per impostazione predefinita, _l'attributo NoScript_ è impostato su **Abilitato** per i _siti_ moderni **e disabilitato** per _i siti_ classici. Dipende dalle impostazioni del tenant.

Per ulteriori informazioni su questi cmdlet, vedere [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) e [Get-SPOTenantCdnPolicies.](https://technet.microsoft.com/library/mt800838.aspx)

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Aggiungere un'origine per le risorse

Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire un'origine. È possibile definire più origini. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.
  
> [!IMPORTANT]
> Non inserire mai risorse che contengono informazioni sull'utente o che sono considerate sensibili all'organizzazione in un'origine pubblica.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Il valore _del percorso_ è il percorso relativo alla raccolta o alla cartella che contiene gli asset. Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly. Origins supporta i caratteri jolly anteposti all'URL. In questo modo è possibile creare origini che si estendono su più siti. Ad esempio, per includere tutte le risorse nella cartella masterpages di tutti i siti come origine pubblica all'interno della rete CDN, digitare il comando seguente:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Il modificatore con caratteri jolly * può essere utilizzato solo all'inizio del percorso e corrisponderà a tutti i **/** segmenti di URL nell'URL specificato.
+ Il percorso può puntare a una raccolta documenti, una cartella o un sito. Ad esempio, il percorso _*/site1_ corrisponderà a tutte le raccolte documenti del sito.

È possibile aggiungere un'origine con un percorso relativo specifico. Non è possibile aggiungere un'origine utilizzando il percorso completo.

In questo esempio viene aggiunta un'origine privata della raccolta siti in un sito specifico:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In questo esempio viene aggiunta un'origine privata della _cartella folder1_ nella raccolta di risorse del sito della raccolta siti:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Se nel percorso è presente uno spazio, è possibile racchiudere il percorso tra virgolette doppie o sostituire lo spazio con la codifica URL %20. Negli esempi seguenti viene aggiunta un'origine privata della cartella _1_ nella raccolta di risorse del sito della raccolta siti:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)

> [!NOTE]
> Nelle origini private, le risorse condivise da un'origine devono avere una versione principale pubblicata prima di poter essere accessibili dalla rete CDN.
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. Questa operazione può richiedere fino a 15 minuti.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Esempio: Configurare un'origine pubblica per le pagine master e per la raccolta stili per SharePoint Online

In genere, queste origini vengono impostate automaticamente quando si abilita la rete CDN di Office 365. Tuttavia, se si desidera abilitarle manualmente, eseguire la procedura seguente.
  
+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la libreria di stili come origine pubblica.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire le pagine master come origine pubblica.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)

Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. Questa operazione può richiedere fino a 15 minuti.

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

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)

Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. Questa operazione può richiedere fino a 15 minuti.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Esempio: Configurare un'origine privata per una raccolta siti per SharePoint Online

Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire una raccolta siti come origine privata. Ad esempio:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service. Questa operazione può richiedere fino a 15 minuti.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Gestire la rete CDN di Office 365

Dopo aver configurato la rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle esigenze, come descritto in questa sezione.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Aggiungere, aggiornare o rimuovere asset dalla rete CDN di Office 365

Dopo aver completato i passaggi di configurazione, puoi aggiungere nuovi asset e aggiornare o rimuovere le risorse esistenti quando vuoi. È sufficiente apportare le modifiche alle risorse nella cartella o nella raccolta di SharePoint identificata come origine. Se aggiungi un nuovo asset, questo sarà immediatamente disponibile tramite la rete CDN. Se tuttavia si aggiorna l'asset, la propagazione della nuova copia e la disponibilità della nuova copia nella rete CDN saranno fino a 15 minuti.
  
Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-SPOTenantCdnOrigins.** Per informazioni su come utilizzare questo cmdlet, vedere [Get-SPOTenantCdnOrigins.](https://technet.microsoft.com/library/mt790770.aspx)

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Rimuovere un'origine dalla rete CDN di Office 365

È possibile rimuovere l'accesso a una cartella o a una raccolta di SharePoint identificata come origine. A tale scopo, utilizzare il cmdlet **Remove-SPOTenantCdnOrigin.**

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Per informazioni su come utilizzare questo cmdlet, vedere [Remove-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790761.aspx)

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificare un'origine nella rete CDN di Office 365

Non è possibile modificare un'origine creata. Rimuovi invece l'origine e quindi aggiungine una nuova. Per ulteriori informazioni, vedere Per rimuovere un'origine dalla rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) e Per aggiungere un'origine [per le risorse.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Utilizzare il cmdlet **Set-SPOTenantCdnEnabled** per disabilitare la rete CDN per l'organizzazione. Se per la rete CDN sono abilitate sia l'origine pubblica che l'origine privata, è necessario eseguire il cmdlet due volte, come illustrato negli esempi seguenti.
  
Per disabilitare l'uso di origini pubbliche nella rete CDN, immettere il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Per disabilitare l'uso delle origini private nella rete CDN, immettere il comando seguente:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Per ulteriori informazioni su questo cmdlet, vedere [Set-SPOTenantCdnEnabled.](https://technet.microsoft.com/library/mt790765.aspx)

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Configurare la rete CDN di Office 365 tramite PowerShell PnP

Le procedure descritte in questa sezione richiedono l'utilizzo di PnP PowerShell per connettersi a SharePoint Online. Per istruzioni, vedere [Introduzione a PnP PowerShell.](https://github.com/SharePoint/PnP-PowerShell#getting-started)

Completare questi passaggi per configurare la rete CDN per ospitare le risorse in SharePoint Online tramite PowerShell PnP.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Abilitare l'organizzazione a usare la rete CDN di Office 365

Prima di apportare modifiche alle impostazioni della rete CDN del tenant, è necessario recuperare lo stato corrente della configurazione della rete CDN privata nel tenant di Office 365. Connettersi al tenant tramite PowerShell PnP:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

A questo punto, utilizzare il cmdlet **Get-PnPTenantCdnEnabled** per recuperare le impostazioni di stato della rete CDN dal tenant:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Lo stato della rete CDN per l'oggetto CdnType specificato verrà visualizzato sullo schermo.

Utilizzare il cmdlet **Set-PnPTenantCdnEnabled** per consentire all'organizzazione di utilizzare la rete CDN di Office 365. È possibile consentire all'organizzazione di usare origini pubbliche, origini private o entrambe contemporaneamente. Puoi anche configurare la rete CDN in modo da ignorare la configurazione delle origini predefinite quando la abiliti. È sempre possibile aggiungere queste origini più avanti, come descritto in questo argomento.
  
In PowerShell PnP:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Ad esempio, per consentire all'organizzazione di utilizzare sia origini pubbliche che private, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Per consentire all'organizzazione di utilizzare origini pubbliche e private ma ignorare la configurazione delle origini predefinite, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Vedere [Origini della rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinita per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365 e il potenziale impatto di ignorare la configurazione delle origini predefinite.

Per consentire all'organizzazione di utilizzare origini pubbliche, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Per ulteriori informazioni su questo cmdlet, vedere [Set-PnPTenantCdnEnabled.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

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

Per ulteriori informazioni su questi cmdlet, vedere [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365 (facoltativo)

> [!TIP]
> Quando si escludono le classificazioni dei siti utilizzando il cmdlet **Set-PnPTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito. Se si desidera escludere ulteriori classificazioni del sito, utilizzare prima il cmdlet per individuare le classificazioni già escluse e quindi aggiungerle insieme alle nuove.

Utilizzare il cmdlet **Set-PnPTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili sulla rete CDN. Per impostazione predefinita, non vengono escluse classificazioni di siti.

In PowerShell PnP:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Per sapere quali classificazioni di sito sono attualmente limitate, utilizzare il cmdlet **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Le proprietà che verranno restituite _sono IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ _e ExcludeIfNoScriptDisabled._

La _proprietà IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno gestite dalla rete CDN.

> [!NOTE]
> Le estensioni di file predefinite sono diverse tra pubblico e privato.

La _proprietà ExcludeRestrictedSiteClassifications_ contiene le classificazioni dei siti che si desidera escludere dalla rete CDN. Ad esempio, è possibile  escludere i siti contrassegnati come Riservati in modo che il contenuto dei siti a cui è applicata tale classificazione non verrà servito dalla rete CDN.

La _proprietà ExcludeIfNoScriptDisabled_ esclude il contenuto dalla rete CDN in base alle impostazioni dell'attributo _NoScript_ a livello di sito. Per impostazione predefinita, _l'attributo NoScript_ è impostato su **Abilitato** per i _siti_ moderni **e disabilitato** per _i siti_ classici. Dipende dalle impostazioni del tenant.

Per ulteriori informazioni su questi cmdlet, vedere [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Aggiungere un'origine per le risorse

Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire un'origine. È possibile definire più origini. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.
  
> [!IMPORTANT]
> Non inserire mai risorse che contengono informazioni sull'utente o che sono considerate sensibili all'organizzazione in un'origine pubblica.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Il valore _del percorso_ è il percorso relativo alla raccolta o alla cartella che contiene gli asset. Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly. Origins supporta i caratteri jolly anteposti all'URL. In questo modo è possibile creare origini che si estendono su più siti. Ad esempio, per includere tutte le risorse nella cartella masterpages di tutti i siti come origine pubblica all'interno della rete CDN, digitare il comando seguente:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Il modificatore con caratteri jolly * può essere utilizzato solo all'inizio del percorso e corrisponderà a tutti i **/** segmenti di URL nell'URL specificato.
+ Il percorso può puntare a una raccolta documenti, una cartella o un sito. Ad esempio, il percorso _*/site1_ corrisponderà a tutte le raccolte documenti del sito.

È possibile aggiungere un'origine con un percorso relativo specifico. Non è possibile aggiungere un'origine utilizzando il percorso completo.

In questo esempio viene aggiunta un'origine privata della raccolta di risorse del sito in un sito specifico:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In questo esempio viene aggiunta un'origine privata della _cartella folder1_ nella raccolta di risorse del sito della raccolta siti:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Se nel percorso è presente uno spazio, è possibile racchiudere il percorso tra virgolette doppie o sostituire lo spazio con la codifica URL %20. Negli esempi seguenti viene aggiunta un'origine privata della cartella _1_ nella raccolta di risorse del sito della raccolta siti:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

> [!NOTE]
> Nelle origini private, le risorse condivise da un'origine devono avere una versione principale pubblicata prima di poter essere accessibili dalla rete CDN.
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. Questa operazione può richiedere fino a 15 minuti.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Esempio: Configurare un'origine pubblica per le pagine master e per la raccolta stili per SharePoint Online

In genere, queste origini vengono impostate automaticamente quando si abilita la rete CDN di Office 365. Tuttavia, se si desidera abilitarle manualmente, eseguire la procedura seguente.
  
+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la libreria di stili come origine pubblica.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire le pagine master come origine pubblica.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. Questa operazione può richiedere fino a 15 minuti.

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

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. Questa operazione può richiedere fino a 15 minuti.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Esempio: Configurare un'origine privata per una raccolta siti per SharePoint Online

Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire una raccolta siti come origine privata. Ad esempio:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)
  
Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter. You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service. Questa operazione può richiedere fino a 15 minuti.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Gestire la rete CDN di Office 365

Dopo aver configurato la rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle esigenze, come descritto in questa sezione.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Aggiungere, aggiornare o rimuovere asset dalla rete CDN di Office 365

Dopo aver completato i passaggi di configurazione, puoi aggiungere nuovi asset e aggiornare o rimuovere le risorse esistenti quando vuoi. È sufficiente apportare le modifiche alle risorse nella cartella o nella raccolta di SharePoint identificata come origine. Se aggiungi un nuovo asset, questo sarà immediatamente disponibile tramite la rete CDN. Se tuttavia si aggiorna l'asset, la propagazione della nuova copia e la disponibilità della nuova copia nella rete CDN saranno fino a 15 minuti.
  
Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-PnPTenantCdnOrigin.** Per informazioni su come utilizzare questo cmdlet, vedere [Get-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Rimuovere un'origine dalla rete CDN di Office 365

È possibile rimuovere l'accesso a una cartella o a una raccolta di SharePoint identificata come origine. A tale scopo, utilizzare il cmdlet **Remove-PnPTenantCdnOrigin.**

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Per informazioni su come utilizzare questo cmdlet, vedere [Remove-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificare un'origine nella rete CDN di Office 365

Non è possibile modificare un'origine creata. Rimuovi invece l'origine e quindi aggiungine una nuova. Per ulteriori informazioni, vedere Per rimuovere un'origine dalla rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) e Per aggiungere un'origine [per le risorse.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Utilizzare il cmdlet **Set-PnPTenantCdnEnabled** per disabilitare la rete CDN per l'organizzazione. Se per la rete CDN sono abilitate sia l'origine pubblica che l'origine privata, è necessario eseguire il cmdlet due volte, come illustrato negli esempi seguenti.
  
Per disabilitare l'uso di origini pubbliche nella rete CDN, immettere il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Per disabilitare l'uso delle origini private nella rete CDN, immettere il comando seguente:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Per ulteriori informazioni su questo cmdlet, vedere [Set-PnPTenantCdnEnabled.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Configurare la rete CDN di Office 365 tramite l'interfaccia cli di Office 365

Le procedure descritte in questa sezione richiedono l'installazione dell'interfaccia della riga di comando di [Office 365.](https://aka.ms/o365cli) Successivamente, connettersi al tenant di Office 365 usando il [comando di](https://pnp.github.io/office365-cli/cmd/login/) accesso.

Completare questi passaggi per configurare la rete CDN per ospitare le risorse in SharePoint Online tramite l'interfaccia cli di Office 365.

<details>
  <summary>Fare clic per espandere</summary>

### <a name="enable-the-office-365-cdn"></a>Abilitare la rete CDN di Office 365

È possibile gestire lo stato della rete CDN di Office 365 nel tenant usando il comando [spo cdn set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)

Per abilitare la rete CDN pubblica di Office 365 nel tenant, eseguire:

```sh
spo cdn set --type Public --enabled true
```

Per abilitare la rete CDN di Office 365 SharePoint, eseguire:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Visualizzare lo stato corrente della rete CDN di Office 365

Per verificare se il tipo specifico di rete CDN di Office 365 è abilitato o disabilitato, usare il comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)

Per verificare se la rete CDN pubblica di Office 365 è abilitata, eseguire:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Visualizzare le origini della rete CDN di Office 365

Per visualizzare le origini della rete CDN pubblica di Office 365 attualmente configurate, eseguire:

```sh
spo cdn origin list --type Public
```

Vedere [Origini della rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinita per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365.

### <a name="add-an-office-365-cdn-origin"></a>Aggiungere un'origine cdN di Office 365

> [!IMPORTANT]
> Non inserire mai risorse considerate sensibili per l'organizzazione in una raccolta documenti di SharePoint configurata come origine pubblica.

Utilizzare il [comando spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) per definire un'origine CDN. È possibile definire più origini. L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Dove `path` è il percorso relativo della cartella che contiene gli asset. Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly.

Per includere tutte le risorse nella raccolta pagine **master** di tutti i siti come origine pubblica, eseguire:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Per configurare un'origine privata per una raccolta siti specifica, eseguire:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Dopo aver aggiunto un'origine CDN, potrebbero essere necessari fino a 15 minuti prima che tu sia in grado di recuperare i file tramite il servizio CDN. È possibile verificare se la determinata origine è già stata abilitata utilizzando il comando [spo cdn origin list.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/)

### <a name="remove-an-office-365-cdn-origin"></a>Rimuovere un'origine della rete CDN di Office 365

Utilizzare il [comando spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) per rimuovere un'origine CDN per il tipo di rete CDN specificato.

Per rimuovere un'origine pubblica dalla configurazione della rete CDN, eseguire:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> La rimozione di un'origine CDN non influisce sui file archiviati in alcuna raccolta documenti corrispondente a tale origine. Se si fa riferimento a queste risorse utilizzando l'URL di SharePoint, SharePoint tornerà automaticamente all'URL originale che punta alla raccolta documenti. Se, tuttavia, è stato fatto riferimento alle risorse utilizzando un URL della rete CDN pubblica, la rimozione dell'origine interromperà il collegamento e sarà necessario modificarli manualmente.

### <a name="modify-an-office-365-cdn-origin"></a>Modificare un'origine della rete CDN di Office 365

Non è possibile modificare un'origine CDN esistente. È invece consigliabile rimuovere l'origine della rete CDN definita in precedenza utilizzando il comando e `spo cdn origin remove` aggiungerne una nuova utilizzando il `spo cdn origin add` comando.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Modificare i tipi di file da includere nella rete CDN di Office 365

Per impostazione predefinita, nella rete CDN sono inclusi i tipi di file seguenti: _css, eot, gif, ico, jpeg, jpg, js, map, png, svg, ttf, woff e woff2._ Se è necessario includere tipi di file aggiuntivi nella rete CDN, è possibile modificare la configurazione della rete CDN utilizzando il comando [spo cdn policy set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)

> [!NOTE]
> Quando si modifica l'elenco dei tipi di file, si sovrascrive l'elenco attualmente definito. Se si desidera includere tipi di file aggiuntivi, utilizzare innanzitutto il comando dell'elenco dei criteri per la rete [cdn di Spo](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) per individuare i tipi di file attualmente configurati.

Per aggiungere il _tipo di_ file JSON all'elenco predefinito dei tipi di file inclusi nella rete CDN pubblica, eseguire:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365

Utilizzare il [comando spo cdn policy set per](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) escludere le classificazioni dei siti che non si desidera rendere disponibili nella rete CDN. Per impostazione predefinita, non vengono escluse classificazioni di siti.

> [!NOTE]
> Quando si modifica l'elenco delle classificazioni di sito escluse, si sovrascrive l'elenco attualmente definito. Se si desidera escludere classificazioni aggiuntive, utilizzare innanzitutto il comando dell'elenco dei criteri per la rete [cdn di Spo](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) per individuare le classificazioni attualmente configurate.

Per escludere i siti _classificati come HBI_ dalla rete CDN pubblica, eseguire

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Disabilitare la rete CDN di Office 365

Per disabilitare la rete CDN di Office 365, utilizzare `spo cdn set` il comando, ad esempio:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Uso delle risorse della rete CDN

Dopo aver abilitato la rete CDN e configurato origini e criteri, è possibile iniziare a usare le risorse della rete CDN.

In questa sezione viene illustrato come utilizzare gli URL della rete CDN nelle pagine e nel contenuto di SharePoint in modo che SharePoint reindirizza le richieste di risorse sia di origine pubblica che privata alla rete CDN.

+ [Aggiornamento dei collegamenti alle risorse della rete CDN](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Uso di risorse in origini pubbliche](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Uso di risorse in origini private](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Per informazioni su come usare la rete CDN per ospitare web part sul lato client, vedere l'argomento Ospitare la web part sul lato client dalla rete CDN di [Office 365 (Hello World parte 4).](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)

> [!NOTE]
> Se si aggiunge la _cartella ClientSideAssets_ all'elenco delle origini **della** rete CDN privata, il rendering delle web part personalizzate ospitate dalla rete CDN non verrà eseguito. I file utilizzati dalle web part SPFX possono utilizzare solo la rete CDN pubblica e la cartella ClientSideAssets è un'origine predefinita per la rete CDN pubblica. 

### <a name="updating-links-to-cdn-assets"></a>Aggiornamento dei collegamenti alle risorse della rete CDN

Per utilizzare gli asset aggiunti a un'origine, è sufficiente aggiornare i collegamenti al file originale con il percorso del file nell'origine.

+ Modificare la pagina o il contenuto che contiene i collegamenti alle risorse aggiunte a un'origine. È inoltre possibile utilizzare uno dei diversi metodi per cercare e sostituire a livello globale i collegamenti in un sito o una raccolta siti immessi se si desidera aggiornare il collegamento a un determinato asset ovunque venga visualizzato.
+ Per ogni collegamento a un asset in un'origine, sostituire il percorso con il percorso del file nell'origine della rete CDN. È possibile utilizzare percorsi relativi.
+ Salvare la pagina o il contenuto.

Si consideri ad esempio l'immagine _/site/SiteAssets/images/image.png,_ copiata nella cartella della raccolta documenti _/site/CDN_origins/public/._ Per utilizzare l'asset cdn, sostituire il percorso originale del file di immagine con il percorso dell'origine per rendere il nuovo URL _/site/CDN_origins/public/image.png_.

Se vuoi usare l'URL completo dell'asset invece di un percorso relativo, crea il collegamento in questo modo:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> In generale, non è consigliabile codificare gli URL direttamente agli asset nella rete CDN. Tuttavia, è possibile creare manualmente url per gli asset di origini pubbliche, se necessario. Per ulteriori informazioni, vedere [Hardcoding CDN URLs for public assets.](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets)

Per informazioni su come verificare che le risorse vengano servite dalla rete CDN, vedere Come verificare che le risorse siano servite dalla [rete CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) nella sezione risoluzione dei problemi della rete CDN di [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>Uso di risorse in origini pubbliche

La **funzionalità** di pubblicazione in SharePoint Online riscrive automaticamente gli URL delle risorse archiviate in origini pubbliche negli equivalenti della rete CDN in modo che le risorse siano servite dal servizio CDN anziché da SharePoint.

Se l'origine si trova in un sito con la caratteristica Pubblicazione abilitata e le risorse che si desidera scaricare nella rete CDN sono in una delle categorie seguenti, SharePoint riscriverà automaticamente gli URL delle risorse nell'origine, purché l'asset non sia stato escluso da un criterio cdn.

Di seguito è riportata una panoramica dei collegamenti che vengono riscritti automaticamente dalla caratteristica Pubblicazione SharePoint:

+ URL IMG/LINK/CSS nelle risposte HTML delle pagine di pubblicazione classiche
  + Sono incluse le immagini aggiunte dagli autori all'interno del contenuto HTML di una pagina
+ URL immagine web part Raccolta immagini SlideShow
+ Campi immagine nei risultati dell'API REST SPList (RenderListDataAsStream)
  + Utilizzare la nuova proprietà _ImageFieldsToTryRewriteToCdnUrls_ per fornire un elenco delimitato da virgole di campi
  + Supporta campi collegamento ipertestuale e campi PublishingImage
+ Rendering di immagini di SharePoint

Nel diagramma seguente viene illustrato il flusso di lavoro quando SharePoint riceve una richiesta per una pagina contenente risorse da un'origine pubblica.

![Diagramma del flusso di lavoro: Recupero delle risorse della rete CDN di Office 365 da un'origine pubblica](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Flusso di lavoro: recupero di risorse della rete CDN di Office 365 da un'origine pubblica")

> [!TIP]
> Se si desidera disabilitare la riscrittura automatica per URL specifici in una pagina, è possibile estrarre la pagina e aggiungere il parametro della stringa di **query? NoAutoReWrites=true** alla fine di ogni collegamento che si desidera disabilitare.

#### <a name="hardcoding-cdn-urls-for-public-assets"></a>URL cdn hardcoding per risorse pubbliche

Se  la caratteristica pubblicazione non è abilitata per un'origine pubblica o l'asset non è uno dei tipi di collegamento supportati dalla funzionalità di riscrittura automatica del servizio CDN, è possibile creare manualmente gli URL nel percorso della rete CDN degli asset e utilizzare questi URL nel contenuto.

> [!NOTE]
> Non è possibile codificare in modo hardcoded gli URL della rete CDN per gli asset in un'origine privata perché il token di accesso necessario che costituisce l'ultima sezione dell'URL viene generato al momento della richiesta della risorsa.

Per gli asset della rete CDN pubblica, il formato dell'URL sarà simile al seguente:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Sostituire **TenantHostName** con il nome del tenant. Esempio:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a>Uso di risorse in origini private

Non è necessaria alcuna configurazione aggiuntiva per l'utilizzo di risorse in origini private. SharePoint Online riscrive automaticamente gli URL delle risorse in origini private in modo che le richieste per tali risorse siano sempre servite dalla rete CDN. Non è possibile creare manualmente URL in asset cdn in origini private perché contengono token che devono essere generati automaticamente da SharePoint Online al momento della richiesta dell'asset.

L'accesso alle risorse in origini private è protetto da token generati dinamicamente in base alle autorizzazioni utente per l'origine, con le avvertenze descritte nelle sezioni seguenti. Gli utenti devono disporre almeno **dell'accesso** in lettura alle origini per consentire il rendering del contenuto da parte della rete CDN.

Nel diagramma seguente viene illustrato il flusso di lavoro quando SharePoint riceve una richiesta per una pagina contenente risorse da un'origine privata.

![Diagramma del flusso di lavoro: Recupero delle risorse della rete CDN di Office 365 da un'origine privata](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Flusso di lavoro: recupero di asset della rete CDN di Office 365 da un'origine privata")

#### <a name="token-based-authorization-in-private-origins"></a>Autorizzazione basata su token in origini private

L'accesso alle risorse in origini private nella rete CDN di Office 365 viene concesso dai token generati da SharePoint Online. Agli utenti che dispongono già dell'autorizzazione per accedere alla cartella o alla raccolta designata dall'origine vengono automaticamente concessi token che consentono all'utente di accedere al file in base al livello di autorizzazione. Questi token di accesso sono validi da 30 a 90 minuti dopo la generazione per evitare attacchi di riproduzione dei token.

Una volta generato il token di accesso, SharePoint Online restituisce un URI personalizzato al client contenente due parametri di autorizzazione _(token_ di autorizzazione edge) e _oat_ (token di autorizzazione di origine). La struttura di ogni token è<'ora di scadenza nel formato epoche >__< _'firma sicura'>_. Ad esempio:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Chiunque sia in possesso del token può accedere alla risorsa nella rete CDN. Tuttavia, gli URL contenenti questi token di accesso vengono condivisi solo tramite HTTPS, quindi, a meno che l'URL non sia esplicitamente condiviso da un utente finale prima della scadenza del token, l'asset non sarà accessibile agli utenti non autorizzati.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Le autorizzazioni a livello di elemento non sono supportate per le risorse in origini private

È importante notare che SharePoint Online non supporta le autorizzazioni a livello di elemento per le risorse di origini private. Ad esempio, per un file che si trova in , gli utenti hanno `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` accesso effettivo al file in base alle condizioni seguenti:

|Utente  |Autorizzazioni  |Accesso efficace  |
|---------|---------|---------|
|Utente 1     |Ha accesso a folder1         |Può accedere image1.jpg dalla rete CDN         |
|Utente 2     |Non ha accesso a folder1         |Impossibile accedere image1.jpg dalla rete CDN         |
|Utente 3     |Non dispone dell'accesso a folder1, ma dispone dell'autorizzazione esplicita per accedere image1.jpg in SharePoint Online         |Può accedere alle risorse image1.jpg direttamente da SharePoint Online, ma non dalla rete CDN         |
|Utente 4     |Ha accesso a folder1, ma gli è stato esplicitamente negato l'accesso image1.jpg in SharePoint Online         |Non è possibile accedere all'asset da SharePoint Online, ma può accedere all'asset dalla rete CDN nonostante sia stato negato l'accesso al file in SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Risoluzione dei problemi relativi alla rete CDN di Office 365

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Come verificare che le risorse siano servite dalla rete CDN?

Dopo aver aggiunto i collegamenti agli asset della rete CDN a una pagina, puoi verificare che l'asset venga servito dalla rete CDN visualizzando la pagina, facendo clic con il pulsante destro del mouse sull'immagine dopo il rendering e esaminando l'URL dell'immagine.

Puoi anche usare gli strumenti di sviluppo del browser per visualizzare l'URL di ogni risorsa in una pagina o usare uno strumento di traccia di rete di terze parti.

> [!NOTE]
> Se si usa uno strumento di rete come Fiddler per testare gli asset all'esterno del rendering dell'asset da una pagina di SharePoint, è necessario aggiungere manualmente l'intestazione referer "Referer: " alla richiesta GET in cui l'URL è l'URL radice del tenant di `https://yourdomain.sharepoint.com` SharePoint Online.

Non è possibile testare gli URL della rete CDN direttamente in un Web browser perché è necessario disporre di un referenziatore proveniente da SharePoint Online. Tuttavia, se si aggiunge l'URL dell'asset della rete CDN a una pagina di SharePoint e quindi si apre la pagina in un browser, nella pagina verrà visualizzato il rendering dell'asset della rete CDN.

Per altre informazioni sull'uso degli strumenti di sviluppo nel browser Microsoft Edge, vedi [Strumenti di sviluppo di Microsoft Edge.](https://docs.microsoft.com/microsoft-edge/devtools-guide)

Per guardare un breve video ospitato nel canale YouTube dei modelli e delle procedure per sviluppatori di [SharePoint](https://aka.ms/sppnp-videos) che illustra come verificare il funzionamento della rete [CDN,](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)vedere Verificare l'utilizzo della rete CDN e garantire una connettività di rete ottimale.

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Perché le risorse di una nuova origine non sono disponibili?
Gli asset nelle nuove origini non saranno immediatamente disponibili per l'uso, perché la registrazione richiede tempo per la propagazione tramite la rete CDN e per il caricamento degli asset dall'origine all'archiviazione della rete CDN. Il tempo necessario per la disponibilità delle risorse nella rete CDN dipende dal numero di asset e dalle dimensioni dei file.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>La web part sul lato client o la soluzione SharePoint Framework non funziona

Quando si abilita la rete CDN di Office 365 per origini pubbliche, il servizio CDN crea automaticamente queste origini predefinite:

+ */MASTERPAGE
+ */STYLE LIBRARY
+ */CLIENTSIDEASSETS

Se l'origine */clientsideassets è mancante, le soluzioni di SharePoint Framework avranno esito negativo e non verranno generati messaggi di avviso o di errore. Questa origine potrebbe non essere presente perché la rete CDN è stata abilitata con il parametro _-NoDefaultOrigins_ impostato su **$true** oppure perché l'origine è stata eliminata manualmente.

È possibile verificare quali origini sono presenti con il comando PowerShell seguente:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Oppure è possibile verificare con l'interfaccia cli di Office 365:

``` powershell
spo cdn origin list
```

Per aggiungere l'origine in PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Per aggiungere l'origine nell'interfaccia cli di Office 365:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Quali moduli di PowerShell e shell cli sono necessari per utilizzare la rete CDN di Office 365?

È possibile scegliere di utilizzare la rete CDN di Office 365 usando il modulo PowerShell di **SharePoint Online Management Shell** o l'interfaccia cli di Office **365.**

+ [Guida introduttiva a SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Installazione dell'interfaccia cli di Office 365](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Vedere anche

[Reti per la distribuzione di contenuti](https://aka.ms/o365cdns)

[Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune)

[Serie di prestazioni di SharePoint - Serie di video sulla rete CDN di Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
