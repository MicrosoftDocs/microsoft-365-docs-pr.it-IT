---
title: Calcolo del Punteggio di conformità
f1.keywords:
- NOCSH
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
description: Informazioni sul modo in cui il Punteggio di conformità di Microsoft calcola un punteggio personalizzato sulla base delle azioni intraprese per risolvere i rischi e migliorare la conformità alla postura.
ms.openlocfilehash: ca8615f8c15264104faa71d155d2656cd788bd53
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078633"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Calcolo del Punteggio di conformità Microsoft (anteprima)

> [!IMPORTANT]
> Il Punteggio di conformità non esprime una misura assoluta di conformità organizzativa rispetto a una norma o a un regolamento particolari. Esprime la misura in cui sono stati adottati controlli che possono ridurre i rischi per i dati personali e la privacy individuale. Le raccomandazioni del Punteggio di conformità e del Compliance Manager non devono essere interpretate come garanzia di conformità. Questo servizio è attualmente in anteprima ed è soggetto ai termini e alle condizioni nelle condizioni dei [servizi online](https://go.microsoft.com/fwlink/?linkid=2108910).

## <a name="overview"></a>Panoramica

Il dashboard del Punteggio di conformità Visualizza un punteggio che misura lo stato di avanzamento del completamento delle azioni di miglioramento all'interno dei controlli. I punti si accumulano quando si completano le azioni.

Il Punteggio viene calcolato in base al completamento delle azioni gestite da Microsoft e delle azioni gestite dal cliente. Ogni azione ha un impatto diverso sulla partitura, a seconda dei possibili rischi, quindi il punteggio può contribuire a definire la priorità su quale azione concentrarsi per migliorare la postura complessiva di conformità.

I valori di Punteggio di conformità visualizzati per il controllo vengono applicati *integralmente* al punteggio totale su una base di pass/fail. Il controllo viene implementato e passa il test di valutazione successivo o non lo è. I punti assegnati vengono aggiunti al Punteggio di conformità quando il controllo è:

- **Lo stato di implementazione** è uguale a **implementato** o all' **implementazione alternativa** e,
- **Risultato del test** uguale a **superato**.

La somma dei punti ottenuti adottando azioni di miglioramento è il Punteggio di controllo. La somma dei punteggi di controllo è il Punteggio di valutazione. La somma dei punteggi di valutazione è il Punteggio di conformità globale

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365
  
Punteggio di conformità consente di ottenere un punteggio esterno alla casella di controllo basato sulla linea di base per la protezione dei dati di Microsoft 365, che è un insieme di controlli che include le normative fondamentali e gli standard per la protezione dei dati e la governance dei dati generale. Questa linea di base estrae gli elementi principalmente dal NIST CSF (Istituto nazionale per gli standard e la tecnologia Cybersecurity Framework) e ISO (organizzazione internazionale per la standardizzazione), nonché da FedRAMP (gestione federale dei rischi e delle autorizzazioni Program) e GDPR (regolamentazione generale sulla protezione dei dati dell'Unione europea).

## <a name="how-compliance-score-continuously-assesses-controls"></a>Come il Punteggio di conformità valuta continuamente i controlli

Il Punteggio di conformità analizza automaticamente l'ambiente Microsoft 365 e rileva le impostazioni di sistema, aggiornando continuamente e automaticamente lo stato del controllo tecnico. Il Punteggio di conformità utilizza il Punteggio sicuro come motore sottostante che esegue il monitoraggio. [Per ulteriori informazioni, vedere Punteggio sicuro e modalità di funzionamento](../security/mtp/microsoft-secure-score.md).

Lo stato del controllo viene aggiornato sul dashboard del Punteggio di conformità ogni 24 ore. Dopo aver seguito una raccomandazione per implementare un controllo, verrà visualizzato lo stato del controllo aggiornato il giorno successivo.

Ad esempio, se si attiva l'autenticazione a più fattori nel portale di Azure AD, il Punteggio di conformità rileva l'impostazione e riflette quella nei dettagli della soluzione di Access Control. Viceversa, se non si è attivato l'AMF, il Punteggio di conformità contrassegna come azione consigliata da eseguire.

Durante l'anteprima pubblica, la valutazione continua è disponibile per una parte dei controlli, ma non per tutti.
  
## <a name="control-types-and-points"></a>Tipi di controllo e punti

Il Punteggio di conformità tiene traccia di due tipi di controlli, gestiti da Microsoft e gestiti dal cliente, ognuno dei quali ha punti che contribuiscono alla valutazione complessiva:

1. I **punti gestiti dal cliente** contribuiscono al Punteggio di conformità basato sui controlli gestiti dall'organizzazione.
2. I **punti gestiti da Microsoft** contribuiscono al Punteggio di conformità basato sui controlli gestiti da Microsoft come provider di servizi cloud.

Ai controlli viene assegnato un valore di punteggio a seconda che siano obbligatori o discrezionali e siano essi preventivo, investigativo o correttivo, come descritto di seguito.

### <a name="mandatory-and-discretionary-controls"></a>Controlli obbligatori e discrezionali

 - I **controlli obbligatori** sono azioni che non possono essere ignorate intenzionalmente o accidentalmente. Un esempio è un criterio di password gestito in modo centralizzato che consente di impostare i requisiti per la lunghezza, la complessità e la scadenza delle password. Gli utenti devono essere conformi a questi requisiti per accedere al sistema.
  
 - I **controlli discrezionali** fanno affidamento sugli utenti per comprendere i criteri e agire di conseguenza. Ad esempio, un criterio che richiede agli utenti di bloccare il proprio computer quando lo lasciano è un controllo discrezionale, perché si basa sull'utente.
  
### <a name="preventative-detective-and-corrective-controls"></a>Controlli preventivo, investigativo e correttivo
  
 - I **controlli preventivi** affrontano rischi specifici. Ad esempio, la protezione delle informazioni a riposo tramite la crittografia è un controllo preventivo per gli attacchi e le violazioni. La separazione dei compiti è un controllo preventivo per la gestione dei conflitti di interesse e la protezione contro le frodi.
  
 - **Detective Controls** monitora attivamente i sistemi per identificare condizioni o comportamenti irregolari che rappresentano i rischi o che possono essere utilizzati per rilevare intrusioni o determinare se si verifica una violazione. Il controllo dell'accesso di sistema e l'auditing delle azioni amministrative privilegiate sono tipi di controlli di monitoraggio detective. I controlli di conformità normativi sono un tipo di controllo detective utilizzato per individuare i problemi del processo.
  
- I **Controlli correttivi** tentano di mantenere al minimo gli effetti negativi di un incidente di sicurezza, intraprendere azioni correttive per ridurre l'effetto immediato e, se possibile, invertire i danni. La risposta agli incidenti sulla privacy è un controllo correttivo per limitare i danni e ripristinare i sistemi a uno stato operativo dopo una violazione.
  
Ogni controllo ha un valore assegnato nel punteggio di conformità basato sul rischio che rappresenta:

|**Tipo**|**Punteggio assegnato**|
|:-----|:-----|
| Obbligatorio preventivo | 27 |
| Discrezionale preventiva | 9  |
| Detective obbligatorio | 3  |
| Discrezionale detective | 1  |
| Obbligatorio correttivo | 3  |
| Discrezionale correttiva | 1  |
  
