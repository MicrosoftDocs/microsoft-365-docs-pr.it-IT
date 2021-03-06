---
title: Accedere al centro notifiche per visualizzare e approvare le indagini automatizzate e le attività di correzione
description: Usare il centro notifiche per visualizzare i dettagli sull'indagine automatizzata e approvare le azioni in sospeso
keywords: Centro notifiche, protezione dalle minacce, indagine, avviso, in sospeso, automatizzato, rilevamento
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ee075f34087d28fc9326d408622d05f363bba768
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022600"
---
# <a name="the-action-center"></a>Centro operativo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Il centro notifiche offre un'esperienza di "singolo riquadro di vetro" per le attività relative a eventi imprevisti e avvisi, ad esempio:

- Approvazione delle azioni di correzione in sospeso.
- Visualizzazione di un log di controllo delle azioni di correzione già approvate.
- revisione delle azioni di correzione completate.

Poiché il centro notifiche offre una panoramica completa dei Microsoft 365 Defender sul lavoro, il team delle operazioni di sicurezza può operare in modo più efficace ed efficiente.

## <a name="the-unified-action-center"></a>Centro notifiche unificato

Nel centro notifiche unificato ( ) sono elencate le azioni di correzione in sospeso e completate per i dispositivi, la posta elettronica & contenuto di collaborazione e le identità [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) in un'unica posizione.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro notifiche unificato in Microsoft 365 Defender":::

Ad esempio: 

- Se in precedenza si usava Office 365 Sicurezza & Compliance Center ( ), provare il Centro notifiche unificato nel portale di Microsoft 365 Defender [https://protection.office.com](https://protection.office.com) ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Se si utilizza il centro notifiche nella Microsoft Defender Security Center ( ), provare il centro notifiche unificato nel portale Microsoft 365 Defender [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Se si usava già il portale di Microsoft 365 Defender ( ), nel centro notifiche verranno visualizzati diversi miglioramenti [https://security.microsoft.com](https://security.microsoft.com) ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).

Il centro notifiche unificato riunisce le azioni di correzione in Defender for Endpoint e Defender per Office 365. Definisce un linguaggio comune per tutte le azioni di correzione e offre un'esperienza di indagine unificata. Il team delle operazioni di sicurezza ha un'esperienza di "singolo riquadro di vetro" per visualizzare e gestire le azioni di correzione.  

È possibile utilizzare il centro notifiche unificato se si dispone delle autorizzazioni appropriate e di una o più delle sottoscrizioni seguenti:

- [Defender per Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> Per ulteriori informazioni, vedere [Requisiti](./prerequisites.md).

## <a name="using-the-action-center"></a>Utilizzo del centro notifiche

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 
2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 

Quando si visita il centro notifiche, vengono visualizzate due schede: **Azioni in sospeso** e **Cronologia.** Nella tabella seguente sono riepilogati gli elementi che verranno visualizzati in ogni scheda:

|Scheda  |Descrizione  |
|---------|---------|
|**In sospeso**     | Visualizza un elenco di azioni che richiedono attenzione. È possibile approvare o rifiutare le azioni una alla volta oppure selezionare più azioni se hanno lo stesso tipo di azione (ad esempio file di quarantena). <p>**SUGGERIMENTO:** verificare e approvare (o rifiutare) le azioni in sospeso il prima possibile in modo che le indagini automatizzate possano essere completate in modo rapido.       |
|**Cronologia**     | Funge da log di controllo per le azioni eseguite, ad esempio: <br/>- Azioni correttive intraprese a seguito di indagini automatizzate <br/>- Azioni di correzione eseguite su messaggi di posta elettronica, file o URL sospetti o dannosi<br/>- Azioni di correzione approvate dal team delle operazioni di sicurezza <br/>- Comandi eseguiti e azioni di correzione applicate durante le sessioni di Live Response<br/>- Azioni di correzione eseguite dalla protezione antivirus <p>Consente di annullare determinate azioni (vedere [Annullare le azioni completate).](m365d-autoir-actions.md#undo-completed-actions)        |

È possibile personalizzare, ordinare, filtrare ed esportare i dati nel centro notifiche.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="Il centro notifiche consente di ordinare, filtrare e personalizzare l'elenco di azioni":::

- Selezionare un'intestazione di colonna per ordinare gli elementi in ordine crescente o decrescente.
- Utilizzare il filtro periodo di tempo per visualizzare i dati relativi al giorno, alla settimana, ai 30 giorni o ai 6 mesi precedenti.
- Scegliere le colonne che si desidera visualizzare.
- Specificare il numero di elementi da includere in ogni pagina di dati.
- Utilizzare i filtri per visualizzare solo gli elementi che si desidera visualizzare.
- Selezionare **Esporta** per esportare i risultati in .csv file.

## <a name="actions-tracked-in-the-action-center"></a>Azioni rilevate nel centro notifiche

Tutte le azioni, in attesa di approvazione o già eseguite, vengono rilevate nel centro notifiche. Le azioni disponibili includono:

- Raccogliere un pacchetto di indagini 
- Isola dispositivo (questa azione può essere annullata) 
- Dispositivo offboard 
- Esecuzione del codice di rilascio 
- Rilascio dalla quarantena 
- Esempio di richiesta 
- Limitare l'esecuzione del codice (questa azione può essere annullata) 
- Eseguire ricerca del virus 
- Arrestare e mettere in quarantena 

Oltre alle azioni di correzione eseguite automaticamente [](m365d-autoir.md)a seguito di indagini automatizzate, il centro notifiche tiene traccia delle azioni intraprese dal team di sicurezza per affrontare le minacce rilevate e le azioni intraprese a seguito delle funzionalità di protezione dalle minacce in Microsoft 365 Defender. Per ulteriori informazioni sulle azioni di correzione automatiche e manuali, vedere [Azioni di correzione.](m365d-remediation-actions.md)

## <a name="viewing-action-source-details"></a>Visualizzazione dei dettagli dell'origine dell'azione

(**NEW!**) Il centro notifiche migliorato ora include una **colonna Origine** azione che indica da dove è stata eseguita ogni azione. Nella tabella seguente vengono descritti i possibili **valori dell'origine azione:**

| Valore di origine dell'azione | Descrizione |
|:-----|:---|
| **Azione manuale del dispositivo** | Azione manuale eseguita su un dispositivo. Alcuni esempi includono [l'isolamento del dispositivo](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) [o la quarantena dei file.](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files) |
| **Azione manuale per la posta elettronica** | Un'azione manuale eseguita sulla posta elettronica. Un esempio include l'eliminazione recidiva dei messaggi di posta elettronica [o la correzione di un messaggio di posta elettronica.](../office-365-security/remediate-malicious-email-delivered-office-365.md) |
| **Azione automatica del dispositivo** | Azione automatizzata eseguita su un'entità, ad esempio un file o un processo. Esempi di azioni automatizzate includono l'invio di un file in quarantena, l'arresto di un processo e la rimozione di una chiave del Registro di sistema. (Vedere [Azioni di correzione in Microsoft Defender per Endpoint).](../defender-endpoint/manage-auto-investigation.md#remediation-actions) |
| **Azione di posta elettronica automatizzata** | Azione automatizzata eseguita sul contenuto della posta elettronica, ad esempio un messaggio di posta elettronica, un allegato o un URL. Esempi di azioni automatizzate includono l'eliminazione recisa dei messaggi di posta elettronica, il blocco degli URL e la disattivazione dell'inoltro della posta esterna. (Vedi [Azioni di correzione in Microsoft Defender per Office 365](../office-365-security/air-remediation-actions.md).) |
| **Azione di ricerca avanzata** | Azioni eseguite su dispositivi o posta elettronica con [ricerca avanzata.](./advanced-hunting-overview.md) |
| **Azione Esplora risorse** | Azioni eseguite sul contenuto della posta elettronica con [Explorer](../office-365-security/threat-explorer.md). |
| **Azione di risposta in tempo reale manuale** | Azioni eseguite su un dispositivo con [risposta in tempo reale.](../defender-endpoint/live-response.md) Alcuni esempi includono l'eliminazione di un file, l'interruzione di un processo e la rimozione di un'attività pianificata. |
| **Azione di risposta in tempo reale** | Azioni eseguite su un dispositivo con LE API di [Microsoft Defender for Endpoint](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis). Esempi di azioni includono l'isolamento di un dispositivo, l'esecuzione di un'analisi antivirus e il recupero di informazioni su un file. |

## <a name="required-permissions-for-action-center-tasks"></a>Autorizzazioni necessarie per le attività del centro notifiche

Per eseguire attività quali l'approvazione o il rifiuto di azioni in sospeso nel centro notifiche, è necessario disporre delle autorizzazioni elencate nella tabella seguente:

|Azione correttiva |Ruoli e autorizzazioni necessari |
|--|----|
|Microsoft Defender for Endpoint remediation (dispositivi) |**Ruolo amministratore** della sicurezza assegnato in Azure Active Directory (Azure AD) ( ) o nella interfaccia di amministrazione di Microsoft 365 [https://portal.azure.com](https://portal.azure.com) ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- o ---<br/>**Ruolo azioni di correzione attive** assegnato in Microsoft Defender per Endpoint <br/> <br/> Per altre informazioni, vedere le risorse seguenti: <br/>- [Autorizzazioni del ruolo di amministratore in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Creare e gestire ruoli per il controllo dell'accesso basato sui ruoli (Microsoft Defender for Endpoint)](../defender-endpoint/user-roles.md)  |
|Microsoft Defender for Office 365 remediation (Office contenuto e posta elettronica)  |**Ruolo amministratore** della sicurezza assegnato in Azure AD ( [https://portal.azure.com](https://portal.azure.com) ) o nella interfaccia di amministrazione di Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- e --- <br/>**Ruolo di ricerca ed eliminazione** assegnato nel Centro sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**IMPORTANTE:** se il  ruolo Amministratore sicurezza è assegnato solo nel Centro sicurezza & di Office 365 & ( ), non sarà possibile accedere al centro notifiche o alle Microsoft 365 Defender [https://protection.office.com](https://protection.office.com) funzionalità. È necessario disporre del **ruolo amministratore della** sicurezza assegnato in Azure AD o nella interfaccia di amministrazione di Microsoft 365. <br/><br/>Per altre informazioni, vedere le risorse seguenti: <br/>- [Autorizzazioni del ruolo di amministratore in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Autorizzazioni nel Centro sicurezza & conformità](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Gli utenti a cui è **assegnato il ruolo amministratore** globale in Azure AD possono approvare o rifiutare qualsiasi azione in sospeso nel centro notifiche. Tuttavia, come procedura consigliata, l'organizzazione deve limitare il numero di persone a cui è assegnato il **ruolo amministratore** globale. È consigliabile utilizzare i ruoli **Amministratore** **sicurezza,** Azioni di correzione attive e Ricerca ed eliminazione elencati nella tabella precedente per le autorizzazioni del centro notifiche. 

## <a name="next-step"></a>Passaggio successivo 

- [Visualizzare e gestire le azioni correttive](m365d-autoir-actions.md)
