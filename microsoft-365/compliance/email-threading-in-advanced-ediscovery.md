---
title: Threading della posta elettronica in Advanced eDiscovery
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
description: Quando si esegue un'analisi Advanced eDiscovery, il threading della posta elettronica analizza una conversazione di posta elettronica e separa ogni messaggio in categorie diverse.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285562"
---
# <a name="email-threading-in-advanced-ediscovery"></a>Threading della posta elettronica in Advanced eDiscovery

Considera una conversazione di posta elettronica che è in corso da un po' di tempo. Nella maggior parte dei casi, l'ultimo messaggio di posta elettronica nel thread includerà il contenuto di tutti i messaggi di posta elettronica precedenti. Esaminando l'ultimo messaggio di posta elettronica verrà visualizzato un contesto completo della conversazione che si è verificata nel thread. Il threading della posta elettronica identifica tali messaggi di posta elettronica in modo che i revisori possano esaminare una frazione di documenti raccolti senza perdere alcun contesto.

## <a name="what-does-email-threading-do"></a>Cosa fa il threading della posta elettronica?

Il threading della posta elettronica analizza ogni messaggio di posta elettronica e lo decostruisce in singoli messaggi. ogni messaggio di posta elettronica è una catena di singoli messaggi. Quindi, analizza tutti i messaggi di posta elettronica nel set di revisione per determinare se un messaggio di posta elettronica ha contenuto univoco o se la catena è interamente contenuta in un altro messaggio di posta elettronica. Alla fine i messaggi di posta elettronica sono suddivisi in quattro categorie:

- **Conversazione completa**: l'ultimo messaggio dell'e-mail include contenuto univoco e l'e-mail contiene tutti gli allegati inclusi in altri messaggi di posta elettronica il cui contenuto è interamente incluso in questa e-mail.

- **Conversazione completa senza allegati**: l'ultimo messaggio dell'e-mail include contenuto univoco e l'e-mail, ma non contiene tutti gli allegati inclusi in altri messaggi di posta elettronica il cui contenuto sia interamente incluso in questa e-mail.

- **Copia della conversazione completa**: una copia esatta di una conversazione completa o di una conversazione completa senza allegati.

- **Nessuno**: il contenuto di questa e-mail è interamente contenuto in una conversazione completa o una conversazione completa senza allegati.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>In che modo è diverso dalle conversazioni in Outlook?

A colpo d'occhio, questo sembra simile ai raggruppamenti di conversazioni in Outlook. Tuttavia, esistono alcune importanti distinzioni. Considerare una conversazione di posta elettronica che è stata suddivisa in due conversazioni; ad esempio, qualcuno ha risposto a un messaggio di posta elettronica che non è l'ultimo della conversazione, quindi gli ultimi due messaggi di posta elettronica nella conversazione hanno contenuto univoco.

Outlook ancora raggruppare i messaggi di posta elettronica in una singola conversazione; leggere solo l'ultimo messaggio di posta elettronica significa mancare il contesto del secondo-ultimo messaggio di posta elettronica, che contiene anche contenuto univoco. Poiché il threading della posta elettronica analizza ogni messaggio di posta elettronica in singoli componenti e li confronta, il threading della posta elettronica contrassegna entrambi gli ultimi due messaggi come inclusivi, assicurandosi di non perdere alcun contesto finché si leggono tutti i messaggi contrassegnati come inclusivi.
