---
title: Informazioni di riferimento tecnico sulla crittografia
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 06/15/2020
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
description: Informazioni sui vari certificati, tecnologie e sui gruppi di crittografia TLS (Transport Layer Security) utilizzati per la crittografia in Office 365 e Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 244d7a6cef6d77322475245435dafb6c89ab5353
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663429"
---
# <a name="technical-reference-details-about-encryption"></a>Informazioni di riferimento tecnico sulla crittografia

Fare riferimento a questo articolo per informazioni sui certificati, le tecnologie e i gruppi di crittografia TLS utilizzati per la [crittografia in Office 365](encryption.md). In questo articolo sono inoltre disponibili informazioni dettagliate sulle deprecazioni pianificate.
  
- Se si cercano informazioni generali, vedere [crittografia in Office 365](encryption.md).
- Se si desiderano informazioni sull'installazione, vedere [configurare la crittografia in Office 365 Enterprise](set-up-encryption.md).
- Per informazioni sui gruppi di crittografia supportati da versioni specifiche di Windows, vedere [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gestione e proprietà dei certificati di Microsoft Office 365

Non è necessario acquistare o mantenere i certificati per Office 365. Invece, Office 365 utilizza i propri certificati.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Standard di crittografia correnti e deprecazioni pianificate

Per fornire la crittografia Best-in-Class, Office 365 esamina regolarmente gli standard di crittografia supportati. A volte, i vecchi standard sono deprecati perché diventano obsoleti e meno sicuri. In questo articolo vengono descritti i gruppi di crittografia attualmente supportati e gli altri standard e i dettagli relativi alle deprecazioni pianificate.

## <a name="fips-compliance-for-office-365"></a>Conformità FIPS per Office 365

Tutti i gruppi di crittografia supportati da Office 365 utilizzano algoritmi accettati in FIPS 140-2. Office 365 eredita le convalide FIPS da Windows (tramite Schannel). Per informazioni su SChannel, vedere [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versioni di TLS supportati da Office 365

TLS e SSL precedenti a TLS, sono protocolli di crittografia che proteggono le comunicazioni tramite una rete utilizzando i certificati di sicurezza per crittografare una connessione tra i computer. Office 365 supporta la versione 1,2 (TLS 1,2) di TLS.

TLS versione 1,3 (TLS 1,3) attualmente non è supportato.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Supporto per la deprecazione di TLS 1,0 e 1,1

Office 365 ha interrotto il supporto di TLS 1,0 e 1,1 il 31 ottobre 2018. I nuovi problemi riscontrati nei client, dispositivi o servizi che si connettono a Office 365 su TLS 1,0 e 1,1 non verranno corretti. La deprecazione ufficiale per gli ambienti GCC High e DoD ha avuto inizio il 15 gennaio 2020. La deprecazione di TLS 1,0 e 1,1 per gli ambienti mondiali e GCC ha avuto inizio il 15 ottobre 2020.

Per mantenere una connessione sicura ai servizi di Office 365 e Microsoft 365, tutte le combinazioni client-server e browser-server utilizzano TLS 1,2 e moderne suite di crittografia. A tale scopo, potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server. Per informazioni su come questa modifica ha un impatto, vedere [preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Supporto obsoleto per 3DES

Dal 31 ottobre 2018, Office 365 non supporta più l'utilizzo di gruppi di crittografia 3DES per la comunicazione con Office 365. In particolare, Office 365 non supporta più la famiglia di crittografia TLS_RSA_WITH_3DES_EDE_CBC_SHA. Dal 28 febbraio 2019 questo gruppo di crittografia è stato disabilitato in Office 365. I client e i server che comunicano con Office 365 devono supportare una o più cifre di crittografia supportate. Per un elenco di crittografia supportate, vedere [TLS Cipher Suites supportato da Office 365](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Sospensione del supporto relativo al certificato SHA-1 in Office 365

A partire da giugno 2016, Office 365 non accetta più un certificato SHA-1 per le connessioni in uscita o in ingresso. Utilizzare SHA-2 (Secure Hash Algorithm 2) o un algoritmo di hash più robusto nella catena di certificati.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Gruppi di crittografia TLS supportati da Office 365

TLS utilizza i *gruppi* di crittografia, insiemi di algoritmi di cifratura, per stabilire connessioni sicure. Office 365 supporta i gruppi di crittografia elencati nella tabella seguente. Nella tabella sono elencati i gruppi di crittografia in base all'ordine di forza, con il gruppo di crittografia più potente elencato per primo.

Office 365 risponde a una richiesta di connessione prima di tentare la connessione utilizzando la famiglia di crittografia più sicura. Se la connessione non funziona, Office 365 tenta la seconda famiglia di crittografia più sicura nell'elenco e così via. Il servizio continua verso il basso nell'elenco fino a quando non viene accettata la connessione. Analogamente, quando Office 365 richiede una connessione, il servizio di ricezione sceglie se TLS verrà utilizzato e quale famiglia di crittografia utilizzare.

> [!IMPORTANT]
> Tenere presente che le versioni di TLS sono obsolete e che *non è consigliabile utilizzare* le versioni obsolete in cui sono disponibili versioni più recenti. TLS 1,3 non è attualmente supportato. Se i servizi legacy non richiedono TLS 1,0 o 1,1, è consigliabile disabilitarli.

| Famiglia di crittografia | Algoritmo o forza di scambio delle chiavi | Perfetta segretezza in avanti | Crittografia/forza | Algoritmo di autenticazione |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |

Questi gruppi di crittografia supportano i protocolli TLS 1,0 e 1,1 fino alla data di deprecazione. Per gli ambienti GCC High e DoD la data di deprecazione era il 15 gennaio 2020 e per gli ambienti mondiali e GCC che data era il 15 ottobre 2020.

| Protocolli | Nome del pacchetto di crittografia | Algoritmo o forza di scambio delle chiavi | Supporto di Perfect Secret forward | Algoritmo di autenticazione/forza | Crittografia/forza |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Articoli correlati

[Suite di crittografia TLS in Windows 10 V1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Crittografia in Office 365](encryption.md)
  
[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md)
  
[Implementazione di SChannel di TLS 1,0 nell'aggiornamento dello stato di sicurezza di Windows: 24 novembre 2015](https://support.microsoft.com/kb/3117336)
  
[Miglioramenti della crittografia TLS/SSL (centro IT di Windows)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Preparazione per TLS 1.2 in Office 365 e Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
