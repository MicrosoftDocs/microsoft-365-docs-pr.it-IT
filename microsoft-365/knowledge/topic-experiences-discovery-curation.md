---
title: 'Individuazione e cura degli argomenti di Microsoft Viva Topics  '
description: Panoramica del modo in cui vengono individuati gli argomenti.
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2f4c726849d438738f3c0d432daab53ee27b19ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917429"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Individuazione e cura di Microsoft Viva Topics 

Viva Topics organizza le informazioni per conoscere l'ambiente Microsoft 365. Tutti i documenti e le pagine del sito sono stati oggetto di un'esperienza di lettura in cui si riscontrano termini di cui non si ha familiarità. Molte volte interrompiamo ciò che stiamo facendo per dedicare tempo prezioso alla ricerca di ulteriori informazioni.

Viva Topics usa Microsoft Graph e AI per identificare **gli argomenti** nell'organizzazione.  Un argomento è una frase o un termine che ha un significato specifico per l'organizzazione e dispone di risorse ad esso correlate che possono aiutare gli utenti a comprendere che cos'è e a trovare ulteriori informazioni su di esso. Ci sono molti tipi di argomenti importanti per la tua organizzazione. Inizialmente, è possibile identificare i seguenti tipi di argomenti:
- Project
- Evento
- Organizzazione
- Posizione
- Prodotto
- Lavoro creativo
- Campo di studio

L'intelligenza artificiale identifica le persone e i contenuti connessi all'argomento e, se ne viene individuato un numero sufficiente, diventa un argomento consigliato. Cerca di identificare le proprietà seguenti e visualizzarle in una **pagina Argomento:**
- Nomi alternativi e/o acronimi.
- Una breve descrizione dell'argomento.
- Persone che potrebbero essere informate sull'argomento.
- File, pagine e siti correlati all'argomento.

Le proprietà vengono identificate dai file e dalle pagine che fanno parte della prova per identificare l'argomento. I nomi alternativi e gli acronimi derivano da questi file e pagine. La breve descrizione viene fornita da questi file e pagine o da Internet tramite Wikipedia. Viene fatto riferimento al file di origine, alla pagina o all'articolo di Wikipedia insieme alle proprietà suggerite. Le persone vengono suggerite in base ai contributi attivi (ad esempio, le modifiche) ai file e alle pagine. Un riferimento alla quantità di contributi di una determinata persona fornisce un suggerimento sul motivo per cui la persona è stata identificata. I file, le pagine e i siti vengono classificati in base al fatto che siano o meno centrali per l'argomento, indipendentemente dal fatto che possano fornire una panoramica o un'introduzione all'argomento. 

Non tutti gli argomenti identificati saranno utili per l'organizzazione. Potrebbe non aver identificato i nomi alternativi, le descrizioni, le persone o il contenuto appropriati. Pertanto, la possibilità di aggiungere argomenti non identificati, mantenere argomenti suggeriti e argomenti curati è fondamentale per migliorare la qualità degli argomenti individuabili nell'organizzazione.

Viva Topics, quindi, quando il contesto è appropriato, suggerirà questi argomenti da evidenziare in tutte le pagine del sito moderno di SharePoint nel tenant. È inoltre possibile fare riferimento direttamente all'argomento nella pagina del sito moderno di SharePoint da un autore della pagina. Quando un utente è incuriosito di saperne di  più su un argomento, può selezionare l'argomento evidenziato per visualizzare una scheda di riepilogo argomento che fornisce una breve descrizione. Se vogliono saperne di più,  possono selezionare un collegamento Dettagli argomento nel riepilogo per aprire la pagina dell'argomento dettagliato.

![Highlight degli argomenti](../media/knowledge-management/saturn.png) </br>

Inoltre, gli utenti saranno in grado di trovare argomenti tramite Microsoft Search.

## <a name="topic-curation-and-feedback"></a>Feedback e cura degli argomenti

Viva Topics accoglie con favore il contributo umano per migliorare la qualità dei tuoi argomenti. Sebbene l'IA identifichi e suggerisca inizialmente gli argomenti, le modifiche apportate manualmente al contenuto dai collaboratori, gli argomenti aggiunti manualmente, la conferma da parte degli utenti per le proprietà e i contenuti individuati dall'IA e il feedback sull'utilità degli argomenti sono tutti essenziali.

- Gli argomenti possono essere esaminati **dai knowledge manager** dell'organizzazione. Il responsabile della knowledge base può esaminare gli argomenti che dispongono delle autorizzazioni per visualizzare. Nella pagina Gestisci argomenti del Centro argomenti, possono scegliere di confermare gli argomenti generati dall'IA ("argomenti suggeriti") come validi, rifiutare gli argomenti per evitare che il contenuto venga visualizzato come argomento, creare argomenti che non sono stati individuati dall'IA o identificare gli argomenti che potrebbero trarre vantaggio da alcune modifiche da parte di esperti in materia per essere più utili o accurati. Per ulteriori informazioni, vedere [Gestire gli argomenti nel Centro argomenti.](manage-topics.md)

- È possibile *assegnare autorizzazioni* per la creazione e la modifica degli argomenti a qualsiasi utente con licenza in modo che possa apportare modifiche agli argomenti esistenti o creare nuovi argomenti. Ciò consente agli utenti esperti dell'argomento di aggiornare direttamente la pagina dell'argomento per apportare correzioni o aggiungere ulteriori informazioni. Possono anche aggiungere nuovi argomenti che l'IA non è stato in grado di identificare. Se sono disponibili informazioni sufficienti su questi argomenti aggiunti manualmente e l'intelligenza artificiale è in grado di identificare questo tipo di argomento, ulteriori suggerimenti dell'IA potrebbero migliorare questi argomenti aggiunti manualmente. Insieme, gli umani e l'intelligenza artificiale possono mantenere accurate le conoscenze nel tempo e non avere questo riposo su una singola persona. Per ulteriori informazioni, vedere [Create a new topic](./create-a-topic.md) e Edit a [topic](./edit-a-topic.md).

- Anche gli utenti che dispongono solo dell'accesso in lettura all'argomento (visualizzatori di argomenti) verranno invitati a verificare l'utilità di argomenti specifici. Nella scheda Riepilogo argomento vengono **poste** domande di feedback per migliorare il valore dell'argomento e le relative informazioni. Le domande sulla qualità e sull'utilità dei suggerimenti di intelligenza artificiale vengono presentate agli utenti una alla volta. Le domande includono:</br>

    1. L'identificazione dell'argomento nella pagina di SharePoint è stata utile. Se non è accurato o utile, è possibile rimuovere l'evidenziazione. Se un numero sufficiente di persone indica che un argomento non è stato identificato correttamente in una determinata pagina, questa evidenziazione verrà rimossa per tutti gli utenti. 

    2. Indica se l'argomento suggerito è utile per l'organizzazione. Se un numero sufficiente di persone indica che l'argomento suggerito è utile, l'argomento viene confermato automaticamente. In alternativa, se l'argomento suggerito non è valido, l'argomento viene rifiutato automaticamente. Il Knowledge Manager può osservare questa attività nella visualizzazione Gestisci argomenti.

    3. Indica se le persone e i suggerimenti per le risorse sono utili.

    4. Nella home page del Centro argomenti è possibile visualizzare gli argomenti dell'organizzazione a cui si dispone di una connessione. Puoi scegliere di rimanere nell'elenco dell'argomento o di rimuoverlo. Questo feedback si riflette su tutti gli utenti che individuano questo argomento. Vedi [Panoramica del Centro argomenti](./topic-center-overview.md) per altri dettagli nella home page del Centro argomenti.

Anche con le modifiche umane, l'IA cerca continuamente ulteriori informazioni sugli argomenti e cerca la verifica umana. Ad esempio, se l'IA pensa che tu sia una persona che dovrebbe essere elencata come esperta in un argomento, ti chiederà di confermarlo. 


## <a name="see-also"></a>Vedere anche