---
title: Informazioni generali sulla connettività di rete di Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365initiative-CoreDeploy
f1.keywords:
- NOCSH
description: Viene illustrato il motivo per cui l'ottimizzazione della rete è importante per i servizi SaaS, l'obiettivo della rete Microsoft 365 e il modo in cui SaaS richiede una rete diversa da altri carichi di lavoro.
ms.openlocfilehash: acc55868e47ea89cd2357487838a88032dc8538d
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327486"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Panoramica della connettività di rete Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Microsoft 365 è un cloud SaaS (software-as-a-Service) distribuito che offre scenari di produttività e collaborazione tramite una serie diversificata di micro-servizi e applicazioni. I componenti client di Microsoft 365, ad esempio Outlook, Word e PowerPoint, vengono eseguiti sui computer degli utenti e si connettono ad altri componenti di Microsoft 365 eseguiti nei Data Center Microsoft. Il fattore più significativo che determina la qualità dell'esperienza dell'utente finale di Microsoft 365 è l'affidabilità della rete e la bassa latenza tra i client Microsoft 365 e Microsoft 365 Service front doors.

In questo articolo vengono illustrati gli obiettivi della rete Microsoft 365 e perché Microsoft 365 networking richiede un approccio diverso all'ottimizzazione rispetto al traffico Internet generico.

## <a name="microsoft-365-networking-goals"></a>Obiettivi di rete di Microsoft 365

L'obiettivo finale della rete Microsoft 365 è ottimizzare l'esperienza dell'utente finale, consentendo l'accesso meno restrittivo tra i client e gli endpoint Microsoft 365 più vicini. La qualità dell'esperienza dell'utente finale è direttamente correlata alle prestazioni e alla capacità di risposta dell'applicazione che l'utente sta utilizzando. Ad esempio, Microsoft teams si basa su una bassa latenza in modo che le chiamate telefoniche degli utenti, le conferenze e le collaborazioni dello schermo condiviso siano prive di problemi e Outlook si basa su una grande connettività di rete per le funzionalità di ricerca immediata che sfruttano l'indicizzazione sul server e le funzionalità AI.

L'obiettivo principale della progettazione della rete dovrebbe essere quello di ridurre al minimo la latenza riducendo il tempo di andata e ritorno (RTT, Round Trip Time) dai computer client alla rete globale Microsoft, la backbone di rete pubblica di Microsoft che interconnette tutti i datacenter di Microsoft con una bassa latenza, punti di ingresso dell'applicazione cloud a disponibilità elevata sparsi in tutto il mondo. Per altre informazioni sulla rete globale di Microsoft, vedere [Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

L'ottimizzazione delle prestazioni di rete di Microsoft 365 non deve essere complicata. È possibile ottenere le migliori prestazioni possibili seguendo alcuni principi fondamentali:

- Identificare il traffico di rete di Microsoft 365
- Consenti l'uscita di una succursale locale del traffico di rete di Microsoft 365 su Internet da ogni percorso in cui gli utenti si connettono a Microsoft 365
- Consenti al traffico Microsoft 365 di bypassare proxy e dispositivi di ispezione di pacchetti

Per ulteriori informazioni sui principi di connettività di rete di Microsoft 365, vedere [principi di connettività di rete di microsoft 365](microsoft-365-network-connectivity-principles.md).

## <a name="traditional-network-architectures-and-saas"></a>Architetture di rete tradizionali e SaaS

I principi dell'architettura di rete tradizionale per i carichi di lavoro client/server sono stati creati in base all'ipotesi che il traffico tra client e endpoint non si estenda all'esterno del perimetro della rete aziendale. Inoltre, in molte reti aziendali, tutte le connessioni Internet in uscita attraversano la rete aziendale e l'uscita da una posizione centrale.

Nelle architetture di rete tradizionali, la latenza più elevata per il traffico Internet generico è un compromesso necessario per mantenere la sicurezza del perimetro della rete e l'ottimizzazione delle prestazioni per il traffico Internet in genere implica l'aggiornamento o la scalabilità delle apparecchiature nei punti di uscita della rete. Tuttavia, questo approccio non risolve i requisiti per le prestazioni di rete ottimali dei servizi SaaS, come Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identificazione del traffico di rete di Microsoft 365

È più facile identificare il traffico di rete di Microsoft 365 e semplificare la gestione dell'identificazione della rete.

- Nuove categorie di endpoint di rete per differenziare il traffico di rete estremamente critico dal traffico di rete non influenzato dalle latenze Internet. Ci sono solo una manciata di URL e indirizzi IP di supporto nella categoria "optimize" più critica.
- Servizi Web per l'utilizzo di script o la configurazione diretta dei dispositivi e la gestione delle modifiche di Microsoft 365 Network Identification. Le modifiche sono disponibili dal servizio Web o in formato RSS o tramite posta elettronica tramite un modello di flusso Microsoft.
- [Office 365 Network Partner Program](https://aka.ms/Office365NPP) con Microsoft Partners che forniscono dispositivi o servizi che seguono i principi di connettività di rete di Microsoft 365 e dispongono di una configurazione semplice.

## <a name="securing-microsoft-365-connections"></a>Protezione delle connessioni di Microsoft 365

L'obiettivo di una sicurezza di rete tradizionale è rafforzare il perimetro della rete aziendale contro intrusioni ed exploit dannosi. La maggior parte delle reti aziendali impone la sicurezza della rete per il traffico Internet utilizzando tecnologie come server proxy, firewall, Break SSL e controlli, Deep Packet Inspection e sistemi di prevenzione della perdita di dati. Queste tecnologie forniscono importanti riduzioni dei rischi per le richieste Internet generiche, ma consentono di ridurre in modo significativo le prestazioni, la scalabilità e la qualità dell'esperienza utente finale se applicati agli endpoint Microsoft 365.

Microsoft 365 aiuta a soddisfare le esigenze dell'organizzazione per la sicurezza del contenuto e l'utilizzo dei dati per la conformità con le funzionalità di governance e sicurezza incorporate progettate appositamente per le caratteristiche e i carichi di lavoro di Microsoft 365. Per ulteriori informazioni sulla sicurezza e la conformità di Microsoft 365, vedere la Guida di [orientamento alla sicurezza di Office 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap). Per ulteriori informazioni sui consigli e sulla posizione di supporto di Microsoft sulle soluzioni di rete avanzate che eseguono l'elaborazione avanzata su traffico Microsoft 365, vedere [utilizzo di dispositivi di rete o soluzioni di terze parti sul traffico di Office 365](https://support.microsoft.com/help/2690045).

## <a name="why-is-microsoft-365-networking-different"></a>Perché Microsoft 365 è diverso per la rete?

Microsoft 365 è stato creato per garantire prestazioni ottimali mediante endpoint Security e connessioni di rete crittografate, riducendo la necessità di applicare la sicurezza perimetrale. I datacenter Microsoft 365 sono ubicati in tutto il mondo e il servizio è stato creato per l'utilizzo di diversi metodi per connettere i client ai migliori endpoint di servizio disponibili. Poiché i dati e l'elaborazione degli utenti sono distribuiti tra molti datacenter Microsoft, non esiste un singolo endpoint di rete a cui i computer client possono connettersi. Infatti, i dati e i servizi del tenant Microsoft 365 sono ottimizzati dinamicamente dalla rete globale Microsoft per adattarsi ai percorsi geografici da cui sono accessibili dagli utenti finali.

Alcuni problemi comuni relativi alle prestazioni vengono creati quando il traffico di Microsoft 365 è soggetto all'ispezione dei pacchetti e all'uscita centralizzata:

- La latenza elevata può causare prestazioni estremamente scarse di flussi video e audio e una risposta lenta del recupero dei dati, ricerche, collaborazione in tempo reale, informazioni sulla disponibilità del calendario, contenuto del prodotto e altri servizi
- Le connessioni di Egressing da una posizione centrale vanificano le funzionalità di routing dinamico della rete globale di Microsoft 365, l'aggiunta di latenza e il tempo di andata e ritorno
- La decrittografia del traffico di rete di Microsoft 365 protetto da SSL e la ricrittografia può causare errori di protocollo e ha un rischio per la sicurezza

Accorciamento del percorso di rete per i punti di ingresso di Microsoft 365 consentendo al traffico client di essere in uscita il più vicino possibile alla propria posizione geografica, è possibile migliorare le prestazioni di connettività e l'esperienza degli utenti finali in Microsoft 365. Può anche contribuire a ridurre l'impatto delle modifiche future nell'architettura di rete su prestazioni e affidabilità di Microsoft 365. Il modello di connettività ottimale consiste nel fornire sempre l'uscita di rete nella posizione dell'utente, indipendentemente dal fatto che si trovi sulla rete aziendale o su postazioni remote come la casa, gli alberghi, i coffee shop e gli aeroporti. Il traffico generico Internet e la rete aziendale basata su WAN verrebbero instradati separatamente e non utilizzeranno il modello di uscita diretta locale. Il modello di uscita diretta locale è rappresentato nel diagramma seguente.

![Architettura di rete locale di uscita](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

L'architettura di uscita locale presenta i seguenti vantaggi per il traffico di rete di Microsoft 365 sul modello tradizionale:
  
- Garantisce prestazioni ottimali di Microsoft 365 ottimizzando la lunghezza del percorso. Le connessioni degli utenti finali vengono instradate dinamicamente al punto di ingresso Microsoft 365 più vicino dall'infrastruttura del _servizio distribut front_ -end di Microsoft Global Network e il traffico viene quindi instradato internamente a dati e endpoint dei servizi sulla fibra a disponibilità elevata a bassa latenza di Microsoft.
- Riduce il carico dell'infrastruttura di rete aziendale consentendo l'uscita locale per il traffico di Microsoft 365, ignorando i proxy e i dispositivi di ispezione del traffico.
- Consente di proteggere le connessioni su entrambe le estremità sfruttando le funzionalità di sicurezza e sicurezza cloud di endpoint client, evitando l'applicazione di tecnologie di sicurezza di rete ridondanti.

> [!NOTE]
> L'infrastruttura del _servizio Distributed front door_ è il perimetro di rete altamente disponibile e scalabile di Microsoft Global Network con posizioni geograficamente distribuite. Termina le connessioni degli utenti finali e le instrada efficacemente all'interno della rete globale di Microsoft. Per altre informazioni sulla rete globale di Microsoft, vedere [Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Per ulteriori informazioni sulla comprensione e sull'applicazione dei principi di connettività di rete di Microsoft 365, vedere [principi di connettività di rete di microsoft 365](microsoft-365-network-connectivity-principles.md).

## <a name="conclusion"></a>Conclusione

L'ottimizzazione delle prestazioni di rete di Microsoft 365 è una vera e propria eliminazione degli impedimenti inutili. Trattando le connessioni Microsoft 365 come traffico attendibile, è possibile impedire che la latenza venga introdotta dal controllo dei pacchetti e dalla concorrenza per la larghezza di banda del proxy. L'abilitazione delle connessioni locali tra i computer client e gli endpoint di Office 365 consente al traffico di essere instradato dinamicamente tramite la rete globale Microsoft.

## <a name="related-topics"></a>Argomenti correlati

[Principi della connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Servizio Web per URL e indirizzi IP di Office 365](microsoft-365-ip-web-service.md)

[Valutazione della connettività di rete di Microsoft 365](assessing-network-connectivity.md)

[Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](network-planning-and-performance.md)

[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)

[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)

[Reti per la distribuzione di contenuti](content-delivery-networks.md)

[Test di connettività di Microsoft 365](https://aka.ms/netonboard)

[Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog di rete di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
