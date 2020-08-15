---
title: Domande frequenti su Office 365 networking video
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: Per trovare le risposte alle domande più frequenti sulla pianificazione della larghezza di banda, la crittografia, & come il servizio sfrutta le reti di distribuzione del contenuto (reti CDN).
ms.openlocfilehash: e08a67988290e7ead87ff30a5ebdf9c8560f4825
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696044"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Domande frequenti su Office 365 networking video

I servizi di archiviazione video e di flusso di Office 365 rendono semplice la memorizzazione e lo streaming dei video all'interno dell'organizzazione. Sono disponibili numerose [informazioni sul video di Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50). queste domande frequenti sulla rete sono state progettate per rispondere alle questioni più comuni relative alla pianificazione della larghezza di banda, alla crittografia e al modo in cui il servizio sfrutta le [reti di distribuzione del contenuto](content-delivery-networks.md) (reti CDN).
  
Se non si ha già una conoscenza approfondita di cosa succede quando un video viene caricato o riprodotto, guardate questo video che abbiamo messo insieme, [cosa succede a un file video quando viene caricato nel video di Office 365](https://www.youtube.com/watch?v=HXSZ0jYBKlM).
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Quali sono i requisiti di larghezza di banda video di Office 365?

Sono disponibili numerosi [formati video supportati](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) che possono essere caricati in Office 365. Ogni file video viene quindi codificato in un formato standard con diverse qualità video per la riproduzione. Il video di Office 365 utilizza il flusso di bitrate adattativo per selezionare la migliore qualità di riproduzione video in base alla larghezza di banda di rete disponibile e alla dimensione del lettore video. A tale scopo, il giocatore richiede inizialmente la qualità di riproduzione più bassa. Il servizio inizia quindi a inviare segmenti video di 2 secondi al lettore video. Il giocatore può quindi richiedere una qualità di riproduzione superiore o inferiore in base alla velocità con cui ogni segmento viene recapitato.
  
Lo streaming Adaptive Bitrate fa tutto questo in background mentre il video gioca con il minor numero di interruzioni o di buffering. Durante la riproduzione video, il lettore video consente al visualizzatore di ignorare manualmente la qualità di riproduzione automatica, per selezionare una qualità di riproduzione video specifica.
  
Di seguito è riportata una tabella rapida che delinea i requisiti di rete per ognuna delle qualità di riproduzione video. La larghezza di banda minima per persona necessaria per riprodurre un video è 802Kbps.
  
| Qualità di riproduzione | Velocità di rete |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1,2 Mbps  <br/> |
|576p  <br/> |2,5 Mbps  <br/> |
|720p  <br/> |3,8 Mbps  <br/> |

([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>In che modo le reti di distribuzione del contenuto (reti CDN) aiutano la riproduzione video?

Se più persone appartenenti alla stessa organizzazione all'interno della stessa posizione geografica eseguono lo stesso video (s), reti CDN memorizzerà una copia di questi video in una posizione più vicina all'area geografica. Con il video memorizzato o memorizzato nella cache nella posizione più vicina, ogni persona trasmette il video dal percorso più vicino a loro invece che a una posizione più lontana. Office 365 video utilizza i servizi di Azure Media per gestire ciò che è memorizzato nella cache in reti CDN di Azure e per quanto tempo. I servizi di Azure Media possono utilizzare una qualsiasi delle posizioni della rete [CDN di Azure](https://azure.microsoft.com/documentation/articles/cdn-pop-locations/) per memorizzare nella cache frammenti video e manifesti per alcuni giorni. Se gli utenti dell'organizzazione continuano a guardare i video memorizzati nella cache, rimarranno nella memoria. Se non si accede al video per diversi giorni, il video verrà eliminato dalla cache. La prossima volta che qualcuno cerca di guardare il video, viene nuovamente memorizzato nella cache nella posizione più vicina alla rete CDN.
  
Tutti coloro che tentano di guardare il video mentre il contenuto viene memorizzato nella cache nei dintorni della rete CDN sono avvantaggiati dal video più vicino e, nella maggior parte dei casi, meno hop, away. Ciò migliora la velocità di riproduzione video; Tuttavia, non cambia il requisito di rete per riprodurre il video.
  
> [!NOTE]
> In alcuni casi, ad esempio, viene raggiunto il limite di capacità, in cui il video può essere rimosso prima che siano stati raggiunti i tre giorni.
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>È possibile memorizzare nella cache i video localmente per una riproduzione più rapida?

Sì. Office 365 non impedisce l'utilizzo di un servizio CDN locale o di un proxy di memorizzazione nella cache per portare video o altri contenuti di Office 365 nella rete locale per ottenere un accesso più rapido. Esistono diversi modi per implementare una soluzione di memorizzazione nella cache locale sulla rete, il metodo più comune consiste nell'utilizzare una soluzione proxy che memorizza nella cache il contenuto in locale. Una volta che un proxy o una rete CDN privata ha memorizzato nella cache i frammenti video e i manifesti, le richieste future per i file che si instradano attraverso il proxy o la rete CDN privata vengono estratte dalla cache locale e non vengono estratte da una posizione Internet. Considerare la larghezza di banda di rete, la capacità e la riproduzione video durante la pianificazione di una soluzione come questa.
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Come vengono crittografati e protetti i video?

Office 365 video sa quanto è importante mantenere i dati sicuri e privati. [Centro protezione Microsoft](https://products.office.com/business/office-365-trust-center-welcome) descrive il nostro impegno per la privacy e la sicurezza del contenuto. Con la riproduzione video, la velocità è importante per una buona esperienza; Tuttavia, non si compromette la sicurezza o la privacy in Exchange for Speed. Ecco come gestire la velocità, la sicurezza e la privacy.
  
Quando un utente o un utente dell'organizzazione carica un nuovo video, questo video viene trascodificato, crittografato con la crittografia AES-128 e archiviato nei servizi di Azure Media. Questo significa che i video vengono crittografati sia in transito che a riposo.
  
Quando un utente dell'organizzazione tenta di guardare un nuovo video, segue la procedura seguente:
  
1. Chiedere a SharePoint Online se dispongono dell'autorizzazione per visualizzare il video.

2. SharePoint Online utilizza le autorizzazioni dei file per determinare se la persona può guardare il video.

3. Se gli utenti sono consentiti, SharePoint Online recupera un token da Azure per fornire al lettore video.

4. Il lettore video quindi utilizza il token per richiedere la chiave di decrittografia da Azure.

5. Con la chiave di decrittografia in mano, il lettore video è in grado di eseguire lo streaming del video.

![Riproduzione video di O365](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Quali sono i requisiti per la riproduzione del video di Office 365?

I sistemi operativi e i Web browser supportati da Office 365 sono gli stessi dei requisiti di sistema di SharePoint online in [office 365](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45). A seconda del sistema operativo e della configurazione del Web browser in uso, vengono determinate le esigenze specifiche del lettore video. Di seguito vengono fornite ulteriori informazioni sui [requisiti di riproduzione video](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Non è possibile ottenere il lavoro di Office 365 video, da dove iniziare?

Risoluzione dei problemi relativi alla connettività a Office 365 video comporta la risoluzione di problemi relativi alla rete, agli ISP e alla configurazione di Office 365. Il primo punto di partenza è il dashboard di integrità dei servizi. Questo vi dirà di Office 365 video ha un problema o meno. Se tutto sembra ottimo, Ecco alcune risorse aggiuntive per aiutarti.
  
- Assicurarsi di essere in grado di connettersi agli [endpoint di rete necessari per il video di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

- Controllare la connettività di rete utilizzando la [Guida alla risoluzione dei problemi di rete di Office 365](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).

- Vedere le [procedure consigliate per l'utilizzo di Office 365 in una rete lenta](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).

- [Trovare informazioni sulla configurazione video di Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).

([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Risorse video di Office 365

Ecco alcune altre risorse utili per la distribuzione e l'utilizzo di Office 365 video:
  
[Informazioni sulla configurazione video di Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Vedere il video di Office 365](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Creare e gestire un canale in Office 365 video](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Gestire il portale video di Office 365](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Formati video che funzionano in Office 365 video](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/video365networkfaq](https://aka.ms/video365networkfaq)
