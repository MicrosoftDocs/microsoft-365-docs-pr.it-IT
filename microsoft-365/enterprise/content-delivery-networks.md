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
description: Utilizzare queste informazioni per scoprire in che modo Office 365 utilizza le reti di distribuzione del contenuto (reti CDN) per migliorare le prestazioni.
ms.openlocfilehash: 1c2230b76f354bf6f3de524b2b8c75b7d8c380e7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691136"
---
# <a name="content-delivery-networks-cdns"></a>Reti per la distribuzione di contenuti (CDN)

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

La Guida di reti CDN consente di mantenere Office 365 veloce e affidabile per gli utenti finali. I servizi cloud come Office 365 utilizzano reti CDN per memorizzare nella cache le risorse statiche più vicino ai browser che richiedono l'accelerazione dei download e la riduzione della latenza dell'utente finale percepita. Le informazioni contenute in questo argomento consentiranno di conoscere le reti di distribuzione del contenuto (reti CDN) e le modalità di utilizzo di Office 365.

## <a name="what-exactly-is-a-cdn"></a>Esattamente, che cos'è esattamente una rete per la distribuzione dei contenuti?

Un CDN è una rete geograficamente distribuita costituita da proxy e file server nei datacenter connessi da reti backbone ad alta velocità. Reti CDN vengono utilizzati per ridurre la latenza e i tempi di caricamento di un determinato insieme di file e oggetti in un sito Web o in un servizio. Una rete CDN può disporre di molte migliaia di endpoint per la manutenzione ottimale delle richieste in arrivo da qualsiasi posizione.

Reti CDN vengono in genere utilizzati per fornire download più rapidi di contenuto generico per un sito Web o un servizio, ad esempio file JavaScript, icone e immagini, nonché l'accesso privato ai contenuti degli utenti, ad esempio i file nelle raccolte documenti di SharePoint Online, i file multimediali di flusso e il codice personalizzato.

Reti CDN vengono utilizzati dalla maggior parte dei servizi cloud aziendali. I servizi cloud come Office 365 dispongono di milioni di clienti che scaricano una combinazione di contenuto proprietario (ad esempio messaggi di posta elettronica) e di contenuto generico (ad esempio le icone) contemporaneamente. È più efficiente inserire immagini, come icone, come il più vicino possibile al computer dell'utente. Non è pratico per ogni servizio cloud creare i datacenter della rete CDN che archiviano questo contenuto generico in ogni area metropolitana o anche in tutti i principali hub Internet di tutto il mondo, quindi alcuni di questi reti CDN sono condivisi.

## <a name="how-do-cdns-make-services-work-faster"></a>In che modo le reti per la distribuzione dei contenuti velocizzano l'esecuzione dei servizi?

Il download di oggetti comuni come le immagini e le icone del sito può richiedere più volte la larghezza di banda della rete che può essere utilizzata per il download di contenuti personali importanti, come la posta elettronica o i documenti. Poiché Office 365 utilizza un'architettura che include reti CDN, le icone, gli script e altri contenuti generici possono essere scaricati da server più vicini ai computer client, rendendo più veloce il download. Questo significa un accesso più rapido ai contenuti personali, che sono archiviati in modo sicuro nei data center di Office 365.

Reti CDN contribuisce a migliorare le prestazioni del servizio cloud in diversi modi:

- Reti CDN consente di spostare parte della rete e scaricare il carico dei file dal servizio cloud, liberando le risorse del servizio cloud per la gestione del contenuto dell'utente e di altri servizi, riducendo la necessità di soddisfare le richieste di risorse statiche.
- Reti CDN sono creati appositamente per garantire l'accesso ai file a bassa latenza, implementando reti e file server con elevate prestazioni e sfruttando i protocolli di rete aggiornati, ad esempio [http/2](https://en.wikipedia.org/wiki/HTTP/2) , con una compressione estremamente efficiente e il multiplexing delle richieste.
- Le reti della rete CDN utilizzano numerosi endpoint distribuiti a livello globale per rendere il contenuto disponibile il più vicino possibile agli utenti.

## <a name="the-office-365-cdn"></a>La rete CDN di Office 365

La rete di distribuzione dei contenuti (CDN) di Office 365 consente agli amministratori di Office 365 di fornire prestazioni migliori per le pagine di SharePoint Online dell'organizzazione memorizzando nella cache le risorse statiche più vicino ai browser che li richiedono, contribuendo ad accelerare i download e a ridurre la latenza. La rete CDN di Office 365 utilizza il [protocollo http/2](https://en.wikipedia.org/wiki/HTTP/2) per migliorare la compressione e la velocità di download.

> [!NOTE]
> La rete CDN di Office 365 è disponibile solo per i tenant nel cloud di **produzione** (tutto il mondo). Gli inquilini del governo degli Stati Uniti, le nuvole cinesi e tedesche attualmente non supportano la rete CDN di Office 365.

La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità. In base al tipo di contenuto che si vuole ospitare nella rete per la distribuzione di contenuti di Office 365, è possibile aggiungere origini **pubbliche**, origini **private** o entrambi.

![Diagramma concettuale della rete CDN di Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagramma concettuale della rete CDN di Office 365")

Il contenuto nelle origini **pubbliche** della rete per la distribuzione di contenuti di Office 365 è accessibile in forma anonima, di conseguenza chiunque disponga degli URL delle risorse ospitate può accedervi. Dal momento che l'accesso al contenuto in origini pubbliche è anonimo, è consigliabile usarle solo per memorizzare nella cache contenuti generici non riservati, ad esempio file JavaScript, script, icone e immagini. Per impostazione predefinita, la rete per la distribuzione di contenuti di Office 365 viene usata per il download di risorse generiche, ad esempio le applicazioni client di Office 365 da un'origine pubblica.

Le origini **private** all'interno della rete CDN di Office 365 offrono accesso privato ai contenuti degli utenti, ad esempio raccolte documenti di SharePoint Online, siti e immagini proprietarie. L'accesso ai contenuti nelle origini private è protetto con token generati dinamicamente in modo da consentire l'accesso solo agli utenti che dispongono delle autorizzazioni per la raccolta documenti o per la posizione di archiviazione originali. Le origini private della rete per la distribuzione di contenuti di Office 365 possono essere usate solo per contenuti di SharePoint Online. L'accesso alle risorse può avvenire solo tramite il reindirizzamento dal tenant di SharePoint Online.

Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.

Per ulteriori informazioni su come utilizzare la rete CDN di Office 365, vedere [use the office 365 Content Delivery Network with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

Per guardare una serie di brevi video che forniscono informazioni concettuali e HOWTO sull'utilizzo della rete CDN di Office 365, visitare il [canale YouTube per i modelli e le procedure](https://aka.ms/sppnp-videos)per gli sviluppatori di SharePoint.

## <a name="other-microsoft-cdns"></a>Altri Microsoft reti CDN

Anche se non fa parte della rete CDN di Office 365, è possibile utilizzare queste reti CDN nel tenant di Office 365 per accedere alle raccolte di sviluppo di SharePoint, al codice personalizzato e ad altri scopi che non rientrano nell'ambito della rete CDN di Office 365.

### <a name="azure-cdn"></a>Rete CDN di Azure

>[!NOTE]
>A partire dal Q3 2020, SharePoint Online inizierà la memorizzazione nella cache dei video sulla rete CDN di Azure per supportare la riproduzione e l'affidabilità migliorate del video. I video più diffusi verranno trasmessi dall'endpoint della rete CDN più vicino all'utente. Questi dati rimarranno all'interno del limite di conformità di Microsoft 365. Si tratta di un servizio gratuito per tutti i tenant e non richiede alcuna azione del cliente da configurare.

È possibile utilizzare la rete **CDN di Azure** per distribuire un'istanza CDN personalizzata per l'hosting di Web part personalizzate, raccolte e altre risorse risorsa, che consente di applicare i tasti di accesso allo spazio di archiviazione CDN e di esercitare un maggiore controllo sulla configurazione CDN. L'utilizzo della rete CDN di Azure non è gratuito e richiede una sottoscrizione di Azure.

Per ulteriori informazioni su come configurare un'istanza di Azure CDN, vedere [Guida introduttiva: integrare un account di archiviazione di Azure con la rete CDN di Azure](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

Per un esempio di come è possibile utilizzare la rete CDN di Azure per ospitare Web part di SharePoint, vedere [distribuire la Web part sul lato client di SharePoint alla rete CDN di Azure](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Per informazioni sul modulo di PowerShell CDN di Azure, vedere Gestione della rete [CDN di Azure con PowerShell](https://docs.microsoft.com/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

La rete **CDN** di Microsoft AJAX è una rete CDN di sola lettura che offre molte librerie di sviluppo popolari, tra cui jQuery (e tutte le sue altre raccolte), ASP.NET AJAX, Bootstrap, Knockout.js e altri.
  
Per includere gli script nel progetto, è sufficiente sostituire i riferimenti a queste raccolte disponibili pubblicamente con riferimenti all'indirizzo della rete CDN anziché includerlo nel progetto stesso. Per creare un collegamento a jQuery, ad esempio, utilizzare il codice seguente:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Per ulteriori informazioni su come utilizzare la rete CDN di Microsoft AJAX, vedere [CDN di Microsoft AJAX](https://docs.microsoft.com/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>In che modo Office 365 utilizza il contenuto di una rete CDN?

Indipendentemente dalla rete CDN configurata per il tenant di Office 365, il processo di recupero dei dati di base è lo stesso.

1. Il client (un browser o un'applicazione client di Office) richiede i dati da Office 365.

2. Office 365 restituisce i dati direttamente al client o, se i dati fanno parte di un insieme di contenuto ospitato dalla rete CDN, reindirizza il client all'URL della rete CDN.

    a. Se i dati sono già memorizzati nella cache in origine _pubblica_ , il client Scarica i dati direttamente dal percorso della rete CDN più vicino al client.

    b. Se i dati sono già memorizzati nella cache in base all'origine _privata_ , il servizio CDN verifica le autorizzazioni dell'account utente di Office 365 sull'origine. Se si dispone delle autorizzazioni, SharePoint Online genera dinamicamente un URL personalizzato composto dal percorso del cespite della rete CDN e da due token di accesso e restituisce l'URL personalizzato al client. Il client Scarica quindi i dati direttamente dal percorso della rete CDN più vicino al client utilizzando l'URL personalizzato.

3. Se i dati non vengono memorizzati nella cache della rete CDN, il nodo CDN richiede i dati da Office 365 e quindi memorizza nella cache i dati per un determinato periodo di tempo dopo che il client ha eseguito il download dei dati.

La rete CDN calcola il data center più vicino al browser dell'utente e, tramite il reindirizzamento, Scarica i dati richiesti da tale centro. Il reindirizzamento della rete CDN è rapido e può salvare gli utenti in tempi di download molto numerosi.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Come è possibile configurare la rete in modo che reti CDN funzioni meglio con Office 365?

Ridurre al minimo la latenza tra i client della rete e gli endpoint CDN è la considerazione fondamentale per garantire prestazioni ottimali. È possibile utilizzare le procedure consigliate delineate nella [gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per garantire che la configurazione di rete consenta ai browser client di accedere direttamente all'CDN anziché instradare il traffico CDN tramite proxy centrali per evitare di introdurre latenze inutili.

È inoltre possibile leggere i [principi di connettività di rete di office 365](https://aka.ms/o365networkingprinciples) per comprendere i concetti relativi all'ottimizzazione delle prestazioni di rete di Office 365.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>È presente un elenco di tutti i reti CDN utilizzati da Office 365?

Le reti CDN in uso da Office 365 sono sempre soggette a modifiche e in molti casi vi sono più partner della rete CDN configurati nell'evento uno non è disponibile. Le reti CDN primarie utilizzate da Office 365 sono le seguenti:

|Rete CDN  |Company  |Usage  |Collegamento  |
|---------|---------|---------|---------|
|Rete CDN di Office 365     |Akamai         |Risorse generiche nelle origini pubbliche, contenuto dell'utente di SharePoint in origini private         |[Utilizzare la rete di distribuzione dei contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Rete CDN di Azure     |Microsoft         |Codice personalizzato, soluzioni di SharePoint Framework         |[Rete CDN di Microsoft Azure](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (sola lettura)     |Microsoft         |Librerie comuni per AJAX, jQuery, ASP.NET, bootstrap, Knockout.js ecc.         |[Microsoft Ajax CDN](https://docs.microsoft.com/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Quali guadagni di prestazioni fornisce una rete CDN?

Esistono numerosi fattori che implicano la misurazione di specifiche differenze nelle prestazioni tra i dati scaricati direttamente da Office 365 e i dati scaricati da una rete CDN specifica, ad esempio la posizione rispetto al tenant e all'endpoint CDN più vicino, il numero di attività in una pagina che sono servite dalla CDN e le modifiche transitorie della latenza e della larghezza di banda. Tuttavia, un semplice test A/B può essere utile per mostrare la differenza di tempo di download per un file specifico.

Nelle schermate seguenti viene illustrata la differenza di velocità di download tra il percorso del file nativo in Office 365 e lo stesso file ospitato nella [rete di distribuzione del contenuto Microsoft AJAX](https://docs.microsoft.com/aspnet/ajax/cdn/overview). Queste schermate sono presenti nella scheda **rete** degli strumenti di sviluppo di Internet Explorer 11. Queste schermate mostrano la latenza sulla popolare libreria jQuery. Per visualizzare questa schermata, in Internet Explorer, premere **F12** e selezionare la scheda **Rete** indicata con un'icona Wi-Fi.
  
![Schermata della rete F12](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Questo screenshot Visualizza la raccolta caricata nella raccolta pagine master nel sito di SharePoint Online. Il tempo necessario per caricare la raccolta è 1,51 secondi.
  
![Schermata del tempo di caricamento 1.51s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
La seconda schermata Visualizza lo stesso file recapitato dalla rete CDN di Microsoft. Questa volta la latenza è di circa 496 millisecondi. Si tratta di un miglioramento elevato e viene mostrato che il tempo totale per scaricare l'oggetto è stato raso al secondo.
  
![Schermata dei tempi di caricamento in 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>I dati sono protetti?

È importante proteggere i dati che eseguono la propria azienda. I dati archiviati nella rete CDN di Office 365 sono crittografati sia in transito che a riposo e l'accesso ai dati nella rete CDN di Office 365 SharePoint è protetto dalle autorizzazioni utente e dall'autorizzazione di token di Office 365. Le richieste per i dati nella rete CDN di SharePoint di Office 365 devono essere reindirizzate (Reindirizzamento) dal tenant di Office 365 o un token di autorizzazione non verrà generato.

Per garantire la protezione dei dati, si consiglia di non archiviare mai il contenuto dell'utente o altri dati sensibili in una rete CDN pubblica. Poiché l'accesso ai dati in una rete CDN pubblica è anonimo, reti CDN pubblico deve essere utilizzato solo per ospitare contenuto generico, ad esempio file di script Web, icone, immagini e altre risorse non sensibili.

> [!NOTE]
> i provider della rete CDN di terze parti possono avere norme sulla privacy e conformità che differiscono dagli impegni delineati dal centro protezione di Office 365. I dati memorizzati nella cache tramite il servizio CDN potrebbero non essere conformi ai termini di elaborazione dati di Microsoft e potrebbero essere esterni ai limiti di conformità di Office 365 Trust Center.

Per informazioni approfondite sulla privacy e la protezione dei dati per i provider di servizi di rete CDN di Office 365, visitare i seguenti elementi:  

- Ulteriori informazioni sulla protezione dei dati e sulla privacy di Office 365 in [Microsoft Trust Center](https://www.microsoft.com/trustcenter)
- Per ulteriori informazioni sulla privacy e la protezione dei dati di Akamai, vedere [Akamai privacy Trust Center](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Per ulteriori informazioni sulla privacy e la protezione dei dati di Azure, vedere il Centro sicurezza di [Azure](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Come è possibile proteggere la rete con tutti i servizi di terze parti?

L'utilizzo di una vasta gamma di servizi partner consente a Office 365 di scalare e soddisfare i requisiti di disponibilità, nonché di migliorare l'esperienza utente quando si utilizza Office 365. I servizi di terze parti Office 365 leverages includono entrambi gli elenchi di revoche di certificati. ad esempio crl.microsoft.com o sa.symcb.com e reti CDN; ad esempio r3.res.outlook.com. Ogni nome di dominio completo della rete CDN generato da Office 365 è un FQDN personalizzato per Office 365. Se si è inviati a un FQDN su richiesta di Office 365, è possibile garantire che il provider CDN controlli il nome di dominio completo e il contenuto sottostante in tale percorso.
  
Per i clienti che desiderano separare le richieste destinate a un datacenter Microsoft o Office 365 dalle richieste destinate a terze parti, sono state scritte linee guida per la [gestione degli endpoint di office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>È presente un elenco di tutti i nomi FQDN che sfruttano reti CDN?

L'elenco di FQDN e la modalità di utilizzo di reti CDN cambiano nel tempo. Consultare la pagina degli [URL e degli intervalli di indirizzi IP pubblicati su Office 365](https://go.microsoft.com/fwlink/p/?LinkID=293744) per essere aggiornati sugli ultimi FQDN che sfruttano reti CDN.

È inoltre possibile utilizzare l' [indirizzo IP e il servizio Web URL di office 365](microsoft-365-ip-web-service.md) per richiedere gli URL di Office 365 e gli intervalli di indirizzi IP correnti formattati come CSV o JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>È possibile utilizzare la rete CDN personale e il contenuto della cache nella propria network locale?

Siamo sempre alla ricerca di nuovi modi per supportare le esigenze dei clienti e stiamo esplorando l'utilizzo delle soluzioni proxy di memorizzazione nella cache e di altre soluzioni CDN locali.

Anche se non fa parte della rete CDN di Office 365, è anche possibile utilizzare la **CDN di Azure** per ospitare Web part personalizzate, raccolte e altre risorse risorsa, che consentono di applicare i tasti di accesso allo spazio di archiviazione CDN e di esercitare un maggiore controllo sulla configurazione CDN. L'utilizzo della rete CDN di Azure non è gratuito e richiede una sottoscrizione di Azure. Per ulteriori informazioni su come configurare un'istanza di Azure CDN, vedere [Guida introduttiva: integrare un account di archiviazione di Azure con la rete CDN di Azure](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Sto usando Azure ExpressRoute per Office 365, che cambia le cose?

[Azure ExpressRoute per office 365](azure-expressroute.md) fornisce una connessione dedicata all'infrastruttura di Office 365 che è stata segregata dalla rete Internet pubblica. Questo significa che i client dovranno comunque connettersi tramite connessioni non ExpressRoute per connettersi a reti CDN e ad altre infrastrutture Microsoft che non sono esplicitamente incluse nell'elenco dei servizi supportati da ExpressRoute. Per ulteriori informazioni su come instradare il traffico specifico, ad esempio le richieste destinate a reti CDN, fare riferimento alla [gestione del traffico di rete di Office 365](routing-with-expressroute.md).

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>È possibile utilizzare reti CDN con SharePoint Server locale?

L'utilizzo di reti CDN ha senso solo in un contesto di SharePoint Online e deve essere evitato con SharePoint Server. Infatti, tutti i vantaggi relativi alla posizione geografica non permangono se il server è locale o geograficamente vicino. Inoltre, se esiste una connessione di rete ai server in cui è ospitata, il sito può essere utilizzato senza una connessione Internet e pertanto non è in grado di recuperare i file CDN. In caso contrario, è consigliabile utilizzare una rete CDN se disponibile e stabile per la raccolta e i file necessari per il sito.
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/o365cdns](https://aka.ms/o365cdns)
  
## <a name="see-also"></a>Vedere anche

[Principi della connettività di rete di Office 365](https://aka.ms/o365networkingprinciples)

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](https://go.microsoft.com/fwlink/p/?LinkID=293744)

[Utilizzare la rete di distribuzione dei contenuti di Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Centro protezione Microsoft](https://www.microsoft.com/trustcenter)

[Ottimizzare le prestazioni di Office 365](tune-microsoft-365-performance.md)
