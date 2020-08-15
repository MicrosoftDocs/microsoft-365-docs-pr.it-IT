---
title: Configurare la ricerca di Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Informazioni su come configurare la ricerca in un ambiente multi-geografico. Solo alcuni client, come OneDrive for business, possono restituire risultati in un ambiente multi-geografico.
ms.openlocfilehash: 22c71661e8f3b643a1fd7afa33b38584a1cd1be5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695071"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a>Configurare la ricerca di Microsoft 365 Multi-Geo

In un ambiente multi-geografico, ogni posizione geografica ha un proprio indice di ricerca e un Centro ricerche. Quando un utente effettua una ricerca, la query viene inviata a tutti gli indici e i risultati restituiti vengono aggregati.

Ad esempio, un utente in una posizione geografica può cercare contenuto archiviato in un'altra posizione geografica o il contenuto di un sito di SharePoint che è limitato a una posizione geografica diversa. Se l'utente ha accesso a tale contenuto, la ricerca mostrerà il risultato.

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a>Quali client di ricerca funzionano in un ambiente multi-geografico?

Questi client possono restituire i risultati di tutte le posizioni geografiche:

-   OneDrive for Business

-   Delve

-   Home page di SharePoint

-   Centro ricerche

-   Applicazioni di ricerca personalizzate che utilizzano l'API del servizio di ricerca di SharePoint

### <a name="onedrive-for-business"></a>OneDrive for Business

Non appena viene configurato l'ambiente multi-geografico, gli utenti che cercano in OneDrive ottengono i risultati di tutte le posizioni geografiche.

### <a name="delve"></a>Delve

Non appena viene configurato l'ambiente multi-geografico, gli utenti che cercano in Delve ottengono risultati da tutte le posizioni geografiche.

Il feed di Delve e la scheda profilo mostrano solo le anteprime dei file archiviati in una posizione centrale. Per i file archiviati nelle posizioni satellite, verrà visualizzata l'icona del tipo di file.

### <a name="the-sharepoint-home-page"></a>Home page di SharePoint

Non appena l'ambiente multi-geografico viene configurato, gli utenti possono vedere le notizie, i siti recenti e i siti seguiti di posizioni geografiche diverse nella propria home page di SharePoint. Se usano la casella di ricerca nella home page di SharePoint, aggregheranno tutti i risultati delle posizioni geografiche.

### <a name="the-search-center"></a>Centro ricerche

Dopo che l'ambiente multi-geografico viene configurato, ogni Centro ricerche continua a mostrare solo i risultati della relativa posizione geografica. Gli amministratori devono [modificare le impostazioni di ogni Centro ricerche](#_Set_up_a_1) per generare i risultati di tutte le posizioni geografiche. Successivamente gli utenti che usano il Centro ricerche potranno ottenere i risultati aggregati di tutte le posizioni geografiche.

### <a name="custom-search-applications"></a>Applicazioni di ricerca personalizzate

In genere, le applicazioni di ricerca personalizzate interagiscono con le API REST del servizio di ricerca di SharePoint esistenti. Per ottenere risultati di tutte le posizioni geografiche o solo di alcune, l'applicazione deve [chiamare l'API e includere i nuovi parametri di query Multi-Geo](#_Get_custom_search) nella richiesta. In questo modo, la query viene estesa a tutte le posizioni geografiche.

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a>In che modo la ricerca è diversa in un ambiente multi-geografico?

Alcune delle funzionalità di ricerca già note potrebbero funzionare diversamente in un ambiente multi-geografico.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Caratteristica</strong></th>
<th align="left"><strong>Come funziona</strong></th>
<th align="left"><strong>Soluzione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Risultati evidenziati</td>
<td align="left">È possibile creare regole di query con risultati promossi a diversi livelli: per l'intero tenant, per una raccolta siti o per un sito. In un ambiente multi-geo definire i risultati promossi a livello di tenant, per promuovere i risultati nei Centri ricerche di tutte le posizioni geografiche. Se si desidera soltanto convertire i risultati nel Centro ricerche che si trova nella posizione geografica della raccolta siti o del sito, definire i risultati promossi a livello della raccolta siti o del sito. Questi risultati non sono promossi in altre posizioni geografiche.</td>
<td align="left">Se non sono necessari diversi risultati evidenziati per ogni posizione geografica, ad esempio direttive diverse per le trasferte di lavoro, è consigliabile definire i risultati evidenziati a livello di tenant.</td>
</tr>
<tr class="even">
<td align="left">Criteri di affinamento ricerca</td>
<td align="left">La ricerca restituisce i criteri di affinamento di tutte le posizioni geografiche di un tenant e poi li aggrega. L'aggregazione è approssimativa e viene eseguita secondo il principio "best effort", quindi i conteggi dei criteri di affinamento potrebbero non essere precisi. Per la maggior parte degli scenari di ricerca questo livello di approssimazione è sufficiente. </td>
<td align="left">Per le applicazioni basate sulla ricerca che richiedono criteri di affinamento precisi, è necessario inviare la query separatamente a ogni posizione geografica.</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left">La ricerca multi-geografica non supporta il bucket di criteri di affinamento numerici.</td>
<td align="left">Utilizzare il <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">parametro "discretizzare"</a> per i perfezionamenti numerici.</td>
</tr>
<tr class="even">
<td align="left">ID documenti</td>
<td align="left">Se si decide di sviluppare un'applicazione basata sulla ricerca che usa gli ID dei documenti, occorre tenere presente che tali ID non sono univoci nell'intero ambiente multi-geografico, ma solo all'interno di una singola posizione geografica.</td>
<td align="left">È stata aggiunta una colonna che identifica la posizione geografica. Usare questa colonna per ottenere l'univocità. Questa colonna è denominata "GeoLocationSource".</td>
</tr>
<tr class="odd">
<td align="left">Numero di risultati</td>
<td align="left">La pagina dei risultati della ricerca mostra i risultati combinati ottenuti dalle posizioni geografiche, ma non è possibile includere più di 500 risultati.</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Ricerca ibrida</td>
<td align="left">In un ambiente SharePoint ibrido con <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">Ricerca ibrida nel cloud</a>, il contenuto locale viene aggiunto all'indice di Microsoft 365 della posizione centrale.</td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a>Cosa non è supportato per la ricerca in un ambiente multi-geografico?

Alcune delle funzionalità di ricerca già note non sono supportate in un ambiente multi-geografico.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Funzionalità di ricerca</strong></th>
<th align="left"><strong>Nota</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Autenticazione solo app</td>
<td align="left">L'autenticazione solo app (accesso con privilegi dai servizi) non è supportata nella ricerca multi-geografica.</td>
</tr>
<tr class="even">
<td align="left">Utenti guest</td>
<td align="left">Gli utenti guest ottengono solo i risultati della posizione geografica dove effettuano la ricerca.</td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a>Come funziona la ricerca in un ambiente multi-geografico?

Tutti i client di ricerca usano le API REST del servizio di ricerca di SharePoint per interagire con gli indici di ricerca.

<img src="../media/configure-search-for-multi-geo-image1-1.png" />

1. Un client di ricerca chiama l'endpoint REST Ricerca con la proprietà di query EnableMultiGeoSearch= true.
2. La query viene inviata a tutte le posizioni geografiche del tenant.
3. I risultati della ricerca di ogni posizione geografica vengono aggregati e classificati.
4. Il client ottiene risultati della ricerca unificati.



<span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Si noti che Microsoft non unisce i risultati della ricerca fino a quando non si ricevono i risultati da tutte le posizioni geografiche. Questo significa che le ricerche multi-geo hanno una latenza maggiore rispetto alle ricerche in un ambiente che ha una sola posizione geografica.

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a>Fare in modo che un Centro ricerche mostri i risultati di tutte le posizioni geografiche

Ogni Centro ricerche dispone di diverse verticali ed è necessario configurarle singolarmente.

1.  Assicurarsi di avere eseguito questi passaggi con un account che dispone dell'autorizzazione per modificare la pagina dei risultati della ricerca e la web part Risultati della ricerca.

2.  Andare alla pagina dei risultati della ricerca (vedere l'[elenco](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) delle pagine di risultati della ricerca).

3.  Selezionare la verticale da configurare, fare clic sull'icona a forma di ingranaggio **Impostazioni** in alto a destra, quindi fare clic su **Modifica pagina**. La pagina dei risultati della ricerca si apre in modalità di modifica.

     ![](../media/configure-search-for-multi-geo-image2.png)
1.  Nella web part Risultati della ricerca, spostare il puntatore sull'angolo in alto a destra della web part, fare clic sulla freccia, quindi fare clic su **Modifica web part** nel menu.   Si apre il riquadro degli strumenti della web part Risultati della ricerca sotto la barra multifunzione in alto a destra nella pagina. ![](../media/configure-search-for-multi-geo-image3.png)

1.  Nella riquadro degli strumenti della web part, nella sezione **Impostazioni**, in **Impostazioni controllo risultati**, selezionare **Mostra risultati Multi-Geo** affinché la web part Risultati della ricerca mostri i risultati di tutte le posizioni geografiche.

2.  Fare clic su **OK** per salvare la modifica e chiudere il riquadro degli strumenti della web part.

3.  Verificare le modifiche apportate alla web part Risultati della ricerca facendo clic su **Controllo** nella scheda Pagina del menu principale.

4.  Pubblicare le modifiche usando il collegamento fornito nella nota in alto nella pagina.

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a>Fare in modo che le applicazioni di ricerca personalizzate mostrino risultati di tutte o di alcune posizioni geografiche

Per ottenere i risultati di tutte o alcune posizioni geografiche nelle applicazioni di ricerca personalizzate, è necessario specificare i parametri di query con la richiesta all'API REST del servizio di ricerca di SharePoint. A seconda dei parametri della query, la query viene inviata a tutte le posizioni geografiche o solo ad alcune. Ad esempio, se serve inviare la query solo a un sottoinsieme di posizioni geografiche per trovare informazioni pertinenti, è possibile estendere la query solo ad esse. Se la richiesta ha esito positivo, l'API REST del servizio di ricerca di SharePoint restituisce i dati della risposta.

**Requisito**

Per ogni posizione geografica è necessario verificare che a tutti gli utenti dell'organizzazione sia stato concesso il livello di autorizzazioni **Lettura** per il sito Web radice, ad esempio contoso**APAC**.sharepoint.com/ e contoso**EU**.sharepoint.com/. [Informazioni sulle autorizzazioni](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).

### <a name="query-parameters"></a>Parametri di query

EnableMultiGeoSearch - questo è un valore Booleano che specifica se la query debba essere estesa agli indici di altre posizioni geografiche del tenant multi-geo. Impostare su **true** per estendere la query, su **false** per non estendere la query. Se non si include questo parametro, il valore predefinito è **false**, tranne quando si esegue una chiamata all'API REST su un sito che usa il modello Centro ricerche organizzazione. In tal caso, il valore predefinito è **true**. Se si usa questo parametro in un ambiente non multi-geografico, il parametro viene ignorato.

ClientType - Questa è una stringa. Immettere un nome univoco di client per ogni applicazione di ricerca. Se non si include questo parametro, la query non viene estesa a diverse posizioni geografiche.

MultiGeoSearchConfiguration - Questo è un elenco facoltativo di quali posizioni geografiche devono essere estese alla query quando **EnableMultiGeoSearch** è impostato su **true**. Se non si include questo parametro o lo si lascia vuoto, la query non viene estesa a diverse posizioni geografiche. Per ogni posizione geografica, immettere quanto segue, in formato JSON:

<table>
<thead>
<tr class="header">
<th align="left">Elemento</th>
<th align="left">Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">DataLocation</td>
<td align="left">La posizione geografica, ad esempio NAM.</td>
</tr>
<tr class="even">
<td align="left">EndPoint</td>
<td align="left">L'endpoint a cui connettersi, ad esempio https://contoso.sharepoint.com</td>
</tr>
<tr class="odd">
<td align="left">SourceId</td>
<td align="left">Il GUID dell'origine dei risultati, ad esempio B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</td>
</tr>
</tbody>
</table>

Se si omette DataLocation o EndPoint oppure se DataLocation è duplicato, la richiesta ha esito negativo. [È possibile ottenere informazioni sull'endpoint delle posizioni geografiche di un tenant utilizzando Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).

### <a name="response-data"></a>Dati di risposta

MultiGeoSearchStatus - Si tratta di una proprietà che restituisce l'API Ricerca di SharePoint in risposta a una richiesta. Il valore della proprietà è una stringa e fornisce le informazioni seguenti sui risultati restituiti dall'API Ricerca di SharePoint:

<table>
<thead>
<tr class="header">
<th align="left">Valore</th>
<th align="left">Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Full</td>
<td align="left">Risultati completi da <strong>tutte</strong> le posizioni di ricerca.</td>
</tr>
<tr class="even">
<td align="left">Partial</td>
<td align="left">Risultati parziali da una o più posizioni geografiche. I risultati non sono completi a causa di un errore temporaneo.</td>
</tr>

</tbody>
</table>

### <a name="query-using-the-rest-service"></a>Query che usa il servizio REST

Con una richiesta GET, si specificano i parametri di query nell'URL. Con una richiesta POST, i parametri della query vengono ignorati nel corpo nel formato JavaScript Object Notation (JSON).


#### <a name="request-headers"></a>Intestazioni di richiesta

<table>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Content-Type</td>
<td align="left">application/json;odata=verbose</td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a>Esempio di richiesta GET estesa a **tutte** le posizioni geografiche

https:// \<tenant\> / \_ API/search/query? QueryText =' SharePoint ' &Properties =' EnableMultiGeoSearch: true ' &ClientType =' My \_ client \_ ID '

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a>Esempio di richiesta GET estesa ad **alcune** posizioni geografiche

https:// \<tenant\> / \_ API/search/query? QueryText =' site ' &ClientType =' my_client_id ' &Properties =' EnableMultiGeoSearch: true, MultiGeoSearchConfiguration: [{datalocation \\ : "Nam" \\ , endpoint \\ : "https \\ ://contosoNAM.SharePoint.com" \\ , SourceID \\ : "B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ , {datalocation \\ : "Can" \\ , endpoint \\ : "https \\ ://contosoCAN.SharePoint-DF.com"}]'

> [!NOTE]
> Le virgole e i due punti nell'elenco di posizioni geografiche per la proprietà MultiGeoSearchConfiguration sono preceduti dalla **barra rovesciata**. Questo perché le richieste GET usano i due punti per separare le proprietà e le virgole per separare gli argomenti delle proprietà. Senza la barra rovesciata come carattere di escape, la proprietà MultiGeoSearchConfiguration viene interpretata in modo errato.

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a>Esempio di richiesta POST estesa a **tutte** le posizioni geografiche

    {
        "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }


#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a>Esempio di richiesta POST estesa ad **alcune** posizioni geografiche


    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }

### <a name="query-using-csom"></a>Query che usa CSOM

Esempio di query CSOM estesa a **tutte** le posizioni geografiche:

    var keywordQuery = new KeywordQuery(ctx);
    keywordQuery.QueryText = query.SearchQueryText;
    keywordQuery.ClientType = <enter a string here>;
    keywordQuery["EnableMultiGeoSearch"] = true;

