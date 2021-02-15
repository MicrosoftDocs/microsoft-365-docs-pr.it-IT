---
title: 'Microsoft Viva Topics, individuazione e cura degli argomenti  '
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
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 435544de1016552c6ce3d39c73f7127223f36331
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107709"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Microsoft Viva Topics discovery and curation 

Viva Topics organizza le informazioni per conoscere l'ambiente Microsoft 365. Tutti gli utenti hanno letto documenti e pagine del sito in cui si riscontrano termini con cui non si ha familiarità. Molte volte interrompiamo ciò che stiamo facendo per dedicare tempo prezioso alla ricerca di altre informazioni.

Viva Topics usa Microsoft Graph e L'intelligenza artificiale per **identificare gli argomenti** nell'organizzazione.  Un argomento è una frase o un termine che ha un significato specifico per l'organizzazione e dispone di risorse ad esso correlate che possono aiutare gli utenti a capire cos'è e a trovare ulteriori informazioni su di esso. Esistono molti tipi diversi di argomenti che saranno importanti per l'organizzazione. Inizialmente, è possibile identificare i seguenti tipi di argomenti:
- Project
- Evento
- Organizzazione
- Posizione
- Prodotto
- Lavoro creativo
- Campo di studio

L'intelligenza artificiale identifica le persone e i contenuti connessi all'argomento e, se ne viene individuato abbastanza, diventa un argomento consigliato. Cerca di identificare le proprietà seguenti e visualizzarle in una **pagina Dell'argomento:**
- Nomi alternativi e/o acronimi.
- Breve descrizione dell'argomento.
- Persone che potrebbero essere a conoscenza dell'argomento.
- File, pagine e siti correlati all'argomento.

Le proprietà vengono identificate dai file e dalle pagine che fanno parte della prova per identificare l'argomento. I nomi alternativi e gli acronimi derivano da questi file e pagine. La breve descrizione viene fornita da questi file e pagine o da Internet tramite Wikipedia. Al file di origine, alla pagina o all'articolo di Wikipedia viene fatto riferimento insieme alle proprietà suggerite. Le persone vengono suggerite in base ai contributi attivi (ad esempio, le modifiche) ai file e alle pagine. Un riferimento all'importo dei contributi di una determinata persona fornisce un suggerimento sul motivo per cui la persona è stata identificata. I file, le pagine e i siti vengono classificati in base al fatto che siano o meno centrali per l'argomento, indipendentemente dal fatto che possano fornire una panoramica o un'introduzione all'argomento. 

Non tutti gli argomenti identificati saranno utili per l'organizzazione. È possibile che non siano stati identificati nomi alternativi, descrizioni, persone o contenuti appropriati. Pertanto, la possibilità di aggiungere argomenti non identificati, di mantenere gli argomenti suggeriti e di curarne gli argomenti è fondamentale per migliorare la qualità degli argomenti individuabili nell'organizzazione.

Viva Topics, quindi, quando il contesto è appropriato, suggerirà questi argomenti da evidenziare in tutte le pagine moderne del sito di SharePoint nel tenant. È inoltre possibile fare riferimento direttamente all'argomento nella pagina del sito moderno di SharePoint da parte di un autore della pagina. Quando un utente è incuriosito di saperne di  più su un argomento, può selezionare l'argomento evidenziato per visualizzare una scheda di riepilogo dell'argomento che fornisce una breve descrizione. Se vogliono saperne di più, possono selezionare un collegamento **Dettagli** argomento nel riepilogo per aprire la pagina dell'argomento dettagliata.

![Evidenziazioni degli argomenti](../media/knowledge-management/saturn.png) </br>

Inoltre, gli utenti saranno in grado di trovare argomenti anche tramite Microsoft Search.

## <a name="topic-curation-and-feedback"></a>Feedback e cura degli argomenti

Viva Topics è il benvenuto nel contributo umano per migliorare la qualità dei tuoi argomenti. Mentre l'intelligenza artificiale inizialmente identifica e suggerisce argomenti, le modifiche apportate manualmente al contenuto dai collaboratori, gli argomenti aggiunti manualmente, la conferma da parte degli utenti per le proprietà e i contenuti individuati dall'intelligenza artificiale e il feedback sull'utilità degli argomenti sono tutti essenziali.

- Gli argomenti possono essere esaminati **dai knowledge manager** dell'organizzazione. Il responsabile della knowledge base può esaminare gli argomenti di cui dispone delle autorizzazioni necessarie. Nella pagina Gestisci argomenti del Centro argomenti possono scegliere di confermare gli argomenti generati dall'IA ("argomenti suggeriti") come validi, rifiutare gli argomenti per evitare che il contenuto venga visualizzato come argomento, creare argomenti non individuati dall'intelligenza artificiale o identificare gli argomenti che potrebbero trarre vantaggio da alcune modifiche di esperti in materia per essere più utili o accurati. Per ulteriori informazioni, vedere [Gestire gli argomenti nel Centro argomenti.](manage-topics.md)

- Puoi assegnare *autorizzazioni per la creazione* e la modifica di argomenti a qualsiasi utente con licenza in modo che possa apportare modifiche agli argomenti esistenti o creare nuovi argomenti. Ciò consente agli utenti esperti dell'argomento di aggiornare direttamente la pagina dell'argomento per apportare correzioni o aggiungere ulteriori informazioni. Possono anche aggiungere nuovi argomenti che l'intelligenza artificiale non è stata in grado di identificare. Se sono disponibili informazioni sufficienti su questi argomenti aggiunti manualmente e l'intelligenza artificiale è in grado di identificare questo tipo di argomento, ulteriori suggerimenti dell'intelligenza artificiale potrebbero migliorare questi argomenti aggiunti manualmente. Insieme, gli umani e l'intelligenza artificiale possono mantenere accurate le conoscenze nel tempo e non avere questo resto su una singola persona. Per ulteriori informazioni, vedere [Creare un nuovo argomento](https://docs.microsoft.com/microsoft-365/knowledge/create-a-topic) e Modificare un [argomento.](https://docs.microsoft.com/microsoft-365/knowledge/edit-a-topic)

- Anche gli utenti che dispongono solo dell'accesso in lettura all'argomento (visualizzatori di argomenti) verranno invitati a verificare l'utilità di argomenti specifici. Le domande relative al feedback vengono poste nella **scheda di riepilogo** dell'argomento per migliorare il valore dell'argomento e le relative informazioni. Le domande sulla qualità e l'utilità dei suggerimenti di intelligenza artificiale vengono presentate agli utenti una alla volta. Le domande includono:</br>

    1. Se l'identificazione dell'argomento nella pagina di SharePoint è stata utile. C'è la possibilità di rimuovere l'evidenziazione se non è accurata o utile. Se un numero sufficiente di persone indica che un argomento non è identificato correttamente in una determinata pagina, questa evidenziazione verrà rimossa per tutti gli utenti. 

    2. Indica se l'argomento consigliato è importante per l'organizzazione. Se un numero sufficiente di persone indica che l'argomento consigliato è importante, l'argomento viene confermato automaticamente. In alternativa, se l'argomento suggerito non è utile, l'argomento viene automaticamente rifiutato. Il Knowledge Manager può osservare questa attività nella visualizzazione Gestisci argomenti.

    3. Indica se le persone e i suggerimenti per le risorse sono utili.

    4. Nella home page del Centro argomenti è possibile visualizzare gli argomenti dell'organizzazione a cui si dispone di una connessione. È possibile scegliere di rimanere nell'elenco dell'argomento o di rimuoverlo. Questo feedback si riflette su tutti gli utenti che individuano questo argomento. Per [ulteriori informazioni, vedere](https://docs.microsoft.com/microsoft-365/knowledge/topic-center-overview) panoramica del Centro argomenti nella home page del Centro argomenti.

Anche con le modifiche umane, l'intelligenza artificiale cerca continuamente ulteriori informazioni sugli argomenti e cerca la verifica umana. Ad esempio, se l'intelligenza artificiale pensa che tu sia una persona che dovrebbe essere elencata come esperta in un argomento, ti chiederà di confermarlo. 


## <a name="see-also"></a>Vedere anche
