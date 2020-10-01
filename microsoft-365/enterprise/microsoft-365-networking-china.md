---
title: Ottimizzazione delle prestazioni di Microsoft 365 Global tenant per gli utenti cinesi
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
- M365initiative-CoreDeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: In questo articolo vengono fornite indicazioni per l'ottimizzazione delle prestazioni di rete per gli utenti cinesi dei tenant globali di Microsoft 365.
ms.openlocfilehash: 1f5f51991c5950d46c9d835a98bea86bcb354366
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327510"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Ottimizzazione delle prestazioni di Microsoft 365 Global tenant per gli utenti cinesi

>[!IMPORTANT]
>Queste linee guida sono specifiche per gli scenari di utilizzo in cui **gli utenti di microsoft 365 dell'organizzazione situati in Cina** si connettono a un **tenant globale di Microsoft 365**. Questa **Guida non è valida per** i tenant di Office 365 gestiti da 21ViaNet.

Per le aziende con tenant globali di Microsoft 365 e una presenza aziendale in Cina, le prestazioni del client Microsoft 365 per gli utenti basati su Cina possono essere complicate da fattori univoci per l'architettura Internet di Telco in Cina.

Gli ISP cinesi hanno regolamentato le connessioni offshore alla rete Internet pubblica globale che passano attraverso dispositivi perimetrali soggetti ad alti livelli di congestione delle reti transfrontaliere. Questa congestione crea la perdita di pacchetti e la latenza per tutto il traffico Internet in entrata e in uscita dalla Cina.

![Traffico Microsoft 365-non ottimizzato](../media/O365-networking/China-O365-unoptimized.png)

La perdita di pacchetti e la latenza sono pregiudizievoli per le prestazioni dei servizi di rete, in particolare i servizi che richiedono scambi di dati di grandi dimensioni (ad esempio, i trasferimenti di file di grandi dimensioni) o che richiedono prestazioni quasi in tempo reale (applicazioni audio e video).

L'obiettivo di questo argomento è fornire procedure consigliate per attenuare l'impatto della congestione della rete transfrontaliera in Cina sui servizi Microsoft 365. In questo argomento non vengono affrontati altri problemi comuni relativi alle prestazioni dell'ultimo chilometro, ad esempio i problemi relativi alla latenza elevata dei pacchetti a causa del routing complesso all'interno di vettori cinesi.

## <a name="corporate-network-best-practices"></a>Procedure consigliate per la rete aziendale

Molte aziende con i tenant e gli utenti globali di Microsoft 365 in Cina hanno implementato reti private che trasportano il traffico di rete aziendale tra le posizioni in Cina e le posizioni offshore in tutto il mondo. Queste aziende possono sfruttare questa infrastruttura di rete per evitare la congestione della rete transfrontaliera e ottimizzare le prestazioni del servizio Microsoft 365 in Cina.

>[!IMPORTANT]
>Come per tutte le implementazioni WAN private, è consigliabile consultare sempre i requisiti normativi per il proprio paese e/o area geografica per garantire che la configurazione di rete sia conforme.

Come primo passaggio, è importante seguire le linee guida di benchmark Network in [Network Planning and Performance Tuning for Microsoft 365](https://aka.ms/tune). L'obiettivo primario dovrebbe essere quello di evitare l'accesso ai servizi globali di Microsoft 365 da Internet in Cina, se possibile.

- Sfruttare la rete privata esistente per portare il traffico di rete di Microsoft 365 tra le reti di Office in Cina e le posizioni offshore che sono in uscita su Internet pubblico esterno alla Cina. Quasi tutte le posizioni fuori dalla Cina forniranno un chiaro vantaggio. Gli amministratori di rete possono ottimizzare ulteriormente egressing in aree con interconnessione a bassa latenza con la [rete globale Microsoft](https://docs.microsoft.com/azure/networking/microsoft-global-network). Alcuni esempi sono Hong Kong, Giappone e Corea del sud.
- Configurare i dispositivi utente per accedere alla rete aziendale tramite una connessione VPN per consentire al traffico Microsoft 365 di transitare sul collegamento offshore privato della rete aziendale. Assicurarsi che i client VPN non siano configurati per l'utilizzo di split tunneling o che i dispositivi utente siano configurati per ignorare il tunneling suddiviso per il traffico di Microsoft 365.
- Configurare la rete per instradare tutto il traffico Microsoft 365 sul collegamento offshore privato. Se è necessario ridurre al minimo il volume del traffico sul collegamento privato, è possibile scegliere di instradare solo gli endpoint nella categoria **optimize** e consentire le richieste di **autorizzazione** e gli endpoint **predefiniti** per transitare su Internet. Ciò consentirà di migliorare le prestazioni e ridurre al minimo il consumo di larghezza di banda limitando il traffico ottimizzato ai servizi critici più sensibili alla latenza elevata e alla perdita di pacchetti.
- Se possibile, utilizzare UDP anziché TCP per il traffico di flussi multimediali in tempo reale, ad esempio per i team. UDP offre prestazioni migliori per il flusso multimediale in tempo reale rispetto a TCP.

Per informazioni su come instradare il traffico Microsoft 365 in modo selettivo, vedere [Managing Office 365 Endpoints](managing-office-365-endpoints.md). Per un elenco di tutti gli indirizzi IP e gli URL di Office 365 in tutto il mondo, vedere [URL e intervalli di indirizzi IP di office 365](urls-and-ip-address-ranges.md).

![Microsoft 365 ottimizzato per il traffico](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Procedure consigliate per gli utenti

Gli utenti in Cina che si connettono a Global Microsoft 365 tenant provenienti da postazioni remote quali case, coffee shop, Hotel e succursali senza alcuna connessione con le reti aziendali possono sperimentare prestazioni di rete insufficienti perché il traffico tra i dispositivi e Microsoft 365 deve transitare nei circuiti di rete transfrontalieri congestionati della Cina.

Se le reti private transfrontaliere e/o l'accesso VPN all'interno della rete aziendale non sono un'opzione, i problemi di prestazioni per utente possono ancora essere attenuati dall'addestramento degli utenti basati su Cina per seguire queste procedure consigliate.

- Utilizzare client di Office ricchi che supportano la memorizzazione nella cache (ad esempio, Outlook, teams, OneDrive e così via) ed evitare client basati sul Web. La memorizzazione nella cache dei client di Office e le funzionalità di accesso offline possono ridurre drasticamente l'impatto della congestione della rete e della latenza.
- Se il tenant Microsoft 365 è stato configurato con la funzionalità _audioconferenza_ , gli utenti possono partecipare alle riunioni tramite la rete PSTN (Public Switched Telephone Network). Per ulteriori informazioni, vedere audioconferenza [in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).
- Se si verificano problemi di prestazioni di rete, è consigliabile riferire al proprio reparto IT per la risoluzione dei problemi e inoltrarsi al supporto tecnico Microsoft se si sospettano problemi con i servizi Microsoft 365. Non tutti i problemi sono causati dalle prestazioni di rete transfrontaliere.

Microsoft sta lavorando continuamente per migliorare l'esperienza utente di Microsoft 365 e le prestazioni dei client sulla più ampia gamma possibile di architetture di rete e caratteristiche. Visitare la [community di Office 365 Tech](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) per avviare o partecipare a una conversazione, trovare risorse e inviare richieste e suggerimenti per le caratteristiche.

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](https://aka.ms/tune)

[Principi di connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Rete globale Microsoft](https://docs.microsoft.com/azure/networking/microsoft-global-network)
