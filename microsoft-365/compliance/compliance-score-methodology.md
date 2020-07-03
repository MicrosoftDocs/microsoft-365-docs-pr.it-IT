---
title: Calcolo del Punteggio di conformità Microsoft (anteprima)
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024676"
---
# <a name="compliance-score-preview-calculation"></a>Calcolo del Punteggio di conformità (anteprima)

> [!IMPORTANT]
> I consigli di Compliance Manager e Punteggio di conformità non devono essere interpretati come una garanzia di conformità. Spetta a te valutare e convalidare l'efficacia dei controlli del cliente per il tuo ambiente normativo. Questi servizi sono attualmente in anteprima e sono soggetti ai termini e alle condizioni nelle condizioni dei [servizi online](https://go.microsoft.com/fwlink/?linkid=2108910). Vedere anche [linee guida per la gestione delle licenze di Microsoft 365 per sicurezza e conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-compliance-score-works"></a>Funzionamento del Punteggio di conformità

Il dashboard del Punteggio di conformità Visualizza un punteggio che misura lo stato di avanzamento del completamento delle azioni di miglioramento all'interno dei controlli. Ogni azione ha un impatto diverso sul punteggio, a seconda dei possibili rischi coinvolti. Il Punteggio può contribuire a definire la priorità su quale azione concentrarsi per migliorare la posizione di conformità generale.

I valori di Punteggio di conformità visualizzati per il controllo vengono applicati *integralmente* al punteggio totale su una base di pass/fail. Il controllo viene implementato e passa il test di valutazione successivo oppure no. 

I punti vengono aggiunti al Punteggio di conformità quando il controllo è:

- **Lo stato di implementazione** è uguale a **implementato** o all' **implementazione alternativa**e
- **Risultato del test** uguale a **superato**.

Un punteggio di controllo è la somma dei punti ottenuti adottando azioni di miglioramento. La somma dei punteggi di controllo è il Punteggio di valutazione. **La somma dei punteggi di valutazione è il Punteggio di conformità globale.**

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365
  
Punteggio di conformità fornisce un punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365. Questa linea di base è un insieme di controlli che include le normative fondamentali e gli standard per la protezione dei dati e la governance dei dati generale. Questa linea di base estrae gli elementi principalmente dal NIST CSF (Istituto nazionale per gli standard e la tecnologia Cybersecurity Framework) e ISO (International Organization for Standardizzation), oltre che da FedRAMP (Federal Risk and Authorization Management Program) e GDPR (General Data Protection Regulation dell'Unione europea).

La valutazione della linea di base per la protezione dei dati (fornita per impostazione predefinita a tutte le organizzazioni) viene utilizzata per calcolare il punteggio iniziale prima di configurare eventuali altre valutazioni. Dopo la prima visita, il Punteggio di conformità è già in grado di raccogliere segnali dalle soluzioni Microsoft 365. Verrà visualizzato a colpo d'occhio il modo in cui l'organizzazione è in esecuzione rispetto agli standard e alle normative sulla protezione dei dati e le azioni consigliate da intraprendere.

Poiché ogni organizzazione ha esigenze specifiche, il Punteggio di conformità si basa su di esso per configurare e gestire le proprie valutazioni per ridurre al minimo e ridurre il rischio nel modo più completo possibile.

## <a name="how-compliance-score-continuously-assesses-controls"></a>Come il Punteggio di conformità valuta continuamente i controlli

Il Punteggio di conformità analizza automaticamente l'ambiente Microsoft 365 e rileva le impostazioni di sistema, aggiornando continuamente e automaticamente lo stato del controllo tecnico. Secure Score è il motore sottostante che esegue il monitoraggio.

Lo stato del controllo viene aggiornato sul dashboard del Punteggio di conformità ogni 24 ore. Dopo aver seguito una raccomandazione per implementare un controllo, viene visualizzato lo stato del controllo aggiornato il giorno successivo.

Ad esempio, se si attiva l'autenticazione a più fattori nel portale di Azure AD, il Punteggio di conformità rileva l'impostazione e riflette quella nei dettagli della soluzione di Access Control. Viceversa, se non si è attivato l'AMF, il Punteggio di conformità contrassegna come azione consigliata da eseguire.

Durante l'anteprima pubblica, la valutazione continua è disponibile per una parte dei controlli, ma non per tutti.

#### <a name="learn-more"></a>Altre informazioni
[Leggere informazioni sul punteggio sicuro e sul suo funzionamento](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Tipi di azione e punti

Il Punteggio di conformità tiene traccia di due tipi di azioni: le azioni gestite e le azioni che Microsoft gestisce. Entrambi i tipi di azioni hanno punti che contano verso il Punteggio globale quando sono stati completati:

1. **I punti** contribuiscono al Punteggio di conformità basato sui controlli gestiti dall'organizzazione.
2. **Microsoft Managed Points** contribuisce al Punteggio di conformità in base alle azioni gestite da Microsoft come provider di servizi cloud.

Alle azioni viene assegnato un valore di punteggio a seconda che sia obbligatorio o discrezionale e che si tratti di preventivo, investigativo o correttivo.

### <a name="mandatory-and-discretionary-actions"></a>Azioni obbligatorie e discrezionali

 - Le **azioni obbligatorie** non possono essere ignorate intenzionalmente o accidentalmente. Un esempio è un criterio di password gestito in modo centralizzato che consente di impostare i requisiti per la lunghezza, la complessità e la scadenza delle password. Gli utenti devono seguire questi requisiti per accedere al sistema.
  
 - Le **azioni discrezionali** fanno affidamento sugli utenti per comprendere i criteri e agire di conseguenza. Ad esempio, un criterio che richiede agli utenti di bloccare il proprio computer quando lo lasciano è un'azione discrezionale, perché si basa sull'utente.
  
### <a name="preventative-detective-and-corrective-actions"></a>Azioni preventive, investigative e correttive
  
 - Le **azioni preventive** affrontano rischi specifici. Ad esempio, la protezione delle informazioni a riposo tramite la crittografia è un'azione preventiva contro gli attacchi e le violazioni. La separazione dei compiti è un'azione preventiva per gestire i conflitti di interesse e prevenire le frodi.
  
 - Le **azioni investigative** eseguono attivamente il monitoraggio dei sistemi per identificare condizioni o comportamenti irregolari che rappresentano il rischio o che possono essere utilizzati per rilevare intrusioni o violazioni. Tra gli esempi sono inclusi il controllo dell'accesso di sistema e le azioni amministrative privilegiate. I controlli di conformità normativi sono un tipo di azione detective utilizzato per individuare i problemi del processo.
  
- Le **azioni correttive** tentano di mantenere al minimo gli effetti negativi di un incidente di sicurezza, intraprendere azioni correttive per ridurre l'effetto immediato e, se possibile, invertire i danni. La risposta agli incidenti sulla privacy è un'azione correttiva per limitare i danni e ripristinare i sistemi a uno stato operativo dopo una violazione.
  
Ogni azione ha un valore assegnato nel punteggio di conformità basato sul rischio che rappresenta:

|**Tipo**|**Punteggio assegnato**|
|:-----|:-----|
| Obbligatorio preventivo | 27 |
| Discrezionale preventiva | 9  |
| Detective obbligatorio | 3  |
| Discrezionale detective | 1  |
| Obbligatorio correttivo | 3  |
| Discrezionale correttiva | 1  |
  
![Punteggio di conformità controlla i valori dei punti](../media/compliance-score-controls-scoring.png "Punteggio di conformità controlla i valori dei punti")