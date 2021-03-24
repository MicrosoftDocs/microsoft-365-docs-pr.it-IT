---
title: Calcolo del punteggio di conformità
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
description: Comprendere in che modo Microsoft Compliance Manager calcola un punteggio personalizzato in base alle azioni intraprese per affrontare i rischi e migliorare la propria posizione di conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 756ce207b1e9583bf63f19351e85955950487404
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052114"
---
# <a name="compliance-score-calculation"></a>Calcolo del punteggio di conformità

**In questo articolo:** Informazioni su come Compliance Manager calcola un punteggio di conformità per l'organizzazione. In questo articolo viene illustrato come interpretare il **punteggio,** cosa include la valutazione data **protection baseline,** il monitoraggio continuo e il modo in cui i diversi tipi di azioni vengono **gestiti e classificati.** 

> [!IMPORTANT]
> I consigli di Compliance Manager non devono essere interpretati come una garanzia di conformità. L'utente deve valutare e convalidare l'efficacia dei controlli dei clienti in base all'ambiente normativo. Questi servizi sono soggetti ai termini e alle condizioni delle Condizioni [dei Servizi online.](https://go.microsoft.com/fwlink/?linkid=2108910) Vedi anche Indicazioni sulla licenza di [Microsoft 365 per la sicurezza e la conformità.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="how-to-read-your-compliance-score"></a>Come leggere il punteggio di conformità

Nel dashboard di Compliance Manager viene visualizzato il punteggio di conformità complessivo. Questo punteggio misura i progressi nel completamento delle azioni di miglioramento consigliate all'interno dei controlli. Il punteggio può aiutarti a comprendere la tua attuale posizione di conformità. Può anche aiutare a definire le priorità delle azioni in base al loro potenziale per ridurre i rischi.

Un valore di punteggio viene assegnato a tre livelli:

1. **Punteggio azione di miglioramento**: ogni azione ha un impatto diverso sul punteggio a seconda del potenziale rischio coinvolto

2. **Punteggio di controllo**: questo punteggio è la somma dei punti ottenuti completando le azioni di miglioramento all'interno del controllo. Questa somma viene applicata per intero al punteggio di conformità complessivo quando il controllo soddisfa entrambe le condizioni seguenti:
    - **Stato implementazione** è uguale **a Implementazione** **implementata o Implementazione** alternativa e
    - **Risultato test** uguale a **Superato**.

3. **Punteggio di valutazione**: questo punteggio è la somma dei punteggi di controllo. Viene calcolato utilizzando i punteggi delle azioni. Ogni azione Microsoft e ogni azione di miglioramento gestita dall'organizzazione viene conteggiata una sola volta, indipendentemente dalla frequenza di riferimento in un controllo.

Il punteggio di conformità complessivo viene calcolato usando i punteggi delle azioni, in cui ogni azione Microsoft viene conteggiata una sola volta, ogni azione tecnica che gestisci viene conteggiata una volta e ogni azione non tecnica che gestisci viene conteggiata una volta per gruppo. Questa logica è progettata per fornire la contabilità più accurata di come le azioni vengono implementate e testate nell'organizzazione. È possibile notare che ciò può causare una differenza tra il punteggio di conformità complessivo e la media dei punteggi di valutazione. Altre informazioni di seguito sul [punteggio delle azioni](#action-types-and-points).

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Punteggio iniziale basato sulla baseline di protezione dei dati di Microsoft 365
  
Compliance Manager fornisce un punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365. Questa linea di base è un insieme di controlli che include normative e standard chiave per la protezione dei dati e la governance generale dei dati. Questa linea di base si basa principalmente su NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), nonché su FedRAMP (Federal Risk and Authorization Management Program) e GDPR (General Data Protection Regulation of the European Union).

Il punteggio iniziale viene calcolato in base alla valutazione di base di protezione dei dati predefinita fornita a tutte le organizzazioni. Al primo passaggio, Compliance Manager sta già raccogliendo segnali dalle soluzioni Microsoft 365. Vedrai a colpo d'occhio le prestazioni dell'organizzazione rispetto agli standard e alle normative di protezione dei dati chiave e vedrai le azioni di miglioramento suggerite da intraprendere.

Poiché ogni organizzazione ha esigenze specifiche, Compliance Manager si basa su di te per configurare e gestire le valutazioni per ridurre al minimo e ridurre i rischi nel modo più completo possibile.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Modalità di valutazione continua dei controlli da parte di Compliance Manager

Compliance Manager analizza automaticamente l'ambiente Microsoft 365 e rileva le impostazioni di sistema, aggiornando continuamente e automaticamente lo stato delle azioni tecniche. Microsoft Secure Score è il motore sottostante che esegue il monitoraggio.

Lo stato dell'azione viene aggiornato nel dashboard ogni 24 ore. Dopo aver seguito un suggerimento per implementare un controllo, lo stato del controllo verrà in genere aggiornato il giorno successivo.

Ad esempio, se si attiva l'autenticazione a più fattori (MFA) nel portale di Azure AD, Compliance Manager rileva l'impostazione e la riflette nei dettagli della soluzione di accesso di controllo. Al contrario, se non è stata attivata l'autenticazione a più fattori, Compliance Manager contrassegna tale azione come azione consigliata da eseguire.

Ulteriori informazioni su [Secure Score e sul suo funzionamento.](../security/defender/microsoft-secure-score.md)
  
## <a name="action-types-and-points"></a>Tipi di azione e punti

Compliance Manager tiene traccia di due tipi di azioni:

1. **Azioni di miglioramento:** azioni gestite dall'organizzazione.
2. **Azioni Microsoft**: azioni gestite da Microsoft.

Entrambi i tipi di azioni hanno punti che vengono conteggiati per il punteggio complessivo al termine.

### <a name="technical-and-non-technical-actions"></a>Azioni tecniche e non tecniche

Le azioni sono raggruppate in base alla natura tecnica o non tecnica. L'impatto del punteggio di ogni azione è diverso per tipo.

- **Le azioni** tecniche vengono implementate interagendo con la tecnologia di una soluzione ( ad esempio, la modifica di una configurazione). I punti per le azioni tecniche vengono concessi una sola volta per azione, indipendentemente dal numero di gruppi a cui appartiene.

- **Le azioni non tecniche** vengono gestite dall'organizzazione e implementate in modi diversi dall'utilizzo della tecnologia di una soluzione. Esistono due tipi di azioni non tecniche: **documentazione** e **operativo.** I punti per queste azioni vengono applicati al punteggio di conformità a livello di gruppo. Ciò significa che se un'azione esiste in più gruppi, riceverai il valore di punto dell'azione ogni volta che la implementi all'interno di un gruppo.

**Esempio di punteggio delle azioni tecniche e non tecniche:**

Supponiamo che tu abbia un'azione tecnica che vale 3 punti che esiste in 5 gruppi e che tu abbia un'azione non tecnica che vale 3 punti che esiste negli stessi 5 gruppi.

Se si implementa correttamente l'azione tecnica, il numero totale di punti ricevuti è 3. Ciò è dovuto al fatto che è necessario implementare l'azione una sola volta per il tenant. L'implementazione e lo stato del test per l'azione tecnica saranno uguali in tutte le istanze di tale azione, in ogni gruppo a cui appartiene.

Se si implementa correttamente l'azione non tecnica in ognuno dei 5 gruppi, il numero totale di punti ricevuti è 15. Ciò è dovuto al fatto che è necessario implementare l'azione in ogni gruppo. L'implementazione e lo stato del test per l'azione non tecnica saranno diversi tra i gruppi perché l'azione viene implementata separatamente all'interno di ognuno dei relativi gruppi.

Questa logica di punteggio è progettata per fornire la contabilità più accurata del modo in cui le azioni vengono implementate e testate nell'organizzazione.

### <a name="how-score-values-are-determined"></a>Come vengono determinati i valori del punteggio
 
Alle azioni viene assegnato un valore di punteggio in base al fatto che siano obbligatorie o discrezionali e che siano preventive, investigative o correttive.

### <a name="mandatory-and-discretionary-actions"></a>Azioni obbligatorie e discrezionali

 - **Le azioni** obbligatorie non possono essere ignorate, intenzionalmente o accidentalmente. Un esempio di azione obbligatoria è un criterio password gestito centralmente che imposta i requisiti per lunghezza, complessità e scadenza delle password. Gli utenti devono attenersi a questi requisiti per accedere al sistema.
  
 - **Le azioni discrezionali** si basano sugli utenti per comprendere e rispettare un criterio. Ad esempio, un criterio che richiede agli utenti di bloccare il computer quando lo abbandona è un'azione discrezionale perché si basa sull'utente.
  
### <a name="preventative-detective-and-corrective-actions"></a>Azioni preventive, investigative e correttive
  
 - **Le azioni preventive** affrontano rischi specifici. Ad esempio, proteggere le informazioni in stato di inquieto utilizzando la crittografia è un'azione preventiva contro attacchi e violazioni. La separazione dei compiti è un'azione preventiva per gestire il conflitto di interessi e proteggere dalle frodi.
  
 - **Le azioni del** detective monitorano attivamente i sistemi per identificare condizioni o comportamenti irregolari che rappresentano rischi o che possono essere utilizzati per rilevare intrusioni o violazioni. Alcuni esempi includono il controllo dell'accesso al sistema e le azioni amministrative con privilegi. I controlli di conformità normativa sono un tipo di azione investigativa usata per individuare i problemi relativi ai processi.
  
- **Le azioni correttive** cercano di ridurre al minimo gli effetti negativi di un incidente di sicurezza, di intraprendere azioni correttive per ridurre l'effetto immediato e di annullare il danno, se possibile. La risposta agli incidenti di privacy è un'azione correttiva per limitare i danni e ripristinare i sistemi a uno stato operativo dopo una violazione.
  
Ogni azione ha un valore assegnato in Compliance Manager in base al rischio rappresentato:

|**Type**|**Punteggio assegnato**|
|:-----|:-----|
| Preventivo obbligatorio | 27 |
| Discrezionale preventivo | 9  |
| Detective obbligatorio | 3  |
| Detective discretionary | 1 |
| Obbligatorio correttivo | 3  |
| Discrezionale correttivo | 1 |
  
![Valori del punto di azione di Compliance Manager](../media/compliance-score-action-scoring.png "Valori del punto di azione di Compliance Manager")