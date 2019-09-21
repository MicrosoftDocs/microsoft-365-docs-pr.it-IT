---
title: Progettare uno schema di classificazione per i dati personali
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Determinare se l'organizzazione implementerà etichette nell'ambito del piano RGPD.
ms.openlocfilehash: c0886ac68cd2d7a6ca7514f39636e74c5b2043ad
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083318"
---
# <a name="architect-a-classification-schema-for-personal-data"></a>Progettare uno schema di classificazione per i dati personali

I precedenti articoli di questa serie si focalizzano sull'uso dei tipi di informazioni riservate per identificare i dati personali soggetti all'RGPD. I tipi di informazioni riservate sono una forma di classificazione. Potrebbero rappresentare tutta la classificazione necessaria all'utente. Tuttavia, molte organizzazioni implementano una strategia di governance dei dati più ampia mediante le etichette. Consultare questo argomento per decidere se si desidera implementare anche le etichette nell'ambito del piano RGPD. Se sì, in questo argomento sono disponibili informazioni dettagliate ed esempi.

Nota: definire uno schema di classificazione per un'organizzazione e configurare criteri, etichette e condizioni richiede una pianificazione attenta. È importante comprendere che non si tratta di una procedura IT. Accertarsi di collaborare con il proprio team legale e della conformità per sviluppare una classificazione e uno schema di etichette appropriati per i dati della propria organizzazione.

## <a name="decide-if-you-are-using-labels-in-addition-to-sensitive-data-types"></a>Decidere se utilizzare le etichette oltre ai tipi di dati riservati

È possibile adottare uno dei due approcci di classificazione in Office 365 per le informazioni personali. Ciascuno di essi può essere utilizzato per la protezione RGPD. Se si decide di usare solo i tipi di informazioni riservate per la classificazione, è possibile ignorare il resto di questo argomento.

Scegliere una delle seguenti opzioni:

### <a name="option-1-use-only-office-365-sensitive-information-types"></a>Opzione 1: usare solo tipi di informazioni riservate di Office 365

-   I tipi di informazioni riservate sono utili per identificare e proteggere i dati personali soggetti a RGPD e altri tipi di normative.

-   Sono più facili da usare se l'organizzazione non dispone o non intende implementare un piano di governance dei dati più ampio con le etichette.

-   Funzionano con le regole DLP (come le etichette di conservazione).

-   I tipi di informazioni sensibili sono compatibili con Cloud App Security per consentire agli utenti di rilevare le informazioni riservate in altre app SaaS.

### <a name="option-2-use-sensitive-information-types--retention-labels"></a>Opzione 2: usare tipi di informazioni sensibili + etichette di conservazione

-   I tipi di informazioni sensibili devono applicare automaticamente le etichette ai dati personali soggetti a GDPR, quindi rappresentano un prerequisito.

-   L'uso delle etichette di conservazione consente di includere dati personali soggetti a GDPR in un piano di governance dei dati più ampio per l'organizzazione.



## <a name="develop-a-label-schema-that-includes-personal-data"></a>Sviluppare uno schema di etichette che include dati personali

Prima di utilizzare funzioni tecniche per applicare etichette e protezione, è opportuno esaminare l'organizzazione per definire uno schema di classificazione. L'organizzazione dovrebbe già avere uno schema di classificazione che semplifica l'aggiunta di dati personali. Questo argomento include uno schema di classificazione di esempio. È possibile utilizzarlo come punto di partenza, se necessario.

### <a name="getting-started"></a>Introduzione

Iniziare decidendo la quantità e i nomi delle etichette da implementare. Eseguire questa operazione senza pensare alla tecnologia da usare e alla modalità di applicazione delle etichette. Applicare questo schema a livello globale nell'organizzazione, includendo i dati in locale e in altri servizi cloud.

### <a name="recommendations"></a>Consigli 

Durante la progettazione e l'implementazione di criteri, etichette e condizioni, seguire questi suggerimenti:

-   Utilizzare lo schema di classificazione esistente (se disponibile): molte organizzazioni già utilizzano la classificazione dei dati in qualche modo. Esaminare attentamente lo schema di assegnazione delle etichette esistente e, se possibile, usarlo così com'è. La scelta sarà influenzata dall'utilizzo di etichette note agli utenti finali.

-   Iniziare con criteri ed etichette predefiniti: tutte le soluzioni sono dotate di un set di criteri ed etichette predefiniti. Esaminarli attentamente nell'ambito dei requisiti aziendali e legali dell'organizzazione e scegliere di usare quelli, anziché crearne di nuovi.

-   Iniziare con poche etichette: potenzialmente non ci sono limiti alla quantità di etichette che è possibile creare. Tuttavia, un gran numero di etichette e etichette secondarie influirà in modo negativo sull'adozione. Un numero eccessivo di scelte spesso è sinonimo di nessuna scelta.

-   Utilizzare scenari e casi d'uso: identificare casi d'uso comuni all'interno dell'organizzazione e scenari derivati da RGPD per verificare se la configurazione pianificata per la classificazione e l'assegnazione di etichette è efficace.

-   Per ogni richiesta di nuova etichetta, è opportuno chiedersi: tutti gli scenari o i casi d'uso necessitano realmente di una nuova etichetta o è possibile utilizzare quelle già disponibili? Mantenere il numero di etichette al minimo migliora l'adozione.

-   Utilizzare etichette secondarie per i reparti chiave, alcuni reparti hanno esigenze specifiche che richiedono etichette specifiche. Definire queste etichette come secondarie rispetto a un'etichetta esistente e utilizzare criteri con ambito assegnati a gruppi di utenti, anziché a livello globale.

-   Prendere in considerazione i criteri con ambito, criteri destinati a sottoinsiemi di utenti che impediscono un "sovraccarico di etichette". Un criterio con ambito consente di abilitare l'assegnazione di etichette (secondarie) specifiche per ruoli o reparti solo ai dipendenti che lavorano per un determinato reparto.

-   Utilizzare nomi significativi per le etichette (si consiglia di non usare termini specifici, standard o acronimi). Provare a usare nomi familiari agli utenti finali per migliorarne l'adozione. Anziché usare etichette come PII, PCI, HIPAA, LBI, MBI e HBI, scegliere nomi quali Non aziendale, Pubblico, Generale, Riservato ed Estremamente riservato.

### <a name="example-classification-schema"></a>Schema di classificazione di esempio

<table>
<thead>
<tr class="header">
<th align="left"><strong>Nome etichetta</strong></th>
<th align="left"><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Personale</td>
<td align="left">Dati non aziendali, solo per uso personale.</td>
</tr>
<tr class="even">
<td align="left">Pubblico</td>
<td align="left">Dati aziendali appositamente preparati e approvati per l'utilizzo pubblico.</td>
</tr>
<tr class="odd">
<td align="left">Dati della società</td>
<td align="left">Dati aziendali contenenti informazioni di identificazione personale (ad esempio; numeri di carte di credito, numeri di conto corrente e numeri di previdenza sociale).</td>
</tr>
<tr class="even">
<td align="left">Dati sulle risorse umane</td>
<td align="left">Dati sulle risorse umane sui dipendenti di Contoso, come i dati sulle retribuzioni e sul numero di dipendenti.</td>
</tr>
<tr class="odd">
<td align="left">Riservato</td>
<td align="left">Dati aziendali riservati che potrebbero causare danni all'azienda qualora fossero condivisi con persone non autorizzate (ad esempio: contratti, report sulla sicurezza, riepilogo delle previsioni e dati sul conto vendite).</td>
</tr>
<tr class="even">
<td align="left">Estremamente riservato</td>
<td align="left">Dati aziendali estremamente riservati che potrebbero causare danni all'azienda qualora fossero condivisi con persone non autorizzate (ad esempio: informazioni su clienti e dipendenti, password, codice sorgente e report finanziari pre-annunciati.</td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a>Definire una tassonomia e criteri di ricerca per ogni etichetta

Dopo aver sviluppato uno schema di classificazione per l'organizzazione, il passaggio successivo consiste nello sviluppo della tassonomia e dei criteri di ricerca per trovare tali dati. Per i dati personali, questa operazione è già stata completata identificando i tipi di informazioni riservate e personalizzando o creando nuovi tipi di informazioni riservate per l'ambiente.

La tabella seguente fornisce un esempio di schema, tassonomia e criteri di ricerca per un'organizzazione. Le etichette sono ordinate per livello di gravità dalla meno riservata alla più riservata per garantire che ai dati che corrispondono a più condizioni vengano assegnate le etichette corrette.

Nota: l'esempio di configurazione viene fornito a scopo puramente illustrativo e non è da considerare come una guida o una risorsa di riferimento.

Il punto importante è accertarsi che il lavoro investito nel classificare i dati personali per la conformità all'RGPD sia adatto agli obiettivi dell'intera organizzazione.

### <a name="example-schema-taxonomy-and-search-criteria"></a>Esempio di schema, tassonomia e criteri di ricerca

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etichetta</strong></th>
<th align="left"><strong>Tassonomia</strong></th>
<th align="left"><strong>Metodo</strong></th>
<th align="left"><strong>Sintassi di ricerca</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Personale</td>
<td align="left">Documenti personali etichettati manualmente dall'utente finale.</td>
<td align="left">Manuale</td>
<td align="left">Documenti personali etichettati manualmente dall'utente finale.</td>
</tr>
<tr class="even">
<td align="left">Pubblico</td>
<td align="left">Documenti contenenti la frase Approvato per la pubblicazione ##/#### (senza distinzione tra maiuscole/minuscole), dove # rappresenta qualsiasi cifra.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Approvato per la pubblicazione*</p>
<p>RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Dati cliente
</td>
<td align="left">Tipi di informazioni riservate per i dati dei cittadini dell'Unione europea.</td>
<td align="left">Tipi di informazioni riservate</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Risorse umane - Dati dipendenti</td>
<td align="left">Documenti che includono l'id dipendente (con distinzione tra maiuscole/minuscole) nel formato CONTOSO-9#####, dove # rappresenta qualsiasi cifra.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — CONTOSO-9*</p>
<p>RegEx — (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Risorse umane - Dati sugli stipendi</td>
<td align="left">Documenti che includono la parola chiave (senza distinzione tra maiuscole/minuscole) Contoso AND un'altra parola chiave (senza distinzione tra maiuscole/minuscole), Stipendio OR Retribuzione</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso AND (Stipendio OR Retribuzione)</p>
<p>RegEx — (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="even">
<td align="left">Riservato</td>
<td align="left">Documenti contenenti la frase (senza distinzione tra maiuscole/minuscole) Contoso - Riservato.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso - Riservato</p>
<p>RegEx — (?i)(\bContoso - Riservato\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Estremamente riservato</td>
<td align="left">Documenti che includono la frase (con distinzione tra maiuscle/minuscole) Contoso Secret o Secret-C####, dove # rappresenta qualsiasi cifra.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso Secret OR Secret-C*</p>
<p>RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</p></td>
</tr>
</tbody>
</table>
