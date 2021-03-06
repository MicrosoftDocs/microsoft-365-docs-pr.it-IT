---
title: Visitare il centro notifiche per visualizzare le azioni di correzione
description: Usare il centro notifiche per visualizzare i dettagli e i risultati dopo un'indagine automatizzata
keywords: azione, centro, autoir, automatizzato, indagine, risposta, correzione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844911"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Visitare il centro notifiche per visualizzare le azioni di correzione

Durante e dopo un'indagine automatizzata, vengono identificate le azioni di correzione per i rilevamenti delle minacce. A seconda della minaccia specifica e della configurazione di [Microsoft Defender for Endpoint](/windows/security/threat-protection) per l'organizzazione, alcune azioni di correzione vengono eseguite automaticamente e altre richiedono l'approvazione. Se si fa parte del team delle operazioni di sicurezza dell'organizzazione, è possibile visualizzare le azioni di correzione [in](manage-auto-investigation.md#remediation-actions) sospeso e completate nel **centro notifiche.** 


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEW!) Un centro notifiche unificato


Siamo lieti di annunciare un nuovo centro notifiche unificato ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Centro notifiche nel centro Microsoft 365 sicurezza":::

Nella tabella seguente viene confrontato il nuovo centro notifiche unificato con il centro notifiche precedente.

|Il nuovo centro notifiche unificato  |Centro notifiche precedente  |
|---------|---------|
|Elenca le azioni in sospeso e completate per i dispositivi e la posta elettronica in un'unica posizione <br/>([Microsoft Defender per Endpoint](microsoft-defender-endpoint.md) più Microsoft Defender per [Office 365](/microsoft-365/security/office-365-security/office-365-atp))|Elenca le azioni in sospeso e completate per i dispositivi <br/> ([Solo Microsoft Defender per Endpoint)](microsoft-defender-endpoint.md)   |
|Si trova in:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Si trova in:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| Nel centro Microsoft 365 sicurezza scegliere **Centro notifiche.** <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Passaggio al Centro notifiche nel centro sicurezza Microsoft 365 sicurezza"::: | Nel riquadro Microsoft Defender Security Center, scegliere **Analisi automatizzate**  >  **Centro notifiche.** <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Spostamento nel centro notifiche dalla Microsoft Defender Security Center":::  |

Il centro notifiche unificato riunisce le azioni di correzione in Defender for Endpoint e Defender per Office 365. Definisce un linguaggio comune per tutte le azioni di correzione e offre un'esperienza di indagine unificata. 

È possibile utilizzare il centro notifiche unificato se si dispone delle autorizzazioni appropriate e di una o più delle sottoscrizioni seguenti:
- [Defender per Endpoint](microsoft-defender-endpoint.md)
- [Defender per Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Per ulteriori informazioni, vedere [Requisiti](/microsoft-365/security/mtp/prerequisites).

## <a name="using-the-action-center"></a>Utilizzo del centro notifiche

Per accedere al centro notifiche unificato nel centro sicurezza Microsoft 365 sicurezza:
1. Accedere al centro Microsoft 365 sicurezza ( [https://security.microsoft.com](https://security.microsoft.com) ) ed eseguire l'accesso.
2. Nel riquadro di spostamento selezionare **Centro notifiche.** 

Quando si visita il centro notifiche, vengono visualizzate due schede: **Azioni in sospeso** e **Cronologia.** Nella tabella seguente sono riepilogati gli elementi che verranno visualizzati in ogni scheda:

|Scheda  |Descrizione  |
|---------|---------|
|**In sospeso**     | Visualizza un elenco di azioni che richiedono attenzione. È possibile approvare o rifiutare le azioni una alla volta oppure selezionare più azioni se hanno lo stesso tipo di azione ( ad esempio **File quarantena**). <br/>**SUGGERIMENTO:** verificare e approvare [(o rifiutare)](manage-auto-investigation.md) le azioni in sospeso il prima possibile in modo che le indagini automatizzate possano essere completate in modo rapido. |
|**Cronologia**     | Funge da log di controllo per le azioni eseguite, ad esempio: <br/>- Azioni correttive intraprese a seguito di indagini automatizzate <br>- Azioni di correzione approvate dal team delle operazioni di sicurezza  <br/>- Comandi eseguiti e azioni di correzione applicate durante le sessioni di Live Response  <br/>- Azioni di correzione eseguite dalle funzionalità di protezione dalle minacce in Antivirus Microsoft Defender  <p>Consente di annullare determinate azioni (vedere [Annullare le azioni completate).](manage-auto-investigation.md#undo-completed-actions)       |

È possibile personalizzare, ordinare, filtrare ed esportare i dati nel centro notifiche.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Colonne e filtri nel centro notifiche":::

- Selezionare un'intestazione di colonna per ordinare gli elementi in ordine crescente o decrescente.
- Utilizzare il filtro periodo di tempo per visualizzare i dati relativi al giorno, alla settimana, ai 30 giorni o ai 6 mesi precedenti.
- Scegliere le colonne che si desidera visualizzare.
- Specificare il numero di elementi da includere in ogni pagina di dati.
- Utilizzare i filtri per visualizzare solo gli elementi che si desidera visualizzare.
- Selezionare **Esporta** per esportare i risultati in .csv file. 

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare e approvare le azioni correttive](manage-auto-investigation.md)
- [Vedere la guida interattiva: Analizzare e correggere le minacce con Microsoft Defender for Endpoint](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>Vedere anche

- [Indirizzare i falsi positivi/negativi in Microsoft Defender per Endpoint](defender-endpoint-false-positives-negatives.md)
