---
title: Indagine automatizzata e risposta (AIR) in Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Iniziare a utilizzare le funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection Plan 2.
ms.custom: air
ms.openlocfilehash: c06874ea5d55334d9049d6c5d9d5c55a499dae06
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634024"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Indagine automatizzata e risposta (AIR) in Office 365

[Protezione avanzata dalle minacce di Office 365](office-365-atp.md) Il piano 2 include potenti funzionalità di analisi e risposta automatizzate che consentono di salvare il tempo e lo sforzo del team per le operazioni di sicurezza. Quando vengono attivati determinati avvisi, vengono avviati uno o più schemi di sicurezza e il processo di analisi automatizzato inizia. In questo modo il team delle operazioni di sicurezza è abilitato a concentrarsi sulle attività con priorità alta senza perdere di vista gli avvisi attivati. 

## <a name="the-overall-flow-of-air"></a>Flusso globale dell'aria

Viene attivato un avviso e viene avviato un sistema di sicurezza PlayBook che avvia un'indagine automatizzata. In alternativa, un analista di sicurezza attiva un'indagine automatizzata durante l'utilizzo di Esplora minacce. L'analisi automatizzata viene eseguita e in genere vengono identificate alcune azioni di correzione. Tali azioni vengono esaminate e approvate dal team per le operazioni di sicurezza e l'analisi viene completata. 

La tabella seguente illustra il flusso globale dell'aria, passo dopo passo:

|Passaggio  |Effetto  |
|---------|---------|
|1      |Un avviso viene attivato da un evento di Office e un sistema di [sicurezza PlayBook](automated-investigation-response-office.md#security-playbooks) avvia un'indagine automatizzata per gli avvisi selezionati. <br/><br/>In alternativa, un analista di sicurezza può [attivare un'indagine automatizzata durante l'](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) utilizzo di [Esplora minacce](threat-explorer.md).        |
|2      |Durante l'esecuzione di un'indagine automatizzata, vengono raccolti dati aggiuntivi relativi all'indirizzo di posta elettronica e alle entità correlate alla posta elettronica: file, URL e destinatari.  L'ambito dell'indagine può aumentare, poiché vengono attivati nuovi avvisi correlati.         |
|3      |Durante e dopo un'analisi automatizzata, [i dettagli e i risultati](air-view-investigation-results.md) sono disponibili per la visualizzazione. I risultati includono [azioni consigliate](air-remediation-actions.md) che è possibile intraprendere per rispondere e correggere eventuali minacce individuate. Inoltre, è disponibile un [Registro PlayBook](air-view-investigation-results.md#playbook-log) che tiene traccia di tutte le attività investigative.<br/><br/>Se l'organizzazione utilizza una soluzione per la creazione di report personalizzati o una soluzione di terze parti, è possibile [utilizzare l'API di attività di gestione di Office 365](air-custom-reporting.md) per visualizzare le informazioni relative a indagini e minacce automatizzate.         |
|4      |Il team delle operazioni di sicurezza esamina i [risultati e le raccomandazioni dell'analisi](air-view-investigation-results.md)e [approva le azioni di correzione](air-remediation-actions.md#approve-or-reject-pending-actions). In Office 365, non viene eseguita alcuna azione automaticamente. Le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team di sicurezza dell'organizzazione.         |

Durante e dopo un processo di analisi automatizzato, il team di sicurezza può eseguire le operazioni seguenti:

- [Visualizzare i dettagli relativi a un avviso relativo a un'indagine](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Visualizzare i dettagli dei risultati di un'indagine](air-view-investigation-results.md#view-details-of-an-investigation)
- [Esaminare e approvare le azioni in seguito a un'indagine](air-remediation-actions.md#approve-or-reject-pending-actions)

Per ulteriori informazioni, vedere [funzionamento dell'aria](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Come ottenere aria

Office 365 AIR è incluso negli abbonamenti seguenti:

- Microsoft 365 E5
- Office 365 E5
- Microsoft Threat Protection
- Office 365 Advanced Threat Protection (Piano 2)

Se non si dispone di una o più di queste sottoscrizioni, [avviare una versione di valutazione gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).

Per ulteriori informazioni sulla disponibilità delle funzionalità, visitare la [disponibilità delle funzionalità tra i piani di Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-permissions-to-use-air-capabilities"></a>Autorizzazioni necessarie per l'utilizzo delle funzionalità AEREe

Le autorizzazioni vengono concesse tramite alcuni ruoli, ad esempio quelli descritti nella tabella seguente: 

|Attività |Ruoli necessari |
|--|--|
|Per impostare le caratteristiche dell'aria |Uno dei ruoli seguenti: <br/>- **Amministratore globale**<br/>- **Amministratore della sicurezza** <br/>Questi ruoli possono essere assegnati in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel [Centro sicurezza & conformità di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Per approvare o rifiutare le azioni consigliate|Uno dei ruoli seguenti, assegnato in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel [Centro sicurezza & conformità di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center):<br/>- **Amministratore globale** <br/>- **Amministratore della sicurezza**<br/>- **Lettore di sicurezza** <br/>--- e ---<br/>- **Search and Purge** (questo ruolo è assegnato solo nel [Centro sicurezza & conformità di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Potrebbe essere necessario creare un nuovo gruppo di ruoli e aggiungere il ruolo Search and Purge a quel nuovo gruppo di ruoli.

## <a name="related-articles"></a>Articoli correlati

- [Indagine e reazione automatizzate in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Analisi e correzione automatizzate in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)