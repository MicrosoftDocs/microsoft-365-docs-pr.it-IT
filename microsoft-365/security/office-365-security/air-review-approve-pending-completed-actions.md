---
title: Esaminare e gestire le azioni di correzione in Microsoft Defender per Office 365
keywords: AIR, autoIR, ATP, automatizzato, indagine, risposta, correzione, minacce, avanzate, minaccia, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Informazioni sulle azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: a11e9ee6a4c2426951fe2b4aa4f2dd08d1931f1c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287114"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Esaminare e gestire le azioni correttive in Office 365

Poiché le indagini automatizzate sulla posta elettronica & contenuto di  collaborazione comportano verdetti, ad esempio dannosi o *sospetti,* vengono create determinate azioni correttive. In Microsoft Defender per Office 365, le azioni di correzione possono includere:
- Blocco di un URL (momento del clic)
- Eliminazione recisa dei messaggi di posta elettronica o dei cluster
- Messa in messa in sicurezza di messaggi di posta elettronica o allegati di posta elettronica
- Disattivazione dell'inoltro della posta esterna

Queste azioni di correzione non vengono eseguite a meno che il team delle operazioni di sicurezza non le approvi. È consigliabile rivedere e approvare tutte le azioni in sospeso il prima possibile, in modo che le indagini automatizzate si completino in modo corretto. In alcuni casi, è possibile annullare un'azione correttiva.

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="approve-or-reject-pending-actions"></a>Approvare (o rifiutare) le azioni in sospeso

1. Accedere al Centro sicurezza Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) e accedere.
2. Nel riquadro di spostamento selezionare **Centro notifiche.**
3. Nella scheda **In** sospeso esaminare l'elenco delle azioni in attesa di approvazione.
4. Selezionare un elemento nell'elenco. Viene visualizzato il riquadro a comparsa. 
5. Esaminare le informazioni nel riquadro a comparsa e quindi eseguire una delle operazioni seguenti:
   - Selezionare **Apri pagina di analisi** per visualizzare ulteriori dettagli sull'indagine.
   - Selezionare **Approva** per avviare un'azione in sospeso.
   - Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.

## <a name="undo-one-remediation-action"></a>Annullare un'azione correttiva

1. Accedere al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedere.
2. Nella scheda **Cronologia** selezionare un'azione che si desidera annullare.
3. Nel riquadro sul lato destro dello schermo selezionare **Annulla.**

## <a name="undo-multiple-remediation-actions"></a>Annullare più azioni correttive

1. Accedere al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedere.
2. Nella scheda **Cronologia** selezionare le azioni che si desidera annullare. Assicurarsi di selezionare gli elementi con lo stesso tipo di azione. Verrà visualizzato un riquadro a comparsa.
3. Nel riquadro a comparsa selezionare Annulla.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Per rimuovere un file dalla quarantena su più dispositivi

1. Accedere al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedere.
2. Nella scheda **Cronologia** selezionare un file con il tipo di azione **File quarantena.**
3. Nel riquadro sul lato destro dello schermo, selezionare Applica **a X altre istanze** del file e quindi scegliere **Annulla.**

## <a name="next-steps"></a>Passaggi successivi

- [Usare Esplora minacce](threat-explorer.md)
- [Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Vedere anche

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata in Office 365](air-view-investigation-results.md)
