---
title: Analisi automatizzata e risposta (AIR)-Guida introduttiva
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Iniziare a utilizzare le funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: b844e4817bc77d7f6f4e99df53fc4b14c7e7110c
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308888"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Iniziare a usare l'analisi e la risposta automatizzate (AIR) in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender per Office 365](office-365-atp.md) include potenti funzionalità di analisi e risposta (aria) automatizzate in grado di salvare il tempo e lo sforzo del team per le operazioni di sicurezza. Quando vengono attivati gli avvisi, spetta al team delle operazioni di sicurezza esaminare, assegnare priorità e rispondere a tali avvisi. Tenere il passo con il volume degli avvisi in ingresso può essere travolgente. Automatizzare alcune di queste informazioni può essere di aiuto. Con AIR, il team delle operazioni di sicurezza può concentrarsi sulle attività con priorità più alta senza perdere di vista gli avvisi attivati.

In questo articolo sono inclusi i seguenti:
- Il [flusso globale](#the-overall-flow-of-air) di aria;
- [Come ottenere aria](#how-to-get-air); e 
- Le [autorizzazioni necessarie](#required-permissions-to-use-air-capabilities) per configurare o utilizzare le funzionalità aeree. 

## <a name="the-overall-flow-of-air"></a>Flusso globale dell'aria

A livello elevato viene attivato un avviso e un playbook di sicurezza avvia un'indagine automatizzata, che risulta in risultati e suggerimenti. Di seguito è indicato il flusso di aria generale, Step by Step:

1. Un'analisi automatizzata viene avviata in uno dei modi seguenti:

   - Un [avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) viene attivato da un evento di Office che consente di creare un'operazione non consentita. A seconda del tipo di evento imprevisto, un [PlayBook di sicurezza](automated-investigation-response-office.md#security-playbooks) avvia un'indagine automatizzata. 

     --- o ---
   
   - Un analista di sicurezza [Avvia un'indagine automatizzata durante l'](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) utilizzo di [Esplora minacce](threat-explorer.md).

2. Durante l'esecuzione di un'indagine automatizzata, vengono raccolti dati aggiuntivi sul messaggio di posta elettronica in questione e sulle entità correlate a tale messaggio di posta elettronica. Tali entità possono includere file, URL e destinatari.  L'ambito dell'indagine può aumentare man mano che vengono attivati gli avvisi nuovi e correlati.

3. Durante e dopo un'analisi automatizzata, [i dettagli e i risultati](air-view-investigation-results.md) sono disponibili per la visualizzazione. I risultati includono [azioni consigliate](air-remediation-actions.md) che è possibile intraprendere per rispondere e correggere eventuali minacce individuate. Inoltre, è disponibile un [Registro PlayBook](air-view-investigation-results.md#playbook-log) che tiene traccia di tutte le attività investigative.

    Se l'organizzazione utilizza una soluzione per la creazione di report personalizzati o una soluzione di terze parti, è possibile [utilizzare l'API di attività di gestione di Office 365](air-custom-reporting.md) per visualizzare le informazioni relative a indagini e minacce automatizzate.

4. Il team delle operazioni di sicurezza esamina i [risultati e le raccomandazioni dell'analisi](air-view-investigation-results.md)e [approva o rifiuta le azioni di correzione](air-review-approve-pending-completed-actions.md). 

    Poiché le azioni di correzione in sospeso sono approvate (o rifiutate), l'analisi automatizzata viene completata.

> [!NOTE]
> In Office 365 ATP, non viene eseguita automaticamente alcuna azione di correzione. Le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team di sicurezza dell'organizzazione. 

Durante e dopo un processo di analisi automatizzato, il team di sicurezza può eseguire le operazioni seguenti:

- [Visualizzare i dettagli relativi a un avviso relativo a un'indagine](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Visualizzare i dettagli dei risultati di un'indagine](air-view-investigation-results.md#view-details-of-an-investigation)

- [Esaminare e approvare le azioni in seguito a un'indagine](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Per ulteriori informazioni, vedere [funzionamento dell'aria](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Come ottenere aria

Le funzionalità AEREe sono incluse in [Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2). Tuttavia, i [criteri devono essere configurati](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in modo che Air funzioni come previsto. Inoltre, assicurarsi di esaminare e potenzialmente configurare i [criteri di avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)dell'organizzazione. 

Microsoft 365 offre numerosi criteri di avviso incorporati che consentono di identificare l'abuso delle autorizzazioni di amministratore di Exchange, l'attività antimalware, le potenziali minacce esterne e interne e i rischi di governance delle informazioni. Alcuni dei [criteri di avviso predefiniti](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) possono attivare indagini automatizzate. Tra le caratteristiche vi sono le seguenti:

- Viene rilevato un clic URL potenzialmente dannoso

- Un messaggio di posta elettronica viene segnalato da un utente come phishing

- I messaggi di posta elettronica contenenti malware vengono rimossi dopo il recapito

- I messaggi di posta elettronica contenenti URL di phishing vengono rimossi dopo il recapito

- Vengono rilevati modelli di invio sospetti di posta elettronica

- Un utente ha la limitazione di inviare messaggi di posta elettronica

[Ulteriori informazioni sugli avvisi e sull'aria](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Autorizzazioni necessarie per l'utilizzo delle funzionalità AEREe

Le autorizzazioni vengono concesse tramite alcuni ruoli, ad esempio quelli descritti nella tabella seguente: 

|Attività |Ruoli necessari |
|--|--|
|Per impostare le caratteristiche dell'aria |Uno dei ruoli seguenti: <br/>-Amministratore globale<br/>-Amministratore della sicurezza <br/>Questi ruoli possono essere assegnati in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel [Centro sicurezza & Compliance](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Per approvare o rifiutare le azioni consigliate|Uno dei ruoli seguenti, assegnati in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel [Centro sicurezza & Compliance](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center):<br/>-Amministratore globale <br/>-Amministratore della sicurezza<br/>-Lettore di sicurezza <br/>--- e ---<br/>-Search and Purge (questo ruolo è assegnato solo nel [Centro sicurezza & Compliance](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Potrebbe essere necessario creare un nuovo gruppo di ruoli e aggiungere il ruolo Search and Purge a quel nuovo gruppo di ruoli.

Le licenze di [Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) devono essere assegnate a:
- Amministratori della sicurezza (compresi gli amministratori globali)
- Il team delle operazioni di sicurezza dell'organizzazione (inclusi i lettori di sicurezza e quelli con il ruolo di ricerca e spurgo)
- Utenti finali

Inoltre, i [criteri di Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) devono essere definiti e applicati in modo che la protezione sia sul posto.

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Esaminare e approvare le azioni in sospeso](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Articoli correlati

- [Analisi e correzione automatizzate in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Analisi e risposta automatizzate in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
