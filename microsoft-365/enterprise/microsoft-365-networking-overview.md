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
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Illustra perché l'ottimizzazione della rete è importante per i servizi SaaS, l'obiettivo della rete di Microsoft 365 e come SaaS richiede reti diverse da altri carichi di lavoro.
ms.openlocfilehash: 50137e507021a6b6d26468a8a299c35a613a065a
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456400"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Panoramica della connettività di rete di Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Microsoft 365 è un cloud SaaS (Software-as-a-Service) distribuito che offre scenari di produttività e collaborazione attraverso un set di micro servizi e applicazioni diversi. I componenti client di Microsoft 365, ad esempio Outlook, Word e PowerPoint, vengono eseguiti nei computer degli utenti e si connettono ad altri componenti di Microsoft 365 eseguiti nei datacenter Microsoft. Il fattore più significativo che determina la qualità dell'esperienza utente finale di Microsoft 365 è l'affidabilità della rete e la bassa latenza tra i client Microsoft 365 e le porte anteriori dei servizi di Microsoft 365.

In questo articolo vengono spiegati gli obiettivi della rete di Microsoft 365 e il motivo per cui la rete di Microsoft 365 richiede un approccio diverso all'ottimizzazione rispetto al traffico Internet generico.

## <a name="microsoft-365-networking-goals"></a>Obiettivi di rete di Microsoft 365

L'obiettivo finale della rete di Microsoft 365 è ottimizzare l'esperienza dell'utente finale abilitando l'accesso meno restrittivo tra i client e gli endpoint di Microsoft 365 più vicini. La qualità dell'esperienza utente finale è direttamente correlata alle prestazioni e alla velocità di risposta dell'applicazione utilizzata dall'utente. Ad esempio, Microsoft Teams si basa su una bassa latenza in modo che le chiamate telefoniche, le conferenze e le collaborazioni su schermo condivise degli utenti siano senza problemi e Outlook si basa su una connettività di rete eccezionale per funzionalità di ricerca immediata che sfruttano l'indicizzazione sul lato server e le funzionalità di intelligenza artificiale.

L'obiettivo principale nella progettazione della rete dovrebbe essere ridurre al minimo la latenza riducendo il tempo di andata e ritorno (RTT) dai computer client alla rete globale Microsoft, la backbone di rete pubblica di Microsoft che interconnette tutti i datacenter di Microsoft con punti di ingresso di applicazioni cloud a bassa latenza e disponibilità elevata distribuiti in tutto il mondo. Per altre informazioni sulla rete globale di Microsoft, vedere [Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

L'ottimizzazione delle prestazioni di rete di Microsoft 365 non deve essere complicata. È possibile ottenere le migliori prestazioni possibili seguendo alcuni principi chiave:

- Identificare il traffico di rete di Microsoft 365
- Consentire l'uscita succursale locale del traffico di rete di Microsoft 365 verso Internet da ogni posizione in cui gli utenti si connettono a Microsoft 365
- Consentire al traffico di Microsoft 365 di ignorare proxy e dispositivi di ispezione dei pacchetti

Per ulteriori informazioni sui principi di connettività di rete di Microsoft 365, vedere Principi di connettività di [rete di Microsoft 365.](microsoft-365-network-connectivity-principles.md)

## <a name="traditional-network-architectures-and-saas"></a>Architetture di rete tradizionali e SaaS

I principi tradizionali dell'architettura di rete per i carichi di lavoro client/server sono progettati in base al presupposto che il traffico tra client ed endpoint non si estenda all'esterno del perimetro della rete aziendale. Inoltre, in molte reti aziendali tutte le connessioni Internet in uscita attraversano la rete aziendale ed e uscita da una posizione centrale.

Nelle architetture di rete tradizionali, una latenza maggiore per il traffico Internet generico è un compromesso necessario per mantenere la sicurezza perimetrale di rete e l'ottimizzazione delle prestazioni per il traffico Internet implica in genere l'aggiornamento o la scalabilità orizzontale delle apparecchiature nei punti di uscita della rete. Tuttavia, questo approccio non consente di soddisfare i requisiti per ottenere prestazioni di rete ottimali dei servizi SaaS come Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identificazione del traffico di rete di Microsoft 365

Stiamo semplificando l'identificazione del traffico di rete di Microsoft 365 e la gestione dell'identificazione della rete.

- Nuove categorie di endpoint di rete per distinguere il traffico di rete altamente critico dal traffico di rete che non è inciso dalle latenze di Internet. Esistono solo pochi URL e indirizzi IP di supporto nella categoria "Ottimizzazione" più critica.
- Servizi Web per l'utilizzo di script o la configurazione diretta dei dispositivi e la gestione delle modifiche dell'identificazione di rete di Microsoft 365. Le modifiche sono disponibili dal servizio Web, in formato RSS o tramite posta elettronica tramite un modello di Microsoft Flow.
- Programma partner Di rete di [Office 365](https://aka.ms/Office365NPP) con partner Microsoft che forniscono dispositivi o servizi che seguono i principi di connettività di rete di Microsoft 365 e hanno una configurazione semplice.

## <a name="securing-microsoft-365-connections"></a>Protezione delle connessioni di Microsoft 365

L'obiettivo di una sicurezza di rete tradizionale è rafforzare il perimetro della rete aziendale contro intrusioni ed exploit dannosi. La maggior parte delle reti aziendali applica la sicurezza di rete per il traffico Internet utilizzando tecnologie come server proxy, firewall, ssl break and inspect, ispezione approfondita dei pacchetti e sistemi di prevenzione della perdita dei dati. Queste tecnologie forniscono importanti riduzioni dei rischi per le richieste Internet generiche, ma consentono di ridurre in modo significativo le prestazioni, la scalabilità e la qualità dell'esperienza utente finale se applicati agli endpoint Microsoft 365.

Microsoft 365 consente di soddisfare le esigenze dell'organizzazione per la sicurezza dei contenuti e la conformità all'utilizzo dei dati con le funzionalità di sicurezza e governance integrate progettate appositamente per le funzionalità e i carichi di lavoro di Microsoft 365. Per ulteriori informazioni sulla sicurezza e la conformità di Microsoft 365, vedere la roadmap sulla sicurezza di [Office 365.](https://docs.microsoft.com/office365/securitycompliance/security-roadmap) Per ulteriori informazioni sulle raccomandazioni di Microsoft e sulla posizione di supporto sulle soluzioni di rete avanzate che eseguono l'elaborazione di livello avanzato sul traffico di Microsoft 365, vedere Uso di dispositivi di rete di terze parti o soluzioni nel traffico di [Office 365.](https://support.microsoft.com/help/2690045)

## <a name="why-is-microsoft-365-networking-different"></a>Perché la rete di Microsoft 365 è diversa?

Microsoft 365 è progettato per ottenere prestazioni ottimali utilizzando la sicurezza degli endpoint e le connessioni di rete crittografate, riducendo la necessità di applicare la sicurezza perimetrale. I data center di Microsoft 365 si trovano in tutto il mondo e il servizio è progettato per usare diversi metodi per la connessione dei client agli endpoint di servizio migliori disponibili. Poiché i dati utente e l'elaborazione vengono distribuiti tra molti datacenter Microsoft, non esiste un singolo endpoint di rete a cui i computer client possono connettersi. Infatti, i dati e i servizi nel tenant di Microsoft 365 sono ottimizzati dinamicamente da Microsoft Global Network per adattarsi alle posizioni geografiche da cui gli utenti finali a cui hanno accesso.

Alcuni problemi di prestazioni comuni vengono creati quando il traffico di Microsoft 365 è soggetto all'ispezione dei pacchetti e all'uscita centralizzata:

- Un'elevata latenza può causare prestazioni estremamente scarse dei flussi video e audio e una risposta lenta al recupero dei dati, alle ricerche, alla collaborazione in tempo reale, alle informazioni sulla disponibilità del calendario, al contenuto nel prodotto e ad altri servizi
- L'uscita delle connessioni da una posizione centrale sconfie le funzionalità di routing dinamico della rete globale di Microsoft 365, aggiungendo latenza e tempo di andata e ritorno
- Decrittografare il traffico di rete di Microsoft 365 protetto da SSL e crittografarlo di nuovo può causare errori di protocollo e presenta rischi per la sicurezza

Ridurre il percorso di rete ai punti di ingresso di Microsoft 365 consentendo l'uscita del traffico client il più vicino possibile alla posizione geografica può migliorare le prestazioni di connettività e l'esperienza dell'utente finale in Microsoft 365. Può anche contribuire a ridurre l'impatto delle modifiche future all'architettura di rete sulle prestazioni e l'affidabilità di Microsoft 365. Il modello di connettività ottimale è quello di fornire sempre l'uscita di rete nella posizione dell'utente, indipendentemente dal fatto che si trova nella rete aziendale o in posizioni remote come casa, hotel, bar e aeroporti. Il traffico Internet generico e il traffico di rete aziendale basato su WAN vengono instradati separatamente e non utilizzano il modello di uscita diretta locale. Il modello di uscita diretta locale è rappresentato nel diagramma seguente.

![Architettura di rete locale di uscita](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

L'architettura di uscita locale offre i vantaggi seguenti per il traffico di rete di Microsoft 365 rispetto al modello tradizionale:
  
- Garantisce prestazioni ottimali di Microsoft 365 ottimizzando la lunghezza del percorso. Le connessioni degli utenti finali vengono instradati in modo dinamico al  punto di ingresso di Microsoft 365 più vicino tramite l'infrastruttura front door del servizio distribuito della rete globale Microsoft e il traffico viene quindi instradato internamente agli endpoint dei dati e dei servizi tramite il fiber ad alta disponibilità a latenza estremamente bassa di Microsoft.
- Riduce il carico sull'infrastruttura di rete aziendale consentendo l'uscita locale per il traffico di Microsoft 365, ignorando proxy e dispositivi di ispezione del traffico.
- Protegge le connessioni su entrambe le estremità sfruttando le funzionalità di sicurezza degli endpoint client e cloud, evitando l'applicazione di tecnologie di sicurezza di rete ridondanti.

> [!NOTE]
> _L'infrastruttura Front Door_ del servizio distribuito è il perimetro di rete a disponibilità elevata e scalabile della rete globale microsoft con posizioni geograficamente distribuite. Termina le connessioni degli utenti finali e le instrada in modo efficiente all'interno della rete globale Microsoft. Per altre informazioni sulla rete globale di Microsoft, vedere [Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Per ulteriori informazioni sulla comprensione e l'applicazione dei principi di connettività di rete di Microsoft 365, vedere Principi di connettività di rete [di Microsoft 365.](microsoft-365-network-connectivity-principles.md)

## <a name="conclusion"></a>Conclusione

L'ottimizzazione delle prestazioni di rete di Microsoft 365 è una rimozione di impedimenti superflui. Trattando le connessioni di Microsoft 365 come traffico attendibile, è possibile impedire che la latenza venga introdotta dall'ispezione dei pacchetti e dalla concorrenza per la larghezza di banda del proxy. Consentire connessioni locali tra i computer client e gli endpoint di Office 365 consente di instradare dinamicamente il traffico attraverso la rete globale Microsoft.

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
