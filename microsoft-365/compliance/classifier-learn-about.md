---
title: Informazioni sui classificatori sottoponibili a training
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Un Microsoft 365 classificatore di cui è possibile eseguire il training è uno strumento che è possibile addestrare a riconoscere vari tipi di contenuto fornendo campioni positivi e negativi da esaminare. Una volta addestrato il classificatore, si conferma che i risultati sono accurati. Viene quindi utilizzato per cercare il contenuto dell'organizzazione e classificarlo per applicare etichette di conservazione o riservatezza o includerlo nei criteri di prevenzione della perdita dei dati (DLP) o di conservazione.
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114052"
---
# <a name="learn-about-trainable-classifiers"></a>Informazioni sui classificatori sottoponibili a training

La classificazione e l'etichettatura dei contenuti in modo che possano essere protetti e gestiti correttamente sono il punto di partenza per la disciplina di protezione delle informazioni. Microsoft 365 sono disponibili tre modi per classificare il contenuto.

## <a name="manually"></a>Manualmente

Questo metodo richiede un'azione e un giudizio umano. Un amministratore può usare le etichette preesiste e i tipi di informazioni riservate oppure crearne di proprie e quindi pubblicarle. Gli utenti e gli amministratori li applicano al contenuto quando lo rilevano. È quindi possibile proteggere il contenuto e gestirne l'eliminazione.

## <a name="automated-pattern-matching"></a>Corrispondenza automatica dei modelli

Questa categoria di meccanismi di classificazione include la ricerca del contenuto in base a:

- Parole chiave o valori di metadati (linguaggio di query con parole chiave).
- Utilizzo di modelli identificati in precedenza di informazioni riservate come i numeri di previdenza sociale, carta di credito o conto corrente [bancario (definizioni di](sensitive-information-type-entity-definitions.md)entità tipo di informazioni riservate) .
- Riconoscimento di un elemento perché si tratta di una variante di un modello [(stampa delle dita del documento)](document-fingerprinting.md).
- Utilizzo della presenza di stringhe esatte [(corrispondenza esatta dei dati)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Le etichette di riservatezza e di conservazione possono quindi essere applicate automaticamente per rendere disponibile il contenuto per l'utilizzo in [Informazioni](dlp-learn-about-dlp.md)sulla prevenzione della perdita dei dati ) e applicare automaticamente criteri per [le etichette di conservazione.](apply-retention-labels-automatically.md)

## <a name="classifiers"></a>Classificatori

Questo metodo di classificazione è particolarmente adatto al contenuto che non è facilmente identificabile con i metodi di corrispondenza dei modelli manuali o automatizzati. Questo metodo di classificazione riguarda principalmente il training di un classificatore per l’identificazione di un elemento in base alla sua entità e non ai suoi costituenti (criteri di ricerca). Un classificatore impara a identificare un tipo di contenuto esaminando centinaia di esempi del contenuto che ti interessa classificare. Per iniziare, vengono forniti esempi sicuramente inclusi nella categoria. Dopo averli processati, puoi testarlo fornendogli una combinazione di esempi di corrispondenza e non corrispondenti. Il classificatore esegue quindi previsioni sul fatto che un determinato elemento appartieni alla categoria che stai creando. È quindi possibile confermarne i risultati, ordinando i veri positivi, i veri negativi, i falsi positivi e i falsi negativi per aumentare l'accuratezza delle previsioni. 

Quando si pubblica il classificatore, questo ordina gli elementi in posizioni come SharePoint Online, Exchange e OneDrive e classifica il contenuto. Dopo aver pubblicato il classificatore, puoi continuare a addestrarlo usando un processo di feedback simile al processo di formazione iniziale.

### <a name="where-you-can-use-trainable-classifiers"></a>Dove è possibile usare classificatori addestrabili
Sia i classificatori incorporati che i classificatori addestrabili sono disponibili come condizione per l'etichettatura automatica di Office con etichette di [riservatezza,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) applicare automaticamente i criteri delle etichette di conservazione in base a una condizione e [in](apply-sensitivity-label-automatically.md)conformità alle [comunicazioni.](communication-compliance.md) 

Le etichette di riservatezza possono usare classificatori come condizioni, vedere Applicare automaticamente un'etichetta di [riservatezza al contenuto.](apply-sensitivity-label-automatically.md)

> [!IMPORTANT]
> I classificatori funzionano solo con elementi non crittografati e in inglese.

## <a name="types-of-classifiers"></a>Tipi di classificatori

- **Classificatori pre-addestrati:** Microsoft ha creato e preparato in precedenza un numero di classificatori che è possibile iniziare a usare senza addestrarli. Questi classificatori verranno visualizzati con lo stato `Ready to use` .
- **classificatori personalizzati:** se le esigenze di classificazione si estendono oltre la copertura dei classificatori pre-addestrati, è possibile creare e formare i propri classificatori.

### <a name="pre-trained-classifiers"></a>Classificatori pre-addestrati

Microsoft 365 viene fornito con cinque classificatori pre-addestrati:

> [!CAUTION]
> Stiamo deprecando  il classificatore pre-addestrato del linguaggio offensivo perché produce un numero elevato di falsi positivi. Non usarlo e, se lo si sta attualmente utilizzando, è consigliabile spostare i processi aziendali al di fuori di esso. È **consigliabile** usare invece i  classificatori pre-addestrati per **minacce,** volgarità e molestie.

- **Curriculum:** rileva gli elementi che sono account testuali delle qualifiche personali, didattiche, professionali, dell'esperienza professionale e di altre informazioni di identificazione personale di un richiedente
- **Source Code**: rileva gli elementi che contengono un set di istruzioni e istruzioni scritte nei 25 linguaggi di programmazione computer utilizzati più di GitHub
    - ActionScript
    - C
    - C #
    - C++
    - Clojure
    - CoffeeScript
    - Go
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Ruby
    - Scala
    - Shell
    - Swift
    - Tex
    - Vim Script

> [!NOTE]
> Il codice sorgente viene addestrato per rilevare quando la maggior parte del testo è codice sorgente. Non rileva il testo del codice sorgente intersperso con testo normale.

- **Molestie:** rileva una categoria specifica di elementi di testo in linguaggio offensivo correlati a comportamenti offensivi mirati a uno o più individui in base ai seguenti tratti: etnia, religione, origine nazionale, sesso, orientamento sessuale, età, disabilità
- **Volgarità**: rileva una categoria specifica di elementi di testo in linguaggio offensivo che contengono espressioni che mette in imbarazzo la maggior parte delle persone
- **Minaccia:** rileva una categoria specifica di elementi di testo in linguaggio offensivo correlati alle minacce per commettere atti di violenza o danneggiare fisicamente o danneggiare una persona o una proprietà

Questi elementi vengono visualizzati nella Microsoft 365 centro **conformità** Visualizzazione Classificatori trainabili con  >    >   stato `Ready to use` .

![classificatori-classificatori pre-addestrati](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Tieni presente che il linguaggio offensivo, le molestie, le volgarità e i classificatori delle minacce funzionano solo con il testo ricercabile non sono esaustivi o completi.  Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare questi classificatori a sua discrezione. Anche se i classificatori possono aiutare l'organizzazione a monitorare l'offensiva e altro linguaggio utilizzato, i classificatori non affrontano le conseguenze di tale linguaggio e non sono destinati a fornire l'unico mezzo dell'organizzazione per monitorare o rispondere all'uso di tale linguaggio. L'organizzazione, e non Microsoft o le relative filiali, rimane responsabile di tutte le decisioni relative al monitoraggio, all'applicazione, al blocco, alla rimozione e alla conservazione di qualsiasi contenuto identificato da un classificatore pre-preparato.

### <a name="custom-classifiers"></a>Classificatori personalizzati

Quando i classificatori pre-addestrati non soddisfano le proprie esigenze, è possibile creare e formare i propri classificatori. C'è molto più lavoro da fare per creare il proprio, ma saranno molto più personalizzati in base alle esigenze delle organizzazioni. 

Ad esempio, è possibile creare classificatori addestrabili per:
 
- Documenti legali, ad esempio privilegio del cliente avvocato, set di chiusura, dichiarazione di lavoro
- Documenti aziendali strategici, come comunicati stampa, fusioni e acquisizioni, accordi, piani aziendali o di marketing, proprietà intellettuale, brevetti, documenti di progettazione
- Informazioni sui prezzi, ad esempio fatture, offerte di prezzo, ordini di lavoro, documenti di offerta 
- Informazioni finanziarie, ad esempio investimenti organizzativi, risultati trimestrali o annuali    

#### <a name="process-flow-for-creating-custom-classifiers"></a>Flusso di processo per la creazione di classificatori personalizzati

La creazione e la pubblicazione di un classificatore da utilizzare nelle soluzioni di conformità, ad esempio i criteri di conservazione e la supervisione delle comunicazioni, segue questo flusso. Per ulteriori dettagli sulla creazione di un classificatore addestrabile personalizzato, vedere [Creazione di un classificatore personalizzato.](classifier-get-started-with.md)

![classificatore personalizzato del flusso di processo](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Riqualificazione dei classificatori

È possibile migliorare l'accuratezza di tutti i classificatori personalizzati e di alcuni classificatori pre-addestrati fornendo loro un feedback sull'accuratezza della classificazione che eseguono. Questa operazione viene definita riqualificazione e segue questo flusso di lavoro.

![flusso di lavoro di riqualificazione classificatore](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Vedere anche

- [Etichette di conservazione](retention.md)
- [Informazioni sulla prevenzione della perdita di dati](dlp-learn-about-dlp.md)
- [Etichette di riservatezza](sensitivity-labels.md)
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
- [Stampa delle dita dei documenti](document-fingerprinting.md)
- [Corrispondenza esatta dei dati](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
