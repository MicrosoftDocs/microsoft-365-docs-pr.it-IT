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
ms.openlocfilehash: cfd1a68c313d1a1335490e2b8d6938de192fe3f3
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877093"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Scegliere tra mobilità e sicurezza di base o Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) è un prodotto autonomo incluso in alcuni piani di Microsoft 365, mentre la mobilità e la sicurezza di base fanno parte dei piani di Microsoft 365. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilità di dispositivi mobili e sicurezza di base e Intune
 
Sia la mobilità che la sicurezza di base e Intune sono inclusi in una serie di piani, descritti nella tabella seguente.

| Piano | Basic Mobility + Security | Microsoft Intune |
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
|Microsoft 365 Education a1 |Sì|Sì|
|Microsoft 365 Education A3 |Sì|Sì|
|Microsoft 365 Education A5 |Sì|Sì|
|Microsoft Intune |No|Sì|
|Sicurezza dell'organizzazione & Enterprise Mobility |No|Sì|
|Sicurezza di Enterprise Mobility & E5 |No|Sì|

>[!NOTE]
>Non è possibile iniziare a utilizzare la sicurezza e la mobilità di base se si sta già utilizzando Microsoft Intune.

 Per informazioni dettagliate, vedere [Microsoft 365 e Office 365 Platform Service Descriptions](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). 

## <a name="differences-in-capabilities"></a>Differenze nelle funzionalità

Microsoft Intune e la sicurezza e la mobilità di base incorporati offrono la possibilità di gestire i dispositivi mobili nell'organizzazione, ma sono presenti differenze sostanziali nelle funzionalità descritte nella tabella seguente.

>[!NOTE]
>È possibile gestire gli utenti e i propri dispositivi mobili utilizzando Intune e la mobilità di base e la sicurezza nella stessa organizzazione di Microsoft 365 business standard impostando *prima la mobilità e la sicurezza di base e quindi aggiungendo Microsoft Intune*. In questo modo è possibile scegliere mobilità e sicurezza di base o la soluzione più ricca di funzionalità di Intune. Assegnare una licenza di Intune per abilitare le funzionalità di Intune.

| Area funzionale | Caratteristiche principali | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipi di dispositivi|Gestione di diverse piattaforme del sistema operativo e varianti di modalità di gestione principali. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS, sistema operativo iPad|
|Conformità dispositivo|Impostare e gestire i criteri di sicurezza, ad esempio il blocco PIN a livello di dispositivo e il rilevamento jailbreak. |Limitazioni su dispositivi Android 9 e versioni successive. Vedere [Details](capabilities.md). |Sì|
|Accesso condizionale basato sulla conformità del dispositivo |Impedire ai dispositivi non conformi di accedere alla posta elettronica aziendale e ai dati dal cloud. |Non supportato in Windows 10.<br/>Limitato a controllare l'accesso a Exchange Online, SharePoint Online e Outlook. |Sì |
|Configurazione delle periferiche  |Configurare le impostazioni dei dispositivi (ad esempio, disabilitando la videocamera)|Set limitato di impostazioni.|Sì|
|Conformità dispositivo  |Impostare e gestire i criteri di sicurezza, ad esempio il blocco PIN a livello di dispositivo e il rilevamento jailbreak. |Limitazioni su dispositivi Android 9 e versioni successive. Vedere [Details](capabilities.md). |Sì|
|Profili di posta elettronica  |Eseguire il provisioning di un profilo di posta elettronica nativo nel dispositivo. |Sì|Sì|
|Profili WiFi |Provisioning di un profilo Wi-Fi nativo sul dispositivo. |No|Sì|
|Profili VPN |Provisioning di un profilo VPN nativo nel dispositivo. |No|Sì|
|Gestione delle applicazioni di sicurezza e mobilità di base  |Distribuire le app line-of-business interne e gli archivi delle app con gli utenti. |No|Sì|
|Protezione delle applicazioni per dispositivi mobili  |Consente agli utenti di accedere in modo sicuro alle informazioni aziendali utilizzando le app di Office Mobile e line-of-business che conoscono, garantendo la sicurezza dei dati contribuendo a limitare azioni come la copia, il taglio, la incolla e il salvataggio come, solo per le app gestite approvate per i dati aziendali. Funziona anche se i dispositivi non sono registrati alla sicurezza e alla mobilità di base. Vedere proteggere i dati delle app utilizzando i criteri MAM. |No|Sì|
|Browser gestito  |Abilitare la navigazione web più sicura utilizzando l'app Edge. |No|Sì|
|Programma automatico di registrazione di zero touch |Registrare un numero elevato di dispositivi di proprietà aziendale, semplificando la configurazione dell'utente. |No|Sì|
|||

Oltre alle funzionalità elencate nella tabella precedente, Basic Mobility and Security e Intune includono una serie di azioni remote che inviano comandi ai dispositivi su Internet. Ad esempio, è possibile rimuovere i dati di Office dal dispositivo di un dipendente lasciando i dati personali sul posto (andare in pensione), rimuovere le app di Office dal dispositivo (wipe) di un dipendente o reimpostare le impostazioni di fabbrica (full wipe) di un dispositivo. 

Le azioni remote sulla sicurezza e sulla mobilità includono il ritiro, il wipe e il wipe completo. Per ulteriori informazioni sulle azioni di sicurezza e sulla mobilità di base, vedere [funzionalità di base per dispositivi mobili e sicurezza](capabilities.md).

Con Intune è presente il set di azioni seguente:

-   Ripristino automatico (solo Windows
-  Rotazione della chiave [BitLocker](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Solo Windows)
-  [Utilizzare wipe, ritirare o annullare la registrazione manuale del dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Disattiva l'attivazione loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (solo iOS)
-  [Nuovo avvio](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Solo Windows)
- [Analisi completa](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Solo Windows 10)
- [Individuare il dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (solo iOS)
- [Modalità persa](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (solo iOS)- [analisi rapida](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(solo Windows 10)
- [Telecomando per Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Blocco remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Rinomina dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Reimposta](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [riavvio](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)del codice di accesso   (solo Windows)
-  Aggiornare Windows Defender Security Intelligence (solo Windows)
-  Ripristino di Windows 10 PIN (solo Windows)
-  [Inviare notifiche personalizzate](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, sistema operativo iPad)
-  [Sincronizza dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Per ulteriori informazioni sulle azioni di Intune, vedere [documentazione di Microsoft Intune](https://docs.microsoft.com/mem/intune/).
