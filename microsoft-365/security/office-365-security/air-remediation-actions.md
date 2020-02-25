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
ms.openlocfilehash: 433813ed1a801117a88da696392030db5091b54b
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261053"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Azioni di correzione dopo un'analisi automatizzata in Office 365

## <a name="remediation-actions"></a>Azioni correttive

[Le funzionalità di ricerca e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection includono determinate azioni di correzione. Ogni volta che un'indagine automatizzata è in esecuzione o è stata completata, in genere vengono visualizzate una o più operazioni di correzione che richiedono l'approvazione da parte del team di operazioni di sicurezza per procedere. Nella tabella seguente sono riepilogate le azioni di correzione attualmente disponibili in Office 365 Advanced Threat Protection. 

|Azione | Descrizione |
|-----|-----|
|Blocco di URL (al momento del clic) |Proteggi da messaggi di posta elettronica e documenti che contengono URL dannosi. In questo modo è possibile bloccare i collegamenti dannosi e tutte le pagine Web correlate tramite [collegamenti sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) quando l'utente fa clic su un collegamento in un file di Office esistente o in un messaggio di posta elettronica precedente. |
|Elimina messaggio di posta elettronica soft  |Eliminazione temporanea di messaggi di posta elettronica specifici dalla cassetta postale di un utente|
|Cluster di posta elettronica con eliminazione morbida  |Eliminare i messaggi di posta elettronica dannosi che corrispondono a una query da tutte le cassette postali degli utenti|
|Disattivazione dell'inoltro della posta elettronica esterna |Rimuove la regola di inoltro dalla cassetta postale di un utente finale specifico|

## <a name="approve-or-reject-pending-actions"></a>Approva (o rifiuta) azioni in sospeso

![Pagina azione indagini AEREe](../../media/air-investigationactionspage.png)

Durante la visualizzazione dei [Dettagli di un'indagine](air-view-investigation-results.md), è possibile approvare o rifiutare tutte le azioni di correzione in sospeso. Si consiglia di eseguire questa operazione non appena possibile in modo che le indagini automatizzate siano state completate.

> [!IMPORTANT]
> Le autorizzazioni appropriate devono essere approvate o rifiutate. Vedere le [autorizzazioni necessarie per utilizzare le funzionalità aeree](office-365-air.md#required-permissions-to-use-air-capabilities).

1. Selezionare la scheda **azioni** .

2. Selezionare un elemento nell'elenco. (Vengono attivati i pulsanti approva e rifiuta).

3. Esaminare le informazioni disponibili per gli elementi selezionati e quindi approvare o rifiutare le azioni. 
 - **Approvazione** consente di iniziare la correzione.
 - **Rifiuto** non esegue altre azioni

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sul PlayBook di sicurezza degli utenti compromesso](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [Visualizzare i report ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)