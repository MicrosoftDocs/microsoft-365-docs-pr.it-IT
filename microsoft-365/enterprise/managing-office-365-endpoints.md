---
title: Gestione degli endpoint di Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 99cab9d4-ef59-4207-9f2b-3728eb46bf9a
description: Informazioni su come gestire gli endpoint di Office 365 in modo che funzionino con l'architettura di rete dell'organizzazione aziendale.
ms.openlocfilehash: dcacb10492f4377dbcdf6e74c848a404f1b64c6f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780485"
---
# <a name="managing-office-365-endpoints"></a>Gestione degli endpoint di Office 365

La maggior parte delle organizzazioni che hanno sedi di lavoro multiple e una connessione WAN devono configurare la connettività di rete per Office 365. È possibile ottimizzare la rete inviando tutte le richieste di rete attendibili di Office 365 direttamente tramite il firewall, escludendo ulteriori attività di ispezione o elaborazione a livello di pacchetti. In questo modo si riducono la latenza e i requisiti di capacità perimetrale. L’identificazione del traffico di rete di Office 365 è il primo passo per garantire le prestazioni ottimali per gli utenti. Per ulteriori informazioni, vedere [principi di connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md).

Microsoft consiglia di accedere agli endpoint di rete di Office 365 e alle relative modifiche utilizzando l' [indirizzo IP e il servizio Web URL di office 365](microsoft-365-ip-web-service.md).

Indipendentemente dal modo in cui il traffico di rete essenziale di Office 365 viene gestito, Office 365 richiede la connettività internet. Gli altri endpoint di rete per cui la connettività è necessaria sono elencati in [Endpoint aggiuntivi non inclusi nel Servizio web per indirizzi IP e URL di Office 365](additional-office365-ip-addresses-and-urls.md).

Il modo in cui gli endpoint di rete di Office 365 vengono usati dipende dall'architettura di rete della propria organizzazione. Questo articolo illustra diversi modi in cui le architetture di rete aziendali possono essere integrate con gli URL e gli indirizzi IP di Office 365. Il modo più semplice per scegliere quali richieste di rete è attendibile consiste nell'utilizzare dispositivi SD-WAN che supportano la configurazione automatizzata di Office 365 in ognuna delle posizioni di Office.

## <a name="sd-wan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>SD-WAN per l'uscita di branch locali del traffico di rete vitale di Office 365

In ogni percorso di succursale, è possibile fornire un dispositivo SD-WAN configurato per instradare il traffico per la categoria di endpoint di Office 365 Optimize, oppure ottimizzare e consentire categorie direttamente alla rete di Microsoft. Altri traffici di rete, tra cui il traffico del data center locale, il traffico generico dei siti internet, e il traffico verso gli endpoint di categoria Predefinito di Office 365, vengono inviati ad altre destinazioni in cui il perimetro di rete è più solido.

Microsoft sta lavorando con i provider SD-WAN per abilitare la configurazione automatizzata. Per altre informazioni, vedere [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>Usare un file PAC per l'instradamento diretto del traffico essenziale di Office 365

I file PAC o WPAD possono essere usati per gestire le richieste di rete associate a Office 365 che non hanno un indirizzo IP. In genere, le richieste di rete che vengono inviate tramite un dispositivo proxy o perimetrale comportano un aumento della latenza. Benché l'ispezione SSL determini la latenza maggiore, altri servizi, come l'autenticazione proxy e la ricerca della reputazione, possono peggiorare le prestazioni e l'esperienza dell'utente. Questi dispositivi di rete perimetrale necessitano anche di una capacità sufficiente per elaborare tutte le richieste di connessione di rete. È consigliabile ignorare i dispositivi proxy o di ispezione per le richieste di rete dirette di Office 365.
  
[PowerShell Gallery Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) è uno script di PowerShell che legge gli ultimi endpoint di rete dall'indirizzo IP e dall'URL di Office 365 e crea un file PAC da usare come modello. Lo script può essere modificato in modo da integrarlo con la gestione dei file PAC esistente.

![Connessione a Office 365 tramite firewall e proxy.](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**Figura 1 - Perimetro di rete aziendale semplice**

Il file PAC viene distribuito nel browser al punto 1 della figura 1. Se si usa un file PAC per il traffico in uscita essenziale di Office 365, è anche necessario consentire la connettività agli indirizzi IP che si trovano dietro questi URL nel firewall del perimetro di rete. Per farlo, bisogna recuperare gli indirizzi IP delle stesse categorie di endpoint di Office 365 specificate nel file PAC, e creare elenchi ACL per il firewall sulla base di tali indirizzi. Il firewall è il punto 3 della figura 1.

Separatamente, se si sceglie di eseguire solo l'instradamento diretto per gli endpoint di categoria Ottimizza, gli endpoint di categoria Consenti necessari che sono inviati al server proxy dovranno essere elencati nel server proxy per ignorare ulteriori elaborazioni. Ad esempio, l'ispezione SSL e l'autenticazione del proxy sono incompatibili con gli endpoint di categoria Ottimizza e Consenti. Il server proxy è il punto 2 della figura 1.

La configurazione più comune prevede di autorizzare senza elaborazione tutto il traffico in uscita dal server proxy verso gli indirizzi IP di destinazione, per il traffico di rete di Office 365 che raggiunge il server proxy. Per altre informazioni sui problemi relativi all'ispezione SSL, vedere [Usare dispositivi o soluzioni di rete di terza parte per il traffico di Office 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

Lo script Get-PacFile genera due tipi di file PAC.

| Tipo | Descrizione |
|:-----|:-----|
|**1** <br/> |Invia il traffico diretto degli endpoint di categoria Ottimizza e tutto il resto al server proxy. <br/> |
|**2** <br/> |Invia il traffico diretto degli endpoint di categoria Ottimizza e Consenti e tutto il resto al server proxy. Questo tipo può essere usato anche per inviare tutto il traffico di ExpressRoute per Office 365 sui segmenti di rete di ExpressRoute, inviando tutto il resto al server proxy. <br/> |

Ecco un semplice esempio dell'esecuzione dello script PowerShell:

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

Sono disponibili numerosi parametri che è possibile passare allo script:

| Parametro | Descrizione |
|:-----|:-----|
|**ClientRequestId** <br/> |Questo è necessario ed è un GUID passato al servizio web che rappresenta il computer client che invia la richiesta. <br/> |
|**Instance** <br/> |L'istanza di servizio di Office 365, che per impostazione predefinita è in tutto il mondo. Questo viene passato anche al servizio Web. <br/> |
|**TenantName** <br/> |Il nome del proprio tenant di Office 365. Viene passato al servizio web ed è usato come parametro sostituibile per alcuni URL di Office 365. <br/> |
|**Type** <br/> |Il tipo di file PAC proxy che si desidera generare. <br/> |

Ecco un altro esempio dell'esecuzione dello script di PowerShell con altri parametri:

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>Il server proxy ignora l'elaborazione del traffico di rete di Office 365

Quando i file PAC non sono usati per il traffico diretto in uscita, si può comunque ignorare l'elaborazione nel proprio perimetro di rete configurando il proprio server proxy. Alcuni fornitori di server proxy hanno abilitato la configurazione automatizzata di questa procedura, come descritto in [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).

Se si esegue questa operazione manualmente, sarà necessario ottenere i dati di categoria ottimizzazione e Consenti endpoint dal servizio Web indirizzo IP e URL di Office 365 e configurare il server proxy per ignorare l'elaborazione. È importante evitare l'ispezione SSL e l'autenticazione del proxy per gli endpoint di categoria Ottimizza e Consenti.
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Gestione delle modifiche per indirizzi IP e URL di Office 365

Oltre alla selezione della configurazione appropriata per il proprio perimetro di rete, è essenziale adottare un processo di gestione delle modifiche per gli endpoint di Office 365. Gli endpoint cambiano regolarmente: se le modifiche non vengono gestite, è possibile che gli utenti vengano bloccati o le prestazioni siano scarse dopo l'aggiunta di un nuovo indirizzo IP o URL.

Le modifiche apportate agli URL e agli indirizzi IP di Office 365 vengono in genere pubblicate intorno all'ultimo giorno di ogni mese. A volte le modifiche non sono pubblicate in questo periodo, a causa di obblighi operativi, di supporto o di sicurezza.

Quando viene pubblicata una modifica che richiede di agire perché è stato aggiunto un indirizzo IP o un URL, bisogna prevedere un preavviso di 30 giorni tra la data di pubblicazione della modifica e la disponibilità di un servizio di Office 365 in tale endpoint. Benché tentiamo di rispettare tale periodo di preavviso, a volte potrebbe non essere possibile a causa di obblighi operativi, di supporto o di sicurezza. Per le modifiche che non richiedono l'intervento immediato per mantenere la connettività, come la rimozione di indirizzi IP o URL o modifiche meno rilevanti, non è prevista la notifica anticipata. Indipendentemente dalla notifica inviata, noi indichiamo la data prevista per l'attivazione del servizio per ogni modifica. 

### <a name="change-notification-using-the-web-service"></a>Modifica la notifica usando il servizio web

Si può usare il Servizio web per indirizzi IP e URL di Office 365 per ricevere la notifica delle modifiche. Raccomandiamo di eseguire il metodo web **/version** una volta all'ora per verificare la versione degli endpoint che sono usati per connettersi a Office 365.  Se la versione cambia rispetto alla versione in uso, bisogna ottenere i dati più recenti sugli endpoint dal metodo web **/endpoints** e ottenere facoltativamente le differenze dal metodo web **/changes**. Non è necessario eseguire i metodi web **/endpoints** o **/changes** se non sono state rilevate modifiche della versione.

Per altre informazioni, vedere [Servizio web per indirizzi IP e URL di Office 365](microsoft-365-ip-web-service.md).

### <a name="change-notification-using-rss-feeds"></a>Notifica delle modifiche tramite feed RSS

Il Servizio web per indirizzi IP e URL di Office 365 fornisce un feed RSS a cui è possibile registrarsi in Outlook. I collegamenti agli URL del feed RSS si trovano in ogni pagina specifica delle istanze del servizio Office 365 per gli indirizzi IP e gli URL. Per altre informazioni, vedere [Servizio web per indirizzi IP e URL di Office 365](microsoft-365-ip-web-service.md).

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>Modificare la notifica e la revisione dell'approvazione con Microsoft Flow

Comprendiamo che l'elaborazione manuale delle modifiche mensili degli endpoint di rete potrebbe comunque essere necessaria. Si può usare Microsoft Flow per creare un flusso che notifica l'utente tramite posta elettronica ed esegue inoltre un processo di approvazione per le modifiche quando gli endpoint di rete di Office 365 vengono modificati. Al termine della revisione, il flusso può inviare tramite posta elettronica le modifiche al proprio team di gestione di firewall e server proxy.

Per informazioni su campioni e modelli di Microsoft Flow, vedere [Usare Microsoft Flow per ricevere un messaggio di posta elettronica per le modifiche apportate agli indirizzi IP e agli URL di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651).
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Domande frequenti sugli endpoint di rete di Office 365

Vedere le domande frequenti su connettività di rete di Office 365.
  
### <a name="how-do-i-submit-a-question"></a>Come si invia una domanda?

Fare clic sul collegamento in fondo per indicare se l'articolo è stato utile e per inviare eventuali altre domande. I feedback vengono monitorati e le domande vengono aggiornate in base a quelle poste con più frequenza.
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>Come si determina la posizione del tenant?

 Il miglior modo di determinare la **posizione del tenant** è usare la nostra [mappa dei data center](https://aka.ms/datamaps).
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>Il peering con Microsoft è eseguito in modo adeguato?

 Le **posizioni di peering** sono descritte in modo più dettagliato nella pagina dedicata al [peering con Microsoft](https://www.microsoft.com/peering).
  
Con oltre 2500 relazioni di peering ISP a livello globale e 70 punti di presenza, il passaggio dalla rete dell'utente alla nostra dovrebbe essere immediato. Può essere utile dedicare qualche minuto ad assicurarsi che la relazione di peering dell'ISP sia ottimale. [Ecco alcuni esempi](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__guidance/) di passaggi di peering di buono e scarso livello verso la rete dell'utente.
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>Sono presenti richieste di rete per indirizzi IP non inclusi nell'elenco pubblicato, occorre consentire loro l'accesso?

Noi forniamo solo gli indirizzi IP per i server di Office 365 a cui instradare direttamente. Non si tratta di un elenco completo degli indirizzi IP per cui si vedranno richieste di rete. Si vedranno richieste di rete per indirizzi IP non pubblicati di proprietà di Microsoft e di terze parti. Questi indirizzi IP vengono generati dinamicamente o gestiti in modo da impedire avvisi tempestivi in caso di modifica. Se il firewall non consente l'accesso in base ai nomi di dominio completi per le richieste di rete, usare un file PAC o WPAD per gestire le richieste.
  
È presente un indirizzo IP associato a Office 365 sul quale si vogliono ottenere altre informazioni?
  
1. Verificare se l'indirizzo IP è incluso in un intervallo pubblicato più ampio usando un calcolatore CIDR, come questi per [IPv4](https://www.ipaddressguide.com/cidr) o [IPv6](https://www.ipaddressguide.com/ipv6-cidr). Ad esempio, 40.96.0.0/13 include l'indirizzo IP 40.103.0.1 nonostante 40.96 non corrisponda a 40.103.
2. Scoprire se l'indirizzo IP appartiene a un partner eseguendo una [query whois](https://dnsquery.org/). Se appartiene a Microsoft, potrebbe trattarsi di un partner interno. Molti endpoint di rete dei partner sono indicati come appartenenti alla categoria _Predefinita_, per cui gli indirizzi IP non vengono pubblicati.
3. L'indirizzo IP potrebbe non essere incluso in Office 365 o in un elemento dipendente. La pubblicazione degli endpoint di rete di Office 365 non include tutti gli endpoint di rete Microsoft.
4. Controllare il certificato. Con un browser, connettersi all'indirizzo IP utilizzando *https:// \<IP_ADDRESS\>* e controllare i domini elencati nel certificato per comprendere quali domini sono associati all'indirizzo IP. Se si tratta di un indirizzo IP di proprietà di Microsoft e non dell'elenco degli indirizzi IP di Office 365, è probabile che l'indirizzo IP sia associato a una rete CDN Microsoft, ad esempio  *MSOCDN.NET*  o un altro dominio Microsoft senza informazioni IP pubblicate. Se il dominio specificato nel certificato è uno di quelli di cui dovrebbe essere elencato l'indirizzo IP, informare Microsoft.

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>Alcuni URL di Office 365 puntano ai record CNAME invece che ai record A del DNS. Cosa bisogna fare con i record CNAME?

I computer client hanno bisogno di un cappello DNS A o AAAA record t) include uno o più indirizzi IP per la connessione a un servizio cloud. Alcuni URL inclusi in Office 365 mostrano i record CNAME invece dei record A o AAAA. Questi record CNAME sono intermediari e potrebbero essere incatenati. Vengono sempre risolti in record A o AAA per gli indirizzi IP. Ad esempio, considerare la serie seguente di record DNS, che viene risolta nell'indirizzo IP _IP_1_:

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

Questi reindirizzamenti CNAME sono un aspetto normale del DNS, e sono trasparenti per il computer client e per i server proxy. Sono usati per bilanciare il carico, le reti di distribuzione dei contenuti, la disponibilità elevata e la correzione degli incidenti dei servizi. Microsoft non pubblica i record CNAME intermediari, che possono essere modificati in qualsiasi momento e non devono essere configurati se consentito dal proprio server proxy.

Un server proxy convalida l'URL iniziale, che nell'esempio precedente è serviceA.office.com, e questo URL verrebbe incluso nella pubblicazione di Office 365. Il server proxy richiede la risoluzione DNS dell'URL a un indirizzo IP, e riceve IP_1 come risposta. Non convalida i record del reindirizzamento CNAME intermediario.

Non è consigliabile eseguire configurazioni hardcoded o consentire il traffico basato sui nomi FQDN indiretti di Office 365, non supportato da Microsoft ed è noto che causa problemi di connettività dei clienti. Le soluzioni DNS che bloccano il reindirizzamento CNAME, o che altrimenti risolvono scorrettamente le voci del DNS di Office 365, possono essere risolte tramite l'inoltro condizionale (configurato sugli FQDN di Office 365 usati direttamente) ed abilitando la ricorsione DNS. Molti prodotti perimetrali di rete di terze parti integrano in modo nativo i servizi consigliati di Office 365 endpoint Traffic bypass nella configurazione tramite l' [indirizzo IP e il servizio Web URL di office 365](microsoft-365-ip-web-service.md).

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>Perché tra i nomi di dominio Microsoft sono presenti nomi come nsatc.net o akadns.net?

Office 365 e altri servizi Microsoft usano diversi servizi di terze parti come Akamai e MarkMonitor per migliorare l'esperienza di Office 365. Per assicurare sempre la migliore esperienza utente possibile, Microsoft potrebbe cambiare questi servizi in futuro. I domini di terze parti possono ospitare contenuto, ad esempio una rete CDN, oppure possono ospitare un servizio, ad esempio un servizio di gestione del traffico geografico. Alcuni dei servizi attualmente in uso includono:
  
[MarkMonitor](https://www.markmonitor.com/) è in uso quando vengono visualizzate le richieste che includono *\* . nsatc.NET*. Questo servizio fornisce protezione dei nomi di dominio e monitoraggio per proteggere da comportamenti dannosi.
  
[ExactTarget](https://www.marketingcloud.com/) è in uso quando si visualizzano le richieste a *\* . ExactTarget.com*. Questo servizio fornisce gestione dei collegamenti di posta elettronica e monitoraggio per proteggere da comportamenti dannosi.
  
[Akamai](https://www.akamai.com/) è in uso quando sono presenti richieste che includono uno degli FQDN seguenti. Questo servizio offre servizi di rete di CDN e instradamento geografico del DNS.
  
```console
*.akadns.net
*.akam.net
*.akamai.com
*.akamai.net
*.akamaiedge.net
*.akamaihd.net
*.akamaized.net
*.edgekey.net
*.edgesuite.net
```

<a name="bkmk_thirdparty"> </a>
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>È necessario avere la connettività minima possibile per Office 365

Dato che Office 365 è una famiglia di servizi progettati per essere eseguiti su internet, il loro livello di affidabilità e disponibilità si basa su numerosi servizi internet standard disponibili. Ad esempio, i servizi Internet standard come DNS, CRL e CDN devono essere raggiungibili per poter usare Office 365, allo stesso modo in cui devono esserlo per usare i servizi internet più moderni.

La famiglia di servizi di Office 365 viene suddivisa in aree di servizio principali. Questi possono essere abilitati in modo selettivo per la connettività ed è presente un'area comune, che è una dipendenza per tutti ed è sempre necessaria.

| Area di servizio | Descrizione |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online ed Exchange Online Protection <br/> |
|**SharePoint** <br/> |SharePoint Online e OneDrive for Business <br/> |
|**Skype for Business Online e Microsoft Teams** <br/> |Skype for Business e Microsoft Teams <br/> |
|**Comune** <br/> |Office 365 Pro Plus, Office su browser, Azure AD, e altri endpoint di rete comuni <br/> |

Oltre ai servizi internet di base, esistono servizi di terza parte usati solo per integrare determinate funzionalità. Anche se questi sono necessari per l'integrazione, sono contrassegnati come facoltativi nell'articolo degli endpoint di Office 365, il che significa che le funzionalità di base del servizio continueranno a funzionare se l'endpoint non è accessibile. Qualsiasi endpoint di rete necessario avrà l'attributo obbligatorio impostato su true. Qualsiasi endpoint di rete facoltativo avrà l'attributo obbligatorio impostato su false e l'attributo Notes fornirà informazioni dettagliate sulla funzionalità mancante che è necessario prevedere se la connettività è bloccata.
  
Se si sta tentando di utilizzare Office 365 e i servizi di terze parti non sono accessibili, è necessario [assicurarsi che tutti i nomi FQDN contrassegnati come necessari o facoltativi in questo articolo siano consentiti tramite il proxy e il firewall](urls-and-ip-address-ranges.md).
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>Come si blocca l'accesso ai servizi consumer Microsoft?

La restrizione dell'accesso ai servizi consumer dovrebbe essere eseguita a proprio rischio. L'unico modo affidabile per bloccare i servizi consumer consiste nel limitare l'accesso al nome FQDN  *login.live.com*. Questo FQDN viene usato da una vasta gamma di servizi, inclusi i servizi non rivolti ai consumatori come MSDN, TechNet e altri. Il nome di dominio FQDN è usato anche dal programma Scambio protetto di file per il Supporto tecnico di Microsoft, ed è necessario per trasferire i file e facilitare la risoluzione dei problemi dei prodotti Microsoft.  La limitazione dell'accesso a questo FQDN può comportare la necessità di includere anche le eccezioni alla regola per le richieste di rete associate a questi servizi.
  
Tenere presente che non basta bloccare l'accesso ai servizi consumer Microsoft per impedire a un utente della rete di sottrarre informazioni mediante un tenant o un altro servizio di Office 365.

<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>Il firewall richiede indirizzi IP e non può elaborare gli URL. Come si configura per Office 365?

Office 365 non fornisce gli indirizzi IP di tutti gli endpoint di rete necessari. Alcuni sono disponibili solo come URL e sono catalogati come predefiniti. Gli URL nella categoria predefinita necessari devono essere consentiti tramite un server proxy. Se non si dispone di un server proxy, vedere come sono state configurate le richieste Web per gli URL che gli utenti digitano nella barra degli indirizzi di un Web browser. l'utente non fornisce nemmeno un indirizzo IP. Gli URL di categoria predefiniti di Office 365 che non forniscono indirizzi IP devono essere configurati nello stesso modo.

## <a name="related-topics"></a>Argomenti correlati

[Servizio web per indirizzi IP e URL di Office 365](microsoft-365-ip-web-service.md)

[Intervalli IP del data center di Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Spazio IP pubblico di Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Requisiti dell'infrastruttura di rete per Microsoft Intune](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute e Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)
  
[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)
  
[Principi della connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md)
