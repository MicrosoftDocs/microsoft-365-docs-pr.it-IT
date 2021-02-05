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
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107519"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Limitazione per motivi di sicurezza di Microsoft Viva Topics 

Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing. Tutte le informazioni visualizzate da un utente in una pagina dell'argomento(ad esempio, siti di SharePoint, documenti, file) saranno informazioni che sono già autorizzate a visualizzare. Viva Topics non apporta modifiche alle autorizzazioni esistenti.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Perché due utenti possono avere visualizzazioni diverse dello stesso argomento

Quando un argomento viene creato tramite IA o la gestione manuale, può contenere una descrizione dell'argomento, nomi alternativi, persone associate all'argomento, nonché siti, pagine e file correlati all'argomento. Quando queste informazioni vengono visualizzate in una pagina dell'argomento, è possibile che due utenti che visualizzano lo stesso argomento non visualizzino le stesse informazioni.
  
Ad esempio, quando l'utente 1 visualizza la pagina dell'argomento Neptune, potrebbe vedere questa visualizzazione della pagina dell'argomento.

![Argomento Nettuno per l'utente 1](../media/knowledge-management/user2-topic-view.png) </br> 

Tuttavia, quando l'utente 2 esamina la stessa pagina dell'argomento neptune, la visualizzazione è diversa dall'utente 1.  L'utente 2 è in grado di visualizzare il file *DG-2000 Product Overview* nella sezione **Pinned files and pages** della pagina dell'argomento, che non viene visualizzata per l'utente 1. 

![Argomento Neptune per l'utente 2](../media/knowledge-management/user1-topic-view.png) </br> 

La differenza tra ciò che gli utenti possono vedere nello stesso argomento è che gli utenti potrebbero non disporre delle autorizzazioni di Office 365 per visualizzare un sito o un file correlato.  Viva Topics rispetta le autorizzazioni impostate per gli elementi di un argomento e non può modificarli. In questo esempio, l'utente 1 non è in grado di visualizzare il file *DG-2000 Product Overview* nella pagina dell'argomento per Nettuno perché l'utente 1 non dispone delle autorizzazioni di Office 365 per visualizzare il file.

Se un utente non è in grado di visualizzare informazioni sufficienti in un argomento per essere utile, l'argomento non sarà disponibile per l'utente. In questo caso, l'utente non visualizza l'argomento evidenziato. Un utente diverso che dispone delle autorizzazioni per ulteriori informazioni nell'argomento per essere utile, sarà in grado di visualizzare l'argomento.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Autorizzazioni per gli argomenti per knowledge manager e collaboratori di argomenti

Gli utenti a cui sono assegnate le autorizzazioni per gestire gli argomenti, i responsabili delle conoscenze, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni necessarie per la visualizzazione all'interno degli argomenti.

Analogamente, gli utenti che dispongono di autorizzazioni per gli argomenti di creazione e modifica, collaboratori di argomenti, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni per la visualizzazione all'interno degli argomenti. 


## <a name="ai-versus-manually-curated-topic-information"></a>Confronto tra IA e informazioni sull'argomento curate manualmente

Gli argomenti possono contenere informazioni generate dall'intelligenza artificiale e informazioni aggiunte o modificate da collaboratori di argomenti o responsabili delle conoscenze.

 - Le informazioni in un argomento aggiunto dall'intelligenza artificiale sono visibili solo agli utenti che hanno accesso al contenuto di origine.
 - Le informazioni aggiunte o modificate manualmente da un collaboratore o un responsabile della conoscenza sono visibili a tutti gli utenti che possono visualizzare l'argomento.

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

