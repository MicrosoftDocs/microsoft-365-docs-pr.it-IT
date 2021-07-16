---
title: Preparazione per TLS 1.2 in Office 365 e Office 365 GCC
description: Viene spiegato come preparare il sistema per l'uso di TLS 1.2 per tutte le combinazioni client-server e browser-server in Office 365 e Office 365 GCC dopo la disattivazione del supporto per TLS 1.0 e 1.1.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: ca689b846589ffcb1b8aa4d85ea8a0312f8d9d51
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53463974"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Preparazione per TLS 1.2 in Office 365 e Office 365 GCC

## <a name="summary"></a>Riepilogo

Per fornire ai clienti la migliore crittografia possibile, Microsoft intende interrompere il supporto per Transport Layer Security (TLS) versioni 1.0 e 1.1 in Office 365 e Office 365 GCC. Sappiamo bene che la sicurezza dei dati è importante e facciamo tutto il possibile per garantire trasparenza in merito alle modifiche che potrebbero influire sull'uso del servizio TLS.

L'[implementazione di Microsoft TLS 1.0](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) non contiene vulnerabilità di sicurezza note. Tuttavia, a causa della possibilità di futuri attacchi alle versioni precedenti del protocollo e alle altre vulnerabilità di TLS, intendiamo interrompere il supporto per TLS 1.0 e 1.1 in Microsoft Office 365 e Office 365 GCC.

Per informazioni su come rimuovere le dipendenze da TLS 1.0 e 1.1, vedere il seguente white paper: [Risolvere il problema TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).

Dopo l'aggiornamento a TLS 1.2, assicurati che le suite di crittografia in uso siano supportate da Azure Front Door. Microsoft 365 e Azure Front Door hanno lievi differenze nel supporto della suite di crittografia. Per informazioni dettagliate, vedere Quali sono le suite di crittografia [correnti supportate da Azure Front Door?](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-).

## <a name="more-information"></a>Ulteriori informazioni

Abbiamo già iniziato la deprecazione di TLS 1.0 e 1.1 a partire da gennaio 2020. Tutti i client, i dispositivi o i servizi che si connettono a Office 365 tramite TLS 1.0 o 1.1 nelle istanze DoD o GCC High non sono supportati. Per i clienti commerciali di Office 365, la deprecazione di TLS 1.0 e 1.1 inizierà il 15 ottobre 2020 e l'implementazione continuerà nelle settimane e nei mesi successivi.

Assicurarsi che tutte le combinazioni client-server e browser-server utilizzino TLS 1.2 (o versione successiva) per garantire una connessione ai servizi di Office 365. A tale scopo, potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server.

Dovrai aggiornare le applicazioni che chiamano Microsoft 365 API su TLS 1.0 o TLS 1.1 per usare TLS 1.2. .NET 4.5 per impostazione predefinita è TLS 1.1. Per aggiornare la configurazione .NET, vedere [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

I client seguenti non sono in grado di utilizzare TLS 1.2. Aggiornare tali client per garantire l'accesso continuo al servizio.

- Android 4.3 e versioni precedenti
- Firefox versione 5.0 e versioni precedenti
- Internet Explorer 8-10 su Windows 7 e versioni precedenti
- Internet Explorer 10 su Windows Phone 8
- Safari 6.0.4/OS X10.8.4 e versioni precedenti

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>TLS 1.2 per Microsoft Teams Rooms e Surface Hub

Microsoft Teams Rooms (precedentemente noto come Skype Room System V2 SRS V2) hanno supportato TLS 1.2 da dicembre 2018. È consigliabile che nei dispositivi Rooms sia installata l'app Microsoft Teams Rooms, versione 4.0.64.0 o successiva. Per ulteriori informazioni, vedere le [note sulla versione](/microsoftteams/room-systems/srs2-release-note). Le modifiche sono compatibili con le versioni precedenti e la versione attualmente installata.

Surface Hub ha rilasciato il supporto TLS 1.2 a maggio 2019.

Il supporto TLS 1.2 per i prodotti Microsoft Teams Rooms e Surface Hub richiede anche le seguenti modifiche al codice lato server:

- Le modifiche al server di Skype for Business Online sono state apportate in aprile 2019. Ora, Skype for Business Online supporta la connessione di dispositivi Microsoft Teams Rooms e Surface Hub tramite TLS 1.2.
- I clienti di Skype for Business Server devono installare un aggiornamento cumulativo (CU) per utilizzare TLS 1.2 per Teams Rooms Systems e Surface Hub.

  - Per Skype for Business Server 2015, CU9 è già stato rilasciato a maggio 2019.
  - Per Skype for Business Server 2019, CU1 era precedentemente previsto per aprile 2019, ma è stato rinviato a giugno 2019.

  > [!NOTE]
  > I clienti locali di Skype for Business non devono disabilitare TLS 1.0/1.1 prima di installare CUs specifici per Skype for Business Server.

Se si utilizza un'infrastruttura locale per gli scenari ibridi o Active Directory Federation Services, assicurarsi che tale infrastruttura sia sia in grado di supportare le connessioni in entrata e in uscita che utilizzano TLS 1.2.

## <a name="references"></a>Riferimenti

Le risorse che seguono forniscono indicazioni per verificare che i client utilizzino TLS 1.2 o versioni successive e per disabilitare TLS 1.0 e 1.1.

- Per client Windows 7 connessi a Office 365, verificare che TLS 1.2 sia impostato come protocollo di sicurezza predefinito nel servizio WinHTTP di Windows. Per ulteriori informazioni, vedere [KB 3140245 - Aggiornamento per abilitare TLS 1.1 e TLS 1.2 come protocollo sicuro predefinito in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- [Pacchetti di crittografia TLS supportati da Office 365](/microsoft-365/compliance/technical-reference-details-about-encryption#tls-cipher-suites-supported-by-office-365)
- Per informazioni su come evitare di utilizzare la versione meno sicura di TLS, rimuovendo le dipendenze da TLS 1.0 e 1.1, vedere [Supporto per TLS 1.2](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/) nel sito Web Microsoft.
- Le [nuove funzionalità di IIS](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) semplificano l'individuazione dei client nei sistemi [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) e [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) che si connettono al servizio utilizzando protocolli di sicurezza inefficaci.
- Ottenere ulteriori informazioni su come [risolvere il problema di TLS 1.0.](https://www.microsoft.com/download/details.aspx?id=55266)
- Per informazioni generali sull'approccio di Microsoft alla sicurezza, visitare il [Centro protezione di Office 365](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Preparazione alla deprecazione di TLS 1.0/1.1 - Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Linee guida TLS di Exchange Server, parte 1: Prepararsi per TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Linee guida TLS di Exchange Server Parte 2: Abilitazione di TLS 1.2 e identificazione dei client che non lo utilizzano](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Linee guida TLS di Exchange Server Parte 3: Disattivazione di TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Abilitare il supporto per TLS 1.1 e TLS 1.2 in Office Online Server](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
