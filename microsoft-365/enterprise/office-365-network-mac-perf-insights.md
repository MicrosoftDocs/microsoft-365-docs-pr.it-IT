---
title: Microsoft 365 Insights Network (anteprima)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Insights Network (anteprima)
ms.openlocfilehash: 682c888fefb9bec9725e470d62019c857fc2de07
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171339"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Insights Network (anteprima)

Le **informazioni sulla rete** sono metriche delle prestazioni raccolte dal tenant Microsoft 365 e sono disponibili per la visualizzazione solo da parte di utenti amministrativi del tenant. Le informazioni dettagliate vengono visualizzate nell'interfaccia di amministrazione di Microsoft 365 all'indirizzo <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Gli Insight sono destinati a facilitare la progettazione di perimetri di rete per le posizioni di Office. Ogni Insight fornisce informazioni dettagliate sulle caratteristiche delle prestazioni per un problema comune specifico per ogni posizione geografica in cui gli utenti accedono al tenant.

Sono presenti sei informazioni specifiche sulla rete che possono essere visualizzate per ogni percorso di Office:

- [Uscita di rete con backhauling](#backhauled-network-egress)
- [Migliorare le prestazioni rilevate per i clienti nelle vicinanze](#better-performance-detected-for-customers-near-you)
- [Utilizzo di una porta anteriore del servizio Exchange Online non ottimale](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Utilizzo di una porta principale del servizio SharePoint Online non ottimale](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Velocità di download bassa dalla porta di ingresso di SharePoint](#low-download-speed-from-sharepoint-front-door)
- [Uscita di rete ottimale per gli utenti cinesi](#china-user-optimal-network-egress)

Sono disponibili due informazioni di rete a livello di tenant che è possibile visualizzare per il tenant. Sono inoltre presenti nelle pagine del Punteggio di producvitivy:

- [Connessioni con campionamento di Exchange interessate da problemi di connettività](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Connessioni con campionamento di SharePoint influenzate da problemi di connettività](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Insights di rete, raccomandazioni sulle prestazioni e valutazioni nell'interfaccia di amministrazione di Microsoft 365 è attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.

## <a name="backhauled-network-egress"></a>Uscita di rete con backhauling

Questa intuizione verrà visualizzata se il servizio Network Insights rileva che la distanza tra un determinato percorso utente e l'uscita di rete è superiore a 500 miglia (800 km), a indicare che il traffico di Microsoft 365 viene reindirizzato a un normale dispositivo o proxy di Internet Edge.

Questa intuizione è abbreviata in "uscita" in alcune visualizzazioni di riepilogo.

![Uscita di rete con backhauling](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Ciò indica che la distanza tra l'area di lavoro e l'uscita di rete è superiore a 500 miglia (800 km). La posizione di Office è identificata da una posizione del computer client offuscata e il percorso dell'uscita di rete viene identificato utilizzando l'indirizzo IP inverso nei database delle posizioni. La posizione di Office potrebbe non essere accurata se i servizi di posizione di Windows sono disabilitati nei computer. La posizione di uscita della rete potrebbe non essere accurata se le informazioni sul database degli indirizzi IP inversi non sono accurate.

Per informazioni dettagliate su questa panoramica, vedere l'ubicazione dell'ufficio, la percentuale stimata dell'utente tenant totale nel percorso, la posizione corrente di uscita della rete, la pertinenza del percorso di uscita, la distanza tra la posizione e il punto di uscita corrente, la data in cui è stata rilevata la condizione e la data in cui è stata risolta la condizione.

### <a name="what-should-i-do"></a>Cosa si può fare?

Per questa intuizione, è consigliabile utilizzare l'uscita di rete più vicina alla posizione di Office in modo che la connettività possa essere instradata in maniera ottimale alla rete globale di Microsoft e alla porta principale del servizio Microsoft 365 più vicina. Dopo aver chiuso l'uscita di rete per gli utenti, le posizioni di Office consentono anche di migliorare le prestazioni in futuro, in quanto Microsoft espande entrambi i punti di rete di presenza e le porte frontali del servizio Microsoft 365 in futuro.

Per ulteriori informazioni su come risolvere il problema, vedere l'argomento relativo alle [connessioni di rete in uscita localmente](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) nei [principi di connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md).

## <a name="better-performance-detected-for-customers-near-you"></a>Migliorare le prestazioni rilevate per i clienti nelle vicinanze

Questa intuizione verrà visualizzata se il servizio Network Insights rileva che un numero significativo di clienti nell'area metropolitana ha prestazioni migliori rispetto a quelle degli utenti dell'organizzazione in questa posizione di ufficio.

Questa intuizione è abbreviata in "peer" in alcune visualizzazioni di riepilogo.

![Prestazioni di rete relative](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

In questa panoramica vengono esaminate le prestazioni aggregate dei clienti di Microsoft 365 nella stessa città del percorso di Office. Questa intuizione viene visualizzata se la latenza media degli utenti è superiore del 10% rispetto alla media latenza dei tenant limitrofi.

### <a name="what-should-i-do"></a>Cosa si può fare?

Sono possibili molti motivi per questa condizione, tra cui la latenza della rete aziendale o dell'ISP, i colli di bottiglia o i problemi di progettazione dell'architettura. Esaminare la latenza tra ogni hop del percorso tra la rete aziendale e l'attuale porta principale di Microsoft 365. Per ulteriori informazioni, vedere [principi di connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Utilizzo di una porta anteriore del servizio Exchange Online non ottimale

Questa intuizione verrà visualizzata se il servizio Network Insights rileva che gli utenti in una posizione specifica non si connettono a un front door del servizio Exchange Online ottimale.

Questa intuizione è abbreviata in "routing" in alcune visualizzazioni di riepilogo.

![Porta anteriore EXO non ottimale](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Vengono elencate le porte anteriori del servizio Exchange Online che sono adatte per l'utilizzo da parte di Office location City con buone prestazioni. Se il test corrente Mostra l'utilizzo di una porta di ingresso del servizio Exchange Online non presente nell'elenco, verrà chiamato questo suggerimento.

### <a name="what-should-i-do"></a>Cosa si può fare?

L'utilizzo di una porta anteriore del servizio Exchange Online non ottimale può essere causato da un backhaul della rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita di rete locale e diretta. Potrebbe anche essere causato dall'utilizzo di un server resolver DNS ricorsivo remoto, nel qual caso si consiglia di allineare il server resolver ricorsivo DNS con l'uscita di rete.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Utilizzo di una porta principale del servizio SharePoint Online non ottimale

Questa intuizione verrà visualizzata se il servizio Network Insights rileva che gli utenti in una posizione specifica non si connettono al portale principale del servizio SharePoint Online più vicino.

Questa intuizione è abbreviata in "AFD" in alcune visualizzazioni di riepilogo.

![Porta anteriore non ottimale per SPO](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Identificare la porta di ingresso del servizio SharePoint Online a cui si connette il client di test. Quindi, per la città Ubicazione di Office, viene confrontato con il servizio SharePoint Online previsto per la città. In caso contrario, è consigliabile eseguire questa operazione.

### <a name="what-should-i-do"></a>Cosa si può fare?

L'utilizzo di un servizio di SharePoint Online non ottimale può essere causato da un backhaul della rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita di rete locale e diretta. Potrebbe anche essere causato dall'utilizzo di un server resolver DNS ricorsivo remoto, nel qual caso si consiglia di allineare il server resolver ricorsivo DNS con l'uscita di rete.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Velocità di download bassa dalla porta di ingresso di SharePoint

Questa intuizione verrà visualizzata se il servizio Network Insights rileva che la larghezza di banda tra la posizione specifica di Office e SharePoint Online è inferiore a 1 MBps.

Questa intuizione è abbreviata come "velocità effettiva" in alcune visualizzazioni di riepilogo.

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

La velocità di download che un utente può ottenere dalle porte frontali di servizio di SharePoint Online e OneDrive for business è misurata in megabyte al secondo (MBps). Se questo valore è inferiore a 1 MBps, verrà fornita questa panoramica.

### <a name="what-should-i-do"></a>Cosa si può fare?

Per migliorare la velocità di download, potrebbe essere necessario aumentare la larghezza di banda. In alternativa, è possibile che vi sia una congestione della rete tra i computer degli utenti nell'ubicazione dell'ufficio e la porta di servizio di SharePoint Online. A volte viene chiamato perdita congestizia e limita la velocità di download disponibile per gli utenti anche se è disponibile una larghezza di banda sufficiente.

## <a name="china-user-optimal-network-egress"></a>Uscita di rete ottimale per gli utenti cinesi

Questa intuizione verrà visualizzata se l'organizzazione dispone di utenti in Cina che si connettono al tenant Microsoft 365 in altre posizioni geografiche. 

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Se l'organizzazione dispone di connettività WAN privata, è consigliabile configurare un circuito WAN di rete dalle posizioni di Office in Cina che dispongono di un'uscita di rete su Internet in una delle posizioni seguenti:

- RAS di Hong Kong
- Giappone
- Taiwan
- Corea del Sud
- Singapore
- Malaysia

L'uscita Internet più lontana dagli utenti rispetto a queste posizioni ridurrà le prestazioni e l'uscita in Cina potrebbe causare problemi di connettività e latenza elevata a causa della congestione transfrontaliera.

### <a name="what-should-i-do"></a>Cosa si può fare?

Per ulteriori informazioni su come attenuare i problemi relativi alle prestazioni relativi a questa intuizione, vedere [Office 365 Global tenant Performance Optimization for China Users](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Connessioni con campionamento di Exchange interessate da problemi di connettività

Questa intuizione mostrerà quando 50% o più delle connessioni campionate sono influito. L'impatto è definito dalla valutazione di Exchange che si trova al di sotto del 60% per ogni campione.

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

È un'indicazione che la maggior parte degli utenti è probabile che si verifichino problemi di esperienza utente con Outlook che si connette a Exchange Online. La percentuale di esempi rappresenta probabilmente la percentuale di utenti che mostrano al di sotto di 60 punti.  

### <a name="what-should-i-do"></a>Cosa si può fare?

Abilitare la visibilità della connettività di rete di Office location se non è stato già fatto. Si desidera identificare quali uffici sono interessati da una scarsa connettività di rete che ha un impatto su Exchange e trovare modi per migliorare il perimetro della rete in ognuno dei quali connette gli utenti alla rete di Microsoft.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>Connessioni con campionamento di SharePoint influenzate da problemi di connettività

Questa intuizione mostrerà quando 50% o più delle connessioni campionate sono influito. L'impatto è definito dalla valutazione di SharePoint al di sotto del 40% per ogni campione.

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

È un'indicazione che la maggior parte degli utenti è probabile che si verifichino problemi di esperienza utente con SharePoint e OneDrive. La percentuale di esempi rappresenta probabilmente la percentuale di utenti che mostrano al di sotto di 40 punti.  

### <a name="what-should-i-do"></a>Cosa si può fare?

Abilitare la visibilità della connettività di rete di Office location se non è stato già fatto. Si desidera identificare quali uffici sono interessati da una scarsa connettività di rete che ha un impatto su SharePoint e trovare modi per migliorare il perimetro della rete in ognuno dei quali connette gli utenti alla rete di Microsoft.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Valutazione della rete Microsoft 365 (Preview)](office-365-network-mac-perf-score.md)

[Strumento di test della connettività di rete Microsoft 365 (anteprima)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)](office-365-network-mac-location-services.md)
