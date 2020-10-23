---
title: Deprecazione TLS 1.0 e 1.1 per Office 365
description: Descrive le funzionalità TLS 1,0 e 1,1 Deprecation per Office 365.
author: workshay
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
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: ab3685883ac08522ab9ea1ee0cf194ba263d9166
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681690"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>Deprecazione TLS 1.0 e 1.1 per Office 365
> [!IMPORTANT]
> Si è momentaneamente interrotto l'applicazione del protocollo di disapprovazione di TLS 1,0 e 1,1 per i clienti commerciali a causa di covid-19, ma poiché le catene di approvvigionamento sono state modificate e alcuni paesi si aprono, viene reimpostato l'applicazione TLS per iniziare il 15 ottobre, 2020 e l'implementazione continuerà nelle settimane e nei mesi seguenti. 

Al 31 ottobre 2018, i protocolli Transport Layer Security (TLS) 1,0 e 1,1 sono deprecati per il servizio Office 365. L'effetto per gli utenti finali dovrebbe essere minimo. Questa modifica è stata pubblicizzata da più di due anni, con il primo annuncio pubblico eseguito nel dicembre 2017. Questo articolo è destinato solo a coprire il client locale di Office 365 in relazione al servizio Office 365, ma può anche essere applicato ai problemi di TLS locali con Office e Office Online Server/Office Web Apps.

## <a name="office-and-tls-overview"></a>Panoramica di Office e TLS

Il client di Office si basa sul servizio Web Windows (WINHTTP) per l'invio e la ricezione del traffico su protocolli TLS. Il client di Office può utilizzare TLS 1,2 Se il servizio Web del computer locale può utilizzare TLS 1,2. Tutti i client di Office possono utilizzare i protocolli TLS, in quanto i protocolli TLS e SSL fanno parte del sistema operativo e non sono specifici del client di Office.

### <a name="on-windows-8-and-later-versions"></a>In Windows 8 e versioni successive

Per impostazione predefinita, i protocolli TLS 1,2 e 1,1 sono disponibili se non sono configurati dispositivi di rete per rifiutare il traffico TLS 1,2.

### <a name="on-windows-7"></a>In Windows 7

I protocolli TLS 1,1 e 1,2 non sono disponibili senza l'aggiornamento di [KB 3140245](https://support.microsoft.com/help/3140245) . L'aggiornamento consente di risolvere il problema e di aggiungere la seguente chiave secondaria del registro di sistema:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Gli utenti di Windows 7 che non dispongono di questo aggiornamento sono intaccati al 31 ottobre 2018. [KB 3140245](https://support.microsoft.com/help/3140245) contiene informazioni dettagliate su come modificare le impostazioni di WinHTTP per abilitare i protocolli TLS.

#### <a name="more-information"></a>Ulteriori informazioni

Il valore della chiave del registro di sistema **DefaultSecureProtocols** descritta nell'articolo della Knowledge base determina i protocolli di rete che è possibile utilizzare:

|Valore di DefaultSecureProtocols|Protocollo abilitato|
|-|-|
|0x00000008|Consente di abilitare SSL 2.0 per impostazione predefinita|
|0x00000020|Consente di abilitare SSL 3.0 per impostazione predefinita|
|0x00000080|Consente di abilitare TLS 1.0 per impostazione predefinita|
|0x00000200|Consente di abilitare TLS 1.1 per impostazione predefinita|
|0x00000800|Consente di abilitare TLS 1.2 per impostazione predefinita|

## <a name="office-clients-and-tls-registry-keys"></a>Client di Office e chiavi del registro di sistema TLS

È possibile fare riferimento a [KB 4057306 prepararsi per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306). Questo è un articolo generale per gli amministratori IT, ed è la documentazione ufficiale relativa alla modifica di TLS 1,2.

Nella tabella seguente vengono illustrati i valori della chiave del registro di sistema corretti nei client di Office 365 dopo il 31 ottobre 2018.

|Protocolli abilitati per il servizio Office 365 dopo il 31 ottobre 2018|Valore esadecimale|
|-|-|
|TLS 1,0 + 1,1 + 1,2|0x00000A80|
|TLS 1,1 + 1,2|0x00000A00|
|TLS 1,0 + 1,2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Non è consigliabile utilizzare i protocolli SSL 2,0 e 3,0, che possono essere impostati anche utilizzando la chiave **DefaultSecureProtocols** . I protocolli SSL 2,0 e 3,0 sono considerati obsoleti. La procedura consigliata consiste nel terminare l'utilizzo di SSL 2,0 e SSL 3,0, anche se la decisione di eseguire questa operazione dipende in ultima analisi da ciò che soddisfa meglio le esigenze del prodotto. Per ulteriori informazioni sulle vulnerabilità di SSL 3,0, fare riferimento a [KB 3009008](https://support.microsoft.com/help/3009008).

È possibile utilizzare la calcolatrice predefinita di Windows in modalità Programmatore per impostare gli stessi valori di chiave del registro di sistema di riferimento. Per ulteriori informazioni, vedere [aggiornamento di KB 3140245 per abilitare tls 1,1 e tls 1,2 come protocolli di sicurezza predefiniti in WinHTTP in Windows](https://support.microsoft.com/help/3140245).

Indipendentemente dal caso in cui l'aggiornamento di Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) sia installato o meno, la chiave secondaria del registro di sistema DefaultSecureProtocols non è presente e deve essere aggiunta manualmente o tramite un oggetto Criteri di gruppo. In altre informazioni, a meno che non sia necessario personalizzare i protocolli protetti abilitati o limitati, questa chiave non è necessaria. È necessario solo l'aggiornamento di Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).
