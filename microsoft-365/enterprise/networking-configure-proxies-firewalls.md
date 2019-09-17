---
title: 'Passaggio 4: configurare il bypass di traffico'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare Web browser e dispositivi periferici per il bypass di traffico a posizioni di Office 365 attendibili.
ms.openlocfilehash: fbc4956525e2661ce791c6ec81b449dba685d0f0
ms.sourcegitcommit: 1ca1062ccddd7a46fa0bb4af6ee5f0eb141e7280
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2019
ms.locfileid: "36999040"
---
# <a name="step-4-configure-traffic-bypass"></a>Passaggio 4: configurare il bypass di traffico

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Poiché il traffico su Internet può essere rischioso, le organizzazioni rafforzano la sicurezza delle proprie reti con dispositivi periferici come server proxy, SSL Break and Inspect, dispositivi di ispezione dei pacchetti e sistemi di prevenzione della perdita dei dati. Alcuni dei problemi con i dispositivi di intercettazione delle reti sono descritti nell'articolo sull'utilizzo di dispositivi di rete di terze parti o soluzioni sul traffico di Office 365.

Tuttavia, i nomi di dominio DNS e gli indirizzi IP usati dai servizi basati sul cloud di Microsoft 365 sono noti. Inoltre, il traffico e i servizi stessi sono protetti da numerose funzionalità di sicurezza. Poiché queste misure di sicurezza e protezione sono già presenti, non è necessario che vengano duplicate dai dispositivi periferici. L'elaborazione di misure di sicurezza duplicate e destinazioni intermedie per il traffico di Microsoft 365 può ridurre notevolmente le prestazioni.

Il primo passaggio nell'eliminazione dell'elaborazione di misure di sicurezza duplicate e destinazioni intermedie consiste nell'identificazione del traffico di Microsoft 365. Microsoft ha definito i seguenti tipi di nomi di dominio DNS e intervalli di indirizzi IP, noti come endpoint:

- **Ottimizzazione**: obbligatori per la connessione a tutti i servizi di Office 365 e rappresentano più del 75% della larghezza di banda, delle connessioni e del volume di dati di Microsoft 365. Questi endpoint rappresentano gli scenari di Microsoft 365 più sensibili alle prestazioni, alla latenza e alla disponibilità di rete.
- **Consenti**: obbligatori per la connessione a funzionalità e servizi specifici di Microsoft 365, ma che non sono sensibili alle prestazioni e alla latenza di rete come quelli della categoria Ottimizzazione.
 - **Predefinita**: rappresentano i servizi e le dipendenze di Microsoft 365 che non richiedono l'ottimizzazione. È possibile considerare gli endpoint di questa categoria come traffico su Internet normale.

I nomi di dominio DNS e gli intervalli di indirizzi IP sono disponibili all'indirizzo [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).

Consigli di Microsoft:

- Usare gli script Proxy Automatic Configuration (PAC) sui browser Internet dei computer locali per eseguire il bypass dei server proxy per i nomi di dominio DNS dei servizi basati sul cloud di Microsoft 365. Per gli script PAC di Microsoft 365 più recenti, vedere [Script Get-Pacfile di PowerShell](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).
- 
- Analizzare i dispositivi periferici in uso per determinare l'elaborazione di duplicati e quindi configurarli per inoltrare il traffico agli endpoint delle categorie Ottimizzazione e Consenti senza elaborazione. Questa procedura è nota come bypass di traffico. 

I dispositivi periferici includono firewall, SSL Break and Inspect, dispositivi di ispezione dei pacchetti e sistemi di prevenzione della perdita dei dati. Per configurare e aggiornare le configurazioni di dispositivi periferici, è possibile usare uno script o una chiamata REST per utilizzare un elenco strutturato di endpoint dal servizio Web degli endpoint di Office 365. Per ulteriori informazioni, vedere [Servizio Web per URL e indirizzi IP di Office 365](https://docs.microsoft.com/it-IT/office365/enterprise/office-365-ip-web-service#exporting-a-proxy-pac-file).

Tenere presente che questa procedura consente di eseguire il bypass solo per l'elaborazione dei dati di protezione di rete e proxy normale per il traffico agli endpoint delle categorie Ottimizzazione e Consenti di Microsoft 365. Tutto il resto del traffico su Internet verrà trasmesso tramite proxy e sarà soggetto all'elaborazione dei dati di protezione di rete esistente.


Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step4) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Ottimizzare prestazioni di client e del servizio di Office 365](networking-optimize-tcp-performance.md) |



