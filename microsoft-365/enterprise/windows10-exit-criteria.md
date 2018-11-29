---
title: "Fase 3: criteri uscita dell'infrastruttura Windows 10 Enterprise"
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 06/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise per Windows 10 Enterprise.
ms.openlocfilehash: 7ac79fec93e4b4aae0b075891917e2f88432b80f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868668"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>Fase 3: criteri uscita dell'infrastruttura Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Se l'infrastruttura Windows 10 Enterprise soddisfa i seguenti requisiti, è possibile procedere alla Fase 4.

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>Obbligatorio: i domini Microsoft 365 sono stati aggiunti e verificati

Il tenant di Azure AD per le sottoscrizioni di Office 365 e Intune è configurato con i nomi di dominio Internet (come contoso.com), anziché con un solo nome di dominio che include "onmicrosoft.com". 

Se non si esegue questa operazione, l'utente sarà limitato nei metodi di autenticazione che è possibile configurare. Ad esempio, l'autenticazione pass-through e federata non può utilizzare il nome di dominio "onmicrosoft.com".

Se necessario, il [Passaggio 1](windows10-prepare-your-org.md) può aiutare a soddisfare questo requisito.

## <a name="optional-your-users-are-added-and-licensed"></a>Facoltativo: gli utenti vengono aggiunti e ricevono una licenza

Gli account corrispondenti agli utenti vengono aggiunti direttamente al tenant di Azure AD per le sottoscrizioni di Office 365 e Intune o dalla sincronizzazione della directory dall'AD di Windows Server locale.

Una volta aggiunti gli utenti, è possibile assegnare loro le licenze Microsoft 365 Enterprise, direttamente come amministratore globale o utente o automaticamente tramite l'appartenenza al gruppo.

Se necessario, il [Passaggio 1](windows10-prepare-your-org.md) può aiutare con questa opzione.

## <a name="optional-diagnostics-are-enabled"></a>Facoltativo: Diagnostica è abilitata

Le impostazioni dei dati di diagnostica sono state abilitate tramite Criteri di gruppo, Microsoft Intune, l'editor del Registro di sistema o al prompt dei comandi.

Se necessario, il [Passaggio 1](windows10-prepare-your-org.md) può aiutare con questa opzione.

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>Obbligatorio per l'aggiornamento sul posto: creata una sequenza di attività di Gestione configurazione per una distribuzione del sistema operativo

Per avviare una sequenza di attività di Gestione configurazione per eseguire un aggiornamento sul posto di un dispositivo con Windows 7 o Windows 8.1, è necessario:

- Impostare il corretto livello dei dati di diagnostica di Windows
- Verificare la disponibilità a eseguire l'aggiornamento di Windows
- Creare una sequenza di attività di Gestione configurazione che includa una raccolta di dispositivi e una distribuzione del sistema operativo con un'immagine del sistema operativo Windows 10

Dopo questa operazione, è possibile eseguire aggiornamenti sul posto su dispositivi pronti per aggiornare Windows. Per trarre il massimo vantaggio da Microsoft 365 Enterprise, aggiornare il maggior numero possibile di dispositivi con Windows 7 e Windows 8.1. 

Ogni dispositivo che esegue Windows 10 Enterprise può ottenere i vantaggi della soluzione integrata di Microsoft 365 Enterprise. I restanti dispositivi che eseguono Windows 7 o Windows 8.1 non possono utilizzare le tecnologie connesse al cloud e le funzionalità di sicurezza avanzate di Windows 10 Enterprise.

Se necessario, il [Passaggio 2](windows10-deploy-inplaceupgrade.md) può aiutare a soddisfare questo requisito.

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>Obbligatorio per i nuovi dispositivi: Windows Autopilot configurato

Per utilizzare Windows Autopilot per distribuire e personalizzare Windows 10 Enterprise su un nuovo dispositivo, è necessario:

- Impostare il corretto livello dei dati di diagnostica di Windows
- Completare i prerequisiti per Windows Autopilot, che includono:
- Registrazione del dispositivo e personalizzazione Configurazione guidata
- Informazioni personalizzate distintive dell'azienda per Configurazione guidata
- Registrazione automatica MDM in Microsoft Intune
- Connettività di rete ai servizi cloud utilizzati da Windows Autopilot
- Dispositivi preinstallati con Windows 10, versione 1703 o successiva
- Selezionare il programma Windows Autopilot Deployment per la propria organizzazione

Una volta eseguita la configurazione di Windows Autopilot, è possibile utilizzarla per configurare e personalizzare Windows 10 Enterprise per la configurazione guidata (OOBE) di:

- Nuovi dispositivi
- Dispositivi per i quali è stata già completata una configurazione guidata nell'organizzazione. 

Windows Autopilot configura il dispositivo e lo collega ad Azure AD.

In mancanza di Windows Autopilot, è necessario configurare manualmente nuovi dispositivi, inclusa la connessione ad Azure AD.

Se necessario, il [Passaggio 3](windows10-deploy-autopilot.md) può aiutare a soddisfare questo requisito.

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>Facoltativo: utilizzo di Integrità del dispositivo di Windows Analytics per monitorare i dispositivi basati su Windows 10 Enterprise

Le informazioni sono state utilizzate in Monitoraggio dell'integrità dei dispositivi con Integrità del dispositivo per rilevare e risolvere i problemi che interessano gli utenti finali. Affrontare in modo rapido i problemi degli utenti finali può ridurre i costi di assistenza e dimostrare agli utenti l'impegno IT per Windows 10 Enterprise, che può aiutare l'adozione in tutta l'organizzazione. 

Se necessario, il [Passaggio 4](windows10-enable-windows-analytics.md) può aiutare con questa opzione.

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>Obbligatorio: utilizzo di Windows Defender Antivirus o la propria soluzione antimalware

Windows Defender Antivirus o la propria soluzione antivirus sono stati distribuiti per proteggere i dispositivi che eseguono Windows 10 Enterprise da software dannoso. Se è stato distribuito Windows Defender Antivirus, è stato implementato un metodo di segnalazione, come System Center Configuration Manager o Microsoft Intune, per monitorare eventi e attività antivirus.

Se necessario, il [Passaggio 5](windows10-enable-security-features.md#windows10-sec-av) può aiutare a soddisfare questo requisito.

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>Obbligatorio: utilizzo di Windows Defender Exploit Guard

Windows Defender Exploit Guard è stato distribuito per proteggere i dispositivi che eseguono Windows 10 Enterprise da intrusioni ed è stato implementato un metodo di segnalazione, come System Center Configuration Manager o Microsoft Intune, per monitorare eventi e attività di intrusione.

Se necessario, il [Passaggio 5](windows10-enable-security-features.md#windows10-sec-eg) può aiutare a soddisfare questo requisito.

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-windows-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a>Obbligatorio: utilizzo di Windows Defender Advanced Threat Protection (solo Microsoft 365 Enterprise E5)

Windows Defender Advanced Threat Protection Defender (ATP) è stato distribuito per rilevare, investigare e rispondere alle minacce avanzate contro la rete e i dispositivi che eseguono Windows 10 Enterprise. 

Opzionalmente, Windows Defender ATP viene integrato con altri strumenti per espandere le proprie capacità.

Se necessario, il [Passaggio 5](windows10-enable-security-features.md#windows10-sec-atp) può aiutare a soddisfare questo requisito.


## <a name="next-phase"></a>Fase successiva

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| La fase successiva del processo di distribuzione end-to-end per Microsoft 365 Enterprise è [Office 365 ProPlus](office365proplus-infrastructure.md). |
