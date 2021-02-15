---
title: Dettagli tecnici di riferimento sulla crittografia
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
description: Informazioni sui diversi certificati, tecnologie e suite di crittografia TLS (Transport Layer Security) usate per la crittografia in Office 365 e Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 244d7a6cef6d77322475245435dafb6c89ab5353
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663429"
---
# <a name="technical-reference-details-about-encryption"></a>Dettagli tecnici di riferimento sulla crittografia

Fare riferimento a questo articolo per informazioni sui certificati, le tecnologie e le suite di crittografia TLS usate per la crittografia [in Office 365.](encryption.md) In questo articolo vengono inoltre fornite informazioni dettagliate sulle deprecate pianificate.
  
- Per informazioni generali, vedere [Crittografia in Office 365.](encryption.md)
- Per informazioni sulla configurazione, vedere [Configurare la crittografia in Office 365 Enterprise.](set-up-encryption.md)
- Per informazioni sulle suite di crittografia supportate da versioni specifiche di Windows, vedi Pacchetti di crittografia [in TLS/SSL (SCHANNEL SSP).](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gestione e proprietà dei certificati di Microsoft Office 365

Non è necessario acquistare o mantenere certificati per Office 365. Al contrario, Office 365 usa i propri certificati.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Standard di crittografia correnti e deprecazione pianificata

Per fornire la crittografia ottimale, Office 365 rivede regolarmente gli standard di crittografia supportati. A volte, i vecchi standard sono deprecati perché diventano obsoleti e meno sicuri. Questo articolo descrive le suite di crittografia attualmente supportate e altri standard e informazioni dettagliate sulle deprecate pianificate.

## <a name="fips-compliance-for-office-365"></a>Conformità FIPS per Office 365

Tutte le suite di crittografia supportate da Office 365 usano algoritmi accettabili in base a FIPS 140-2. Office 365 eredita le convalide FIPS da Windows (tramite SChannel). Per informazioni su Schannel, vedere [Cipher Suites in TLS/SSL (SChannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versioni di TLS supportati da Office 365

TLS e SSL precedenti a TLS sono protocolli crittografici che assicurano la protezione delle comunicazioni in rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. Office 365 supporta TLS versione 1.2 (TLS 1.2).

TLS versione 1.3 (TLS 1.3) non è attualmente supportato.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Supporto per la deprecazione di TLS 1.0 e 1.1

Office 365 ha interrotto il supporto di TLS 1.0 e 1.1 il 31 ottobre 2018. I nuovi problemi rilevati nei client, nei dispositivi o nei servizi che si connettono a Office 365 tramite TLS 1.0 e 1.1 non verranno risolti. La deprecazione ufficiale per gli ambienti GCC High e DoD è iniziata il 15 gennaio 2020. La deprecazione di TLS 1.0 e 1.1 per gli ambienti worldwide e GCC è iniziata il 15 ottobre 2020.

Per mantenere una connessione sicura ai servizi di Office 365 e Microsoft 365, tutte le combinazioni client-server e browser-server usano TLS 1.2 e le moderne suite di crittografia. A tale scopo, potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server. Per informazioni sull'impatto di questa modifica, vedere Preparazione per l'uso obbligatorio di [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>Rimozione del supporto per 3DES

Dal 31 ottobre 2018, Office 365 non supporta più l'uso delle suite di crittografia 3DES per la comunicazione con Office 365. In particolare, Office 365 non supporta più la TLS_RSA_WITH_3DES_EDE_CBC_SHA di crittografia. Dal 28 febbraio 2019, questa famiglia di prodotti di crittografia è stata disabilitata in Office 365. I client e i server che comunicano con Office 365 devono supportare una o più delle crittografia supportate. Per un elenco delle crittografia supportate, vedere pacchetti di crittografia [TLS supportati da Office 365.](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Sospensione del supporto relativo al certificato SHA-1 in Office 365

Da giugno 2016, Office 365 non accetta più un certificato SHA-1 per le connessioni in ingresso o in uscita. Utilizzare SHA-2 (Secure Hash Algorithm 2) o un algoritmo hash più sicuro nella catena di certificati.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Pacchetti di crittografia TLS supportati da Office 365

TLS utilizza *pacchetti di crittografia,* raccolte di algoritmi di crittografia, per stabilire connessioni sicure. Office 365 supporta le suite di crittografia elencate nella tabella seguente. La tabella elenca le suite di crittografia in ordine di forza, con la famiglia di prodotti di crittografia più forte elencata per prima.

Office 365 risponde a una richiesta di connessione tentando innanzitutto di connettersi utilizzando la famiglia di prodotti di crittografia più sicura. Se la connessione non funziona, Office 365 tenta la seconda famiglia di prodotti di crittografia più sicura nell'elenco e così via. Il servizio continua verso il basso nell'elenco fino a quando la connessione non viene accettata. Allo stesso modo, quando Office 365 richiede una connessione, il servizio di ricezione sceglie se verrà utilizzato TLS e quale famiglia di prodotti di crittografia usare.

> [!IMPORTANT]
> Tenere presente che le versioni TLS sono deprecate e che le versioni deprecate non devono essere *usate* dove sono disponibili versioni più recenti. TLS 1.3 non è attualmente supportato. Se i servizi legacy non richiedono TLS 1.0 o 1.1, è necessario disabilitarli.

| Famiglia di prodotti di crittografia | Algoritmo/forza di scambio delle chiavi | Perfect Forward Secrecy | Crittografia/forza | Algoritmo di autenticazione |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Sì <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Sì <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |No <br/> |AES/256 <br/>|RSA/112 <br/> |

Queste suite di crittografia supportano i protocolli TLS 1.0 e 1.1 fino alla data di deprecazione. Per gli ambienti GCC High e DoD la data di deprecazione era il 15 gennaio 2020 e per gli ambienti in tutto il mondo e GCC la data era il 15 ottobre 2020.

| Protocolli | Nome del pacchetto di crittografia | Algoritmo/forza di scambio delle chiavi | Supporto per Perfect Forward Secrecy | Algoritmo di autenticazione/Complessità | Crittografia/forza |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |No  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |No   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Articoli correlati

[Pacchetti di crittografia TLS in Windows 10 v1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Crittografia in Office 365](encryption.md)
  
[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md)
  
[Implementazione SChannel di TLS 1.0 nell'aggiornamento dello stato di sicurezza di Windows: 24 novembre 2015](https://support.microsoft.com/kb/3117336)
  
[Miglioramenti della crittografia TLS/SSL (Windows IT Center)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Preparazione per TLS 1.2 in Office 365 e Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
