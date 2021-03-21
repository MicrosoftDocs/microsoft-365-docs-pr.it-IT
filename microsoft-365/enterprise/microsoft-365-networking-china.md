---
title: Ottimizzazione delle prestazioni del tenant globale di Microsoft 365 per gli utenti della Cina
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
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
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923195"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Ottimizzazione delle prestazioni del tenant globale di Microsoft 365 per gli utenti della Cina

>[!IMPORTANT]
>Queste indicazioni sono specifiche per gli scenari di utilizzo in cui gli utenti di **Microsoft 365** aziendali situati in Cina si connettono a un **tenant globale di Microsoft 365.** Questa guida non **si** applica ai tenant in Office 365 gestito da 21Vianet.

Per le aziende con tenant globali di Microsoft 365 e presenza aziendale in Cina, le prestazioni dei client Microsoft 365 per gli utenti basati sulla Cina possono essere complicate da fattori specifici dell'architettura Internet di China Telco.

Gli ISP della Cina hanno connessioni off-shore regolamentate a Internet pubblico globale che passano attraverso dispositivi perimetrali che sono inclini a livelli elevati di congestione della rete transfrontaliera. Questa congestione crea perdita di pacchetti e latenza per tutto il traffico Internet in ingresso e in uscita dalla Cina.

![Traffico di Microsoft 365 - non definito](../media/O365-networking/China-O365-unoptimized.png)

La perdita e la latenza dei pacchetti è dannosa per le prestazioni dei servizi di rete, in particolare per i servizi che richiedono scambi di dati di grandi dimensioni (ad esempio trasferimenti di file di grandi dimensioni) o che richiedono prestazioni quasi in tempo reale (applicazioni audio e video).

L'obiettivo di questo argomento è fornire le procedure consigliate per ridurre l'impatto della congestione della rete transfrontaliera cinese sui servizi di Microsoft 365. In questo argomento non vengono risolti altri problemi comuni relativi alle prestazioni dell'ultimo miglio, ad esempio problemi di latenza elevata dei pacchetti a causa di instradamento complesso all'interno dei vettori cinesi.

## <a name="corporate-network-best-practices"></a>Procedure consigliate per la rete aziendale

Molte aziende con tenant e utenti di Microsoft 365 globali in Cina hanno implementato reti private che trasportano il traffico di rete aziendale tra sedi di uffici della Cina e sedi off-shore in tutto il mondo. Queste aziende possono sfruttare questa infrastruttura di rete per evitare congestione della rete transfrontaliera e ottimizzare le prestazioni dei servizi di Microsoft 365 in Cina.

>[!IMPORTANT]
>Come per tutte le implementazioni WAN private, è sempre consigliabile consultare i requisiti normativi per il proprio paese e/o area geografica per assicurarsi che la configurazione di rete sia conforme.

Come primo passaggio, è fondamentale seguire le linee guida di rete di riferimento in Pianificazione della rete e ottimizzazione delle prestazioni [per Microsoft 365.](./network-planning-and-performance.md) L'obiettivo principale dovrebbe essere evitare di accedere ai servizi globali di Microsoft 365 da Internet in Cina, se possibile.

- Sfruttare la rete privata esistente per trasportare il traffico di rete di Microsoft 365 tra le reti di uffici della Cina e le posizioni off-shore in uscita su Internet pubblico al di fuori della Cina. Quasi tutte le località al di fuori della Cina offriranno un chiaro vantaggio. Gli amministratori di rete possono ottimizzare ulteriormente l'uscita in aree con interconnessione a bassa latenza con [la rete globale Microsoft.](/azure/networking/microsoft-global-network) Hong Kong, Giappone e Corea del Sud sono esempi.
- Configurare i dispositivi utente per accedere alla rete aziendale tramite una connessione VPN per consentire al traffico di Microsoft 365 di transitare sul collegamento off-shore privato della rete aziendale. Verificare che i client VPN non siano configurati per l'utilizzo del split tunneling o che i dispositivi utente siano configurati per ignorare il split tunneling per il traffico di Microsoft 365.
- Configurare la rete per instradare tutto il traffico di Microsoft 365 attraverso il collegamento off-shore privato. Se è necessario ridurre al minimo il volume di traffico sul collegamento privato, è possibile  scegliere di instradare solo gli endpoint nella categoria **Ottimizza** e consentire alle richieste agli endpoint Allow e **Default** di transitare su Internet. Ciò consente di migliorare le prestazioni e ridurre al minimo il consumo di larghezza di banda limitando il traffico ottimizzato ai servizi critici più sensibili all'elevata latenza e alla perdita di pacchetti.
- Se possibile, utilizzare UDP anziché TCP per il traffico di streaming multimediale live, ad esempio per Teams. UDP offre prestazioni di streaming multimediale live migliori rispetto a TCP.

Per informazioni su come instradare in modo selettivo il traffico di Microsoft 365, vedere [Managing Office 365 endpoints.](managing-office-365-endpoints.md) Per un elenco di tutti gli URL e gli indirizzi IP di Office 365 in tutto il mondo, vedere URL e intervalli di [indirizzi IP di Office 365.](urls-and-ip-address-ranges.md)

![Traffico di Microsoft 365 - ottimizzato](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Procedure consigliate per gli utenti

Gli utenti in Cina che si connettono ai tenant globali di Microsoft 365 da posizioni remote come case, bar, hotel e succursali senza connessione a reti aziendali possono sperimentare prestazioni di rete scarse perché il traffico tra i dispositivi e Microsoft 365 deve transitare nei circuiti di rete transfrontalieri congestionati della Cina.

Se le reti private cross-border e/o l'accesso VPN alla rete aziendale non sono un'opzione, i problemi di prestazioni per utente possono comunque essere attenuati addestrando gli utenti basati sulla Cina a seguire queste procedure consigliate.

- Utilizzare client di Office ricchi che supportano la memorizzazione nella cache (ad esempio Outlook, Teams, OneDrive e così via) ed evitare client basati sul Web. La memorizzazione nella cache dei client di Office e le funzionalità di accesso offline possono ridurre notevolmente l'impatto della congestione e della latenza di rete.
- Se il tenant di Microsoft 365 è stato configurato con la funzionalità _di audioconferenza,_ gli utenti di Teams possono partecipare alle riunioni tramite la rete PSTN (Public Switched Telephone Network). Per ulteriori informazioni, vedere [Audioconferenza in Office 365.](/microsoftteams/audio-conferencing-in-office-365)
- Se gli utenti si verificano problemi di prestazioni di rete, devono segnalare al proprio reparto IT per la risoluzione dei problemi e inoltrare al supporto Tecnico Microsoft se si sospettano problemi con i servizi di Microsoft 365. Non tutti i problemi sono causati dalle prestazioni della rete transfrontaliera.

Microsoft sta continuamente lavorando per migliorare l'esperienza utente di Microsoft 365 e le prestazioni dei client nella più ampia gamma possibile di architetture e caratteristiche di rete. Visitare la [Office 365 Tech Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) per avviare o partecipare a una conversazione, trovare risorse e inviare richieste di funzionalità e suggerimenti.

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](./network-planning-and-performance.md)

[Principi di connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Rete globale Microsoft](/azure/networking/microsoft-global-network)