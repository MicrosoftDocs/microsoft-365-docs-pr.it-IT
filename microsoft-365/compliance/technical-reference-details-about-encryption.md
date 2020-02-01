---
title: Dettagli tecnici di riferimento sulla crittografia in Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Visualizzare i dettagli tecnici relativi a Encyption in Office 365.
ms.openlocfilehash: a1eaa10f35a70688bc26967b7344cd90b2ad8343
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601393"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Dettagli tecnici di riferimento sulla crittografia in Office 365

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

Transport Layer Security (TLS) e il precedente Secure Sockets Layer (SSL) sono protocolli crittografici che proteggono la comunicazione in rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. Office 365 supporta diverse versioni di TLS, tra cui:
  
- TLS versione 1.2 (TLS 1.2)
    
- TLS versione 1.1 (TLS 1.1)
    
- TLS versione 1.0 (TLS 1.0)
    
 Il supporto di TLS 1,0 e TLS 1,1 diventerà obsoleto il 31 ottobre 2018. Per ulteriori informazioni, vedere [deprecating support for TLS 1,0 e 1,1 e cosa significa questo per voi](technical-reference-details-about-encryption.md#TLS11and12deprecation) . 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>Supporto obsoleto per TLS 1,0 e 1,1 e cosa significa per te
<a name="TLS11and12deprecation"> </a>

Dal 31 ottobre 2018, Office 365 non supporta più TLS 1,0 e 1,1. Questo significa che Microsoft non risolverà i nuovi problemi che vengono rilevati in client, dispositivi o servizi che si connettono a Office 365 tramite TLS 1.0 e 1.1.

Si noti che questo non significa che Office 365 bloccherà le connessioni TLS 1,0 e 1,1. 

TLS 1,0 e TLS 1,1 saranno ufficialmente deprecati nelle date seguenti:
- 1 ° giugno 2020 per i clienti negli ambienti mondiali e GCC.
- 15 gennaio 2020 per i clienti nell'ambiente GCC High e DoD Sovereign. 

È necessario assicurarsi che tutte le combinazioni client-server e browser-server utilizzino TLS 1,2 (o versione successiva) per mantenere la connessione ai servizi di Office 365. Potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server. Per informazioni su come questo ha un impatto, vedere [preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Supporto obsoleto per 3DES
<a name="TLS11and12deprecation"> </a>

Dal 31 ottobre 2018, Office 365 non supporta più l'utilizzo di gruppi di crittografia 3DES per la comunicazione con Office 365. In particolare, Office 365 non supporta più la famiglia di crittografia TLS_RSA_WITH_3DES_EDE_CBC_SHA. Dal 28 febbraio 2019, questa famiglia di crittografia viene disabilitata in Office 365. I client e i server che comunicano con O365 dopo questa data devono supportare almeno una delle cifrature più sicure elencate in questo argomento (vedere [TLS Cipher Suites supportato da Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Sospensione del supporto relativo al certificato SHA-1 in Office 365
<a name="TLS11and12deprecation"> </a>

A giugno 2016, Office 365 non accetta più un certificato SHA-1 per le connessioni in uscita o in ingresso. Se si sta attualmente utilizzando un certificato con SHA-1 nella catena di certificati, sarà necessario aggiornare la catena per l'utilizzo di SHA-2 (Secure Hash Algorithm 2) o di un algoritmo di hash più robusto.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Gruppi di crittografia TLS supportati da Office 365
<a name="TLSCipherSuites"> </a>

Un pacchetto di crittografia è una raccolta di algoritmi di crittografia utilizzati da TLS per stabilire connessioni protette. I gruppi di crittografia supportati da Office 365 sono elencati nella tabella seguente in ordine di forza con il gruppo di crittografia più potente elencato per primo. Quando Office 365 riceve una richiesta di connessione, innanzitutto tenta di stabilire una connessione utilizzando il primo pacchetto di crittografia nell'elenco; in caso di esito negativo, tenta utilizzando il secondo pacchetto di crittografia nell'elenco e così via. Quando Office 365 invia una richiesta di connessione a un altro server o a un client, la scelta del pacchetto di crittografia da utilizzare o della possibilità o meno di utilizzare TLS dipende dal server o dal client ricevente.

> [!IMPORTANT]
> Tenere presente che le versioni di TLS sono obsolete e che *non è consigliabile utilizzare* le versioni obsolete in cui sono disponibili versioni più recenti. In altre parole, in qualsiasi luogo in cui è elencato che TLS 1,0, 1,1 e 1,2 sono supportati, scegliere la versione *più recente* (TLS 1,2).
  
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
[Suite di crittografia TLS in Windows 10 v1607](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Crittografia in Office 365](encryption.md)
  
[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md)
  
[Implementazione di SChannel di TLS 1,0 nell'aggiornamento dello stato di sicurezza di Windows: 24 novembre 2015](https://support.microsoft.com/kb/3117336)
  
[Miglioramenti della crittografia TLS/SSL (centro IT di Windows)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  

