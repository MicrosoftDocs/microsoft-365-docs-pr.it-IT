---
title: Reti per la distribuzione di contenuti
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: Usare queste informazioni per informazioni su come Office 365 usa le reti per la distribuzione di contenuti (CDN) per migliorare le prestazioni.
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911097"
---
# <a name="content-delivery-networks-cdns"></a>Reti per la distribuzione di contenuti (CDN)

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Le reti CDN consentono di mantenere Office 365 veloce e affidabile per gli utenti finali. I servizi cloud come Office 365 usano reti CDN per memorizzare nella cache asset statici più vicini ai browser che li richiedono per velocizzare i download e ridurre la latenza percepita dagli utenti finali. Le informazioni contenute in questo argomento consentono di ottenere informazioni sulle reti per la distribuzione di contenuti (CDN) e su come vengono utilizzate da Office 365.

## <a name="what-exactly-is-a-cdn"></a>Esattamente, che cos'è esattamente una rete per la distribuzione dei contenuti?

Una rete CDN è una rete geograficamente distribuita costituita da server proxy e file server nei datacenter connessi da reti backbone ad alta velocità. Le reti CDN vengono utilizzate per ridurre la latenza e i tempi di caricamento per un set specificato di file e oggetti in un sito Web o in un servizio. Una rete CDN può avere molte migliaia di endpoint per una manutenzione ottimale delle richieste in arrivo da qualsiasi posizione.

Le reti CDN vengono comunemente utilizzate per fornire download più veloci di contenuto generico per un sito Web o un servizio, ad esempio file javascript, icone e immagini, e possono anche fornire l'accesso privato al contenuto degli utenti, ad esempio file nelle raccolte documenti di SharePoint Online, file multimediali di streaming e codice personalizzato.

Le reti CDN vengono utilizzate dalla maggior parte dei servizi cloud aziendali. I servizi cloud come Office 365 hanno milioni di clienti che scaricano una combinazione di contenuti proprietari (ad esempio messaggi di posta elettronica) e di contenuti generici (ad esempio icone) contemporaneamente. È più efficiente posizionare le immagini utilizzate da tutti, come le icone, il più vicino possibile al computer dell'utente. Non è pratico per ogni servizio cloud creare datacenter CDN che archiviano questo contenuto generico in ogni area metropolitana o persino in ogni hub Internet principale in tutto il mondo, quindi alcune di queste reti CDN sono condivise.

## <a name="how-do-cdns-make-services-work-faster"></a>In che modo le reti per la distribuzione dei contenuti velocizzano l'esecuzione dei servizi?

Il download di oggetti comuni come le immagini e le icone del sito più e più volte può richiedere larghezza di banda di rete che può essere usata meglio per scaricare contenuti personali importanti, come messaggi di posta elettronica o documenti. Poiché Office 365 usa un'architettura che include reti CDN, le icone, gli script e altri contenuti generici possono essere scaricati dai server più vicini ai computer client, velocizzare i download. Ciò significa un accesso più rapido ai contenuti personali, che viene archiviato in modo sicuro nei datacenter di Office 365.

Le reti CDN consentono di migliorare le prestazioni del servizio cloud in diversi modi:

- Le reti CDN spostano parte del carico di download di rete e file dal servizio cloud, liberando le risorse del servizio cloud per la gestione del contenuto degli utenti e di altri servizi riducendo la necessità di gestire le richieste di asset statici.
- Le reti CDN sono state create per fornire l'accesso ai file a bassa latenza implementando reti e file server ad alte prestazioni e sfruttando protocolli di rete aggiornati come [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) con compressione altamente efficiente e multiplexing delle richieste.
- Le reti CDN usano molti endpoint distribuiti a livello globale per rendere il contenuto disponibile il più vicino possibile agli utenti.

## <a name="the-office-365-cdn"></a>Rete CDN di Office 365

La rete CDN (Content Delivery Network) di Office 365 incorporata consente agli amministratori di Office 365 di offrire prestazioni migliori per le pagine di SharePoint Online dell'organizzazione memorizzando nella cache asset statici più vicini ai browser che le richiedono, in modo da velocizzare i download e ridurre la latenza. La rete CDN di Office 365 usa il [protocollo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) per migliorare la compressione e la velocità di download.

> [!NOTE]
> La rete CDN di Office 365 è disponibile solo per i tenant **nel** cloud di produzione (in tutto il mondo). I tenant nel cloud del governo degli Stati Uniti, della Cina e della Germania non supportano attualmente la rete CDN di Office 365.

La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità. In base al tipo di contenuto che si vuole ospitare nella rete per la distribuzione di contenuti di Office 365, è possibile aggiungere origini **pubbliche**, origini **private** o entrambi.

![Diagramma concettuale della rete CDN di Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagramma concettuale della rete CDN di Office 365")

Il contenuto nelle origini **pubbliche** della rete per la distribuzione di contenuti di Office 365 è accessibile in forma anonima, di conseguenza chiunque disponga degli URL delle risorse ospitate può accedervi. Dal momento che l'accesso al contenuto in origini pubbliche è anonimo, è consigliabile usarle solo per memorizzare nella cache contenuti generici non riservati, ad esempio file JavaScript, script, icone e immagini. Per impostazione predefinita, la rete per la distribuzione di contenuti di Office 365 viene usata per il download di risorse generiche, ad esempio le applicazioni client di Office 365 da un'origine pubblica.

**Le** origini private all'interno della rete CDN di Office 365 forniscono l'accesso privato al contenuto degli utenti, ad esempio raccolte documenti, siti e immagini proprietarie di SharePoint Online. L'accesso ai contenuti nelle origini private è protetto con token generati dinamicamente in modo da consentire l'accesso solo agli utenti che dispongono delle autorizzazioni per la raccolta documenti o per la posizione di archiviazione originali. Le origini private della rete per la distribuzione di contenuti di Office 365 possono essere usate solo per contenuti di SharePoint Online. L'accesso alle risorse può avvenire solo tramite il reindirizzamento dal tenant di SharePoint Online.

Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

Per ulteriori informazioni su come usare la rete CDN di Office 365, vedere [Use the Office 365 content delivery network with SharePoint Online.](use-microsoft-365-cdn-with-spo.md)

Per guardare una serie di brevi video che forniscono informazioni concettuali e HOWTO sull'utilizzo della rete CDN di Office 365, visitare il canale YouTube Modelli e procedure per sviluppatori di [SharePoint.](https://aka.ms/sppnp-videos)

## <a name="other-microsoft-cdns"></a>Altre reti CDN Microsoft

Anche se non fa parte della rete CDN di Office 365, è possibile utilizzare queste reti CDN nel tenant di Office 365 per accedere alle raccolte di sviluppo di SharePoint, al codice personalizzato e ad altri scopi che non rientrano nell'ambito della rete CDN di Office 365.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>A partire dal terzo trimestre 2020, SharePoint Online inizierà a memorizzare nella cache i video nella rete CDN di Azure per supportare la riproduzione e l'affidabilità video migliorate. I video più popolari verranno trasmessi dall'endpoint della rete CDN più vicino all'utente. Questi dati rimarranno entro il limite di conformità di Microsoft 365. Si tratta di un servizio gratuito per tutti i tenant e non richiede alcuna azione da parte del cliente per la configurazione.

È possibile usare la **rete CDN** di Azure per distribuire la propria istanza della rete CDN per ospitare web part, raccolte e altre risorse personalizzate, che consente di applicare chiavi di accesso all'archiviazione della rete CDN e esercitare un maggiore controllo sulla configurazione della rete CDN. L'uso della rete CDN di Azure non è gratuito e richiede una sottoscrizione di Azure.

Per ulteriori informazioni su come configurare un'istanza della rete CDN di Azure, vedere Guida introduttiva: Integrare un account di archiviazione di [Azure con la rete CDN di Azure.](/azure/cdn/cdn-create-a-storage-account-with-cdn)

Per un esempio di come usare la rete CDN di Azure per ospitare web part di SharePoint, vedere [Deploy your SharePoint client-side web part to Azure CDN](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Per informazioni sul modulo Azure CDN PowerShell, vedere [Manage Azure CDN with PowerShell.](/azure/cdn/cdn-manage-powershell)

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

La **rete CDN Ajax** di Microsoft è una rete CDN di sola lettura che offre molte librerie di sviluppo popolari, tra cui jQuery (e tutte le altre librerie), ASP.NET Ajax, Bootstrap, Knockout.js e altri.
  
Per includere gli script nel progetto, è sufficiente sostituire i riferimenti a queste raccolte disponibili pubblicamente con riferimenti all'indirizzo della rete CDN anziché includerlo nel progetto stesso. Per creare un collegamento a jQuery, ad esempio, utilizzare il codice seguente:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Per ulteriori informazioni su come usare la rete CDN di Microsoft Ajax, vedere [CdN di Microsoft Ajax.](/aspnet/ajax/cdn/overview)

## <a name="how-does-office-365-use-content-from-a-cdn"></a>In che modo Office 365 usa il contenuto di una rete CDN?

Indipendentemente dalla rete CDN configurata per il tenant di Office 365, il processo di recupero dei dati di base è lo stesso.

1. Il client (un browser o un'applicazione client di Office) richiede i dati da Office 365.

2. Office 365 restituisce i dati direttamente al client oppure, se i dati fanno parte di un set di contenuti ospitati dalla rete CDN, reindirizza il client all'URL della rete CDN.

    a. Se i dati sono già  memorizzati nella cache in un'origine pubblica, il client scarica i dati direttamente dalla posizione CDN più vicina al client.

    b. Se i dati sono già  memorizzati nella cache in un'origine privata, il servizio CDN controlla le autorizzazioni dell'account utente di Office 365 per l'origine. Se si dispone delle autorizzazioni, SharePoint Online genera in modo dinamico un URL personalizzato composto dal percorso dell'asset nella rete CDN e da due token di accesso e restituisce l'URL personalizzato al client. Il client scarica quindi i dati direttamente dalla posizione CDN più vicina al client usando l'URL personalizzato.

3. Se i dati non vengono memorizzati nella cache nella rete CDN, il nodo CDN richiede i dati da Office 365 e quindi li memorizza nella cache per un periodo di tempo dopo che il client scarica i dati.

La rete CDN figura il datacenter più vicino al browser dell'utente e, usando il reindirizzamento, scarica i dati richiesti da lì. Il reindirizzamento della rete CDN è rapido e consente agli utenti di risparmiare molto tempo di download.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Come configurare la rete in modo che le reti CDN funzionino al meglio con Office 365?

Ridurre al minimo la latenza tra i client della rete e gli endpoint della rete CDN è la considerazione fondamentale per garantire prestazioni ottimali. È possibile utilizzare le procedure consigliate descritte in [Managing Office 365 endpoints](managing-office-365-endpoints.md) per garantire che la configurazione di rete consenta ai browser client di accedere direttamente alla rete CDN anziché instradare il traffico della rete CDN attraverso proxy centrali per evitare di introdurre latenza non necessaria.

È inoltre possibile leggere Principi di connettività di rete di [Office 365](./microsoft-365-network-connectivity-principles.md) per comprendere i concetti alla base dell'ottimizzazione delle prestazioni di rete di Office 365.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Esiste un elenco di tutte le reti CDN utilizzate da Office 365?

Le reti CDN in uso da Office 365 sono sempre soggette a modifiche e in molti casi sono presenti più partner CDN configurati nel caso in cui uno non sia disponibile. Le reti CDN principali utilizzate da Office 365 sono:

|Rete CDN  |Company  |Usage  |Collegamento  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Risorse generiche in origini pubbliche, contenuto utente di SharePoint in origini private         |[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |Codice personalizzato, soluzioni SharePoint Framework         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Rete CDN Di Microsoft Ajax (sola lettura)     |Microsoft         |Librerie comuni per Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js e così via.         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Quali vantaggi offre una rete CDN?

Esistono molti fattori coinvolti nella misurazione di differenze specifiche nelle prestazioni tra i dati scaricati direttamente da Office 365 e i dati scaricati da una rete CDN specifica, ad esempio la posizione relativa al tenant e all'endpoint CDN più vicino, il numero di asset in una pagina servita dalla rete CDN e le modifiche temporanee nella latenza di rete e nella larghezza di banda. Tuttavia, un semplice test A/B può aiutare a mostrare la differenza nel tempo di download per un file specifico.

Le schermate seguenti illustrano la differenza nella velocità di download tra il percorso del file nativo in Office 365 e lo stesso file ospitato nella rete per la distribuzione di contenuti [di Microsoft Ajax.](/aspnet/ajax/cdn/overview) Queste schermate sono disponibili nella **scheda Rete** negli strumenti di sviluppo di Internet Explorer 11. Queste schermate mostrano la latenza della popolare libreria jQuery. Per visualizzare questa schermata, in Internet Explorer, premere **F12** e selezionare la scheda **Rete** indicata con un'icona Wi-Fi.
  
![Schermata della rete F12](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Questa cattura di schermata mostra la raccolta caricata nella raccolta pagine master nel sito di SharePoint Online stesso. Il tempo necessario per caricare la raccolta è 1,51 secondi.
  
![Schermata del tempo di caricamento 1.51s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
La seconda schermata mostra lo stesso file fornito dalla rete CDN di Microsoft. Questa volta la latenza è di circa 496 millisecondi. Questo è un grande miglioramento e mostra che un intero secondo viene rasato fuori il tempo totale per scaricare l'oggetto.
  
![Schermata dei tempi di caricamento in 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>I dati sono protetti?

Microsoft si occupa di proteggere i dati che eserciteranno l'azienda. I dati archiviati nella rete CDN di Office 365 vengono crittografati sia in transito che in pausa e l'accesso ai dati nella rete CDN di Office 365 SharePoint è protetto dalle autorizzazioni utente e dall'autorizzazione token di Office 365. Le richieste di dati nella rete CDN di Office 365 SharePoint devono essere inviate (reindirizzate) dal tenant di Office 365 oppure non verrà generato un token di autorizzazione.

Per garantire che i dati rimangano sicuri, è consigliabile non archiviare mai il contenuto dell'utente o altri dati sensibili in una rete CDN pubblica. Poiché l'accesso ai dati in una rete CDN pubblica è anonimo, le reti CDN pubbliche devono essere utilizzate solo per ospitare contenuto generico, ad esempio file script Web, icone, immagini e altri asset non sensibili.

> [!NOTE]
> I provider cdN di terze parti possono avere standard di privacy e conformità diversi dagli impegni delineati dal Centro protezione di Office 365. I dati memorizzati nella cache tramite il servizio CDN potrebbero non essere conformi alle condizioni DPT (Data Processing Terms) di Microsoft e potrebbero essere esterni ai limiti di conformità del Centro protezione di Office 365.

Per informazioni approfondite sulla privacy e sulla protezione dei dati per i provider di reti CDN di Office 365, visitare il sito Web seguente:  

- Per ulteriori informazioni sulla privacy e sulla protezione dei dati di Office 365, vedere Centro protezione [Microsoft](https://www.microsoft.com/trustcenter)
- Per ulteriori informazioni sulla privacy e sulla protezione dei dati di [Akamai,](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp) vedere Il Centro protezione della privacy di Akamai
- Per altre informazioni sulla privacy e sulla protezione dei dati di [Azure,](https://azure.microsoft.com/overview/trusted-cloud/) vedere Centro protezione di Azure

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Come è possibile proteggere la rete con tutti questi servizi di terze parti?

L'utilizzo di un ampio set di servizi partner consente a Office 365 di ridimensionare e soddisfare i requisiti di disponibilità, nonché di migliorare l'esperienza utente quando si usa Office 365. I servizi di terze parti di Office 365 includono entrambi gli elenchi di revoche di certificati; ad esempio crl.microsoft.com o sa.symcb.com e CDN; ad esempio r3.res.outlook.com. Ogni FQDN della rete CDN generato da Office 365 è un FQDN personalizzato per Office 365. Se si viene inviati a un nome di dominio completo su richiesta di Office 365, è possibile essere certi che il provider della rete CDN controlla il nome di dominio completo e il contenuto sottostante in tale posizione.
  
Per i clienti che desiderano separare le richieste destinate a un datacenter di Microsoft o Office 365 dalle richieste destinate a una terza parte, abbiamo scritto indicazioni sulla gestione degli endpoint di [Office 365.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Esiste un elenco di tutti gli FQDN che sfruttano le reti CDN?

L'elenco di FQDN e il modo in cui sfruttano le reti CDN cambiano nel tempo. Fare riferimento alla pagina url e intervalli di indirizzi IP di [Office 365](./urls-and-ip-address-ranges.md) pubblicati per essere aggiornati sugli FQDN più recenti che sfruttano le reti CDN.

È inoltre possibile utilizzare il servizio Web Indirizzo IP e URL di [Office 365](microsoft-365-ip-web-service.md) per richiedere gli URL e gli intervalli di indirizzi IP correnti di Office 365 formattati come CSV o JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>È possibile usare la rete CDN e memorizzare nella cache il contenuto nella rete locale?

Stiamo continuamente cercando nuovi modi per supportare le esigenze dei nostri clienti e stiamo attualmente esplorando l'uso di soluzioni proxy di memorizzazione nella cache e altre soluzioni CDN locali.

Anche se non fa parte della rete CDN di Office 365, è anche possibile usare la **rete CDN** di Azure per ospitare web part, raccolte e altre risorse personalizzate, che consente di applicare i tasti di scelta all'archiviazione della rete CDN ed esercitare un maggiore controllo sulla configurazione della rete CDN. L'uso della rete CDN di Azure non è gratuito e richiede una sottoscrizione di Azure. Per ulteriori informazioni su come configurare un'istanza della rete CDN di Azure, vedere Guida introduttiva: Integrare un account di archiviazione di [Azure con la rete CDN di Azure.](/azure/cdn/cdn-create-a-storage-account-with-cdn)

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Se si usa Azure ExpressRoute per Office 365, le cose cambiano?

[Azure ExpressRoute per Office 365](azure-expressroute.md) offre una connessione dedicata all'infrastruttura di Office 365 che è segregata da Internet pubblico. Ciò significa che i client dovranno comunque connettersi tramite connessioni non ExpressRoute per connettersi alle reti CDN e ad altre infrastrutture Microsoft non esplicitamente incluse nell'elenco dei servizi supportati da ExpressRoute. Per ulteriori informazioni su come instradare il traffico specifico, ad esempio le richieste destinate alle reti CDN, vedere Gestione del traffico di rete di [Office 365.](routing-with-expressroute.md)

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>È possibile utilizzare reti CDN con SharePoint Server locale?

L'uso delle reti CDN ha senso solo in un contesto di SharePoint Online e deve essere evitato con SharePoint Server. Infatti, tutti i vantaggi relativi alla posizione geografica non permangono se il server è locale o geograficamente vicino. Inoltre, se è presente una connessione di rete ai server in cui è ospitato, il sito può essere utilizzato senza una connessione Internet e pertanto non può recuperare i file CDN. In caso contrario, è consigliabile utilizzare una rete CDN se è disponibile e stabile per la raccolta e i file necessari per il sito.
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>Vedere anche

[Principi della connettività di rete di Office 365](./microsoft-365-network-connectivity-principles.md)

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](./urls-and-ip-address-ranges.md)

[Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Centro protezione Microsoft](https://www.microsoft.com/trustcenter)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)