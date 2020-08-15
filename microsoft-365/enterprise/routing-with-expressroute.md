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
description: In questo articolo vengono fornite informazioni sui requisiti di routing, sui circuiti e sui domini di routing di Azure ExpressRoute per l'utilizzo con Office 365.
ms.openlocfilehash: 7201c23777cbf4ca5285736db5a947955a443c51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691014"
---
# <a name="routing-with-expressroute-for-office-365"></a>Routing con ExpressRoute per Office 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Per comprendere adeguatamente il traffico di routing a Office 365 utilizzando Azure ExpressRoute, è necessario disporre di una solida conoscenza dei [requisiti di routing di ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-routing/) di base e dei circuiti di [ExpressRoute e i domini di routing](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/). Questi sono i principi fondamentali per l'utilizzo di ExpressRoute su cui si basano i clienti di Office 365.
  
Di seguito sono elencati alcuni degli articoli principali che è necessario comprendere:
  
- I circuiti di ExpressRoute non vengono mappati a un'infrastruttura fisica specifica, ma sono una connessione logica eseguita in un unico percorso di peering da Microsoft e da un provider di peering per conto dell'utente.

- Esiste una mappatura 1:1 tra un circuito di ExpressRoute e un s-Key del cliente.

- Ogni circuito è in grado di supportare 2 relazioni di peering indipendenti (peering privato di Azure e peering Microsoft); Office 365 richiede peering Microsoft.

- Ogni circuito ha una larghezza di banda fissa condivisa tra tutte le relazioni di peering.

- Tutti gli indirizzi IPv4 pubblici e i numeri pubblici che verranno utilizzati per il circuito di ExpressRoute devono essere convalidati come di proprietà dell'utente o assegnati esclusivamente all'utente dal proprietario dell'intervallo di indirizzi.

- I circuiti ExpressRoute virtuali sono ridondanti a livello globale e seguiranno procedure di routing standard BGP. Per questo motivo, si consiglia di utilizzare due circuiti fisici per ogni uscita al provider in una configurazione attiva/attiva.

Per ulteriori informazioni sui servizi supportati, i costi e i dettagli di configurazione, vedere la [pagina delle domande frequenti](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) . Vedere l' [articolo posizioni ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) per informazioni sull'elenco dei provider di connettività che offrono supporto per peering Microsoft. Inoltre, è stata registrata una serie di [corsi di formazione di Azure ExpressRoute per Office 365](https://channel9.msdn.com/series/aer) in 10 parti su Channel 9 per spiegare i concetti in modo più approfondito.
  
## <a name="ensuring-route-symmetry"></a>Garantire la simmetria del percorso

I front end server di Office 365 sono accessibili sia su Internet che su ExpressRoute. Questi server preferiscono ripartire nei circuiti locali su ExpressRoute quando sono disponibili entrambi. Per questo motivo esiste la possibilità di instradare l'asimmetria se il traffico della rete preferisce instradare i circuiti Internet. Le route asimmetriche rappresentano un problema perché i dispositivi che eseguono l'ispezione di pacchetti con stato possono bloccare il traffico di ritorno che segue un percorso diverso rispetto ai pacchetti in uscita seguiti.
  
Indipendentemente dal fatto che si avvii una connessione a Office 365 su Internet o ExpressRoute, l'origine deve essere un indirizzo instradabile pubblicamente. Con molti clienti che si occupano di peering direttamente con Microsoft, non è possibile disporre di indirizzi privati in cui la duplicazione può essere intervista.
  
Di seguito sono illustrati gli scenari in cui verranno avviate le comunicazioni da Office 365 alla rete locale. Per semplificare la progettazione della rete, è consigliabile instradarli sul percorso Internet.
  
- Servizi SMTP come la posta da un tenant di Exchange Online a un host locale o a una posta di SharePoint Online inviata da SharePoint Online a un host locale. Il protocollo SMTP viene utilizzato in modo più generale all'interno della rete Microsoft rispetto ai prefissi di route condivisi su ExpressRoute e ai server SMTP locali pubblicitari su ExpressRoute che causano errori con gli altri servizi.

- ADFS durante la convalida delle password per l'accesso.

- [Distribuzioni ibride di Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- [Ricerca ibrida federata di SharePoint](https://technet.microsoft.com/library/dn197174.aspx).

- [BCS ibrido di SharePoint](https://technet.microsoft.com/library/dn197239.aspx ).

- Federazione di [Skype for business ibrida](https://technet.microsoft.com/library/jj205403.aspx) e/o [Skype for business](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Connettore Cloud Skype for business](https://technet.microsoft.com/library/mt605227.aspx ).

Per instradare nuovamente la rete per questi flussi di traffico bi-direzionale, le route BGP ai dispositivi locali devono essere condivise con Microsoft. Quando si pubblicizzano i prefissi di route su Microsoft su ExpressRoute, è consigliabile attenersi alle procedure consigliate riportate di seguito:

1) Non annunciare lo stesso prefisso per l'indirizzo IP pubblico alla rete pubblica Internet e su ExpressRoute. È consigliabile che la route IP BGP prefissi gli annunci pubblicitari a Microsoft su ExpressRoute provengano da un intervallo non pubblicizzato su Internet. Se non è possibile ottenerlo a causa dello spazio di indirizzi IP disponibile, è essenziale garantire che venga pubblicizzato un intervallo più specifico rispetto a ExpressRoute rispetto a qualsiasi circuito Internet.

2) Utilizzare pool IP NAT distinti per ogni circuito di ExpressRoute e separato da quello dei circuiti Internet.

3) Tenere presente che qualsiasi route pubblicizzata a Microsoft attirerà il traffico di rete da qualsiasi server della rete Microsoft, non solo quelli per cui le route vengono pubblicizzate nella rete su ExpressRoute. Pubblicizzare solo le route verso i server in cui gli scenari di routing sono definiti e ben compresi dal team. Pubblicizzare i prefissi degli indirizzi IP separati in ognuno dei circuiti di ExpressRoute multipli dalla rete.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Decidere le applicazioni e le funzionalità Route over ExpressRoute

Quando si configura una relazione di peering utilizzando il dominio di routing peering di Microsoft e sono approvati per l'accesso appropriato, è possibile visualizzare tutti i servizi PaaS e SaaS disponibili su ExpressRoute. I servizi di Office 365 creati per ExpressRoute possono essere gestiti con le [community BGP](https://aka.ms/bgpexpressroute365) o con i [filtri di route](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal).
  
Altre applicazioni, ad esempio Office 365 video, sono un'applicazione di Office 365. Tuttavia, Office 365 video è costituito da tre diversi componenti, il portale, il servizio di flusso e la rete di distribuzione del contenuto. Il portale vive all'interno di SharePoint Online, il servizio di flusso vive all'interno di Azure Media Services e la rete di distribuzione del contenuto vive all'interno della CDN di Azure. Nella tabella seguente vengono descritti i componenti.

|**Componente**|**Applicazione sottostante**|**Incluso nella community di SharePoint Online BGP?**|**Utilizzo**|
|:-----|:-----|:-----|:-----|
|Portale video di Office 365  <br/> |SharePoint Online  <br/> |Sì  <br/> |Configurazione, caricamento  <br/> |
|Servizio di streaming video di Office 365  <br/> |Servizi multimediali di Azure  <br/> |No  <br/> |Servizio di flusso, utilizzato nel caso in cui il video non sia disponibile dalla rete CDN  <br/> |
|Rete di distribuzione del contenuto video di Office 365  <br/> |Rete CDN di Azure  <br/> |No  <br/> |Origine principale del download/streaming video. [Per ulteriori informazioni, vedere rete video di Office 365](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e).  <br/> |

Tutte le funzionalità di Office 365 disponibili con Microsoft peering sono elencate nell' [articolo endpoint di office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) in base al tipo di applicazione e al nome di dominio completo. Il motivo dell'utilizzo del nome di dominio completo nelle tabelle consiste nel consentire ai clienti di gestire il traffico mediante file PAC o altre configurazioni proxy, vedere la guida per la [gestione degli endpoint di Office 365](https://aka.ms/manageo365endpoints) , ad esempio i file PAC.
  
In alcuni casi è stato utilizzato un dominio con caratteri jolly in cui uno o più FQDN secondari sono pubblicizzati in modo diverso rispetto al dominio con caratteri jolly di livello superiore. Questo accade in genere quando il carattere jolly rappresenta un lungo elenco di server che sono tutti annunciati a ExpressRoute e a Internet, mentre un piccolo set di destinazioni è solo pubblicizzato su Internet o viceversa. Fare riferimento alle tabelle riportate di seguito per capire dove sono le differenze.
  
In questa tabella vengono visualizzati i nomi FQDN dei caratteri jolly pubblicizzati sia in Internet che in Azure ExpressRoute insieme ai sub-FQDN che vengono pubblicizzati solo su Internet.

|**Dominio con caratteri jolly pubblicizzato su ExpressRoute e circuiti Internet**|**FQDN secondario pubblicizzato solo sui circuiti Internet**|
|:-----|:-----|
|\*. microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*. officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

In genere i file PAC sono destinati a inviare richieste di rete a ExpressRoute gli endpoint annunciati direttamente al circuito e a tutte le altre richieste di rete al proxy. Se si sta configurando un file PAC come questo, comporre il file PAC nell'ordine seguente:
  
1. Includere i sub-FQDN dalla colonna 2 nella tabella precedente nella parte superiore del file PAC, inviando il traffico verso il proxy. È stato creato un file PAC di esempio da utilizzare nel nostro articolo relativo alla [gestione degli endpoint di Office 365](https://aka.ms/manageexpressroute365).

2. Includere tutti i nomi FQDN contrassegnati come pubblicizzati in ExpressRoute in [questo articolo](https://aka.ms/o365endpoints) sotto la prima sezione, inviando il traffico direttamente al circuito ExpressRoute.

3. Includere qualsiasi altro endpoint o regola di rete al di sotto di queste due voci, inviando il traffico verso il proxy.

In questa tabella vengono visualizzati i domini jolly che vengono pubblicizzati nei circuiti Internet solo insieme ai sub-FQDN che vengono pubblicizzati in Azure ExpressRoute e nei circuiti Internet. Per il file PAC precedente, i nomi FQDN nella colonna 2 della tabella seguente sono elencati come annunciati a ExpressRoute nel collegamento a cui si fa riferimento, il che significa che verrebbero inclusi nel secondo gruppo di voci del file.

|**Dominio con caratteri jolly pubblicizzato solo sui circuiti Internet**|**FQDN secondario pubblicizzato in ExpressRoute e circuiti Internet**|
|:-----|:-----|
|\*. office.com  <br/> |\*. outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*. office.net  <br/> |agent.office.net  <br/> |
|\*. office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*. outlook.com  <br/> |\*. protection.outlook.com  <br/> \*. mail.protection.outlook.com  <br/> individuazione automatica- \<tenant\> . Outlook.com  <br/> |
|\*. windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Routing di Office 365 traffico su Internet e ExpressRoute

Per instradare l'applicazione Office 365 di vostra scelta, è necessario determinare una serie di fattori chiave.
  
1. La quantità di larghezza di banda necessaria per l'applicazione. Il campionamento dell'utilizzo esistente è l'unico metodo affidabile per determinarlo nell'organizzazione.

2. Quali posizioni di uscita per le quali si desidera che il traffico di rete lasci la rete. È consigliabile pianificare la riduzione della latenza di rete per la connettività a Office 365 perché avrà un impatto sulle prestazioni. Poiché Skype for business usa la voce e il video in tempo reale, è particolarmente suscettibile alla scarsa latenza della rete.

3. Se si desidera che tutti o un sottoinsieme dei percorsi di rete ExpressRoute.

4. Quali sono le posizioni in cui il provider di rete scelto offre ExpressRoute.

Dopo aver determinato le risposte a queste domande, è possibile effettuare il provisioning di un circuito di ExpressRoute che soddisfi le esigenze di larghezza di banda e posizione. Per ulteriori informazioni sulla pianificazione della rete, vedere la [Guida alla ottimizzazione della rete di Office 365](https://aka.ms/tune) e il [case study su come Microsoft gestisce la pianificazione delle prestazioni della rete](https://aka.ms/tunemsit).
  
### <a name="example-1-single-geographic-location"></a>Esempio 1: posizione geografica singola
  
Questo esempio è uno scenario per una società fittizia denominata Trey Research che dispone di una singola posizione geografica.
  
Ai dipendenti di Trey Research è consentito connettersi solo ai servizi e ai siti web su Internet che il reparto di sicurezza consente in modo esplicito sulla coppia di proxy in uscita che si trovano tra la rete aziendale e il relativo ISP.
  
Trey Research prevede di utilizzare Azure ExpressRoute per Office 365 e riconosce che alcuni traffici, ad esempio il traffico destinato alle reti di distribuzione del contenuto, non saranno in grado di instradare la connessione ExpressRoute per Office 365. Poiché tutto il traffico è già stato indirizzato ai dispositivi proxy per impostazione predefinita, queste richieste continueranno a funzionare come in precedenza. Dopo che Trey Research ha stabilito che è in grado di soddisfare i requisiti di routing di Azure ExpressRoute, si procede alla creazione di un circuito, alla configurazione del routing e al collegamento del nuovo circuito ExpressRoute a una rete virtuale. Dopo che è stata eseguita la configurazione di Azure ExpressRoute fondamentale, Trey Research utilizza il [file di #2 PAC che viene pubblicato](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) per instradare il traffico con dati specifici del cliente tramite la ExpressRoute Direct per le connessioni di Office 365.
  
Come illustrato nel diagramma seguente, Trey Research è in grado di soddisfare i requisiti necessari per instradare il traffico di Office 365 su Internet e un sottoinsieme del traffico su ExpressRoute utilizzando una combinazione di modifiche di configurazione del routing e del proxy in uscita.
  
1. Utilizzando il [file di #2 PAC che viene pubblicato](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) per instradare il traffico attraverso un punto di uscita Internet separato per Azure ExpressRoute per Office 365.

2. I client sono configurati con una route predefinita verso i proxy di Trey Research.

In questo scenario di esempio, Trey Research utilizza un dispositivo proxy in uscita. Analogamente, i clienti che non utilizzano Azure ExpressRoute per Office 365 possono utilizzare questa tecnica per instradare il traffico in base ai costi di controllo del traffico destinati ad endpoint di alto volume noti.
  
Gli FQDN dei volumi più alti per Exchange Online, SharePoint Online e Skype for business online sono i seguenti:
  
![Rete perimetrale dei clienti di ExpressRoute](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>. SharePoint.com, \<tenant-name\> -My.SharePoint.com, \<tenant-name\> - \<app\> . SharePoint.com

- \*. Lync.com insieme agli intervalli IP per il traffico non TCP

- \*broadcast.officeapps.live.com, \* Excel.officeapps.Live.com, \* onenote.officeapps.live.com, \* PowerPoint.officeapps.Live.com, \* view.officeapps.live.com, \* Visio.officeapps.Live.com, \* Word-Edit.officeapps.Live.com, Word-View.officeapps.Live.com \* , Office.Live.com

Per ulteriori informazioni, vedere [distribuzione e gestione delle impostazioni proxy in Windows 8](https://blogs.technet.com/b/deploymentguys/archive/2013/05/08/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy.aspx) e [garantire che Office 365 non sia limitato dal proxy](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx).
  
Con un singolo circuito di ExpressRoute non è disponibile un'elevata disponibilità per Trey Research. Nella coppia di dispositivi perimetrali ridondanti dell'evento Trey che stanno servendo la connettività di ExpressRoute non è possibile eseguire il failover di un circuito ExpressRoute aggiuntivo. Questo lascia Trey Research in una situazione in cui il failover su Internet richiederà la riconfigurazione manuale e, in alcuni casi, nuovi indirizzi IP. Se Trey desidera aggiungere disponibilità elevata, la soluzione più semplice consiste nell'aggiungere ulteriori circuiti di ExpressRoute per ogni posizione e configurare i circuiti in modo attivo/attivo.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Routing di ExpressRoute per Office 365 con più percorsi

L'ultimo scenario, instradare il traffico di Office 365 su ExpressRoute, è la base per un'architettura di routing ancora più complessa. Indipendentemente dal numero di posizioni, dal numero di continenti in cui sono presenti tali posizioni, dal numero di circuiti di ExpressRoute e così via, è possibile instradare il traffico verso Internet ed è necessario un certo traffico su ExpressRoute.
  
Le domande aggiuntive che devono essere risolte per i clienti con più posizioni in più aree geografiche includono:
  
1. È necessario un circuito ExpressRoute in tutte le posizioni? Se si utilizza Skype for business online o si è preoccupati per la sensibilità alla latenza per SharePoint Online o Exchange Online, è consigliabile utilizzare una coppia ridondante di circuiti ExpressRoute attivi/attivi in ogni posizione. Per ulteriori informazioni, vedere la guida alla qualità multimediale di Skype for business e la connettività di rete.

2. Se un circuito di ExpressRoute non è disponibile in una determinata area, come deve essere instradato il traffico destinato a Office 365?

3. Qual è il metodo preferito per il consolidamento del traffico nel caso di reti con molte piccole posizioni?

Ognuna di queste rappresenta una sfida unica che richiede di valutare la propria rete e le opzioni disponibili da Microsoft.

|**Considerazione**|**Componenti di rete da valutare**|
|:-----|:-----|
|Circuiti in più di una posizione  <br/> |È consigliabile disporre di un minimo di due circuiti configurati in modo attivo/attivo.  <br/> Il costo, la latenza e la larghezza di banda devono essere confrontate.  <br/> Utilizzo del costo della route BGP, dei file PAC e del NAT per gestire il routing con più circuiti.  <br/> |
|Routing da percorsi senza un circuito ExpressRoute  <br/> |Si consiglia l'uscita e la risoluzione DNS più vicina alla persona che ha avviato la richiesta di Office 365.  <br/> L'inoltro DNS può essere utilizzato per consentire agli uffici remoti di individuare l'endpoint appropriato.  <br/> I client di Office remote devono disporre di una route disponibile che consente di accedere al circuito di ExpressRoute.  <br/> |
|Piccolo consolidamento di Office  <br/> |La larghezza di banda disponibile e l'utilizzo dei dati devono essere confrontati accuratamente.  <br/> |

> [!NOTE]
> Microsoft preferirà ExpressRoute su Internet se la route è disponibile indipendentemente dalla posizione fisica.
  
Ognuna di queste considerazioni deve essere presa in considerazione per ogni rete univoca. Di seguito è riportato un esempio.
  
### <a name="example-2-multi-geographic-locations"></a>Esempio 2: percorsi multi-geografici
  
Questo esempio è uno scenario per una società fittizia denominata assicurazioni di nome gigantesco che dispone di più posizioni geografiche.
  
L'assicurazione gigantesca è dislocata geograficamente con uffici di tutto il mondo. Si desidera implementare Azure ExpressRoute per Office 365 per mantenere la maggior parte del traffico di Office 365 su connessioni di rete dirette. La coesistenza di assicurazioni ha anche uffici in due continenti aggiuntivi. Per utilizzare una connessione ExpressRoute, è necessario che i dipendenti dell'ufficio remoto in cui ExpressRoute non sia possibile eseguire il routing di nuovo a una o entrambe le strutture principali.
  
Il principio guida è di ottenere il traffico destinato a un centro dati Microsoft Office 365 al più presto possibile. In questo esempio, l'assicurazione gigantesca deve decidere se le proprie sedi remote devono essere instradate su Internet per accedere a un datacenter Microsoft su qualsiasi connessione il più velocemente possibile o se le rispettive sedi remote devono essere instradate su una rete interna per accedere a un datacenter Microsoft su una connessione ExpressRoute il più velocemente possibile.
  
I datacenter, le reti e l'architettura delle applicazioni di Microsoft sono stati studiati per rendere più efficienti le comunicazioni e il servizio nel modo più efficiente possibile. Si tratta di una delle reti più grandi al mondo. Le richieste destinate a Office 365 che rimangono sulle reti dei clienti più lunghe del necessario non potranno usufruire di questa architettura.
  
Nel caso di una situazione di assicurazione di tipo gigantesco, dovrebbero procedere a seconda delle applicazioni che intendono utilizzare su ExpressRoute. Ad esempio, se si tratta di un cliente di Skype for business online o si intende utilizzare la connettività di ExpressRoute per la connessione a riunioni esterne di Skype for business online, la progettazione consigliata nella Guida alla qualità multimediale di Skype for business online e alla connettività di rete è quella di eseguire il provisioning di un ulteriore circuito di ExpressRoute per la terza posizione. Questo potrebbe essere più costoso rispetto a una prospettiva di rete. Tuttavia, l'instradamento delle richieste da un continente all'altro prima del recapito a un datacenter Microsoft può causare un'esperienza scarsa o inutilizzabile durante le riunioni e le comunicazioni di Skype for business online.
  
Se l'assicurazione non è in uso o non prevede di utilizzare Skype for business online in alcun modo, in365 stradare il traffico di rete destinato a un continente con una connessione ExpressRoute potrebbe essere possibile anche se potrebbe causare latenza o congestione TCP inutili. In entrambi i casi, è consigliabile instradare il traffico destinato a Internet su Internet nel sito locale per sfruttare le reti di distribuzione del contenuto su cui si basa Office 365.
  
![ExpressRoute multi-geography](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Quando l'assicurazione gigante sta pianificando la propria strategia di multi-geografia, sono disponibili diverse considerazioni sulla dimensione del circuito, il numero di circuiti, il failover e così via.
  
Con ExpressRoute in un'unica posizione con più aree che tentano di utilizzare il circuito, l'assicurazione gigante vuole garantire che le connessioni a Office 365 dall'ufficio remoto vengano inviate al centro dati di Office 365 più vicino al quartier generale e ricevute dal percorso della sede centrale. A tale scopo, l'assicurazione di tipo gigantesco implementa l'inoltro DNS per ridurre il numero di round trip e le ricerche DNS necessarie per stabilire la connessione appropriata con l'ambiente Office 365 più vicino al punto di uscita Internet della sede centrale. In questo modo si impedisce al client di risolvere un front end server locale e garantisce che il front end server a cui si connette la persona sia vicino alla sede centrale, in cui l'assicurazione è in peering con Microsoft. È inoltre possibile imparare a [assegnare un forwarder condizionale per un nome di dominio](https://technet.microsoft.com/library/Cc794735%28v=WS.10%29.aspx).
  
In questo scenario, il traffico proveniente dall'ufficio remoto risolverebbe l'infrastruttura di Office 365 front end nel Nord America e sfrutterà Office 365 per connettersi ai server back-end in base all'architettura dell'applicazione Office 365. Ad esempio, Exchange Online disporrà la connessione in Nord America e i Front End Server si connetteranno al server cassette postali di backend laddove risiedeva il tenant. Tutti i servizi dispongono di un servizio front door ampiamente distribuito costituito da destinazioni unicast e anycast.
  
Se il numeroso ha uffici importanti in più continenti, è consigliato un minimo di due circuiti attivi/attivi per ogni area geografica per ridurre la latenza per le applicazioni sensibili come Skype for business online. Se tutti gli uffici si trovano in un unico continente o non utilizzano la collaborazione in tempo reale, la scelta di un punto di uscita consolidato o distribuito è una decisione specifica del cliente. Quando sono disponibili più circuiti, il routing BGP assicurerà il failover nel caso in cui un singolo circuito diventi non disponibile.
  
Per ulteriori informazioni, vedere [configurazioni di routing](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-routing/) di esempio e [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/) .
  
## <a name="selective-routing-with-expressroute"></a>Routing selettivo con ExpressRoute

Il routing selettivo con ExpressRoute può essere necessario per una serie di motivi, ad esempio testing, implementazione di ExpressRoute a un sottoinsieme di utenti. Sono disponibili vari strumenti che i clienti possono utilizzare per instradare selettivamente il traffico di rete di Office 365 su ExpressRoute:
  
1. **Route filtering/segregazione** -consentendo la route BGP a Office 365 su ExpressRoute a un sottoinsieme delle subnet o dei router. Questo consente di instradare selettivamente il segmento di rete del cliente o la posizione fisica dell'ufficio. Questo è comune per l'implementazione scaglionata di ExpressRoute per Office 365 ed è configurata nei dispositivi BGP.

2. **File PAC/URL** -direzione del traffico di rete destinato a Office 365 per FQDN specifici da instradare su un percorso specifico. Questo consente di instradare selettivamente il computer client come identificato dalla [distribuzione dei file PAC](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies).

3. **Filtro route**  -  I [filtri route](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) sono un modo per utilizzare un sottoinsieme di servizi supportati tramite peering Microsoft.

4. **Comunità BGP** -il filtro basato sui [tag della community BGP](https://aka.ms/bgpexpressroute365) consente a un cliente di determinare quali applicazioni di Office 365 attraverserà ExpressRoute e che attraverserà Internet.

Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/erorouting](https://aka.ms/erorouting)
  
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
  
[Utilizzo delle community BGP in ExpressRoute per gli scenari di Office 365](bgp-communities-in-expressroute.md)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)
