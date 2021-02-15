---
title: Deprecazione TLS 1.0 e 1.1 per Office 365
description: Descrive la deprecazione di TLS 1.0 e 1.1 per Office 365.
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
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777058"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>Deprecazione TLS 1.0 e 1.1 per Office 365
> [!IMPORTANT]
> Abbiamo temporaneamente interrotto l'applicazione della deprecazione di TLS 1.0 e 1.1 per i clienti commerciali a causa di COVID-19, ma poiché le catene di approvvigionamento sono state modificate e alcuni paesi si aprono di nuovo, stiamo reimpostando l'applicazione TLS per iniziare il 15 ottobre 2020 e l'implementazione continuerà nelle settimane e nei mesi successivi. 

A partire dal 31 ottobre 2018, i protocolli Transport Layer Security (TLS) 1.0 e 1.1 sono deprecati per il servizio Office 365. L'effetto per gli utenti finali dovrebbe essere minimo. Questa modifica è stata resa pubblica per oltre due anni, con il primo annuncio pubblico effettuato a dicembre 2017. Questo articolo ha lo scopo di coprire solo il client locale di Office 365 in relazione al servizio Office 365, ma può essere applicato anche a problemi TLS locali con Office e Office Online Server/Office Web Apps.

## <a name="office-and-tls-overview"></a>Panoramica di Office e TLS

Il client Office si basa sul servizio Web Windows (WINHTTP) per inviare e ricevere traffico tramite protocolli TLS. Il client di Office può utilizzare TLS 1.2 se il servizio Web del computer locale può utilizzare TLS 1.2. Tutti i client di Office possono utilizzare i protocolli TLS, in quanto i protocolli TLS e SSL fanno parte del sistema operativo e non sono specifici del client di Office.

### <a name="on-windows-8-and-later-versions"></a>In Windows 8 e versioni successive

Per impostazione predefinita, i protocolli TLS 1.2 e 1.1 sono disponibili se nessun dispositivo di rete è configurato per rifiutare il traffico TLS 1.2.

### <a name="on-windows-7"></a>In Windows 7

I protocolli TLS 1.1 e 1.2 non sono disponibili senza l'aggiornamento [KB 3140245.](https://support.microsoft.com/help/3140245) L'aggiornamento risolve questo problema e aggiunge la seguente chiave secondaria del Registro di sistema:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Gli utenti di Windows 7 che non dispongono di questo aggiornamento sono interessati dal 31 ottobre 2018. [KB 3140245](https://support.microsoft.com/help/3140245) include informazioni dettagliate su come modificare le impostazioni WINHTTP per abilitare i protocolli TLS.

#### <a name="more-information"></a>Altre informazioni

Il valore della chiave **del Registro di sistema DefaultSecureProtocols** descritta nell'articolo della Knowledge Base determina quali protocolli di rete possono essere utilizzati:

|Valore DefaultSecureProtocols|Protocollo abilitato|
|-|-|
|0x00000008|Consente di abilitare SSL 2.0 per impostazione predefinita|
|0x00000020|Consente di abilitare SSL 3.0 per impostazione predefinita|
|0x00000080|Consente di abilitare TLS 1.0 per impostazione predefinita|
|0x00000200|Consente di abilitare TLS 1.1 per impostazione predefinita|
|0x00000800|Consente di abilitare TLS 1.2 per impostazione predefinita|

## <a name="office-clients-and-tls-registry-keys"></a>Client di Office e chiavi del Registro di sistema TLS

È possibile fare riferimento a KB 4057306 Preparazione per l'uso obbligatorio di [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306) Questo è un articolo generale per gli amministratori IT ed è la documentazione ufficiale sulla modifica di TLS 1.2.

La tabella seguente mostra i valori delle chiavi del Registro di sistema appropriati nei client di Office 365 dopo il 31 ottobre 2018.

|Protocolli abilitati per il servizio Office 365 dopo il 31 ottobre 2018|Valore esadecimale|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Non è consigliabile utilizzare i protocolli SSL 2.0 e 3.0, che possono essere impostati anche utilizzando la chiave **DefaultSecureProtocols.** SSL 2.0 e 3.0 sono considerati protocolli deprecati. La procedura consigliata consiste nel terminare l'utilizzo di SSL 2.0 e SSL 3.0, anche se la decisione di eseguire questa operazione dipende in ultima analisi da ciò che meglio soddisfa le esigenze del prodotto. Per ulteriori informazioni sulle vulnerabilità di SSL 3.0, vedere [kb 3009008.](https://support.microsoft.com/help/3009008)

Puoi usare lo Strumento di calcolo Windows predefinito in modalità programmatore per configurare gli stessi valori delle chiavi del Registro di sistema di riferimento. Per ulteriori informazioni, vedere [l'aggiornamento KB 3140245 per abilitare TLS 1.1 e TLS 1.2](https://support.microsoft.com/help/3140245)come protocolli sicuri predefiniti in WinHTTP in Windows.

Indipendentemente dal fatto che l'aggiornamento di Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) sia installato o meno, la chiave secondaria del Registro di sistema DefaultSecureProtocols non è presente e deve essere aggiunta manualmente o tramite un oggetto Criteri di gruppo. In altri casi, a meno che non sia necessario personalizzare i protocolli sicuri abilitati o limitati, questa chiave non è necessaria. È necessario solo l'aggiornamento di Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)
