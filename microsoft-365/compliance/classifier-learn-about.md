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
description: Un classificatore formabile di Microsoft 365 è uno strumento che è possibile formare per riconoscere vari tipi di contenuto fornendo esempi positivi e negativi da esaminare. Dopo aver preparato il classificatore, si conferma che i risultati sono accurati. È quindi possibile utilizzarlo per cercare il contenuto dell'organizzazione e classificarlo per applicare etichette di conservazione o riservatezza o includerlo nei criteri di prevenzione della perdita dei dati (DLP) o di conservazione.
ms.openlocfilehash: 0e5f712b76af2fba3d456997a47352773d92d766
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759900"
---
# <a name="learn-about-trainable-classifiers"></a>Informazioni sui classificatori sottoponibili a training

La classificazione e l'etichettatura dei contenuti in modo che possano essere protetti e gestiti correttamente sono il punto di partenza per la disciplina di protezione delle informazioni. Microsoft 365 ha tre modi per classificare il contenuto.

## <a name="manually"></a>Manualmente

Questo metodo richiede un'azione e un'azione umana. Un amministratore può usare le etichette e i tipi di informazioni riservate esistenti oppure crearne di propri e quindi pubblicarli. Gli utenti e gli amministratori li applicano al contenuto non appena vengono rilevati. È quindi possibile proteggere il contenuto e gestirne l'eliminazione.

## <a name="automated-pattern-matching"></a>Corrispondenza automatica dei modelli

Questa categoria di meccanismi di classificazione include la ricerca del contenuto tramite:

- Parole chiave o valori di metadati (linguaggio query con parole chiave).
- Uso di modelli identificati in precedenza di informazioni riservate come la previdenza sociale, i numeri di carta di credito o di conto corrente [bancario (definizioni di](sensitive-information-type-entity-definitions.md)entità tipo di informazioni riservate) .
- Riconoscimento di un elemento perché si tratta di una variante di un modello (stampa delle [dita del documento).](document-fingerprinting.md)
- Utilizzo della presenza di stringhe esatte [(corrispondenza esatta dei dati)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Le etichette di riservatezza e conservazione possono quindi essere applicate automaticamente per rendere il contenuto disponibile per l'utilizzo nella prevenzione della perdita di dati [(DLP)](data-loss-prevention-policies.md) e applicare automaticamente i criteri per [le etichette di conservazione.](apply-retention-labels-automatically.md)

## <a name="classifiers"></a>Classificatori

Questo metodo di classificazione è particolarmente adatto al contenuto che non è facilmente identificato dai metodi di corrispondenza dei modelli manuali o automatizzati. Questo metodo di classificazione riguarda più il training di un classificatore per identificare un elemento in base all'elemento, non in base agli elementi presenti nell'elemento (corrispondenza del modello). Un classificatore apprende come identificare un tipo di contenuto esaminando centinaia di esempi del contenuto che ti interessa classificare. Per iniziare, vengono forniti esempi che sono sicuramente inclusi nella categoria. Dopo averli elaborati, puoi testarlo fornendo una combinazione di esempi di corrispondenza e non corrispondenti. Il classificatore esegue quindi previsioni per stabilire se un determinato elemento rientra nella categoria che si sta creando. È quindi possibile confermarne i risultati, ordinando i veri positivi, i veri negativi, i falsi positivi e i falsi negativi per aumentare l'accuratezza delle previsioni. 

Quando si pubblica il classificatore, questo ordina gli elementi in posizioni come SharePoint Online, Exchange e OneDrive e classifica il contenuto. Dopo aver pubblicato il classificatore, è possibile continuare a formarlo usando un processo di feedback simile al processo di formazione iniziale.

### <a name="where-you-can-use-trainable-classifiers"></a>Dove è possibile usare classificatori di cui è possibile eseguire il training
Sia i classificatori predefiniti che i classificatori formabili sono disponibili come condizione per l'etichettatura automatica di [Office](apply-sensitivity-label-automatically.md)con etichette di riservatezza, applicare automaticamente i criteri delle etichette di conservazione in base [a](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) una condizione e nella conformità delle [comunicazioni.](communication-compliance.md) 

Le etichette di riservatezza possono usare i classificatori come condizioni, vedere Applicare automaticamente [un'etichetta](apply-sensitivity-label-automatically.md)di riservatezza al contenuto.

> [!IMPORTANT]
> I classificatori funzionano solo con elementi non crittografati e in inglese.

## <a name="types-of-classifiers"></a>Tipi di classificatori

- **Classificatori già** preparati: Microsoft ha creato e preparato in precedenza un numero di classificatori che è possibile iniziare a usare senza formarli. Questi classificatori verranno visualizzati con lo stato `Ready to use` .
- **classificatori personalizzati:** se si hanno esigenze di classificazione che vanno oltre quella dei classificatori già preparati, è possibile creare e formare i propri classificatori.

### <a name="pre-trained-classifiers"></a>Classificatori già preparati

Microsoft 365 include cinque classificatori pre-preparati:

> [!CAUTION]
> Stiamo deprecando **il** classificatore pre-preparato del linguaggio offensivo perché ha prodotto un numero elevato di falsi positivi. Non usarlo e, se lo si sta attualmente utilizzando, è consigliabile disattivare i processi aziendali. È consigliabile **usare** invece i  classificatori pre-preparati per **minacce,** volgarità e molestie.

- **Curriculum:** rileva gli elementi che sono account testuali delle qualificazioni personali, didattiche, professionali, dell'esperienza professionale e di altre informazioni di identificazione personale di un candidato
- **Codice sorgente:** rileva gli elementi che contengono un set di istruzioni e istruzioni scritte nei primi 25 linguaggi di programmazione del computer usati su GitHub
    - ActionScript
    - C
    - C #
    - C++
    - Clojure
    - CoffeeScript
    - Vai
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
> Il codice sorgente viene preparato per rilevare quando la maggior parte del testo è codice sorgente. Non rileva il testo del codice sorgente che è intersperso con testo normale.

- Molestie: rileva una categoria specifica di elementi di testo in linguaggio offensivo correlati a comportamenti offensivi mirati a uno o più individui in base alle seguenti caratteristiche: corsa, etnia, razziale, origine nazionale, sesso, orientamento sessuale, età, disabilità
- **Volgarità:** rileva una categoria specifica di elementi di testo in linguaggio offensivo che contengono espressioni che invade la maggior parte delle persone
- **Minaccia:** rileva una categoria specifica di elementi di testo in linguaggio offensivo correlati alle minacce per commettere atti di violenza o danneggiare fisicamente una persona o una proprietà

Questi vengono visualizzati nella visualizzazione classificatori sotto forma di training del Centro conformità **Microsoft 365**  >    >   con lo stato `Ready to use` .

![classificatori-classificatori pre-preparati](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Tieni presente che il linguaggio offensivo, le molestie, le volgarità e i classificatori delle minacce funzionano solo con il testo ricercabile non sono esaustivi o completi.  Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare tali classificatori a sua discrezione. Anche se i classificatori possono aiutare l'organizzazione nel monitoraggio offensivo e di altro linguaggio utilizzato, i classificatori non affrontano le conseguenze di tale linguaggio e non sono destinati a fornire l'unico mezzo dell'organizzazione per monitorare o rispondere all'uso di tale linguaggio. L'organizzazione, e non Microsoft o le sue filiali, rimane responsabile di tutte le decisioni relative al monitoraggio, all'applicazione, al blocco, alla rimozione e alla conservazione di qualsiasi contenuto identificato da un classificatore preparato.

### <a name="custom-classifiers"></a>Classificatori personalizzati

Quando i classificatori già preparati non soddisfano le proprie esigenze, è possibile creare e formare i propri classificatori. C'è molto più lavoro da eseguire per creare il proprio, ma saranno molto più personalizzati in base alle esigenze delle organizzazioni. 

Ad esempio, è possibile creare classificatori che possono essere addestrati per:
 
- Documenti legali, ad esempio privilegio avvocato cliente, insiemi di chiusura, dichiarazione di lavoro
- Documenti aziendali strategici, come comunicati stampa, fusioni e acquisizioni, accordi, piani aziendali o di marketing, proprietà intellettuale, brevetti, documentazione di progettazione
- Informazioni sui prezzi, ad esempio fatture, offerte di prezzo, ordini di lavoro, documenti di offerta 
- Informazioni finanziarie, ad esempio investimenti nell'organizzazione, risultati trimestrali o annuali    

#### <a name="process-flow-for-creating-custom-classifiers"></a>Flusso di processo per la creazione di classificatori personalizzati

La creazione e la pubblicazione di un classificatore da utilizzare nelle soluzioni di conformità, ad esempio i criteri di conservazione e la supervisione delle comunicazioni, segue questo flusso. Per ulteriori informazioni sulla creazione di un classificatore trainabile personalizzato, vedere Creazione [di un classificatore personalizzato.](classifier-get-started-with.md)

![classificatore personalizzato del flusso di processo](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Riqualificazione dei classificatori

È possibile migliorare l'accuratezza di tutti i classificatori personalizzati e di alcuni classificatori già preparati fornendo loro un feedback sull'accuratezza della classificazione che eseguono. Questa operazione è detta riqualificazione e segue questo flusso di lavoro.

![flusso di lavoro di riqualificazione dei classificatori](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Vedere anche

- [Etichette di conservazione](retention.md)
- [Data loss prevention (DLP)](data-loss-prevention-policies.md)
- [Etichette di riservatezza](sensitivity-labels.md)
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
- [Stampa delle dita dei documenti](document-fingerprinting.md)
- [Corrispondenza esatta dei dati](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
