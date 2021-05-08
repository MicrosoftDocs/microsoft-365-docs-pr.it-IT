---
title: 'Panoramica: split tunneling per VPN con Office 365'
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Informazioni su come usare lo split tunneling per VPN con Office 365 per ottimizzare la connettività di Office 365 per gli utenti remoti.
ms.openlocfilehash: c92599469431732136637cee2bb6a029c4eb4037
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259248"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>Ottimizzare la connettività di Office 365 per gli utenti remoti tramite split tunneling VPN
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

Per i clienti che connettono i dispositivi di lavoro remoti alla rete aziendale o all'infrastruttura cloud tramite VPN, Microsoft consiglia di instradare gli scenari chiave di Office 365 **Microsoft Teams,** **SharePoint Online** e **Exchange Online** tramite una configurazione split _tunnel VPN._ Ciò diventa particolarmente importante come strategia di prima linea per facilitare la produttività continua dei dipendenti durante eventi di lavoro da casa su larga scala, come la crisi COVID-19.

![Configurazione di split tunneling per VPN](../media/vpn-split-tunneling/vpn-model-2.png)

_Figura 1 - Soluzione split tunneling per VPN con evidenti eccezioni di Office 365 inviate direttamente al servizio. Tutto il resto del traffico attraversa il tunnel VPN indipendentemente dalla destinazione._

L'aspetto fondamentale di questo approccio è quello di fornire alle aziende un metodo semplice per ridurre il rischio di saturazione dell'infrastruttura VPN e migliorare significativamente le prestazioni di Office 365 nel più breve tempo possibile. La configurazione dei client VPN per consentire all'intenso traffico di Office 365 di livello più critico di bypassare il tunnel VPN offre i seguenti vantaggi:

- Attenua subito la causa principale della maggior parte dei problemi relativi alle prestazioni e alla capacità di rete segnalati dai clienti nelle architetture VPN aziendali che hanno impatto sull'esperienza utente di Office 365
  
  La soluzione consigliata si rivolge in modo specifico agli endpoint del servizio Office 365 della categoria **Optimize** nell'argomento [URL e intervalli di indirizzi IP per Office 365](./urls-and-ip-address-ranges.md). Il traffico verso questi endpoint è estremamente sensibile alla latenza e alla limitazione della larghezza di banda e consentire di ignorare il tunnel VPN può migliorare notevolmente l'esperienza dell'utente finale e ridurre il carico di rete aziendale. Le connessioni di Office 365, che non costituiscono la maggior parte delle larghezze di banda o dell'esperienza utente, possono continuare a essere instradate attraverso il tunnel VPN insieme al resto del traffico connesso a Internet. Per ulteriori informazioni, vedere [La strategia split tunneling per VPN](#the-vpn-split-tunnel-strategy).

- Può essere configurato, testato e implementato rapidamente dai clienti e senza requisiti di infrastruttura o applicazioni aggiuntivi

  L'implementazione può richiedere alcune ore, a seconda della piattaforma VPN e dell'architettura di rete. Per altre informazioni, vedere [Implementare lo split tunneling per VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- Garantisce il livello di sicurezza delle implementazioni VPN dei clienti, senza modificare il modo in cui vengono instradate le altre connessioni, incluso il traffico su Internet

  La configurazione consigliata segue il principio dei **privilegi minimi** per le eccezioni relative al traffico VPN e consente ai clienti di implementare la funzione di split tunneling per VPN senza esporre gli utenti o l'infrastruttura a ulteriori rischi per la sicurezza. Il traffico di rete instradato direttamente agli endpoint di Office 365 viene crittografato, convalidato per l'integrità dagli stack di applicazioni client di Office e con ambito agli indirizzi IP dedicati ai servizi Office 365 con protezione avanzata sia a livello di applicazione che di rete. Per ulteriori informazioni, vedere [Modi alternativi per i professionisti della sicurezza e l'IT per ottenere moderni controlli di sicurezza nei particolari scenari odierni di lavoro remoto (blog del team di sicurezza di Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- È supportato in modo nativo dalla maggior parte delle piattaforme VPN aziendali

  Microsoft continua a collaborare con i partner del settore realizzando soluzioni VPN commerciali che consentono ai partner di sviluppare indicazioni mirate e modelli di configurazione per le soluzioni in linea con i suggerimenti sopra descritti. Per altre informazioni, vedere [PROCEDURE per le piattaforme VPN più comuni](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms).

>[!TIP]
>Microsoft consiglia di focalizzare la configurazione di split tunneling per VPN su intervalli IP dedicati indicati per i servizi di Office 365. Le configurazioni di split tunneling basate su FQDN o AppID sono possibili in determinate piattaforme client VPN, tuttavia potrebbero non coprire completamente gli scenari principali di Office 365 ed entrare in conflitto con le regole di routing VPN basate su IP. Per questo motivo, Microsoft consiglia di non usare FQDN di Office 365 per la configurazione di split tunneling per VPN. La configurazione FQDN può essere utile in altri scenari correlati, ad esempio per personalizzare file PAC o per implementare regole per bypassare il proxy.

Per informazioni sull'implementazione completa, vedere [Implementazione dello split tunneling per VPN per Office 365](microsoft-365-vpn-implement-split-tunnel.md).

Per un processo dettagliato per configurare le Microsoft 365 per i lavoratori remoti, vedere [Configurare l'infrastruttura per il lavoro remoto](..\solutions\empower-people-to-work-remotely.md)

## <a name="the-vpn-split-tunnel-strategy"></a>La strategia split tunneling per VPN

Le reti aziendali tradizionali spesso sono progettate per garantire la sicurezza durante il lavoro in una situazione antecedente al cloud, in cui la maggior parte dei dati, dei servizi e delle applicazioni importanti sono ospitati in locale e sono direttamente collegati alla rete aziendale interna, come la maggior parte degli utenti. Pertanto, l'infrastruttura di rete è costruita attorno a questi elementi in quanto le filiali sono collegate alla sede centrale tramite reti _Multiprotocol Label Switching (MPLS)_ e gli utenti remoti devono connettersi alla rete aziendale attraverso una rete VPN per accedere sia agli endpoint locali che a Internet. In questo modello, tutto il traffico proveniente da utenti remoti attraversa la rete aziendale e viene instradato al servizio cloud attraverso un punto di uscita comune.

![Configurazione VPN forzata](../media/vpn-split-tunneling/vpn-model-1.png)

_Figura 2 - Soluzione VPN comune per gli utenti remoti, in cui tutto il traffico è obbligato a tornare nella rete aziendale indipendentemente dalla destinazione_

Quando le organizzazioni spostano dati e applicazioni nel cloud, questo modello ha iniziato a diventare meno efficace in quanto diventa rapidamente ingombrante, costoso e inscalzabile, influenzando in modo significativo le prestazioni e l'efficienza della rete degli utenti e limitando la capacità dell'organizzazione di adattarsi alle esigenze mutevoli. Numerosi clienti Microsoft hanno segnalato che qualche anno fa l'80% del traffico di rete era verso una destinazione interna, ma nel 2020 l'80% più il traffico si connette a una risorsa esterna basata su cloud.

Il problema è stato aggravato dalla crisi COVID-19, che richiede soluzioni immediate per la maggior parte delle organizzazioni. Molti clienti hanno rilevato che il modello VPN forzato non è scalabile o non è sufficiente per il 100% degli scenari di lavoro remoto, come quello sorto in seguito a questa crisi. Per continuare a operare in modo efficiente, sono necessarie soluzioni rapide.

Per il servizio Office 365, Microsoft ha progettato i requisiti di connettività per il servizio con questo problema, in modo da ottimizzare in modo semplice e rapido un set di endpoint del servizio mirato, strettamente controllato e relativamente statico in modo da garantire prestazioni elevate agli utenti che accedono al servizio e ridurre il carico sull'infrastruttura VPN in modo che possa essere utilizzato dal traffico che lo richiede ancora.

Office 365 classifica gli endpoint necessari per Office 365 in tre categorie: **Optimize**, **Allow** e **Default**. Gli endpoint **Optimize** sono al centro di questa soluzione e presentano le seguenti caratteristiche:

- Sono endpoint gestiti di proprietà di Microsoft, ospitati sull'infrastruttura Microsoft
- Sono dedicati ai carichi di lavoro principali di Office 365, come Exchange Online, SharePoint Online, Skype for Business Online e Microsoft Teams.
- Sono forniti di IP
- Sono caratterizzati da indicatore ROC basso che dovrebbe mantenersi tale (attualmente 20 subnet IP)
- Sono caratterizzati da sensibilità alla latenza e/o intensità
- Sono in grado di avere elementi di sicurezza richiesti forniti nel servizio piuttosto che in linea sulla rete
- Rappresentano circa il 70-80% del volume di traffico nel servizio Office 365

Questo set limitato di endpoint può essere diviso dal tunnel VPN forzato e inviato in modo sicuro e diretto al servizio Office 365 tramite l'interfaccia locale dell'utente. Ciò è noto come **split tunneling**.

Gli elementi di sicurezza come DLP, protezione AV, autenticazione e controllo degli accessi possono essere tutti recapitati in modo molto più efficiente su questi endpoint a livelli diversi all'interno del servizio. Inoltre, allontanando la maggior parte del volume di traffico dalla soluzione VPN, la capacità VPN viene liberata per il traffico critico per l'azienda che si basa ancora su di esso. Consente inoltre di evitare di passare attraverso un programma di aggiornamento, in molti casi, lungo e costoso per far fronte a questo nuovo modo di operare.

![Dettagli Tunnel configurazione VPN suddivisa](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Figura 3 - Soluzione split tunnel VPN con evidenti eccezioni di Office 365 inviate direttamente al servizio. Tutto il resto del traffico è obbligato a tornare nella rete aziendale indipendentemente dalla destinazione._

Da un punto di vista della sicurezza, Microsoft offre una vasta gamma di funzionalità che possono essere usate per garantire una sicurezza simile o anche superiore a quella offerta dal controllo in linea tramite stack di sicurezza locali. Il post del blog del team di sicurezza di Microsoft [Modi alternativi per i professionisti della sicurezza e l'IT per ottenere moderni controlli di sicurezza nei particolari scenari odierni di lavoro remoto](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) contiene un chiaro riepilogo delle funzionalità disponibili oltre alle informazioni dettagliate in questo articolo. È anche possibile leggere informazioni sull'implementazione della soluzione split tunneling per VPN di Microsoft nella pagina [Running on VPN: How Microsoft is keeping its remote workforce connected](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) (Lavorare su VPN: la soluzione Microsoft per mantenere connessa la forza lavoro remota).

In molti casi, l'implementazione è possibile in poche ore, il che offre una rapida risoluzione a uno dei problemi più urgenti delle organizzazioni, il rapido passaggio al lavoro remoto su vasta scala. Per informazioni sullo split tunneling per VPN, vedere [Implementazione dello split tunneling per VPN per Office 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="related-topics"></a>Argomenti correlati

[Implementazione dello split tunneling per VPN per Office 365](microsoft-365-vpn-implement-split-tunnel.md)

[Ottimizzazione delle prestazioni di Office 365 per utenti della Cina](microsoft-365-networking-china.md)

[Modi alternativi per i professionisti della sicurezza e l'IT per ottenere moderni controlli di sicurezza nei particolari scenari odierni di lavoro remoto (blog del team di sicurezza di Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Ottimizzazione delle prestazioni VPN in Microsoft: usare i profili VPN di Windows 10 per consentire connessioni automatiche](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Esecuzione del servizio VPN: la soluzione Microsoft per mantenere connessa la forza lavoro remota](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Principi della connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md)

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)

[Test di connettività di Microsoft 365](https://aka.ms/netonboard)