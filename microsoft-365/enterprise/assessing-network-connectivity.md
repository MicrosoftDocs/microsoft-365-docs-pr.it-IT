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
description: Microsoft 365 è progettato per consentire ai clienti di tutto il mondo di connettersi al servizio tramite una connessione Internet. Con l'evolversi del servizio, la sicurezza, le prestazioni e l'affidabilità di Microsoft 365 vengono migliorate in base ai clienti che utilizzano Internet per stabilire una connessione al servizio.
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905477"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Valutazione della connettività di rete di Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Microsoft 365 è progettato per consentire ai clienti di tutto il mondo di connettersi al servizio tramite una connessione Internet. Con l'evolversi del servizio, la sicurezza, le prestazioni e l'affidabilità di Microsoft 365 vengono migliorate in base ai clienti che utilizzano Internet per stabilire una connessione al servizio.
  
I clienti che pianificano di utilizzare Microsoft 365 devono valutare le esigenze di connettività Internet esistenti e previste come parte del progetto di distribuzione. Per le distribuzioni di classe enterprise la connettività Internet affidabile e di dimensioni appropriate è una parte fondamentale dell'utilizzo delle funzionalità e degli scenari di Microsoft 365.
  
Le valutazioni di rete possono essere eseguite da molte persone e organizzazioni diverse a seconda delle dimensioni e delle preferenze. L'ambito di rete della valutazione può anche variare a seconda di dove ci si trova nel processo di distribuzione. Per aiutarti a comprendere meglio cosa serve per eseguire una valutazione della rete, abbiamo prodotto una guida alla valutazione della rete per aiutarti a comprendere le opzioni disponibili. Questa valutazione determinerà quali passaggi e risorse devono essere aggiunti al progetto di distribuzione per consentire l'adozione corretta di Microsoft 365.
  
Una valutazione completa della rete fornirà le possibili soluzioni alle sfide di progettazione della rete insieme ai dettagli dell'implementazione. Alcune valutazioni di rete mostreranno che la connettività di rete ottimale a Microsoft 365 può essere ospitata con modifiche di configurazione o progettazione minori all'infrastruttura di rete esistente e in uscita da Internet.

Alcune valutazioni indicherà che la connettività di rete a Microsoft 365 richiederà ulteriori investimenti nei componenti di rete. Ad esempio, le reti aziendali che si estendono su succursale e più aree geografiche potrebbero richiedere investimenti in soluzioni SD-WAN o infrastrutture di routing ottimizzate per supportare la connettività Internet a Microsoft 365. Occasionalmente una valutazione indicherà che la connettività di rete a Microsoft 365 è influenzata da requisiti di regolazione o prestazioni per scenari come la qualità multimediale di [Skype for Business online.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Questi requisiti aggiuntivi possono comportare investimenti nell'infrastruttura di connettività Internet, nell'ottimizzazione del routing e nella connettività diretta specializzata.

Alcune risorse per valutare la rete:

- Per informazioni concettuali sulla rete [di Microsoft 365,](microsoft-365-networking-overview.md) vedere Panoramica della connettività di rete di Microsoft 365.
- Vedere Principi di connettività di rete di [Microsoft 365](./microsoft-365-network-connectivity-principles.md) per comprendere i principi di connettività per gestire in modo sicuro il traffico di Microsoft 365 e ottenere le migliori prestazioni possibili.
- Iscriversi a [Microsoft FastTrack per](https://www.microsoft.com/fasttrack) assistenza guidata nella pianificazione, progettazione e distribuzione di Microsoft 365. 
- Vedere la sezione test di connettività di [Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) riportata di seguito per eseguire test di connettività di base che forniscono indicazioni specifiche sui miglioramenti della connettività di rete che possono essere apportati tra una determinata posizione utente e Microsoft 365.

> [!NOTE]
> L'autorizzazione Microsoft è necessaria per usare ExpressRoute per Office 365. Microsoft esamina ogni richiesta del cliente e autorizza ExpressRoute solo per l'utilizzo di Office 365 quando il requisito normativo di un cliente impone la connettività diretta. Se si dispone di tali requisiti, fornire l'estratto di testo e il collegamento Web al regolamento che si interpreta per indicare che la connettività diretta è necessaria nel modulo di richiesta [ExpressRoute per Office 365](https://aka.ms/O365ERReview) per avviare una revisione Microsoft. Le sottoscrizioni non autorizzate che tentano di creare filtri di route per Office 365 riceveranno un [messaggio di errore.](https://support.microsoft.com/kb/3181709)
  
Punti chiave da considerare quando si pianifica la valutazione della rete per Microsoft 365:
  
- Microsoft 365 è un servizio sicuro, affidabile e ad alte prestazioni che viene eseguito su Internet pubblico. Continuiamo a investire per migliorare questi aspetti del servizio. Tutti i servizi di Microsoft 365 sono disponibili tramite connettività Internet.

- Microsoft ottimizza costantemente aspetti di base di Microsoft 365, ad esempio disponibilità, copertura globale e prestazioni per la connettività basata su Internet. Ad esempio, molti servizi di Microsoft 365 sfruttano un set in espansione di nodi perimetrali rivolti a Internet. Questa rete perimetrale offre la migliore prossimità e prestazioni alle connessioni provenienti da Internet.

- Quando si valuta l'uso di Microsoft 365 per uno qualsiasi dei servizi inclusi, ad esempio Teams o Skype for Business Online, funzionalità vocali, video o riunioni, i clienti devono completare una valutazione end-to-end della rete e soddisfare i requisiti di connettività con [Microsoft FastTrack.](https://www.microsoft.com/fasttrack)

Se stai valutando Microsoft 365 e non sai da dove iniziare con la valutazione della rete o hai riscontrato problemi di progettazione della rete da superare, contatta il team dell'account Microsoft.

## <a name="the-microsoft-365-connectivity-test"></a>Test di connettività di Microsoft 365

Il test di connettività di [Microsoft 365](https://aka.ms/netonboard) è uno strumento di valutazione della rete di prova (POC) che esegue test di connettività di base nel tenant di Microsoft 365 e formula consigli specifici per la progettazione della rete per ottenere prestazioni ottimali di Microsoft 365. Lo strumento evidenzia le scelte comuni di progettazione perimetrali di rete aziendale di grandi dimensioni, utili per l'esplorazione Web in Internet, ma che influiscono sulle prestazioni delle applicazioni SaaS di grandi dimensioni, ad esempio Microsoft 365.

Lo strumento di onboarding di rete esegue le operazioni seguenti:

- Rileva la posizione oppure è possibile specificare una posizione da testare
- Controlla il percorso dell'uscita di rete
- Verifica il percorso di rete alla porta principale del servizio Microsoft 365 più vicina
- Fornisce test avanzati tramite un'applicazione di Windows 10 scaricabile che fornisce consigli sulla progettazione della rete perimetrale relativi a server proxy, firewall e DNS. Lo strumento esegue anche test delle prestazioni per Skype for Business online, Microsoft Teams, SharePoint Online ed Exchange Online.

Lo strumento include due componenti: un'interfaccia utente basata su browser che raccoglie informazioni di connettività di base e un'applicazione di Windows 10 scaricabile che esegue test avanzati e restituisce dati di valutazione aggiuntivi.

Lo strumento basato su browser visualizza le informazioni seguenti:

- Scheda Risultati e impatto
  - Posizione su una mappa della porta d'ingresso del servizio in uso
  - La posizione su una mappa di altre porte anteriori del servizio che offrirebbe una connettività ottimale
  - Prestazioni relative rispetto ad altri clienti di Microsoft 365 nelle vicinanze
- Scheda Dettagli e soluzioni
  - Posizione utente per città e paese
  - Posizione di uscita della rete per città, stato e paese
  - Distanza da utente a rete in uscita
  - Posizione della porta principale del servizio Microsoft 365 Exchange Online
  - Porta principale del servizio Microsoft 365 Exchange Online ottimale per la posizione dell'utente
  - Clienti nell'area della metropolitana con prestazioni migliori

L'applicazione scaricabile Advanced Tests fornisce le informazioni aggiuntive seguenti:

- Scheda Dettagli e soluzioni (aggiunta)
  - Gateway predefinito dell'utente
  - Client DNS Server
  - Resolver ricorsivo DNS client
  - Server DNS di Exchange Online
  - Server DNS di SharePoint Online
  - Identificazione del server proxy
  - Controllo connettività multimediale
  - Perdita di pacchetti di qualità multimediale
  - Latenza qualità multimediale
  - Instabilità della qualità multimediale
  - Riordino dei pacchetti di qualità multimediale
- Test di connettività a più endpoint specifici delle funzionalità
- Diagnostica del percorso di rete che include dati di tracert e latenza per i servizi Exchange Online, SharePoint Online e Teams

È possibile leggere il test di connettività di Microsoft 365 e fornire commenti e suggerimenti nel post di blog POC test di connettività di [Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) aggiornato con nuovi suggerimenti per la progettazione della rete. Le informazioni sugli aggiornamenti futuri di questo strumento e di altri aggiornamenti di rete di Microsoft 365 verranno pubblicate nel blog sulla rete di [Office 365.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
  
Ecco un breve collegamento che puoi usare per tornare: [ https://aka.ms/o365networkconnectivity .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>Argomenti correlati

[Informazioni generali sulla connettività di rete di Microsoft 365](microsoft-365-networking-overview.md)

[Principi della connettività di rete di Microsoft 365](./microsoft-365-network-connectivity-principles.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Servizio Web per URL e indirizzi IP di Office 365](microsoft-365-ip-web-service.md)

[Ottimizzazione della rete e delle prestazioni di Microsoft 365](network-planning-and-performance.md)

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)