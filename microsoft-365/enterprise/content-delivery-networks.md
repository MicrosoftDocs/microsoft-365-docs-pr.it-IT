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
description: Usa queste informazioni per informazioni su come Office 365 reti per la distribuzione di contenuti (CDN) per migliorare le prestazioni.
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911097"
---
# <a name="content-delivery-networks-cdns"></a>Reti per la distribuzione di contenuti (CDN)

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Le reti CDN consentono di Office 365 veloci e affidabili per gli utenti finali. I servizi cloud come Office 365 usano reti CDN per memorizzare nella cache asset statici più vicini ai browser che li richiedono per velocizzare i download e ridurre la latenza percepita dagli utenti finali. Le informazioni contenute in questo argomento consentono di ottenere informazioni sulle reti per la distribuzione di contenuti (CDN) e su come vengono utilizzate da Office 365.

## <a name="what-exactly-is-a-cdn"></a>Esattamente, che cos'è esattamente una rete per la distribuzione dei contenuti?

Un rete CDN è una rete geograficamente distribuita costituita da server proxy e file server in datacenter connessi da reti backbone ad alta velocità. Le reti CDN vengono utilizzate per ridurre la latenza e i tempi di caricamento per un set specificato di file e oggetti in un sito Web o in un servizio. Un rete CDN può avere molte migliaia di endpoint per una manutenzione ottimale delle richieste in arrivo da qualsiasi posizione.

Le reti CDN vengono comunemente usate per fornire download più veloci di contenuto generico per un sito Web o un servizio, ad esempio file JavaScript, icone e immagini, e possono anche fornire l'accesso privato al contenuto degli utenti, ad esempio i file nelle raccolte documenti di SharePoint Online, i file multimediali di streaming e il codice personalizzato.

Le reti CDN vengono utilizzate dalla maggior parte dei servizi cloud aziendali. I servizi cloud Office 365 milioni di clienti scaricano una combinazione di contenuti proprietari (ad esempio messaggi di posta elettronica) e di contenuti generici (ad esempio icone) contemporaneamente. È più efficiente posizionare le immagini utilizzate da tutti, come le icone, il più vicino possibile al computer dell'utente. Non è pratico per ogni servizio cloud creare datacenter di rete CDN che archiviano questo contenuto generico in ogni area metropolitana o persino in ogni hub Internet principale in tutto il mondo, quindi alcune di queste reti CDN sono condivise.

## <a name="how-do-cdns-make-services-work-faster"></a>In che modo le reti per la distribuzione dei contenuti velocizzano l'esecuzione dei servizi?

Il download di oggetti comuni come le immagini e le icone del sito più e più volte può richiedere larghezza di banda di rete che può essere usata meglio per scaricare contenuti personali importanti, come messaggi di posta elettronica o documenti. Poiché Office 365 un'architettura che include reti CDN, le icone, gli script e altri contenuti generici possono essere scaricati dai server più vicini ai computer client, velocizzare i download. Ciò significa un accesso più rapido ai contenuti personali, che viene archiviato in modo sicuro in Office 365 datacenter.

Le reti CDN consentono di migliorare le prestazioni del servizio cloud in diversi modi:

- Le reti CDN spostano parte del carico di download di rete e file dal servizio cloud, liberando le risorse del servizio cloud per la gestione del contenuto degli utenti e di altri servizi riducendo la necessità di gestire le richieste di asset statici.
- Le reti CDN sono state create per fornire l'accesso ai file a bassa latenza implementando reti e file server ad alte prestazioni e sfruttando protocolli di rete aggiornati come [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) con compressione altamente efficiente e multiplexing delle richieste.
- rete CDN le reti usano molti endpoint distribuiti a livello globale per rendere il contenuto disponibile il più vicino possibile agli utenti.

## <a name="the-office-365-cdn"></a>Il Office 365 rete CDN

Il Office 365 rete per la distribuzione di contenuti (rete CDN) incorporato consente agli amministratori di Office 365 di offrire prestazioni migliori per le pagine di SharePoint Online dell'organizzazione memorizzando nella cache asset statici più vicini ai browser che le richiedono, in modo da velocizzare i download e ridurre la latenza. Il Office 365 rete CDN utilizza il [protocollo HTTP/2 per](https://en.wikipedia.org/wiki/HTTP/2) migliorare la compressione e la velocità di download.

> [!NOTE]
> Il Office 365 rete CDN è disponibile solo per i tenant **nel** cloud di produzione (globale). I tenant nel cloud del governo degli Stati Uniti, della Cina e della Germania non supportano attualmente il Office 365 rete CDN.

La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità. In base al tipo di contenuto che si vuole ospitare nella rete per la distribuzione di contenuti di Office 365, è possibile aggiungere origini **pubbliche**, origini **private** o entrambi.

![Office 365 rete CDN concettuale](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 rete CDN concettuale")

Il contenuto nelle origini **pubbliche** della rete per la distribuzione di contenuti di Office 365 è accessibile in forma anonima, di conseguenza chiunque disponga degli URL delle risorse ospitate può accedervi. Dal momento che l'accesso al contenuto in origini pubbliche è anonimo, è consigliabile usarle solo per memorizzare nella cache contenuti generici non riservati, ad esempio file JavaScript, script, icone e immagini. Per impostazione predefinita, la rete per la distribuzione di contenuti di Office 365 viene usata per il download di risorse generiche, ad esempio le applicazioni client di Office 365 da un'origine pubblica.

**Le** origini private all'interno Office 365 rete CDN l'accesso privato al contenuto degli utenti, ad esempio raccolte documenti, siti e immagini proprietarie di SharePoint Online. L'accesso ai contenuti nelle origini private è protetto con token generati dinamicamente in modo da consentire l'accesso solo agli utenti che dispongono delle autorizzazioni per la raccolta documenti o per la posizione di archiviazione originali. Le origini private della rete per la distribuzione di contenuti di Office 365 possono essere usate solo per contenuti di SharePoint Online. L'accesso alle risorse può avvenire solo tramite il reindirizzamento dal tenant di SharePoint Online.

Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

Per ulteriori informazioni su come usare il Office 365 rete CDN, vedere [Use the Office 365 content delivery network with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

Per guardare una serie di brevi video che forniscono informazioni concettuali e HOWTO sull'uso del Office 365 rete CDN, visita il canale [YouTube SharePoint Developer Patterns and Practices.](https://aka.ms/sppnp-videos)

## <a name="other-microsoft-cdns"></a>Altre reti CDN Microsoft

Anche se non fa parte del Office 365 rete CDN, è possibile usare queste reti CDN nel tenant di Office 365 per accedere alle librerie di sviluppo di SharePoint, al codice personalizzato e ad altri scopi che non rientrano nell'ambito del Office 365 rete CDN.

### <a name="azure-cdn"></a>Rete CDN di Azure

>[!NOTE]
>A partire dal terzo trimestre 2020, SharePoint Online inizierà a memorizzare nella cache i video Rete CDN di Azure per supportare la riproduzione e l'affidabilità video migliorate. I video più popolari verranno trasmessi dall rete CDN endpoint più vicino all'utente. Questi dati rimarranno all'interno del Microsoft 365 di conformità. Si tratta di un servizio gratuito per tutti i tenant e non richiede alcuna azione da parte del cliente per la configurazione.

È possibile utilizzare **il Rete CDN di Azure** per distribuire la propria istanza di rete CDN per ospitare web part, raccolte e altre risorse personalizzate, che consente di applicare i tasti di scelta all'archiviazione di rete CDN e esercitare un maggiore controllo sulla configurazione rete CDN. L'uso del Rete CDN di Azure non è gratuito e richiede una sottoscrizione di Azure.

Per altre informazioni su come configurare un'istanza Rete CDN di Azure, vedere Guida introduttiva: Integrare un account di archiviazione di [Azure con Rete CDN di Azure](/azure/cdn/cdn-create-a-storage-account-with-cdn).

Per un esempio di come utilizzare Rete CDN di Azure per ospitare web part SharePoint, vedere [Deploy your SharePoint client-side web part to Rete CDN di Azure](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Per informazioni sul modulo Rete CDN di Azure PowerShell, vedere [Manage Rete CDN di Azure with PowerShell](/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax rete CDN

Microsoft Ajax **rete CDN** è un rete CDN di sola lettura che offre molte librerie di sviluppo popolari tra cui jQuery (e tutte le altre librerie), ASP.NET Ajax, Bootstrap, Knockout.js e altri.
  
Per includere gli script nel progetto, è sufficiente sostituire i riferimenti a queste raccolte disponibili pubblicamente con riferimenti all'indirizzo della rete CDN anziché includerlo nel progetto stesso. Per creare un collegamento a jQuery, ad esempio, utilizzare il codice seguente:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Per ulteriori informazioni sull'utilizzo di Microsoft Ajax rete CDN, vedere [Microsoft Ajax rete CDN](/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>In che modo Office 365 il contenuto di un rete CDN?

Indipendentemente dalle rete CDN configurate per il tenant Office 365, il processo di recupero dei dati di base è lo stesso.

1. Il client (un browser o un Office appalto client) richiede i dati da Office 365.

2. Office 365 restituisce i dati direttamente al client o, se i dati fanno parte di un set di contenuto ospitato dal rete CDN, reindirizza il client all'URL rete CDN.

    a. Se i dati sono già  memorizzati nella cache in un'origine pubblica, il client li scarica direttamente dal percorso rete CDN più vicino al client.

    b. Se i dati sono già  memorizzati nella cache in un'origine privata, il servizio rete CDN verifica le autorizzazioni dell'account Office 365'account utente per l'origine. Se si dispone delle autorizzazioni, SharePoint Online genera dinamicamente un URL personalizzato composto dal percorso dell'asset nel rete CDN e da due token di accesso e restituisce l'URL personalizzato al client. Il client scarica quindi i dati direttamente dalla posizione rete CDN più vicina al client usando l'URL personalizzato.

3. Se i dati non vengono memorizzati nella cache nel rete CDN, il nodo rete CDN richiede i dati da Office 365 e quindi li memorizza nella cache per un periodo di tempo dopo che il client scarica i dati.

Il rete CDN il datacenter più vicino al browser dell'utente e, usando il reindirizzamento, scarica i dati richiesti da lì. rete CDN il reindirizzamento rapido e può consentire agli utenti di risparmiare molto tempo di download.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Come configurare la rete in modo che le reti CDN funzionino meglio con Office 365?

Ridurre al minimo la latenza tra i client della rete e rete CDN endpoint è fondamentale per garantire prestazioni ottimali. È possibile utilizzare le procedure consigliate descritte in [Managing Office 365 endpoints](managing-office-365-endpoints.md) per garantire che la configurazione di rete consenta ai browser client di accedere direttamente al rete CDN anziché instradare il traffico rete CDN attraverso proxy centrali per evitare di introdurre latenza non necessaria.

È inoltre possibile leggere i [Office 365 di](./microsoft-365-network-connectivity-principles.md) connettività di rete per comprendere i concetti alla base dell'ottimizzazione Office 365 prestazioni di rete.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Esiste un elenco di tutte le reti CDN Office 365 utilizzato?

Le reti CDN in uso Office 365 sono sempre soggette a modifiche e in molti casi sono presenti più rete CDN partner configurati nel caso in cui uno non sia disponibile. Le reti CDN principali utilizzate da Office 365 sono:

|Rete CDN  |Company  |Utilizzo  |Collegamento  |
|---------|---------|---------|---------|
|Office 365 rete CDN     |Akamai         |Risorse generiche in origini pubbliche, SharePoint contenuto utente in origini private         |[Usare la Office 365 di recapito del contenuto con SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Rete CDN di Azure     |Microsoft         |Codice personalizzato, soluzioni SharePoint Framework personalizzate         |[Microsoft Azure rete CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax rete CDN (sola lettura)     |Microsoft         |Librerie comuni per Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js e così via.         |[Microsoft Ajax rete CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Quali vantaggi offre una rete CDN prestazioni?

Esistono molti fattori coinvolti nella misurazione di differenze specifiche nelle prestazioni tra i dati scaricati direttamente da Office 365 e i dati scaricati da un rete CDN specifico, ad esempio la posizione relativa al tenant e all'endpoint rete CDN più vicino, il numero di asset in una pagina serviti dal rete CDN e le modifiche temporanee nella latenza di rete e nella larghezza di banda. Tuttavia, un semplice test A/B può aiutare a mostrare la differenza nel tempo di download per un file specifico.

Le schermate seguenti illustrano la differenza di velocità di download tra il percorso del file nativo in Office 365 e lo stesso file ospitato in [Microsoft Ajax rete per la distribuzione di contenuti](/aspnet/ajax/cdn/overview). Queste schermate sono disponibili nella **scheda Rete** negli strumenti di sviluppo di Internet Explorer 11. Queste schermate mostrano la latenza della popolare libreria jQuery. Per visualizzare questa schermata, in Internet Explorer, premere **F12** e selezionare la scheda **Rete** indicata con un'icona Wi-Fi.
  
![Schermata della rete F12](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Questa cattura di schermata mostra la raccolta caricata nella raccolta pagine master nel sito SharePoint Online. Il tempo necessario per caricare la raccolta è 1,51 secondi.
  
![Schermata del tempo di caricamento 1.51s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
La seconda schermata mostra lo stesso file recapitato dalla rete CDN Microsoft. Questa volta la latenza è di circa 496 millisecondi. Questo è un grande miglioramento e mostra che un intero secondo viene rasato fuori il tempo totale per scaricare l'oggetto.
  
![Schermata dei tempi di caricamento in 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>I dati sono protetti?

Microsoft si occupa di proteggere i dati che eserciteranno l'azienda. I dati archiviati nel Office 365 rete CDN vengono crittografati sia in transito che in pausa e l'accesso ai dati nel Office 365 SharePoint rete CDN è protetto da autorizzazioni utente Office 365 e autorizzazione token. Le richieste di dati nel Office 365 SharePoint rete CDN devono essere inviate (reindirizzate) dal tenant Office 365 o non verrà generato un token di autorizzazione.

Per garantire che i dati rimangano sicuri, è consigliabile non archiviare mai il contenuto dell'utente o altri dati sensibili in un rete CDN. Poiché l'accesso ai dati in un rete CDN pubblico è anonimo, le reti CDN pubbliche devono essere utilizzate solo per ospitare contenuto generico, ad esempio file script Web, icone, immagini e altri asset non sensibili.

> [!NOTE]
> I provider di rete CDN di terze parti possono avere standard di privacy e conformità diversi dagli impegni delineati dal Centro protezione Office 365 protezione. I dati memorizzati nella cache tramite il servizio rete CDN potrebbero non essere conformi alle condizioni DPT (Data Processing Terms) microsoft e potrebbero essere esterni ai limiti di conformità del Centro protezione Office 365.

Per informazioni approfondite sulla privacy e sulla protezione dei dati per i Office 365 rete CDN, visitare il sito Web seguente:  

- Per ulteriori informazioni Office 365 privacy e protezione dei dati, vedere Centro protezione [Microsoft](https://www.microsoft.com/trustcenter)
- Per ulteriori informazioni sulla privacy e sulla protezione dei dati di [Akamai,](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp) vedere Il Centro protezione della privacy di Akamai
- Per altre informazioni sulla privacy e sulla protezione dei dati di [Azure,](https://azure.microsoft.com/overview/trusted-cloud/) vedere Centro protezione di Azure

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Come è possibile proteggere la rete con tutti questi servizi di terze parti?

L'utilizzo di un ampio set di servizi partner consente Office 365 scalare e soddisfare i requisiti di disponibilità, oltre a migliorare l'esperienza utente quando si usa Office 365. I servizi di terze parti Office 365 includono entrambi gli elenchi di revoche di certificati; ad esempio crl.microsoft.com o sa.symcb.com e CDN; ad esempio r3.res.outlook.com. Ogni rete CDN FQDN generato da Office 365 è un FQDN personalizzato per Office 365. Se si viene inviati a un nome di dominio completo su richiesta di Office 365 è possibile essere certi che il provider di rete CDN controlla il nome di dominio completo e il contenuto sottostante in tale posizione.
  
Per i clienti che desiderano separare le richieste destinate a un datacenter Microsoft o Office 365 dalle richieste destinate a una terza parte, abbiamo scritto indicazioni sulla gestione degli [endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Esiste un elenco di tutti gli FQDN che sfruttano le reti CDN?

L'elenco di FQDN e il modo in cui sfruttano le reti CDN cambiano nel tempo. Fare riferimento alla pagina Office 365 url e intervalli di indirizzi [IP](./urls-and-ip-address-ranges.md) pubblicati per essere aggiornati sugli FQDN più recenti che sfruttano le reti CDN.

È inoltre possibile utilizzare il servizio Web Office 365 indirizzo IP e [URL](microsoft-365-ip-web-service.md) per richiedere gli URL Office 365 e gli intervalli di indirizzi IP correnti formattati come CSV o JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>È possibile usare il proprio rete CDN e memorizzare nella cache il contenuto nella rete locale?

Stiamo continuamente cercando nuovi modi per supportare le esigenze dei nostri clienti e stiamo attualmente esplorando l'uso di soluzioni proxy di memorizzazione nella cache e altre soluzioni rete CDN locali.

Anche se non fa parte del Office 365 rete CDN, è anche possibile utilizzare il **Rete CDN di Azure** per ospitare web part, raccolte e altre risorse personalizzate, che consente di applicare i tasti di scelta all'archiviazione di rete CDN ed esercitare un maggiore controllo sulla configurazione rete CDN. L'uso del Rete CDN di Azure non è gratuito e richiede una sottoscrizione di Azure. Per altre informazioni su come configurare un'istanza Rete CDN di Azure, vedere Guida introduttiva: Integrare un account di archiviazione di [Azure con Rete CDN di Azure](/azure/cdn/cdn-create-a-storage-account-with-cdn).

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Si usa Azure ExpressRoute per Office 365, le cose cambiano?

[Azure ExpressRoute per Office 365](azure-expressroute.md) fornisce una connessione dedicata all Office 365 intervaistica che è segregata da Internet pubblico. Ciò significa che i client dovranno comunque connettersi tramite connessioni non ExpressRoute per connettersi alle reti CDN e ad altre infrastrutture Microsoft non esplicitamente incluse nell'elenco dei servizi supportati da ExpressRoute. Per ulteriori informazioni su come instradare il traffico specifico, ad esempio le richieste destinate alle reti CDN, fare riferimento Office 365 [gestione del traffico di rete.](routing-with-expressroute.md)

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>È possibile usare reti CDN con SharePoint Server locale?

L'uso delle reti CDN ha senso solo in un contesto SharePoint Online e deve essere evitato con SharePoint Server. Infatti, tutti i vantaggi relativi alla posizione geografica non permangono se il server è locale o geograficamente vicino. Inoltre, se esiste una connessione di rete ai server in cui è ospitato, il sito può essere utilizzato senza una connessione Internet e pertanto non può recuperare i rete CDN file. In caso contrario, è consigliabile utilizzare un rete CDN se disponibile e stabile per la raccolta e i file necessari per il sito.
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>Vedere anche

[Principi della connettività di rete di Office 365](./microsoft-365-network-connectivity-principles.md)

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](./urls-and-ip-address-ranges.md)

[Usare la Office 365 di recapito del contenuto con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Centro protezione Microsoft](https://www.microsoft.com/trustcenter)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)