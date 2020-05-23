---
title: Personalizzare o creare un nuovo tipo di informazione riservata
f1.keywords:
- NOCSH
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
ms.custom: seo-marvel-apr2020
ms.assetid: ''
description: Informazioni su come modificare o creare nuovi tipi di informazioni sensibili di Office 365 per la conformità al Regolamento generale sulla protezione dei dati (GDPR).
ms.openlocfilehash: 70ce61f582cbc952811d01cccc7b958bf1b52dbb
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224633"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a>Personalizzare o creare un nuovo tipo di informazione riservata

In questo vengono forniti tre esempi che dimostrano come modificare o creare nuovi tipi di informazioni riservate per il GDPR.

- Modificare un tipo di informazione riservata esistente — Numero di carta di debito dell'Unione Europea

- Creare un nuovo tipo di informazione riservata — Indirizzo e-mail

- Creare un nuovo tipo di informazione riservata con file XML di esempio — Numero cliente Contoso

Vedere anche:

- [Creare un tipo di informazione riservata personalizzata usando PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [Personalizzare una tipologia integrata di informazioni sensibili](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a>Modificare un tipo di informazione riservata per migliorare l'accuratezza

Se si utilizza Ricerca contenuto per cercare dati personali con i tipi di informazioni riservate e non si ottengono i risultati previsti, oppure la query restituisce un numero eccessivo di falsi positivi, è possibile modificare il tipo di informazione riservata in modo che funzioni meglio con il proprio ambiente.

La procedura consigliata quando si crea o si personalizza un tipo di informazione riservata consiste nel creare un nuovo tipo di informazione riservata basato su uno esistente, attribuendogli nome e identificatore univoci. Ad esempio, se si desidera regolare i parametri del tipo di informazione riservata "Numero di carta di debito dell'Unione Europea", è possibile denominare la copia di tale regola "Numero di carta di debito dell'Unione Europea avanzato" per distinguerla dall'originale.

Nel nuovo tipo di informazione riservata, è sufficiente modificare i valori che si desidera cambiare per migliorarne l'accuratezza. Al termine dell'operazione, caricare il nuovo tipo di informazione riservata e creare una nuova regola DLP (o modificarne una esistente) per utilizzare il nuovo tipo di informazione riservata appena aggiunto. La modifica dell'accuratezza dei tipi di informazioni riservate potrebbe richiedere alcuni tentativi e comportare degli errori, quindi mantenere una copia del tipo originale ne consente il recupero per eventuali utilizzi futuri.

Per personalizzare un tipo di informazione riservata:

1.  Esportare il Pacchetto di regole Microsoft esistente di tipi di informazioni riservate integrati in Office 365.

2.  Rinominare questo file XML e aprirlo nell'editor XML preferito.

3.  Isolare il tipo di informazione riservata e rimuovere gli altri.

4.  Utilizzare PowerShell per generare due nuovi GUID per il tipo di informazione riservata da modificare.

5.  Modificare l'ID e gli altri elementi di base affinché il tipo di informazione riservata sia univoco (ciò include la sostituzione di due GUID con quelli nuovi generati).

6.  Ottimizzare i requisiti di corrispondenza per migliorare l'accuratezza.

    1.  Modifiche di prossimità: modificare la prossimità del modello di carattere per espandere o ridurre la finestra in cui è necessario trovare le parole chiave rispetto al tipo di informazione riservata.

    2.  Modifiche delle parole chiave: aggiungere parole chiave a uno degli elementi \<Keywords\> per fornire al tipo di informazione riservata un elemento avvalorante più specifico per le ricerche in modo da segnalare una corrispondenza per tale regola. In alternativa, rimuovere le parole chiave che causano falsi positivi.

    3.  Modifiche di probabilità: modificare la probabilità con cui il tipo di informazione riservata deve soddisfare i criteri specificati nella sua definizione prima che venga segnalata una corrispondenza.

7.  Caricare il nuovo tipo di informazione riservata.

8.  Rieffettuare una ricerca per indicizzazione del contenuto per identificare l'informazione riservata. Vedere [Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un sito](https://docs.microsoft.com/sharepoint/crawl-site-content).

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a>Esempio: modificare il tipo di informazione riservata "Numero di carta di debito dell'Unione Europea"

Per migliorare l'accuratezza delle regole DLP in qualsiasi sistema è necessario il test con un set di dati campione; inoltre, potrebbe essere necessaria un'ulteriore ottimizzazione attraverso ripetute modifiche e prove. In questo esempio vengono mostrate le modifiche al tipo di informazione riservata "Numero di carta di debito dell'Unione Europea" per migliorarne l'accuratezza.

Quando si cerca un numero di carta di debito dell'Unione Europea nell'esempio fornito, la definizione di tale numero è rigorosamente specificata tramite 16 cifre con uno schema complesso e soggette alla convalida di un checksum. Non è possibile alterare questo schema a causa della definizione della stringa di questo tipo di informazione riservata. Tuttavia, è possibile apportare le modifiche seguenti per migliorare l'accuratezza del modo in cui i criteri DLP rilevano questo tipo di informazione riservata in Office 365.

### <a name="proximity-modification"></a>Modifica di prossimità

Verrà ridotta la finestra modificando il valore patternProximity nell'elemento \<Entity\> da 300 a 150 caratteri. Ciò significa che l'elemento avvalorante (o le parole chiave) deve essere più vicino al tipo di informazione riservata in uso per segnalare una corrispondenza a questa regola.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

### <a name="keyword-modifications"></a>Modifica della parole chiave

Alcune parole chiave potrebbero causare la presenza di falsi positivi. Di conseguenza, è consigliabile rimuovere le parole chiave. Di seguito sono indicate le parole chiave per l'esempio:

\<Keyword id="Keyword\_card\_terms\_dict"\>

\<Group\>

\<Term\>corporate card\</Term\>

\<Term\>organization card\</Term\>

\<Term\>acct nbr\</Term\>

\<Term\>acct num\</Term\>

\<Term\>acct no\</Term\>

…

\</Group\>

\</Keyword\>

### <a name="confidence-modifications"></a>Modifiche di probabilità

Se si rimuovono parole chiave dalla definizione, è preferibile impostare la probabilità di individuare il tipo di informazione riservata riducendo questo valore. Il livello predefinito per il tipo Numero di carta di debito dell'Unione Europea è 85.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

…

\</Pattern\>

\</Entity\>

## <a name="create-a-new-custom-sensitive-information-type"></a>Creare un nuovo tipo di informazione riservata personalizzato

Per creare un nuovo tipo di informazione riservata personalizzato, iniziare con Ricerca contenuto per:

-   Ottimizzare una query KQL

-   Visualizzare le parole chiave particolarmente utili

Utilizzare questi risultati per creare un nuovo tipo di informazione riservata. Ottimizzare quindi il nuovo tipo di informazione riservata per il proprio ambiente.

Nota: molti nuovi tipi di informazioni riservate saranno presto disponibili per i dati personali nei paesi dell'Unione Europea. Se è necessario creare i nuovi tipi di informazioni riservate, iniziare assegnando i dati personalizzati al proprio ambiente.

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a>Passaggio 1: utilizzare query KQL e parole chiave per individuare dati aggiuntivi nel proprio ambiente

Potrebbe essere necessario creare query aggiuntive per trovare dati personali soggetti a GDPR. Ricerca contenuto si avvale di Keyword Query Language (KQL) per individuare i dati. I dati più riservati non possono essere rilevati in modo accurato utilizzando solo KQL senza i tipi di informazioni riservate. Pertanto, l'obiettivo consiste nel testare e ottimizzare le stringhe KQL tramite Ricerca contenuto e quindi utilizzarle per creare e ottimizzare nuovi tipi di informazioni riservate in cui è possibile ottenere un'accuratezza maggiore.

Utilizzare queste risorse per formulare e ottimizzare query tramite KQL:

- [Riferimenti per la sintassi (DMC) di Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [Eseguire una Ricerca contenuto](content-search.md)

Ricerca contenuto fornisce un'altra risorsa che consente di sviluppare query KQL e tipi di informazioni riservate: le parole chiave. Perché utilizzare l'elenco delle parole chiave? È possibile ottenere le statistiche che mostrano quanti elementi corrispondo a ciascuna parola chiave. Questo può essere utile per trovare rapidamente le parole chiave più o meno efficaci. Per ulteriori informazioni sulle statistiche di ricerca, vedere [Visualizzare statistiche delle parole chiave per i risultati di Ricerca contenuto](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).

Le parole chiave in ogni riga sono collegate dall'operatore OR nella query di ricerca creata. È inoltre possibile utilizzare una frase parola chiave (racchiusa tra parentesi) in una riga.

Per ulteriori informazioni, vedere [Query delle parole chiave e condizioni di ricerca per ricerca contenuto](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions).

### <a name="exampleusing-content-search-to-identify-email-addresses"></a>Esempio: identificare indirizzi e-mail tramite Ricerca contenuto

Gli indirizzi e-mail sono considerati informazioni riservate correlate ai soggetti dei dati. Questo è un esempio semplice che consente di mostrare come può aiutare Ricerca contenuto.

Non è possibile utilizzare KQL e parole chiave insieme. Utilizzare questi strumenti separatamente per perfezionare la query e determinare le parole chiave che potrebbero essere utili nei tipi di informazioni riservate.

### <a name="kql-query"></a>Query KQL

(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)

Note:

-   È possibile utilizzare NEAR per le ricerche di prossimità.

-   Purtroppo al momento KQL non supporta le query con la classe Regex (esempio: IdRef="Regex\_email\_address").

### <a name="keywords"></a>Parole chiave

Immettere ogni parola chiave in una riga separata. Parole chiave di esempio:

-   indirizzo di posta elettronica

-   posta elettronica

-   contatto

-   mittente

-   destinatario

-   cc

-   bcc

In questo esempio, viene mostrato che le parole chiave non sono necessarie e generano molti falsi positivi.

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a>Passaggio 2: creare un nuovo tipo di informazione riservata personalizzato

Dopo aver utilizzato le query KQL e le parole chiave per identificare informazioni riservate, usarle per creare nuovi tipi di informazioni riservate personalizzati. In molti casi, sarà necessario il perfezionamento dei tipi di informazioni riservate per ottenere il giusto livello di accuratezza. Sarà quindi possibile utilizzare questi tipi di informazioni riservate personalizzati con Ricerca contenuto, nei criteri DLP e in altri strumenti, nonché nelle query KQL.

La procedura consigliata consiste nel creare un nuovo tipo di informazione riservata basato su uno esistente. Utilizzare la stessa procedura descritta in precedenza in questo articolo.

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a>Esempio: creare un nuovo tipo di informazione riservata per gli indirizzi e-mail 

È stato scelto questo esempio per la sua semplicità. Nella seguente tabella sono riportate le modifiche consigliate per un nuovo tipo di informazione riservata relativo alla posta elettronica.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Passaggio</strong></th>
<th align="left"><strong>Modifica</strong></th>
<th align="left"><strong>Sintassi XML di esempio</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Impostare la proprietà IdRef
<p>Nell'elemento &lt;Entity&gt;, modificare l'elemento &lt;IdMatch&gt; affinché la relativa proprietà idRef sia uguale a un valore univoco. Questo valore farà riferimento a un elemento che definisce l'espressione regolare per trovare gli indirizzi e-mail.</p></td>
<td align="left">IdRef=&quot;Regex_email_address&quot;</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left"><p>Attributo di prossimità</p>
<p>Iniziare con un valore patternProximity nell'elemento &lt;Entity&gt; di 300.</p></td>
<td align="left">patternsProximity=&quot;300&quot;</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left"><p>Livello di probabilità</p>
<p>Impostare la proprietà recommendedConfidence su un valore che si pensi possa rappresentare la probabilità di trovare una corrispondenza accurata. Ciò potrebbe richiedere un tentativo con un set di dati rappresentativi per ottenere un risultato accurato. Come impostazione iniziale, impostare questo valore su 75.</p></td>
<td align="left"><p>recommendedConfidence=&quot;75&quot;&gt;</p>
<p>L'XML ottenuto per questi primi tre elementi combinati sarà simile al seguente:</p>
<p>&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</p>
<p>&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</p>
<p>&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</p>
<p>&lt;Any minMatches=&quot;1&quot;&gt;</p>
<p>&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</p>
<p>&lt;/Any&gt;</p>
<p>&lt;/Pattern&gt;</p>
<p>&lt;/Entity&gt;</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left"><p>Elemento Regex</p>
<p>Aggiungere un nuovo elemento &lt;Regex&gt; immediatamente sotto gli elementi &lt;Entity&gt; che definisce l'espressione regolare utilizzata per identificare gli indirizzi e-mail.</p></td>
<td align="left">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left"><p>Parole chiave</p>
<p>Aggiungere un nuovo elemento &lt;Keyword&gt; sotto l'elemento &lt;Regex&gt; che definisce l'elenco di indirizzi e-mail correlati alle parole chiave. Verificare che il valore id dell'elemento &lt;Keyword&gt; corrisponda al valore &lt;Match idRef&gt; nell'elemento &lt;Entity&gt;&lt;Pattern&gt;. È possibile continuare ad aggiungere le proprie parole chiave se necessario.</p>
<p>Le parole chiave non devono necessariamente essere incluse in un tipo di informazione riservata per la posta elettronica. Di seguito ne sono forniti degli esempi.</p></td>
<td align="left"><p>&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</p>
<p>&lt;Group&gt;</p>
<p>&lt;Term&gt;email&lt;/Term&gt;</p>
<p>&lt;Term&gt;email address&lt;/Term&gt;</p>
<p>&lt;Term&gt;contact&lt;/Term&gt;</p>
<p>&lt;/Group&gt;</p>
<p>&lt;/Keyword&gt;</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left"><p>Elemento LocalizedStrings</p>
<p>Nell'elemento &lt;LocalizedStrings&gt;&lt;Resource&gt; verificare di disporre di un nome univoco che identifichi il tipo di informazione riservata.</p></td>
<td align="left"><p>&lt;LocalizedStrings&gt;</p>
<p>&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</p>
<p>&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</p>
<p>&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</p>
<p>&lt;/Resource&gt;</p>
<p>&lt;/LocalizedStrings&gt;</p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a>Creare un nuovo tipo di informazione riservata con file XML e PowerShell di esempio — Numero cliente Contoso

Contoso utilizza un Numero cliente Contoso (CCN) per identificare ogni cliente nel proprio database dei clienti. Un CCN è costituito dalla seguente tassonomia:

-   Due cifre che rappresentano l'anno di creazione del record. Contoso è stata fondata nel 2002; quindi, il primo valore possibile dovrebbe essere 02.

-   Tre cifre che rappresentano l'agenzia partner che ha creato il record. I valori possibili per l'agenzia sono compresi tra 000 e 999.

-   Un carattere alfabetico che rappresenta la linea di business. I valori possibili vanno dalla a alla z, con distinzione tra maiuscole e minuscole.

-   Un numero di serie di quattro cifre. I possibili valori per il numero di serie sono compresi tra 0000 e 9999.

CCN di esempio:

> 15080P9562
>
> 14040O1119
>
> 15020J8317
>
> 14050E2330
>
> 16050E2166
>
> 17040O1118

Contoso fa sempre riferimento ai clienti utilizzando un CCN nella corrispondenza interna/esterna, nei documenti e così via. Vuole creare un tipo di informazione riservata personalizzato che rilevi l'uso di CCN per poter applicare la protezione per l'utilizzo di questo modulo di dati personali.

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a>Creare un nuovo tipo di informazione riservata per il numero cliente Contoso

<table>
<thead>
<tr class="header">
<th align="left"><strong>Passaggio</strong></th>
<th align="left"><strong>Azione </strong></th>
<th align="left"><strong>Risultato</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Contoso si avvale di PowerShell e Ricerca contenuto per trovare documenti che corrispondono a un set di CCN di esempio.</td>
<td align="left">

<p>#Connettersi al Centro sicurezza e conformità</p>
<p>$adminUser = &quot;alland@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Creazione e avvio della ricerca per i dati campione</p>
<p>$searchName = &quot;Sample Customer Information Search&quot;</p>
<p>$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</p>
<p>New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</p>
<p>Start-ComplianceSearch -Identity $searchName</p>
</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Contoso analizza i risultati. Ogni volta che è stato usato il CCN, è stata utilizzata una data in formato europeo ed è stata impiegata anche una delle parole chiave entro una prossimità di 300 caratteri.</td>
<td align="left">numero cliente, n. cliente, cliente #, cliente#, cliente Contoso</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Contoso ha sviluppato il seguente schema Regular Expression (RegEx) per identificare il proprio CCN.</td>
<td align="left">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">Contoso ha sviluppato il seguente schema Regular Expression (RegEx) per identificare le date EU nei formati utilizzati dalle sue varie filiali.</td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">Contoso usa PowerShell per generare tre GUID univoci.</td>
<td align="left"><p>#Generazione di un GUID univoco per RulePack Id, Publisher Id ed Entity Id</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left">Contoso definisce i seguenti parametri per la regola del tipo di elemento riservato.</td>
<td align="left"><p>Nome: Numero cliente Contoso (CCN)</p>
<p>Descrizione: Numero cliente Contoso (CCN) che cerca parole chiave aggiuntive e data in formato europeo</p></td>
</tr>
<tr class="odd">
<td align="left">7</td>
<td align="left">Contoso crea un file XML per un nuovo tipo di informazione riservata per rilevare un Numero cliente Contoso (CCN) e lo salva in un file system locale come C:\Scripts\ContosoCCN.xml con codifica UTF-8.</td>
<td align="left">Vedere il file XML sotto questa tabella.</td>
</tr>
<tr class="even">
<td align="left">8</td>
<td align="left">Contoso crea il tipo di informazione riservata personalizzato con PowerShell.</td>
<td align="left"><p>#Connettersi al Centro sicurezza e conformità</p>
<p>$adminUser = &quot;alland@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Creazione del nuovo tipo di informazione riservata</p>
<p>New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a>File XML di esempio per il nuovo tipo di informazione riservata (passaggio 7)
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
