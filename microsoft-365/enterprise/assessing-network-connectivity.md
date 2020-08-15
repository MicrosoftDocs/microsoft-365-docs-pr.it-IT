---
title: Valutazione della connettività di rete di Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 è stato creato per consentire ai clienti di tutto il mondo di connettersi al servizio tramite una connessione Internet. Man mano che il servizio si evolve, la sicurezza, le prestazioni e l'affidabilità di Microsoft 365 sono state migliorate in base ai clienti che utilizzano Internet per stabilire una connessione al servizio.
ms.openlocfilehash: c0bca2f354d71aa2f4f0c2b6fd05cb4786368b43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691348"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Valutazione della connettività di rete di Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Microsoft 365 è stato creato per consentire ai clienti di tutto il mondo di connettersi al servizio tramite una connessione Internet. Man mano che il servizio si evolve, la sicurezza, le prestazioni e l'affidabilità di Microsoft 365 sono state migliorate in base ai clienti che utilizzano Internet per stabilire una connessione al servizio.
  
I clienti che pianificano l'utilizzo di Microsoft 365 devono valutare le esigenze di connettività Internet esistenti e previste come parte del progetto di distribuzione. Per le distribuzioni di classi Enterprise la connettività Internet affidabile e di dimensioni appropriate è una parte importante dell'utilizzo delle funzionalità e degli scenari di Microsoft 365.
  
Le valutazioni di rete possono essere eseguite da molte persone e organizzazioni diverse in base alle dimensioni e alle preferenze. L'ambito di rete della valutazione può anche variare a seconda della posizione del processo di distribuzione. Per ottenere maggiori informazioni sulle operazioni necessarie per eseguire una valutazione della rete, è stata creata una guida di valutazione della rete che consente di comprendere le opzioni disponibili per l'utente. Questa valutazione determinerà i passaggi e le risorse che devono essere aggiunti al progetto di distribuzione per consentire di adottare correttamente Microsoft 365.
  
Una valutazione globale della rete fornirà le possibili soluzioni alle sfide di progettazione della rete insieme ai dettagli sull'implementazione. Alcune valutazioni di rete dimostreranno che la connettività di rete ottimale a Microsoft 365 può essere adattata con modifiche di configurazione o progettazione secondarie all'infrastruttura di rete e di uscita Internet esistente.

Alcune valutazioni indicheranno che la connettività di rete a Microsoft 365 richiederà ulteriori investimenti nei componenti di rete. Ad esempio, le reti aziendali che interessano succursali e più aree geografiche possono richiedere investimenti in soluzioni SD-WAN o infrastruttura di routing ottimizzata per supportare la connettività Internet a Microsoft 365. Ogni tanto una valutazione indicherà che la connettività di rete a Microsoft 365 è influenzata dai requisiti di regolamentazione o prestazioni per scenari come la [qualità multimediale di Skype for business online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917). Questi requisiti aggiuntivi possono comportare investimenti in infrastruttura di connettività Internet, ottimizzazione del routing e connettività diretta specializzata.

Alcune risorse utili per valutare la rete:

- Vedere [microsoft 365 Network Connectivity Overview](microsoft-365-networking-overview.md) per informazioni concettuali sulla rete di Microsoft 365.
- Vedere i [principi di connettività di rete di microsoft 365](https://aka.ms/o365networkingprinciples) per comprendere i principi di connettività per la gestione sicura del traffico di Microsoft 365 e ottenere le migliori prestazioni possibili.
- Iscriversi a [Microsoft FastTrack](https://www.microsoft.com/fasttrack) per assistenza guidata con Microsoft 365 pianificazione, progettazione e distribuzione. 
- Vedere la sezione [test di connettività di microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) seguente per eseguire test di connettività di base che forniscono indicazioni specifiche sui miglioramenti della connettività di rete che possono essere effettuati tra una determinata posizione utente e Microsoft 365.

> [!NOTE]
> È necessaria l'autorizzazione Microsoft per l'utilizzo di ExpressRoute per Office 365. Microsoft esamina tutte le richieste dei clienti e autorizza ExpressRoute per l'utilizzo di Office 365 solo quando il requisito normativo del cliente delega la connettività diretta. Se si dispone di tali requisiti, fornire l'Estratto di testo e il collegamento Web al regolamento che si intende interpretare per indicare che la connettività diretta è necessaria nel [modulo di richiesta di ExpressRoute per Office 365](https://aka.ms/O365ERReview) per avviare una revisione Microsoft. Gli abbonamenti non autorizzati che tentano di creare filtri di route per Office 365 riceveranno un [messaggio di errore](https://support.microsoft.com/kb/3181709).
  
Punti chiave da prendere in considerazione durante la pianificazione della valutazione della rete per Microsoft 365:
  
- Microsoft 365 è un servizio sicuro, affidabile e ad alte prestazioni che viene eseguito su Internet pubblico. Continuiamo a investire per migliorare questi aspetti del servizio. Tutti i servizi Microsoft 365 sono disponibili tramite connettività Internet.

- Vengono continuamente ottimizzati gli aspetti di base di Microsoft 365 quali la disponibilità, la portata globale e le prestazioni per la connettività basata su Internet. Ad esempio, molti servizi Microsoft 365 sfruttano un insieme di nodi perimetrali Internet con espansione. Questa rete Edge offre le migliori caratteristiche di prossimità e prestazioni alle connessioni provenienti da Internet.

- Quando si considera l'utilizzo di Microsoft 365 per uno qualsiasi dei servizi inclusi, ad esempio teams o funzionalità di riunione di Skype for business online, i clienti devono terminare la valutazione della rete finale e soddisfare i requisiti di connettività con [Microsoft FastTrack](https://www.microsoft.com/fasttrack).

Se si sta valutando Microsoft 365 e non si è certi di dove iniziare con la valutazione della rete o si sono verificati problemi di progettazione della rete per i quali è necessario un intervento di assistenza da superare, è possibile collaborare con il team dell'account Microsoft.

## <a name="the-microsoft-365-connectivity-test"></a>Test di connettività di Microsoft 365

Il [test di connettività microsoft 365](https://aka.ms/netonboard) è uno strumento di valutazione della rete di prova (POC) che esegue i test di connettività di base sul tenant di Microsoft 365 e apporta indicazioni specifiche sulla progettazione della rete per ottenere prestazioni ottimali di Microsoft 365. Lo strumento evidenzia le scelte di progettazione del perimetro della rete aziendale di grandi dimensioni utili per la Web Browsing Internet, ma ha un impatto sulle prestazioni di applicazioni SaaS di grandi dimensioni, ad esempio Microsoft 365.

Lo strumento di onboarding di rete esegue le operazioni seguenti:

- Rileva la posizione oppure è possibile specificare una posizione in cui eseguire il test
- Verifica la posizione dell'uscita di rete
- Verifica il percorso di rete per il porta anteriore del servizio Microsoft 365 più vicino
- Fornisce test avanzati tramite un'applicazione scaricabile di Windows 10 che rende le indicazioni relative alla progettazione della rete perimetrale correlate ai server proxy, ai firewall e al DNS. Lo strumento esegue anche test delle prestazioni per Skype for business online, Microsoft teams, SharePoint Online e Exchange Online.

Lo strumento dispone di due componenti: un'interfaccia utente basata su browser che raccoglie informazioni di connettività di base e un'applicazione di Windows 10 scaricabile che esegue test avanzati e restituisce ulteriori dati di valutazione.

Lo strumento basato su browser Visualizza le informazioni seguenti:

- Scheda risultati e impatto
  - La posizione in una mappa della porta di ingresso del servizio in uso
  - La posizione in una mappa di altre porte anteriori del servizio che forniscono una connettività ottimale
  - Prestazioni relative rispetto ad altri clienti di Microsoft 365 vicino a te
- Scheda dettagli e soluzioni
  - Posizione dell'utente in base alla città e al paese
  - Posizione di uscita di rete per città, stato e paese
  - Utente per la distanza di uscita dalla rete
  - Posizione della porta anteriore del servizio Microsoft 365 Exchange Online
  - Optimal Microsoft 365 Exchange Online Service porta anteriore (s) per la posizione dell'utente
  - Clienti nell'area metropolitana con prestazioni migliori

L'applicazione scaricabile test avanzati fornisce le seguenti informazioni aggiuntive:

- Scheda dettagli e soluzioni (aggiunta)
  - Gateway predefinito dell'utente
  - Server DNS client
  - Resolver ricorsivo DNS client
  - Server DNS Exchange Online
  - Server DNS di SharePoint Online
  - Identificazione del server proxy
  - Verifica della connettività multimediale
  - Perdita di pacchetti di qualità multimediale
  - Latenza qualità multimediale
  - Instabilità della qualità multimediale
  - Riordino dei pacchetti di qualità multimediale
- Test di connettività a più endpoint specifici delle funzionalità
- Diagnostica percorso di rete che include i dati di tracert e latenza per i servizi di Exchange Online, SharePoint Online e teams

È possibile leggere informazioni sul test di connettività di Microsoft 365 e fornire commenti e suggerimenti all' [aggiornamento di microsoft 365 Connectivity test POC with New Network Design raccomandazioni](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) post del Blog. Informazioni sugli aggiornamenti futuri di questo strumento e di altri aggiornamenti di rete di Microsoft 365 verranno inviati al Blog di [rete di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) .
  
Ecco un breve collegamento che è possibile utilizzare per tornare: [ https://aka.ms/o365networkconnectivity .](https://aka.ms/o365networkconnectivity)
  
## <a name="related-topics"></a>Argomenti correlati

[Informazioni generali sulla connettività di rete di Microsoft 365](microsoft-365-networking-overview.md)

[Principi della connettività di rete di Microsoft 365](https://aka.ms/o365networkingprinciples)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Servizio Web per URL e indirizzi IP di Office 365](microsoft-365-ip-web-service.md)

[Ottimizzazione della rete e delle prestazioni di Microsoft 365](network-planning-and-performance.md)

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
