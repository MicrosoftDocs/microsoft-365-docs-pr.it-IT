---
title: Azioni di correzione nell'analisi e nella risposta automatizzate di Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Informazioni sulle azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836859"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Azioni di correzione dopo un'analisi automatizzata in Office 365

## <a name="remediation-actions"></a>Azioni correttive

[Le funzionalità di ricerca e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) piano 2 includono determinate azioni di correzione. Ogni volta che un'indagine automatizzata è in esecuzione o è stata completata, in genere vengono visualizzate una o più operazioni di correzione che richiedono l'approvazione da parte del team di operazioni di sicurezza per procedere. 

Nella tabella seguente sono riepilogate le azioni di correzione attualmente disponibili in Office 365 ATP. 

|Azione | Descrizione |
|-----|-----|
|Blocco di URL (al momento del clic) |Protegge da messaggi di posta elettronica e documenti che contengono URL dannosi. In questo modo è possibile bloccare i collegamenti dannosi e tutte le pagine Web correlate tramite [collegamenti sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) quando l'utente fa clic su un collegamento in un file di Office esistente o in un messaggio di posta elettronica precedente. |
|Elimina messaggio di posta elettronica soft  |Elimina temporaneamente i messaggi di posta elettronica specifici dalla cassetta postale di un utente. <br/>Un messaggio eliminato temporaneamente viene spostato nella cartella elementi ripristinabili di un utente e viene mantenuto fino alla scadenza del periodo di conservazione dell'elemento eliminato. |
|Cluster di posta elettronica con eliminazione morbida  |Eliminare i messaggi di posta elettronica dannosi che corrispondono a una query da tutte le cassette postali degli utenti. <br/>I messaggi eliminati temporaneamente vengono spostati nella cartella elementi ripristinabili degli utenti e vengono mantenuti fino alla scadenza del periodo di conservazione dell'elemento eliminato. |
|Disattivazione dell'inoltro della posta elettronica esterna |Rimuove una regola di inoltro dalla cassetta postale di un utente finale specifico.|

> [!NOTE]
> In Office 365 ATP, non viene eseguita automaticamente alcuna azione di correzione. Le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team di sicurezza dell'organizzazione. 

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare le azioni di correzione in sospeso o completate dopo un'analisi automatizzata in Office 365](air-review-approve-pending-completed-actions.md)

- [Informazioni dettagliate e risultati di un'indagine automatizzata in Office 365](air-view-investigation-results.md)