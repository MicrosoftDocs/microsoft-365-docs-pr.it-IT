---
title: Threading della posta elettronica-indagini sui dati
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Quando si gestisce un'analisi dei dati, il threading della posta elettronica analizza una conversazione di posta elettronica e separa ogni messaggio in categorie diverse.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6cc466bf89187f292acd454fd8ca6efb05958d2b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035658"
---
# <a name="email-threading"></a>Threading posta elettronica

Si consideri una conversazione di posta elettronica che si sta protrattando da un po' di tempo. Nella maggior parte dei casi, l'ultimo messaggio di posta elettronica sul thread includerà il contenuto di tutti i messaggi di posta elettronica precedenti. la revisione dell'ultimo messaggio di posta elettronica fornirà un contesto completo della conversazione che è stata eseguita nel thread. Il threading e-mail identifica tali messaggi di posta elettronica in modo che i revisori possano rivedere una frazione dei documenti raccolti senza perdere alcun contesto.

## <a name="what-does-email-threading-do"></a>Cosa fa il threading della posta elettronica?

Il threading della posta elettronica analizza ogni messaggio di posta elettronica e lo desconstructs ai singoli messaggi; ogni messaggio di posta elettronica è una catena di singoli messaggi. Quindi, analizza tutti i messaggi di posta elettronica nel working set per determinare se un messaggio di posta elettronica ha contenuto univoco o se la catena è totalmente contenuta in un altro indirizzo di posta elettronica. Alla fine i messaggi di posta elettronica sono divisi in quattro categorie:

- **Inclusive**: l'ultimo messaggio nella posta elettronica ha contenuto univoco e l'indirizzo di posta elettronica include tutti gli allegati inclusi in altri messaggi di posta elettronica di cui il contenuto è totalmente contenuto in questa e-mail.


- **Inclusive minus**: l'ultimo messaggio nella posta elettronica ha contenuto univoco, ma la posta elettronica non contiene alcuni degli allegati che sono stati inclusi in altri messaggi di posta elettronica di cui il contenuto è totalmente contenuto in questo indirizzo di posta elettronica.

- **Copia inclusiva**: una copia esatta di un messaggio di posta elettronica incluso/incluso

- **None**: il contenuto di questo messaggio di posta elettronica è totalmente contenuto in almeno un messaggio di posta elettronica contrassegnato come incluso/inclusivo meno.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>In che modo è diversa dalle conversazioni in Outlook?
A colpo d'occhio, questo sembra molto simile ai gruppi di conversazione in Outlook. Tuttavia, esistono alcune distinzioni importanti. Si consideri una conversazione di posta elettronica che è stata biforcuta in due conversazioni; ad esempio, qualcuno ha risposto a un messaggio di posta elettronica che non è l'ultimo della conversazione in modo che gli ultimi due messaggi di posta elettronica nella conversazione abbiano entrambi contenuto univoco.

Outlook potrebbe comunque raggruppare i messaggi di posta elettronica in una singola conversazione; leggere solo l'ultimo messaggio di posta elettronica significherebbe mancare il contesto del penultimo messaggio di posta elettronica, che contiene anche contenuti univoci. Poiché il threading della posta elettronica analizza tutti i messaggi di posta elettronica in singoli componenti e li confronta, il threading della posta elettronica contrassegna entrambi gli ultimi due messaggi di posta elettronica come inclusivi, assicurando che non mancherà alcun contesto purché vengano lette tutte le e-mail contrassegnate come inclusive.
