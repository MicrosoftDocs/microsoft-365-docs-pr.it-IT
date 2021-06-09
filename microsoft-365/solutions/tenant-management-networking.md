---
title: Passaggio 2. Rete ottimale per la Microsoft 365 per i tenant aziendali
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Ottimizzare l'accesso di rete Microsoft 365 tenant.
ms.openlocfilehash: 5eac0793d2afc924a919671ffa105362ea1866d9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407193"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 2. Rete ottimale per la Microsoft 365 per i tenant aziendali

Microsoft 365 per le aziende include app di produttività cloud come Teams, Exchange Online e Microsoft Intune, insieme a molti servizi di identità e sicurezza di Microsoft Azure. Tutti questi servizi basati sul cloud si basano sulla sicurezza, sulle prestazioni e sull'affidabilità delle connessioni dai dispositivi client nella rete locale o in qualsiasi posizione su Internet. 

Per ottimizzare l'accesso alla rete per il tenant, è necessario:

- Ottimizzare il percorso tra gli utenti locali e la posizione più vicina a Microsoft Global Network.
- Ottimizzare l'accesso a Microsoft Global Network per gli utenti remoti che utilizzano una soluzione VPN di accesso remoto.
- Usare Network Insights per progettare il perimetro di rete per le posizioni dell'ufficio.
- Ottimizzare l'accesso a risorse specifiche ospitate SharePoint siti con Office 365 rete CDN.
- Configurare i dispositivi proxy e perimetrali di rete per ignorare l'elaborazione per Microsoft 365 traffico attendibile con l'elenco di endpoint e automatizzare l'aggiornamento dell'elenco quando vengono apportate modifiche.

## <a name="enterprise-on-premises-workers"></a>Enterprise dipendenti locali

Per le reti aziendali, è consigliabile ottimizzare l'esperienza utente finale abilitando l'accesso di rete con le prestazioni più alte tra i client e gli endpoint Microsoft 365 più vicini. La qualità dell'esperienza utente finale è direttamente correlata alle prestazioni e alla velocità di risposta dell'applicazione utilizzata dall'utente. Ad esempio, Microsoft Teams si basa su una bassa latenza in modo che le chiamate telefoniche, le conferenze e le collaborazioni su schermo condivise siano senza problemi.

L'obiettivo principale nella progettazione della rete deve essere ridurre al minimo la latenza riducendo il tempo di andata e ritorno (RTT) dai dispositivi client a Microsoft Global Network, la backbone di rete pubblica di Microsoft che collega tutti i data center di Microsoft con punti di ingresso dell'applicazione cloud a bassa latenza e disponibilità elevata, noti come porte anteriori, distribuiti in tutto il mondo.

Ecco un esempio di rete aziendale tradizionale.

![Una rete aziendale tradizionale con accesso centrale a Internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

In questa illustrazione, le succursali si connettono a un ufficio centrale tramite dispositivi WAN (Wide Area Network) e una backbone WAN. L'accesso a Internet è tramite un dispositivo di sicurezza o proxy nella rete dell'ufficio centrale e un provider di servizi Internet (ISP). Su Internet, Microsoft Global Network dispone di una serie di porte anteriori nelle aree geografiche di tutto il mondo. Le organizzazioni possono inoltre utilizzare posizioni intermedie per l'elaborazione e la sicurezza dei pacchetti aggiuntive per il traffico. Il tenant di Microsoft 365'organizzazione si trova all'interno di Microsoft Global Network.

I problemi relativi a questa configurazione per Microsoft 365 cloud sono:

- Per gli utenti nelle succursali, il traffico viene inviato alle porte anteriori non locali, aumentando la latenza.
- L'invio di traffico a posizioni intermedie crea hairpin di rete che eseguono l'elaborazione di pacchetti duplicati sul traffico attendibile, aumentando la latenza.
- I dispositivi perimetrali di rete eseguono un'elaborazione dei pacchetti non richiesta e duplicata sul traffico attendibile, aumentando la latenza.

L'ottimizzazione Microsoft 365 prestazioni di rete non deve essere complicata. È possibile ottenere le migliori prestazioni possibili seguendo alcuni principi chiave:

- Identificare Microsoft 365 di rete, ovvero il traffico attendibile destinato ai servizi cloud Microsoft.
- Consentire l'uscita del ramo locale Microsoft 365 traffico di rete verso Internet da ogni posizione in cui gli utenti si connettono Microsoft 365.
- Evitare i tornanti di rete.
- Consentire Microsoft 365 traffico di ignorare proxy e dispositivi di ispezione dei pacchetti.

Se si implementano questi principi, si ottiene una rete aziendale ottimizzata per Microsoft 365.

![Una rete aziendale ottimizzata per la Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

In questa illustrazione, le succursali dispongono di una propria connessione Internet tramite un dispositivo SDWAN (Software-Defined WAN Device), che invia il traffico Microsoft 365 trusted alla porta principale più vicina a livello regionale. Nell'ufficio centrale, il traffico Microsoft 365 ignora il dispositivo di sicurezza o proxy e i dispositivi intermedi non vengono più utilizzati.

Ecco come la configurazione ottimizzata risolve i problemi di latenza di una rete aziendale tradizionale:

- Il Microsoft 365 attendibile ignora la backbone WAN e viene inviato alle porte anteriori locali per tutti gli uffici, riducendo la latenza.
- I hairpin di rete che eseguono l'elaborazione di pacchetti duplicati vengono ignorati per Microsoft 365 traffico attendibile, riducendo la latenza.
- I dispositivi perimetrali di rete che eseguono l'elaborazione di pacchetti non necessario e duplicati vengono ignorati per Microsoft 365 traffico attendibile, riducendo la latenza.

Per ulteriori informazioni, vedere panoramica Microsoft 365 [connettività di rete](../enterprise/microsoft-365-networking-overview.md).

## <a name="remote-workers"></a>Lavoratori remoti

Se i lavoratori remoti usano un client VPN tradizionale per ottenere l'accesso remoto alla rete dell'organizzazione, verificare che nel client VPN vi sia la modalità split tunneling. Senza split tunneling, tutto il traffico di lavoro remoto viene inviato attraverso la connessione VPN, tramite la quale viene poi inoltrato ai dispositivi perimetrali dell'organizzazione per essere quindi elaborato e inviato su Internet. Ecco un esempio.

![Traffico di rete dai client VPN senza tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

In questa figura, Microsoft 365 traffico deve eseguire una route indiretta attraverso l'organizzazione, che potrebbe essere inoltrata a una porta principale di Microsoft Global Network lontano dalla posizione fisica del client VPN. Questo percorso indiretto aggiunge latenza al traffico di rete e riduce le prestazioni complessive. 

Grazie alla modalità split tunneling, è possibile configurare il client VPN per escludere tipi specifici di traffico da inviare tramite la connessione VPN alla rete dell'organizzazione.

Per ottimizzare l'accesso alle risorse cloud di Microsoft 365, configurare i client VPN di split tunneling per escludere il traffico agli endpoint di Microsoft 365 di categoria **Ottimizzazione** tramite connessione VPN. Per ulteriori informazioni, vedere Office 365 [](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) [di endpoint](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) e gli elenchi di endpoint di categoria Optimize per lo split tunneling.

Ecco il flusso di traffico risultante per lo split tunneling, in cui la maggior parte del traffico verso Microsoft 365 cloud ignora la connessione VPN.

![Traffico di rete dai client VPN con tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

In questa illustrazione, il client VPN invia e riceve il traffico fondamentale del servizio cloud Microsoft 365 direttamente su Internet e verso la porta principale più vicina alla rete globale Microsoft.

Per informazioni dettagliate e per materiale sussidiario, consultare [Ottimizzare la connettività di Office 365 per gli utenti remoti tramite split tunneling per VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Uso di Network Insights (anteprima)

Le informazioni dettagliate sulla rete sono metriche sulle prestazioni raccolte dal tenant Microsoft 365 che consentono di progettare perimetri di rete per le posizioni dell'ufficio. Ogni approfondimento fornisce dettagli in tempo reale sulle caratteristiche delle prestazioni per un problema specifico per ogni posizione geografica in cui gli utenti locali accedono al tenant.

Sono disponibili due informazioni dettagliate sulla rete a livello di tenant che possono essere visualizzate per il tenant:

- [Exchange le connessioni campionate influenzate da problemi di connettività](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint le connessioni campionate influenzate da problemi di connettività](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Queste sono le informazioni dettagliate di rete specifiche per ogni posizione dell'ufficio:

- [Uscita di rete con backhauled](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Prestazioni migliori rilevate per i clienti nelle vicinanze](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Uso di una porta d'ingresso del Exchange Online non ottimale](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso di una porta d'ingresso del servizio SharePoint online non ottimale](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Bassa velocità di download da SharePoint porta principale](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Uscita di rete ottimale per gli utenti in Cina](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Informazioni dettagliate sulla rete, consigli sulle prestazioni e valutazioni nell Microsoft 365'interfaccia di amministrazione è attualmente in stato di anteprima. È disponibile solo per Microsoft 365 tenant registrati nel programma di anteprima delle funzionalità.

Per ulteriori informazioni, vedere [Microsoft 365 Network Insights.](../enterprise/office-365-network-mac-perf-insights.md)

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>SharePoint prestazioni con il Office 365 rete CDN

Una soluzione basata su cloud rete per la distribuzione di contenuti (rete CDN) consente di ridurre i tempi di caricamento, risparmiare larghezza di banda e velocità di risposta. Un rete CDN migliora le prestazioni memorizzando nella cache asset statici come file grafici o video più vicini ai browser che li richiedono, per velocizzare i download e ridurre la latenza. Puoi usare il Office 365 rete per la distribuzione di contenuti (rete CDN), incluso con SharePoint in Microsoft 365 E3 ed E5, per ospitare asset statici per garantire prestazioni migliori per le pagine SharePoint.

La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità. A seconda del tipo di contenuto che vuoi ospitare nel  Office 365 rete CDN, puoi aggiungere origini **pubbliche,** origini private o entrambe.

Quando viene distribuito e configurato, il Office 365 rete CDN carica gli asset da origini pubbliche e private e li rende disponibili per l'accesso rapido agli utenti che si trovano su Internet.

![Office 365 rete CDN distribuiti per gli utenti](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 rete CDN distribuiti per gli utenti")

Per ulteriori informazioni, vedere [Use the Office 365 rete CDN with SharePoint Online.](../enterprise/use-microsoft-365-cdn-with-spo.md)

## <a name="automated-endpoint-listing"></a>Presentazione automatica degli endpoint

Per fare in modo che i client locali, i dispositivi perimetrali e i servizi di analisi dei pacchetti basati su cloud eserevano l'elaborazione del traffico Microsoft 365 attendibile, è necessario configurarli con il set di endpoint (intervalli di indirizzi IP e nomi DNS) corrispondenti ai servizi Microsoft 365. Questi endpoint possono essere configurati manualmente nei firewall e in altri dispositivi di sicurezza perimetrali, nei file PAC per i computer client per ignorare i proxy o nei dispositivi SD-WAN nelle succursali. Tuttavia, gli endpoint cambiano nel tempo, richiedendo una manutenzione manuale continua degli elenchi di endpoint in queste posizioni.

Per automatizzare la gestione delle presentazioni e delle modifiche per gli endpoint di Microsoft 365 nei file PAC client e nei dispositivi di rete, utilizzare il servizio Web basato su REST Office 365 e [l'URL](../enterprise/microsoft-365-ip-web-service.md). Questo servizio consente di identificare e differenziare meglio Microsoft 365 di rete, semplificando la valutazione, la configurazione e il rispetto delle modifiche più recenti.

Puoi usare PowerShell, Python o altri linguaggi per determinare le modifiche apportate agli endpoint nel tempo e configurare i file PAC e i dispositivi di rete perimetrale.

Il processo di base è:

1. Usa il servizio Web Office 365 indirizzo IP e URL e il meccanismo di configurazione di tua scelta per configurare i file PAC e i dispositivi di rete con il set corrente di endpoint Microsoft 365 rete.
2. Eseguire una ricorrenza giornaliera per verificare la presenza di modifiche negli endpoint o usare un metodo di notifica.
3. Quando vengono rilevate modifiche, rigenerare e ridistribuire il file PAC per i computer client e apportare le modifiche ai dispositivi di rete.

Per ulteriori informazioni, vedere [Office 365 ip address and URL web service](../enterprise/microsoft-365-ip-web-service.md).

## <a name="results-of-step-2"></a>Risultati del passaggio 2

Per il Microsoft 365 tenant con una rete ottimale, è stato determinato:

- Come ottimizzare le prestazioni di rete per gli utenti locali aggiungendo connessioni Internet a tutte le succursali ed eliminando i tornanti di rete.
- Come implementare la presentazione automatica degli endpoint attendibili per i file PAC basati su client e i dispositivi e i servizi di rete, inclusi gli aggiornamenti in corso (più adatti per le reti aziendali).
- Come supportare l'accesso dei lavoratori remoti alle risorse locali.
- Come usare Network Insights
- Come distribuire il Office 365 rete CDN.

Ecco un esempio di un'organizzazione aziendale e del relativo tenant con una rete ottimale.

![Esempio di tenant con rete ottimale](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Vedi una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

In questa figura, il tenant per questa organizzazione aziendale dispone di:

- Accesso a Internet locale per ogni succursale con un dispositivo SDWAN che inoltra il traffico Microsoft 365 attendibile a una porta principale locale.
- Nessun hairpin di rete.
- Sicurezza dell'ufficio centrale e dispositivi perimetrali proxy che inoltrano Microsoft 365 traffico attendibile a una porta principale locale.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Manutenzione continua per una rete ottimale

Su base continuativa, potrebbe essere necessario:

- Aggiornare i dispositivi perimetrali e i file PAC distribuiti per le modifiche negli endpoint o verificare che il processo automatizzato funzioni correttamente.
- Gestire gli asset nella Office 365 rete CDN.
- Aggiornare la configurazione di split tunneling nei client VPN per le modifiche negli endpoint.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 3. Sincronizzare le identità e applicare gli accesso sicuri](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Continuare con [l'identità](tenant-management-identity.md) per sincronizzare gli account e i gruppi locali e applicare gli accesso degli utenti sicuri.
