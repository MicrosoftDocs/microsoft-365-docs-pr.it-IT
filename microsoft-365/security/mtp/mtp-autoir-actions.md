---
title: Approvare o rifiutare le azioni in sospeso in seguito a un'indagine automatizzata
description: Utilizzare il centro notifiche per gestire le azioni relative all’analisi e alla risposta automatizzate
keywords: azione, centro, autoair, automatizzato, indagine, risposta, correzione
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
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930379"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Approvare o rifiutare le azioni in sospeso in seguito a un'indagine automatizzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Quando viene eseguita un’indagine automatizzata, può dare come risultato una o più [azioni di correzione](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) che richiedono l’approvazione prima di procedere. Ad esempio, potrebbe essere necessario eliminare un gruppo di email o potrebbe essere necessario eliminare un file in quarantena. È importante approvare (o rifiutare) le azioni in sospeso il prima possibile in modo che l’indagine automatizzata possa essere completata nel tempo previsto. 

> [!TIP]
> Se ritieni che qualcosa sia stato perso o rilevato in modo errato dalle funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender, contattaci. Vedere Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta [automatizzate (AIR) in Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

Le azioni in sospeso possono essere esaminate e approvate utilizzando il centro [notifiche](#review-a-pending-action-in-the-action-center) o la [visualizzazione dei dettagli dell'indagine.](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> È necessario avere [autorizzazioni appropriate](mtp-action-center.md#required-permissions-for-action-center-tasks) per approvare o rifiutare azioni correttive. Per ulteriori informazioni, vedere [Prerequisiti per l'analisi e la risposta automatizzate in Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)

## <a name="review-a-pending-action-in-the-action-center"></a>Rivedere un'azione in sospeso nel centro notifiche

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l’accesso. 

2. Nel riquadro di spostamento fare clic su **Centro notifiche**. 

3. Nel centro notifiche, nella scheda **In sospeso**, selezionare un elemento dall’elenco. 

    - Se si seleziona un elemento nella colonna **Numero indagine**, verrà visualizzata la pagina con i dettagli sulle indagini. In questa pagina è possibile visualizzare i risultati dell'indagine e quindi approvare o rifiutare l'azione consigliata.
 
    - Se si seleziona una riga nell'elenco, verrà visualizzato un riquadro a comparsa, in cui sarà possibile vedere le informazioni su quell'elemento. <br/>![Approvare o rifiutare un’azione](../../media/air-actioncenter-itemselected.png)<br/>Utilizzare i collegamenti per visualizzare un avviso associato o un’indagine e approvare o rifiutare l’azione.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Rivedere un'azione in sospeso nella visualizzazione dettagli indagini

![Dettagli indagine](../../media/mtp-air-investdetails.png)

1. In una pagina di [investigazione dettagli](mtp-autoir-results.md), selezionare la scheda **azioni in sospeso** (o **Azioni**). Gli elementi in attesa di approvazione sono elencati in questa scheda.

2. Selezionare un elemento nella lista, quindi scegliere **Approva** o **Rifiuta**.

## <a name="undo-completed-actions"></a>Annullamento delle azioni completate

Se hai determinato che un dispositivo o un file non è una minaccia, puoi annullare le azioni di correzione eseguite, indipendentemente dal fatto che siano state eseguite automaticamente o manualmente. Nella scheda Cronologia del  centro notifiche è possibile annullare una delle azioni seguenti:  

| Origine azione | Azioni supportate |
|:---|:---|
| - Indagine automatizzata <br/>- Microsoft Defender Antivirus <br/>- Azioni di risposta manuali | - Isolare il dispositivo <br/>- Limitare l'esecuzione del codice <br/>- Mettere in quarantena un file <br/>- Rimuovere una chiave del Registro di sistema <br/>- Arrestare un servizio <br/>- Disabilitare un driver <br/>- Rimuovere un'attività pianificata |

### <a name="to-undo-a-remediation-action"></a>Per annullare un'azione correttiva

1. Accedere al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedere.

2. Nella scheda **Cronologia** selezionare un'azione che si desidera annullare.

3. Nel riquadro sul lato destro dello schermo selezionare **Annulla.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Per rimuovere un file dalla quarantena su più dispositivi 

1. Accedere al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedere.

2. Nella scheda **Cronologia** selezionare un file con il tipo di azione **File quarantena.**

3. Nel riquadro sul lato destro dello schermo, selezionare Applica a X altre istanze del **file,** quindi scegliere **Annulla.**

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata](mtp-autoir-results.md)
- [Gestire falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate](mtp-autoir-report-false-positives-negatives.md)
