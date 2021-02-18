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
description: Panoramica del modo in cui viene utilizzata la sicurezza per visualizzare gli argomenti.
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279333"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Limitazione per motivi di sicurezza di Microsoft Viva Topics 

Gli utenti di Viva Topics non possono visualizzare informazioni negli argomenti che le autorizzazioni di Office 365 esistenti ne impediscono la visualizzazione. Tutte le informazioni visualizzate da un utente in una pagina dell'argomento(ad esempio, siti di SharePoint, documenti, file) saranno informazioni che sono già autorizzate a visualizzare. Viva Topics non apporta modifiche alle autorizzazioni esistenti.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Perché due utenti possono avere visualizzazioni diverse dello stesso argomento

Quando un argomento viene creato tramite IA o la gestione manuale, può contenere una descrizione dell'argomento, nomi alternativi, persone associate all'argomento, nonché siti, pagine e file correlati all'argomento. Quando queste informazioni vengono visualizzate in una pagina dell'argomento, è possibile che due utenti che visualizzano lo stesso argomento non visualizzino le stesse informazioni.
  
Ad esempio, quando l'utente 1 visualizza la pagina dell'argomento Neptune, potrebbe vedere questa visualizzazione della pagina dell'argomento.

![Argomento neptune per l'utente 1](../media/knowledge-management/user2-topic-view.png) </br> 

Tuttavia, quando l'utente 2 esamina la stessa pagina dell'argomento neptune, la visualizzazione è diversa dall'utente 1.  L'utente 2 è in grado di visualizzare il file *DG-2000 Product Overview* nella sezione **Pinned files and pages** della pagina dell'argomento, che non viene visualizzata per l'utente 1. 

![Argomento Neptune per l'utente 2](../media/knowledge-management/user1-topic-view.png) </br> 

La differenza tra ciò che gli utenti possono vedere nello stesso argomento è che gli utenti potrebbero non disporre delle autorizzazioni di Office 365 per visualizzare un sito o un file correlato.  Viva Topics rispetta le autorizzazioni impostate per gli elementi di un argomento e non può modificarne l'accesso. In questo esempio, l'utente 1 non è in grado di visualizzare il file *DG-2000 Product Overview* nella pagina dell'argomento per Nettuno perché l'utente 1 non dispone delle autorizzazioni di Office 365 per visualizzare il file.

Se un utente non è in grado di visualizzare informazioni sufficienti in un argomento perché sia utile, l'argomento non sarà disponibile per l'utente. In questo caso, l'utente non visualizza l'argomento evidenziato. Un utente diverso che dispone delle autorizzazioni per ulteriori informazioni nell'argomento per essere utile, sarà in grado di visualizzare l'argomento.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Autorizzazioni per gli argomenti per knowledge manager e collaboratori di argomenti

Gli utenti a cui sono assegnate le autorizzazioni per gestire gli argomenti, i responsabili delle conoscenze, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni necessarie per la visualizzazione all'interno degli argomenti.

Analogamente, gli utenti che dispongono delle autorizzazioni per la creazione e la modifica degli argomenti, i collaboratori degli argomenti, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni per la visualizzazione all'interno degli argomenti. 


## <a name="ai-versus-manually-curated-topic-information"></a>Confronto tra IA e informazioni sull'argomento curate manualmente

Gli argomenti possono contenere informazioni generate dall'intelligenza artificiale e informazioni aggiunte o modificate da collaboratori di argomenti o responsabili delle conoscenze.

 - Le informazioni in un argomento aggiunto dall'intelligenza artificiale sono visibili solo agli utenti che hanno accesso al contenuto di origine.
 - La descrizione dell'argomento e le informazioni sulle persone aggiunte o modificate manualmente da un collaboratore o un responsabile della conoscenza sono visibili a tutti gli utenti che possono visualizzare l'argomento.
 - I file, le pagine e i siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine, sia aggiunte manualmente che dall'intelligenza artificiale.

Nella tabella seguente vengono descritti gli utenti, i visualizzatori di argomenti, i collaboratori e i responsabili delle conoscenze, che possono visualizzare in un determinato argomento in base alle relative autorizzazioni.

|Elemento dell'argomento|Cosa possono vedere gli utenti|
|:---------|:------------------|
|Nome argomento|Gli utenti possono visualizzare il nome dell'argomento di tutti gli argomenti nel Centro argomenti. Alcuni argomenti potrebbero non essere visibili se hanno una pertinenza bassa per l'utente.|
|Descrizione dell'argomento|Le descrizioni generate dall'intelligenza artificiale sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine. Le descrizioni immesse o modificate manualmente sono visibili a tutti gli utenti.|
|Persone|Gli utenti aggiunti sono visibili a tutti gli utenti. Gli utenti suggeriti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|File|I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Pagine|Le pagine sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Siti|I siti sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.|




## <a name="see-also"></a>Vedere anche

