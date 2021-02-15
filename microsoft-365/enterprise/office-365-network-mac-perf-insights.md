---
title: Microsoft 365 Network Insights (anteprima)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (anteprima)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055474"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (anteprima)

**Le informazioni dettagliate** di rete sono metriche sulle prestazioni raccolte dal tenant di Microsoft 365 e possono essere visualizzate solo dagli utenti amministrativi nel tenant. I dati statistici vengono visualizzati nell'interfaccia di amministrazione di Microsoft 365 all'indirizzo <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Le informazioni dettagliate sono utili per progettare i perimetri di rete per le sedi degli uffici. Ogni approfondimento fornisce dettagli in tempo reale sulle caratteristiche delle prestazioni per un problema comune specifico per ogni posizione geografica in cui gli utenti accedono al tenant.

Sono disponibili sei informazioni dettagliate di rete specifiche che possono essere visualizzate per ogni posizione dell'ufficio:

- [Uscita dalla rete con backhauled](#backhauled-network-egress)
- [Dispositivo intermedio di rete](#network-intermediary-device)
- [Prestazioni migliori rilevate per i clienti nelle vicinanze](#better-performance-detected-for-customers-near-you)
- [Utilizzo di una porta d'ingresso del servizio Exchange Online non ottimale](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso di un front door del servizio SharePoint Online non ottimale](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Bassa velocità di download dalla porta d'ingresso di SharePoint](#low-download-speed-from-sharepoint-front-door)
- [Uscita di rete ottimale per gli utenti della Cina](#china-user-optimal-network-egress)

Sono disponibili due informazioni dettagliate sulla rete a livello di tenant che possono essere visualizzate per il tenant. Queste vengono visualizzate anche nelle pagine dei punteggi di produzione:

- [Connessioni campionate di Exchange influenzate da problemi di connettività](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Connessioni campionate di SharePoint influenzate da problemi di connettività](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Le informazioni dettagliate sulla rete, i consigli sulle prestazioni e le valutazioni nell'interfaccia di amministrazione di Microsoft 365 sono attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.

## <a name="backhauled-network-egress"></a>Uscita dalla rete con backhauled

Queste informazioni dettagliate verranno visualizzate se il servizio informazioni dettagliate di rete rileva che la distanza da una determinata posizione utente all'uscita di rete è maggiore di 800 chilometri, a indicare che il traffico di Microsoft 365 viene backhauled a un proxy o a un dispositivo perimetrale Internet comune.

Queste informazioni sono abbreviate come "Uscita" in alcune visualizzazioni di riepilogo.

![Uscita dalla rete con backhauled](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Ciò indica che la distanza tra la sede dell'ufficio e l'uscita di rete è superiore a 800 chilometri. La posizione dell'ufficio è identificata da un percorso del computer client offuscato e il percorso di uscita dalla rete viene identificato utilizzando l'indirizzo IP inverso per i database delle località. La posizione dell'ufficio potrebbe non essere corretta se i servizi di posizione di Windows sono disabilitati nei computer. Il percorso di uscita dalla rete potrebbe non essere accurato se le informazioni del database degli indirizzi IP inversa non sono accurate.

I dettagli per queste informazioni includono la posizione dell'ufficio, la percentuale stimata dell'utente tenant totale nella posizione, la posizione corrente di uscita dalla rete, la pertinenza della posizione di uscita, la distanza tra la posizione e il punto di uscita corrente, la data in cui la condizione è stata rilevata per la prima volta e la data in cui la condizione è stata risolta.

### <a name="what-should-i-do"></a>Cosa si può fare?

Per queste informazioni, è consigliabile l'uscita di rete più vicina alla sede dell'ufficio, in modo che la connettività possa instradare in modo ottimale alla rete globale di Microsoft e al front door del servizio Microsoft 365 più vicino. Una stretta uscita di rete nelle sedi degli utenti consente anche di migliorare le prestazioni in futuro, in quanto Microsoft espande i punti di presenza di rete e le porte anteriori dei servizi di Microsoft 365 in futuro.

Per ulteriori informazioni su come risolvere questo problema, vedere [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles.](microsoft-365-network-connectivity-principles.md)

## <a name="network-intermediary-device"></a>Dispositivo intermedio di rete

Queste informazioni verranno visualizzate se sono stati rilevati dispositivi tra gli utenti e la rete di Microsoft che potrebbero influire sull'esperienza utente di Office 365. È consigliabile ignorarlo per il traffico di rete specifico di Microsoft 365 destinato ai datacenter Microsoft. Questa raccomandazione è descritta anche in Principi di connettività di [rete di Microsoft 365](microsoft-365-network-connectivity-principles.md)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

I dispositivi intermedi di rete come server proxy, VPN e dispositivi di prevenzione della perdita dei dati possono influire sulle prestazioni e sulla stabilità dei client Microsoft 365 in cui il traffico è intermedio.

### <a name="what-should-i-do"></a>Cosa si può fare?

Configurare il dispositivo intermedio di rete rilevato per ignorare l'elaborazione del traffico di rete di Microsoft 365.

## <a name="better-performance-detected-for-customers-near-you"></a>Prestazioni migliori rilevate per i clienti nelle vicinanze

Queste informazioni dettagliate verranno visualizzate se il servizio informazioni dettagliate di rete rileva che un numero significativo di clienti nell'area della metropolitana ha prestazioni migliori rispetto agli utenti dell'organizzazione in questa sede dell'ufficio.

Queste informazioni sono abbreviate come "Peer" in alcune visualizzazioni di riepilogo.

![Prestazioni di rete relative](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Queste informazioni approfondite esaminano le prestazioni aggregate dei clienti di Microsoft 365 nella stessa città di questa sede. Queste informazioni vengono visualizzate se la latenza media degli utenti è superiore del 10% alla latenza media dei tenant adiacenti.

### <a name="what-should-i-do"></a>Cosa si può fare?

Questa condizione può essere causata da diversi motivi, tra cui la latenza nella rete aziendale o nell'ISP, colli di bottiglia o problemi di progettazione dell'architettura. Esaminare la latenza tra ogni hop nella route tra la rete dell'ufficio e l'attuale porta d'ingresso di Microsoft 365. Per ulteriori informazioni, vedere Principi di connettività di [rete di Microsoft 365.](microsoft-365-network-connectivity-principles.md)

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Utilizzo di una porta d'ingresso del servizio Exchange Online non ottimale

Queste informazioni dettagliate verranno visualizzate se il servizio informazioni dettagliate di rete rileva che gli utenti in una posizione specifica non si connettono a un front door ottimale del servizio Exchange Online.

Queste informazioni sono abbreviate come "Routing" in alcune visualizzazioni di riepilogo.

![Porta anteriore EXO non ottimale](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Sono elencate le porte anteriori del servizio Exchange Online adatte per l'uso dalla città di sede dell'ufficio con buone prestazioni. Se il test corrente mostra l'uso di un front door del servizio Exchange Online non in questo elenco, viene chiamato questo consiglio.

### <a name="what-should-i-do"></a>Cosa si può fare?

L'uso di una porta anteriore del servizio Exchange Online non ottimale potrebbe essere causato dal backhaul di rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita dalla rete locale e diretta. Potrebbe anche essere causato dall'uso di un server resolver DNS ricorsivo remoto, nel qual caso è consigliabile allineare il server resolver ricorsivo DNS all'uscita di rete.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Uso di un front door del servizio SharePoint Online non ottimale

Queste informazioni dettagliate verranno visualizzate se il servizio Informazioni dettagliate di rete rileva che gli utenti in una posizione specifica non si connettono al front door del servizio SharePoint Online più vicino.

Queste informazioni sono abbreviate come "Afd" in alcune visualizzazioni di riepilogo.

![Porta anteriore di Spo non ottimale](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Viene identificata la porta d'ingresso del servizio SharePoint Online a cui si connette il client di test. Quindi, per la città della sede centrale viene confrontata con la porta d'ingresso del servizio SharePoint Online prevista per quella città. Se non corrisponde, è consigliabile farlo.

### <a name="what-should-i-do"></a>Cosa si può fare?

L'uso di una porta anteriore del servizio SharePoint Online non ottimale potrebbe essere causato dal backhaul di rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita dalla rete locale e diretta. Potrebbe anche essere causato dall'uso di un server resolver DNS ricorsivo remoto, nel qual caso è consigliabile allineare il server resolver ricorsivo DNS all'uscita di rete.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Bassa velocità di download dalla porta d'ingresso di SharePoint

Queste informazioni dettagliate verranno visualizzate se il servizio Informazioni dettagliate di rete rileva che la larghezza di banda tra la posizione specifica dell'ufficio e SharePoint Online è inferiore a 1 MBps.

Queste informazioni sono abbreviate come "Velocità effettiva" in alcune visualizzazioni di riepilogo.

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

La velocità di download che un utente può ottenere dalle porte anteriori del servizio SharePoint Online e OneDrive for Business è misurata in megabyte al secondo (MBps). Se questo valore è inferiore a 1 MBps, queste informazioni vengono fornite.

### <a name="what-should-i-do"></a>Cosa si può fare?

Per migliorare la velocità di download, potrebbe essere necessario aumentare la larghezza di banda. In alternativa, potrebbe verificarsi una congestione della rete tra i computer degli utenti nella sede dell'ufficio e la porta d'ingresso del servizio SharePoint Online. A volte si tratta di una perdita congestionata che limita la velocità di download disponibile per gli utenti anche se è disponibile una larghezza di banda sufficiente.

## <a name="china-user-optimal-network-egress"></a>Uscita di rete ottimale per gli utenti della Cina

Queste informazioni verranno visualizzate se l'organizzazione ha utenti in Cina che si connettono al tenant di Microsoft 365 in altre posizioni geografiche. 

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Se l'organizzazione dispone di connettività WAN privata, è consigliabile configurare un circuito WAN di rete dalle sedi degli uffici in Cina con uscita di rete verso Internet in una delle posizioni seguenti:

- Hong Kong
- Giappone
- Taiwan
- Corea del Sud
- Singapore
- Malaysia

L'uscita di Internet più lontano dagli utenti rispetto a queste posizioni ridurrà le prestazioni e l'uscita in Cina potrebbe causare problemi di latenza e connettività elevati a causa della congestione oltre i confini.

### <a name="what-should-i-do"></a>Cosa si può fare?

Per ulteriori informazioni su come ridurre i problemi di prestazioni correlati a queste informazioni, vedere Ottimizzazione delle prestazioni del tenant globale di [Microsoft 365 per gli utenti della Cina.](microsoft-365-networking-china.md)

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Connessioni campionate di Exchange influenzate da problemi di connettività

Queste informazioni mostrano quando il 50% o più delle connessioni campionate sono influenzate. L'impatto è definito dalla valutazione di Exchange inferiore al 60% per ogni campione.

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Si tratta di un'indicazione del fatto che la maggior parte degli utenti probabilmente riscontra problemi di esperienza utente con Outlook che si connette a Exchange Online. La percentuale di campioni rappresenta probabilmente la percentuale di utenti che mostrano meno di 60 punti.  

### <a name="what-should-i-do"></a>Cosa si può fare?

Abilitare la visibilità della connettività di rete della posizione dell'ufficio, se non è già stata eseguita. Si desidera identificare quali uffici sono influenzati da una connettività di rete scadente che influisce su Exchange e trovare modi per migliorare il perimetro di rete in ognuno di essi che connette gli utenti alla rete di Microsoft.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>Connessioni campionate di SharePoint influenzate da problemi di connettività

Queste informazioni mostrano quando il 50% o più delle connessioni campionate sono influenzate. L'impatto è definito dalla valutazione di SharePoint inferiore al 40% per ogni campione.

### <a name="what-does-this-mean"></a>Cosa significa questo messaggio?

Si tratta di un'indicazione del fatto che è probabile che la maggior parte degli utenti stia riscontrando problemi di esperienza utente con SharePoint e OneDrive. La percentuale di campioni rappresenta probabilmente la percentuale di utenti che mostrano meno di 40 punti.  

### <a name="what-should-i-do"></a>Cosa si può fare?

Abilitare la visibilità della connettività di rete della posizione dell'ufficio, se non è già stata eseguita. Si desidera identificare gli uffici che sono influenzati da una connettività di rete scadente che influisce su SharePoint e trovare modi per migliorare il perimetro di rete in ognuno di essi che connette gli utenti alla rete di Microsoft.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Valutazione della rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-score.md)

[Strumento di test della connettività di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (anteprima)](office-365-network-mac-location-services.md)
