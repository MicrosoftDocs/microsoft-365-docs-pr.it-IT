---
title: Visualizzare e gestire le azioni nel centro notifiche
description: Utilizzare il Centro notifiche per visualizzare e gestire le azioni correttive
keywords: azione, centro, autoair, automatizzato, indagine, risposta, correzione
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
ms.technology: m365d
ms.openlocfilehash: 95c82f815c794662f7eb0ffaabcfb5f81df3e828
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782994"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>Visualizzare e gestire le azioni nel centro notifiche

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Le funzionalità di protezione dalle minacce in Microsoft 365 Defender possono comportare determinate azioni di correzione. Di seguito vengono descritti alcuni esempi:

- [Le indagini automatizzate](m365d-autoir.md) possono comportare azioni di correzione che vengono eseguite automaticamente o in attesa dell'approvazione.
- Antivirus, antimalware e altre funzionalità di protezione dalle minacce possono comportare azioni di correzione, ad esempio il blocco di un file, un URL o un processo o l'invio di un artefatto in quarantena.
- Il team delle operazioni di sicurezza può eseguire [](advanced-hunting-overview.md) azioni di correzione manualmente, ad esempio durante la ricerca avanzata o durante l'analisi [di avvisi](investigate-alerts.md) [o incidenti.](investigate-incidents.md)

> [!NOTE]
> È necessario avere [autorizzazioni appropriate](m365d-action-center.md#required-permissions-for-action-center-tasks) per approvare o rifiutare azioni correttive. Per ulteriori informazioni, vedere i [prerequisiti](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).

## <a name="review-pending-actions-in-the-action-center"></a>Esaminare le azioni in sospeso nel centro notifiche

È importante approvare (o rifiutare) le azioni in sospeso il prima possibile in modo che l’indagine automatizzata possa essere completata nel tempo previsto. 

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 

2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 

3. Nel centro notifiche, nella scheda **In** sospeso, selezionare un elemento nell'elenco. Verrà visualizzato il riquadro a comparsa. Di seguito viene riportato un esempio.

   ![Approvare o rifiutare un’azione](../../media/air-actioncenter-itemselected.png)

4. Esaminare le informazioni nel riquadro a comparsa e quindi eseguire una delle operazioni seguenti:
   - Selezionare **Apri pagina di indagine** per visualizzare ulteriori dettagli sull'indagine.
   - Selezionare **Approva** per avviare un'azione in sospeso.
   - Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.
   - Seleziona **Vai a ricerca** per passare a Ricerca [avanzata.](advanced-hunting-overview.md) 

## <a name="undo-completed-actions"></a>Annullare le azioni completate

Se hai determinato che un dispositivo o un file non è una minaccia, puoi annullare le azioni di correzione eseguite, indipendentemente dal fatto che tali azioni siano state eseguite automaticamente o manualmente. Nel centro notifiche, nella **scheda Cronologia,** è possibile annullare una delle azioni seguenti:  

| Origine azione | Azioni supportate |
|:---|:---|
| - Indagine automatizzata <br/>- Antivirus Microsoft Defender <br/>- Azioni di risposta manuale | - Isola dispositivo <br/>- Limitare l'esecuzione del codice <br/>- Mettere in quarantena un file <br/>- Rimuovere una chiave del Registro di sistema <br/>- Arrestare un servizio <br/>- Disabilitare un driver <br/>- Rimuovere un'attività pianificata |

### <a name="undo-one-remediation-action"></a>Annullare un'azione di correzione

1. Vai al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedi.

2. Nella scheda **Cronologia** selezionare un'azione che si desidera annullare.

3. Nel riquadro sul lato destro dello schermo selezionare **Annulla.**

### <a name="undo-multiple-remediation-actions"></a>Annullare più azioni di correzione

1. Passare al centro notifiche ( https://security.microsoft.com/action-center) ed eseguire l'accesso.

2. Nella scheda **Cronologia** selezionare le azioni che si desidera annullare. Assicurarsi di selezionare gli elementi con lo stesso tipo di azione. Verrà visualizzato un riquadro a comparsa.

3. Nel riquadro a comparsa selezionare **Annulla.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Per rimuovere un file dalla quarantena su più dispositivi 

1. Vai al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedi.

2. Nella scheda **Cronologia** selezionare un file con tipo di azione **File** quarantena.

3. Nel riquadro sul lato destro dello schermo, selezionare Applica a X altre istanze **del file** e quindi scegliere **Annulla.**

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata](m365d-autoir-results.md)
- [Risolvere i falsi positivi o i falsi negativi](m365d-autoir-report-false-positives-negatives.md)
