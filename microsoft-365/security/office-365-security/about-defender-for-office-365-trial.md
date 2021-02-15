---
title: Informazioni sulla versione di valutazione di Microsoft Defender per Office 365
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX
description: Gli amministratori possono conoscere la modalità di valutazione di Microsoft Defender per Office 365
ms.openlocfilehash: f5ab0b0cd4ef5c2bf1a799043af94a0938a53783
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114896"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Informazioni sulla versione di valutazione di Microsoft Defender per Office 365

Microsoft Defender per Office 365 protegge l'organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. Defender per Office 365 include:

- **Criteri di protezione dalle minacce**: consente di definire i criteri di protezione dalle minacce per impostare il livello di protezione appropriato per l'organizzazione.
- **Report:** consente di visualizzare report in tempo reale per monitorare le prestazioni di Defender 365 nell'organizzazione.
- **Funzionalità di analisi e risposta alle minacce**: consente di usare strumenti all'avanguardia per analizzare, comprendere, simulare e prevenire minacce.
- **Funzionalità di analisi e risposta automatizzate**: consente di risparmiare tempo e fatica nell'analisi e nell'attenuazione delle minacce.

Una versione di valutazione di Microsoft Defender per Office 365 è il modo più semplice per provare le funzionalità di Defender per Office 365 e la configurazione richiede solo un paio di clic. Al termine della configurazione della versione di valutazione, tutte le funzionalità di Defender per Office 365 Piano 1 e Piano 2 sono disponibili nell'organizzazione per un massimo di 90 giorni.

> [!NOTE]
> La configurazione automatica descritta in questo articolo è attualmente in anteprima pubblica e potrebbe non essere disponibile nella posizione dell'utente.

## <a name="terms-and-conditions"></a>Termini e condizioni

La versione di valutazione di Defender per Office 365 è disponibile per 90 giorni e può essere avviata per tutti gli utenti. Per ulteriori informazioni, vedere [Condizioni per l'utilizzo per la versione di valutazione di Microsoft Defender per Office 365.](terms-of-use-defender-for-office-365-trial.md)

## <a name="set-up-a-defender-for-office-365-trial"></a>Configurare una versione di valutazione di Defender per Office 365

Una versione di valutazione consente alle organizzazioni di configurare facilmente le funzionalità di Defender per Office 365. Durante l'installazione, i criteri esclusivi di Defender per Office 365 (in [particolare,](atp-safe-attachments.md)Allegati [sicuri,](atp-safe-links.md)Collegamenti sicuri e protezione dalla rappresentazione nei criteri di protezione dalla posta [indesiderata)](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)vengono applicati utilizzando il modello Standard per i criteri di sicurezza preimpostati. [](preset-security-policies.md)

Per impostazione predefinita, questi criteri hanno come ambito tutti gli utenti dell'organizzazione, ma gli amministratori possono personalizzare i criteri durante o dopo l'installazione in modo che siano applicabili solo a utenti specifici.

Durante l'installazione, la funzionalità di risposta MDO (disponibile in MDO P2 o equivalente) viene impostata anche per l'intera organizzazione. Non è richiesto alcun ambito dei criteri.

## <a name="licensing"></a>Licenze

Come parte della configurazione di prova, le licenze di Defender per Office 365 vengono applicate automaticamente all'organizzazione. Le licenze sono gratuite per i primi 90 giorni.

## <a name="permissions"></a>Autorizzazioni

Per avviare o terminare la versione di valutazione, è necessario essere membri dei ruoli **Amministratore** globale o Amministratore **della** sicurezza in Azure Active Directory. Per informazioni dettagliate, vedere [Informazioni sui ruoli di amministratore.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

## <a name="additional-information"></a>Informazioni aggiuntive

Dopo la registrazione alla versione di valutazione, potrebbero essere necessarie fino a 2 ore prima che le modifiche e gli aggiornamenti siano disponibili. Inoltre, gli amministratori devono disconnettersi e accedere di nuovo per visualizzare le modifiche.

Gli amministratori possono disabilitare la versione di valutazione in qualsiasi momento andando alla <> carta.

## <a name="availability"></a>Disponibilità

La versione di valutazione di Defender per Office 365 è in fase di implementazione graduale per i clienti esistenti che soddisfano criteri specifici (inclusa la geografia) e che non dispongono di licenze defender per Office 365 Piano 1 o Piano 2 (incluse nella sottoscrizione o come componente aggiuntivo).

## <a name="learn-more-about-defender-for-office-365"></a>Ulteriori informazioni su Defender per Office 365

Defender per Office 365 consente alle organizzazioni di proteggere la propria azienda offrendo un'ampia gamma di funzionalità.

Per altre informazioni su Defender per Office 365, vedere questa [guida interattiva.](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)

![Diagramma concettuale di Microsoft Defender per Office 365](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>Prevenzione

Un solido stack di filtro impedisce un'ampia gamma di attacchi mirati e basati su volume, tra cui compromissione della posta elettronica aziendale, phishing delle credenziali, ransomware e malware avanzato.

- [Criteri anti-phishing: impostazioni esclusive in Defender per Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Allegati sicuri](atp-safe-attachments.md)
- [Collegamenti sicuri](atp-safe-links.md)

### <a name="detection"></a>Rilevamento

L'intelligenza artificiale leader del settore rileva contenuti dannosi e sospetti e correla i modelli di attacco per identificare le campagne progettate per eludere la protezione.

- [Visualizzazioni della campagna in Microsoft Defender per Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>Indagine e ricerca

Esperienze efficaci consentono di identificare, assegnare priorità e analizzare le minacce, con funzionalità di ricerca avanzate per tenere traccia degli attacchi in Office 365.

- [Esplora minacce e rilevamenti in tempo reale](threat-explorer.md)
- [Report in tempo reale in Defender per Office 365](view-reports-for-atp.md)
- [Tracker delle minacce - Nuovi e degni di nota](threat-trackers.md)
- Integrazione con [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)

### <a name="response-and-remediation"></a>Risposta e correzione

Ampie funzionalità di automazione e risposta a eventi imprevisti semplificano l'efficacia e l'efficienza del team di sicurezza.

- [Analisi e risposta automatizzate (AIR) in Microsoft Defender per Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>Sensibilizzazione e formazione

Le funzionalità avanzate di simulazione e formazione, insieme alle esperienze integrate all'interno delle applicazioni client, generano consapevolezza degli utenti.

- [Introduzione alla formazione sull’uso di Simulatore di attacchi](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>Posizione sicura

I modelli consigliati e le informazioni dettagliate sulla configurazione consentono ai clienti di ottenere e mantenere la sicurezza.

- [Criteri di sicurezza preimpostati in EOP e Microsoft Defender per Office 365](preset-security-policies.md)
- [Analizzatore della configurazione per i criteri di protezione in EOP e Microsoft Defender per Office 365.](configuration-analyzer-for-security-policies.md)

## <a name="give-feedback"></a>Inviare commenti e suggerimenti

Il feedback degli utenti ci aiuta a migliorare la protezione dell'ambiente da attacchi avanzati. Condividi l'esperienza e le impressioni delle funzionalità del prodotto e dei risultati delle versioni di valutazione.
