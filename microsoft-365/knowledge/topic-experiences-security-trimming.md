---
title: Topic Experience taglio di sicurezza (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Panoramica del modo in cui viene utilizzata la sicurezza per visualizzare gli argomenti.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698951"
---
# <a name="topic-experiences-security-trimming-preview"></a>Topic Experience taglio di sicurezza (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Altre informazioni su Project Cortex](https://aka.ms/projectcortex).

Topic experiences gli utenti non saranno in grado di visualizzare le informazioni negli argomenti che le autorizzazioni esistenti di Office 365 impediscono loro di vedere. Tutto ciò che un utente vede in una pagina di un argomento (ad esempio, siti di SharePoint, documenti, file) sarà informazioni che sono già autorizzati a visualizzare. L'argomento esperienze non consente di apportare modifiche alle autorizzazioni esistenti.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Perché due utenti possono avere visualizzazioni diverse dello stesso argomento

Quando si crea un argomento tramite AI o con la cura manuale, può contenere una descrizione dell'argomento, nomi alternativi, persone associate all'argomento, nonché siti, pagine e file correlati all'argomento. Quando queste informazioni vengono visualizzate in una pagina di argomento, è possibile che due utenti che stanno visualizzando lo stesso argomento My non vedano le stesse informazioni.
  
Ad esempio, quando l'utente 1 Visualizza la pagina dell'argomento Neptune, questo è ciò che potrebbe vedere.

![Argomento Neptune per l'utente 1](../media/knowledge-management/user2-topic-view.png) </br> 

Tuttavia, quando l'utente 2 Guarda la stessa pagina dell'argomento Neptune, la sua visualizzazione è diversa da quella dell'utente 1.  L'utente 2 è in grado di visualizzare il file di *Panoramica del prodotto DG-2000* nella sezione **file bloccati e pagine** della pagina dell'argomento, che non viene visualizzata per l'utente 1. 

![Argomento Neptune per l'utente 2](../media/knowledge-management/user1-topic-view.png) </br> 

La differenza in quello che gli utenti possono vedere nello stesso argomento è che gli utenti potrebbero non disporre delle autorizzazioni di Office 365 per visualizzare un sito o un file correlato.  L'argomento experiences rispetta le autorizzazioni impostate per gli elementi di un argomento e non è in grado di modificarne l'accesso. In questo esempio, l'utente 1 non è in grado di visualizzare il file di *Panoramica del prodotto DG-2000* nella relativa pagina degli argomenti per Neptune perché l'utente 1 non dispone di autorizzazioni di Office 365 per visualizzare il file.

Se un utente non è in grado di visualizzare informazioni sufficienti in un argomento perché sia utile, l'argomento non sarà disponibile per l'utente. In questo caso, l'argomento evidenziato non verrà visualizzato dall'utente. Tuttavia, un utente diverso che dispone delle autorizzazioni per ulteriori informazioni nell'argomento per essere utile, sarà in grado di vedere l'argomento.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Autorizzazioni di argomento per i responsabili delle informazioni e i collaboratori degli argomenti

Gli utenti a cui vengono assegnate le autorizzazioni per la gestione degli argomenti-Knowledge Manager saranno in grado di visualizzare le informazioni che hanno le autorizzazioni per la visualizzazione all'interno degli argomenti.

Analogamente, gli utenti che dispongono di autorizzazioni per l'argomento Create and Edit sono in grado di visualizzare le informazioni che dispongono di autorizzazioni per la visualizzazione all'interno degli argomenti. 


## <a name="ai-versus-manually-curated-topic-information"></a>Informazioni sull'argomento AI rispetto a quelle curate manualmente

Gli argomenti possono contenere informazioni generate da AI e informazioni aggiunte o modificate da parte di collaboratori o responsabili della conoscenza.

 - Le informazioni contenute in un argomento aggiunto da AI sono visibili solo agli utenti che hanno accesso al contenuto di origine.
 - Le informazioni aggiunte manualmente o modificate da un partecipante all'argomento o Knowledge Manager sono visibili a tutti gli utenti che possono visualizzare l'argomento.

Nella tabella seguente vengono descritti gli utenti, ovvero i visualizzatori di argomenti, i collaboratori e i Knowledge Manager, che possono essere visualizzati in un argomento specifico in base alle autorizzazioni.

|Elemento dell'argomento|Cosa possono vedere gli utenti|
|:---------|:------------------|
|Nome dell'argomento|Gli utenti possono visualizzare il nome dell'argomento di tutti gli argomenti nel centro argomenti. Alcuni argomenti potrebbero non essere visibili se l'utente ha una scarsa pertinenza.|
|Descrizione argomento|Le descrizioni generate AI sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine. Le descrizioni inserite o modificate manualmente sono visibili a tutti gli utenti.|
|Persone|Le persone bloccate sono visibili a tutti gli utenti. Le persone suggerite sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|File|I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Pagine|Le pagine sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Siti|I siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|




## <a name="see-also"></a>Vedere anche

