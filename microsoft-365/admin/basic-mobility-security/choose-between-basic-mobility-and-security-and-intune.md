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
ms.openlocfilehash: ec3ffa8879bf14ab3116bbbbf5cf2a1a3fd7c6e6
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053802"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Scegliere tra Dispositivi mobili di base e Sicurezza o Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) è un prodotto autonomo incluso in alcuni piani di Microsoft 365, mentre Basic Mobility and Security fa parte dei piani di Microsoft 365.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilità di dispositivi mobili e sicurezza di base e Intune

Sia Basic Mobility che Security e Intune sono inclusi in un'ampia gamma di piani, descritti nella tabella seguente.

| Piano | Basic Mobility + Security | Microsoft Intune |
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
>Non è possibile iniziare a usare Basic Mobility and Security se si usa già Microsoft Intune.

 Per informazioni dettagliate, vedere le descrizioni dei servizi della piattaforma [Microsoft 365 e Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Differenze nelle funzionalità

Microsoft Intune e basic mobility and Security incorporati offrono entrambi la possibilità di gestire i dispositivi mobili nell'organizzazione, ma esistono differenze chiave nelle funzionalità, descritte nella tabella seguente.

>[!NOTE]
>È possibile gestire gli utenti e i loro dispositivi mobili usando sia Intune che Basic Mobility and Security nella stessa organizzazione di Microsoft 365 Business Standard configurando prima Basic Mobility and Security e quindi aggiungendo *Microsoft Intune.* In questo modo è possibile scegliere Basic Mobility and Security o la soluzione Intune più ricca di funzionalità. Assegnare una licenza di Intune per abilitare le funzionalità di Intune.

| Area funzionale | Caratteristiche principali | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipi di dispositivi|Gestione di diverse piattaforme del sistema operativo e varianti principali della modalità di gestione. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Conformità dispositivo|Impostare e gestire i criteri di sicurezza, come il blocco PIN a livello di dispositivo e il rilevamento jailbreak. |Limitazioni per i dispositivi Android 9 e versioni successive. Vedere [i dettagli.](capabilities.md) |Sì|
|Accesso condizionale in base alla conformità dei dispositivi |Impedire ai dispositivi non conformi di accedere alla posta elettronica e ai dati aziendali dal cloud. |Non supportato in Windows 10.<br/>Limitato al controllo dell'accesso a Exchange Online, SharePoint Online e Outlook. |Sì |
|Configurazione delle periferiche  |Configurare le impostazioni del dispositivo (ad esempio, disabilitare la fotocamera)|Set limitato di impostazioni.|Sì|
|Conformità dispositivo  |Impostare e gestire i criteri di sicurezza, come il blocco PIN a livello di dispositivo e il rilevamento jailbreak. |Limitazioni per i dispositivi Android 9 e versioni successive. Vedere [i dettagli.](capabilities.md) |Sì|
|Profili di posta elettronica  |Effettuare il provisioning di un profilo di posta elettronica nativo nel dispositivo. |Sì|Sì|
|Profili WiFi |Esegui il provisioning di un profilo WiFi nativo nel dispositivo. |No|Sì|
|Profili VPN |Effettuare il provisioning di un profilo VPN nativo nel dispositivo. |No|Sì|
|Gestione delle applicazioni di sicurezza e mobilità di base  |Distribuisci le tue app line-of-business interne e dagli archivi app agli utenti. |No|Sì|
|Protezione delle applicazioni mobili  |Consentire agli utenti di accedere in modo sicuro alle informazioni aziendali utilizzando le app per dispositivi mobili e line-of-business di Office che conoscono, garantendo al contempo la sicurezza dei dati, limitando azioni come copia, taglia, incolla e salva con nome solo alle app gestite approvate per i dati aziendali. Funziona anche se i dispositivi non sono registrati in Basic Mobility and Security. Vedi Proteggere i dati delle app con i criteri MAM. |No|Sì|
|Browser gestito  |Abilitare un'esplorazione Web più sicura con l'app Edge. |No|Sì|
|Programmi di registrazione Zero Touch Autopilot) |Registrare un numero elevato di dispositivi di proprietà dell'azienda, semplificando al contempo la configurazione degli utenti. |No|Sì|
|||

Oltre alle funzionalità elencate nella tabella precedente, Basic Mobility and Security e Intune includono un set di azioni remote che inviano comandi ai dispositivi tramite Internet. Ad esempio, è possibile rimuovere i dati di Office dal dispositivo di un dipendente lasciando i dati personali sul posto (ritiro), rimuovere le app di Office dal dispositivo di un dipendente (cancellazione) o ripristinare le impostazioni di fabbrica di un dispositivo (cancellazione completa). 

Le azioni remote di base per dispositivi mobili e sicurezza includono il ritiro, la cancellazione e la cancellazione completa. Per ulteriori informazioni sulle azioni di sicurezza e mobilità di base, vedere Funzionalità [di sicurezza e mobilità di base.](capabilities.md)

Con Intune hai il seguente set di azioni:

-   Reimpostazione autopilot (solo Windows)
-  [Rotazione della chiave](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   Bitlocker (solo Windows)
-  [Usare cancellazione, ritiro o annullamento manuale della registrazione del dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Disabilitare loc di attivazione](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (solo iOS)
-  [Nuovo inizio](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (solo Windows)
- [Analisi completa](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (solo Windows 10)
- [Individuare il dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (solo iOS)
- [Modalità persa](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (solo iOS) - [Analisi rapida](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(solo Windows 10)
- [Controllo remoto per Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Blocco remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Rinomina dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Reimpostare il riavvio del passcode](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (solo Windows)
-  Aggiornare Windows Defender Security Intelligence (solo Windows)
-  Reimpostazione del PIN di Windows 10 (solo Windows)
-  [Inviare notifiche personalizzate](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, sistema operativo iPad)
-  [Sincronizzare il dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Per ulteriori informazioni sulle azioni di Intune, vedere la [documentazione di Microsoft Intune.](https://docs.microsoft.com/mem/intune/)
