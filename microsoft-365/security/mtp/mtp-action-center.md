---
title: Accedere al centro notifiche per visualizzare e approvare le indagini automatizzate e le attività di correzione
description: Utilizzare il centro notifiche per visualizzare dettagli relativi alle indagini automatizzate e approvare le azioni in sospeso
keywords: Centro notifiche, protezione dalla minacce, indagine, avviso, in sospeso, automatizzata, rilevamento
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 45e02e4ce7d5d813cc8215a1f27ed9c415707cb1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930427"
---
# <a name="the-action-center"></a>Centro operativo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Utilizzare il centro notifiche ( ) per visualizzare i risultati delle indagini correnti e passate nei dispositivi e nelle cassette postali [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) dell'organizzazione. A seconda del tipo di minaccia e del verdetto [risultante,](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) le azioni di correzione possono verificarsi automaticamente o dopo l'approvazione da parte del team delle operazioni di sicurezza dell'organizzazione. Tutte le azioni correttive, siano esse in attesa di approvazione o già approvate, vengono consolidate nel centro notifiche. 

![Centro notifiche](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Un'esperienza a "riquadro unico"

Il centro notifiche include un "riquadro unico" per le attività, ad esempio:
- approvazione delle azioni di correzione in sospeso;
- visualizzazione di un log di controllo delle azioni di correzione già approvate;
- revisione delle azioni di correzione completate.

Il team delle operazioni di sicurezza può operare in modo più efficace ed efficiente, perché il centro notifiche offre una panoramica completa di Microsoft 365 Defender sul lavoro.

## <a name="go-to-the-action-center"></a>Accedere al centro notifiche

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l’accesso. 

2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 

3. Nel centro notifiche verranno visualizzate due **schede:** In sospeso e **Cronologia.**

    - Nella scheda **In sospeso** sono elencate le indagini che richiedono la revisione e l'approvazione da parte di qualcuno nel team delle operazioni di sicurezza per continuare. Assicurarsi di rivedere e agire sugli elementi in sospeso visualizzati nella scheda.

    - Nella scheda **Cronologia** sono elencate le indagini precedenti e le azioni correttive intraprese automaticamente. È possibile visualizzare i dati relativi all'ultimo giorno, mese, all'ultima settimana o agli ultimi sei mesi.

4. Per visualizzare solo le colonne desiderate, selezionare **Personalizza colonne**.<br/>![Centro notifiche in Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Selezionare un elemento nell'elenco per visualizzare maggiori dettagli relativi a un'indagine. Si aprirà la visualizzazione dei dettagli dell'indagine.<br/>![Dettagli indagine](../../media/mtp-air-investdetails.png)

    - Se l'indagine riguarda il contenuto della posta elettronica (ad esempio, l'entità è una cassetta postale), i dettagli dell'indagine si aprono nel Centro sicurezza & conformità ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Se l'indagine riguarda un dispositivo, i dettagli dell'indagine vengono aperti nel Centro sicurezza ([https://security.microsoft.com](https://security.microsoft.com)). 

> [!TIP]
> Se ritieni che qualcosa sia stato perso o rilevato in modo errato dalle funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender, contattaci. Vedere Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta [automatizzate (AIR) in Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

## <a name="available-actions"></a>Azioni disponibili

Quando vengono eseguite azioni correttive, vengono elencate nella **scheda Cronologia** nel centro notifiche. Tali azioni includono:

- Raccogliere il pacchetto di analisi 
- Isola dispositivo (questa azione può essere annullata) 
- Offboard machine 
- Rilasciare l'esecuzione del codice 
- Rilascio dalla quarantena 
- Esempio di richiesta 
- Limitare l'esecuzione del codice (questa azione può essere annullata) 
- Eseguire l'analisi antivirus 
- Arrestare e mettere in quarantena 

> [!NOTE]
> Oltre alle azioni di correzione eseguite automaticamente, il team delle operazioni di sicurezza può eseguire azioni manuali per risolvere le minacce rilevate. Per ulteriori informazioni sulle azioni di correzione automatiche e manuali, vedere [Azioni di correzione.](mtp-remediation-actions.md)

## <a name="action-source"></a>Origine azione

(**NUOVO!**) Come sai, Microsoft 365 Defender riunisce funzionalità di analisi e risposta automatizzate in più servizi, ad esempio [Microsoft Defender per Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) e Microsoft Defender per Office [365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Il centro notifiche nuovo e migliorato ora include una colonna **di origine** azione che indica la origine di ogni azione correttiva. 

Nella tabella seguente vengono descritti i valori **possibili per l'origine dell'azione:**

| Valore di origine dell'azione | Descrizione |
|:-----|:---|
| **Azione manuale del dispositivo** | Un'azione manuale eseguita su un dispositivo. Alcuni esempi includono [l'isolamento del dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) o [la quarantena dei file.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **Azione manuale tramite posta elettronica** | Un'azione manuale eseguita sulla posta elettronica. Un esempio include l'eliminazione recisa dei messaggi di posta elettronica o [la correzione di un messaggio di posta elettronica.](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365) |
| **Azione automatica del dispositivo** | Un'azione automatizzata eseguita su un'entità, ad esempio un file o un processo. Esempi di azioni automatizzate includono l'invio di un file in quarantena, l'interruzione di un processo e la rimozione di una chiave del Registro di sistema. Vedere [Azioni di correzione in Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions) |
| **Azione di posta elettronica automatizzata** | Un'azione automatica eseguita sul contenuto della posta elettronica, ad esempio un messaggio di posta elettronica, un allegato o un URL. Esempi di azioni automatizzate includono l'eliminazione recisa dei messaggi di posta elettronica, il blocco degli URL e la disattivazione dell'inoltro della posta esterna. Vedere [Azioni di correzione in Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions) |
| **Azione di ricerca avanzata** | Azioni eseguite su dispositivi o posta elettronica con [ricerca avanzata.](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview) |
| **Azione Esplora risorse** | Azioni eseguite sul contenuto della posta elettronica con [Esplora risorse.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) |
| **Azione di risposta in tempo reale manuale** | Azioni eseguite su un dispositivo con [risposta in tempo reale.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) Alcuni esempi includono l'eliminazione di un file, l'interruzione di un processo e la rimozione di un'attività pianificata. |
| **Azione di risposta in tempo reale** | Azioni eseguite su un dispositivo con LE API [di Microsoft Defender per endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) Esempi di azioni includono l'isolamento di un dispositivo, l'esecuzione di un'analisi antivirus e il recupero di informazioni su un file. |

## <a name="required-permissions-for-action-center-tasks"></a>Autorizzazioni necessarie per le attività del centro notifiche

Per approvare o rifiutare le azioni in sospeso nel centro notifiche, è necessario disporre delle autorizzazioni elencate nella tabella seguente:

|Azione correttiva |Ruoli e autorizzazioni necessari |
|--|----|
|Correzione di Microsoft Defender per endpoint (dispositivi) |Ruolo di amministratore della protezione assegnato in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- o ---<br/>Ruolo azioni correttive attive assegnato in Microsoft Defender per endpoint <br/> <br/> Per altre informazioni, vedere le risorse seguenti: <br/>- [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Creare e gestire ruoli per il controllo dell'accesso basato sui ruoli (Microsoft Defender per endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Correzione di Microsoft Defender per Office 365 (contenuto di Office e posta elettronica)  |Ruolo di amministratore della protezione assegnato in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- e --- <br/>Ruolo di ricerca ed eliminazione assegnato al Centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**IMPORTANTE:** se il ruolo Amministratore della sicurezza è assegnato solo nel Centro sicurezza & e conformità, non sarà possibile accedere alle funzionalità del Centro notifiche o di Microsoft 365 Defender. È necessario avere il ruolo di amministratore della protezione assegnato in Azure Active Directory o nell'interfaccia di amministrazione di Microsoft 365. <br/><br/>Per altre informazioni, vedere le risorse seguenti: <br/>- [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Autorizzazioni nel Centro sicurezza & conformità](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Gli utenti che hanno il ruolo di amministratore globale assegnato in Azure Active Directory possono approvare o rifiutare qualsiasi azione in sospeso nel centro notifiche. Tuttavia, come procedura consigliata, l'organizzazione dovrebbe limitare il numero di persone a cui è assegnato il ruolo di amministratore globale. È consigliabile usare i ruoli di amministratore della protezione, azioni correttive attive e ricerca ed eliminazione elencati in precedenza per le autorizzazioni del centro notifiche.

## <a name="next-steps"></a>Passaggi successivi 

- [Approvare o rifiutare le azioni in sospeso in seguito a un'indagine automatizzata](mtp-autoir-actions.md)
- [Visualizzare i risultati di un'indagine automatizzata](mtp-autoir-results.md)

