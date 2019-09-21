---
title: Cercare e trovare i dati personali
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come cercare e trovare i dati personali dell'utente in Office 365.
ms.openlocfilehash: b63cf930a38feab6df815b5350d60184a6339927
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084153"
---
# <a name="search-for-and-find-personal-data"></a>Cercare e trovare i dati personali

L'RGPD definisce i dati personali in modo molto generico come qualsiasi dato relativo a una persona fisica identificata o identificabile residente nell'Unione Europea.


Articolo 4 - Definizioni

> Il termine "dati personali" si riferisce a qualsiasi informazione relativa a una persona fisica identificata o identificabile ("soggetto dei dati"); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, tramite dati specifici come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica;


In questo articolo viene illustrato come trovare i dati personali archiviati in SharePoint Online e OneDrive for Business (che include i siti per tutti i gruppi di Office 365 e Microsoft Teams).

L'individuazione dei dati personali soggetti all'RGPD si basa sull'utilizzo di tipi di informazioni riservate in Office 365. Queste definiscono il modo in cui il processo automatico riconosce tipi di informazione specifici come i numeri di previdenza sociale e di carta di credito. Al momento, tali informazioni non possono essere usate per trovare i dati nelle cassette postali di Exchange inattive. Tuttavia, i tipi di informazioni riservate possono essere usate con criteri di prevenzione della perdita dei dati per trovare dati personali nella posta elettronica in transito.

Quindi, attualmente non è possibile usare Ricerca contenuto per trovare i dati personali archiviati nelle cassette postali di Exchange Online, ma è possibile utilizzare le tipologie di informazioni sensibili definite per l'RGPD per trovare e proteggere le informazioni personali quando vengono inviate tramite posta elettronica.


## <a name="use-content-search-to-find-personal-data"></a>Usare Ricerca contenuto per trovare dati personali

Microsoft consiglia un approccio in tre fasi per la ricerca di dati personali dell'utente in Office 365. Il resto di questo argomento fornisce informazioni su ognuno di questi passaggi.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Passaggio</strong></th>
<th align="left"><strong>Descrizione</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>1. Cercare le tipologie di informazioni riservate
</p></td>
<td align="left"><p>Iniziare utilizzando tipi di informazioni riservate per trovare dati personali. Creare una query di Ricerca contenuto per ogni tipo di informazione riservata. Eseguire la query e analizzare i risultati.</p>
Se necessario, è possibile aggiungere parametri alla query per ridurre i falsi positivi: <li>Numero istanze</li>
    <li>Intervallo di confidenza</li>
    <li>Altre proprietà od operatori per query più complesse
</li>
<p>Se necessario, modificare una tipologia di informazione sensibile per ottenere risultati più accurati:
</p>
<p><li>Modificare il livello di confidenza direttamente nel file XML.
</li></p>
<p><li>Aggiungere parole chiave.</li></p>
<p><li>Modificare i requisiti di prossimità delle parole chiave.</li></p></td>
</tr>
<tr class="even">
<td align="left"><p>2. Usare Keyword Query Language (KQL) per trovare ulteriori dati personali nell'ambiente</p></td>
<td align="left"><p>Per trovare i dati non inclusi nei tipi di informazioni riservate, usare il linguaggio di query KQL per lo sviluppo di query personalizzate.</p>
<p>Verificare i risultati di queste ricerche e modificare la stringa di query KQL fino a ottenere il risultato previsto.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3. Creare nuovi tipi di informazioni riservate personalizzati con le query KQL</p></td>
<td align="left">Dopo l'ottimizzazione delle query KQL per trovare i dati di destinazione, è possibile creare nuovi tipi di informazioni riservate personalizzati con queste query. Quindi, è possibile usare questi tipi di informazioni riservate personalizzati con Ricerca contenuto, nei criteri DLP e con altri strumenti e in altre query KQL.</td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a>Cercare le tipologie di informazioni sensibili con Ricerca contenuto


Avviare la ricerca dei dati personali usando i tipi di informazioni riservate incluse in Office 365. Questi sono elencati sotto Classificazioni nel Centro sicurezza e conformità.

Questo argomento include un elenco di alcuni tipi di informazioni riservate che si applicano ai cittadini dell'Unione Europea. Controllare il Centro sicurezza e conformità per le nuove aggiunte che semplificano la conformità all’RGDP.

Vedere anche l'articolo: [Elenco dei tipi di informazioni riservate e l'aspetto di ognuno di essi](https://support.office.com/it-IT/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).

Le tipologie di informazioni sensibili permettono di riconoscere in modo automatico informazioni specifiche come i numeri di previdenza sociale e di carta di credito. Le tipologie di informazioni sensibili sono chiamate anche condizioni. Una tipologia di informazioni sensibili corrisponde a un modello identificato da un'espressione regolare o da una funzione. Inoltre, è possibile utilizzare altri elementi come parole chiave e checksum per identificare una tipologia di informazioni sensibili. In questa procedura di valutazione vengono usati anche il livello di confidenza e la prossimità.


Attualmente le tipologie di informazioni sensibili non sono utilizzabili per trovare i dati conservati nelle cassette postali.


### <a name="using-content-search-with-sensitive-information-types"></a>Utilizzo di Ricerca contenuto con le tipologie di informazioni sensibili


<table>
<thead>
<tr class="header">
<th align="left"><strong>Passaggio</strong></th>
<th align="left"><strong>Ulteriori informazioni</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p>Andare a Ricerca contenuto nel Centro sicurezza e conformità</p></td>
<td align="left"><p>Nel riquadro a sinistra del Centro sicurezza e conformità, fare clic su **Ricerca e analisi** &gt; **Ricerca contenuto**.</p>
<p>Vedere <a href="https://support.office.com/it-IT/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Eseguire Ricerca contenuto nel Centro sicurezza e conformità di Office 365</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Creare un nuovo elemento di ricerca per ogni tipo di informazioni riservate</p></td>
<td align="left"><p>Utilizzare la sintassi seguente:</p>
<blockquote>
<p>SensitiveType:"&lt;tipologia&gt;"
</p>
</blockquote>
<p>Ad esempio:</p>
<blockquote>
<p>SensitiveType:&quot;Numero di passaporto francese&quot;</p>
</blockquote>
<p>Definire l'ambito di ricerca per SharePoint (include OneDrive for Business). Verificare che la sintassi sia esatta e non siano presenti spazi o errori di digitazione.</p>
<p>Vedere <a href="https://support.office.com/it-IT/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Creare una query per individuare dati riservati memorizzati nei siti</a>.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Esaminare i risultati per ogni ricerca</p></td>
<td align="left"><p>Cercare i tipi di problemi per determinare se la precisione della query viene rispettata:</p>
<p><li>Molti falsi positivi</li></p>
<p><li>Mancano istanze note dei dati
</li></p>
<p>Vedere <a href="https://support.office.com/it-IT/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Esportare i risultati di Ricerca contenuto dal Centro sicurezza e conformità di Office 365</a>.</p>
<p>Nota: se si utilizza Mozilla Firefox o Chrome, è necessario prima scaricare i report utilizzando Internet Explorer o Edge per installare il componente aggiuntivo necessario.</p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a>Tipi di informazioni riservate per i dati dei cittadini dell'Unione europea

Iniziare con queste tipologie di informazioni sensibili. Molte altre tipologie saranno presto disponibili per i dati personali nei paesi dell'Unione europea.


> Belgio - Numero nazionale
>
> Numero di carta di credito
>
> Numero di carta di identità della Croazia
>
> Numero di identificazione personale (OIB) - Croazia
>
> Numero carta d’identità (Repubblica Ceca)
>
> Codice PIN - Danimarca
>
> Unione Europea - Numero di carta di debito
>
> Finland National ID
>
> Finlandia - Numero di passaporto
>
> Francia - Numero della patente di guida
>
> Francia - Carta d'identità nazionale (CNI)
>
> Francia - Numero di passaporto
>
> Francia - Numero di previdenza sociale (INSEE)
>
> Germania - Numero della patente di guida
>
> Germania - Numero carta di identità
>
> Germania - Numero di passaporto
>
> Carta d'identità (Grecia)
>
> Numero di conto bancario internazionale (IBAN)
>
> Indirizzo IP
>
> Irlanda - Numero personale di servizio pubblico (PPS)
>
> Italia - Numero della patente di guida
>
> Paesi Bassi - Numero di servizio cittadino (BSN)
>
> Norvegia - Numero di identificazione
>
> Carta di identità - Polonia
>
> ID nazionale Polonia (PESEL)
>
> Passaporto Polonia
>
> Portogallo - Numero di carta del cittadino
>
> Spagna - Numero di previdenza sociale (SSN)
>
> Svezia - Identificativo nazionale
>
> Svezia - Numero di passaporto
>
> Regno Unito - Numero della patente di guida
>
> Regno Unito - Numero di iscrizione alle liste elettorali
>
> Regno Unito - Codice del servizio sanitario nazionale
>
> Regno Unito - Numero di assicurazione nazionale (NINO)
>
> Stati Uniti/Regno Unito - Numero di passaporto

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a>Aggiungere parametri a una query di un tipo di informazione riservata per perfezionare i risultati

È possibile aggiungere i parametri a una query di un tipo di informazioni riservate:

-   Numero istanze - Consente di definire il numero di occorrenze di informazioni riservato che un documento deve contenere prima di essere incluso nei risultati della query.

-   Intervallo di confidenza - Indica il livello di confidenza secondo il quale la tipologia di informazione sensibile identificata rappresenta effettivamente una corrispondenza, ad esempio 85 (85%).


Sintassi:

-   SensitiveType:”\<tipologia\>|\<numero istanze\>|\<intervallo confidenza\>”


Esempi:

-   SensitiveType:“Credit Card Number|5” (restituisce soltanto i documenti che contengono esattamente cinque numeri di carta di credito)

-   SensitiveType:“Credit Card Number|\*|85..” (l'intervallo di confidenza è pari almeno all'85%)

Nota: "SensitiveType" distingue tra maiuscole e minuscole, il resto della query no.

È inoltre possibile usare le proprietà e gli operatori per illustrare il modo in cui è possibile perfezionare le query. Per ulteriori informazioni ed esempi, vedere [Creare una query per trovare i dati riservati archiviati nei siti](https://support.office.com/it-IT/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).
