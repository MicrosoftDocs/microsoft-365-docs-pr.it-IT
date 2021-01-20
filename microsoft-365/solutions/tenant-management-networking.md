---
title: Passaggio 2. Rete ottimale per i tenant di Microsoft 365 per Enterprise
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
ms.custom:
- Ent_Solutions
description: Ottimizzare l'accesso di rete ai tenant di Microsoft 365.
ms.openlocfilehash: 1e57911a6e8c51af3ae00ff0f9053bf9273e0e17
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908648"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 2. Rete ottimale per i tenant di Microsoft 365 per Enterprise

Microsoft 365 per Enterprise include app per la produttività del cloud quali teams ed Exchange Online e Microsoft Intune, oltre a numerosi servizi di sicurezza e identità di Microsoft Azure. Tutti questi servizi basati su cloud si basano sulla sicurezza, le prestazioni e l'affidabilità delle connessioni dai dispositivi client sulla rete locale o su qualsiasi percorso su Internet. 

Per ottimizzare l'accesso alla rete per il tenant, è necessario eseguire le operazioni seguenti:

- Ottimizzare il percorso tra gli utenti locali e la posizione più vicina alla rete globale di Microsoft.
- Ottimizzare l'accesso alla rete globale Microsoft per gli utenti remoti che utilizzano una soluzione VPN di accesso remoto.
- Utilizzare le informazioni di rete per progettare il perimetro di rete per le posizioni di Office.
- Ottimizzare l'accesso a risorse specifiche ospitate in siti di SharePoint con la rete CDN di Office 365.
- Configurare i dispositivi proxy e di rete perimetrale per ignorare l'elaborazione per il traffico trusted di Microsoft 365 con l'elenco degli endpoint e automatizzare l'aggiornamento dell'elenco in base alle modifiche apportate.

## <a name="enterprise-on-premises-workers"></a>Operai locali aziendali

Per le reti aziendali, è consigliabile ottimizzare l'esperienza dell'utente finale abilitando l'accesso alla rete con prestazioni massime tra i client e gli endpoint Microsoft 365 più vicini. La qualità dell'esperienza dell'utente finale è direttamente correlata alle prestazioni e alla capacità di risposta dell'applicazione che l'utente sta utilizzando. Ad esempio, Microsoft teams si basa su una bassa latenza, in modo che le chiamate telefoniche degli utenti, le conferenze e le collaborazioni dello schermo condiviso siano senza problemi.

L'obiettivo principale della progettazione della rete deve essere ridurre al minimo la latenza riducendo il tempo di andata e ritorno (RTT, Round Trip Time) dai dispositivi client alla rete globale Microsoft, la backbone di rete pubblica di Microsoft che collega tutti i datacenter di Microsoft con una bassa latenza, punti di ingresso dell'applicazione cloud a disponibilità elevata, noti come front door, distribuiti in tutto il mondo

Di seguito è riportato un esempio di una rete aziendale tradizionale.

![Una rete aziendale tradizionale con accesso centrale a Internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

In questa figura, le succursali si connettono a una sede centrale tramite i dispositivi WAN (Wide Area Network) e una backbone WAN. L'accesso a Internet avviene tramite un dispositivo di sicurezza o proxy nel perimetro della rete dell'ufficio centrale e di un provider di servizi Internet (ISP). Su Internet, la rete globale di Microsoft ha una serie di porte frontali nelle aree di tutto il mondo. Le organizzazioni possono anche utilizzare posizioni intermedie per l'elaborazione e la sicurezza dei pacchetti aggiuntivi per il traffico. Il tenant Microsoft 365 di un'organizzazione si trova all'interno della rete globale Microsoft.

I problemi relativi alla configurazione per i servizi cloud di Microsoft 365 sono i seguenti:

- Per gli utenti nelle succursali, il traffico viene inviato a porte anteriori non locali, aumentando la latenza.
- Invio di traffico verso percorsi intermedi creare tornanti di rete che eseguono l'elaborazione di pacchetti duplicati sul traffico attendibile, aumentando la latenza.
- I dispositivi di rete perimetrale eseguono l'elaborazione di pacchetti non necessari e duplicati sul traffico attendibile, aumentando la latenza.

L'ottimizzazione delle prestazioni di rete di Microsoft 365 non deve essere complicata. È possibile ottenere le migliori prestazioni possibili seguendo alcuni principi fondamentali:

- Identificare il traffico di rete Microsoft 365, ovvero il traffico Trusted destinato ai servizi cloud Microsoft.
- Consenti la fuoriuscita delle succursali locali del traffico di rete di Microsoft 365 su Internet da ogni percorso in cui gli utenti si connettono a Microsoft 365.
- Evitare i tornanti di rete.
- Consenti al traffico Microsoft 365 di bypassare proxy e dispositivi di ispezione di pacchetti.

Se si implementano questi principi, è possibile ottenere una rete aziendale ottimizzata per Microsoft 365.

![Una rete aziendale ottimizzata per Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

In questa figura, le succursali dispongono di una connessione Internet tramite un dispositivo WAN (SDWAN) software definito, che invia il traffico attendibile di Microsoft 365 alla porta principale più vicina a livello regionale. Presso la sede centrale, il traffico trusted Microsoft 365 ignora il dispositivo di sicurezza o proxy e i dispositivi intermedi non vengono più utilizzati.

Ecco come la configurazione ottimizzata risolve i problemi di latenza di una rete aziendale tradizionale:

- Il traffico trusted Microsoft 365 ignora la backbone WAN e viene inviata a porte anteriori locali per tutti gli uffici, diminuendo la latenza.
- I tornanti di rete che eseguono l'elaborazione di pacchetti duplicati vengono ignorati per il traffico trusted di Microsoft 365, che diminuisce la latenza.
- I dispositivi di rete perimetrale che eseguono l'elaborazione di pacchetti non necessari e duplicati vengono ignorati per il traffico trusted di Microsoft 365, diminuendo la latenza.

Per ulteriori informazioni, vedere [Panoramica della connettività di rete di Microsoft 365](../enterprise/microsoft-365-networking-overview.md).

## <a name="remote-workers"></a>Lavoratori remoti

Se i lavoratori remoti usano un client VPN tradizionale per ottenere l'accesso remoto alla rete dell'organizzazione, verificare che nel client VPN vi sia la modalità split tunneling. Senza split tunneling, tutto il traffico di lavoro remoto viene inviato attraverso la connessione VPN, tramite la quale viene poi inoltrato ai dispositivi perimetrali dell'organizzazione per essere quindi elaborato e inviato su Internet. Ecco un esempio.

![Traffico di rete dai client VPN senza tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

In questa figura, il traffico di Microsoft 365 deve intraprendere una route indiretta tramite l'organizzazione, che potrebbe essere inoltrata a una porta principale di Microsoft Global Network lontana dal percorso fisico del client VPN. Questo percorso indiretto aggiunge latenza al traffico di rete e riduce le prestazioni complessive. 

Grazie alla modalità split tunneling, è possibile configurare il client VPN per escludere tipi specifici di traffico da inviare tramite la connessione VPN alla rete dell'organizzazione.

Per ottimizzare l'accesso alle risorse cloud di Microsoft 365, configurare i client VPN di split tunneling per escludere il traffico agli endpoint di Microsoft 365 di categoria **Ottimizzazione** tramite connessione VPN. Per ulteriori informazioni, vedere [categorie di endpoint di Office 365](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) e [gli elenchi](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) di endpoint di categoria optimize per il tunneling suddiviso.

Di seguito è indicato il flusso di traffico risultante per il tunneling suddiviso, in cui la maggior parte del traffico verso le app cloud di Microsoft 365 ignora la connessione VPN.

![Traffico di rete dai client VPN con tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

In questa figura, il client VPN invia e riceve il traffico del servizio cloud Microsoft 365 cruciale direttamente su Internet e verso la porta principale più vicina alla rete globale Microsoft.

Per informazioni dettagliate e per materiale sussidiario, consultare [Ottimizzare la connettività di Office 365 per gli utenti remoti tramite split tunneling per VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Utilizzo di informazioni di rete (anteprima)

Le informazioni sulla rete sono metriche delle prestazioni raccolte dal tenant Microsoft 365 che consentono di progettare perimetri di rete per le posizioni di Office. Ogni Insight fornisce informazioni dettagliate sulle caratteristiche delle prestazioni per un determinato problema per ogni posizione geografica in cui gli utenti locali stanno accedendo al tenant.

Sono disponibili due informazioni di rete a livello di tenant che è possibile visualizzare per il tenant:

- [Connessioni con campionamento di Exchange interessate da problemi di connettività](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Connessioni con campionamento di SharePoint influenzate da problemi di connettività](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Si tratta di informazioni specifiche sulla rete per ogni percorso di Office:

- [Uscita di rete con backhauling](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Migliorare le prestazioni rilevate per i clienti nelle vicinanze](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Utilizzo di una porta anteriore del servizio Exchange Online non ottimale](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Utilizzo di una porta principale del servizio SharePoint Online non ottimale](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Velocità di download bassa dalla porta di ingresso di SharePoint](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Uscita di rete ottimale per gli utenti cinesi](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Le informazioni di rete, le raccomandazioni sulle prestazioni e le valutazioni nell'interfaccia di amministrazione di Microsoft 365 sono attualmente in stato di anteprima. È disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.

Per ulteriori informazioni, vedere [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>Prestazioni di SharePoint con la rete CDN di Office 365

La rete CDN (Content Delivery Network) basata su cloud consente di ridurre i tempi di caricamento, la larghezza di banda e la velocità di risposta. Una rete CDN consente di migliorare le prestazioni memorizzando nella cache risorse statiche quali file grafici o video più vicini ai browser che li richiedono, contribuendo ad accelerare i download e a ridurre la latenza. È possibile utilizzare la rete di distribuzione dei contenuti (CDN) di Office 365 integrata, inclusa in SharePoint in Microsoft 365 E3 e E5, per ospitare le risorse statiche per offrire prestazioni migliori per le pagine di SharePoint.

La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità. A seconda del tipo di contenuto che si desidera ospitare nella rete CDN di Office 365, è possibile aggiungere origini **pubbliche** , origini **private** o entrambe.

Quando viene distribuita e configurata, la rete CDN di Office 365 carica le risorse da origini pubbliche e private e le rende disponibili per un accesso rapido agli utenti che si trovano su Internet.

![Distribuzione della rete CDN di Office 365 per gli utenti](../media/O365-CDN/o365-cdn-flow-transparent.svg "Distribuzione della rete CDN di Office 365 per gli utenti")

Per ulteriori informazioni, vedere [utilizzare la rete CDN di Office 365 con SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md).

## <a name="automated-endpoint-listing"></a>Elenco automatico di endpoint

Affinché i client locali, i dispositivi perimetrali e i servizi di analisi pacchetti basati su cloud ignorino l'elaborazione del traffico attendibile di Microsoft 365, è necessario configurarli con l'insieme di endpoint (intervalli di indirizzi IP e nomi DNS) corrispondenti ai servizi di Microsoft 365. Tali endpoint possono essere configurati manualmente nei firewall e in altri dispositivi di sicurezza Edge, i file PAC per i computer client per ignorare i proxy o i dispositivi SD-WAN nelle succursali. Tuttavia, gli endpoint cambiano nel tempo, richiedendo la manutenzione manuale in corso degli elenchi di endpoint in queste posizioni.

Per automatizzare l'elenco e la gestione delle modifiche per gli endpoint di Microsoft 365 nei file PAC e nei dispositivi di rete del client, utilizzare l' [indirizzo IP e il servizio Web di Office 365 basato sul Rest](../enterprise/microsoft-365-ip-web-service.md). Questo servizio consente di identificare e distinguere meglio il traffico di rete di Microsoft 365, semplificando la valutazione, la configurazione e la permanenza delle modifiche più recenti.

È possibile utilizzare PowerShell, Python o altre lingue per determinare le modifiche apportate agli endpoint nel tempo e configurare i file PAC e i dispositivi di rete perimetrale.

Il processo di base è:

1. Utilizzare il servizio Web indirizzo IP e URL di Office 365 e il meccanismo di configurazione desiderato per configurare i file PAC e i dispositivi di rete con il set corrente di endpoint di Microsoft 365.
2. Eseguire una ricorrenza giornaliera per verificare le modifiche apportate agli endpoint oppure utilizzare un metodo di notifica.
3. Quando vengono rilevate modifiche, rigenerare e ridistribuire il file PAC per i computer client e apportare le modifiche ai dispositivi di rete.

Per ulteriori informazioni, vedere [Office 365 IP address and URL Web Service](../enterprise/microsoft-365-ip-web-service.md).

## <a name="results-of-step-2"></a>Risultati del passaggio 2

Per il tenant Microsoft 365 con reti ottimali, sono state determinate le seguenti operazioni:

- Come ottimizzare le prestazioni di rete per gli utenti locali aggiungendo connessioni Internet a tutte le filiali ed eliminando i tornanti di rete.
- Come implementare l'elenco degli endpoint attendibili automatizzati per i file PAC basati su client e i dispositivi e i servizi di rete, inclusi gli aggiornamenti in esecuzione (più adatti per le reti aziendali).
- Informazioni su come supportare l'accesso dei dipendenti remoti alle risorse locali.
- Come utilizzare le informazioni di rete
- Come distribuire la rete CDN di Office 365.

Di seguito è riportato un esempio di organizzazione aziendale e del relativo tenant con una rete ottimale.

![Esempio di un tenant con reti ottimali](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Visualizzazione di una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

In questa figura, il tenant per l'organizzazione Enterprise ha:

- Accesso Internet locale per ogni succursale con un dispositivo di SDWAN che inoltra il traffico trusted di Microsoft 365 a una porta anteriore locale.
- Nessun tornanti di rete.
- Dispositivi di sicurezza e proxy perimetrali di Office centrali che inoltrano il traffico trusted di Microsoft 365 a una porta principale locale.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Manutenzione continua per una rete ottimale

Su base continuativa, potrebbe essere necessario eseguire le operazioni seguenti:

- Aggiornare i dispositivi perimetrali e i file PAC distribuiti per le modifiche negli endpoint o verificare che il processo automatico funzioni correttamente.
- Gestione delle risorse nella rete CDN di Office 365.
- Aggiornare la configurazione del tunneling suddiviso nei client VPN per le modifiche negli endpoint.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 3. Sincronizzare le identità e applicare gli accessi sicuri](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Continuare con l' [identità](tenant-management-identity.md) per sincronizzare gli account e i gruppi locali e applicare gli accessi per gli utenti sicuri.
