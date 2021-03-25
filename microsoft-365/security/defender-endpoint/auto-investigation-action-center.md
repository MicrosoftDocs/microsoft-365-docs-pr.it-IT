---
title: Visitare il centro notifiche per visualizzare le azioni di correzione
description: Usare il centro notifiche per visualizzare i dettagli e i risultati dopo un'indagine automatizzata
keywords: azione, centro, autoir, automatizzato, indagine, risposta, correzione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: 6caa1cfe08a20aa824d85966c104a25988b8be53
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165358"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Visitare il centro notifiche per visualizzare le azioni di correzione

Durante e dopo un'indagine automatizzata, vengono identificate le azioni di correzione per i rilevamenti delle minacce. A seconda della minaccia specifica e della configurazione di [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) per l'organizzazione, alcune azioni di correzione vengono eseguite automaticamente e altre richiedono l'approvazione. Se si fa parte del team delle operazioni di sicurezza dell'organizzazione, è possibile visualizzare le azioni di correzione [in](manage-auto-investigation.md#remediation-actions) sospeso e completate nel **centro notifiche.** 


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEW!) Un centro notifiche unificato


Siamo lieti di annunciare un nuovo centro notifiche unificato ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Centro notifiche nel centro sicurezza Microsoft 365":::

Nella tabella seguente viene confrontato il nuovo centro notifiche unificato con il centro notifiche precedente.

|Il nuovo centro notifiche unificato  |Centro notifiche precedente  |
|---------|---------|
|Elenca le azioni in sospeso e completate per i dispositivi e la posta elettronica in un'unica posizione <br/>([Microsoft Defender per Endpoint](microsoft-defender-advanced-threat-protection.md) più Microsoft Defender per Office [365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))|Elenca le azioni in sospeso e completate per i dispositivi <br/> ([Solo Microsoft Defender per Endpoint)](microsoft-defender-advanced-threat-protection.md)   |
|Si trova in:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Si trova in:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| Nel Centro sicurezza Microsoft 365 scegliere **Centro notifiche.** <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Passaggio al Centro notifiche nel Centro sicurezza Microsoft 365"::: | In Microsoft Defender Security Center scegli **Centro notifiche** indagini  >  **automatizzate.** <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Passaggio al centro notifiche dal Microsoft Defender Security Center":::  |

Il centro notifiche unificato riunisce le azioni di correzione in Defender for Endpoint e Defender per Office 365. Definisce un linguaggio comune per tutte le azioni di correzione e offre un'esperienza di indagine unificata. 

È possibile utilizzare il centro notifiche unificato se si dispone delle autorizzazioni appropriate e di una o più delle sottoscrizioni seguenti:
- [Defender per endpoint](microsoft-defender-advanced-threat-protection.md)
- [Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Per ulteriori informazioni, vedere [Requisiti](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).

## <a name="using-the-action-center"></a>Utilizzo del centro notifiche

Per accedere al centro notifiche unificato nel Centro sicurezza Microsoft 365 migliorato:
1. Accedere al Centro sicurezza Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e accedere.
2. Nel riquadro di spostamento selezionare **Centro notifiche.** 

Quando si visita il centro notifiche, vengono visualizzate due schede: **Azioni in sospeso** e **Cronologia.** Nella tabella seguente sono riepilogati gli elementi che verranno visualizzati in ogni scheda:

|Scheda  |Descrizione  |
|---------|---------|
|**In sospeso**     | Visualizza un elenco di azioni che richiedono attenzione. È possibile approvare o rifiutare le azioni una alla volta oppure selezionare più azioni se hanno lo stesso tipo di azione ( ad esempio **File quarantena**). <br/>**SUGGERIMENTO:** verificare e approvare [(o rifiutare)](manage-auto-investigation.md) le azioni in sospeso il prima possibile in modo che le indagini automatizzate possano essere completate in modo rapido. |
|**Cronologia**     | Funge da log di controllo per le azioni eseguite, ad esempio: <br/>- Azioni correttive intraprese a seguito di indagini automatizzate <br>- Azioni di correzione approvate dal team delle operazioni di sicurezza  <br/>- Comandi eseguiti e azioni di correzione applicate durante le sessioni di Live Response  <br/>- Azioni di correzione eseguite dalle funzionalità di protezione dalle minacce in Microsoft Defender Antivirus  <p>Consente di annullare determinate azioni (vedere [Annullare le azioni completate).](manage-auto-investigation.md#undo-completed-actions)       |

È possibile personalizzare, ordinare, filtrare ed esportare i dati nel centro notifiche.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Colonne e filtri nel centro notifiche":::

- Selezionare un'intestazione di colonna per ordinare gli elementi in ordine crescente o decrescente.
- Utilizzare il filtro periodo di tempo per visualizzare i dati relativi al giorno, alla settimana, ai 30 giorni o ai 6 mesi precedenti.
- Scegliere le colonne che si desidera visualizzare.
- Specificare il numero di elementi da includere in ogni pagina di dati.
- Utilizzare i filtri per visualizzare solo gli elementi che si desidera visualizzare.
- Selezionare **Esporta** per esportare i risultati in un file CSV. 

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare e approvare le azioni di correzione](manage-auto-investigation.md)
- [Vedere la guida interattiva: Analizzare e correggere le minacce con Microsoft Defender for Endpoint](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>Vedere anche

- [Risolvere i falsi positivi/negativi in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md)
