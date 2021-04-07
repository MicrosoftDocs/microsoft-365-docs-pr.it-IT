---
title: Ottimizzazione delle prestazioni del tenant globale di Microsoft 365 per gli utenti della Cina
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: In questo articolo vengono fornite indicazioni per l'ottimizzazione delle prestazioni di rete per gli utenti in Cina dei tenant globali di Microsoft 365.
ms.openlocfilehash: e330e892b584c805bded2228381e74e6a4fa615a
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615196"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Ottimizzazione delle prestazioni del tenant globale di Microsoft 365 per gli utenti della Cina

>[!IMPORTANT]
>Queste indicazioni sono specifiche per gli scenari di utilizzo in cui gli utenti di **Microsoft 365** aziendali situati in Cina si connettono a un **tenant globale di Microsoft 365.** Questa guida non **si** applica ai tenant in Office 365 gestito da 21Vianet.

Per le aziende con tenant globali di Microsoft 365 e presenza aziendale in Cina, le prestazioni dei client Microsoft 365 per gli utenti basati sulla Cina possono essere complicate da fattori specifici dell'architettura Internet di China Telco.

Gli ISP della Cina hanno connessioni off-shore regolamentate a Internet pubblico globale che passano attraverso dispositivi perimetrali che sono inclini a livelli elevati di congestione della rete cross-border. Questa congestione crea perdita di pacchetti e latenza per tutto il traffico Internet in ingresso e in uscita dalla Cina.

![Traffico di Microsoft 365 - non definito](../media/O365-networking/China-O365-unoptimized.png)

La perdita e la latenza dei pacchetti sono dannose per le prestazioni dei servizi di rete, in particolare per i servizi che richiedono scambi di dati di grandi dimensioni (ad esempio trasferimenti di file di grandi dimensioni) o che richiedono prestazioni quasi in tempo reale (applicazioni audio e video).

L'obiettivo di questo argomento è fornire le procedure consigliate per ridurre l'impatto della congestione della rete transfrontaliera cinese sui servizi di Microsoft 365. In questo argomento non vengono risolti altri problemi comuni relativi alle prestazioni dell'ultimo miglio, ad esempio problemi di latenza elevata dei pacchetti a causa di instradamento complesso all'interno dei vettori cinesi.

## <a name="corporate-network-best-practices"></a>Procedure consigliate per la rete aziendale

Molte aziende con tenant e utenti di Microsoft 365 globali in Cina hanno implementato reti private che trasportano il traffico di rete aziendale tra sedi di uffici della Cina e sedi off-shore in tutto il mondo. Queste aziende possono sfruttare questa infrastruttura di rete per evitare congestione della rete transfrontaliera e ottimizzare le prestazioni dei servizi di Microsoft 365 in Cina.

>[!IMPORTANT]
>Come per tutte le implementazioni WAN private, è sempre consigliabile consultare i requisiti normativi per il proprio paese e/o area geografica per assicurarsi che la configurazione di rete sia conforme.

Come primo passaggio, è fondamentale seguire le linee guida di rete di riferimento in Pianificazione della rete e ottimizzazione delle prestazioni [per Microsoft 365.](./network-planning-and-performance.md) L'obiettivo principale dovrebbe essere evitare di accedere ai servizi globali di Microsoft 365 da Internet in Cina, se possibile.

- Sfruttare la rete privata esistente per trasportare il traffico di rete di Microsoft 365 tra le reti di uffici della Cina e le posizioni off-shore in uscita su Internet pubblico al di fuori della Cina. Quasi tutte le località al di fuori della Cina offriranno un chiaro vantaggio. Gli amministratori di rete possono ottimizzare ulteriormente l'uscita in aree con interconnessione a bassa latenza con [la rete globale Microsoft.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hong Kong, Giappone e Corea del Sud sono esempi.
- Configurare i dispositivi utente per accedere alla rete aziendale tramite una connessione VPN per consentire al traffico di Microsoft 365 di transitare sul collegamento off-shore privato della rete aziendale. Verificare che i client VPN non siano configurati per l'utilizzo del split tunneling o che i dispositivi utente siano configurati per ignorare il split tunneling per il traffico di Microsoft 365. Per ulteriori informazioni sull'ottimizzazione della connettività VPN per Teams e sul traffico multimediale in tempo reale, vedere [questa sezione.](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)
- Configurare la rete per instradare tutto il traffico di Microsoft 365 attraverso il collegamento off-shore privato. Se è necessario ridurre al minimo il volume di traffico sul collegamento privato, è possibile  scegliere di instradare solo gli endpoint nella categoria **Ottimizza** e consentire alle richieste agli endpoint Allow e **Default** di transitare su Internet. Ciò consente di migliorare le prestazioni e ridurre al minimo il consumo di larghezza di banda limitando il traffico ottimizzato ai servizi critici più sensibili all'elevata latenza e alla perdita di pacchetti.
- Se possibile, utilizzare UDP anziché TCP per il traffico di streaming multimediale live, ad esempio per Teams. UDP offre prestazioni di streaming multimediale live migliori rispetto a TCP.

Per informazioni su come instradare in modo selettivo il traffico di Microsoft 365, vedere [Managing Office 365 endpoints.](managing-office-365-endpoints.md) Per un elenco di tutti gli URL e gli indirizzi IP di Office 365 in tutto il mondo, vedere URL e intervalli di [indirizzi IP di Office 365.](urls-and-ip-address-ranges.md)

![Traffico di Microsoft 365 - ottimizzato](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Procedure consigliate per gli utenti

Gli utenti in Cina che si connettono ai tenant globali di Microsoft 365 da posizioni remote come case, bar, hotel e succursali senza connessione alle reti aziendali possono sperimentare prestazioni di rete scarse perché il traffico tra i dispositivi e Microsoft 365 deve transitare nei circuiti di rete transfrontalieri congestionati della Cina.

Se le reti private cross-border e/o l'accesso VPN alla rete aziendale non sono un'opzione, i problemi di prestazioni per utente possono comunque essere attenuati addestrando gli utenti basati sulla Cina a seguire queste procedure consigliate.

- Utilizzare client di Office ricchi che supportano la memorizzazione nella cache (ad esempio Outlook, Teams, OneDrive e così via) ed evitare client basati sul Web. La memorizzazione nella cache dei client di Office e le funzionalità di accesso offline possono ridurre notevolmente l'impatto della congestione e della latenza di rete.
- Se il tenant di Microsoft 365 è stato configurato con la funzionalità _di audioconferenza,_ gli utenti di Teams possono partecipare alle riunioni tramite la rete PSTN (Public Switched Telephone Network). Per ulteriori informazioni, vedere [Audioconferenza in Office 365.](/microsoftteams/audio-conferencing-in-office-365)
- Se gli utenti si verificano problemi di prestazioni di rete, devono segnalare al proprio reparto IT per la risoluzione dei problemi e inoltrare al supporto Tecnico Microsoft se si sospettano problemi con i servizi di Microsoft 365. Non tutti i problemi sono causati dalle prestazioni della rete transfrontaliera.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Ottimizzazione delle prestazioni di rete delle riunioni di Microsoft Teams per gli utenti in Cina  

Per le organizzazioni con tenant globali di Microsoft 365 e presenza in Cina, le prestazioni dei client Microsoft 365 per gli utenti basati sulla Cina possono essere complicate da fattori specifici dell'architettura Internet in Cina. Molte aziende e istituti scolastici hanno riportato buoni risultati seguendo queste indicazioni. Tuttavia, l'ambito è limitato ai percorsi di rete degli utenti che sono sotto il controllo della configurazione di rete IT, ad esempio le posizioni di ufficio o gli endpoint casa/mobile con connettività VPN. Le chiamate e le riunioni di Microsoft Teams vengono spesso utilizzate da posizioni esterne, ad esempio uffici di casa, postazioni mobili, in viaggio e bar. Poiché le chiamate e le riunioni si basano sul traffico multimediale in tempo reale, queste esperienze di Teams sono particolarmente sensibili alla congestione della rete.

Di conseguenza, Microsoft ha collaborato con i provider di telecomunicazioni per supportare il traffico multimediale in tempo reale di Teams e Skype for Business Online utilizzando un percorso di rete preferenziale di qualità superiore tra le connessioni Internet nazionali e pubbliche in Cina e i servizi Teams e Skype nel cloud globale di Microsoft 365. Questa funzionalità ha comportato un miglioramento più di dieci volte della perdita di pacchetti e altre metriche chiave che influiscono sull'esperienza dell'utente.

>[!IMPORTANT]
>Attualmente, questi miglioramenti non affrontano la partecipazione a riunioni di eventi live Microsoft, ad esempio riunioni in stile "municipio" o trasmissione di grandi dimensioni tramite Teams o Microsoft Stream. Per visualizzare una riunione di eventi live, gli utenti in Cina devono utilizzare una rete privata o una soluzione SDWAN/VPN. Tuttavia, i miglioramenti apportati alla rete andranno a vantaggio degli utenti che stanno presentando o producendo una riunione di eventi live, perché tale esperienza funge da normale riunione di Teams per il produttore o il relatore.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Procedure consigliate per la rete dell'organizzazione per le riunioni di Teams

È necessario considerare come sfruttare questi miglioramenti di rete, dato che le indicazioni precedenti per prendere in considerazione un'estensione di rete privata per evitare congestione della rete transfrontaliera. Esistono due opzioni generali per le reti dell'ufficio dell'organizzazione:

1.  Non eseguire alcuna operazione nuova. Continuare a seguire le indicazioni precedenti relative al bypass della rete privata per evitare congestioni transfrontaliere. Il traffico multimediale in tempo reale di Teams si avvale di tale configurazione, come in precedenza.
2.  Implementare un modello split/ibrido. 

  - Usa le indicazioni precedenti per tutto il traffico contrassegnato per l'ottimizzazione ad eccezione delle riunioni di Teams e del traffico multimediale in tempo reale.

  - Instradare le riunioni di Teams e chiamare il traffico multimediale in tempo reale su Internet pubblico. Vedi le informazioni seguenti per informazioni specifiche sull'identificazione del traffico di rete multimediale in tempo reale.

L'invio di traffico audio e video multimediale in tempo reale di Teams su Internet pubblico, che utilizza una connettività di qualità superiore, può comportare notevoli risparmi in termini di costi, perché è gratuito e non pagare per inviare tale traffico su una rete privata. Potrebbero esserci vantaggi aggiuntivi simili se gli utenti usano anche client SDWAN o VPN. Come prassi generale, alcune organizzazioni potrebbero preferire che una maggiore parte dei dati attraversi le connessioni Internet pubbliche.

Le stesse opzioni possono essere applicate alle configurazioni SDWAN o VPN. Ad esempio, un utente utilizza una rete SDWAN o VPN per instradare il traffico di Microsoft 365 alla rete aziendale e quindi sfruttare l'estensione privata di tale rete per evitare congestioni transfrontaliere. La rete SDWAN o VPN dell'utente può ora essere configurata per escludere le riunioni di Teams e il traffico in tempo reale dal routing VPN. Questa configurazione VPN viene definita split tunneling. Per ulteriori informazioni, vedere [Split tunneling VPN per Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel)

Puoi anche continuare a usare SDWAN o VPN per tutto il traffico di Microsoft 365, incluso il traffico in tempo reale di Microsoft Teams. Microsoft non ha suggerimenti sull'uso di soluzioni SDWAN o VPN.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Procedure consigliate per la rete domestica, mobile e utente per le riunioni di Teams

Gli utenti in Cina possono sfruttare questi miglioramenti semplicemente connettendosi al servizio Internet pubblico in Cina con una connessione fissa o mobile. Il traffico audio e video multimediale in tempo reale di Teams su Internet pubblico beneficia direttamente di connettività e qualità migliorate.

Tuttavia, i dati di altri servizi di Microsoft 365 e altro traffico in Teams, ad esempio chat o file, non trarranno direttamente vantaggio da questi miglioramenti. Gli utenti esterni alla rete dell'organizzazione potrebbero comunque avere prestazioni di rete scarse per questo traffico. Come descritto in questo articolo, è possibile attenuare questi effetti utilizzando una VPN o SDWAN. Puoi anche fare in modo che gli utenti usino client desktop rtf su client Web, che supportano la memorizzazione nella cache in-app per ridurre i problemi di rete.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Identificazione del traffico di rete multimediale in tempo reale di Teams

Per configurare un dispositivo di rete o una configurazione VPN/SDWAN, è necessario escludere solo il traffico audio e video multimediale in tempo reale di Teams. I dettagli del traffico sono disponibili per l'ID 11 nell'elenco ufficiale degli URL e degli intervalli di indirizzi IP di [Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) Tutte le altre configurazioni di rete devono rimanere invariate.

Microsoft sta continuamente lavorando per migliorare l'esperienza utente di Microsoft 365 e le prestazioni dei client nella più ampia gamma possibile di architetture e caratteristiche di rete. Visitare office [365 Networking Tech Community]( https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) per avviare o partecipare a una conversazione, trovare risorse e inviare richieste di funzionalità e suggerimenti

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](./network-planning-and-performance.md)

[Principi di connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Rete globale Microsoft](/azure/networking/microsoft-global-network)