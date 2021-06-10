---
title: Dettagli tecnici di riferimento sulla crittografia
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Informazioni sui vari certificati, tecnologie e suite di crittografia TLS (Transport Layer Security) utilizzate per la crittografia in Office 365 e Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919352"
---
# <a name="technical-reference-details-about-encryption"></a>Dettagli tecnici di riferimento sulla crittografia

Fare riferimento a questo articolo per informazioni sui certificati, le tecnologie e le suite di crittografia TLS utilizzate per la crittografia [in Office 365](encryption.md). In questo articolo vengono inoltre fornite informazioni dettagliate sulle deprecate pianificate.
  
- Per informazioni generali, vedere [Crittografia in Office 365](encryption.md).
- Per informazioni sull'installazione, vedere [Set up encryption in Office 365 Enterprise.](set-up-encryption.md)
- Per informazioni sulle suite di crittografia supportate da versioni specifiche di Windows, vedere [Cipher Suites in TLS/SSL (SCHANNEL SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gestione e proprietà dei certificati di Microsoft Office 365

Non è necessario acquistare o gestire certificati per Office 365. Al contrario, Office 365 i propri certificati.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Standard di crittografia correnti e deprecazione pianificata

Per fornire la crittografia più avanzata, Office 365 regolarmente gli standard di crittografia supportati. A volte, i vecchi standard sono deprecati quando diventano obsoleti e meno sicuri. Questo articolo descrive le suite di crittografia attualmente supportate e altri standard e dettagli sulle deprecazioni pianificate.

## <a name="fips-compliance-for-office-365"></a>Conformità FIPS per Office 365

Tutte le suite di crittografia supportate Office 365 algoritmi accettabili in FIPS 140-2. Office 365 eredita le convalide FIPS da Windows (tramite Schannel). Per informazioni su Schannel, vedere [Cipher Suites in TLS/SSL (SSP Schannel).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versioni di TLS supportati da Office 365

TLS e SSL precedenti a TLS sono protocolli crittografici che assicurano la comunicazione su una rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. Office 365 supporta TLS versione 1.2 (TLS 1.2).

TLS versione 1.3 (TLS 1.3) non è attualmente supportato.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Supporto per la deprecazione di TLS 1.0 e 1.1

Office 365 ha smesso di supportare TLS 1.0 e 1.1 il 31 ottobre 2018. È stata completata la disabilitazione di TLS 1.0 e 1.1 in GCC High e DoD. Abbiamo iniziato a disabilitare TLS 1.0 e 1.1 per gli ambienti worldwide e GCC a partire dal 15 ottobre 2020 e continueremo con l'implementazione nelle prossime settimane e mesi.

Per mantenere una connessione sicura ai servizi Office 365 e Microsoft 365, tutte le combinazioni client-server e browser-server utilizzano TLS 1.2 e le moderne suite di crittografia. A tale scopo, potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server. Per informazioni sull'impatto di questa modifica, vedere [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Rimozione del supporto per 3DES

Dal 31 ottobre 2018, Office 365 non supporta più l'uso di suite di crittografia 3DES per la comunicazione con Office 365. In particolare, Office 365 non supporta più la TLS_RSA_WITH_3DES_EDE_CBC_SHA di crittografia. Dal 28 febbraio 2019, questa suite di crittografia è stata disabilitata in Office 365. I client e i server che Office 365 devono supportare una o più delle crittografia supportate. Per un elenco delle crittografia supportate, vedi Suite di crittografia [TLS supportate da Office 365](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Sospensione del supporto relativo al certificato SHA-1 in Office 365

Da giugno 2016, Office 365 non accetta più un certificato SHA-1 per le connessioni in uscita o in ingresso. Utilizzare SHA-2 (Secure Hash Algorithm 2) o un algoritmo di hashing più avanzato nella catena di certificati.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Pacchetti di crittografia TLS supportati da Office 365

TLS usa *suite di crittografia,* raccolte di algoritmi di crittografia, per stabilire connessioni sicure. Office 365 supporta le suite di crittografia elencate nella tabella seguente. La tabella elenca le suite di crittografia in ordine di forza, con la suite di crittografia più forte elencata per prima.

Office 365 risponde a una richiesta di connessione tentando innanzitutto di connettersi utilizzando la suite di crittografia più sicura. Se la connessione non funziona, Office 365 la seconda suite di crittografia più sicura nell'elenco e così via. Il servizio continua verso il basso nell'elenco fino a quando la connessione non viene accettata. Allo stesso modo, quando Office 365 richiede una connessione, il servizio di ricezione sceglie se verrà utilizzato TLS e quale suite di crittografia utilizzare.

> [!IMPORTANT]
> Tenere presente che le versioni TLS sono deprecate e che le versioni deprecate non devono essere *usate* quando sono disponibili versioni più recenti. TLS 1.3 non è attualmente supportato. Se i servizi legacy non richiedono TLS 1.0 o 1.1, è consigliabile disabilitarli.

| Famiglia di prodotti di crittografia | Algoritmo/forza di scambio delle chiavi | Forward Secrecy | Crittografia/forza | Algoritmo di autenticazione |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |

Queste suite di crittografia supportano i protocolli TLS 1.0 e 1.1 fino alla data di deprecazione. Per GCC ambienti High e DoD la data di deprecazione era il 15 gennaio 2020 e per gli ambienti Worldwide e GCC quella data era il 15 ottobre 2020.

| Protocolli | Nome del pacchetto di crittografia | Algoritmo/forza di scambio delle chiavi | Supporto di Forward Secrecy | Algoritmo/forza di autenticazione | Crittografia/Forza |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Articoli correlati

[Pacchetti di crittografia TLS in Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Crittografia in Office 365](encryption.md)
  
[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md)
  
[Implementazione Schannel di TLS 1.0 in Windows stato di sicurezza: 24 novembre 2015](https://support.microsoft.com/kb/3117336)
  
[Miglioramenti della crittografia TLS/SSL (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Preparazione per TLS 1.2 in Office 365 e Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)