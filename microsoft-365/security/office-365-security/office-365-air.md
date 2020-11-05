---
title: Introduzione a indagini e risposte automatiche in Microsoft Defender per Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Iniziare a utilizzare le funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925605"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Iniziare a usare l'analisi e la risposta automatizzata (AIR) in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender per Office 365](office-365-atp.md) include potenti funzionalità di analisi e risposta (aria) automatizzate in grado di salvare il tempo e lo sforzo del team per le operazioni di sicurezza. Quando vengono attivati gli avvisi, spetta al team delle operazioni di sicurezza esaminare, assegnare priorità e rispondere a tali avvisi. Tenere il passo con il volume degli avvisi in ingresso può essere travolgente. L'automazione di alcune di queste attività può essere di aiuto. Con AIR, il team delle operazioni di sicurezza può concentrarsi sulle attività con priorità più alta senza perdere di vista gli avvisi importanti che vengono attivati.

In questo articolo viene descritto:
- Il [flusso globale di aria](#the-overall-flow-of-air);
- [Come ottenere aria](#how-to-get-air); e 
- Le [autorizzazioni necessarie](#required-permissions-to-use-air-capabilities) per configurare o utilizzare le funzionalità aeree. 

## <a name="the-overall-flow-of-air"></a>Flusso globale dell'aria

Viene attivato un avviso e un playbook di sicurezza avvia un'indagine automatizzata, che genera risultati e azioni consigliate. Di seguito è indicato il flusso di aria generale, Step by Step:

1. Un'analisi automatizzata viene avviata in uno dei modi seguenti:

   - Un [avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) viene attivato da un messaggio di posta elettronica (ad esempio messaggi, allegati o URL) sospetto. Viene creato un evento Incident. A seconda del tipo di evento imprevisto, viene eseguito un [PlayBook di sicurezza](automated-investigation-response-office.md#security-playbooks) e viene avviata un'indagine automatizzata. 

     --- o ---
   
   - Un analista di sicurezza [Avvia un'indagine automatizzata durante l'](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) utilizzo di [Esplora minacce](threat-explorer.md).

2. Durante l'esecuzione di un'indagine automatizzata, vengono raccolti dati aggiuntivi sul messaggio di posta elettronica in questione e sulle entità correlate a tale messaggio di posta elettronica. Tali entità possono includere file, URL e destinatari.  L'ambito dell'indagine può aumentare man mano che vengono attivati gli avvisi nuovi e correlati.

3. Durante e dopo un'analisi automatizzata, [i dettagli e i risultati](air-view-investigation-results.md) sono disponibili per la visualizzazione. I risultati includono [azioni consigliate](air-remediation-actions.md) che è possibile eseguire per rispondere e correggere eventuali minacce individuate. Inoltre, è disponibile un [Registro PlayBook](air-view-investigation-results.md#playbook-log) che tiene traccia di tutte le attività investigative.


4. Il team delle operazioni di sicurezza esamina i [risultati e le raccomandazioni dell'analisi](air-view-investigation-results.md)e [approva o rifiuta le azioni di correzione](air-review-approve-pending-completed-actions.md). 

5. Poiché le azioni di correzione in sospeso sono approvate (o rifiutate), l'analisi automatizzata viene completata.

> [!IMPORTANT]
> In Microsoft Defender per Office 365, non vengono eseguite automaticamente azioni di correzione. Le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team di sicurezza dell'organizzazione. Tuttavia, le funzionalità AEREe salvano il tempo del team delle operazioni di sicurezza identificando le azioni correttive e fornendo i dettagli necessari per prendere una decisione informata.

Durante e dopo ogni indagine automatizzata, il team delle operazioni di sicurezza può:

- [Visualizzare i dettagli relativi a un avviso relativo a un'indagine](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Visualizzare i dettagli dei risultati di un'indagine](air-view-investigation-results.md#view-details-of-an-investigation)

- [Esaminare e approvare le azioni in seguito a un'indagine](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Per una panoramica più dettagliata, vedere [modalità di funzionamento dell'aria](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Come ottenere aria

Le funzionalità AEREe sono incluse in [Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), purché siano configurati i criteri e gli avvisi. Per ulteriori informazioni, seguire le istruzioni riportate in [protezione contro le minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) per impostare o configurare le seguenti impostazioni di protezione: 

1. [Registrazione di controllo](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (dovrebbe essere attivata)

2. [Criteri antimalware](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [Protezione antiphishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. [Protezione antispam](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).
   
5. [Collegamenti sicuri e allegati sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).
   
6. [Allegati sicuri per SharePoint, OneDrive e Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).
   
7. [Spurgo automatico zero-hour per la posta elettronica](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).

Inoltre, assicurarsi di esaminare i [criteri di avviso dell'organizzazione](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), in particolare i [criteri predefiniti nella categoria Gestione minacce](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies). 

## <a name="which-alert-policies-trigger-automated-investigations"></a>Quali criteri di avviso attivano le indagini automatizzate?

Microsoft 365 offre numerosi criteri di avviso incorporati che consentono di identificare l'abuso delle autorizzazioni di amministratore di Exchange, l'attività antimalware, le potenziali minacce esterne e interne e i rischi di governance delle informazioni. Alcuni dei [criteri di avviso predefiniti](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) possono attivare indagini automatizzate. Tra le caratteristiche vi sono le seguenti:

- Viene rilevato un clic URL potenzialmente dannoso
- Un messaggio di posta elettronica viene segnalato da un utente come phishing
- I messaggi di posta elettronica contenenti malware vengono rimossi dopo il recapito
- I messaggi di posta elettronica contenenti URL di phishing vengono rimossi dopo il recapito
- Vengono rilevati modelli di invio sospetti di posta elettronica
- Un utente ha la limitazione di inviare messaggi di posta elettronica

## <a name="required-permissions-to-use-air-capabilities"></a>Autorizzazioni necessarie per l'utilizzo delle funzionalità AEREe

Le autorizzazioni vengono concesse tramite alcuni ruoli, ad esempio quelli descritti nella tabella seguente: 

|Attività |Ruoli necessari |
|--|--|
|Per impostare le caratteristiche dell'aria |Uno dei ruoli seguenti: <br/>-Amministratore globale<br/>-Amministratore della sicurezza <br/>Questi ruoli possono essere assegnati in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel [Centro sicurezza & Compliance](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Per approvare o rifiutare le azioni consigliate|Uno dei ruoli seguenti, assegnati in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel [Centro sicurezza & Compliance](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center):<br/>-Amministratore globale <br/>-Amministratore della sicurezza<br/>-Lettore di sicurezza <br/>--- e ---<br/>-Search and Purge (questo ruolo è assegnato solo nel [Centro sicurezza & Compliance](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Potrebbe essere necessario creare un nuovo gruppo di ruoli e aggiungere il ruolo Search and Purge a quel nuovo gruppo di ruoli.

## <a name="required-licenses"></a>Licenze necessarie

Le licenze di [Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) devono essere assegnate a:
- Amministratori della sicurezza (compresi gli amministratori globali)
- Il team delle operazioni di sicurezza dell'organizzazione (inclusi i lettori di sicurezza e quelli con il ruolo di ricerca e spurgo)
- Utenti finali


## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Esaminare e approvare le azioni in sospeso](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Articoli correlati

- [Analisi e correzione automatizzate in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Analisi e risposta automatizzate in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
