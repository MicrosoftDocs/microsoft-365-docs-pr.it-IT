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
ms.openlocfilehash: ba01fa45ca9a4e2e5b3597378bf7ddafc8be3f56
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768747"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Informazioni sulla versione di valutazione di Microsoft Defender per Office 365

Microsoft Defender per Office 365 protegge l'organizzazione da minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. Defender per Office 365 include:

- **Criteri di protezione dalle minacce**: consente di definire i criteri di protezione dalle minacce per impostare il livello di protezione appropriato per l'organizzazione.
- **Report**: visualizzare report in tempo reale per monitorare le prestazioni di Defender per Office 365 nell'organizzazione.
- **Funzionalità di analisi e risposta alle minacce**: consente di usare strumenti all'avanguardia per analizzare, comprendere, simulare e prevenire minacce.
- **Funzionalità di analisi e risposta automatizzate**: consente di risparmiare tempo e fatica nell'analisi e nell'attenuazione delle minacce.

Una versione di valutazione di Microsoft Defender per Office 365 è il modo più semplice per provare le funzionalità di Defender per Office 365 e la configurazione richiede solo un paio di clic. Al termine della configurazione di valutazione, tutte le funzionalità di Defender per Office 365 Piano 1 e Piano 2 sono disponibili nell'organizzazione per un massimo di 90 giorni.

> [!NOTE]
> La configurazione automatica descritta in questo articolo è attualmente in Anteprima pubblica e potrebbe non essere disponibile nella posizione dell'utente.

## <a name="terms-and-conditions"></a>Termini e condizioni

La versione di valutazione di Defender per Office 365 è disponibile per 90 giorni e può essere avviata per tutti gli utenti. Per ulteriori informazioni, vedere Condizioni di valutazione di [Microsoft Defender per Office 365 & Condizioni](defender-for-office-365-trial-terms-and-conditions.md).

## <a name="set-up-a-defender-for-office-365-trial"></a>Configurare una versione di valutazione di Defender per Office 365

Una versione di valutazione consente alle organizzazioni di configurare e configurare facilmente le funzionalità di Defender per Office 365. Durante l'installazione, i criteri esclusivi di Defender per Office 365 (in [particolare,](safe-attachments.md)Allegati [sicuri,](safe-links.md)Collegamenti sicuri e protezione dalla rappresentazione nei criteri di protezione da posta [indesiderata)](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)vengono applicati utilizzando il modello Standard per i criteri di sicurezza [predefiniti.](preset-security-policies.md)

Per impostazione predefinita, questi criteri hanno come ambito tutti gli utenti dell'organizzazione, ma gli amministratori possono personalizzare i criteri durante o dopo l'installazione in modo che si applicino solo a utenti specifici.

Durante l'installazione, viene impostata anche la funzionalità di risposta MDO (disponibile in MDO P2 o equivalente) per l'intera organizzazione. Non è necessario alcun ambito dei criteri.

## <a name="licensing"></a>Licenze

Come parte della configurazione di valutazione, le licenze defender per Office 365 vengono applicate automaticamente all'organizzazione. Le licenze sono gratuite per i primi 90 giorni.

## <a name="permissions"></a>Autorizzazioni

Per avviare o terminare la versione di valutazione, è necessario essere membri dei ruoli **Amministratore** globale o Amministratore **della** sicurezza in Azure Active Directory. Per informazioni dettagliate, vedere [Informazioni sui ruoli di amministratore.](../../admin/add-users/about-admin-roles.md)

## <a name="additional-information"></a>Informazioni aggiuntive

Dopo la registrazione alla versione di valutazione, potrebbero essere necessarie fino a 2 ore prima che le modifiche e gli aggiornamenti siano disponibili. Inoltre, gli amministratori devono disconnettersi e accedere di nuovo per visualizzare le modifiche.

Gli amministratori possono disabilitare la versione di valutazione in qualsiasi momento andando alla <> carta.

## <a name="availability"></a>Disponibilità

La versione di valutazione di Defender per Office 365 viene gradualmente lanciata ai clienti esistenti che soddisfano criteri specifici (inclusa la geografia) e che non dispongono di licenze Defender per Office 365 Piano 1 o Piano 2 (incluse nell'abbonamento o come componente aggiuntivo).

## <a name="learn-more-about-defender-for-office-365"></a>Altre informazioni su Defender per Office 365

Defender per Office 365 aiuta le organizzazioni a proteggere la propria azienda offrendo un elenco completo di funzionalità.

Per altre informazioni su Defender per Office 365, vedere questa [guida interattiva.](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)

![Diagramma concettuale di Microsoft Defender per Office 365](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>Prevenzione

Un solido stack di filtro impedisce un'ampia gamma di attacchi mirati e basati su volume, tra cui la compromissione della posta elettronica aziendale, il phishing delle credenziali, il ransomware e il malware avanzato.

- [Criteri anti-phishing: impostazioni esclusive in Defender per Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Allegati sicuri](safe-attachments.md)
- [Collegamenti sicuri](safe-links.md)

### <a name="detection"></a>Rilevamento

L'IA leader del settore rileva contenuti dannosi e sospetti e correla i modelli di attacco per identificare le campagne progettate per evitare la protezione.

- [Visualizzazioni della campagna in Microsoft Defender per Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>Indagine e ricerca

Esperienze efficaci consentono di identificare, definire le priorità e analizzare le minacce, con funzionalità di ricerca avanzate per tenere traccia degli attacchi in Office 365.

- [Threat Explorer e rilevamenti in tempo reale](threat-explorer.md)
- [Report in tempo reale in Defender per Office 365](view-reports-for-mdo.md)
- [Threat Trackers - New and Noteworthy](threat-trackers.md)
- Integrazione con [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

### <a name="response-and-remediation"></a>Risposta e correzione

Ampie funzionalità di automazione e risposta agli incidenti amplificano l'efficacia e l'efficienza del team di sicurezza.

- [Analisi e risposta automatizzate (AIR) in Microsoft Defender per Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>Sensibilizzazione e formazione

Le funzionalità avanzate di simulazione e formazione e le esperienze integrate all'interno delle applicazioni client generano consapevolezza dell'utente.

- [Introduzione alla formazione sull’uso di Simulatore di attacchi](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>Postura sicura

I modelli consigliati e le informazioni dettagliate sulla configurazione consentono ai clienti di ottenere e mantenere la sicurezza.

- [Criteri di sicurezza predefiniti in EOP e Microsoft Defender per Office 365](preset-security-policies.md)
- [Analizzatore della configurazione per i criteri di protezione in EOP e Microsoft Defender per Office 365](configuration-analyzer-for-security-policies.md).

## <a name="give-feedback"></a>Inviare commenti e suggerimenti

Il tuo feedback ci aiuta a migliorare la protezione dell'ambiente da attacchi avanzati. Condividere l'esperienza e le impression delle funzionalità del prodotto e dei risultati della versione di valutazione.
