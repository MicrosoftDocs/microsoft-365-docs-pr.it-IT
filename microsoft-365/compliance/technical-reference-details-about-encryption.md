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
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Informazioni sui vari certificati, tecnologie e gruppi di crittografia TLS utilizzati per la crittografia in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91fa21fff12c429032af6468ff3024acfc6ca2ab
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024542"
---
# <a name="technical-reference-details-about-encryption"></a>Informazioni di riferimento tecnico sulla crittografia

Fare riferimento a questo articolo per informazioni sui certificati, le tecnologie e i gruppi di crittografia TLS utilizzati per la [crittografia in Office 365](encryption.md). In questo articolo sono inoltre disponibili informazioni dettagliate sulle deprecazioni pianificate.
  
- Se si cercano informazioni generali, vedere [crittografia in Office 365](encryption.md).
- Se si desiderano informazioni sull'installazione, vedere [configurare la crittografia in Office 365 Enterprise](set-up-encryption.md).
- Per informazioni sui gruppi di crittografia supportati da versioni specifiche di Windows, vedere [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gestione e proprietà dei certificati di Microsoft Office 365

Dal momento che Microsoft utilizza il proprio certificato, non è necessario acquistare o mantenere i certificati per Office 365.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Standard di crittografia correnti e deprecazioni pianificate

Per continuare a fornire la crittografia Best-in-class per Office 365, Microsoft esamina periodicamente gli standard di crittografia supportati. A volte, è necessario deprecare gli standard precedenti quando diventano obsoleti e pertanto meno sicuri. In questo argomento vengono descritti i gruppi di crittografia attualmente supportati e altri standard, nonché i dettagli relativi alle deprecazioni pianificate. 

## <a name="fips-compliance-for-office-365"></a>Conformità FIPS per Office 365

Tutti i gruppi di crittografia supportati da Office 365 utilizzano algoritmi accettati in FIPS 140-2. Office 365 eredita le convalide FIPS da Windows (tramite Schannel). Per informazioni su SChannel, vedere [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versioni di TLS supportati da Office 365

Transport Layer Security (TLS) e il precedente Secure Sockets Layer (SSL) sono protocolli crittografici che proteggono la comunicazione in rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. Office 365 supporta la versione 1,2 (TLS 1,2) di TLS.

TLS versione 1,3 (TLS 1,3) attualmente non è supportato.
  
## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>Supporto per la deprecazione di TLS 1,0 e 1,1 e cosa significa per te

Dal 31 ottobre 2018, Office 365 non supporta più TLS 1,0 e 1,1. Questo significa che Microsoft non risolverà i nuovi problemi che vengono rilevati in client, dispositivi o servizi che si connettono a Office 365 tramite TLS 1.0 e 1.1.

Questo non significa che Office 365 bloccherà le connessioni TLS 1,0 e 1,1.

Anche se in origine è stata impostata la data del 1 ° giugno 2020 per la deprecazione TLS 1,0 e TLS 1,1 per gli ambienti mondiali e GCC, questa data non è più valida. Ciò è dovuto a COVID-19. Quando si dispone di una nuova data per questa deprecazione, verrà pubblicata qui. 

Per gli ambienti GCC High e DoD, la deprecazione ufficiale si è verificata il 15 gennaio 2020.

È necessario assicurarsi che tutte le combinazioni client-server e browser-server utilizzino TLS 1,2 e le moderne suite di crittografia per mantenere una connessione sicura ai servizi di Office 365 e Microsoft 365. A tale scopo, potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server. Per informazioni su come questo ha un impatto, vedere [preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Supporto obsoleto per 3DES

Dal 31 ottobre 2018, Office 365 non supporta più l'utilizzo di gruppi di crittografia 3DES per la comunicazione con Office 365. In particolare, Office 365 non supporta più la famiglia di crittografia TLS_RSA_WITH_3DES_EDE_CBC_SHA. Dal 28 febbraio 2019 questo gruppo di crittografia è stato disabilitato in Office 365. I client e i server che comunicano con Office 365 dopo questa data devono supportare almeno una delle cifrature più sicure elencate in questo argomento (vedere [TLS Cipher Suites supportato da office 365](#tls-cipher-suites-supported-by-office-365)).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Sospensione del supporto relativo al certificato SHA-1 in Office 365

A giugno 2016, Office 365 non accetta più un certificato SHA-1 per le connessioni in uscita o in ingresso. Se si sta attualmente utilizzando un certificato con SHA-1 nella catena di certificati, sarà necessario aggiornare la catena per l'utilizzo di SHA-2 (Secure Hash Algorithm 2) o di un algoritmo di hash più robusto.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Gruppi di crittografia TLS supportati da Office 365

Un pacchetto di crittografia è una raccolta di algoritmi di crittografia utilizzati da TLS per stabilire connessioni protette. Nella tabella seguente sono riportati i pacchetti di crittografia supportati da Office 365 in ordine di priorità, a partire dai pacchetti di crittografia dotati di forza maggiore. Quando Office 365 riceve una richiesta di connessione, Office 365 prima tenta di connettersi utilizzando la famiglia di crittografia di primo livello. Quindi, se non è riuscito, Office 365 tenta la seconda famiglia di crittografia nell'elenco e così via verso il basso nell'elenco. Quando Office 365 invia una richiesta di connessione a un altro server o a un client, la scelta del pacchetto di crittografia da utilizzare o della possibilità o meno di utilizzare TLS dipende dal server o dal client ricevente.

> [!IMPORTANT]
> Tenere presente che le versioni di TLS sono obsolete e che *non è consigliabile utilizzare* le versioni obsolete in cui sono disponibili versioni più recenti. TLS 1,3 non è attualmente supportato. Se i servizi legacy non richiedono TLS 1,0 o 1,1, è consigliabile disabilitarli.
  
|**Protocolli**|**Nome del pacchetto di crittografia**|**Algoritmo o forza di scambio delle chiavi**|**Supporto di Perfect Secret forward**|**Algoritmo di autenticazione/forza**|**Crittografia/forza**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>Argomenti correlati
[Suite di crittografia TLS in Windows 10 V1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Crittografia in Office 365](encryption.md)
  
[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md)
  
[Implementazione di SChannel di TLS 1,0 nell'aggiornamento dello stato di sicurezza di Windows: 24 novembre 2015](https://support.microsoft.com/kb/3117336)
  
[Miglioramenti della crittografia TLS/SSL (centro IT di Windows)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
 [Preparazione per TLS 1.2 in Office 365 e Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

