---
title: Metodologia del Punteggio di conformità
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal. Compliance Manager consente di monitorare, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: 148920fac825dab9f67a79bc11907b72218e47bc
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083230"
---
# <a name="compliance-score-methodology-preview"></a>Metodologia del Punteggio di conformità (anteprima)

> [!NOTE]
> Il punteggio di conformità non esprime una misura assoluta di conformità organizzativa a nessun particolare standard o regolamento. Esprime la misura in cui sono stati adottati controlli che possono ridurre i rischi per i dati personali e la privacy individuale. Nessun servizio può garantire la conformità a uno standard o regolamento e il punteggio di conformità non deve essere interpretato come una garanzia in alcun modo.

Il dashboard di Compliance Manager visualizza un punteggio di conformità totale per le valutazioni in ogni riquadro di valutazione. Si tratta del Punteggio di conformità globale per la valutazione ed è l'accumulo di punti ricevuti per ogni controllo implementato e testato nella valutazione. Per una nuova valutazione, il Punteggio di conformità ha un valore iniziale per i controlli gestiti Microsoft inclusi testati da terze parti indipendenti. Il Punteggio di conformità può aiutare a definire la priorità quali valutazioni e controlli concentrarsi su per migliorare la posizione di conformità globale.

I valori di Punteggio di conformità visualizzati per il controllo vengono applicati *integralmente* al Punteggio di conformità totale su una base pass/fail. Il controllo viene implementato e passa il test di valutazione successivo o non lo è. Non vi è alcun credito parziale per un'implementazione parziale. I punti assegnati vengono aggiunti al Punteggio di conformità quando il controllo è:

- **Lo stato di implementazione** è uguale a **implementato** o all' **implementazione alternativa** e,
- **Risultato del test** uguale a **superato**.

## <a name="compliance-score"></a>Punteggio di conformità
  
In Compliance Manager, i punteggi della linea di base passano dal livello di controllo al livello dell'elemento Action. I punteggi si basano sullo scopo (Detective, preventivo o correttivo) e sull'applicazione (discrezionale o obbligatoria) dell'azione.

Gli elementi azione vengono mappati ai controlli e quando un controllo viene mappato a più elementi azione, la somma dei punteggi degli elementi azione è il Punteggio di controllo. La somma del Punteggio di controllo per tutti i controlli in una determinata valutazione è il Punteggio di valutazione. Il Punteggio medio di tutte le valutazioni in un gruppo è il Punteggio di conformità per tale gruppo.
  
### <a name="mandatory-or-discretionary-controls"></a>Controlli obbligatori o discrezionali
  
 I **controlli obbligatori** sono azioni che non possono essere ignorate intenzionalmente o accidentalmente. Un esempio di controllo obbligatorio comune è costituito da un criterio password gestito in modo centralizzato che consente di impostare i requisiti per la lunghezza, la complessità e la scadenza delle password. Gli utenti devono essere conformi a questi requisiti per accedere al sistema.
  
 I **controlli discrezionali** fanno affidamento sugli utenti per comprendere i criteri e agire di conseguenza. Ad esempio, un criterio che richiede agli utenti di bloccare il proprio computer quando lo lasciano è un controllo discrezionale, perché si basa sull'utente.
  
### <a name="preventative-detective-or-corrective-controls"></a>Controlli preventivo, investigativo o correttivo
  
 I **controlli preventivi** sono azioni che impediscono rischi specifici. Ad esempio, la protezione delle informazioni a riposo tramite la crittografia è un controllo preventivo contro gli attacchi, le violazioni. La separazione dei compiti è un controllo preventivo per gestire i conflitti di interesse e prevenire le frodi.
  
 I **controlli detective** sono azioni che monitorano attivamente i sistemi per identificare condizioni o comportamenti irregolari che rappresentano il rischio o che possono essere utilizzati per rilevare intrusioni o determinare se si è verificata una violazione. Il controllo dell'accesso di sistema e l'auditing delle azioni amministrative privilegiate sono tipi di controlli di monitoraggio detective. I controlli di conformità normativi sono un tipo di controllo detective utilizzato per individuare i problemi del processo.
  
I **Controlli correttivi** sono controlli che tentano di mantenere al minimo gli effetti negativi di un incidente di sicurezza, intraprendere azioni correttive per ridurre l'effetto immediato e invertire il danno, se possibile. La risposta agli incidenti sulla privacy è un controllo correttivo per limitare i danni e ripristinare i sistemi a uno stato operativo dopo una violazione.
  
Ogni controllo ha un valore assegnato in Compliance Manager in base al rischio che rappresenta:

|**Tipo**|**Punteggio assegnato**|
|:-----|:-----|
| Obbligatorio preventivo | 27 |
| Discrezionale preventiva | 9  |
| Detective obbligatorio | 3 |
| Discrezionale detective | 1 |
| Obbligatorio correttivo | 3 |
| Discrezionale correttiva | 1 |
  
## <a name="action-item-workflow"></a>Flusso di lavoro elementi azione

Di seguito è indicato il flusso di lavoro di base per un elemento di azione tipico:
  
1. La conformità, il rischio, la privacy e/o il responsabile della protezione dei dati di un'organizzazione assegna un'attività a un utente dell'organizzazione per implementare un controllo. Tale persona potrebbe essere:

    - Proprietario di un criterio aziendale.
    - Un responsabile dell'implementazione IT.
    - Un altro individuo nell'organizzazione con la responsabilità di eseguire l'attività.

2. Tale individuo esegue le attività necessarie per implementare il controllo, carica la prova dell'implementazione in Compliance Manager e contrassegna il controllo associato all'elemento di azione implementato. Una volta completate queste attività, assegnano l'elemento azione a un valutatore per la convalida.

    I valutatori possono essere:

    - Valutatori interni che eseguono la convalida dei controlli all'interno di un'organizzazione.
    - Valutatori esterni che esaminano, verificano e certificano la conformità, ad esempio le organizzazioni indipendenti di terze parti che controllano i servizi cloud di Microsoft.

3. Il valutatore convalida il controllo ed esamina l'evidenza e contrassegna il controllo come valutato e i risultati della valutazione.

Una volta valutati tutti i controlli associati a una valutazione, la valutazione è stata completata.