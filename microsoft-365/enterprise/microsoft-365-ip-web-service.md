---
title: Servizio Web per URL e indirizzi IP di Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Informazioni su come usare l'indirizzo IP e il servizio Web URL di Office 365 per identificare e distinguere meglio il traffico di rete di Office 365.
ms.openlocfilehash: 1948491e1d3db724e7b7b6a5275234acab4be08a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918955"
---
# <a name="office-365-ip-address-and-url-web-service"></a>Servizio Web per URL e indirizzi IP di Office 365

Servizio Web per URL e indirizzi IP di Office 365 consentono di identificare e distinguere il traffico di rete di Office 365, semplificando la valutazione, la configurazione e il miglioramento delle modifiche apportate. Questo servizio Web basato su REST sostituisce i file XML scaricabili precedenti, che sono stati eliminati il 2 ottobre 2018.

Come cliente o fornitore di dispositivi perimetrali di rete, è possibile eseguire la compilazione con il servizio Web per gli indirizzi IP di Office 365 e le voci di FQDN. È possibile accedere ai dati direttamente in un Web browser usando questi URL:

- Per la versione più recente degli URL e degli intervalli di indirizzi IP di Office 365, usare [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).
- Per i dati sulla pagina degli URL e degli intervalli di indirizzi IP di Office 365 per firewall e server proxy, usare [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).
- Per ottenere tutte le ultime modifiche apportate da luglio 2018, quando il servizio Web ha iniziato a essere disponibile, usare [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Un cliente può utilizzare questo servizio Web per le operazioni seguenti:

- Aggiornare gli script di PowerShell per ottenere i dati degli endpoint di Office 365 e modificare la formattazione dei dispositivi di rete in uso.
- Usare queste informazioni per aggiornare i file PAC distribuiti ai computer client.

Un fornitore di dispositivi di rete perimetrale può utilizzare questo servizio Web per le operazioni seguenti:

- Creare e testare il software dei dispositivi per scaricare l'elenco per la configurazione automatizzata.
- Verificare la versione corrente.
- Conoscere le modifiche apportate.

> [!NOTE]
> Se si usa Azure ExpressRoute per connettersi a Office 365, vedere [Azure ExpressRoute per Office 365](azure-expressroute.md) per acquisire familiarità con i servizi di Office 365 supportati su Azure ExpressRoute. Per comprendere quali richieste di rete per le applicazioni di Office 365 richiedono la connettività Internet, vedere l'articolo [URL e intervalli di indirizzi IP di Office 365](urls-and-ip-address-ranges.md). Queste precauzioni consentiranno di migliorare la configurazione dei dispositivi di protezione perimetrale.

Per ulteriori informazioni, vedere:

- [Post di blog dell'annuncio nel forum della community IT di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [Forum della community IT di Office 365 per domande sull'uso dei servizi Web](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a>Parametri comuni

Questi parametri sono comuni a tutti i metodi di servizio Web:

- **formato = < JSON | CSV >** — Per impostazione predefinita il formato dei dati restituiti è JSON. Questo parametro facoltativo consente di restituire i dati con valori delimitati da virgole (CSV).
- **ClientRequestId =\<guid>** — GUID necessario creato per l'associazione di client. Generare un GUID univoco per ogni computer che chiama il servizio Web, ossia gli script inclusi in questa pagina generano un GUID. Non usare i GUID illustrati negli esempi seguenti perché potrebbero essere bloccati dal servizio web in futuro. Il formato GUID è _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, dove x rappresenta un numero esadecimale.

  Per generare un GUID, è possibile usare il comando di PowerShell [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) oppure usare un servizio online come [generatore di GUID online](https://www.guidgenerator.com/).

## <a name="version-web-method"></a>Metodo per la versione web

Microsoft aggiorna l'indirizzo IP e le voci di FQDN di Office 365 alla fine di ogni mese. Gli aggiornamenti out-of-band sono talvolta pubblicati a causa di problemi di supporto, aggiornamenti della sicurezza o altri requisiti operativi.

Ai dati di ogni istanza pubblicata è assegnato un numero di versione e la versione metodo Web consente di controllare la versione più recente di ogni istanza di servizio di Office 365. È consigliabile controllare la versione non più di una volta all'ora.

I parametri per il metodo per la versione web sono:

- **Completaversioni = < true | False >** — Per impostazione predefinita la versione restituita è la più recente. Includere questo parametro facoltativo per richiedere tutte le versioni pubblicate dopo il primo rilascio del servizio web.
- **Format=< JSON | CSV | RSS >** — oltre ai formati JSON e CSV, la versione metodo web supporta inoltre RSS. È possibile usare questo parametro facoltativo con _AllVersions=true_ per richiedere un feed RSS che può essere usato con Outlook o altri lettori RSS.
- **Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>**: questo parametro facoltativo specifica l'istanza per ripristinare la versione. Se omesso, vengono restituite tutte le istanze. Le istanze valide sono: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.

La metodo Web per la versione non è limitata a tariffe e non restituisce mai i codici di risposta HTTP 429. La risposta al metodo Web per la versione include un'intestazione cache-controllo che consiglia la memorizzazione nella cache dei dati per 1 ora. Il risultato ottenuto dal metodo Web per la versione potrebbe essere un singolo record o una matrice di record.  Gli elementi di ogni record sono:

- instance: il nome breve dell'istanza del servizio di Office 365.
- latest: l'ultima versione degli endpoint dell'istanza specificata.
- versioni: elenco di tutte le versioni precedenti per l'istanza specificata. Questo elemento è incluso solo se il parametro _allversions_ è vero.

### <a name="examples"></a>Esempi:

URI della richiesta di esempio 1: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Questo URI restituisce l'ultima versione di ogni istanza del servizio di Office 365. Risultato dell'esempio:

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> Il GUID del parametro ClientRequestID in questi URI è solo un esempio. Per provare gli URI del servizio Web, generare il proprio GUID. I GUID mostrati in questi esempi potrebbero essere bloccati dal servizio Web in futuro.

URI della richiesta di esempio 2: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Questo URI restituisce l'ultima versione dell'istanza del servizio di Office 365 specificata. Risultato dell'esempio:

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

URI della richiesta di esempio 3: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Questo URI mostra l'output in formato CSV. Risultato dell'esempio:

```csv
instance,latest
Worldwide,2018063000
```

URI della richiesta di esempio 4: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Questo URI mostra tutte le versioni precedenti che sono state pubblicate per l'istanza Worldwide del servizio di Office 365. Risultato dell'esempio:

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

URI del feed RSS di esempio 5: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)

Questo URI mostra un feed RSS delle versioni pubblicate che includono collegamenti all'elenco di modifiche di ogni versione. Risultato dell'esempio:

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a>Metodo Web per gli endpoint

Il metodo web per gli endpoint restituisce tutti i record per intervalli di indirizzi IP e URL del servizio Office 365. Per la configurazione dei dispositivi di rete, è consigliabile usare sempre i dati più recenti del metodo Web endpoint. Microsoft fornisce un preavviso 30 giorni prima di pubblicare nuove aggiunte per fornire il tempo necessario per aggiornare gli elenchi di controllo di accesso e gli elenchi di esclusioni del server proxy. È consigliabile chiamare il metodo web per gli endpoint solo quando la versione metodo web indica che è disponibile una nuova versione dei dati.

I parametri per il metodo web per gli endpoint sono:

- **ServiceAreas = < comuni | Exchange | SharePoint | Skype >**, un elenco delle aree di servizio separato da virgole. Sono validi _Common_, _Exchange_, _SharePoint_ e _Skype_. Poiché gli elementi dell’area di servizio di _Common_ sono un prerequisito per tutte le altre aree di servizio, il servizio web li includerà sempre. Se non si include questo parametro, tutte le aree del servizio vengono restituite.
- **TenantName=< tenant_name >** - Nome tenant di Office 365. Il servizio web prende il nome specificato e lo inserisce in parti dell'URL che includono il nome del tenant. Se non si specifica alcun nome tenant, tali parti dell'URL avranno il carattere jolly (\*).
- **NoIPv6=<true | false>**: Impostare questo parametro su _true_ per escludere gli indirizzi IPv6 dall'output, se non si usa il protocollo IPv6 nella propria rete.
- **Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>**. Questo parametro obbligatorio specifica l'istanza da cui restituire gli endpoint. Le istanze valide sono: _Worldwide_, _China_, _Germany_, _USGovDoD_ e _USGovGCCHigh_.

Se si chiama il metodo Web per gli endpoint troppe volte dallo stesso indirizzo IP client, si potrebbe ricevere il codice di risposta HTTP _429 (Troppe richieste)_. Se viene visualizzato questo codice di risposta, attendere un'ora prima di ripetere la richiesta o generare un nuovo GUID per la richiesta. Come procedura consigliata, pianificare la chiamata del metodo Web per gli endpoint solo quando la versione metodo Web indica che è disponibile una nuova versione dei dati.

Il risultato ottenuto dal metodo Web per gli endpoint è una matrice di record in cui ogni record rappresenta uno specifico set di endpoint.  Gli elementi per ogni record sono:

- id: il numero ID non modificabile del set di endpoint.
- serviceArea: l'area del servizio di cui fa parte: _Common_, _Exchange_, _SharePoint_ o _Skype_.
- URL: URL per il set di endpoint. Una matrice JSON di record DNS. Questo elemento viene omesso se non specificato.
- tcpPorts: porte TCP per il set di endpoint. Tutti gli elementi Ports sono formattati come un elenco con valori delimitati da virgole (-). Le porte sono valide per tutti gli indirizzi IP e per tutti gli URL del set di endpoint di una specifica categoria. Questo elemento viene omesso se non specificato.
- udpPorts: le porte UDP degli intervalli di indirizzi IP nel set di endpoint.  Questo elemento viene omesso se non specificato.
- ips: gli intervalli di indirizzi IP associati al set di endpoint come associati alle porte UDP o TCP elencate. Una matrice JSON di intervalli di indirizzi IP. Questo elemento viene omesso se non specificato.
- Categoria: categoria di connettività per il set di endpoint. I valori validi sono _Ottimizza_, _Consenti_ e _Predefinito_. Se si esegue una ricerca nell'output del metodo Web endpoint per la categoria di un indirizzo IP o URL specifico, è possibile che la query restituisca più categorie. In tal caso, seguire le indicazioni della categoria priorità più alta. Se ad esempio il punto finale compare sia in _Ottimizza_ che in _Consenti_, seguire i requisiti per _Ottimizza_. Obbligatorio.
- expressRoute: _True_ se il set di endpoint sfrutta la connessione ExpressRoute, _False_ in caso contrario.
- required: _True_ se il set di endpoint deve avere una connettività per Office 365 che sia supportata. _False_ se il set di endpoint è facoltativo.
- notes: per gli endpoint facoltativi, questo testo descrive la funzionalità di Office 365 che non sarà disponibile se gli URL o gli indirizzi IP nel set di endpoint non sono accessibili al livello della rete. Questo elemento viene omesso se non specificato.

### <a name="examples"></a>Esempi:

URI della richiesta di esempio 1: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Questo URI ottiene tutti gli endpoint per l'istanza Worldwide di Office 365 per tutti i carichi di lavoro. Risultato dell'esempio che mostra un estratto dell'output:

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

Si noti che l'output completo della richiesta in questo esempio conterrebbe altri set di endpoint.

URI della richiesta di esempio 2: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

In questo esempio si ottengono gli endpoint per l'istanza Worldwide di Office 365 solo per Exchange Online e le dipendenze.

L'output dell'esempio 2 è simile a quello dell'esempio 1, ad eccezione del fatto che i risultati non includerebbero endpoint per SharePoint Online o Skype for Business Online.

## <a name="changes-web-method"></a>Metodo Web per le modifiche

Il metodo Web per le modifiche restituisce gli aggiornamenti più recenti che sono stati pubblicati, in genere le modifiche apportate al mese precedente agli intervalli di indirizzi IP e degli URL.

Le modifiche più importanti ai dati degli endpoint sono nuovi URL e indirizzi IP. Se non si aggiunge un indirizzo IP a un elenco di controllo di accesso del firewall o un URL a un elenco di bypass del server proxy, è possibile che si sia verificata un'interruzione per gli utenti di Office 365. In deroga ai requisiti operativi, i nuovi endpoint vengono pubblicati nel servizio Web 30 giorni prima della data di provisioning degli endpoint da usare per fornire il tempo necessario per aggiornare gli elenchi di controllo di accesso e gli elenchi di esclusioni del server proxy.

Il parametro obbligatorio del metodo Web per le modifiche è il seguente:

- **Versione =\<YYYYMMDDNN>** - Parametro obbligatorio di route URL. Questo valore deve corrispondere alla versione attualmente implementata. Il servizio Web restituisce le modifiche apportate dopo tale versione. Il formato è _AAAAMMGGNN_, dove _NN_ è un numero naturale incrementabile se è necessario pubblicare più versioni nello stesso giorno, con _00_ che rappresenta il primo aggiornamento del giorno. Il servizio Web richiede che il parametro della _versione_ contenga esattamente 10 cifre.

Il metodo Web per le modifiche ha frequenza limitata, allo stesso modo del metodo Web per gli endpoint. Se viene visualizzato il codice di risposta 429 HTTP, attendere un'ora prima di ripetere la richiesta o generare un nuovo GUID per la richiesta.

Il risultato ottenuto dal metodo Web per le modifiche è una matrice di record in cui ogni record rappresenta una modifica in una specifica versione di endpoint.  Gli elementi per ogni record sono:

- id: l'ID non modificabile del record della modifica.
- endpointSetId: l'ID del record del set di endpoint cui è stata apportata la modifica.
- disposizione: descrive la modifica apportata al record set di endpoint. I valori sono _cambia_, _aggiungi_ o _rimuovi_.
- impatto: non tutte le modifiche saranno ugualmente importanti per ogni ambiente. Questo elemento descrive l'impatto atteso di un ambiente perimetrale della rete aziendale in seguito a questa modifica. Questo elemento è incluso solo in Change Records della versione **2018112800** e versioni successive. Le opzioni per l'impatto sono:-AddedIp-un indirizzo IP è stato aggiunto a Office 365 e sarà presto disponibile per il servizio. Rappresenta una modifica da eseguire in un firewall o un dispositivo di rete perimetrale di livello 3. Se non si aggiunge prima di iniziare a usarlo, può verificarsi un'interruzione del servizio.
  — AddedUrl: un URL è stato aggiunto a Office 365 e sarà presto live nel servizio. Rappresenta una modifica da eseguire in un server proxy o in un dispositivo di rete perimetrale per analisi URL. Se non si aggiunge tale URL prima di iniziare a usarlo, può verificarsi un'interruzione del servizio.
  -AddedIpAndUrl-sono stati aggiunti sia un indirizzo IP che un URL. Rappresenta una modifica da eseguire in un dispositivo firewall di livello 3 o un server proxy o in un dispositivo per analisi URL. Se non si aggiunge tale IP/URL prima di iniziare a usarlo, può verificarsi un'interruzione del servizio.
  -RemovedIpOrUrl: almeno un indirizzo IP o un URL è stato rimosso da Office 365. Rimuovere gli endpoint di rete dai dispositivi perimetrali, ma non c’è una scadenza per eseguire questa operazione.
  -ChangedIsExpressRoute: è stato modificato l'attributo di supporto ExpressRoute. Se si usa ExpressRoute, potrebbe essere necessario eseguire un'azione in base alla configurazione.
  — MovedIpOrUrl: abbiamo spostato un indirizzo IP o un Url da questo set di endpoint a un altro. In genere, non è necessario alcun intervento.
  — RemovedDuplicateIpOrUrl: abbiamo rimosso un indirizzo IP o URL duplicato ma questo è ancora pubblicato per Office 365. In genere, non è necessario alcun intervento.
  — OtherNonPriorityChanges: abbiamo modificato qualcosa di meno critico rispetto a tutte le altre opzioni, ad esempio il contenuto di un campo della nota.
- Versione: versione del set di endpoint pubblicato in cui è stata introdotta la modifica. I numeri delle versioni sono in formato _AAAAMMGGNN_, dove _NN_ è un numero naturale incrementabile se è necessario pubblicare più versioni in un singolo giorno.
- previous: una sottostruttura che descrive dettagliatamente i valori precedenti degli elementi modificati nel set di endpoint. Non sarà inclusa per i set di endpoint appena aggiunti. Include _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ e _notes_.
- current: una sottostruttura che descrive dettagliatamente i valori aggiornati degli elementi di modifica nel set di endpoint. Include _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ e _notes_.
- add: una sottostruttura che descrive nel dettaglio gli elementi da aggiungere alle raccolte dei set di endpoint.  Questo elemento viene omesso se non ci sono aggiunte.
  effectiveDate: definisce la data in cui le aggiunte saranno effettive nel servizio.
  ips: gli elementi da aggiungere alla matrice di _indirizzi IP_.
  urls: gli elementi da aggiungere alla matrice di _urls_.
- remove: una sottostruttura che descrive nel dettaglio gli elementi da rimuovere dal set di endpoint. Questo elemento viene omesso se non ci sono rimozioni.
  ips: gli elementi da rimuovere dalla matrice di _indirizzi IP_.
  urls: gli elementi da rimuovere dalla matrice di _URL_.

### <a name="examples"></a>Esempi:

URI della richiesta di esempio 1: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Richiede tutte le modifiche precedenti apportate all'istanza Worldwide del servizio di Office 365. Risultato dell'esempio:

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

URI della richiesta di esempio 2: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Richiede le modifiche apportate all'istanza Worldwide di Office 365 a partire dalla versione specificata. In questo caso, la versione specificata è la più recente. Risultato dell'esempio:

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a>Script di PowerShell di esempio

È possibile eseguire questo script di PowerShell per verificare se esistono attività da eseguire per ottenere dati aggiornati. È possibile eseguire lo script come attività programmata per verificare la necessità di un aggiornamento della versione. Per evitare un carico eccessivo nel servizio Web, provare a non eseguire lo script più di una volta all'ora.

Questo script consente di:

- Controlla il numero di versione degli endpoint di istanza correnti di Office 365 in tutto il mondo chiamando l'API REST per il servizio Web.
- Verifica la presenza di un file di versione corrente _$Env:TEMP\O365_endpoints_latestversion.txt_. Il percorso della variabile globale **$ENV: temp** in genere _è C:\Users\\< nomeutente\>\AppData\Local\Temp_.
- Se è la prima volta che si esegue lo script, lo script restituirà la versione corrente e tutti gli URL e gli indirizzi IP correnti, scriverà la versione di endpoint nel file _$Env:TEMP\O365_endpoints_latestversion.txt_ e gli endpoint l'output dei dati nel file _$Env:TEMP\O365_endpoints_data.txt_.. È possibile modificare il percorso e/o il nome del file di output modificando le righe seguenti:

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- In ogni successiva esecuzione dello script, se la versione più recente del servizio Web è identica alla versione del file _O365_endpoints_latestversion. txt_, lo script esce senza apportare modifiche.
- Se la versione più recente del servizio Web è più recente della versione _O365_endpoints_latestversion.txt_, lo script restituirà gli endpoint e i filtri per la versione **Consenti** e **Ottimizza** endpoint di categoria, aggiorna la versione nel file _O365_endpoints_latestversion.txt_ e scrive i dati aggiornati nel file _O365_endpoints_data.txt_.

Lo script genera un _ClientRequestId_ univoco per il computer in cui è stato eseguito e riutilizza questo ID tra più chiamate. Questo ID viene archiviato nel file _O365_endpoints_latestversion. txt_.

### <a name="to-run-the-powershell-script"></a>Per eseguire lo script di PowerShell

1. Copiare lo script e salvarlo nel disco rigido locale o nel percorso dello script come _Get-O365WebServiceUpdates.ps1_.
1. Eseguire lo script nell'editor di script preferito, ad esempio il codice di PowerShell ISE o VS, o da una console di PowerShell con il comando seguente:

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    Non sono disponibili parametri per passare allo script.

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a>Script di Python di esempio

Di seguito è riportato uno script di Python, testato con Python 3.6.3 su Windows 10, che è possibile eseguire per verificare se sono presenti azioni che è necessario effettuare per i dati aggiornati. Questo script controlla il numero di versione degli endpoint dell'istanza Worldwide di Office 365. Quando è presente una modifica, scarica gli endpoint e li filtra per quelli di categoria _Allow_ e _Optimize_. Inoltre, usa un ClientRequestId unico tra più chiamate e salva l'ultima versione trovata in un file temporaneo. È necessario chiamare questo script ogni ora per verificare la disponibilità di un aggiornamento della versione.

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a>Controllo delle versioni dell'interfaccia del servizio Web

In futuro potrebbero essere necessari aggiornamenti ai parametri o ai risultati di questi metodi di servizio Web. Dopo la pubblicazione della versione della disponibilità generale di tali servizi Web, Microsoft adotterà misure ragionevoli per fornire un avviso anticipato agli aggiornamenti del materiale al servizio Web. Se Microsoft ritiene che un aggiornamento richiederà modifiche ai client che usano il servizio Web, Microsoft manterrà la versione precedente, ossia una versione posteriore, del servizio Web, disponibile per almeno 12 mesi dopo il rilascio della nuova versione. I clienti che non eseguono l'aggiornamento durante quel periodo potrebbero non essere in grado di accedere al servizio Web e ai relativi metodi. I clienti devono accertarsi che i client del servizio Web continuino a funzionare senza errori se sono state apportate le modifiche seguenti alla firma dell'interfaccia del servizio Web:

- L'aggiunta di un nuovo parametro opzionale a un metodo Web esistente che non deve essere fornito dai client precedenti e che non influisce sul risultato ottenuto da un client precedente.
- L'aggiunta di un nuovo attributo denominato in una delle colonne aggiuntive o in uno degli elementi REST della risposta nel CSV di risposta.
- L'aggiunta di un nuovo metodo Web con un nuovo nome che non è chiamato dai client precedenti.

## <a name="update-notifications"></a>Notifiche sugli aggiornamenti

Per ricevere notifiche tramite posta elettronica, è possibile usare diversi metodi, quando le modifiche apportate agli indirizzi IP e agli URL vengono pubblicate nel servizio Web.

- Per usare una soluzione di Microsoft Flow, vedere [Usare Microsoft Flow per ricevere un messaggio di posta elettronica per le modifiche apportate agli indirizzi IP e agli URL di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).
- Per distribuire un'app logica di Azure con un modello ARM, [vedere notifica di aggiornamento di Office 365 (v 1.1)](https://aka.ms/ipurlws-updates-template).
- Per scrivere uno script di notifica personalizzato con PowerShell, [vedere Invio-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).

## <a name="exporting-a-proxy-pac-file"></a>Esportare un file PAC Proxy

[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) è uno script di PowerShell che legge gli ultimi endpoint di rete dall'indirizzo IP e dall'URL di Office 365 e crea un file PAC di esempio. Per informazioni sull'uso di Get-PacFile, vedere [Usare un file PAC per il routing diretto del traffico vitale di Office 365](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

## <a name="related-topics"></a>Argomenti correlati
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)
  
[Domande frequenti sugli endpoint di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[Principi della connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md)

[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)
  
[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Ottimizzazione della rete per Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)