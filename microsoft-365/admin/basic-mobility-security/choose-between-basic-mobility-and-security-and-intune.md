---
title: Scegliere tra Dispositivi mobili di base e sicurezza e Intune
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
description: La mobilità e la sicurezza di base fanno parte dei piani di Microsoft 365.
ms.openlocfilehash: b7b1d229e87a313a9567daed87f03452b1925a65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904265"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Scegliere tra Dispositivi mobili di base e sicurezza o Intune

[Microsoft Intune](/mem/intune/) è un prodotto autonomo incluso in alcuni piani di Microsoft 365, mentre Basic Mobility and Security fa parte dei piani di Microsoft 365.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilità di Dispositivi mobili e sicurezza di base e Intune

Sia Basic Mobility che Security e Intune sono inclusi in un'ampia gamma di piani, descritti nella tabella seguente.

| Pianificare | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 Apps|Sì|No|
|Microsoft 365 Business Basic|Sì|No|
|Microsoft 365 Business Standard|Sì|No|
|Office 365 E1 |Sì|No|
|Office 365 E3 |Sì|No|
|Office 365 E5 |Sì|No|
|Microsoft 365 Business Premium |Sì|Sì|
|Microsoft 365 Firstline 3 |Sì|Sì|
|Microsoft 365 Enterprise E3 |Sì|Sì|
|Microsoft 365 Enterprise E5 |Sì|Sì|
|Microsoft 365 Education A1 |Sì|Sì|
|Microsoft 365 Education A3 |Sì|Sì|
|Microsoft 365 Education A5 |Sì|Sì|
|Microsoft Intune |No|Sì|
|Enterprise Mobility & Security E3 |No|Sì|
|Enterprise Mobility & Security E5 |No|Sì|

>[!NOTE]
>Non è possibile iniziare a usare Dispositivi mobili e sicurezza di base se si usa già Microsoft Intune.

 Per informazioni dettagliate, vedere Descrizioni dei servizi della piattaforma [Microsoft 365 e Office 365.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Differenze nelle funzionalità

Microsoft Intune e Basic Mobility and Security incorporati offrono entrambe la possibilità di gestire i dispositivi mobili nell'organizzazione, ma esistono differenze fondamentali nelle funzionalità, descritte nella tabella seguente.

>[!NOTE]
>È possibile gestire gli utenti e i loro dispositivi mobili usando sia Intune che Basic Mobility and Security nella stessa organizzazione di Microsoft 365 Business Standard configurando prima Basic Mobility and Security e quindi aggiungendo *Microsoft Intune.* In questo modo è possibile scegliere dispositivi mobili e sicurezza di base o la soluzione Intune più ricca di funzionalità. Assegnare una licenza di Intune per abilitare le funzionalità di Intune.

| Area funzionale | Caratteristiche evidenziate | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipi di dispositivi|Gestione di diverse piattaforme del sistema operativo e varianti principali della modalità di gestione. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Conformità dispositivo|Imposta e gestisci i criteri di sicurezza, ad esempio il blocco PIN a livello di dispositivo e il rilevamento jailbreak. |Limitazioni sui dispositivi Android 9 e versioni successive. Vedere [i dettagli](capabilities.md). |Sì|
|Accesso condizionale in base alla conformità dei dispositivi |Impedire ai dispositivi non conformi di accedere alla posta elettronica aziendale e ai dati dal cloud. |Non supportato in Windows 10.<br/>Limitato al controllo dell'accesso a Exchange Online, SharePoint Online e Outlook. |Sì |
|Configurazione delle periferiche  |Configurare le impostazioni del dispositivo (ad esempio, disabilitando la fotocamera)|Set limitato di impostazioni.|Sì|
|Conformità dispositivo  |Imposta e gestisci i criteri di sicurezza, ad esempio il blocco PIN a livello di dispositivo e il rilevamento jailbreak. |Limitazioni sui dispositivi Android 9 e versioni successive. Vedere [i dettagli](capabilities.md). |Sì|
|Profili di posta elettronica  |Effettuare il provisioning di un profilo di posta elettronica nativo nel dispositivo. |Sì|Sì|
|Profili WiFi |Esegui il provisioning di un profilo WiFi nativo nel dispositivo. |No|Sì|
|Profili VPN |Effettuare il provisioning di un profilo VPN nativo nel dispositivo. |No|Sì|
|Gestione di applicazioni mobili  |Distribuisci le app line-of-business interne e dagli archivi app agli utenti. |No|Sì|
|Protezione delle applicazioni mobili  |Consentire agli utenti di accedere in modo sicuro alle informazioni aziendali utilizzando le app per dispositivi mobili e line-of-business di Office che conoscono, garantendo al contempo la sicurezza dei dati, contribuendo a limitare azioni quali copia, taglia, incolla e salva con nome, solo alle app gestite approvate per i dati aziendali. Funziona anche se i dispositivi non sono registrati in Dispositivi mobili e sicurezza di base. Vedi Proteggere i dati delle app con i criteri MAM. |No|Sì|
|Browser gestito  |Abilita un'esplorazione Web più sicura usando l'app Edge. |No|Sì|
|Programmi di registrazione zero tocco (AutoPilot) |Registrare un numero elevato di dispositivi di proprietà dell'azienda, semplificando al contempo la configurazione degli utenti. |No|Sì|
|||

Oltre alle funzionalità elencate nella tabella precedente, Basic Mobility and Security e Intune includono entrambi un set di azioni remote che inviano comandi ai dispositivi tramite Internet. Ad esempio, è possibile rimuovere i dati di Office dal dispositivo di un dipendente lasciando i dati personali sul posto (ritirare), rimuovere le app di Office dal dispositivo di un dipendente (cancellazione) o reimpostare un dispositivo alle impostazioni di fabbrica (cancellazione completa). 

Le azioni remote di base per dispositivi mobili e sicurezza includono ritiro, cancellazione e cancellazione completa. Per ulteriori informazioni sulle azioni di base per dispositivi mobili e sicurezza, vedere [capabilities of Basic Mobility and Security.](capabilities.md)

Con Intune hai il set di azioni seguente:

-   Reimpostazione autopilot (solo Windows
-  [Rotazione della chiave bitlocker](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (solo Windows)
-  [Usare cancellazione, ritiro o annullamento manuale della registrazione del dispositivo](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Disabilitare loc di attivazione](/mem/intune/remote-actions/device-activation-lock-disable)   (solo iOS)
-  [Nuovo inizio](/mem/intune/remote-actions/device-fresh-start)   (solo Windows)
- [Analisi completa](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (solo Windows 10)
- [Individuare il dispositivo](/mem/intune/remote-actions/device-locate)   (solo iOS)
- [Modalità persa](/mem/intune/remote-actions/device-lost-mode)   (solo iOS) - [Analisi rapida](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(solo Windows 10)
- [Controllo remoto per Android](/mem/intune/remote-actions/teamviewer-support)
- [Blocco remoto](/mem/intune/remote-actions/device-remote-lock)
- [Rinomina dispositivo](/mem/intune/remote-actions/device-rename)
-  [Reimposta passcode](/mem/intune/remote-actions/device-passcode-reset) [Riavvia](/mem/intune/remote-actions/device-restart)   (solo Windows)
-  Aggiornare Windows Defender Security Intelligence (solo Windows)
-  Reimpostazione del PIN di Windows 10 (solo Windows)
-  [Inviare notifiche personalizzate](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Sincronizza dispositivo](/mem/intune/remote-actions/device-sync)

Per altre informazioni sulle azioni di Intune, vedi la [documentazione di Microsoft Intune.](/mem/intune/)