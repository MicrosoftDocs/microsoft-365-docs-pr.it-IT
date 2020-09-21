---
title: Informazioni sui classificatori addestrabili (anteprima)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Un classificatore addestrabile di Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto, fornendo campioni positivi e negativi da esaminare. Una volta che il classificatore è stato addestrato, conferma che i risultati sono accurati. È quindi possibile utilizzarla per eseguire una ricerca nel contenuto dell'organizzazione e classificarla in modo da applicare etichette di conservazione o di sensibilità o includerla nella prevenzione della perdita di dati (DLP) o nei criteri di conservazione.
ms.openlocfilehash: 9a628eec748681e0a22911bf7cf3774895b10ead
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132397"
---
# <a name="learn-about-classifiers-preview"></a>Informazioni sui classificatori (anteprima)

Classificare ed etichettare il contenuto in modo che possa essere protetto e gestito correttamente è il punto di partenza per la disciplina di protezione delle informazioni. Microsoft 365 ha tre modi per classificare il contenuto.

## <a name="manually"></a>Manualmente

Questo metodo richiede il giudizio umano e l'azione. Un amministratore può utilizzare le etichette preesistenti e i tipi di informazioni riservate oppure crearne di propri e quindi pubblicarli. Gli utenti e gli amministratori li applicano al contenuto quando lo incontrano. È quindi possibile proteggere il contenuto e gestirne la disposizione.

## <a name="automated-pattern-matching"></a>Corrispondenza del modello automatizzata

Questa categoria di meccanismi di classificazione include la ricerca di contenuto per:

- Parole chiave o valori di metadati (linguaggio di query con parole chiave).
- Utilizzo di modelli di informazioni riservate in precedenza identificati come la sicurezza sociale, la carta di credito o il conto corrente bancario [(definizioni di entità tipo di informazioni riservate)](sensitive-information-type-entity-definitions.md).
- Riconoscere un elemento perché è una variante su un modello [(stampa su un dito del documento)](document-fingerprinting.md).
- Utilizzo della presenza di stringhe esatte [(corrispondenza esatta dei dati)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Le etichette di conservazione e di sensibilità possono quindi essere applicate automaticamente per rendere il contenuto disponibile per l'utilizzo in [prevenzione della perdita di dati (DLP)](data-loss-prevention-policies.md) e [per l'applicazione automatica delle politiche per le etichette di conservazione](apply-retention-labels-automatically.md).

## <a name="classifiers"></a>Classificatori

Questo metodo di classificazione è particolarmente adatto ai contenuti che non sono facilmente identificabili tramite i metodi di corrispondenza dei modelli manuale o automatico. Questo metodo di classificazione è più relativo all'addestramento di un classificatore per identificare un elemento in base a ciò che l'elemento è, non per elementi che si trovano nell'elemento (pattern matching). Un classificatore apprende come identificare un tipo di contenuto esaminando centinaia di esempi del contenuto che si desidera classificare. Si inizia con l'alimentazione di esempi che sono definitivamente nella categoria. Dopo averli elaborati, è possibile testarli conferendogli una combinazione di esempi di corrispondenza e non corrispondenti. Il classificatore effettua quindi stime per determinare se un determinato elemento rientra nella categoria che si sta creando. È quindi necessario confermare i risultati, ordinare i veri positivi, i negativi veri, i falsi positivi e i falsi negativi per aumentare l'accuratezza delle stime. 

Quando si pubblica il classificatore, l'ordinamento viene ordinato tramite gli elementi in posizioni come SharePoint Online, Exchange e OneDrive e classifica il contenuto. Dopo aver pubblicato il classificatore, è possibile continuare a addestrarlo utilizzando un processo di commenti e suggerimenti analogo al processo di formazione iniziale.

### <a name="where-you-can-use-trainable-classifiers"></a>Dove è possibile utilizzare i classificatori addestrabili
Sia i classificatori incorporati che i classificatori addestrati sono disponibili come condizione per [Office autolabeling con etichette di riservatezza](apply-sensitivity-label-automatically.md), [applicare automaticamente i criteri delle etichette di conservazione in base a una condizione](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) e in [conformità alla comunicazione](communication-compliance.md). 

Le etichette di riservatezza possono utilizzare i classificatori come condizioni, vedere [applicazione automatica di un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> I classificatori funzionano solo con elementi che non sono crittografati e sono in lingua inglese.

## <a name="types-of-classifiers"></a>Tipi di classificatori

- **classificatori** preformati-Microsoft ha creato e preparato un certo numero di classificatori che è possibile iniziare a usare senza addestrarli. Questi classificatori verranno visualizzati con lo stato di `Ready to use` .
- **classificatori personalizzati** : se si dispone di esigenze di classificazione che si estendono oltre a quelle prequalificate, è possibile creare e formare i propri classificatori.

### <a name="pre-trained-classifiers"></a>Classificatori prequalificati

Microsoft 365 viene fornito con cinque classificatori prequalificati:

> [!CAUTION]
> Il classificatore preconfigurato per la **lingua offensiva** è obsoleto perché produce un numero elevato di falsi positivi. Non utilizzarlo e, se lo si sta attualmente utilizzando, è consigliabile spostarne i processi aziendali. Si consiglia di utilizzare invece la **minaccia**, la **profanità**e le **molestie** prequalificate.

- **Resumes**: rileva gli elementi che sono account testuali di qualifiche personali, didattiche, professionali del richiedente, esperienze lavorative e altre informazioni di identificazione personale
- **Codice sorgente**: consente di rilevare gli elementi che contengono una serie di istruzioni e istruzioni scritte nella Top 25 linguaggi di programmazione utilizzati su GitHub
    - ActionScript
    - C
    - C #
    - C++
    - Clojure
    - CoffeeScript
    - CSS
    - Andare
    - Haskell
    - HTML
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Trascizione fonetica
    - Scala
    - Shell
    - Swift
    - Tex
    - Script VIM

> [!NOTE]
> Il codice sorgente è addestrato per rilevare quando la maggior parte del testo è codice sorgente. Non rileva il testo del codice sorgente intervallato da testo normale.

- **Molestie**: rileva una categoria specifica di elementi di testo di lingua offensiva relativi alla condotta offensiva che mira a una o più persone in base alle caratteristiche seguenti: razza, etnia, religione, origine nazionale, genere, orientamento sessuale, età, disabilità
- **Parolacce**: rileva una categoria specifica di elementi di testo di lingua offensiva che contengono espressioni che imbarazzano la maggior parte delle persone
- **Threat**: rileva una categoria specifica di elementi di testo offensivi relativi alle minacce per commettere violenze o arrecare danni fisici a una persona o a una proprietà

Questi vengono visualizzati nella visualizzazione classificazione dei classificati di **Microsoft 365 Compliance Center**  >  **Data Classification (Preview)**  >  **Trainable classifiers** con lo stato di `Ready to use` .

![classificatori-preformati-classificatori](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Si noti che la lingua offensiva, la molestia, la profanità e i classificatori di minacce funzionano solo con il testo ricercabile non sono esaustivi o completi.  Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare questi classificatori a sua discrezione. Anche se i classificatori possono assistere la propria organizzazione nel monitoraggio di un'offensiva e di altre lingue utilizzate, i classificatori non affrontano le conseguenze di tale lingua e non sono destinati a fornire il solo mezzo di monitoraggio o di risposta dell'organizzazione all'uso di tale lingua. La propria organizzazione e non Microsoft o le sue affiliate resta responsabile di tutte le decisioni relative al monitoraggio, all'applicazione, al blocco, alla rimozione e alla conservazione di qualsiasi contenuto identificato da un classificatore preformato.

### <a name="custom-classifiers"></a>Classificatori personalizzati

Quando i classificatori prequalificati non soddisfano le proprie esigenze, è possibile creare e formare i propri classificatori. È molto più necessario collaborare con la creazione dei propri utenti, ma sarà molto meglio adattare le proprie esigenze alle organizzazioni.

> [!IMPORTANT]
> Per impostazione predefinita, solo l'utente che crea un classificatore personalizzato può formare ed esaminare le stime eseguite dal classificatore. Se si desidera che gli altri utenti siano in grado di formare e rivedere le stime del classificatore, vedere [Give others Train and Review Rights](classifier-get-started-with.md#give-others-train-and-review-rights).

#### <a name="process-flow-for-creating-custom-classifiers"></a>Flusso di processo per la creazione di classificatori personalizzati

La creazione e la pubblicazione di un classificatore per l'utilizzo in soluzioni di conformità, ad esempio i criteri di conservazione e la supervisione della comunicazione, seguono questo flusso. Per ulteriori informazioni sulla creazione di un classificatore addestrabile personalizzato, vedere [creazione di un classificatore personalizzato](classifier-get-started-with.md).

![classificatore personalizzato flusso di processo](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Riqualificazione di classificazione

È possibile migliorare l'accuratezza di tutti i classificatori personalizzati e alcuni classificatori prequalificati fornendo loro commenti e suggerimenti sull'accuratezza della classificazione che eseguono. Si tratta della riqualificazione e del flusso di lavoro.

![flusso di lavoro di riqualificazione del classificatore](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Vedere anche

- [Etichette di conservazione](retention.md)
- [Data loss prevention (DLP)](data-loss-prevention-policies.md)
- [Etichette di riservatezza](sensitivity-labels.md)
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
- [Stampa di impronte digitali del documento](document-fingerprinting.md)
- [Corrispondenza esatta dei dati](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
