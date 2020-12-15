---
title: Accedere al centro notifiche per visualizzare e approvare le indagini automatizzate e le attività di correzione
description: Utilizzare il centro notifiche per visualizzare dettagli relativi alle indagini automatizzate e approvare le azioni in sospeso
keywords: Centro notifiche, protezione dalla minacce, indagine, avviso, in sospeso, automatizzata, rilevamento
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: aa9f433bc60949aa625d9346421b025121347a2c
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683320"
---
# <a name="the-action-center"></a>Centro operativo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Utilizzare il centro azioni ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) per visualizzare i risultati delle indagini correnti e precedenti nei dispositivi e nelle cassette postali dell'organizzazione. A seconda del tipo di minaccia e del verdetto risultante, le [azioni di correzione](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) possono verificarsi automaticamente o dopo l'approvazione da parte del team di operazioni di sicurezza dell'organizzazione. Tutte le azioni correttive, siano esse in attesa di approvazione o già approvate, vengono consolidate nel centro notifiche. 

![Centro notifiche](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Un'esperienza a "riquadro unico"

Il centro notifiche include un "riquadro unico" per le attività, ad esempio:
- approvazione delle azioni di correzione in sospeso;
- visualizzazione di un log di controllo delle azioni di correzione già approvate;
- revisione delle azioni di correzione completate.

Il team delle operazioni di sicurezza può operare in modo più efficace ed efficiente, poiché il centro informazioni fornisce una panoramica completa di Microsoft 365 Defender sul lavoro.

## <a name="go-to-the-action-center"></a>Accedere al centro notifiche

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l’accesso. 

2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 

3. Nel centro azioni vengono visualizzate due schede: in **sospeso** e **cronologia**.

    - Nella scheda **In sospeso** sono elencate le indagini che richiedono la revisione e l'approvazione da parte di qualcuno nel team delle operazioni di sicurezza per continuare. Assicurarsi di rivedere e agire sugli elementi in sospeso visualizzati nella scheda.

    - Nella scheda **Cronologia** sono elencate le indagini precedenti e le azioni correttive intraprese automaticamente. È possibile visualizzare i dati relativi all'ultimo giorno, mese, all'ultima settimana o agli ultimi sei mesi.

4. Per visualizzare solo le colonne desiderate, selezionare **Personalizza colonne**.<br/>![Centro azioni in Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Selezionare un elemento nell'elenco per visualizzare maggiori dettagli relativi a un'indagine. Si aprirà la visualizzazione dei dettagli dell'indagine.<br/>![Dettagli indagine](../../media/mtp-air-investdetails.png)

    - Se l'indagine è relativa al contenuto della posta elettronica (ad esempio, l'entità è una cassetta postale), i dettagli dell'indagine vengono aperti nel centro sicurezza & Compliance ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Se l'indagine riguarda un dispositivo, i dettagli dell'indagine vengono aperti nel Centro sicurezza ([https://security.microsoft.com](https://security.microsoft.com)). 

> [!TIP]
> Se si pensa che qualcosa è stato perso o erroneamente rilevato dalle funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender, fatecelo sapere! Vedere [How to report false positives/negatives in Automatic Investigation and Response (Air) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).

## <a name="available-actions"></a>Azioni disponibili

Poiché vengono eseguite azioni di correzione, sono elencate nella scheda **cronologia** del centro operazioni. Tali azioni includono le seguenti:

- Raccolta del pacchetto di analisi 
- Dispositivo isolato (questa azione può essere annullata) 
- Macchina trasferisce 
- Esecuzione del codice di rilascio 
- Rilascio dalla quarantena 
- Esempio di richiesta 
- Limitare l'esecuzione del codice (questa azione può essere annullata) 
- Eseguire l'analisi antivirus 
- Arresto e quarantena 

> [!NOTE]
> Oltre alle azioni di correzione eseguite automaticamente, il team delle operazioni di sicurezza può eseguire azioni manuali per risolvere le minacce rilevate. Per ulteriori informazioni sulle azioni di correzione automatica e manuale, vedere [Remediation actions](mtp-remediation-actions.md).

## <a name="action-source"></a>Origine azione

(**Nuovo!**) Come sapete, Microsoft 365 Defender riunisce le funzionalità di analisi e risposta automatizzate su più servizi, ad esempio [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) e [Microsoft defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). Il centro azioni nuovo e migliorato ora include una colonna di **origine azione** che indica la provenienza di ogni azione di correzione. 

Nella tabella seguente vengono descritti i possibili valori di **origine delle azioni** :

| Valore di origine azione | Descrizione |
|:-----|:---|
| **Azione manuale del dispositivo** | Azione manuale eseguita in un dispositivo. Tra gli esempi sono inclusi l' [isolamento del dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) o la [quarantena del file](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files). |
| **Azione di posta elettronica manuale** | Azione manuale intrapresa tramite posta elettronica. Un esempio include la cancellazione di messaggi di posta elettronica o [la correzione di un messaggio di posta elettronica](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365). |
| **Azione dispositivo automatizzato** | Azione automatizzata eseguita su un'entità, ad esempio un file o un processo. Esempi di azioni automatizzate includono l'invio di un file in quarantena, l'interruzione di un processo e la rimozione di una chiave del registro di sistema. Vedere azioni correttive [in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions). |
| **Azione di posta elettronica automatizzata** | Azione automatizzata eseguita sul contenuto della posta elettronica, ad esempio un messaggio di posta elettronica, un allegato o un URL. Esempi di azioni automatizzate includono l'eliminazione dei messaggi di posta elettronica, il blocco degli URL e la disattivazione dell'inoltro della posta esterna. (Vedere [azioni correttive in Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)). |
| **Azione di caccia avanzata** | Azioni intraprese su dispositivi o messaggi di posta elettronica con la [ricerca avanzata](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview). |
| **Azione Esplora risorse** | Azioni intraprese nei contenuti della posta elettronica con [Esplora risorse](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer). |
| **Azione di risposta diretta manuale** | Azioni intraprese su un dispositivo con [risposta in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response). Alcuni esempi includono l'eliminazione di un file, l'interruzione di un processo e la rimozione di un'attività pianificata. |
| **Azione Live Response** | Azioni intraprese su un dispositivo con [Microsoft Defender per le API di endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis). Esempi di azioni includono l'isolamento di un dispositivo, l'esecuzione di un'analisi antivirus e l'acquisizione di informazioni su un file. |

## <a name="required-permissions-for-action-center-tasks"></a>Autorizzazioni necessarie per le attività del centro notifiche

Per approvare o rifiutare le azioni in sospeso nel centro notifiche, è necessario disporre delle autorizzazioni elencate nella tabella seguente:

|Azione correttiva |Ruoli e autorizzazioni necessari |
|--|----|
|Microsoft Defender per la correzione di endpoint (dispositivi) |Ruolo di amministratore della protezione assegnato in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- o ---<br/>Ruolo di azione di correzione attivo assegnato in Microsoft Defender per endpoint <br/> <br/> Per altre informazioni, vedere le risorse seguenti: <br/>- [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Creare e gestire i ruoli per il controllo di accesso basato sui ruoli (Microsoft Defender per endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Microsoft Defender per la correzione di Office 365 (contenuto e posta elettronica di Office)  |Ruolo di amministratore della protezione assegnato in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- e --- <br/>Ruolo di ricerca e spurgo assegnato al centro sicurezza & Compliance ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**Importante**: se il ruolo amministratore della sicurezza è assegnato solo nel centro sicurezza & Compliance, non sarà possibile accedere al centro azioni o alle funzionalità di Microsoft 365 Defender. È necessario avere il ruolo di amministratore della protezione assegnato in Azure Active Directory o nell'interfaccia di amministrazione di Microsoft 365. <br/><br/>Per altre informazioni, vedere le risorse seguenti: <br/>- [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Autorizzazioni nel centro sicurezza & conformità](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Gli utenti che hanno il ruolo di amministratore globale assegnato in Azure Active Directory possono approvare o rifiutare qualsiasi azione in sospeso nel centro notifiche. Tuttavia, come procedura consigliata, l'organizzazione dovrebbe limitare il numero di persone a cui è assegnato il ruolo di amministratore globale. È consigliabile usare i ruoli di amministratore della protezione, azioni correttive attive e ricerca ed eliminazione elencati in precedenza per le autorizzazioni del centro notifiche.

## <a name="next-steps"></a>Passaggi successivi 

- [Approvare o rifiutare le azioni in sospeso dopo un'analisi automatizzata](mtp-autoir-actions.md)
- [Visualizzare i risultati di un'indagine automatizzata](mtp-autoir-results.md)

