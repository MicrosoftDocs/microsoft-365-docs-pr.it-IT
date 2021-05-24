---
title: Gestire gli argomenti su vasta scala in Microsoft Viva Topics
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: lauriellis
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Informazioni sulle procedure consigliate per gestire i numerosi argomenti dell'organizzazione tramite Viva Topics.
ms.openlocfilehash: 613c4ed85a62efd22ba104c810420a2d0af015c5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624838"
---
# <a name="manage-topics-at-scale-in-microsoft-viva-topics"></a>Gestire gli argomenti su vasta scala in Microsoft Viva Topics

Quando si indicizzano SharePoint siti o l'intera organizzazione per Viva Topics, è possibile che venga generato un numero di argomenti. In questo caso e vengono visualizzati migliaia  di argomenti suggeriti nella pagina Gestisci argomenti, può essere difficile sapere da dove iniziare. In questo articolo viene descritto come Viva Topics consente di ottimizzare gli argomenti e le informazioni visualizzati agli utenti che cercano informazioni, anche in organizzazioni di grandi dimensioni con un numero elevato di argomenti.

Innanzitutto, un promemoria delle [quattro fasi per gli argomenti:](manage-topics.md#topic-stages)

- **Consigliati**: un argomento è stato identificato dall'IA e ha risorse di supporto, connessioni e proprietà sufficienti. Questi argomenti sono contrassegnati come **argomento consigliato** nell'interfaccia utente.

- **Confirmed**: Argomento che è stato individuato dall'IA ed è stato convalidato. La convalida degli argomenti si verifica quando:

   - Un responsabile della conoscenza conferma un argomento. Un responsabile [della knowledge base conferma un argomento](manage-topics.md#confirmed-topics) nella pagina **Gestisci** argomenti.

   - Più utenti confermano un argomento. Deve essere presente una rete di due voti positivi ricevuti dagli utenti che hanno votato usando il meccanismo di feedback nella scheda dell'argomento. Ad esempio, se un utente ha votato positivo e un utente ha votato negativo per un determinato argomento, sarebbero comunque necessari altri due voti positivi per confermare l'argomento.
 
- **Published**: Argomento che è stato curato. Sono state apportate modifiche manuali per migliorarne la qualità o sono state create da un utente.

- **Rimosso**: argomento rifiutato e non più visibile per i visualizzatori. Un argomento può essere rimosso in qualsiasi stato (suggerito, confermato o pubblicato). La rimozione degli argomenti si verifica quando:

   - Un responsabile della conoscenza rimuove un argomento. Un responsabile della knowledge base rimuove un argomento nella **pagina Gestisci** argomenti.

   - Più utenti votano negativamente usando il meccanismo di feedback nella scheda dell'argomento. Per rimuovere un argomento, deve essere presente una rete di due voti negativi ricevuti dagli utenti. Ad esempio, se un utente ha votato negativo e un utente ha votato positivo per un determinato argomento, sarebbero comunque necessari altri due voti negativi per rimuovere l'argomento.

  Quando un argomento pubblicato viene rimosso, la pagina con i dettagli curati dovrà essere eliminata manualmente tramite la raccolta pagine del Centro argomenti.

## <a name="knowledge-manager-role"></a>Ruolo di knowledge manager 

Quando si configura Viva Topics, si aggiungerà un gruppo di utenti a cui sono concesse le autorizzazioni per visualizzare la **pagina Gestisci** argomenti nel Centro argomenti. Verrà visualizzato solo per gli utenti che hanno il ruolo di cura principale per gli argomenti. Avranno accesso ai dati relativi agli argomenti e potranno visualizzare gli elenchi di tutti gli argomenti a cui hanno accesso per la revisione e la cura.

I dipendenti di questo ruolo devono disporre di ampie autorizzazioni per visualizzare un'ampia gamma di argomenti. In caso contrario, se le autorizzazioni sono segmentate, è possibile selezionare un gruppo di utenti che rappresentano aree diverse dell'azienda e possono essere curate per le proprie aree.

Quando si esaminano per la prima volta gli argomenti nel Centro argomenti, gli argomenti suggeriti sono puramente definiti dall'IA. I responsabili della conoscenza potrebbero voler esaminare ognuno di essi prima di eseguire l'implementazione di Viva Topics in una community di utenti ampia. Quando si lavora su larga scala, questo approccio è raramente pratico a causa delle migliaia di argomenti.

L'approccio consigliato consiste nel trovare un equilibrio tra gli argomenti più pertinenti o importanti per il set iniziale di utenti e concentrarsi sulla cura di tali argomenti prima dell'implementazione di Viva Topics. Iniziare a raccogliere feedback dagli utenti e consentire al crowdsourcing di determinare i modelli di utilizzo e di contributo degli utenti per informare le strategie suggerite in questo articolo.

È importante riconoscere che il sistema identificherà e mostrerà a tutti gli utenti sia gli argomenti pubblicati suggeriti dall'IA che gli argomenti pubblicati curati dall'utente. Tuttavia, questo non significa che tutti gli argomenti suggeriti verranno visualizzati a tutti gli utenti finali. Le impostazioni di sicurezza in atto mostreranno solo gli argomenti a cui ogni dipendente può accedere in base alle autorizzazioni impostate per il contenuto stesso.

In quanto knowledge manager con  autorizzazioni per visualizzare la pagina Gestisci argomenti, è possibile che venga visualizzato un numero molto maggiore di argomenti elencati a causa delle proprie autorizzazioni elevate, a seconda del ruolo nell'organizzazione e del livello di accesso. Avrai anche accesso alle visualizzazioni che consentono di visualizzare gli argomenti elencati in un'unica posizione anziché accedervi tramite evidenziazioni o ricerche.

Inoltre, è probabile che la maggior parte degli utenti visualizza una percentuale minore di argomenti e un insieme più ampio di argomenti che verranno visualizzati molto meno frequentemente a causa delle autorizzazioni. Di conseguenza, è bene concentrare innanzitutto le attività di cura sugli argomenti più importanti per l'organizzazione e che sono più probabili essere visti in modo più ampio.

In questo articolo vengono illustrate alcune strategie per la curazione. Queste strategie potrebbero indicare che gli argomenti meno frequenti o meno comuni potrebbero non essere completamente curati dai knowledge manager. Tuttavia, questi argomenti suggeriti rimangono utili e possono fornire informazioni approfondite o un puntatore a una persona, in modo da risparmiare ore a un dipendente per cercare un punto di partenza. Consentire aggiornamenti in crowdsource per gli argomenti è vantaggioso e offre più contenuto e copertura per gli argomenti meno comuni.

In questo articolo vengono fornite alcune linee guida e procedure consigliate per affrontare la gestione e la cura degli argomenti.

## <a name="understanding-suggested-topics"></a>Informazioni sugli argomenti suggeriti

Quando gli argomenti vengono individuati dall'IA, vengono contrassegnati come argomento **consigliato,** sia nella pagina Gestisci argomenti che nelle schede degli argomenti presentate agli utenti.  Tutti gli argomenti che non sono stati contrassegnati come rimossi verranno visualizzati agli utenti, inclusi gli argomenti confermati, pubblicati e suggeriti. Gli argomenti in tutti e tre gli stati sono disponibili per gli utenti finali.

All'interno di una scheda argomento o di una pagina, usiamo vari segnali per mostrare come l'IA ha generato le informazioni. Il sistema usa un'ampia gamma di prove per aggiungere le risorse, principalmente tramite il contenuto stesso.

- Le etichette mostrano che un argomento è stato suggerito e che è stato individuato da Viva Topics.  

   ![Scheda di esempio che mostra un argomento consigliato e include le persone suggerite e le risorse suggerite.](../media/knowledge-management/scale-topics-sample-card-suggested-topic.png)

- Informazioni sugli stati della scheda da cui provengono le definizioni specificandone l'origine.

- Le persone suggerite derivano aggregando persone che hanno scritto o modificato documenti con prove di argomento. Se una persona scrive un documento con un nome di argomento nel titolo e che dispone di molte visualizzazioni, potrebbe essere necessario un solo documento per stabilire la persona come correlata. Tuttavia, in molti casi è meglio avere più prove e le persone elencate hanno lavorato su più documenti.  

   ![Pagina che mostra un argomento consigliato e include persone, file e pagine suggerite.](../media/knowledge-management/scale-topics-sample-page-suggested-topic.png)

- Per i file e le pagine mostrati, il sistema identifica il numero di volte in cui l'argomento è stato menzionato nel documento, ma l'argomento deve essere menzionato anche in un contesto specifico che identifichi il riferimento all'argomento di tipo specifico (ad esempio progetto o team). Questo è ciò che conta come prova per l'IA. Il sistema considera anche l'occorrenza di un nome di argomento nei titoli dei documenti, dei tipi di documenti e di altre funzionalità di analisi (ad esempio le visualizzazioni).

   ![Immagine di un banner che indica l'argomento Consigliato e Microsoft Viva ha individuato questo argomento.](../media/knowledge-management/scale-topics-suggested-you-have-access.png)

   ![Immagine di un banner con l'argomento Consigliato e Modifica questa pagina per descrivere il coinvolgimento dell'utente in questo argomento.](../media/knowledge-management/scale-topics-suggested-describe-your-involvement.png)

   ![Immagine di un banner che indica Argomento consigliato e Modifica questa pagina se è possibile aggiungere persone connesse all'argomento.](../media/knowledge-management/scale-topics-suggested-add-people.png)

Questi attributi dimostrano che il contenuto è stato aggiunto dall'IA e come l'IA ha determinato questa decisione.

### <a name="communication"></a>Comunicazione

Quando comunichi agli utenti argomenti viva, è importante chiarire la differenza tra gli argomenti suggeriti dall'IA e il contenuto e i relativi equivalenti curati.

In quanto lettore, dovresti visualizzare gli argomenti suggeriti con un occhio più critico. Non devono essere percepite come fonti autorevoli di veritá organizzativa. Si tratta piuttosto di uno strumento di ricerca delle modalità per accedere a conoscenze tacita presentate tramite il contenuto a cui si ha accesso. L'IA ha individuato l'argomento e ha prove sufficienti per mostrarlo all'utente, ma il suo valore non è stato confermato da una persona.

### <a name="crowdsourced-controls"></a>Controlli crowdsourced

Gli argomenti suggeriti possono essere migliorati curando la pagina e tramite feedback in crowdsource sull'argomento.

Quando gli utenti interagiscono con un argomento suggerito, potrebbero essere poste una semplice domanda nell'interfaccia utente. Ad esempio: *questo argomento è rilevante per la pagina?* *Questa persona è rilevante per l'argomento?* *Questa definizione è accurata?* Utilizzando il feedback per tali domande, l'accuratezza degli argomenti può aumentare senza la necessità di un individuo denominato per la cura della pagina.

La home page di un centro argomenti è un'altra posizione in cui vengono raccolti i commenti e suggerimenti sugli argomenti suggeriti. Nel Centro argomenti, un utente può visualizzare gli argomenti a cui è stato associato e può confermare l'associazione o farlo rimuovere.

   ![Esempio di centro argomenti che visualizza gli argomenti suggeriti per l'utente per confermare o rimuovere la connessione agli argomenti suggeriti.](../media/knowledge-management/scale-topics-topic-center-confirm-connections.png)

Quando si consente un ampio crowdsourcing di argomenti, è necessario considerare i fattori seguenti:

-   Gli utenti visualizzano **l'opzione** Modifica nelle pagine degli argomenti e possono modificare le pagine nella stessa esperienza di altre pagine SharePoint moderne.

-   Alcune **web part Argomento** consigliato non possono essere rimosse. Non è possibile rimuovere il nome dell'argomento, i nomi alternativi, la definizione, le persone suggerite e le risorse suggerite.

-   Può essere necessario del tempo per spostare un argomento suggerito o confermato che è stato pubblicato **nell'elenco Pubblicato** nella **pagina Gestisci** argomenti.

    -   Il tempo stimato per la visualizzazione di un argomento in ricerca, evidenziazioni, hashtag o annotazioni è di 2 ore.

    -   Nella maggior parte dei casi, il  tempo stimato per la visualizzazione di un argomento nell'elenco Pubblicato nella pagina Argomenti gestiti non è superiore a 24 ore.  Dovrebbero essere visualizzati entro 2 ore, ma poiché esiste una sincronizzazione completa ogni 24 ore, l'attesa non deve essere più lunga di 24 ore.

-   È possibile che un utente lasci un argomento pubblicato in uno stato di estrazione o modifica. Un responsabile della conoscenza può visualizzare tali informazioni nella raccolta pagine del Centro argomenti e può eliminare le modifiche dell'utente per ripubblicare l'argomento o contattare l'utente per richiedere di archiviare l'argomento.

### <a name="topic-visibility-and-content-is-based-on-a-users-permissions"></a>La visibilità degli argomenti e il contenuto si basano sulle autorizzazioni di un utente

Quando si esamina l'elenco degli argomenti suggeriti come knowledge manager, tenere presente che il contenuto di un argomento suggerito sarà basato in modo dinamico sulle autorizzazioni. Il contenuto suggerito e le persone visualizzate potrebbero non essere uguali a quelli presentati a un utente o a un altro responsabile della conoscenza.

In base alle autorizzazioni per visualizzare il contenuto associato a un argomento, ogni utente potrebbe visualizzare un set diverso di risorse suggerite, persone, nomi alternativi e definizione.

## <a name="prioritize-the-topics-for-curation"></a>Assegnare priorità agli argomenti per la curazione

È possibile utilizzare le strategie seguenti per identificare gli argomenti che potrebbero essere importanti e pertanto sono buoni candidati per la cura. 

### <a name="taxonomies"></a>Tassonomie

L'uso di tassonomie esistenti può fornire un elenco di argomenti che potrebbero essere importanti per gli utenti. Ad esempio, questi potrebbero essere:

-   Prodotti e servizi forniti dall'organizzazione

-   Teams nell'organizzazione

-   Progetti di alto profilo

Questo approccio può essere assunto anche a livello di reparto o funzionale, con esperti in materia che comprendono tale area dell'organizzazione. L'obiettivo non è fare in modo che riveda una selezione o tutti gli argomenti. Piuttosto, mettono a disposizione le proprie competenze di dominio per guidare la cura selettiva.

### <a name="search"></a>Ricerca

I termini di ricerca comuni vengono spesso individuati come argomenti. Utilizzando i [report di query principali in Microsoft Search,](/sharepoint/view-search-usage-reports)è possibile identificare i termini di ricerca più frequenti nell'organizzazione. Se sono stati individuati argomenti per questi termini, sono buoni candidati per la curazione. Questi argomenti possono essere presentati come schede di risposta in Microsoft Search.

Se attualmente si usano segnalibri [di Microsoft Search,](/microsoftsearch/manage-bookmarks)valutare quale di questi può essere sostituito con un argomento. Una scheda di risposta segnalibro contiene un titolo, una descrizione e un URL. In alcuni casi, una scheda argomento potrebbe essere più utile per un utente e una scheda argomento mostra anche risorse e persone.

Nell'esperienza di ricerca dell'utente, quando un utente cerca un termine come *viaggi,* i risultati della ricerca vengono visualizzati nell'ordine di priorità seguente in Microsoft Search:

1.  Argomenti pubblicati o confermati

2.  Segnalibri

3.  Argomenti suggeriti

### <a name="impressions-and-quality-score"></a>Impression e punteggio di qualità

Il [conteggio delle impression](manage-topics.md#impressions) e il punteggio [di](manage-topics.md#quality-score) qualità sono metriche importanti per comprendere il comportamento di un argomento. Il valore di queste metriche sarà limitato quando solo i knowledge manager o i team IT hanno accesso agli argomenti. L'esposizione di argomenti a un gruppo pilota di utenti genererà dati più rappresentativi per queste misure.

È probabile che gli argomenti con un numero elevato di impression interagiscano con maggiore frequenza. Il punteggio di qualità per questi argomenti darà un'idea di quanto siano ricchi questi argomenti. Gli argomenti con un numero di impression elevato e un punteggio di bassa qualità sono ottimi obiettivi per la gestione.

### <a name="key-terms-from-the-information-architecture-of-larger-organizational-sites"></a>Termini chiave dell'architettura delle informazioni di siti organizzativi di grandi dimensioni

I siti portale più grandi all'interno dell'organizzazione potrebbero aver investito tempo nell'organizzazione dell'architettura delle informazioni e della struttura di spostamento del sito attorno ad aree chiave per le unità aziendali, le linee di prodotti, i progetti principali e così via. La revisione di questi termini e l'identificazione e la cura degli argomenti relativi a tali termini possono aiutare gli utenti che cercano informazioni su queste aree.

### <a name="leverage-internal-knowledge-bases-or-wiki-sites"></a>Sfruttare le knowledge base interne o i siti wiki

Se l'organizzazione ha investito in knowledge base o siti wiki, questi possono fornire un elenco di argomenti da utilizzare per le attività di cura iniziale. Se sono particolarmente grandi, selezionare gli argomenti più visualizzati o modificati come punto di partenza.

## <a name="see-also"></a>Vedere anche

[Gestire gli argomenti nel centro argomenti](manage-topics.md)

[Panoramica sul centro argomenti](topic-center-overview.md)
