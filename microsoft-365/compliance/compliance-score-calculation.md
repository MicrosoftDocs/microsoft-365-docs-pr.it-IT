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
description: Comprendere in che modo Microsoft Compliance Manager calcola un punteggio personalizzato in base alle azioni intraprese per risolvere i rischi e migliorare la propria postura di conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f1707e0117d0a61f572716f21d13a02821955401
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262269"
---
# <a name="compliance-score-calculation"></a>Calcolo del Punteggio di conformità

**In questo articolo:** Informazioni su come Compliance Manager calcola un punteggio di conformità per l'organizzazione. In questo articolo viene illustrato come **interpretare il Punteggio**, quali sono le valutazioni della linea di base per la **protezione dei dati** , il **monitoraggio continuo**e il modo in cui i **diversi tipi di azioni vengono gestiti e segnati**.

> [!IMPORTANT]
> I consigli di Compliance Manager non devono essere interpretati come una garanzia di conformità. Spetta a te valutare e convalidare l'efficacia dei controlli del cliente per il tuo ambiente normativo. Questi servizi sono soggetti ai termini e alle condizioni nelle condizioni dei [servizi online](https://go.microsoft.com/fwlink/?linkid=2108910). Vedere anche [linee guida per la gestione delle licenze di Microsoft 365 per sicurezza e conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-to-read-your-compliance-score"></a>Come leggere il Punteggio di conformità

Il dashboard di Compliance Manager Visualizza il Punteggio di conformità globale. Questo punteggio misura lo stato di avanzamento del completamento delle azioni di miglioramento consigliate all'interno dei controlli. Il Punteggio può aiutare a capire la postura di conformità corrente. Consente inoltre di definire le priorità delle azioni in base alle proprie potenzialità di riduzione dei rischi.

Un valore score viene assegnato a tre livelli:

1. **Punteggio azione di miglioramento**: ogni azione ha un impatto diverso sulla partitura a seconda dei possibili rischi coinvolti

2. **Punteggio di controllo**: questo punteggio è la somma dei punti ottenuti completando le azioni di miglioramento all'interno del controllo. Questa somma viene applicata integralmente al Punteggio di conformità globale quando il controllo soddisfa entrambe le condizioni seguenti:
    - **Lo stato di implementazione** è uguale a **implementato** o all' **implementazione alternativa**e
    - **Risultato del test** uguale a **superato**.

3. **Punteggio valutazione**: questo punteggio è la somma dei punteggi di controllo. Viene calcolata utilizzando i punteggi azione. Ogni azione di Microsoft e ogni azione di miglioramento gestita dall'organizzazione viene conteggiata una sola volta, indipendentemente dalla frequenza con cui viene fatto riferimento in un controllo.

Il Punteggio di conformità globale viene calcolato utilizzando punteggi azione, in cui ogni azione di Microsoft viene conteggiata una sola volta, ogni azione tecnica gestita viene conteggiata una sola volta e ogni azione non tecnica gestita viene conteggiata una volta per ogni gruppo. Questa logica è progettata per fornire la contabilità più accurata del modo in cui le azioni vengono implementate e testate nell'organizzazione. È possibile notare che può comportare che il Punteggio di conformità globale sia diverso dalla media dei punteggi di valutazione. Per ulteriori informazioni [, vedere come vengono segnate le azioni](#action-types-and-points).

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365
  
Compliance Manager fornisce un punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365. Questa linea di base è un insieme di controlli che include le normative fondamentali e gli standard per la protezione dei dati e la governance dei dati generale. Questa linea di base estrae gli elementi principalmente dal NIST CSF (Istituto nazionale per gli standard e la tecnologia Cybersecurity Framework) e ISO (International Organization for Standardizzation), oltre che da FedRAMP (Federal Risk and Authorization Management Program) e GDPR (General Data Protection Regulation dell'Unione europea).

Il Punteggio iniziale viene calcolato in base alla valutazione di base predefinita per la protezione dei dati fornita a tutte le organizzazioni. Durante la prima visita, Compliance Manager sta già raccogliendo segnali dalle soluzioni Microsoft 365. Verrà visualizzato a colpo d'occhio il modo in cui l'organizzazione è in esecuzione rispetto agli standard e alle normative sulla protezione dei dati e le azioni consigliate da intraprendere.

Poiché ogni organizzazione ha esigenze specifiche, Compliance Manager si basa su di essa per impostare e gestire le valutazioni per ridurre al minimo e ridurre il rischio nel modo più completo possibile.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Modalità di valutazione continua dei controlli da Compliance Manager

Compliance Manager analizza automaticamente l'ambiente Microsoft 365 e rileva le impostazioni di sistema, aggiornando continuamente e automaticamente lo stato dell'azione tecnica. Microsoft Secure Score è il motore sottostante che esegue il monitoraggio.

Lo stato dell'azione viene aggiornato sul dashboard ogni 24 ore. Dopo aver seguito una raccomandazione per l'implementazione di un controllo, lo stato del controllo verrà visualizzato in genere aggiornato il giorno successivo.

Ad esempio, se si attiva l'autenticazione a più fattori nel portale di Azure AD, Compliance Manager rileva l'impostazione e la riflette nei dettagli della soluzione di Access Control. Viceversa, se non è stato attivato l'AMF, Compliance Manager contrassegna come azione consigliata per l'esecuzione.

Per ulteriori informazioni, vedere [Punteggio sicuro e modalità di funzionamento](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Tipi di azione e punti

Compliance Manager tiene traccia di due tipi di azioni:

1. **Azioni di miglioramento**: azioni gestite dall'organizzazione.
2. **Azioni Microsoft**: azioni che Microsoft gestisce.

Entrambi i tipi di azioni hanno punti che contano verso il Punteggio globale quando sono stati completati.

### <a name="technical-and-non-technical-actions"></a>Azioni tecniche e non tecniche

Le azioni sono raggruppate in base al fatto che si tratti di carattere tecnico o non tecnico. L'impatto dei punteggi di ogni azione varia in base al tipo.

- Le **azioni tecniche** vengono implementate interagendo con la tecnologia di una soluzione, ad esempio la modifica di una configurazione. I punti per le azioni tecniche vengono concessi una volta per azione, indipendentemente dal numero di gruppi a cui appartiene.

- Le **azioni non tecniche** vengono gestite dall'organizzazione e implementate in modi diversi dall'utilizzo della tecnologia di una soluzione. Esistono due tipi di azioni non tecniche: la **documentazione** e l' **operatività**. I punti per queste azioni vengono applicati al Punteggio di conformità a livello di gruppo. Questo significa che se un'azione esiste in più gruppi, il valore del punto dell'azione verrà visualizzato ogni volta che viene implementato all'interno di un gruppo.

**Esempio di come vengono segnate le azioni tecniche e non tecniche:**

Si supponga di disporre di un'azione tecnica di 3 punti che esiste in 5 gruppi e che si dispone di un'azione non tecnica del valore di 3 punti che esiste negli stessi 5 gruppi.

Se l'azione tecnica viene implementata correttamente, il numero totale di punti ricevuti è 3. Ciò è dovuto al fatto che è necessario implementare un'azione solo una volta per il tenant. Lo stato di implementazione e di testing per l'azione tecnica mostrerà lo stesso in tutte le istanze di tale azione, in tutti i gruppi a cui appartiene.

Se si implementa correttamente l'azione non tecnica in ognuno dei 5 gruppi, il numero totale di punti ricevuti è 15. Ciò è dovuto al fatto che è necessario implementare l'azione in ogni gruppo. L'implementazione e lo stato dei test per l'azione non tecnica differiscono tra i gruppi perché l'azione viene implementata separatamente all'interno di ognuno dei suoi gruppi.

Questa logica di punteggio è progettata per fornire la contabilità più accurata del modo in cui le azioni vengono implementate e testate nell'organizzazione.

### <a name="how-score-values-are-determined"></a>Come vengono determinati i valori dei punteggi
 
Alle azioni viene assegnato un valore di punteggio a seconda che sia obbligatorio o discrezionale e che si tratti di preventivo, investigativo o correttivo.

### <a name="mandatory-and-discretionary-actions"></a>Azioni obbligatorie e discrezionali

 - Le **azioni obbligatorie** non possono essere ignorate intenzionalmente o accidentalmente. Un esempio di azione obbligatoria è un criterio di password gestito centralmente che consente di impostare i requisiti per la lunghezza, la complessità e la scadenza delle password. Gli utenti devono seguire questi requisiti per accedere al sistema.
  
 - Le **azioni discrezionali** fanno affidamento sugli utenti per comprendere e rispettare un criterio. Ad esempio, un criterio che richiede agli utenti di bloccare il proprio computer quando lo lasciano è un'azione discrezionale, perché si basa sull'utente.
  
### <a name="preventative-detective-and-corrective-actions"></a>Azioni preventive, investigative e correttive
  
 - Le **azioni preventive** affrontano rischi specifici. Ad esempio, la protezione delle informazioni a riposo tramite la crittografia è un'azione preventiva contro gli attacchi e le violazioni. La separazione dei compiti è un'azione preventiva per gestire i conflitti di interesse e prevenire le frodi.
  
 - Le **azioni investigative** eseguono attivamente il monitoraggio dei sistemi per identificare condizioni o comportamenti irregolari che rappresentano il rischio o che possono essere utilizzati per rilevare intrusioni o violazioni. Tra gli esempi sono inclusi il controllo dell'accesso di sistema e le azioni amministrative privilegiate. I controlli di conformità normativi sono un tipo di azione detective utilizzato per individuare i problemi del processo.
  
- Le **azioni correttive** tentano di mantenere al minimo gli effetti negativi di un incidente di sicurezza, intraprendere azioni correttive per ridurre l'effetto immediato e, se possibile, invertire i danni. La risposta agli incidenti sulla privacy è un'azione correttiva per limitare i danni e ripristinare i sistemi a uno stato operativo dopo una violazione.
  
Ogni azione ha un valore assegnato in Compliance Manager in base al rischio che rappresenta:

|**Type**|**Punteggio assegnato**|
|:-----|:-----|
| Obbligatorio preventivo | 27 |
| Discrezionale preventiva | 9  |
| Detective obbligatorio | 3 |
| Discrezionale detective | 1  |
| Obbligatorio correttivo | 3 |
| Discrezionale correttiva | 1  |
  
![Valori dei punti di azione di Compliance Manager](../media/compliance-score-action-scoring.png "Valori dei punti di azione di Compliance Manager")