---
title: Microsoft 365 Panoramica della connettività di rete
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
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Vengono illustrati i motivi per cui l'ottimizzazione della rete è importante per i servizi SaaS, l'obiettivo di Microsoft 365 rete e il modo in cui SaaS richiede reti diverse da altri carichi di lavoro.
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923183"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Informazioni generali sulla connettività di rete di Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Microsoft 365 è un cloud SaaS (Software-as-a-Service) distribuito che fornisce scenari di produttività e collaborazione tramite un set diversificato di microservizi e applicazioni. I componenti client di Microsoft 365, ad esempio Outlook, Word e PowerPoint vengono eseguiti nei computer degli utenti e si connettono ad altri componenti di Microsoft 365 che vengono eseguiti nei datacenter Microsoft. Il fattore più significativo che determina la qualità dell'esperienza Microsoft 365'utente finale è l'affidabilità della rete e la bassa latenza tra i client Microsoft 365 e le porte anteriori Microsoft 365 servizio.

In questo articolo vengono spiegati gli obiettivi della rete Microsoft 365 e il motivo per cui la rete Microsoft 365 richiede un approccio di ottimizzazione diverso rispetto al traffico Internet generico.

## <a name="microsoft-365-networking-goals"></a>Microsoft 365 obiettivi di rete

L'obiettivo finale Microsoft 365 rete è ottimizzare l'esperienza utente finale consentendo l'accesso meno restrittivo tra i client e gli endpoint Microsoft 365 più vicini. La qualità dell'esperienza utente finale è direttamente correlata alle prestazioni e alla velocità di risposta dell'applicazione utilizzata dall'utente. Ad esempio, Microsoft Teams si basa su una bassa latenza in modo che le chiamate telefoniche, le conferenze e le collaborazioni sullo schermo condivise degli utenti siano senza problemi e Outlook si basa su una connettività di rete eccezionale per funzionalità di ricerca istantanea che sfruttano l'indicizzazione sul lato server e le funzionalità di IA.

L'obiettivo principale nella progettazione della rete deve essere ridurre al minimo la latenza riducendo il tempo di round trip (RTT) dai computer client a Microsoft Global Network, la backbone di rete pubblica di Microsoft che collega tutti i data center di Microsoft con punti di ingresso di applicazioni cloud a bassa latenza e disponibilità elevata distribuiti in tutto il mondo. Per altre informazioni sulla rete globale di Microsoft, vedere [Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

L'ottimizzazione Microsoft 365 prestazioni di rete non deve essere complicata. È possibile ottenere le migliori prestazioni possibili seguendo alcuni principi chiave:

- Identificare Microsoft 365 traffico di rete
- Consentire l'uscita del ramo locale Microsoft 365 traffico di rete verso Internet da ogni posizione in cui gli utenti si connettono a Microsoft 365
- Consentire Microsoft 365 traffico di ignorare proxy e dispositivi di ispezione dei pacchetti

Per ulteriori informazioni sui principi Microsoft 365 connettività di rete, [vedere Microsoft 365 Principi di connettività di rete](microsoft-365-network-connectivity-principles.md).

## <a name="traditional-network-architectures-and-saas"></a>Architetture di rete tradizionali e SaaS

I principi tradizionali dell'architettura di rete per i carichi di lavoro client/server sono progettati in base al presupposto che il traffico tra client ed endpoint non si estenda al di fuori del perimetro della rete aziendale. Inoltre, in molte reti aziendali, tutte le connessioni Internet in uscita attraversano la rete aziendale ed e uscita da una posizione centrale.

Nelle architetture di rete tradizionali, una latenza maggiore per il traffico Internet generico è un compromesso necessario per mantenere la sicurezza del perimetro di rete e l'ottimizzazione delle prestazioni per il traffico Internet in genere implica l'aggiornamento o la scalabilità orizzontale delle apparecchiature nei punti di uscita della rete. Tuttavia, questo approccio non consente di soddisfare i requisiti per ottenere prestazioni di rete ottimali dei servizi SaaS, ad esempio Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identificazione del Microsoft 365 di rete

Stiamo semplificando l'identificazione Microsoft 365 traffico di rete e semplificando la gestione dell'identificazione di rete.

- Nuove categorie di endpoint di rete per differenziare il traffico di rete altamente critico dal traffico di rete che non è intasato dalle latenze Internet. Esistono solo pochi URL e indirizzi IP di supporto nella categoria "Optimize" più critica.
- Servizi Web per l'utilizzo di script o la configurazione diretta dei dispositivi e la gestione delle modifiche Microsoft 365 di rete. Le modifiche sono disponibili dal servizio Web, in formato RSS o tramite posta elettronica utilizzando un Microsoft Flow predefinito.
- [Office 365 partner network con partner](./microsoft-365-networking-partner-program.md) Microsoft che forniscono dispositivi o servizi che Microsoft 365 principi di connettività di rete e hanno una configurazione semplice.

## <a name="securing-microsoft-365-connections"></a>Protezione di Microsoft 365 connessioni

L'obiettivo di una sicurezza di rete tradizionale è rafforzare il perimetro della rete aziendale contro intrusioni ed exploit dannosi. La maggior parte delle reti aziendali impone la sicurezza di rete per il traffico Internet utilizzando tecnologie come server proxy, firewall, interruzione e ispezione SSL, ispezione approfondita dei pacchetti e sistemi di prevenzione della perdita di dati. Queste tecnologie forniscono importanti riduzioni dei rischi per le richieste Internet generiche, ma consentono di ridurre in modo significativo le prestazioni, la scalabilità e la qualità dell'esperienza utente finale se applicati agli endpoint Microsoft 365.

Microsoft 365 consente di soddisfare le esigenze dell'organizzazione per la sicurezza del contenuto e la conformità all'utilizzo dei dati con funzionalità di governance e sicurezza integrate progettate specificamente per le funzionalità Microsoft 365 e i carichi di lavoro. Per ulteriori informazioni sulla Microsoft 365 sicurezza e conformità, vedere la guida [Office 365 sicurezza.](/office365/securitycompliance/security-roadmap) Per ulteriori informazioni sui suggerimenti di Microsoft e sulla posizione di supporto sulle soluzioni di rete avanzate che eseguono l'elaborazione di livello avanzato sul traffico di Microsoft 365, vedere [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045).

## <a name="why-is-microsoft-365-networking-different"></a>Perché la Microsoft 365 di rete è diversa?

Microsoft 365 è progettato per ottenere prestazioni ottimali utilizzando la sicurezza degli endpoint e le connessioni di rete crittografate, riducendo la necessità di applicazione della sicurezza perimetrale. Microsoft 365 datacenter si trovano in tutto il mondo e il servizio è progettato per utilizzare diversi metodi per la connessione dei client agli endpoint di servizio migliori disponibili. Poiché i dati e l'elaborazione degli utenti vengono distribuiti tra molti datacenter Microsoft, non esiste un singolo endpoint di rete a cui i computer client possono connettersi. Infatti, i dati e i servizi nel tenant di Microsoft 365 sono ottimizzati in modo dinamico da Microsoft Global Network per adattarsi alle posizioni geografiche da cui gli utenti finali a cui sono accessibili.

Alcuni problemi di prestazioni comuni vengono creati quando Microsoft 365 traffico è soggetto all'ispezione dei pacchetti e all'uscita centralizzata:

- Un'elevata latenza può causare prestazioni estremamente scarse dei flussi audio e video e una risposta lenta al recupero dei dati, alle ricerche, alla collaborazione in tempo reale, alle informazioni sulla disponibilità del calendario, al contenuto in-product e ad altri servizi
- L'uscita delle connessioni da una posizione centrale non è più in funzione delle funzionalità di routing dinamico della rete globale Microsoft 365, aggiungendo latenza e tempi di andata e ritorno
- Decrittografare SSL Microsoft 365 traffico di rete e crittografarlo di nuovo può causare errori di protocollo e presenta rischi per la sicurezza

Ridurre il percorso di rete Microsoft 365 punti di ingresso consentendo al traffico client di regredire il più vicino possibile alla propria posizione geografica può migliorare le prestazioni di connettività e l'esperienza dell'utente finale in Microsoft 365. Può anche contribuire a ridurre l'impatto delle modifiche future all'architettura di rete Microsoft 365 prestazioni e affidabilità. Il modello di connettività ottimale è quello di fornire sempre l'uscita di rete nella posizione dell'utente, indipendentemente dal fatto che si tratta della rete aziendale o di posizioni remote come casa, hotel, bar e aeroporti. Il traffico Internet generico e il traffico di rete aziendale basato su WAN vengono instradati separatamente e non utilizzano il modello di uscita diretta locale. Il modello di uscita diretta locale è rappresentato nel diagramma seguente.

![Architettura di rete locale di uscita](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

L'architettura di uscita locale offre i seguenti vantaggi per il traffico di rete di Microsoft 365 rispetto al modello tradizionale:
  
- Garantisce prestazioni ottimali di Microsoft 365 ottimizzando la lunghezza del percorso. Le connessioni degli utenti finali vengono instradati in modo dinamico  al punto di ingresso Microsoft 365 più vicino dall'infrastruttura front-door del servizio distribuito di Microsoft Global Network e il traffico viene quindi instradato internamente agli endpoint di dati e di servizio tramite il fiber a disponibilità elevata a latenza estremamente bassa di Microsoft.
- Riduce il carico sull'infrastruttura di rete aziendale consentendo l'uscita locale per il traffico Microsoft 365, ignorando proxy e dispositivi di ispezione del traffico.
- Protegge le connessioni su entrambe le estremità sfruttando la sicurezza degli endpoint client e le funzionalità di sicurezza cloud, evitando l'applicazione di tecnologie di sicurezza di rete ridondanti.

> [!NOTE]
> _L'infrastruttura Front Door del_ servizio distribuito è il perimetro di rete altamente disponibile e scalabile di Microsoft Global Network con posizioni geograficamente distribuite. Termina le connessioni degli utenti finali e le instrada in modo efficiente all'interno di Microsoft Global Network. Per altre informazioni sulla rete globale di Microsoft, vedere [Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Per ulteriori informazioni sulla comprensione e l'applicazione Microsoft 365 di connettività di rete, [vedere Microsoft 365 Principi di connettività di rete](microsoft-365-network-connectivity-principles.md).

## <a name="conclusion"></a>Conclusione

L'ottimizzazione Microsoft 365 delle prestazioni di rete è realmente la rimozione di impedimenti non necessari. Trattando le Microsoft 365 come traffico attendibile, è possibile impedire che la latenza venga introdotta dall'ispezione dei pacchetti e dalla concorrenza per la larghezza di banda proxy. Se si consentono connessioni locali tra computer client Office 365 endpoint, il traffico può essere instradato in modo dinamico attraverso La rete globale Microsoft.

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