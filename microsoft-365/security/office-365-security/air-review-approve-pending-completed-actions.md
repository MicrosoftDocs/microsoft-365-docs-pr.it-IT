---
title: Esaminare e gestire le azioni di correzione in Microsoft Defender per Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automatizzato, indagine, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028932"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Esaminare e gestire le azioni di correzione in Office 365

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)

Poiché le indagini automatizzate sulla posta elettronica & contenuto di  collaborazione comportano verdetti, ad esempio dannosi o *sospetti,* vengono create determinate azioni di correzione. In Microsoft Defender per Office 365, le azioni di correzione possono includere:

- Eliminazione recisa dei messaggi di posta elettronica o dei cluster
- Disattivazione dell'inoltro della posta esterna

Queste azioni di correzione non vengono eseguite a meno che il team delle operazioni di sicurezza non le approvi. È consigliabile rivedere e approvare tutte le azioni in sospeso il prima possibile, in modo che le indagini automatizzate si completino in modo appropriato. In alcuni casi, è possibile riconsiderare le azioni inviate.  È necessario essere parte del ruolo di & di eliminazione prima di eseguire qualsiasi azione.


## <a name="approve-or-reject-pending-actions"></a>Approvare (o rifiutare) le azioni in sospeso
Esistono quattro modi diversi per trovare ed eseguire azioni di indagine automatica:

- [Coda eventi imprevisti](https://security.microsoft.com/incidents)
- [Centro notifiche](https://security.microsoft.com/action-center/pending)
- Indagine stessa (accessibile tramite evento imprevisto o da un avviso)
- [Coda delle indagini di analisi e correzione](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Coda eventi imprevisti
1. Accedere al Centro [sicurezza Microsoft 365 e](https://security.microsoft.com) accedere.
2. Nel riquadro di spostamento selezionare **Eventi imprevisti & avvisi > eventi imprevisti**.
3. Selezionare il nome di un evento imprevisto per aprire la relativa pagina di riepilogo.
4. Selezionare la **scheda Prova e** risposta.
5. Selezionare un elemento nell'elenco. Viene aperto il riquadro laterale.
6. Nel riquadro laterale, eseguire le azioni di approvazione o rifiuto.

## <a name="investigation-queue"></a>Coda di analisi 
1. Accedere al Centro [sicurezza Microsoft 365 e](https://security.microsoft.com) accedere.
2. Passare dalla pagina avvisi/eventi imprevisti. 
3. Nella pagina Indagine passare alla scheda **Azioni in** sospeso. 
4. Selezionare un elemento nell'elenco. Viene aperto il riquadro laterale.  
5. Nel riquadro laterale, eseguire le azioni di approvazione o rifiuto.

## <a name="action-center"></a>Centro notifiche
1. Accedere al Centro [sicurezza Microsoft 365 e](https://security.microsoft.com) accedere.
2. Nel riquadro di spostamento selezionare **Centro notifiche.**
3. Nella scheda **In** sospeso esaminare l'elenco delle azioni in attesa di approvazione.
   - Selezionare **Apri pagina di indagine** per visualizzare ulteriori dettagli sull'indagine.
   - Selezionare **Approva** per avviare un'azione in sospeso.
   - Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.

## <a name="investigation-and-remediation-investigations-queue"></a>Coda delle indagini di analisi e correzione
1. Accedere al Centro [sicurezza Microsoft 365 e](https://security.microsoft.com) accedere.
2. Aprire indagini in sospeso. 
3. Nella pagina Indagine passare alla scheda **Azioni in** sospeso.
4. Selezionare un elemento nell'elenco. Viene aperto il riquadro laterale.  
5. Nel riquadro laterale, eseguire le azioni di approvazione o rifiuto.

## <a name="change-or-undo-one-remediation-action"></a>Modificare o annullare un'azione di correzione

Esistono due modi diversi per riconsiderare le azioni inviate:
   - Tramite il [centro notifiche unificato](https://security.microsoft.com/action-center).
   - Anche se [il Office action center](https://security.microsoft.com/threatincidents).
   
## <a name="change-or-undo-through-the-unified-action-center"></a>Modificare o annullare il centro notifiche unificato
1. Passare al [centro notifiche unificato](https://security.microsoft.com/action-center) ed eseguire l'accesso.
2. Nella scheda **Cronologia** selezionare un'azione che si desidera modificare o annullare.
3. Nel riquadro sul lato destro dello schermo, selezionare l'azione appropriata **(** sposta nella posta in **arrivo,** sposta nella posta **indesiderata,** passa agli elementi eliminati, **eliminazione recidiva o **elimina definitivamente**).

 ## <a name="change-or-undo-through-the-office-action-center"></a>Modifica o annullamento tramite il Office notifiche 
1. Accedere al Office [action center](https://security.microsoft.com/threatincidents) ed eseguire l'accesso.
2. Selezionare la correzione appropriata.
3. Nel riquadro laterale fare clic sulla voce relativa agli invii di posta e attendere il caricamento dell'elenco. 
4. Attendere che il pulsante Azione nella parte superiore sia abilitato e selezionare il pulsante Azione per modificare il tipo di azione. 
5. Verranno create le azioni appropriate.

## <a name="next-steps"></a>Passaggi successivi

- [Usare Esplora minacce](threat-explorer.md) 
- [Admin /Manual Actions](remediate-malicious-email-delivered-office-365.md)
- [Come segnalare falsi positivi/negativi nelle funzionalità di indagine e risposta automatizzate](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Vedere anche

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata in Office 365](air-view-investigation-results.md)
