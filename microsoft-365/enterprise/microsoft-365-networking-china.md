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
- m365initiative-coredeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: Questo articolo fornisce indicazioni per ottimizzare le prestazioni di rete per gli utenti della Cina dei tenant globali di Microsoft 365.
ms.openlocfilehash: 9b397e60b4a3b80563ed31731a6f7aa8e0bdab7f
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456364"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Ottimizzazione delle prestazioni del tenant globale di Microsoft 365 per gli utenti della Cina

>[!IMPORTANT]
>Questa guida è specifica per gli scenari di utilizzo in cui gli utenti di **Microsoft 365** aziendali che si trovano in Cina si connettono a un **tenant globale di Microsoft 365.** Questa guida non **si** applica ai tenant in Office 365 gestito da 21Vianet.

Per le aziende con tenant globali di Microsoft 365 e presenza aziendale in Cina, le prestazioni dei client Microsoft 365 per gli utenti basati sulla Cina possono essere complicate da fattori specifici dell'architettura Internet della Cina Telco.

Gli ISP della Cina dispongono di connessioni internet pubbliche regolamentate a Internet pubblico globale che passano attraverso dispositivi perimetrali che sono inclini a livelli elevati di congestione della rete cross-border. Questa congestione crea perdita di pacchetti e latenza per tutto il traffico Internet in ingresso e in uscita dalla Cina.

![Traffico di Microsoft 365 - non standardizzato](../media/O365-networking/China-O365-unoptimized.png)

La perdita e la latenza dei pacchetti sono dannose per le prestazioni dei servizi di rete, in particolare per i servizi che richiedono scambi di dati di grandi dimensioni (ad esempio trasferimenti di file di grandi dimensioni) o che richiedono prestazioni quasi in tempo reale (applicazioni audio e video).

L'obiettivo di questo argomento è fornire le procedure consigliate per ridurre l'impatto della congestione della rete oltre i confini della Cina sui servizi di Microsoft 365. In questo argomento non vengono risolti altri problemi comuni relativi alle prestazioni dell'ultimo miglio, ad esempio problemi di latenza elevata dei pacchetti a causa di instradamento complesso all'interno dei vettori della Cina.

## <a name="corporate-network-best-practices"></a>Procedure consigliate per la rete aziendale

Molte aziende con tenant e utenti di Microsoft 365 globali in Cina hanno implementato reti private che trasportano il traffico di rete aziendale tra le sedi degli uffici della Cina e le sedi di tutto il mondo. Queste aziende possono sfruttare questa infrastruttura di rete per evitare la congestione della rete oltre i confini e ottimizzare le prestazioni dei servizi di Microsoft 365 in Cina.

>[!IMPORTANT]
>Come per tutte le implementazioni WAN private, è consigliabile consultare sempre i requisiti normativi per il proprio paese e/o area geografica per verificare che la configurazione di rete sia conforme.

Come primo passaggio, è fondamentale seguire le linee guida di rete benchmark in Pianificazione della rete e ottimizzazione delle prestazioni [per Microsoft 365.](https://aka.ms/tune) L'obiettivo principale dovrebbe essere evitare di accedere ai servizi globali di Microsoft 365 da Internet in Cina, se possibile.

- Sfruttare la rete privata esistente per trasportare il traffico di rete di Microsoft 365 tra le reti degli uffici della Cina e le posizioni delle sedi aziendali in uscita su Internet pubblico al di fuori della Cina. Quasi tutte le località al di fuori della Cina offriranno un chiaro vantaggio. Gli amministratori di rete possono ottimizzare ulteriormente l'ambiente in uscita in aree con interconnessione a bassa latenza con [la rete globale Microsoft.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hong Kong, Giappone e Corea del Sud sono esempi.
- Configurare i dispositivi degli utenti per accedere alla rete aziendale tramite una connessione VPN per consentire al traffico di Microsoft 365 di transitare sul collegamento privato della rete aziendale. Verificare che i client VPN non siano configurati per l'uso di split tunneling o che i dispositivi utente siano configurati per ignorare lo split tunneling per il traffico di Microsoft 365.
- Configurare la rete in modo che tutto il traffico di Microsoft 365 sia instradato attraverso il collegamento privato. Se è necessario ridurre al minimo il volume di traffico sul collegamento  privato, è possibile  scegliere di instradare solo gli endpoint nella categoria Ottimizzazione e consentire alle richieste di consentire e agli **endpoint** predefiniti di transitare su Internet. Ciò consente di migliorare le prestazioni e ridurre al minimo il consumo di larghezza di banda limitando il traffico ottimizzato ai servizi critici più sensibili all'elevata latenza e alla perdita di pacchetti.
- Se possibile, usare UDP anziché TCP per il traffico di streaming multimediale live, ad esempio per Teams. UDP offre prestazioni di streaming multimediale live migliori rispetto a TCP.

Per informazioni su come instradare in modo selettivo il traffico di Microsoft 365, vedere [Gestione degli endpoint di Office 365.](managing-office-365-endpoints.md) Per un elenco di tutti gli URL e gli indirizzi IP di Office 365 in tutto il mondo, vedere URL e intervalli [di indirizzi IP di Office 365.](urls-and-ip-address-ranges.md)

![Traffico di Microsoft 365 - ottimizzato](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Procedure consigliate per gli utenti

Gli utenti in Cina che si connettono ai tenant globali di Microsoft 365 da posizioni remote come case, bar, hotel e succursali senza connessione alle reti aziendali possono sperimentare prestazioni di rete scarse, perché il traffico tra i dispositivi e Microsoft 365 deve transitare nei circuiti di rete cross-border congestionati della Cina.

Se le reti private cross-border e/o l'accesso VPN alla rete aziendale non sono un'opzione, è comunque possibile ridurre i problemi di prestazioni per utente formando gli utenti basati sulla Cina a seguire queste procedure consigliate.

- Utilizzare client di Office rtf che supportano la memorizzazione nella cache (ad esempio Outlook, Teams, OneDrive e così via) ed evitare client basati sul Web. La memorizzazione nella cache dei client di Office e le funzionalità di accesso offline possono ridurre notevolmente l'impatto della congestione e della latenza della rete.
- Se il tenant di Microsoft 365 è stato configurato con la funzionalità _di audioconferenza,_ gli utenti di Teams possono partecipare alle riunioni tramite la rete PSTN (Public Switched Telephone Network). Per altre informazioni, vedere [Audioconferenza in Office 365.](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)
- Se si verificano problemi di prestazioni di rete, gli utenti devono segnalare al proprio reparto IT per la risoluzione dei problemi e inoltrare al supporto Tecnico Microsoft se si sospettano problemi con i servizi di Microsoft 365. Non tutti i problemi sono causati dalle prestazioni della rete cross-border.

Microsoft sta lavorando costantemente per migliorare l'esperienza utente di Microsoft 365 e le prestazioni dei client nella più ampia gamma possibile di architetture e caratteristiche di rete. Visitare la [Community tecnica di Office 365](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) per avviare o partecipare a una conversazione, trovare risorse e inviare richieste di funzionalità e suggerimenti.

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](https://aka.ms/tune)

[Principi di connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Rete globale Microsoft](https://docs.microsoft.com/azure/networking/microsoft-global-network)
