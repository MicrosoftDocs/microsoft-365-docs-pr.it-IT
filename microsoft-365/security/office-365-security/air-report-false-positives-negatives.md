---
title: Come segnalare falsi positivi o falsi negativi nell'analisi e nella risposta automatizzata di Office 365
description: Si è verificato un errore o rilevato erroneamente da Office 365 Advanced Threat Protection? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dd67af62a400f3e217f146e6d0ee213d74ad99a
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262411"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate

**Si applica a:**
- Office 365 Advanced Threat Protection

[Le funzionalità di analisi e risposta automatizzate in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) non hanno o rilevato erroneamente qualcosa? Per risolvere il problema, è possibile eseguire la procedura. È possibile:
- [Segnala un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Modificare gli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario); e 
- [Annullare le azioni di correzione eseguite nei dispositivi](#undo-a-remediation-action). 

Utilizzare questo articolo come guida. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Segnalare un falso positivo/negativo a Microsoft per l'analisi

Se Office 365 AIR ha perso un messaggio di posta elettronica, un allegato di posta elettronica, un URL in un messaggio di posta elettronica o un URL in un file di Office, è possibile [inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft per l'analisi di office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

È inoltre possibile [inviare un file a Microsoft per l'analisi antimalware](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Modificare un avviso per evitare che i falsi positivi vengano ricorrenti

Se un avviso viene attivato tramite un utilizzo legittimo o se l'avviso non è accurato, è possibile [gestire gli avvisi nel portale di cloud app Security](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Se l'organizzazione utilizza [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) oltre a Office 365 e un file, un indirizzo IP, un URL o un dominio viene considerato come malware su un dispositivo, anche se è sicuro, è possibile [creare un indicatore personalizzato con un'azione "Consenti" per il dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Annullare un'azione di correzione

Nella maggior parte dei casi, se è stata eseguita un'azione di correzione su un messaggio di posta elettronica, un allegato di posta elettronica o un URL e l'elemento non è effettivamente una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione e intraprendere le operazioni necessarie per impedire il ripetersi del falso positivo. È possibile utilizzare [Esplora minacce](#undo-an-action-using-threat-explorer) o la [scheda azioni per un'analisi](#undo-an-action-using-the-actions-tab-for-an-investigation) per annullare un'azione. 

> [!IMPORTANT]
> Accertarsi di disporre delle autorizzazioni necessarie prima di tentare di eseguire le attività seguenti.

### <a name="undo-an-action-using-threat-explorer"></a>Annullamento di un'azione tramite Esplora minacce

Con Esplora minacce, il team delle operazioni di sicurezza può trovare un messaggio di posta elettronica influenzato da un'azione e potenzialmente annullare l'azione.

|Scenario  |Opzioni di annullamento  |Altre informazioni |
|---------|---------|---------|
|Un messaggio di posta elettronica è stato instradato alla cartella posta indesiderata di un utente     |-Spostare il messaggio nella cartella Posta eliminata dell'utente<br/>-Spostare il messaggio nella cartella posta in arrivo dell'utente <br/>-Eliminare il messaggio          |[Individuare e studiare messaggi di posta elettronica dannosi che sono stati recapitati in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|Un messaggio di posta elettronica o un file è stato messo in quarantena     |-Rilasciare il messaggio di posta elettronica o il file <br/>-Eliminare il messaggio di posta elettronica o il file         |[Gestire i messaggi e i file in quarantena come amministratore in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Annullamento di un'azione tramite la scheda azioni per un'analisi

Nel centro azioni, è possibile visualizzare le azioni di correzione eseguite e potenzialmente annullare l'azione.

1. Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso. Questo porta al centro sicurezza & Compliance.

2. Andare a indagini sulla **gestione delle minacce**  >  **Investigations**.

3. Nell'elenco delle indagini selezionare l'icona **Apri in nuova finestra** accanto all'ID di un elemento.

4. Selezionare la scheda **azioni** .

5. Selezionare un elemento con stato **completato**e cercare un collegamento, ad esempio **approvato**, nella colonna **decisione** . Verrà aperto un riquadro a comparsa con maggiori dettagli sull'azione.

6. Per annullare l'azione, selezionare **Elimina correzione**.

## <a name="related-articles"></a>Articoli correlati

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Iniziare a usare l'analisi e la risposta automatizzate (AIR) in Office 365](office-365-air.md)