---
title: Che cosa viene in Microsoft Secure Score?
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, in che modo vengono calcolati i dettagli e quali amministratori della sicurezza possono aspettarsi.
keywords: sicurezza, malware, Microsoft 365, M365, Punteggio sicuro, Centro sicurezza, azioni di miglioramento
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266974"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Che cosa viene in Microsoft Secure Score?

Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza e migliorare l'usabilità, vengono apportate alcune modifiche nel prossimo futuro. Il Punteggio e il punteggio massimo possono variare. Tuttavia, ciò non implica una modifica della posizione di sicurezza.

Per informazioni sulle modifiche recenti, vedere [What ' s New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)

## <a name="march-2nd-2020"></a>2 marzo 2020

### <a name="removing-improvement-actions-from-intune"></a>Rimozione di azioni di miglioramento da Intune

Dopo una valutazione delle azioni di miglioramento di Microsoft Secure Score forniti da Intune, è stato deciso che non forniscono una rappresentazione utile della posizione di sicurezza dei dispositivi nelle organizzazioni. Invece di concentrarsi sui criteri, stiamo lavorando per portare i controlli di sicurezza che valutano direttamente lo stato di configurazione dei dispositivi.

Verranno rimosse le seguenti azioni di miglioramento di Intune:

- Abilitare la gestione dei dispositivi mobili di Microsoft Intune
- Creare un criterio di conformità di Microsoft Intune per Android
- Creare un criterio di conformità di Microsoft Intune per Android per il lavoro
- Creare un criterio di protezione delle app di Microsoft Intune per Android
- Creare un criterio di protezione delle app di Microsoft Intune per iOS
- Contrassegnare i dispositivi senza criteri di conformità di Microsoft Intune assegnati come non conformi
- Creare un criterio di conformità di Microsoft Intune per iOS
- Creare un criterio di conformità di Microsoft Intune per macOS
- Creare un criterio di conformità di Microsoft Intune per Windows
- Creare un profilo di configurazione di Microsoft Intune per Android
- Creare un profilo di configurazione di Microsoft Intune per Android per il lavoro
- Creare un profilo di configurazione di Microsoft Intune per macOS
- Creare un profilo di configurazione di Microsoft Intune per iOS
- Creare un profilo di configurazione di Microsoft Intune per Windows
- Abilitare il rilevamento migliorato del jailbreak in Microsoft Intune
- Richiedere la correzione di tutti i dispositivi, disporre di antivirus e firewall abilitati
- Abilitare l'integrazione di Windows Defender ATP in Microsoft Intune
- Creare un criterio di protezione delle informazioni di Windows per Microsoft Intune
- Richiedere che tutti i dispositivi dispongano di configurazioni di sicurezza avanzate
- Rivedere i dispositivi bloccati segnala settimanalmente

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili

Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.

- Abilitare la registrazione dei dati di controllo
- Individuare le applicazioni IT Shadow a rischio e non conformi
- Esaminare le autorizzazioni & bloccare le applicazioni OAuth rischiose connesse all'ambiente
- Configurare il controllo delle versioni nelle raccolte documenti di SharePoint Online

### <a name="mfa-improvement-action-updates"></a>Aggiornamenti dell'azione per il miglioramento dell'AMF

Per riflettere la necessità per le aziende di garantire la massima sicurezza durante l'applicazione di criteri che funzionano con le loro attività, Microsoft Secure Score rimuove tre azioni di miglioramento incentrate sull'autenticazione a più fattori e l'aggiunta di due.

I tre che verranno rimossi:

- Registrare tutti gli utenti per l'autenticazione a più fattori
- Richiedi l'AMF per tutti gli utenti
- Richiedere l'autenticazione master per i ruoli con privilegi di Azure AD

Sono state aggiunte nuove azioni di miglioramento:

- Garantire che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro
- Richiedere l'AMF per i ruoli amministrativi

 Queste nuove azioni di miglioramento richiedono la registrazione di utenti o amministratori per l'autenticazione a più fattori (AMF) all'interno della directory e la definizione del set di criteri appropriato che soddisfano le esigenze dell'organizzazione. L'obiettivo principale è la flessibilità garantendo che tutti gli utenti e gli amministratori siano in grado di eseguire l'autenticazione con più fattori o richieste di verifica dell'identità basata sui rischi. Che può assumere la forma di avere più criteri che applicano decisioni con ambito o impostazione dei valori predefiniti per la sicurezza (a partire dal 16 marzo) che consentono a Microsoft di decidere quando sfidare gli utenti per l'AMF.

### <a name="removing-review-improvement-actions"></a>Rimozione delle azioni di miglioramento "revisione"

Uno dei principi del Punteggio sicuro è che il punteggio dovrebbe essere standardizzato e facilmente correlabile. L'utilizzo di azioni di miglioramento non misurabili o utilizzabili ha provocato confusione. Un punteggio sicuro di Microsoft ha senso solo quando ogni suggerimento può avere un effetto chiaro sulla partitura. Esaminare le azioni di miglioramento non vengono misurate allo stesso livello di altre azioni di miglioramento.  

Per questi motivi, tutte le azioni di miglioramento che richiedono una cadenza di revisione verranno temporaneamente rimosse. Non è necessaria alcuna azione da parte vostra.

## <a name="march-16th-2020"></a>16 marzo 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili

Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.

- Archiviare i documenti degli utenti in OneDrive for business
- Impostare i criteri degli allegati sicuri di Office 365 ATP
- Configurare i collegamenti sicuri di Office 365 per verificare gli URL
- Non consentire la delega delle cassette postali
- Consenti collegamenti di condivisione guest anonimi per siti e documenti

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Supporto delle impostazioni predefinite per la sicurezza per le azioni di miglioramento di Azure AD

Microsoft Secure Score aggiornerà le azioni di miglioramento per supportare le impostazioni predefinite per la [sicurezza di Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), che facilitano la protezione dell'organizzazione con quelle preconfigurate per gli attacchi più comuni.

Influenzerà le operazioni di miglioramento seguenti:

- Garantire che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro
- Richiedere l'AMF per i ruoli amministrativi
- Abilitazione del criterio per bloccare l'autenticazione legacy
