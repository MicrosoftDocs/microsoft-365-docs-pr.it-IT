---
title: Introduzione all'adozione di Microsoft Viva Topics
description: Scopri come guidare l'adozione di Microsoft Viva Topics nella tua organizzazione.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e8d7ca4786893fb5eb39090d9a271ace1c62d321
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596969"
---
# <a name="get-started-driving-adoption-of-microsoft-viva-topics"></a>Introduzione all'adozione di Microsoft Viva Topics

Prima di iniziare l'adozione, è necessario comprendere i concetti relativi alla gestione delle conoscenze e agli argomenti viva. Il diagramma seguente mostra cosa accade durante l'individuazione e la cura degli argomenti:

![Architettura Viva Topics](../media/knowledge-management/topic-management-architecture.png)

- **Individuazione**: gli utenti possono individuare le conoscenze nelle app che usano ogni giorno tramite schede di argomento, oppure individuare gli argomenti in Microsoft Search.
- **Cura**: gli esperti in materia (SME) perfezionano gli argomenti tramite pagine di argomenti e l'AI apprende dai loro input. Il Centro argomenti contiene pagine di argomenti che gli utenti possono esplorare e gestire dagli esperti.
- **Identificazione**: con Microsoft Graph e Artificial Intelligence (AI), conoscenze e persone (argomenti, competenze e così via) vengono identificate e organizzate automaticamente in argomenti correlati. I contenuti di SharePoint sono indicizzati con contenuti di sicurezza.
- **Estensione:** con Microsoft Graph connettori di contenuto (presto disponibile), è possibile inserire conoscenze da servizi esterni e archivi dati.

Per ulteriori informazioni, è possibile esaminare la [panoramica](topic-experiences-overview.md) per un'introduzione.

Tenere presente che:

- L'individuazione degli argomenti migliora quando sono disponibili più contenuti.
- La sicurezza, la privacy e la posizione dei dati vengono mantenute anche se le informazioni vengono presentate in una nuova esperienza.
- Per visualizzare Viva Topics, gli utenti hanno bisogno di una licenza.
- L'individuazione è inizialmente limitata a contenuti in lingua inglese.

Per prepararsi, rispondere a queste domande:

- Quali contenuti devono essere utilizzati per l'individuazione degli argomenti?
- Chi gestirà gli argomenti?
- Chi può vedere le schede degli argomenti e le evidenziazioni?
- Quali argomenti sono previsti?

Esaminare questo elenco di prerequisiti per ottenere il massimo da Viva Topics:

|Prodotto o funzionalità |Descrizione |
|:-------|:--------|
|SharePoint Online con pagine di SharePoint moderne |Il data mining degli argomenti include solo contenuto SharePoint siti e le schede argomento possono essere evase solo nelle pagine moderne.|
|Microsoft Graph |È possibile controllare se gli argomenti sono inclusi o esclusi dalla ricerca o da Delve tramite le impostazioni di Microsoft Graph*. |

## <a name="plan-for-adoption"></a>Pianificare l'adozione

Per pianificare l'adozione di Viva Topics, è necessario:

![Passaggi per pianificare l'adozione](../media/knowledge-management/km-adoption-plan-adoption.png)

1. Pianificare l'approccio e gli scenari di destinazione:
    - È necessario definire e definire le priorità degli [scenari.](#target-scenarios)
    - Pensa ai [cointeressati](#identify-stakeholders) e ai membri del team di progetto necessari.  
    - Scopri l'impatto aziendale che vuoi ottenere e come misurerai [il successo.](#create-a-success-plan)

2. Gestire l'organizzazione:
    - Identificare i gruppi aziendali e i team aziendali che devono essere coinvolti e ottenere l'allineamento tra questi e gli scenari che si stanno pianificando.
    - Iniziare a pensare a come coinvolgere alcuni primi utilizzatori per ottenere un feedback cruciale e in anticipo al fine di iterare per raggiungere la soluzione migliore.
    - Iniziare a creare la community e pensare a come Viva Topics può essere usato all'interno dell'organizzazione da questi gruppi diversi.

3. Formare l'organizzazione: la maggior parte delle persone comprenderà in modo intuitivo il concetto di argomenti e il modo in cui le schede degli argomenti compilano le informazioni pertinenti e comprendono e visualizzano il valore. Tuttavia, potresti voler creare una formazione personalizzata per la tua cultura e la tua organizzazione, per mostrare come vuoi usare Viva Topics. Alcune risorse di formazione:
    - [Project centro risorse cortex](https://aka.ms/projectcortex). Include panoramiche e informazioni sulle funzionalità, video e presentazioni dell'orario di ufficio registrati e informazioni sui partner e sulle loro offerte.
    - Presto, video di formazione e assistenza per gli utenti finali.

4. [Creare una rete di campioni:](#build-a-champion-network)
    - Potrebbero essere già presenti community dedicate all'esercitazione o reti di promotori. Si tratta di soluzione efficaci per socializzare, promuovere l'adozione e spingere i colleghi ad aiutarsi a vicenda. E possono condividere storie di successo che possono essere preziose. Possono offrire consigli e generare entusiasmo.

### <a name="target-scenarios"></a>Scenari di destinazione

Determinare come si desidera utilizzare Viva Topics nell'organizzazione in modo da utilizzarli correttamente. Ecco alcuni scenari in cui la gestione delle conoscenze e gli argomenti possono aiutare l'organizzazione:

- Formazione sull'onboard & ing dei ruoli: comprendere la terminologia, i progetti chiave e la cultura di una nuova organizzazione sono passaggi importanti per l'onboarding. Facilitare la scoperta degli argomenti consente ai nuovi dipendenti di trovare rapidamente nuove attività, ruoli o progetti.
- Ricerca di competenze e condivisione delle informazioni: quando gli argomenti vengono gestiti e condivisi, gli utenti delle organizzazioni possono trovare più facilmente informazioni ed esperti per aiutarli nel loro lavoro quotidiano.
- Processi decisionali più ampi e time to market ottimizzato: un facile accesso alle informazioni e alle competenze consente di prendere decisioni più facilmente e di evitare di svolgere progetti durante il periodo non lavorativo.

#### <a name="example-scenario-for-role-onboarding"></a>Scenario di esempio per l'onboarding dei ruoli

Un responsabile delle risorse umane deve fornire informazioni ai nuovi dipendenti che li aiuteranno a eseguire rapidamente l'onboardboard all'azienda e ai loro team. Vogliono puntare alle risorse, ai documenti e ai membri del team corretti di cui dovranno eseguire l'onboard in modo rapido ed efficiente. Cercano una soluzione che consenta al nuovo dipendente di trovare rapidamente le informazioni necessarie senza dover eseguire ricerche in più archivi o lasciare le applicazioni già in uso.

Ad esempio:

- Un dipendente (Giordania) assume un nuovo ruolo o è stato appena assunto e sta iniziando con un ruolo. La Giordania vuole essere coinvolta e produttiva il prima possibile. Ma anche Jordan ha bisogno di aiuto per trovare un punto di partenza.
- Un collega (Kim) che era nel ruolo prima di Jordan ha creato pagine di argomento che possono aiutare i nuovi dipendenti e chiunque altro cerchi queste informazioni.
- Kim era una PMI e aveva le autorizzazioni per esaminare le pagine degli argomenti non confermati. Le pagine di argomenti non confermate sono ottimi punti di partenza, in quanto contengono argomenti scoperti e creati dall'IA. Kim è riuscita a modificarle per aggiungere risorse per esperti, definizioni e altre risorse.
- Mentre Jordan legge un nuovo post su SharePoint, vede un argomento in evidenza e passa il mouse su di esso per ottenere rapidamente una definizione del termine e chi contattare con altre domande. In precedenza, Jordan avrebbe dovuto cercare questa informazione e contattare i colleghi per capire a chi chiedere.
- L'esposizione di queste informazioni tramite argomenti può essere efficace, perché anche se queste informazioni potrebbero essere già disponibili, potrebbero essere state isolate e risultare difficili da trovare. L'uso delle applicazioni in Giordania e l'aiuto di questi esperti può anche contribuire a creare un senso di coinvolgimento e di community. Può inoltre aiutarli a sentirsi più autonomi nella gestione del nuovo ruolo.

Quando si automatizza questo scenario, è possibile verificare che:

- I nuovi dipendenti possano connettersi rapidamente con le persone giuste nei progetti giusti.
- I nuovi dipendenti hanno accesso immediato alle informazioni più recenti sul progetto nel loro flusso di lavoro.
- I tempi di ricerca si riducono notevolmente.
- I tempi di onboarding si riducono notevolmente.

#### <a name="example-scenario-for-customer-call-center"></a>Scenario di esempio per il servizio clienti

È possibile consentire al servizio clienti di trovare rapidamente file ed esperti per rispondere a domande fiscali insolite e documentare rapidamente la risposta agli altri per accedervi facilmente con Viva Topics.

Ad esempio, un rappresentante del supporto deve trovare rapidamente articoli, documenti e criteri della Knowledge Base in modo che possano supportare i clienti. Vogliono trovare le informazioni giuste al momento giusto, senza dover setacciare manualmente diverse basi di dati, archivi o applicazioni o inviare una chiamata. E stanno cercando una soluzione che consenta loro di rimanere all'interno del prompt delle chiamate principale e di accedere a criteri, normative e linee guida nel flusso delle conversazioni, in modo che possano rispondere rapidamente alle domande e aggiornare il caso.

Quando si automatizza questo scenario con Viva Topics, è possibile verificare che:

- I tempi di chiamata del supporto sono ridotti.
- Il passaggio a supporti di secondo e terzo livello vengono ridotti.
- Il numero di call-back di un dato caso viene ridotto.
- La soddisfazione del cliente aumenta.

#### <a name="prioritize-your-scenarios"></a>Definire la priorità degli scenari

Dopo aver identificato gli scenari, è possibile definire le priorità degli scenari:

Un modo per classificarli in ordine di priorità è tracciare gli scenari in una griglia che mostri impatto e facilità di implementazione. Cerca gli scenari che hanno un impatto elevato e sono facili da implementare e rendere tali scenari la priorità principale. Gli scenari a basso impatto e difficili da implementare avranno la priorità più bassa. In uno scenario ad alto impatto e facile da implementare, gli utenti possono entusiasmarsi e vedere le possibilità offerte dall'uso degli argomenti.

![Gli scenari ad alto impatto e facile da implementare hanno priorità alta](../media/knowledge-management/topics-prioritize-scenarios.png)

Selezionare un paio di scenari principali su cui concentrarsi inizialmente, collaborare con i primi utenti per ottenere un feedback e quindi procedere per gradi. In questo modo è possibile eseguire un'iterazione, apportare miglioramenti e ottenere feedback in modo da aumentare l'adozione nel tempo.

### <a name="identify-stakeholders"></a>Identificare le parti interessate

Identificare le parti interessate per il progetto. I ruoli principali sono lo sponsor esecutivo, il proprietario del successo e i campioni.

|Ruolo |Responsabilità |Reparto |
|:-------|:-------|:--------|
| Sponsor esecutivi   | Comunicare la visione e i valori di alto livello all'azienda   |  Leadership esecutiva   |
| Project lead | Supervisionare l'intero processo di esecuzione e implementazione del lancio | Gestione dei progetti |
| Amministratori delle conoscenze| Installare e configurare Viva Topics | Reparto IT |
| Responsabili delle conoscenze | Gestire gli argomenti e supervisionare la tassonomia | Tutti i reparti |
| Responsabili della tassonomia | Supervisionare la tassonomia | Tutti i reparti |
| Esperti in materia e collaboratori di argomenti | Generare o rivedere argomenti e descrizioni | Tutti i reparti |
| Promotori | Aiutare a migliorare e a gestire le obiezioni | Tutti i reparti (personale) |
| Amministratore tenant | Configurare le impostazioni di livello tenant | Reparto IT |
| Amministratore di Power Platform| Configurare l'ambiente dei servizi dati comuni | Reparto IT |
| Amministratore o responsabile della ricerca | Configurare le impostazioni di ricerca | Reparto IT |

In un'organizzazione di grandi dimensioni, potresti avere anche più persone in questi ruoli e dovrai coordinarti tra di loro. In un'azienda di piccole dimensioni, una sola persona potrebbe svolgere molti di questi ruoli. Ruoli diversi potrebbero essere maggiormente coinvolti in fasi diverse del progetto. Ad esempio, gli amministratori tenant sono più coinvolti nella configurazione delle funzionalità, mentre gli esperti in materia e i campioni non vengono coinvolti fino a quando non si inizia a definire gli argomenti.
 
Anche se è consigliabile che ognuno di questi ruoli venga evaso durante l'implementazione, è possibile che non sia necessario che tutti questi ruoli inizino a usare la soluzione identificata.

### <a name="create-a-success-plan"></a>Creare un piano di successo

Utilizzare questi indicatori per misurare il successo di Viva Topics nell'organizzazione. Guardare:

1. Utilizzo argomento:
      - Impression degli argomenti
      - Quantità di argomenti, sia confermati che non confermati nell'elenco degli argomenti trattati.
      - Numero di pagine degli argomenti pubblicate.
1. Feedback per l'utente finale dalle schede degli argomenti.
1. Eseguire sondaggi sulla soddisfazione dei dipendenti. Viva Topics dovrebbe migliorare la capacità dei dipendenti di trovare informazioni, in modo da trovare modi per raccogliere il loro input e feedback su tale esperienza.
1. Impatto positivo sull'analisi della ricerca. Poiché gli argomenti vengono visualizzati nell'esperienza di ricerca, nel corso del tempo è possibile che vengano visualizzate percentuali inferiori di ricerche abbandonate perché gli utenti sono più facilmente in grado di trovare gli argomenti nella ricerca. 

### <a name="build-a-champion-network"></a>Creare una rete di campioni

Creare una rete di campioni nell'organizzazione. I campioni sono importanti perché possono:

- Creare un cerchio di influenza all'interno dei team
- Gestione degli argomenti delle & gestione

È possibile reclutare i campioni da ruoli diversi: knowledge manager ed esperti in materia.

Molte reti di campioni usano Yammer come piattaforma. In Yammer, gli utenti possono pubblicare domande e ottenere risposte e condividere storie di successo. È difficile ottenere la parola da solo, in modo da poter fare affidamento sulla rete di persone in tutta l'azienda per offrire consigli ai propri colleghi e mostrare come il team usa Viva Topics in modo che altri team possano pensare ai propri scenari.

Alcune organizzazioni usano hackathon (formali o informali, virtuali o di persona) per raccogliere gruppi di persone per lavorare a un progetto specifico. Ad esempio, potresti raccogliere i tuoi esperti in materia e farli collaborare per curare un set di pagine di argomenti.

Pensa a come riconoscere i tuoi campioni. Premia le attività, assegna loro un riconoscimento e genera una sensazione e un coinvolgimento visibili della community in modo che sentano di contribuire a qualcosa e stanno anche ottenendo qualcosa dai loro investimenti.

Ora che sei pronto per l'implementazione, vuoi assicurarti di incoraggiare l'impegno continuo.

- Mantenere gruppi Yammer attivi per i tuoi campioni.
- Condividere storie di successo.
- Ospita periodicamente eventi di coinvolgimento per condividere storie o introdurre nuove funzionalità.
- Impostare le sfide per le persone ed eseguire competizioni.

## <a name="next-steps"></a>Passaggi successivi

Quando tutto è pronto per implementare Viva Topics, è necessario coinvolgere le persone.

- Iniziare a presentare il set di funzionalità e far riflettere sugli scenari possibili.
- Riunire gli stakeholder e creare scenari.
- Guidare la community e riflettere su come coinvolgerla.
- Completare quindi i passaggi di preparazione. Alcuni possono essere di preparazione tecnica e di preparazione aziendale.
- Infine, socializzare e promuovere.
