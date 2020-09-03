---
title: Scegliere tra mobilità e sicurezza di base e Intune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: La sicurezza e la mobilità di base fanno parte dei piani di Microsoft 365.
ms.openlocfilehash: d4595428dd2e2b14948b9f788720fcadcf9eb895
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336951"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>Scegliere tra mobilità e sicurezza di base e Intune

Microsoft Intune è un prodotto autonomo incluso in alcuni piani di Microsoft 365, mentre Basic Mobility & Security è parte dei piani di Microsoft 365. Entrambi sono inclusi in una serie di piani, descritti nella tabella seguente.

|**Piano**|**Mobilità e sicurezza di base**|**Microsoft Intune**|
|:-----|:-----|:-----|
|Microsoft 365 Apps|Sì|No|
|Microsoft 365 Business Basic|Sì|No|
|Microsoft 365 Business Standard|Sì|No|
|Office 365 E1 |Sì|No|
|Office 365 E3 |Sì|No|
|Office 365 E5 |Sì|No|
|Microsoft 365 Business Premium |Sì|Sì|
|Microsoft 365 FIRSTLINE 3 |Sì|Sì|
|Microsoft 365 Enterprise E3 |Sì|Sì|
|Microsoft 365 Enterprise E5 |Sì|Sì|
|Microsoft 365 Eductation a1 |Sì|Sì|
|Microsoft 365 Education A3 |Sì|Sì|
|Microsoft 365 Education A5 |Sì|Sì|
|Microsoft Intune |No|Sì|
|Sicurezza dell'organizzazione & Enterprise Mobility |No|Sì|
|Sicurezza di Enterprise Mobility & E5 |No|Sì|

>[!NOTE]
>Non è possibile iniziare a utilizzare la sicurezza e la mobilità di base se si sta già utilizzando Microsoft Intune.

## <a name="differences-in-capabilities"></a>Differenze nelle funzionalità

Microsoft Intune e la sicurezza e la mobilità di base incorporati offrono la possibilità di gestire i dispositivi mobili nell'organizzazione, ma sono presenti differenze sostanziali nelle funzionalità descritte nella tabella seguente.

>[!NOTE]
>È possibile gestire gli utenti e i propri dispositivi mobili utilizzando Intune e la mobilità di base e la sicurezza nella stessa organizzazione di Microsoft 365 business standard impostando prima la mobilità e la sicurezza di base e quindi aggiungendo Microsoft Intune. In questo modo è possibile scegliere se gestire i dispositivi di un utente con mobilità e sicurezza di base o con la soluzione di Intune più ricca di funzionalità. Nella modalità, l'assegnazione della licenza determina il servizio a cui è stato registrato il dispositivo. Assegnare una licenza di Intune per abilitare le funzionalità solo di Intune.

|**Area funzionale**|**Caratteristiche principali**|**Mobilità e sicurezza di base**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|Tipi di dispositivi|Diverse piattaforme del sistema operativo e varianti di modalità di gestione principali. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS<br/>sistema operativo iPad|
|Conformità dispositivo|Impostare e gestire i criteri di sicurezza, ad esempio il blocco PIN a livello di dispositivo e il rilevamento jailbreak. |Limitazioni su dispositivi Android 9 e versioni successive. Per informazioni dettagliate, vedere [funzionalità di base per dispositivi mobili e sicurezza](capabilities-of-basic-mobility-and-secruity.md).|Sì|
|Accesso condizionale basato sulla conformità del dispositivo |Impedire ai dispositivi non conformi di accedere alla posta elettronica aziendale e ai dati dal cloud. |-Non supportato in Windows 10.<br/>-Limitato a controllare l'accesso ai servizi di Exchange Online, SharePoint Online e Outlook. |No|
|Configurazione delle periferiche  |Configurare le impostazioni dei dispositivi (ad esempio, disabilitando la videocamera). |Set limitato di impostazioni.Per informazioni dettagliate, vedere [funzionalità di base per dispositivi mobili e sicurezza](capabilities-of-basic-mobility-and-secruity.md). |Sì|
|Azioni remote  |Inviare comandi ai dispositivi su Internet. Ad esempio, rimuovere i dati di Office dal dispositivo di un dipendente lasciando i dati personali sul posto (ritiro). |Ritiro<br/>Cancellazione<br/>Eliminazione|-Ripristino automatico (solo Windows)<br/>- Rotazione della chiave [BitLocker](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Solo Windows)<br/>- [Eliminare](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [Disattiva l'attivazione loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (solo iOS)<br/>- [Nuovo avvio](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Solo Windows)<br/>- [Analisi completa](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Solo Windows 10)<br/>- [Individuare il dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (solo iOS)<br/>- [Modalità persa](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (solo iOS)<br/>- [Analisi rapida](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(solo Windows 10)<br/>- [Telecomando per Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [Blocco remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [Rinomina dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [Reimposta codice di accesso](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [Riavvio](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (Solo Windows)<br/>- [Ritirare](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>-Aggiornare Windows Defender Security Intelligence (solo Windows)<br/>-Ripristino Windows 10 PIN (solo Windows)<br/>- [Cancellazione](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [Inviare notifiche personalizzate](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, sistema operativo iPad)<br/>- [Sincronizza dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|Profili di posta elettronica  |Eseguire il provisioning di un profilo di posta elettronica nativo nel dispositivo. |Sì|Sì|
|Profili WIFI |Provisioning di un profilo Wi-Fi nativo sul dispositivo. |No|Sì|
|Profili VPN |Provisioning di un profilo VPN nativo nel dispositivo. |No|Sì|
|Gestione delle applicazioni MDM  |Distribuire le app line-of-business interne e gli archivi delle app con gli utenti. |No|Sì|
|Protezione delle applicazioni per dispositivi mobili  |Consente agli utenti di accedere in modo sicuro alle informazioni aziendali utilizzando le app di Office Mobile e line-of-business che conoscono, garantendo la sicurezza dei dati contribuendo a limitare azioni come la copia, il taglio, la incolla e il salvataggio come, solo per le app gestite approvate per i dati aziendali. Funziona anche se i dispositivi non sono registrati in MDM. Vedere proteggere i dati delle app utilizzando i criteri MAM. |No|Sì|
|Browser gestito  |Abilitare la navigazione web più sicura utilizzando l'app Edge. |No|Sì|
|Programmi di registrazione a zero touch |Registrare un numero elevato di dispositivi di proprietà aziendale, semplificando la configurazione dell'utente. |No|Sì|
