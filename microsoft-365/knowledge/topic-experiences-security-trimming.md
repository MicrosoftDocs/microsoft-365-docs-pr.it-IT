---
title: Limitazione per motivi di sicurezza di Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Panoramica dell'utilizzo della sicurezza per visualizzare gli argomenti.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939624"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Limitazione per motivi di sicurezza di Microsoft Viva Topics 

Gli utenti di Viva Topics non possono visualizzare informazioni negli argomenti che le autorizzazioni di Office 365 esistenti impediscono loro di visualizzare. Tutti gli elementi visualizzati da un utente in una pagina dell'argomento, ad esempio siti di SharePoint, documenti, file, saranno informazioni che possono già visualizzare. Viva Topics non apporta modifiche alle autorizzazioni esistenti.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Perché due utenti possono avere visualizzazioni diverse dello stesso argomento

Quando un argomento viene creato tramite IA o la cura manuale, può contenere una descrizione dell'argomento, nomi alternativi, persone associate all'argomento, nonché siti, pagine e file correlati all'argomento. Quando queste informazioni vengono visualizzate in una pagina dell'argomento, è possibile che due utenti che visualizzano lo stesso argomento non visualizzino le stesse informazioni.
  
Ad esempio, quando l'utente 1 visualizza la pagina dell'argomento Nettuno, potrebbe visualizzare questa visualizzazione della pagina dell'argomento.

![Argomento Nettuno per l'utente 1](../media/knowledge-management/user2-topic-view.png) </br> 

Tuttavia, quando l'utente 2 esamina la stessa pagina dell'argomento di Nettuno, la relativa visualizzazione è diversa dall'utente 1.  L'utente 2 è in grado di visualizzare il file *DG-2000 Product Overview* nella sezione **File** e pagine aggiunti della pagina dell'argomento, che non viene visualizzata per l'utente 1. 

![Argomento Nettuno per l'utente 2](../media/knowledge-management/user1-topic-view.png) </br> 

La differenza tra ciò che gli utenti possono visualizzare nello stesso argomento è che gli utenti potrebbero non disporre delle autorizzazioni di Office 365 per visualizzare un sito o un file correlato.  Viva Topics rispetta le autorizzazioni impostate per gli elementi di un argomento e non può modificarne l'accesso. In questo esempio, l'utente 1 non è in grado di visualizzare il file *DG-2000 Product Overview* nella pagina dell'argomento relativa a Nettuno perché l'utente 1 non dispone delle autorizzazioni di Office 365 per visualizzare il file.

Se un utente non è in grado di visualizzare informazioni sufficienti in un argomento per essere utile, l'argomento non sarà disponibile per l'utente. In questo caso, l'utente non visualizza l'argomento evidenziato. Un utente diverso che dispone delle autorizzazioni per ulteriori informazioni nell'argomento in modo che sia utile, sarà in grado di visualizzare l'argomento.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Autorizzazioni per gli argomenti per i knowledge manager e i collaboratori degli argomenti

Gli utenti a cui sono assegnate le autorizzazioni per gestire gli argomenti, i responsabili delle conoscenze, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni necessarie per la visualizzazione all'interno degli argomenti.

Analogamente, gli utenti che dispongono di autorizzazioni per la creazione e la modifica di argomenti, i collaboratori di argomenti, potranno visualizzare solo le informazioni di cui dispongono delle autorizzazioni per visualizzare gli argomenti. 


## <a name="ai-versus-manually-curated-topic-information"></a>IA e informazioni sugli argomenti curati manualmente

Gli argomenti possono contenere informazioni generate dall'IA e informazioni aggiunte o modificate da collaboratori o knowledge manager.

 - Le informazioni in un argomento aggiunto dall'IA sono visibili solo agli utenti che hanno accesso al contenuto di origine.
 - La descrizione dell'argomento e le informazioni sulle persone aggiunte o modificate manualmente da un collaboratore o da un responsabile della conoscenza sono visibili a tutti gli utenti che possono visualizzare l'argomento.
 - I file, le pagine e i siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine, sia aggiunte manualmente o aggiunte dall'IA.

Nella tabella seguente vengono descritti gli elementi che gli utenti, i visualizzatori di argomenti, i collaboratori e i responsabili della conoscenza, possono visualizzare in un determinato argomento in base alle autorizzazioni.

|Elemento argomento|Cosa possono vedere gli utenti|
|:---------|:------------------|
|Nome argomento|Gli utenti possono visualizzare il nome degli argomenti nel Centro argomenti. Alcuni argomenti potrebbero non essere visibili se gli utenti non dispongono delle autorizzazioni per il contenuto di origine o hanno una pertinenza bassa per l'utente.|
|Descrizione argomento|Le descrizioni generate dall'IA sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine. Le descrizioni immesse o modificate manualmente sono visibili a tutti gli utenti.|
|Persone|Gli utenti aggiunti sono visibili a tutti gli utenti. Gli utenti suggeriti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|File|I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Pagine|Le pagine sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Siti|I siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|




## <a name="see-also"></a>Vedere anche

