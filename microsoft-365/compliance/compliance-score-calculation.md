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
ms.openlocfilehash: f1707e0117d0a61f572716f21d13a02821955401
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262269"
---
# <a name="compliance-score-calculation"></a>Calcolo del punteggio di conformità

**In questo articolo:** Informazioni su come Compliance Manager calcola un punteggio di conformità per l'organizzazione. In questo articolo viene illustrato come  interpretare il **punteggio,** cosa include la valutazione di base della protezione dei **dati,** il monitoraggio continuo e il modo in cui vengono gestiti e classificati i **diversi tipi di azioni.**

> [!IMPORTANT]
> I consigli di Compliance Manager non devono essere interpretati come una garanzia di conformità. L'utente deve valutare e convalidare l'efficacia dei controlli dei clienti in base al proprio ambiente normativo. Questi servizi sono soggetti ai termini e alle condizioni delle Condizioni dei [Servizi online.](https://go.microsoft.com/fwlink/?linkid=2108910) Vedere anche [indicazioni sulle licenze di Microsoft 365 per la sicurezza e la conformità.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="how-to-read-your-compliance-score"></a>Come leggere il punteggio di conformità

Nel dashboard di Compliance Manager viene visualizzato il punteggio di conformità complessivo. Questo punteggio misura lo stato di avanzamento nel completamento delle azioni di miglioramento consigliate all'interno dei controlli. Il punteggio può aiutarti a comprendere la tua attuale posizione di conformità. Può anche aiutare a definire le priorità delle azioni in base al loro potenziale per ridurre i rischi.

Un valore di punteggio viene assegnato a tre livelli:

1. **Punteggio dell'azione di** miglioramento: ogni azione ha un impatto diverso sul punteggio a seconda del potenziale rischio coinvolto

2. **Punteggio di** controllo: questo punteggio è la somma dei punti ottenuti completando le azioni di miglioramento all'interno del controllo. Questa somma viene applicata per intero al punteggio di conformità complessivo quando il controllo soddisfa entrambe le condizioni seguenti:
    - **Lo stato di** implementazione **è uguale a Implementazione** **implementata o Implementazione** alternativa e
    - **Risultato test** uguale a **Superato.**

3. **Punteggio di valutazione:** questo punteggio è la somma dei punteggi di controllo. Viene calcolato utilizzando i punteggi delle azioni. Ogni azione Microsoft e ogni azione di miglioramento gestita dall'organizzazione viene conteggiata una sola volta, indipendentemente dalla frequenza con cui viene fatto riferimento in un controllo.

Il punteggio di conformità complessivo viene calcolato usando i punteggi delle azioni, in cui ogni azione Microsoft viene conteggiata una sola volta, ogni azione tecnica che gestisci viene conteggiata una sola volta e ogni azione non tecnica che gestisci viene conteggiata una volta per gruppo. Questa logica è progettata per fornire la contabilità più precisa di come le azioni vengono implementate e testate nell'organizzazione. Si potrebbe notare che ciò può causare un punteggio di conformità complessivo diverso dalla media dei punteggi di valutazione. Altre informazioni di seguito sul [punteggio delle azioni.](#action-types-and-points)

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Punteggio iniziale basato sulla linea di base di protezione dei dati di Microsoft 365
  
Compliance Manager fornisce un punteggio iniziale basato sulla linea di base di protezione dei dati di Microsoft 365. Questa linea di base è un insieme di controlli che include normative e standard chiave per la protezione dei dati e la governance generale dei dati. Questa linea di base si basa principalmente su NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), nonché su FedRAMP (Federal Risk and Authorization Management Program) e GDPR (Regolamento generale sulla protezione dei dati dell'Unione Europea).

Il punteggio iniziale viene calcolato in base alla valutazione di base della protezione dei dati predefinita fornita a tutte le organizzazioni. Al primo passaggio, Compliance Manager sta già raccogliendo segnali dalle soluzioni di Microsoft 365. Vedrai a colpo d'occhio le prestazioni dell'organizzazione in relazione agli standard e alle normative di protezione dei dati chiave e vedrai le azioni di miglioramento suggerite da intraprendere.

Poiché ogni organizzazione ha esigenze specifiche, Compliance Manager si basa sull'utente per configurare e gestire le valutazioni per ridurre al minimo e ridurre al minimo i rischi nel modo più completo possibile.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Valutazione continua dei controlli da parte di Compliance Manager

Compliance Manager analizza automaticamente l'ambiente Microsoft 365 e rileva le impostazioni di sistema, aggiornando continuamente e automaticamente lo stato delle azioni tecniche. Microsoft Secure Score è il motore sottostante che esegue il monitoraggio.

Lo stato dell'azione viene aggiornato nel dashboard ogni 24 ore. Dopo aver seguito un consiglio per implementare un controllo, lo stato del controllo viene in genere aggiornato il giorno successivo.

Ad esempio, se si attiva l'autenticazione a più fattori (MFA) nel portale di Azure AD, Compliance Manager rileva l'impostazione e la riflette nei dettagli della soluzione di accesso di controllo. Al contrario, se non è stata attivata l'autenticazione a più fattori, Compliance Manager contrassegna tale azione come azione consigliata da eseguire.

Ulteriori informazioni [su Secure Score e sul suo funzionamento.](../security/mtp/microsoft-secure-score-new.md)
  
## <a name="action-types-and-points"></a>Tipi di azione e punti

Compliance Manager tiene traccia di due tipi di azioni:

1. **Azioni di miglioramento:** azioni gestite dall'organizzazione.
2. **Azioni Microsoft:** azioni gestite da Microsoft.

Entrambi i tipi di azioni hanno punti che contano verso il punteggio complessivo al termine.

### <a name="technical-and-non-technical-actions"></a>Azioni tecniche e non tecniche

Le azioni sono raggruppate in base alla natura tecnica o non tecnica. L'impatto del punteggio di ogni azione varia in base al tipo.

- **Le azioni** tecniche vengono implementate interagendo con la tecnologia di una soluzione ( ad esempio, la modifica di una configurazione). I punti per le azioni tecniche vengono concessi una volta per azione, indipendentemente dal numero di gruppi a cui appartiene.

- **Le azioni non tecniche** vengono gestite dall'organizzazione e implementate in modi diversi dall'utilizzo della tecnologia di una soluzione. Esistono due tipi di azioni non tecniche: **documentazione** e **operatività.** I punti per queste azioni vengono applicati al punteggio di conformità a livello di gruppo. Ciò significa che se un'azione esiste in più gruppi, riceverai il valore in punti dell'azione ogni volta che la implementi all'interno di un gruppo.

**Esempio di punteggio delle azioni tecniche e non tecniche:**

Supponiamo che tu abbia un'azione tecnica che vale 3 punti che esiste in 5 gruppi e che tu abbia un'azione non tecnica che vale 3 punti che esiste negli stessi 5 gruppi.

Se si implementa correttamente l'azione tecnica, il numero totale di punti ricevuti è 3. Questo perché è necessario implementare l'azione una sola volta per il tenant. Lo stato di implementazione e test per l'azione tecnica sarà lo stesso in tutte le istanze di tale azione, in ogni gruppo a cui appartiene.

Se si implementa correttamente l'azione non tecnica in ognuno dei 5 gruppi, il numero totale di punti ricevuti è 15. Questo perché è necessario implementare l'azione in ogni gruppo. Lo stato di implementazione e test per l'azione non tecnica sarà diverso tra i gruppi perché l'azione viene implementata separatamente all'interno di ogni gruppo.

Questa logica di punteggio è progettata per fornire la contabilità più precisa di come le azioni vengono implementate e testate nell'organizzazione.

### <a name="how-score-values-are-determined"></a>Come vengono determinati i valori del punteggio
 
Alle azioni viene assegnato un valore di punteggio in base al fatto che siano obbligatorie o discrezionali e che siano preventive, investigative o correttive.

### <a name="mandatory-and-discretionary-actions"></a>Azioni obbligatorie e discrezionali

 - **Le azioni** obbligatorie non possono essere ignorate, intenzionalmente o accidentalmente. Un esempio di azione obbligatoria è un criterio password gestito centralmente che imposta i requisiti per la lunghezza, la complessità e la scadenza delle password. Gli utenti devono attenersi a questi requisiti per accedere al sistema.
  
 - **Le azioni discrezionali** si basano sugli utenti per comprendere e rispettare un criterio. Ad esempio, un criterio che richiede agli utenti di bloccare il computer quando lasciano il computer è un'azione discrezionale perché si basa sull'utente.
  
### <a name="preventative-detective-and-corrective-actions"></a>Azioni preventive, investigative e correttive
  
 - **Le azioni preventive affrontano** rischi specifici. Ad esempio, la protezione delle informazioni in stato di inquieto utilizzando la crittografia è un'azione preventiva contro attacchi e violazioni. La separazione dei compiti è un'azione preventiva per gestire il conflitto di interessi e proteggersi dalle frodi.
  
 - **Le azioni investigative** monitorano attivamente i sistemi per identificare condizioni o comportamenti irregolari che rappresentano rischi o che possono essere utilizzati per rilevare intrusioni o violazioni. Ad esempio, il controllo dell'accesso al sistema e le azioni amministrative privilegiate. I controlli di conformità alle normative sono un tipo di azione investigativa usata per individuare i problemi di processo.
  
- **Le azioni correttive** cercano di limitare al minimo gli effetti negativi di un incidente di sicurezza, di intraprendere azioni correttive per ridurre l'effetto immediato e di annullare il danno, se possibile. La risposta agli incidenti di privacy è un'azione correttiva per limitare i danni e ripristinare i sistemi a uno stato operativo dopo una violazione.
  
Ogni azione ha un valore assegnato in Compliance Manager in base al rischio che rappresenta:

|**Type**|**Punteggio assegnato**|
|:-----|:-----|
| Preventivo obbligatorio | 27 |
| Discrezionale preventivo | 9  |
| Detective obbligatorio | 3  |
| Investigativo a discrezione dell'utente | 1  |
| Correzione obbligatoria | 3  |
| Discrezionale correttivo | 1  |
  
![Valori dei punti azione di Compliance Manager](../media/compliance-score-action-scoring.png "Valori dei punti azione di Compliance Manager")