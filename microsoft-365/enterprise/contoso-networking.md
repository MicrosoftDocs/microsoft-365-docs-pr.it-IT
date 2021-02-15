---
title: Servizi di rete per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere l'infrastruttura di rete di Contoso e come l'azienda usa la tecnologia SD-WAN per ottenere prestazioni di rete ottimali per i servizi cloud di Microsoft 365 per le aziende.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754015"
---
# <a name="networking-for-the-contoso-corporation"></a>Servizi di rete per Contoso Corporation

Per adottare un'infrastruttura inclusiva del cloud, Contoso ha ideato un cambiamento fondamentale nel modo in cui viaggia il traffico di rete verso i servizi cloud. Invece di un modello hub e spoke interno che concentra la connettività di rete e il traffico per il livello successivo della gerarchia degli uffici, ha mappato le posizioni degli utenti all'uscita internet locale e le connessioni locali al percorso di rete di Microsoft 365 più vicino su Internet.

## <a name="networking-infrastructure"></a>Infrastruttura di rete

Questi sono gli elementi di rete che collegano gli uffici di Contoso in tutto il mondo:

- Rete WAN MPLS (Multiprotocol Label Switching)

  Una rete WAN MPLS connette la sede di Parigi agli uffici regionali e agli uffici regionali agli uffici satellite in una configurazione spoke-and-hub. La rete consente agli utenti di accedere ai server locali che costituiscono applicazioni line-of-business nella sede di Parigi. Inoltre, instrada qualsiasi traffico Internet generico all'ufficio di Parigi, dove i dispositivi di sicurezza di rete pulino le richieste. All'interno di ogni ufficio, i router recapitare il traffico agli host cablati o ai punti di accesso wireless sulle subnet, che utilizzano lo spazio di indirizzi IP privato.

- Accesso a Internet diretto locale per il traffico di Microsoft 365

  Ogni ufficio dispone di un dispositivo WAN (SD-WAN) software-defined che dispone di uno o più circuiti di rete ISP Internet locali con la propria connettività Internet tramite un server proxy. Questa funzionalità viene in genere implementata come collegamento WAN a un ISP locale che fornisce anche indirizzi IP pubblici e un server DNS locale.

- Presenza Internet

  Contoso è proprietario del nome \. di dominio pubblico contoso com. Il sito Web pubblico di Contoso per ordinare i prodotti è un set di server in un datacenter connesso a Internet nel campus di Parigi. Contoso usa un intervallo di indirizzi IP pubblici /24 su Internet.

La figura 1 mostra l'infrastruttura di rete di Contoso e le relative connessioni a Internet.

![Rete Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
**Figura 1: rete Contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso di SD-WAN per la connettività di rete ottimale a Microsoft

Contoso ha seguito i [principi della connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md) per:

- Identificare e differenziare il traffico di rete di Microsoft 365
- Uscire dalle connessione di rete a livello locale
- Evitare fenomeni di "hairpinning" di rete
- Bypassare i dispositivi di protezione di rete duplicati

Esistono tre categorie di traffico di rete per Microsoft 365: *Ottimizzazione,* *Consenti* e *Predefinito.* Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.

Contoso ha deciso di:

- Usa l'uscita internet diretta per il traffico delle categorie Optimize e Allow e per inoltrare tutto il traffico della categoria Default alla connessione Internet centrale di Parigi.

- Distribuire i dispositivi SD-WAN in ogni ufficio come un modo semplice per seguire questi principi e ottenere prestazioni di rete ottimali per i servizi basati sul cloud di Microsoft 365.

  I dispositivi SD-WAN sono dotati di una porta LAN per la rete di uffici locale e di più porte WAN. Una porta WAN si connette alla rete MPLS. Un altro si connette a un circuito ISP locale. Il dispositivo SD-WAN instrada il traffico di rete delle categorie Optimize e Allow ai collegamenti ISP.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Infrastruttura delle app line-of-business di Contoso

Contoso ha architettato l'infrastruttura Intranet di applicazioni line-of-business e server per gli elementi seguenti:

- Gli uffici secondari si avvalgono dei server di memorizzazione nella cache locale per archiviare documenti con accesso frequente e siti Web interni.
- Gli hub regionali si avvalgono di server applicazioni regionali per gli uffici regionali e quelli secondari. Tali server effettuano la sincronizzazione con i server della sede di Parigi.
- I datacenter del campus di Parigi contengono server applicazioni centralizzati che servono l'intera organizzazione.

Nella figura 2 viene mostrata la percentuale di capacità del traffico di rete utilizzata per l'accesso ai server nella rete Intranet di Contoso.

![Infrastruttura contoso per le applicazioni interne](../media/contoso-networking/contoso-networking-fig2.png)
 
**Figura 2: Infrastruttura di Contoso per le applicazioni interne**

Per gli hub satellite o regionali, il 60% delle risorse necessarie ai dipendenti può essere servito da server di uffici hub satellite e regionali. Il 40% aggiuntivo delle richieste di risorse deve passare attraverso il collegamento WAN al campus di Parigi.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Analisi di rete e preparazione per Microsoft 365 per le aziende

L'adozione corretta dei servizi microsoft 365 per le aziende da parte degli utenti di Contoso dipende dalla connettività a Internet o direttamente ai servizi cloud Microsoft. Contoso ha seguito questi passaggi per pianificare e implementare una connettività ottimizzata ai servizi cloud di Microsoft 365 per le aziende:

1. Creare un diagramma di rete WAN aziendale per facilitare la pianificazione

   Per avviare la pianificazione della rete, Contoso ha creato un diagramma che mostra le posizioni dell'ufficio, la connettività di rete esistente, i dispositivi perimetrali di rete esistenti e le classi di servizio gestite nella rete. Questo diagramma è stato utilizzato per ogni passaggio successivo della pianificazione e dell'implementazione della connettività di rete.

2. Creare un piano per la connettività di rete di Microsoft 365 per le aziende

   Contoso ha usato i principi di connettività di rete di [Microsoft 365](microsoft-365-network-connectivity-principles.md) e le architetture di rete di riferimento di esempio per identificare SD-WAN come topologia preferita per la connettività di Microsoft 365.

3. Analizzare l'utilizzo della connessione Internet e la larghezza di banda MPLS-WAN in ogni ufficio e aumentare la larghezza di banda in base alle esigenze

   L'utilizzo corrente di ogni ufficio è stato analizzato e i circuiti sono stati aumentati in modo che il traffico basato sul cloud di Microsoft 365 previsto funzioni con una capacità inutilizzata media del 20%.

4. Ottimizzare le prestazioni per i servizi di rete Microsoft

   Contoso ha determinato il set di endpoint di Office 365, Intune e Azure e ha configurato firewall, dispositivi di sicurezza e altri sistemi nel percorso Internet per ottenere prestazioni ottimali. Gli endpoint per il traffico della categoria Ottimizzazione e Consenti di Office 365 sono stati configurati nei dispositivi SD-WAN per il routing sul circuito ISP.

5. Configurare dns interno

   Il DNS deve essere funzionale e ricercato localmente per il traffico di Microsoft 365.

6. Convalidare la connettività delle porte e degli endpoint di rete

   Contoso ha eseguito strumenti di test della connettività di rete Microsoft per convalidare la connettività per i servizi cloud di Microsoft 365 per le aziende.

7. Ottimizzare i computer dei dipendenti per la connettività di rete

   I singoli computer sono stati controllati per verificare che siano stati installati gli aggiornamenti più recenti del sistema operativo e che il monitoraggio della sicurezza degli endpoint sia attivo in tutti i client.

## <a name="next-step"></a>Passaggio successivo

Informazioni su come Contoso usa i servizi di dominio [Active Directory locali](contoso-identity.md) nel cloud per i dipendenti e sull'autenticazione federata per clienti e partner commerciali.

## <a name="see-also"></a>Vedere anche

[Roadmap di rete per Microsoft 365](networking-roadmap-microsoft-365.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
