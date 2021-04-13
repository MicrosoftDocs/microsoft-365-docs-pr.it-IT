---
title: Routing con ExpressRoute per Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: In questo articolo sono disponibili informazioni sui requisiti di routing, i circuiti e i domini di routing di Azure ExpressRoute da usare con Office 365.
ms.openlocfilehash: b455ed7e53b3018babb1abd58919a077fb9d0685
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687170"
---
# <a name="routing-with-expressroute-for-office-365"></a>Routing con ExpressRoute per Office 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Per comprendere correttamente il traffico di instradamento a Office 365 tramite Azure ExpressRoute, è necessario conoscere i requisiti di [routing ExpressRoute](/azure/expressroute/expressroute-routing) di base e i circuiti ExpressRoute e i domini [di routing.](/azure/expressroute/expressroute-circuit-peerings) Vengono così definiti i concetti fondamentali per l'uso di ExpressRoute su cui si basano i clienti di Office 365.
  
Alcuni degli elementi chiave degli articoli precedenti che è necessario comprendere includono:
  
- I circuiti ExpressRoute non sono mappati a un'infrastruttura fisica specifica, ma sono una connessione logica effettuata in un'unica posizione di peering da Microsoft e da un provider di peering per conto dell'utente.

- Esiste un mapping 1:1 tra un circuito ExpressRoute e una chiave s del cliente.

- Ogni circuito può supportare due relazioni di peering indipendenti (peering privato di Azure e peering Microsoft); Office 365 richiede il peering Microsoft.

- Ogni circuito ha una larghezza di banda fissa condivisa tra tutte le relazioni di peering.

- Tutti gli indirizzi IPv4 pubblici e i numeri AS pubblici che verranno utilizzati per il circuito ExpressRoute devono essere convalidati come di proprietà dell'utente o assegnati esclusivamente dal proprietario dell'intervallo di indirizzi.

- I circuiti ExpressRoute virtuali sono ridondanti a livello globale e seguiranno le procedure di routing BGP standard. Ecco perché consigliamo due circuiti fisici per ogni uscita al provider in una configurazione attiva/attiva.

Per ulteriori [informazioni sui](/azure/expressroute/expressroute-faqs) servizi supportati, sui costi e sui dettagli di configurazione, vedere la pagina domande frequenti. Per informazioni [sull'elenco dei](/azure/expressroute/expressroute-locations) provider di connettività che offrono il supporto per il peering Microsoft, vedere l'articolo Percorsi ExpressRoute. Abbiamo anche registrato una serie di Azure [ExpressRoute per Office 365 Training](https://channel9.msdn.com/series/aer) in 10 parti su Channel 9 per illustrare i concetti in modo più approfondito.
  
## <a name="ensuring-route-symmetry"></a>Garantire la simmetria delle route

I server front-end di Office 365 sono accessibili sia su Internet che su ExpressRoute. Questi server preferiranno eseguire il routing verso i circuiti locali su ExpressRoute quando entrambi sono disponibili. Per questo, esiste la possibilità di instradare l'asimmetria se il traffico dalla rete preferisce instradare i circuiti Internet. Le route asimmetriche sono un problema perché i dispositivi che eseguono l'ispezione dei pacchetti con stato possono bloccare il traffico restituito che segue un percorso diverso rispetto ai pacchetti in uscita seguiti.
  
Indipendentemente dal fatto che si avvii una connessione a Office 365 tramite Internet o ExpressRoute, l'origine deve essere un indirizzo pubblicamente instradabile. Con molti clienti che peering direttamente con Microsoft, avere indirizzi privati in cui è possibile duplicare tra i clienti non è fattibile.
  
Di seguito sono riportati gli scenari in cui verranno avviate le comunicazioni da Office 365 alla rete locale. Per semplificare la progettazione della rete, è consigliabile instradarlo tramite il percorso Internet.
  
- Servizi SMTP, ad esempio la posta da un tenant di Exchange Online a un host locale o la posta di SharePoint Online inviata da SharePoint Online a un host locale. Il protocollo SMTP viene utilizzato in modo più ampio all'interno della rete Microsoft rispetto ai prefissi di route condivisi sui circuiti ExpressRoute e la pubblicità dei server SMTP locali su ExpressRoute causerà errori con questi altri servizi.

- ADFS durante la convalida della password per l'accesso.

- [Exchange Server distribuzioni ibride](/exchange/exchange-hybrid).

- [Ricerca ibrida federata di SharePoint](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [SharePoint hybrid BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Federazione ibrida di Skype for Business](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e/o Skype for [Business](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

- [Skype for Business Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Per fare in modo che Microsoft instrada di nuovo alla rete questi flussi di traffico bidirezionali, le route BGP ai dispositivi locali devono essere condivise con Microsoft. Quando si annunciano prefissi di route a Microsoft su ExpressRoute, è consigliabile seguire queste procedure consigliate:

1) Non annunciare lo stesso prefisso di route dell'indirizzo IP pubblico su Internet pubblico e su ExpressRoute. È consigliabile che gli annunci del prefisso di route BGP IP a Microsoft tramite ExpressRoute siano di un intervallo non annunciato a Internet. Se ciò non è possibile a causa dello spazio di indirizzi IP disponibile, è essenziale assicurarsi di annunciare un intervallo più specifico su ExpressRoute rispetto a qualsiasi circuito Internet.

2) Usa pool IP NAT separati per ogni circuito ExpressRoute e separato da quello dei circuiti Internet.

3) Tenere presente che qualsiasi route annunciata a Microsoft attirerà il traffico di rete da qualsiasi server della rete Di Microsoft, non solo quelli per i quali le route vengono annunciate alla rete tramite ExpressRoute. Annunciare solo le route ai server in cui gli scenari di routing sono definiti e ben compresi dal team. Annunciare prefissi di route di indirizzi IP separati in ognuno dei circuiti ExpressRoute dalla rete.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Decidere quali applicazioni e funzionalità instradare su ExpressRoute

Quando si configura una relazione di peering utilizzando il dominio di routing di peering Microsoft e vengono approvati per l'accesso appropriato, sarà possibile visualizzare tutti i servizi PaaS e SaaS disponibili su ExpressRoute. I servizi di Office 365 progettati per ExpressRoute possono essere gestiti con [community BGP](./bgp-communities-in-expressroute.md) o [filtri di route.](/azure/expressroute/how-to-routefilter-portal)
  
Altre applicazioni, ad esempio Office 365 Video, sono un'applicazione di Office 365. Tuttavia, Office 365 Video è costituito da tre diversi componenti, il portale, il servizio di streaming e la rete di recapito dei contenuti. Il portale si trova in SharePoint Online, il servizio di streaming si trova all'interno di Servizi multimediali di Azure e la rete per la distribuzione di contenuti si trova all'interno della rete CDN di Azure. Nella tabella seguente vengono descritti questi componenti.

|**Componente**|**Applicazione sottostante**|**Incluso nella community BGP di SharePoint Online?**|**Utilizzo**|
|:-----|:-----|:-----|:-----|
|Portale di Office 365 Video  <br/> |SharePoint Online  <br/> |Sì  <br/> |Configurazione, caricamento  <br/> |
|Servizio di streaming di Office 365 Video  <br/> |Servizi multimediali di Azure  <br/> |No  <br/> |Servizio di streaming, utilizzato nel caso in cui il video non sia disponibile dalla rete CDN  <br/> |
|Rete per la distribuzione di contenuti di Office 365 Video  <br/> |Azure CDN  <br/> |No  <br/> |Origine principale di download/streaming video. [Ulteriori informazioni sulla rete video di Office 365](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e).  <br/> |

Ognuna delle funzionalità di Office 365 disponibili con il peering Microsoft sono elencate nell'articolo Endpoint di [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) in base al tipo di applicazione e all'FQDN. Il motivo per usare il nome di dominio completo nelle tabelle è consentire ai clienti di gestire il traffico usando file PAC o altre configurazioni proxy, vedere la guida alla gestione degli endpoint di [Office 365,](./managing-office-365-endpoints.md) ad esempio file PAC.
  
In alcuni casi è stato utilizzato un dominio con caratteri jolly in cui uno o più FQDN secondari vengono annunciati in modo diverso rispetto al dominio con caratteri jolly di livello superiore. Questo accade in genere quando il carattere jolly rappresenta un lungo elenco di server tutti annunciati a ExpressRoute e a Internet, mentre un piccolo sottoinsieme di destinazioni viene annunciato solo su Internet o al contrario. Fare riferimento alle tabelle seguenti per comprendere dove sono le differenze.
  
In questa tabella vengono visualizzati gli FQDN con caratteri jolly annunciati sia su Internet che su Azure ExpressRoute insieme ai nomi fqdn secondari annunciati solo su Internet.

|**Dominio con caratteri jolly annunciato ai circuiti ExpressRoute e Internet**|**Fqdn secondario annunciato solo per circuiti Internet**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

In genere i file PAC sono destinati a inviare richieste di rete agli endpoint annunciati expressRoute direttamente al circuito e a tutte le altre richieste di rete al proxy. Se configuri un file PAC come questo, componi il file PAC nell'ordine seguente:
  
1. Includi gli FQDN secondari della colonna 2 nella tabella precedente nella parte superiore del file PAC, inviando il traffico verso il proxy. È stato creato un file PAC di esempio da usare nell'articolo sulla gestione degli endpoint di [Office 365.](./managing-office-365-endpoints.md)

2. Includi tutti gli FQDN contrassegnati come annunciati a ExpressRoute [in](./urls-and-ip-address-ranges.md) questo articolo sotto la prima sezione, inviando il traffico direttamente al circuito ExpressRoute.

3. Includi eventuali altri endpoint di rete o regole al di sotto di queste due voci, inviando il traffico verso il proxy.

In questa tabella vengono visualizzati i domini con caratteri jolly annunciati ai circuiti Internet solo insieme ai nomi FQDN secondari annunciati per i circuiti DisRoute e Internet di Azure.This table displays the wildcard domains that are advertised to Internet circuits only alongside the sub-FQDNs that are advertised to Azure ExpressRoute and Internet circuits. Per il file PAC precedente, gli FQDN nella colonna 2 nella tabella seguente sono elencati come annunciati a ExpressRoute nel collegamento a cui si fa riferimento, il che significa che verrebbero inclusi nel secondo gruppo di voci nel file.

|**Dominio con caratteri jolly annunciato solo per circuiti Internet**|**Fqdn secondario annunciato ai circuiti ExpressRoute e Internet**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Routing del traffico di Office 365 su Internet ed ExpressRoute

Per eseguire il routing all'applicazione di Office 365 di propria scelta, è necessario determinare una serie di fattori chiave.
  
1. Quantità di larghezza di banda necessaria per l'applicazione. Il campionamento dell'utilizzo esistente è l'unico metodo affidabile per determinare tale utilizzo nell'organizzazione.

2. Da quali località di uscita si desidera che il traffico di rete lasci la rete. È consigliabile pianificare di ridurre al minimo la latenza di rete per la connettività a Office 365 in quanto ciò inciderà sulle prestazioni. Poiché Skype for Business usa voce e video in tempo reale, è particolarmente soggetto a una latenza di rete scarsa.

3. Se vuoi che tutti o un sottoinsieme dei percorsi di rete usiNo ExpressRoute.

4. Da quali posizioni il provider di rete scelto offre ExpressRoute.

Dopo aver determinato le risposte a queste domande, è possibile effettuare il provisioning di un circuito ExpressRoute che soddisfi le esigenze di larghezza di banda e posizione. Per ulteriori informazioni sulla pianificazione della rete, fare riferimento alla guida all'ottimizzazione della rete di [Office 365](./network-planning-and-performance.md) e al case study su come Microsoft gestisce la pianificazione [delle prestazioni di rete.](https://aka.ms/tunemsit)
  
### <a name="example-1-single-geographic-location"></a>Esempio 1: singola posizione geografica
  
Questo esempio è uno scenario per una società fittizia denominata Trey Research con una singola posizione geografica.
  
Ai dipendenti di Trey Research è consentito connettersi solo ai servizi e ai siti Web su Internet che il reparto di sicurezza consente esplicitamente sulla coppia di proxy in uscita che siedono tra la rete aziendale e il proprio ISP.
  
Trey Research prevede di usare Azure ExpressRoute per Office 365 e riconosce che parte del traffico, ad esempio il traffico destinato alle reti per la distribuzione di contenuti, non sarà in grado di eseguire il routing sulla connessione ExpressRoute per Office 365. Poiché tutto il traffico è già instradato ai dispositivi proxy per impostazione predefinita, queste richieste continueranno a funzionare come prima. Dopo che Trey Research ha determinato di essere in grado di soddisfare i requisiti di routing di Azure ExpressRoute, procede alla creazione di un circuito, alla configurazione del routing e al collegamento del nuovo circuito ExpressRoute a una rete virtuale. Dopo aver definito la configurazione di Azure ExpressRoute di base, Trey Research usa il [file PAC di #2](./managing-office-365-endpoints.md)  pubblicato per instradare il traffico con dati specifici del cliente tramite ExpressRoute diretto per le connessioni di Office 365.
  
Come illustrato nel diagramma seguente, Trey Research è in grado di soddisfare il requisito di instradare il traffico di Office 365 su Internet e un sottoinsieme di traffico su ExpressRoute usando una combinazione di modifiche alla configurazione del routing e del proxy in uscita.
  
1. Usando il [#2 PAC](./managing-office-365-endpoints.md) pubblicato per instradare il traffico attraverso un punto di uscita Internet separato per Azure ExpressRoute per Office 365.

2. I client sono configurati con una route predefinita verso i proxy di Trey Research.

In questo scenario di esempio, Trey Research usa un dispositivo proxy in uscita. Analogamente, i clienti che non usano Azure ExpressRoute per Office 365 potrebbero voler usare questa tecnica per instradare il traffico in base al costo dell'ispezione del traffico destinato a endpoint di volume elevato noti.
  
I fqdn di volume più elevati per Exchange Online, SharePoint Online e Skype for Business online sono i seguenti:
  
![Rete perimetrale del cliente ExpressRoute](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\> -my.sharepoint.com, \<tenant-name\> - \<app\> .sharepoint.com

- \*. Lync.com con gli intervalli IP per il traffico non TCP

- \*broadcast.officeapps.live.com, \* excel.officeapps.live.com, \* onenote.officeapps.live.com, \* powerpoint.officeapps.live.com, \* view.officeapps.live.com, \* visio.officeapps.live.com, \* word-edit.officeapps.live.com, \* word-view.officeapps.live.com, office.live.com

Altre informazioni sulla distribuzione e la gestione delle impostazioni [proxy in Windows 8](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy) e sulla sicurezza che [Office 365](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)non sia limitato dal proxy.
  
Con un singolo circuito ExpressRoute, non esiste una disponibilità elevata per Trey Research. Nel caso in cui la coppia ridondante di dispositivi perimetrali di Trey che si sta servindo della connettività ExpressRoute non riesca, non esiste un circuito ExpressRoute aggiuntivo a cui eseguire il failover. Ciò lascia Trey Research in una situazione di problema poiché il failover su Internet richiederà una riconfigurazione manuale e, in alcuni casi, nuovi indirizzi IP. Se Trey vuole aggiungere disponibilità elevata, la soluzione più semplice consiste nell'aggiungere circuiti ExpressRoute aggiuntivi per ogni posizione e configurare i circuiti in modo attivo/attivo.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Routing ExpressRoute per Office 365 con più posizioni

L'ultimo scenario, il routing del traffico di Office 365 su ExpressRoute è la base per un'architettura di routing ancora più complessa. Indipendentemente dal numero di posizioni, dal numero di continenti in cui tali posizioni esistono, dal numero di circuiti ExpressRoute e così via, sarà necessario poter instradare parte del traffico verso Internet e parte del traffico su ExpressRoute.
  
Le domande aggiuntive a cui devono rispondere i clienti con più posizioni in più aree geografiche includono:
  
1. È necessario un circuito ExpressRoute in ogni posizione? Se si usa Skype for Business online o si è interessati alla riservatezza della latenza per SharePoint Online o Exchange Online, è consigliabile utilizzare una coppia ridondante di circuiti ExpressRoute attivi/attivi in ogni posizione. Per altri dettagli, vedi la guida alla qualità dei supporti e alla connettività di rete di Skype for Business.

2. Se un circuito ExpressRoute non è disponibile in una determinata area geografica, come instradare il traffico destinato a Office 365?

3. Qual è il metodo preferito per consolidare il traffico nel caso di reti con molte posizioni di piccole dimensioni?

Ognuno di questi presenta una sfida unica che richiede di valutare la propria rete e le opzioni disponibili da Microsoft.

|**Considerazione**|**Componenti di rete da valutare**|
|:-----|:-----|
|Circuiti in più di una posizione  <br/> |È consigliabile configurare almeno due circuiti in modo attivo/attivo.  <br/> È necessario confrontare i costi, la latenza e la larghezza di banda.  <br/> Usa il costo della route BGP, i file PAC e NAT per gestire il routing con più circuiti.  <br/> |
|Routing da posizioni senza circuito ExpressRoute  <br/> |È consigliabile l'uscita e la risoluzione DNS il più vicino alla persona che avvia la richiesta per Office 365.  <br/> L'inoltro DNS può essere utilizzato per consentire agli uffici remoti di individuare l'endpoint appropriato.  <br/> I client nell'ufficio remoto devono disporre di una route disponibile che fornisce l'accesso al circuito ExpressRoute.  <br/> |
|Consolidamento di uffici di piccole dimensioni  <br/> |La larghezza di banda disponibile e l'utilizzo dei dati devono essere confrontati con attenzione.  <br/> |

> [!NOTE]
> Microsoft preferirà ExpressRoute su Internet se la route è disponibile indipendentemente dalla posizione fisica.
  
Ognuna di queste considerazioni deve essere presa in considerazione per ogni rete univoca. Di seguito è riportato un esempio.
  
### <a name="example-2-multi-geographic-locations"></a>Esempio 2: posizioni geografiche diverse
  
Questo esempio è uno scenario per una società fittizia denominata Humongous Insurance con più posizioni geografiche.
  
Humongous Insurance è geograficamente dislocata con uffici in tutto il mondo. Vogliono implementare Azure ExpressRoute per Office 365 per mantenere la maggior parte del traffico di Office 365 sulle connessioni di rete dirette. Humongous Insurance ha anche uffici in altri due continenti. I dipendenti dell'ufficio remoto in cui ExpressRoute non è fattibile dovranno instradare di nuovo a una o a entrambe le strutture principali per usare una connessione ExpressRoute.
  
Il principio guida è quello di ottenere il traffico destinato a Office 365 a un datacenter Microsoft il prima possibile. In questo esempio, Humongous Insurance deve decidere se le proprie sedi remote devono instradare su Internet per raggiungere un datacenter Microsoft su qualsiasi connessione il più rapidamente possibile o se le loro sedi remote devono instradare su una rete interna per raggiungere un datacenter Microsoft tramite una connessione ExpressRoute il più rapidamente possibile.
  
I data center, le reti e l'architettura delle applicazioni di Microsoft sono progettati per consentire comunicazioni disparate a livello globale e servizi nel modo più efficiente possibile. Questa è una delle reti più grandi al mondo. Le richieste destinate a Office 365 che rimangono sulle reti dei clienti più a lungo del necessario non saranno in grado di sfruttare questa architettura.
  
Nella situazione di Humongous Insurance, devono procedere a seconda delle applicazioni che intendono usare su ExpressRoute. Ad esempio, se si tratta di un cliente skype for business online o si prevede di usare la connettività ExpressRoute durante la connessione a riunioni esterne di Skype for Business online, la progettazione consigliata nella guida alla qualità multimediale e alla connettività di rete di Skype for Business Online è di effettuare il provisioning di un circuito ExpressRoute aggiuntivo per la terza posizione. Questo può essere più costoso dal punto di vista della rete; Tuttavia, il routing delle richieste da un continente all'altro prima di recapitare a un datacenter Microsoft può causare un'esperienza scarsa o inutilizzabile durante le riunioni e le comunicazioni di Skype for Business online.
  
Se Humongous Insurance non usa o non prevede di usare Skype for Business online in alcun modo, il routing del traffico di rete destinato a Office 365 verso un continente con una connessione ExpressRoute può essere fattibile anche se potrebbe causare latenza non necessaria o congestione TCP. In entrambi i casi, è consigliabile instradare il traffico destinato a Internet verso Internet nel sito locale per sfruttare le reti di recapito del contenuto su cui si basa Office 365.
  
![ExpressRoute multi-geography](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Quando Humongous Insurance pianifica la propria strategia multi-geografica, è necessario tenere conto di una serie di aspetti relativi alle dimensioni del circuito, al numero di circuiti, al failover e così via.
  
Con ExpressRoute in un'unica posizione con più aree geografiche che tentano di utilizzare il circuito, Humongous Insurance vuole garantire che le connessioni a Office 365 dall'ufficio remoto siano inviate al datacenter di Office 365 più vicino alla sede centrale e ricevute dalla sede centrale. A tale scopo, Humongous Insurance implementa l'inoltro DNS per ridurre il numero di round trip e ricerche DNS necessarie per stabilire la connessione appropriata con l'ambiente Office 365 più vicino al punto di uscita Internet della sede centrale. Ciò impedisce al client di risolvere un server front-end locale e garantisce che il server Front-End che la persona si connette sia vicino alla sede centrale in cui Humongous Insurance sta peering con Microsoft. È inoltre possibile imparare [ad assegnare un server d'inoltro condizionale per un nome di dominio.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))
  
In questo scenario, il traffico proveniente dall'ufficio remoto risolve l'infrastruttura front-end di Office 365 in Nord America e usa Office 365 per connettersi ai server back-end in base all'architettura dell'applicazione Office 365. Ad esempio, Exchange Online interrompe la connessione in Nord America e tali server front-end si connetterebbero al server cassette postali back-end in qualsiasi posizione del tenant. Tutti i servizi dispongono di un servizio porta anteriore ampiamente distribuito costituito da destinazioni unicast e anycast.
  
Se Humongous ha uffici principali in più continenti, sono consigliati almeno due circuiti attivi/attivi per area geografica per ridurre la latenza per applicazioni sensibili come Skype for Business online. Se tutti gli uffici si trova in un unico continente o non utilizzano la collaborazione in tempo reale, avere un punto di uscita consolidato o distribuito è una decisione specifica del cliente. Quando sono disponibili più circuiti, il routing BGP garantisce il failover nel caso in cui un singolo circuito diventi non disponibile.
  
Ulteriori informazioni sulle configurazioni di [routing di esempio](/azure/expressroute/expressroute-config-samples-routing) e [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat) .
  
## <a name="selective-routing-with-expressroute"></a>Routing selettivo con ExpressRoute

Il routing selettivo con ExpressRoute può essere necessario per diversi motivi, ad esempio per il testing, la distribuzione di ExpressRoute in un sottoinsieme di utenti. Esistono diversi strumenti che i clienti possono usare per instradare in modo selettivo il traffico di rete di Office 365 su ExpressRoute:
  
1. **Filtro delle route/separazione:** consente le route BGP a Office 365 su ExpressRoute a un sottoinsieme di subnet o router. Questo instrada in modo selettivo in base al segmento di rete del cliente o alla posizione fisica dell'ufficio. Ciò è comune per l'implementazione sfalsante di ExpressRoute per Office 365 ed è configurato nei dispositivi BGP.

2. **File/URL PAC** - Indirizzamento del traffico di rete destinato a Office 365 per FQDN specifici da instradare in un percorso specifico. In questo modo viene instradato in modo selettivo dal computer client come identificato dalla [distribuzione di file PAC.](./managing-office-365-endpoints.md)

3. **Filtro route**  -  [I filtri](/azure/expressroute/how-to-routefilter-portal) di route consentono di utilizzare un sottoinsieme di servizi supportati tramite peering Microsoft.

4. **Community BGP:** il filtro basato sui tag [della community BGP](./bgp-communities-in-expressroute.md) consente a un cliente di determinare quali applicazioni di Office 365 attraverseranno ExpressRoute e quali attraverseranno Internet.

Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/erorouting]()
  
## <a name="related-topics"></a>Argomenti correlati

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute per Office 365](azure-expressroute.md)
  
[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)
  
[Pianificazione della rete con ExpressRoute per Office 365](network-planning-with-expressroute.md)
  
[Implementazione di ExpressRoute per Office 365](implementing-expressroute.md)
  
[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Ottimizzazione della rete per Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flusso di chiamata con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Uso delle community BGP in ExpressRoute per scenari di Office 365](bgp-communities-in-expressroute.md)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)
