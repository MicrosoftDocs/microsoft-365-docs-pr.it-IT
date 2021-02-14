---
title: Domande frequenti sulla rete di Office 365 Video
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
description: Risposte ad alcune delle domande più frequenti sulla pianificazione della larghezza di banda, sulla crittografia e & su come il servizio sfrutta le reti per la distribuzione di contenuti (CDN).
ms.openlocfilehash: e08a67988290e7ead87ff30a5ebdf9c8560f4825
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696044"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Domande frequenti sulla rete di Office 365 Video

I servizi di streaming e repository di Office 365 Video rendono semplice l'archiviazione e lo streaming di video all'interno dell'organizzazione. Sono disponibili molte informazioni su [Office 365 Video;](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50) Queste domande frequenti sulla rete sono progettate per rispondere alle domande [](content-delivery-networks.md) più comuni sulla pianificazione della larghezza di banda, sulla crittografia e su come il servizio sfrutta le reti per la distribuzione di contenuti (CDN).
  
Se non si ha ancora una conoscenza approfondita di ciò che accade quando un video viene caricato o riprodotto, guardare questo video che abbiamo messo insieme, Cosa succede a un file video quando viene caricato in [Office 365 Video](https://www.youtube.com/watch?v=HXSZ0jYBKlM).
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Quali sono i requisiti di larghezza di banda di Office 365 Video?

Esistono numerosi [formati video supportati](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) che possono essere caricati in Office 365. Ogni file video viene quindi codificato in un formato standard con diverse qualità video per la riproduzione. Office 365 Video usa lo streaming a velocità in bit adattiva per selezionare la migliore qualità di riproduzione video in base alla larghezza di banda di rete disponibile e alle dimensioni del lettore video. A tale scopo, il lettore richiede inizialmente la qualità di riproduzione più bassa. Il servizio inizia quindi a inviare segmenti video di 2 secondi al lettore video. Il lettore può quindi richiedere una qualità di riproduzione superiore o inferiore in base alla velocità di recapito di ogni segmento.
  
Lo streaming a velocità in bit adattiva esegue tutte queste attività in background mentre il video viene riprodotto con il minor numero di interruzioni o buffering. Durante la riproduzione video, il lettore video consente al visualizzatore di ignorare manualmente la qualità di riproduzione automatica per selezionare una qualità di riproduzione video specifica.
  
Ecco una tabella rapida che descrive i requisiti di rete per ogni qualità di riproduzione video. La larghezza di banda minima necessaria per riprodurre un video è di 802 KBps.
  
| Qualità riproduzione | Velocità di rete |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1,2 Mbps  <br/> |
|576p  <br/> |2,5 Mbps  <br/> |
|720p  <br/> |3,8 Mbps  <br/> |

([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>In che modo le reti per la distribuzione di contenuti (CDN) consentono la riproduzione video?

Se più persone della stessa organizzazione all'interno della stessa posizione geografica stanno streaming degli stessi video, le reti CDN archivieranno una copia di questi video in una posizione più vicina a tale area geografica. Con il video archiviato o memorizzato nella cache nella posizione più vicina, ogni utente lo stream viene trasmesso dalla posizione più vicina anziché da una posizione più vicina. Office 365 Video usa Servizi multimediali di Azure per gestire ciò che viene memorizzato nella cache nelle reti CDN di Azure e per quanto tempo. Servizi multimediali di Azure può usare uno qualsiasi dei percorsi [della rete CDN](https://azure.microsoft.com/documentation/articles/cdn-pop-locations/) di Azure per memorizzare nella cache frammenti e manifesti video per alcuni giorni. Se gli utenti dell'organizzazione continuano a guardare i video memorizzati nella cache, rimarranno nella cache. Se nessuno accede al video per diversi giorni, il video verrà eliminato dalla cache. La volta successiva che qualcuno tenta di guardare il video, il video viene nuovamente memorizzato nella cache nella posizione CDN più vicina.
  
Chiunque tenti di guardare il video mentre il contenuto viene memorizzato nella cache in una rete CDN nelle vicinanze trae vantaggio dal fatto che il video è più vicino e, nella maggior parte dei casi, meno passaggi. In questo modo si migliora la velocità di riproduzione del video; tuttavia, non modifica il requisito di rete per riprodurre il video.
  
> [!NOTE]
> Esistono alcune circostanze, ad esempio il limite di capacità raggiunto, in cui il video può essere rimosso prima che vengano raggiunti i tre giorni.
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Posso memorizzare nella cache i video in locale per velocizzare la riproduzione?

Sì. Office 365 non impedisce l'uso di una rete CDN locale o di un proxy di memorizzazione nella cache per portare video o altri contenuti di Office 365 nella rete locale per un accesso più rapido. Esistono diversi modi per implementare una soluzione di memorizzazione nella cache locale nella rete, il metodo più comune consiste nell'usare una soluzione proxy che memorizza il contenuto nella cache locale. Dopo che un proxy o una rete CDN privata ha memorizzato nella cache i manifesti e i frammenti video, le richieste future per i file instradati attraverso il proxy o la rete CDN privata vengono estrarte dalla cache locale e non da un percorso Internet. Considerare la concorrenza di larghezza di banda, capacità e riproduzione video durante la pianificazione di una soluzione come questa.
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Come vengono crittografati e protetti i video?

Office 365 Video sa quanto sia importante mantenere i dati protetti e privati. [Il Centro protezione Microsoft](https://products.office.com/business/office-365-trust-center-welcome) descrive il nostro impegno per la privacy e la sicurezza dei contenuti. Con la riproduzione di video, la velocità è importante per una buona esperienza; Tuttavia, microsoft non compromette la sicurezza o la privacy dell'utente in cambio di velocità. Ecco come supportare velocità, sicurezza e privacy.
  
Quando un utente o un utente dell'organizzazione carica un nuovo video, il video viene transcodificato, crittografato con la crittografia AES-128 e archiviato in Servizi multimediali di Azure. Ciò significa che i video sono crittografati sia in transito che in pausa.
  
Quando un utente dell'organizzazione tenta di guardare un nuovo video, segue questi passaggi:
  
1. Chiedere a SharePoint Online se sono autorizzati a visualizzare il video.

2. SharePoint Online usa le autorizzazioni per i file per determinare se l'utente può guardare il video.

3. Se sono consentiti, SharePoint Online recupera un token da Azure da assegnare al lettore video.

4. Il lettore video usa quindi il token per richiedere la chiave di decrittografia da Azure.

5. Con la chiave di decrittografia in mano, il lettore video è in grado di trasmettere il video.

![Riproduzione video di O365](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Quali sono i requisiti per la riproduzione di Office 365 Video?

I sistemi operativi e i Web browser supportati da Office 365 Video sono gli stessi dei requisiti di SharePoint Online nei requisiti di sistema di [Office 365.](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45) A seconda del sistema operativo e della configurazione del Web browser di cui si dispone, sarà possibile determinare le esigenze specifiche del lettore video. Ecco altre informazioni sui requisiti di [riproduzione dei video.](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Non è possibile far funzionare il video di Office 365, da dove iniziare?

La risoluzione dei problemi di connettività a Office 365 Video implica la risoluzione dei problemi relativi alla rete, agli ISP e alla configurazione di Office 365. Il primo punto da avviare è il dashboard sull'integrità del servizio. Questo ti dirà che Office 365 Video ha un problema o meno. Se l'aspetto è perfetto, ecco alcune risorse aggiuntive utili.
  
- Assicurarsi di potersi connettere agli endpoint di rete [necessari per Office 365 Video.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Controllare la connettività di rete usando la guida alla risoluzione dei problemi di rete [di Office 365.](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- Vedere le [procedure consigliate per l'uso di Office 365 in una rete lenta.](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)

- [Informazioni sulla configurazione di Office 365 Video.](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)

([Torna all'inizio](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Risorse di Office 365 Video

Ecco alcune altre risorse utili per distribuire e usare Office 365 Video:
  
[Informazioni sulla configurazione di Office 365 Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Presentazione di Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Creare e gestire un canale in Office 365 Video](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Gestire il portale di Office 365 Video](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Formati video che funzionano in Office 365 Video](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Torna all'inizio](office-365-video-networking-faq.md))
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/video365networkfaq](https://aka.ms/video365networkfaq)
