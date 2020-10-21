---
title: Servizi di rete per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere l'infrastruttura di rete di Contoso e come la società utilizza la tecnologia SD-WAN per garantire prestazioni di rete ottimali a Microsoft 365 per i servizi cloud aziendali.
ms.openlocfilehash: ca673e6dcbf0f3db4bde33d388598e5f4ffac914
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637188"
---
# <a name="networking-for-the-contoso-corporation"></a>Servizi di rete per Contoso Corporation

Per adottare un'infrastruttura cloud-inclusive, Contoso ha messo a punto un passaggio fondamentale per la modalità di spostamento del traffico di rete verso i servizi cloud. Invece di un modello hub-and-spoke interno che concentra la connettività di rete e il traffico per il livello successivo della gerarchia di Office, sono state mappate le posizioni degli utenti all'uscita Internet locale e alle connessioni locali al percorso di rete Microsoft 365 più vicino su Internet.

## <a name="networking-infrastructure"></a>Infrastruttura di rete

Questi sono gli elementi di rete che collegano gli uffici di Contoso in tutto il mondo:

- Rete WAN MPLS (Multiprotocol Label Switching)

  Una rete WAN MPLS connette la sede di Parigi agli uffici regionali e alle sedi regionali agli uffici satellite in una configurazione a raggio e Hub. La rete consente agli utenti di accedere a server locali che compongono applicazioni line-of-business nella sede di Parigi. Inoltre, consente di instradare qualsiasi traffico Internet generico all'ufficio di Parigi, dove i dispositivi di sicurezza di rete scrub le richieste. All'interno di ogni ufficio, i router offrono traffico a host cablati o a punti di accesso wireless sulle subnet, che utilizzano lo spazio di indirizzi IP privato.

- Accesso Internet diretto locale per il traffico Microsoft 365

  Ogni ufficio ha un dispositivo WAN (SD-WAN) definito dal software che dispone di uno o più circuiti di rete Internet ISP locali con la propria connettività Internet tramite un server proxy. Questo è in genere implementato come un collegamento WAN a un ISP locale che fornisce anche indirizzi IP pubblici e un server DNS locale.

- Presenza Internet

  Contoso possiede il \. nome di dominio pubblico contoso com. Il sito Web pubblico contoso per l'ordinamento dei prodotti è un set di server in un datacenter connesso a Internet nel campus di Parigi. Contoso utilizza l'intervallo di indirizzi IP pubblici a/24 su Internet.

Nella figura 1 viene illustrata l'infrastruttura di rete Contoso e le relative connessioni a Internet.

![La rete contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
**Figura 1: la rete contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso di SD-WAN per la connettività di rete ottimale a Microsoft

Contoso ha seguito i [principi della connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md) per:

- Identificare e differenziare il traffico di rete di Microsoft 365
- Uscire dalle connessione di rete a livello locale
- Evitare fenomeni di "hairpinning" di rete
- Bypassare i dispositivi di protezione di rete duplicati

Esistono tre categorie di traffico di rete per Microsoft 365: *optimize*, *Allow*e *default*. Ottimizzare e consentire il traffico è il traffico di rete attendibile crittografato e protetto negli endpoint ed è destinato alla rete Microsoft 365.

Contoso ha deciso di:

- Utilizzare l'uscita Internet diretta per ottimizzare e consentire il traffico delle categorie e inoltrare tutto il traffico di categoria predefinito alla connessione Internet centralizzata basata su Parigi.

- Distribuire i dispositivi SD-WAN in ogni ufficio come un modo semplice per seguire questi principi e ottenere prestazioni di rete ottimali per i servizi basati su cloud di Microsoft 365.

  I dispositivi SD-WAN sono dotati di una porta LAN per la rete di uffici locale e di più porte WAN. Una porta WAN si connette alla rete MPLS. Un altro si connette a un circuito ISP locale. Il dispositivo SD-WAN instrada il traffico di rete delle categorie Optimize e Allow ai collegamenti ISP.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>L'infrastruttura delle app line-of-business di contoso

Contoso ha architettato l'infrastruttura Intranet del server e dell'applicazione line-of-business per gli elementi seguenti:

- Gli uffici secondari si avvalgono dei server di memorizzazione nella cache locale per archiviare documenti con accesso frequente e siti Web interni.
- Gli hub regionali si avvalgono di server applicazioni regionali per gli uffici regionali e quelli secondari. Tali server effettuano la sincronizzazione con i server della sede di Parigi.
- I centri dati di Paris Campus contengono server applicazioni centralizzati che servono l'intera organizzazione.

Nella figura 2 viene illustrata la percentuale di capacità del traffico di rete utilizzata per l'accesso ai server nell'Intranet contoso.

![L'infrastruttura di Contoso per applicazioni interne](../media/contoso-networking/contoso-networking-fig2.png)
 
**Figura 2: infrastruttura di Contoso per applicazioni interne**

Per le sedi degli hub satellite o regionale, il 60% delle risorse necessarie per i dipendenti può essere utilizzato dai server di Office Hub satellite e Regional. L'ulteriore 40% delle richieste di risorse deve superare il collegamento WAN al campus di Parigi.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Analisi di rete e preparazione per Microsoft 365 per Enterprise

L'adozione corretta di Microsoft 365 per i servizi Enterprise da parte degli utenti di Contoso dipende da una connettività estremamente disponibile e performante a Internet o direttamente ai servizi cloud Microsoft. Contoso ha eseguito questa procedura per pianificare e implementare la connettività ottimizzata a Microsoft 365 per i servizi cloud aziendali:

1. Creare un diagramma della rete WAN aziendale per agevolare la pianificazione

   Per avviare la pianificazione della rete, Contoso ha creato un diagramma che mostra le posizioni di Office, la connettività di rete esistente, i dispositivi perimetrali di rete esistenti e le classi di servizi gestiti sulla rete. Questo diagramma è stato utilizzato per ogni passaggio successivo nella pianificazione e nell'implementazione della connettività di rete.

2. Creare un piano per Microsoft 365 per la connettività di rete aziendale

   Contoso ha usato i [principi di connettività di rete di microsoft 365](microsoft-365-network-connectivity-principles.md) e le architetture di rete di riferimento di esempio per identificare SD-WAN come topologia preferita per la connettività di Microsoft 365.

3. Analizzare l'utilizzo della connessione Internet e la larghezza di banda della rete WAN MPLS in ogni ufficio e aumentare la larghezza di banda in base alle esigenze

   Ogni utilizzo corrente di Office è stato analizzato e i circuiti sono stati aumentati in modo che il traffico basato sul cloud previsto per Microsoft 365 funzionerebbe con una media della capacità inutilizzata del 20%.

4. Ottimizzare le prestazioni per i servizi di rete Microsoft

   Contoso ha determinato l'insieme degli endpoint di Office 365, Intune e Azure e dei firewall configurati, dei dispositivi di sicurezza e di altri sistemi nel percorso Internet per ottenere prestazioni ottimali. Gli endpoint per il traffico di categoria di Office 365 optimize and allow sono stati configurati nei dispositivi SD-WAN per il routing sul circuito dell'ISP.

5. Configurare il DNS interno

   Il DNS deve essere funzionale e ricercato localmente per il traffico di Microsoft 365.

6. Convalidare l'endpoint di rete e la connettività delle porte

   Contoso ha eseguito strumenti di test della connettività di rete Microsoft per convalidare la connettività per Microsoft 365 per i servizi cloud aziendali.

7. Ottimizzare i computer dei dipendenti per la connettività di rete

   Sono stati controllati singoli computer per garantire che gli aggiornamenti del sistema operativo più recenti siano stati installati e che il monitoraggio della sicurezza di endpoint fosse attivo su tutti i client.

## <a name="next-step"></a>Passaggio successivo

[Informazioni su](contoso-identity.md) come Contoso si avvale di Active Directory Domain Services (AD DS) locale nel cloud per i dipendenti dell'autenticazione federata per clienti e partner commerciali.

## <a name="see-also"></a>Vedere anche

[Roadmap di rete per Microsoft 365](networking-roadmap-microsoft-365.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
