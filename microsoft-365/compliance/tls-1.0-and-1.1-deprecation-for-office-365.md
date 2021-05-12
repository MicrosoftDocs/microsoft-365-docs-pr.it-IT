---
title: Disabilitazione di TLS 1.0 e 1.1 per Microsoft 365
description: Descrive la deprecazione e la disabilitazione di TLS 1.0 e 1.1 per Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332679"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Disabilitazione di TLS 1.0 e 1.1 per Microsoft 365

> [!IMPORTANT]
> Abbiamo temporaneamente interrotto la disabilitazione di TLS 1.0 e 1.1 per i clienti commerciali a causa di COVID-19. Con l'aggiustamento delle catene di approvvigionamento e l'apertura di alcuni paesi, l'implementazione dell'imposizione TLS 1.2 è stata riavviata il 15 ottobre 2020. L'implementazione continuerà nelle settimane e nei mesi successivi.

A partire dal 31 ottobre 2018, i protocolli Transport Layer Security (TLS) 1.0 e 1.1 sono deprecati per il servizio Microsoft 365. L'effetto per gli utenti finali è minimo. Questo cambiamento è stato reso pubblico per oltre due anni, con il primo annuncio pubblico fatto a dicembre 2017. Questo articolo ha lo scopo di coprire solo il client locale di Office 365 in relazione al servizio Office 365, ma può essere applicato anche ai problemi TLS locali con Office e Office Online Server/Office Web Apps.

Per SharePoint e OneDrive, è necessario aggiornare e configurare .NET per supportare TLS 1.2. Per informazioni, vedere [Come abilitare TLS 1.2 nei client.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="office-365-and-tls-overview"></a>Office 365 e TLS

Il client Office si basa sul servizio Web Windows (WINHTTP) per inviare e ricevere traffico su protocolli TLS. Il Office client può utilizzare TLS 1.2 se il servizio Web del computer locale può utilizzare TLS 1.2. Tutti Office client possono utilizzare i protocolli TLS, poiché i protocolli TLS e SSL fanno parte del sistema operativo e non sono specifici del client Office client.

### <a name="on-windows-8-and-later-versions"></a>In Windows 8 versioni successive

Per impostazione predefinita, i protocolli TLS 1.2 e 1.1 sono disponibili se nessun dispositivo di rete è configurato per rifiutare il traffico TLS 1.2.

### <a name="on-windows-7"></a>In Windows 7

I protocolli TLS 1.1 e 1.2 non sono disponibili senza l'aggiornamento [KB 3140245.](https://support.microsoft.com/help/3140245) L'aggiornamento risolve questo problema e aggiunge la seguente chiave secondaria del Registro di sistema:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7 utenti che non dispongono di questo aggiornamento sono interessati dal 31 ottobre 2018. [KB 3140245](https://support.microsoft.com/help/3140245) contiene informazioni dettagliate su come modificare le impostazioni WINHTTP per abilitare i protocolli TLS.

#### <a name="more-information"></a>Ulteriori informazioni

Il valore della chiave del Registro di sistema **DefaultSecureProtocols** descritto nell'articolo della Knowledge Base determina quali protocolli di rete possono essere utilizzati:

|Valore DefaultSecureProtocols|Protocollo abilitato|
|-|-|
|0x00000008|Consente di abilitare SSL 2.0 per impostazione predefinita|
|0x00000020|Consente di abilitare SSL 3.0 per impostazione predefinita|
|0x00000080|Consente di abilitare TLS 1.0 per impostazione predefinita|
|0x00000200|Consente di abilitare TLS 1.1 per impostazione predefinita|
|0x00000800|Consente di abilitare TLS 1.2 per impostazione predefinita|

## <a name="office-clients-and-tls-registry-keys"></a>Office client e chiavi del Registro di sistema TLS

È possibile fare riferimento [a KB 4057306 Preparazione](https://support.microsoft.com/help/4057306)per l'utilizzo obbligatorio di TLS 1.2 in Office 365 . Questo è un articolo generale per gli amministratori IT ed è la documentazione ufficiale sulla modifica di TLS 1.2.

La tabella seguente mostra i valori appropriati delle chiavi del Registro di sistema nei client Office 365 dopo il 31 ottobre 2018.

|Protocolli abilitati per Office 365 servizio dopo il 31 ottobre 2018|Valore esadecimale|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Non utilizzare i protocolli SSL 2.0 e 3.0, che possono essere impostati anche utilizzando la chiave **DefaultSecureProtocols.** SSL 2.0 e 3.0 sono considerati protocolli obsoleti e non sicuri. La procedura consigliata consiste nel terminare l'utilizzo di SSL 2.0 e SSL 3.0, anche se la decisione di eseguire questa operazione dipende in ultima analisi da ciò che meglio soddisfa le esigenze del prodotto. Per ulteriori informazioni sulle vulnerabilità di SSL 3.0, vedere [KB 3009008](https://support.microsoft.com/help/3009008).

Puoi usare la calcolatrice Windows predefinita in modalità programmatore per impostare gli stessi valori delle chiavi del Registro di sistema di riferimento. Per ulteriori informazioni, vedere [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).

Indipendentemente dal fatto che l'aggiornamento di Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) sia installato o meno, la sottochiave del Registro di sistema DefaultSecureProtocols non è presente e deve essere aggiunta manualmente o tramite un oggetto Criteri di gruppo. In altri casi, a meno che non sia necessario personalizzare i protocolli sicuri abilitati o limitati, questa chiave non è necessaria. È necessario solo l'Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Aggiornare e configurare il .NET Framework per supportare TLS 1.2

Dovrai aggiornare le applicazioni che chiamano Microsoft 365 API su TLS 1.0 o TLS 1.1 per usare TLS 1.2. .NET 4.5 per impostazione predefinita è TLS 1.1. Per aggiornare la configurazione .NET, vedere [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="more-information"></a>Ulteriori informazioni

Per ulteriori informazioni, vedere [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="references"></a>Riferimenti

Le risorse seguenti forniscono indicazioni per assicurarsi che i client utilizzino TLS 1.2 o versione successiva e per disabilitare TLS 1.0 e 1.1:

- Per client Windows 7 connessi a Office 365, verificare che TLS 1.2 sia impostato come protocollo di sicurezza predefinito nel servizio WinHTTP di Windows. Per ulteriori informazioni, vedere [KB 3140245 - Aggiornamento per abilitare TLS 1.1 e TLS 1.2 come protocolli](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)sicuri predefiniti in WinHTTP in Windows .
- Per risolvere l'utilizzo debole di TLS rimuovendo le dipendenze TLS 1.0 e 1.1, vedere [Supporto di TLS 1.2 in Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- Le [nuove funzionalità di IIS](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) semplificano l'individuazione dei client nei sistemi [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) e [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) che si connettono al servizio utilizzando protocolli di sicurezza inefficaci.
- Ottenere ulteriori informazioni su come [risolvere il problema di TLS 1.0.](https://www.microsoft.com/download/details.aspx?id=55266)
- Per informazioni generali sull'approccio di Microsoft alla sicurezza, visitare il [Centro protezione di Office 365](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Preparazione alla deprecazione di TLS 1.0/1.1 - Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Linee guida TLS di Exchange Server, parte 1: Prepararsi per TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Linee guida TLS di Exchange Server Parte 2: Abilitazione di TLS 1.2 e identificazione dei client che non lo utilizzano](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Linee guida TLS di Exchange Server Parte 3: Disattivazione di TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Abilitare il supporto per TLS 1.1 e TLS 1.2 in Office Online Server](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

