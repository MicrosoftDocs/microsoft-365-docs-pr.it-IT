---
title: Opzioni di spostamento per SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
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
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: In questo articolo vengono descritti i siti delle opzioni di spostamento con la pubblicazione di SharePoint abilitata in SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696078"
---
# <a name="navigation-options-for-sharepoint-online"></a>Opzioni di spostamento per SharePoint Online

In questo articolo vengono descritti i siti delle opzioni di spostamento con la pubblicazione di SharePoint abilitata in SharePoint Online. La scelta e la configurazione della struttura di spostamento incidono in modo significativo sulle prestazioni e sulla scalabilità dei siti in SharePoint Online. Il modello di sito di pubblicazione di SharePoint deve essere utilizzato solo se necessario per un portale centralizzato e la funzionalità di pubblicazione deve essere abilitata solo in siti specifici e solo quando è assolutamente necessaria perché può influire sulle prestazioni se utilizzata in modo errato.

>[!NOTE]
>Se si utilizzano le opzioni di spostamento di SharePoint moderne come menu Mega, spostamento a cascata o spostamento Hub, questo articolo non si applica al sito. Le architetture di siti di SharePoint moderne sfruttano una gerarchia di siti più appiattita e un modello hub e spoke. In questo modo è possibile ottenere numerosi scenari che non richiedono l'utilizzo della caratteristica di pubblicazione di SharePoint.

## <a name="overview-of-navigation-options"></a>Panoramica delle opzioni di spostamento

La configurazione del provider di spostamento può influire in modo significativo sulle prestazioni per l'intero sito e è necessario prendere in considerazione attentamente la scelta di un provider di spostamento e una configurazione in grado di ridimensionare efficacemente i requisiti di un sito di SharePoint. Sono disponibili due provider di spostamento fuori dalla casella, nonché implementazioni di spostamento personalizzate.

La prima opzione, la [**struttura di spostamento strutturale**](#using-structural-navigation-in-sharepoint-online), è l'opzione di spostamento consigliata in SharePoint Online per i siti di SharePoint classici, **se si attiva la memorizzazione nella cache di spostamento strutturale per il sito**. In questo provider di spostamento vengono visualizzate le voci di spostamento al di sotto del sito corrente e, facoltativamente, il sito corrente e i relativi elementi di pari livello. Offre funzionalità aggiuntive quali la limitazione della sicurezza e l'enumerazione della struttura del sito. Se la memorizzazione nella cache è disattivata, questo influirà negativamente sulle prestazioni e la scalabilità e potrebbe essere soggetta a limitazione.

La seconda opzione, [**spostamento gestito (metadati)**](#using-managed-navigation-and-metadata-in-sharepoint-online), rappresenta gli elementi di spostamento utilizzando un set di termini metadati gestiti. È consigliabile disabilitare la riduzione della sicurezza a meno che non sia necessario. La limitazione di sicurezza è abilitata come impostazione di protezione per il provider di spostamento. Tuttavia, molti siti non richiedono il sovraccarico della limitazione di sicurezza poiché gli elementi di spostamento spesso sono coerenti per tutti gli utenti del sito. Con la configurazione consigliata per disabilitare la limitazione di sicurezza, questo provider di spostamento non richiede l'enumerazione della struttura del sito ed è altamente scalabile con un impatto sulle prestazioni accettabile.

Oltre ai provider di spostamento fuori campo, molti clienti hanno implementato con successo implementazioni di spostamento personalizzate alternative. Vedere [scripting sul fianco client](#using-search-driven-client-side-scripting) basato sulla ricerca in questo articolo.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Vantaggi e svantaggi delle opzioni di spostamento di SharePoint Online

Nella tabella seguente sono riepilogati i vantaggi e gli svantaggi di ogni opzione.

|Esplorazione strutturale  |Esplorazione gestita  |Esplorazione basata sulla ricerca  |Provider di spostamento personalizzato  |
|---------|---------|---------|---------|
|Professionisti<br/><br/>Facile da gestire<br/>Protezione ritagliata<br/>Viene aggiornato automaticamente entro 24 ore dal momento in cui viene modificato il contenuto<br/>     |Professionisti<br/><br/>Facile da gestire<br/>|Professionisti<br/><br/>Protezione ritagliata<br/>Si aggiorna automaticamente man mano che i siti vengono aggiunti<br/>Tempo di caricamento rapido e struttura dell'esplorazione memorizzata nella cache<br/>|Professionisti<br/><br/>Scelta più ampia di opzioni disponibili<br/>Caricamento veloce quando la memorizzazione nella cache viene utilizzata correttamente<br/>Molte opzioni funzionano bene con la progettazione delle pagine reattive<br/>|
|Contro<br/><br/>**Impatto delle prestazioni se la memorizzazione nella cache è disabilitata**<br/>Soggette a limitazione<br/>|Contro<br/><br/>Non si aggiorna automaticamente per riflettere la struttura del sito<br/>**Impatto delle prestazioni se la limitazione di sicurezza è abilitata** o quando la struttura di spostamento è complessa<br/>|Contro<br/><br/>Non è possibile ordinare facilmente i siti<br/>Richiede la personalizzazione della pagina master (necessarie competenze tecniche)<br/>|Contro<br/><br/>Lo sviluppo personalizzato è obbligatorio<br/>L'origine dati esterna/cache memorizzata è necessaria ad esempio Azure<br/>|

L'opzione più appropriata per il sito dipende dai requisiti del sito e dalle proprie capacità tecniche. Se si desidera un provider di spostamento di facile configurazione che si aggiorna automaticamente quando il contenuto viene modificato, la struttura [di spostamento strutturale con memorizzazione nella cache abilitata](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) è una buona opzione.

>[!NOTE]
>Se si applica lo stesso principio dei siti di SharePoint moderni semplificando la struttura complessiva del sito a una struttura più piatta e non gerarchica, le prestazioni vengono semplificate e il passaggio a siti di SharePoint moderni è più semplice. Ciò significa che, invece di disporre di una singola raccolta siti con centinaia di Site (Web secondari), un approccio migliore consiste nell'avere molte raccolte siti con pochissimi sottositi (Web secondari).

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Analisi delle prestazioni di spostamento in SharePoint Online

Lo [strumento page Diagnostics for SharePoint](https://aka.ms/perftool) è un'estensione del browser per i browser Microsoft Edge e Chrome che analizzano sia il portale moderno di SharePoint Online che le pagine del sito di pubblicazione classiche. Questo strumento funziona solo per SharePoint Online e non può essere utilizzato in una pagina di sistema di SharePoint.

Lo strumento genera un rapporto per ogni pagina analizzata che mostra la modalità di esecuzione della pagina in base a un set di regole predefinito e visualizza informazioni dettagliate quando i risultati di un test non rientrano nel valore previsto. Gli amministratori e i progettisti di SharePoint Online possono utilizzare lo strumento per risolvere i problemi relativi alle prestazioni per garantire che le nuove pagine vengano ottimizzate prima della pubblicazione.

**SPRequestDuration** in particolare è il tempo necessario per l'elaborazione della pagina da parte di SharePoint. La navigazione pesante (come ad esempio le pagine in navigazione), le gerarchie di siti complesse e altre opzioni di configurazione e topologia possono contribuire in modo significativo a una durata più lunga.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Utilizzo dell'esplorazione strutturale in SharePoint Online

Questa è la struttura di spostamento fuori campo utilizzata per impostazione predefinita ed è la soluzione più semplice. Non richiede alcuna personalizzazione e un utente non tecnico può anche aggiungere facilmente elementi, nascondere gli elementi e gestire la struttura di spostamento dalla pagina impostazioni. Si consiglia di [abilitare la memorizzazione nella cache](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), altrimenti si verifica un costo elevato delle prestazioni.

### <a name="how-to-implement-structural-navigation-caching"></a>Informazioni su come implementare la memorizzazione nella cache di spostamento strutturale

In **Impostazioni sito**  >  **aspetto**di  >  **spostamento**, è possibile convalidare se l'esplorazione strutturale è selezionata per la struttura di spostamento globale o di spostamento corrente. La selezione di **Mostra pagine** avrà un impatto negativo sulle prestazioni.

![Struttura di spostamento strutturale con i siti secondari visualizzati selezionati](../media/SPONavOptionsStructuredShowSubsites.png)

La memorizzazione nella cache può essere abilitata o disabilitata a livello di raccolta siti e a livello di sito ed è abilitata per entrambi per impostazione predefinita. Per abilitare a livello di raccolta siti, in esplorazione raccolta siti di Amministrazione raccolta siti **Impostazioni sito**  >  **Site Collection Administration**  >  **Site Collection Navigation**selezionare la casella per **abilitare la memorizzazione nella cache**.

![Abilitare la memorizzazione nella cache a livello di sito](../media/structural-nav/structural-nav-caching-site-coll.png)

Per abilitare a livello di sito, in **spostamento Impostazioni sito**  >  **Navigation**selezionare la casella per **abilitare la memorizzazione nella cache**.

![Abilitare la memorizzazione nella cache a livello di sito](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Utilizzo dell'esplorazione e dei metadati gestiti in SharePoint Online

L'esplorazione gestita è un'altra opzione che è possibile utilizzare per ricreare la maggior parte delle stesse funzionalità della struttura di spostamento strutturale. I metadati gestiti possono essere configurati in modo da abilitare o disabilitare la limitazione di sicurezza. Una volta configurata con la limitazione della sicurezza disabilitata, l'esplorazione gestita è piuttosto efficiente poiché carica tutti i collegamenti di spostamento con un numero costante di chiamate del server. L'abilitazione della limitazione della sicurezza, tuttavia, nega alcuni dei vantaggi delle prestazioni dell'esplorazione gestita.

Se è necessario abilitare la limitazione della sicurezza, è consigliabile:

- Aggiornare tutti i collegamenti a collegamenti semplici tramite URL
- Aggiungere nodi di ritaglio di sicurezza richiesti come URL descrittivi
- Limitare il numero di elementi di spostamento a un massimo di 100 e non più di 3 livelli di profondità

Molti siti non richiedono la limitazione della sicurezza, in quanto la struttura di spostamento è spesso coerente per tutti gli utenti del sito. Se la limitazione di sicurezza è disabilitata e viene aggiunto un collegamento alla struttura di spostamento a cui non è consentito l'accesso a tutti gli utenti, il collegamento verrà comunque visualizzato, ma comporterà un messaggio di accesso negato. Non vi è alcun rischio di accesso involontario al contenuto.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Come implementare l'esplorazione gestita e i risultati

Sono disponibili numerosi articoli su docs.microsoft.com per i dettagli relativi all'esplorazione gestita. Ad esempio, vedere [Overview of Managed Navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).

Per implementare l'esplorazione gestita, è necessario configurare i termini con gli URL corrispondenti alla struttura di spostamento del sito. L'esplorazione gestita può anche essere curata manualmente per sostituire la struttura di spostamento strutturale in molti casi. Ad esempio:

![Struttura del sito di SharePoint Online](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Utilizzo di script sul lato client basato sulla ricerca

Una classe comune di implementazioni di spostamento personalizzate abbraccia modelli di progettazione con rendering client che archiviano una cache locale dei nodi di spostamento.

Questi provider di spostamento hanno un paio di vantaggi principali:

- In genere funzionano bene con i progetti di pagina reattivi.
- Sono estremamente scalabili e performanti perché è possibile eseguire il rendering senza costi di risorse (e aggiornare in background dopo un timeout).
- Tali provider di spostamento possono recuperare i dati di spostamento utilizzando diverse strategie, che vanno dalle configurazioni statiche semplici ai vari provider di dati dinamici.

Un esempio di provider di dati prevede l'utilizzo di una struttura di **spostamento basata sulla ricerca**, che consente la flessibilità per l'enumerazione dei nodi di spostamento e la gestione efficiente del taglio di sicurezza.

Sono disponibili altre opzioni popolari per la creazione di **provider di spostamento personalizzati**. Leggere le [soluzioni di navigazione per i portali di SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) per ulteriori informazioni sulla creazione di un provider di spostamento personalizzato.

Utilizzando la ricerca è possibile utilizzare gli indici sviluppati in background tramite la ricerca per indicizzazione continua. I risultati della ricerca vengono recuperati dall'indice di ricerca e i risultati sono limitati per motivi di sicurezza. Questo è in genere più veloce rispetto ai provider di spostamento esterno alla casella quando è richiesta la limitazione della sicurezza. Utilizzando la ricerca per l'esplorazione strutturale, soprattutto se si dispone di una struttura di siti complessa, è possibile velocizzare notevolmente tempi di caricamento delle pagine. Il principale vantaggio di questa esplorazione gestita è che è possibile beneficiare della limitazione per motivi di sicurezza.

Questo approccio implica la creazione di una pagina master personalizzata e la sostituzione del codice di spostamento predefinito con codice HTML personalizzato. Seguire questa procedura illustrata nell'esempio seguente per sostituire il codice di spostamento nel file `seattle.html` . In questo esempio viene aperto il `seattle.html` file e sostituito l'intero elemento `id="DeltaTopNavigation"` con codice HTML personalizzato.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Esempio: sostituire il codice di spostamento fuori dalla casella in una pagina master

1. Andare alla pagina Impostazioni sito.
2. Aprire la raccolta di pagine master facendo clic su **Pagine master**.
3. Da qui è possibile passare alla raccolta e scaricare il file `seattle.master` .
4. Modificare il codice utilizzando un editor di testo ed eliminare il blocco di codice nella schermata seguente.<br/>![Eliminare il blocco di codice visualizzato](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Rimuovere il codice tra i `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` tag e e sostituirlo con il seguente frammento:<br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. Sostituire l'URL nel tag Anchor dell'immagine di caricamento all'inizio, con un collegamento a un'immagine di caricamento nella raccolta siti. Dopo aver apportato le modifiche, rinominare il file, quindi caricarlo nella raccolta di pagine master. Ciò genera un nuovo file con estensione master.<br/>
7. Questo codice HTML è il codice di base che verrà precompilato dai risultati della ricerca restituiti dal codice JavaScript. Sarà necessario modificare il codice per modificare il valore di var root = "URL della raccolta siti", come illustrato nel seguente frammento:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. I risultati vengono assegnati alla matrice self. Nodes e viene creata una gerarchia degli oggetti utilizzando linq.js assegnando l'output a una matrice self. Hierarchy. Questa matrice è l'oggetto in cui è associato il codice HTML. Questa operazione viene eseguita nella funzione toggleView() passando l'oggetto utente alla funzione ko.applyBinding().<br/>Quindi, in questo modo la matrice di gerarchia va associata al codice HTML seguente:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

I gestori eventi per `mouseenter` e `mouseexit` vengono aggiunti all'esplorazione di livello principale per gestire i menu a discesa dei siti secondari, che vengono eseguiti nella `addEventsToElements()` funzione.

Nell'esempio di esplorazione complessa, un caricamento di pagina aggiornato senza la memorizzazione nella cache locale indica che il tempo trascorso nel server è stato ridotto dall'esplorazione strutturale di benchmark per ottenere un risultato simile a quello dell'approccio di spostamento gestito.

### <a name="about-the-javascript-file"></a>Informazioni sul file JavaScript...

>[!NOTE]
>Se si utilizza JavaScript personalizzato, verificare che la rete CDN pubblica sia abilitata e che il file si trovi in un percorso CDN.

Di seguito è riportato l'intero file JavaScript:

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

Per riepilogare il codice sopra riportato nella `jQuery $(document).ready` funzione viene `viewModel object` creata e quindi `loadNavigationNodes()` viene chiamata la funzione su quell'oggetto. Questa funzione carica la gerarchia di spostamento precedentemente creata memorizzata nell'archiviazione locale di HTML5 del browser client o chiama la funzione `queryRemoteInterface()` .

`QueryRemoteInterface()` Compila una richiesta utilizzando la `getRequest()` funzione con il parametro di query definito in precedenza nello script e quindi restituisce i dati dal server. Questi dati sono sostanzialmente una matrice di tutti i siti nella raccolta di siti rappresentati come oggetti di trasferimento dei dati con alcune proprietà.

Questi dati vengono quindi analizzati negli oggetti definiti in precedenza `SPO.Models.NavigationNode` che utilizzano `Knockout.js` per creare proprietà osservabili per l'utilizzo da parte dei dati per l'associazione dei valori nel codice HTML definito in precedenza.

Gli oggetti vengono quindi inseriti in una matrice di risultati. Questa matrice viene analizzata in JSON utilizzando Knockout e memorizzata nell'archivio locale del browser per migliorare le prestazioni su caricamenti di pagina futuri.

### <a name="benefits-of-this-approach"></a>Vantaggi di questo approccio

Uno dei principali vantaggi di [questo approccio](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) consiste nel fatto che tramite l'archiviazione locale di HTML5 la struttura di spostamento viene archiviata localmente per l'utente al successivo caricamento della pagina. Si ottengono miglioramenti delle prestazioni principali utilizzando l'API di ricerca per l'esplorazione strutturale; tuttavia, sono necessarie alcune capacità tecniche per eseguire e personalizzare questa funzionalità.

Nell' [implementazione di esempio](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), i siti vengono ordinati in modo analogo a quello della struttura di spostamento strutturale fuori campo. ordine alfabetico. Se si desidera deviare da questo ordine, diventa più complesso lo sviluppo e la manutenzione. Inoltre, questo approccio richiede di deviare dalle pagine master supportate. Se non viene mantenuta la pagina master personalizzata, il sito verrà escluso dagli aggiornamenti e dai miglioramenti che Microsoft apporta alle pagine master.

Il [codice sopra](#about-the-javascript-file) riportato presenta le dipendenze seguenti:

- jQuery https://jquery.com/
- KnockoutJS - https://knockoutjs.com/
- Linq.js- https://linqjs.codeplex.com/ , o github.com/neuecc/linq.js

La versione corrente di LinqJS non contiene il metodo ByHierarchy utilizzato nel codice precedente e interrompe il codice di spostamento. Per risolvere il cosa, aggiungere il seguente metodo al file Linq.js prima della riga `Flatten: function ()` .

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a>Argomenti correlati

[Panoramica dell'esplorazione gestita in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[Memorizzazione nella cache e prestazioni della struttura di spostamento strutturale](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
