---
title: Regolamento generale sulla protezione dei dati
description: Documentazione tecnica di Microsoft per il Regolamento generale sulla protezione dei dati (GDPR)
keywords: Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: d64d9b98fe3cf24a14b3f3126ff3f38b1d84087d
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2020
ms.locfileid: "41557983"
---
# <a name="general-data-protection-regulation-summary"></a>Riepilogo del Regolamento generale sulla protezione dei dati

Il Regolamento generale sulla protezione dei dati (GDPR) introduce nuove regole per le organizzazioni che offrono beni e servizi alle persone che risiedono nell'Unione europea (UE) o che raccolgono e analizzano i dati dei residenti nell'UE in qualunque luogo si trovi l'utente o la sua azienda.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrOQI] 

Questo documento illustra le informazioni che consentono di rispettare i diritti e adempiere agli obblighi in conformità al GDPR quando si usano i prodotti e i servizi Microsoft. Un [piano d'azione consigliato per il GDPR](gdpr-action-plan.md) e gli [elenchi di controllo di preparazione della conformità](gdpr-arc.md) forniscono ulteriori risorse per la valutazione e l'implementazione della conformità al GDPR.

## <a name="terminology"></a>Terminologia

Definizioni utili per i termini relativi al GDPR usati nel documento:

- *Titolare del trattamento dei dati (titolare)*: una persona giuridica, un'autorità pubblica, un'agenzia o un altro organismo che, da solo o congiuntamente con altri, determina le finalità e le modalità di trattamento dei dati personali.  
- *Dati personali* e *interessato*: qualsiasi informazione relativa a una persona fisica identificata o identificabile (interessato); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente.  
- *Responsabile*: una persona fisica o giuridica, un'autorità pubblica o un altro ente che si occupa del trattamento dei dati personali per conto del titolare.  
- *Dati dei clienti*: dati prodotti e archiviati relativi alle attività quotidiane di gestione della propria attività.

## <a name="what-is-the-gdpr"></a>Che cos'è il GDPR?

Il GDPR concede alle persone il diritto di gestire i dati personali raccolti da un'organizzazione. Tali diritti possono essere esercitati tramite una richiesta dell'interessato (DSR). L'organizzazione è tenuta a fornire informazioni tempestive relative alle richieste dell'interessato e alle violazioni dei dati e a eseguire valutazioni d'impatto sulla protezione dei dati (DPIA).

In caso di implementazione o valutazione dei requisiti del GDPR, è necessario tenere presente diverse considerazioni.

- Sviluppo e valutazione dell'informativa sulla privacy relativa ai dati in conformità al GDPR.
- Valutazione della sicurezza dei dati dell'organizzazione.
- Chi è il titolare del trattamento dei dati?
- Quali processi per la sicurezza dei dati potrebbe essere necessario eseguire?

Il [piano d'azione consigliato per il GDPR](gdpr-action-plan.md) e gli [elenchi di controllo di preparazione della conformità](gdpr-arc.md) potrebbero richiedere la considerazione di ulteriori fattori.

Le attività seguenti sono previste per soddisfare gli standard del GDPR. Per i dettagli relativi all'implementazione, seguire i collegamenti nell'elenco.  

- **[Richieste dell'interessato (DSR)](gdpr-data-subject-requests.md)**. Una richiesta formale da un interessato a un titolare di agire (modificare, limitare, accedere) sui dati personali.
- **[Notifica di violazione](gdpr-breach-notification.md)**. Secondo il GDPR, una violazione dei dati personali è "una violazione di sicurezza che comporta accidentalmente o in modo illecito la distruzione, la perdita, la modifica, la divulgazione non autorizzata o l'accesso ai dati personali trasmessi, conservati o comunque trattati".
- **[Valutazione dell'impatto sulla protezione dei dati (DPIA)](gdpr-data-protection-impact-assessments.md)**. Il GDPR richiede che i titolari del trattamento sui dati preparino una valutazione dell'impatto sulla protezione dei dati (DPIA) per le operazioni relative ai dati che "potrebbero comportare un rischio elevato per i diritti e le libertà delle persone fisiche".

Come già accennato, il piano d'azione consigliato per il GDPR e gli elenchi di controllo di preparazione della conformità forniscono una guida all'implementazione o alla valutazione della conformità al GDPR quando si usano i prodotti e i servizi Microsoft.

## <a name="the-gdpr-in-action"></a>Applicazione del GDPR

Questa sezione fornisce descrizioni e considerazioni relative al completamento delle attività relative al GDPR menzionate sopra. Il completamento di tali attività potrebbe variare in base alla configurazione di Microsoft.

### <a name="data-subject-request-dsr"></a>Richiesta dell'interessato (DSR)

Le richieste dell'interessato forniscono un mezzo per gli interessati per esercitare i propri diritti secondo il GDPR. Il titolare ha la responsabilità di rispondere tempestivamente in conformità al GDPR. Di seguito sono riportate eventuali domande da tenere in considerazione. Per i dettagli tecnici, fare riferimento a [Richieste dell'interessato](gdpr-data-subject-requests.md).  

- **Quali azioni sono necessarie per il completamento di una richiesta dell'interessato?** Le richieste dell'interessato implicano sei attività, ovvero individuazione, accesso, rettifica, limitazione, esportazione ed eliminazione.
- **Quali sono le origini dati?** Una considerevole quantità dei dati dell'organizzazione viene generata da [applicazioni di Office](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) come Excel e Outlook. È inoltre possibile trovare i dati rilevanti per una richiesta dell'interessato nelle [informazioni approfondite](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) generate dai prodotti e servizi Microsoft e [dai log generati dal sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs).
- **Quali tipi di dati è necessario cercare?** È possibile trovare i dati personali nei dati dei clienti, nelle informazioni approfondite generate dai prodotti e dai servizi Microsoft e nei log generati dal sistema.
- **In che modo è possibile cercare i dati personali?** La ricerca dei dati personali potrebbe variare in base ai prodotti e ai servizi Microsoft. Gli strumenti di ricerca includono [Ricerca contenuto](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) o la funzionalità di [ricerca in-app](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs). Gli amministratori possono accedere ai [log generati dal sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs) associati all'attività di un utente.  
- **In che formato dovrebbero essere resi disponibili i dati personali?** Il "diritto alla portabilità dei dati" del GDPR consente all'interessato di richiedere una copia dei dati personali in un "formato leggibile su computer, di uso comune e strutturato" e di richiedere che l'organizzazione trasmetta questi file a un altro titolare del trattamento dei dati.

### <a name="data-protection-impact-assessment"></a>Valutazione dell'impatto sulla protezione dei dati

Il GDPR richiede che i titolari preparino una [valutazione dell'impatto sulla protezione dei dati ](gdpr-data-protection-impact-assessments.md) (DPIA) per l'esecuzione di operazioni che "potrebbero comportare un rischio elevato per i diritti e le libertà delle persone fisiche". Non c'è nulla di insito ai prodotti e servizi Microsoft che richieda la creazione di una DPIA. Al contrario, dipende dai dettagli della configurazione di Microsoft.

Di seguito sono riportate alcune considerazioni relative alla DPIA. È possibile trovare un elenco di dettagli da tenere in considerazione per Office in [Contenuto di una DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia).

- Quali attività dell'organizzazione relative ai dati potrebbero compromettere la sicurezza dei dati personali?
- La configurazione dei prodotti e dei servizi Microsoft potrebbe risultare vulnerabile alle violazioni dei dati?
- Quando dovrebbe essere eseguita una DPIA?

    - I titolari devono eseguire una DPIA per rispondere ai rischi relativi alla sicurezza dei dati personali o in seguito a una violazione dei dati. Esempi specifici di fattori di rischio di Office sono trattati in [Determinare se è necessaria una DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed).  

- Cosa è necessario per completare una DPIA?

    Secondo il GDPR, una DPIA deve includere quanto segue:  
    - Una valutazione della necessità e proporzionalità dell'elaborazione dei dati in relazione agli scopi della DPIA.
    - Una valutazione dei rischi per i diritti e le libertà dell'interessato.
    - Misure previste per risolvere i rischi, garanzie, misure di sicurezza e meccanismi per garantire la protezione dei dati personali e dimostrare la conformità al GDPR.

### <a name="breach-notification"></a>Notifica di violazione

In qualità di responsabile del trattamento dei dati, Microsoft assicura che i clienti riescano a soddisfare i requisiti di notifica della violazione del GDPR. I titolari del trattamento dei dati sono responsabili della valutazione dei rischi per la privacy di tali dati e della scelta se una violazione richiede la notifica relativa alla Legge sulla protezione dei dati del cliente. Microsoft fornisce le informazioni necessarie per eseguire tale valutazione. Per ulteriori informazioni su come Microsoft rileva e gestisce un caso di violazione dei dati personali, vedere [Notifica di violazione dei dati secondo il GDPR](gdpr-breach-notification.md). Alcune domande relative alla notifica di una violazione sono:

- Quali informazioni relative a una violazione dovrebbero essere comunicate agli interessati?
- Come è possibile contattare gli interessati (e-mail, notifica scritta ecc.)?

### <a name="accountability-readiness-checklists-for-the-gdpr"></a>Elenchi di controllo di preparazione della conformità al GDPR

Questi [elenchi di controllo](gdpr-arc.md) offrono un modo pratico per accedere alle informazioni necessarie per l'applicazione del GDPR quando si usano i prodotti Microsoft. È possibile gestire gli elementi di questo elenco di controllo con il [punteggio di conformità Microsoft](compliance-score.md) usando il codice e il nome dei controlli nel riquadro del GDPR che comprende i controlli gestiti dai clienti.

## <a name="learn-more"></a>Altre informazioni

- [Centro protezione Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
