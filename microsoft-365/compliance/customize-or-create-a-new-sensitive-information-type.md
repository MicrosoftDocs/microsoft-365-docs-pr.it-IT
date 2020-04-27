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
ms.custom: ''
ms.assetid: ''
description: Informazioni su come modificare o creare nuovi tipi di informazioni riservate per il GDPR.
ms.openlocfilehash: e29193e3fdb7f4d2cd6a5810137bc120fb1171e5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637778"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a><span data-ttu-id="ac5d3-103">Personalizzare o creare un nuovo tipo di informazione riservata</span><span class="sxs-lookup"><span data-stu-id="ac5d3-103">Customize or create a new sensitive information type</span></span>

<span data-ttu-id="ac5d3-104">In questo vengono forniti tre esempi che dimostrano come modificare o creare nuovi tipi di informazioni riservate per il GDPR.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-104">This article provides three examples to demonstrate how to modify or create new sensitive information types for GDPR.</span></span>

- <span data-ttu-id="ac5d3-105">Modificare un tipo di informazione riservata esistente — Numero di carta di debito dell'Unione Europea</span><span class="sxs-lookup"><span data-stu-id="ac5d3-105">Modify an existing sensitive information type — EU Debit Card Number</span></span>

- <span data-ttu-id="ac5d3-106">Creare un nuovo tipo di informazione riservata — Indirizzo e-mail</span><span class="sxs-lookup"><span data-stu-id="ac5d3-106">Create a new sensitive information type — email address</span></span>

- <span data-ttu-id="ac5d3-107">Creare un nuovo tipo di informazione riservata con file XML di esempio — Numero cliente Contoso</span><span class="sxs-lookup"><span data-stu-id="ac5d3-107">Create a new sensitive information type with example XML file — Contoso customer number</span></span>

<span data-ttu-id="ac5d3-108">Vedere anche:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-108">Also see:</span></span>

- [<span data-ttu-id="ac5d3-109">Creare un tipo di informazione riservata personalizzata usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac5d3-109">Create a custom sensitive information type using PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [<span data-ttu-id="ac5d3-110">Personalizzare una tipologia integrata di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="ac5d3-110">Customize a built-in sensitive information type</span></span>](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a><span data-ttu-id="ac5d3-111">Modificare un tipo di informazione riservata per migliorare l'accuratezza</span><span class="sxs-lookup"><span data-stu-id="ac5d3-111">Modify a sensitive information type to improve accuracy</span></span>

<span data-ttu-id="ac5d3-112">Se si utilizza Ricerca contenuto per cercare dati personali con i tipi di informazioni riservate e non si ottengono i risultati previsti, oppure la query restituisce un numero eccessivo di falsi positivi, è possibile modificare il tipo di informazione riservata in modo che funzioni meglio con il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-112">If you're using Content Search to search for personal data using sensitive information types and you're not returning the expected results, or the query returns too many false positives, consider modifying the sensitive information type to work better with your environment.</span></span>

<span data-ttu-id="ac5d3-p101">La procedura consigliata quando si crea o si personalizza un tipo di informazione riservata consiste nel creare un nuovo tipo di informazione riservata basato su uno esistente, attribuendogli nome e identificatore univoci. Ad esempio, se si desidera regolare i parametri del tipo di informazione riservata "Numero di carta di debito dell'Unione Europea", è possibile denominare la copia di tale regola "Numero di carta di debito dell'Unione Europea avanzato" per distinguerla dall'originale.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p101">The best practice when creating or customizing a sensitive information type is to create a new sensitive information type based on an existing one, giving it a unique name and identifiers. For example, if you wish to adjust the parameters of the "EU Debit Card Number" sensitive information type, you could name your copy of that rule "EU Debit Card Enhanced" to distinguish it from the original.</span></span>

<span data-ttu-id="ac5d3-p102">Nel nuovo tipo di informazione riservata, è sufficiente modificare i valori che si desidera cambiare per migliorarne l'accuratezza. Al termine dell'operazione, caricare il nuovo tipo di informazione riservata e creare una nuova regola DLP (o modificarne una esistente) per utilizzare il nuovo tipo di informazione riservata appena aggiunto. La modifica dell'accuratezza dei tipi di informazioni riservate potrebbe richiedere alcuni tentativi e comportare degli errori, quindi mantenere una copia del tipo originale ne consente il recupero per eventuali utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p102">In your new sensitive information type, simply modify the values you wish to change to improve its accuracy. Once complete, upload your new sensitive information type and create a new DLP rule (or modify an existing one) to use the new sensitive information type you just added. Modifying the accuracy of sensitive information types might require some trial and error, so maintaining a copy of the original type allows you to fall back to it if required in the future.</span></span>

<span data-ttu-id="ac5d3-118">Per personalizzare un tipo di informazione riservata:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-118">To customize a sensitive information type:</span></span>

1.  <span data-ttu-id="ac5d3-119">Esportare il Pacchetto di regole Microsoft esistente di tipi di informazioni riservate integrati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-119">Export the existing Microsoft Rule Package of built in sensitive information types in Office 365.</span></span>

2.  <span data-ttu-id="ac5d3-120">Rinominare questo file XML e aprirlo nell'editor XML preferito.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-120">Rename this XML file and open it in your favorite XML editor.</span></span>

3.  <span data-ttu-id="ac5d3-121">Isolare il tipo di informazione riservata e rimuovere gli altri.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-121">Isolate the sensitive information type and remove all others.</span></span>

4.  <span data-ttu-id="ac5d3-122">Utilizzare PowerShell per generare due nuovi GUID per il tipo di informazione riservata da modificare.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-122">Use PowerShell to generate two new GUIDs for the sensitive information type you are modifying.</span></span>

5.  <span data-ttu-id="ac5d3-123">Modificare l'ID e gli altri elementi di base affinché il tipo di informazione riservata sia univoco (ciò include la sostituzione di due GUID con quelli nuovi generati).</span><span class="sxs-lookup"><span data-stu-id="ac5d3-123">Modify the ID and other basic elements so the sensitive information type is unique (this includes replacing two GUIDs with the new ones you generated).</span></span>

6.  <span data-ttu-id="ac5d3-124">Ottimizzare i requisiti di corrispondenza per migliorare l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-124">Tune the match requirements to improve accuracy.</span></span>

    1.  <span data-ttu-id="ac5d3-125">Modifiche di prossimità: modificare la prossimità del modello di carattere per espandere o ridurre la finestra in cui è necessario trovare le parole chiave rispetto al tipo di informazione riservata.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-125">Proximity modifications — Modify the character pattern proximity to expand or shrink the window in which keywords must be found around the sensitive information type.</span></span>

    2.  <span data-ttu-id="ac5d3-p103">Modifiche delle parole chiave: aggiungere parole chiave a uno degli elementi \<Keywords\> per fornire al tipo di informazione riservata un elemento avvalorante più specifico per le ricerche in modo da segnalare una corrispondenza per tale regola. In alternativa, rimuovere le parole chiave che causano falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p103">Keyword modifications — Add keywords to one of the \<Keywords\> element in order to provide our sensitive information type more specific corroborative evidence to search for in order to signal a match on this rule. Or remove keywords that are causing false positives.</span></span>

    3.  <span data-ttu-id="ac5d3-128">Modifiche di probabilità: modificare la probabilità con cui il tipo di informazione riservata deve soddisfare i criteri specificati nella sua definizione prima che venga segnalata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-128">Confidence modifications — Modify the confidence with which the sensitive information type must match the criteria specified in its definition before a match is signaled and reported.</span></span>

7.  <span data-ttu-id="ac5d3-129">Caricare il nuovo tipo di informazione riservata.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-129">Upload the new sensitive information type.</span></span>

8.  <span data-ttu-id="ac5d3-p104">Rieffettuare una ricerca per indicizzazione del contenuto per identificare l'informazione riservata. Vedere [Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un sito](https://support.office.com/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p104">Recrawl your content to identify the sensitive information. See [Manually request crawling and re-indexing of a site](https://support.office.com/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).</span></span>

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a><span data-ttu-id="ac5d3-132">Esempio: modificare il tipo di informazione riservata "Numero di carta di debito dell'Unione Europea"</span><span class="sxs-lookup"><span data-stu-id="ac5d3-132">Example: modify the 'EU Debit Card Number' sensitive information type</span></span>

<span data-ttu-id="ac5d3-p105">Per migliorare l'accuratezza delle regole DLP in qualsiasi sistema è necessario il test con un set di dati campione; inoltre, potrebbe essere necessaria un'ulteriore ottimizzazione attraverso ripetute modifiche e prove. In questo esempio vengono mostrate le modifiche al tipo di informazione riservata "Numero di carta di debito dell'Unione Europea" per migliorarne l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p105">Improving the accuracy of DLP rules in any system requires testing against a sample data set, and may require fine tuning through repetitive modifications and tests. This example demonstrates modifications to the 'EU Debit Card Number' sensitive information type to improve its accuracy.</span></span>

<span data-ttu-id="ac5d3-p106">Quando si cerca un numero di carta di debito dell'Unione Europea nell'esempio fornito, la definizione di tale numero è rigorosamente specificata tramite 16 cifre con uno schema complesso e soggette alla convalida di un checksum. Non è possibile alterare questo schema a causa della definizione della stringa di questo tipo di informazione riservata. Tuttavia, è possibile apportare le modifiche seguenti per migliorare l'accuratezza del modo in cui i criteri DLP rilevano questo tipo di informazione riservata in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p106">When searching for an EU Debit Card Number in our example, the definition of that number is strictly defined as 16 digits using a complex pattern, and being subject to the validation of a checksum. We cannot alter this pattern due to the string definition of this sensitive information type. However, we can make the following adjustments to improve the accuracy of how DLP finds this sensitive information type within Office 365.</span></span>

### <a name="proximity-modification"></a><span data-ttu-id="ac5d3-138">Modifica di prossimità</span><span class="sxs-lookup"><span data-stu-id="ac5d3-138">Proximity modification</span></span>

<span data-ttu-id="ac5d3-p107">Verrà ridotta la finestra modificando il valore patternProximity nell'elemento \<Entity\> da 300 a 150 caratteri. Ciò significa che l'elemento avvalorante (o le parole chiave) deve essere più vicino al tipo di informazione riservata in uso per segnalare una corrispondenza a questa regola.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p107">We'll shrink the window by modifying the patternProximity value in our \<Entity\> element from 300 to 150 characters. This means that our corroborative evidence, or our keywords, must be closer to our sensitive information type in order to signal a match on this rule.</span></span>

<span data-ttu-id="ac5d3-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-141">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

### <a name="keyword-modifications"></a><span data-ttu-id="ac5d3-142">Modifica della parole chiave</span><span class="sxs-lookup"><span data-stu-id="ac5d3-142">Keyword modifications</span></span>

<span data-ttu-id="ac5d3-p108">Alcune parole chiave potrebbero causare la presenza di falsi positivi. Di conseguenza, è consigliabile rimuovere le parole chiave. Di seguito sono indicate le parole chiave per l'esempio:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p108">Some keywords might cause false positives to occur. As a result you might want to remove keywords. Here are the keywords for this example::</span></span>

<span data-ttu-id="ac5d3-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-146">\<Keyword id="Keyword\_card\_terms\_dict"\></span></span>

<span data-ttu-id="ac5d3-147">\<Group\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-147">\<Group\></span></span>

<span data-ttu-id="ac5d3-148">\<Term\>corporate card\</Term\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-148">\<Term\>corporate card\</Term\></span></span>

<span data-ttu-id="ac5d3-149">\<Term\>organization card\</Term\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-149">\<Term\>organization card\</Term\></span></span>

<span data-ttu-id="ac5d3-150">\<Term\>acct nbr\</Term\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-150">\<Term\>acct nbr\</Term\></span></span>

<span data-ttu-id="ac5d3-151">\<Term\>acct num\</Term\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-151">\<Term\>acct num\</Term\></span></span>

<span data-ttu-id="ac5d3-152">\<Term\>acct no\</Term\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-152">\<Term\>acct no\</Term\></span></span>

<span data-ttu-id="ac5d3-153">…</span><span class="sxs-lookup"><span data-stu-id="ac5d3-153">…</span></span>

<span data-ttu-id="ac5d3-154">\</Group\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-154">\</Group\></span></span>

<span data-ttu-id="ac5d3-155">\</Keyword\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-155">\</Keyword\></span></span>

### <a name="confidence-modifications"></a><span data-ttu-id="ac5d3-156">Modifiche di probabilità</span><span class="sxs-lookup"><span data-stu-id="ac5d3-156">Confidence modifications</span></span>

<span data-ttu-id="ac5d3-p109">Se si rimuovono parole chiave dalla definizione, è preferibile impostare la probabilità di individuare il tipo di informazione riservata riducendo questo valore. Il livello predefinito per il tipo Numero di carta di debito dell'Unione Europea è 85.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p109">If you remove keywords from the definition, you would typically want to adjust how confident you are that this sensitive information type was found by lowering this value. The default level for EU Debit Card Number type is 85.</span></span>

<span data-ttu-id="ac5d3-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-159">\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\></span></span>

<span data-ttu-id="ac5d3-160">\<Pattern confidenceLevel="85"\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-160">\<Pattern confidenceLevel="85"\></span></span>

<span data-ttu-id="ac5d3-161">…</span><span class="sxs-lookup"><span data-stu-id="ac5d3-161">…</span></span>

<span data-ttu-id="ac5d3-162">\</Pattern\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-162">\</Pattern\></span></span>

<span data-ttu-id="ac5d3-163">\</Entity\></span><span class="sxs-lookup"><span data-stu-id="ac5d3-163">\</Entity\></span></span>

## <a name="create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="ac5d3-164">Creare un nuovo tipo di informazione riservata personalizzato</span><span class="sxs-lookup"><span data-stu-id="ac5d3-164">Create a new custom sensitive information type</span></span>

<span data-ttu-id="ac5d3-165">Per creare un nuovo tipo di informazione riservata personalizzato, iniziare con Ricerca contenuto per:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-165">To create a new custom sensitive information type, start by using Content Search to:</span></span>

-   <span data-ttu-id="ac5d3-166">Ottimizzare una query KQL</span><span class="sxs-lookup"><span data-stu-id="ac5d3-166">Optimize a KQL query</span></span>

-   <span data-ttu-id="ac5d3-167">Visualizzare le parole chiave particolarmente utili</span><span class="sxs-lookup"><span data-stu-id="ac5d3-167">See which keywords are most useful</span></span>

<span data-ttu-id="ac5d3-p110">Utilizzare questi risultati per creare un nuovo tipo di informazione riservata. Ottimizzare quindi il nuovo tipo di informazione riservata per il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p110">Use these results to create a new sensitive information type. Then optimize the new sensitive information type for your environment.</span></span>

<span data-ttu-id="ac5d3-p111">Nota: molti nuovi tipi di informazioni riservate saranno presto disponibili per i dati personali nei paesi dell'Unione Europea. Se è necessario creare i nuovi tipi di informazioni riservate, iniziare assegnando i dati personalizzati al proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p111">Note: Many new sensitive information types are coming soon for personal data in EU countries. If you need to create new sensitive information types, begin by targeting data that is custom to your environment.</span></span>

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a><span data-ttu-id="ac5d3-172">Passaggio 1: utilizzare query KQL e parole chiave per individuare dati aggiuntivi nel proprio ambiente</span><span class="sxs-lookup"><span data-stu-id="ac5d3-172">Step 1 — Use KQL queries and key words to find additional data in your environment</span></span>

<span data-ttu-id="ac5d3-p112">Potrebbe essere necessario creare query aggiuntive per trovare dati personali soggetti a GDPR. Ricerca contenuto si avvale di Keyword Query Language (KQL) per individuare i dati. I dati più riservati non possono essere rilevati in modo accurato utilizzando solo KQL senza i tipi di informazioni riservate. Pertanto, l'obiettivo consiste nel testare e ottimizzare le stringhe KQL tramite Ricerca contenuto e quindi utilizzarle per creare e ottimizzare nuovi tipi di informazioni riservate in cui è possibile ottenere un'accuratezza maggiore.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p112">You might need to create additional queries to find personal data that is subject to GDPR. Content Search uses Keyword Query Language (KQL) to find data. Most sensitive data can't be accurately detected using just KQL without sensitive information types. So the goal is to test and optimize KQL strings using Content Search and then use these to create and tune new sensitive information types where you can achieve even greater accuracy.</span></span>

<span data-ttu-id="ac5d3-177">Utilizzare queste risorse per formulare e ottimizzare query tramite KQL:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-177">Use these resources to formulate and optimize queries using KQL:</span></span>

- [<span data-ttu-id="ac5d3-178">Riferimenti per la sintassi (DMC) di Keyword Query Language (KQL)</span><span class="sxs-lookup"><span data-stu-id="ac5d3-178">Keyword Query Language (KQL) syntax reference (DMC)</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [<span data-ttu-id="ac5d3-179">Eseguire una Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="ac5d3-179">Run a Content Search</span></span>](content-search.md)

<span data-ttu-id="ac5d3-p113">Ricerca contenuto fornisce un'altra risorsa che consente di sviluppare query KQL e tipi di informazioni riservate: le parole chiave. Perché utilizzare l'elenco delle parole chiave? È possibile ottenere le statistiche che mostrano quanti elementi corrispondo a ciascuna parola chiave. Questo può essere utile per trovare rapidamente le parole chiave più o meno efficaci. Per ulteriori informazioni sulle statistiche di ricerca, vedere [Visualizzare statistiche delle parole chiave per i risultati di Ricerca contenuto](https://support.office.com/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p113">Content Search provides another resource to help you develop KQL queries and sensitive information types — keywords. Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. For more information about search statistics, see [View keyword statistics for Content Search results](https://support.office.com/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).</span></span>

<span data-ttu-id="ac5d3-p114">Le parole chiave in ogni riga sono collegate dall'operatore OR nella query di ricerca creata. È inoltre possibile utilizzare una frase parola chiave (racchiusa tra parentesi) in una riga.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p114">Keywords on each row are connected by the OR operator in the search query that's created. You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span>

<span data-ttu-id="ac5d3-187">Per ulteriori informazioni, vedere [Query delle parole chiave e condizioni di ricerca per ricerca contenuto](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).</span><span class="sxs-lookup"><span data-stu-id="ac5d3-187">For more information, see [Keyword queries and search conditions for Content Search](https://support.office.com/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).</span></span>

### <a name="exampleusing-content-search-to-identify-email-addresses"></a><span data-ttu-id="ac5d3-188">Esempio: identificare indirizzi e-mail tramite Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="ac5d3-188">Example—Using Content Search to identify email addresses</span></span>

<span data-ttu-id="ac5d3-p115">Gli indirizzi e-mail sono considerati informazioni riservate correlate ai soggetti dei dati. Questo è un esempio semplice che consente di mostrare come può aiutare Ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p115">Email addresses are considered sensitive information related to data subjects. This is a simple example to demonstrate how Content Search can help.</span></span>

<span data-ttu-id="ac5d3-p116">Non è possibile utilizzare KQL e parole chiave insieme. Utilizzare questi strumenti separatamente per perfezionare la query e determinare le parole chiave che potrebbero essere utili nei tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p116">KQL and keywords can't be used together. Use these tools separately to hone your query and determine keywords that might be useful in sensitive information types.</span></span>

### <a name="kql-query"></a><span data-ttu-id="ac5d3-193">Query KQL</span><span class="sxs-lookup"><span data-stu-id="ac5d3-193">KQL query</span></span>

<span data-ttu-id="ac5d3-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span><span class="sxs-lookup"><span data-stu-id="ac5d3-194">(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)</span></span>

<span data-ttu-id="ac5d3-195">Note:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-195">Notes:</span></span>

-   <span data-ttu-id="ac5d3-196">È possibile utilizzare NEAR e ONEAR per le ricerche di prossimità.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-196">You can use NEAR and ONEAR for proximity searches.</span></span>

-   <span data-ttu-id="ac5d3-197">Purtroppo al momento KQL non supporta le query con la classe Regex (esempio: IdRef="Regex\_email\_address").</span><span class="sxs-lookup"><span data-stu-id="ac5d3-197">Unfortunately, KQL doesn't support queries with the Regex Class (ex: IdRef="Regex\_email\_address")</span></span>

### <a name="keywords"></a><span data-ttu-id="ac5d3-198">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ac5d3-198">Keywords</span></span>

<span data-ttu-id="ac5d3-p117">Immettere ogni parola chiave in una riga separata. Parole chiave di esempio:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p117">Enter each keyword on a separate line. Example keywords:</span></span>

-   <span data-ttu-id="ac5d3-201">indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ac5d3-201">email address</span></span>

-   <span data-ttu-id="ac5d3-202">posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ac5d3-202">mail</span></span>

-   <span data-ttu-id="ac5d3-203">contatto</span><span class="sxs-lookup"><span data-stu-id="ac5d3-203">contact</span></span>

-   <span data-ttu-id="ac5d3-204">mittente</span><span class="sxs-lookup"><span data-stu-id="ac5d3-204">sender</span></span>

-   <span data-ttu-id="ac5d3-205">destinatario</span><span class="sxs-lookup"><span data-stu-id="ac5d3-205">recipient</span></span>

-   <span data-ttu-id="ac5d3-206">cc</span><span class="sxs-lookup"><span data-stu-id="ac5d3-206">cc</span></span>

-   <span data-ttu-id="ac5d3-207">bcc</span><span class="sxs-lookup"><span data-stu-id="ac5d3-207">bcc</span></span>

<span data-ttu-id="ac5d3-208">In questo esempio, viene mostrato che le parole chiave non sono necessarie e generano molti falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-208">In this example, you might learn the keywords are not necessary and produce a lot of false positive results.</span></span>

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a><span data-ttu-id="ac5d3-209">Passaggio 2: creare un nuovo tipo di informazione riservata personalizzato</span><span class="sxs-lookup"><span data-stu-id="ac5d3-209">Step 2 — Create a new custom sensitive information type</span></span>

<span data-ttu-id="ac5d3-p118">Dopo aver utilizzato le query KQL e le parole chiave per identificare informazioni riservate, usarle per creare nuovi tipi di informazioni riservate personalizzati. In molti casi, sarà necessario il perfezionamento dei tipi di informazioni riservate per ottenere il giusto livello di accuratezza. Sarà quindi possibile utilizzare questi tipi di informazioni riservate personalizzati con Ricerca contenuto, nei criteri DLP e in altri strumenti, nonché nelle query KQL.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p118">After using KQL queries and keywords to identify sensitive information, use these to create new custom sensitive information types. In many cases, you'll require the sophistication of sensitive information types to achieve the right level of accuracy. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span>

<span data-ttu-id="ac5d3-p119">La procedura consigliata consiste nel creare un nuovo tipo di informazione riservata basato su uno esistente. Utilizzare la stessa procedura descritta in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p119">The best practice is to create a new sensitive information type based on an existing one. Use the same process described earlier in this article.</span></span>

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a><span data-ttu-id="ac5d3-215">Esempio: creare un nuovo tipo di informazione riservata per gli indirizzi e-mail</span><span class="sxs-lookup"><span data-stu-id="ac5d3-215">Example — Create a new sensitive information for email addresses</span></span> 

<span data-ttu-id="ac5d3-p120">È stato scelto questo esempio per la sua semplicità. Nella seguente tabella sono riportate le modifiche consigliate per un nuovo tipo di informazione riservata relativo alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p120">We'll continue with the email address as an example because it's simple. The following table details the modifications recommended for a new email sensitive information type.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ac5d3-218"><strong>Passaggio</strong></span><span class="sxs-lookup"><span data-stu-id="ac5d3-218"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="ac5d3-219"><strong>Modifica</strong></span><span class="sxs-lookup"><span data-stu-id="ac5d3-219"><strong>Modification </strong></span></span></th>
<th align="left"><span data-ttu-id="ac5d3-220"><strong>Sintassi XML di esempio</strong></span><span class="sxs-lookup"><span data-stu-id="ac5d3-220"><strong>Example XML syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ac5d3-221">1</span><span class="sxs-lookup"><span data-stu-id="ac5d3-221">1</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-222">Impostare la proprietà IdRef</span><span class="sxs-lookup"><span data-stu-id="ac5d3-222">Set the IdRef property</span></span>
<p><span data-ttu-id="ac5d3-p121">Nell'elemento &lt;Entity&gt;, modificare l'elemento &lt;IdMatch&gt; affinché la relativa proprietà idRef sia uguale a un valore univoco. Questo valore farà riferimento a un elemento che definisce l'espressione regolare per trovare gli indirizzi e-mail.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p121">Within the &lt;Entity&gt; element, modify the &lt;IdMatch&gt; element so that its idRef property is = to a unique value. This value will point to an element that defines our regular expression to find email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="ac5d3-225">IdRef=&quot;Regex_email_address&quot;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-225">IdRef=&quot;Regex_email_address&quot;</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ac5d3-226">2</span><span class="sxs-lookup"><span data-stu-id="ac5d3-226">2</span></span></td>
<td align="left"><p><span data-ttu-id="ac5d3-227">Attributo di prossimità</span><span class="sxs-lookup"><span data-stu-id="ac5d3-227">Proximity attribute</span></span></p>
<p><span data-ttu-id="ac5d3-228">Iniziare con un valore patternProximity nell'elemento &lt;Entity&gt; di 300.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-228">We'll start with a patternProximity value in our &lt;Entity&gt; element of 300.</span></span></p></td>
<td align="left"><span data-ttu-id="ac5d3-229">patternsProximity=&quot;300&quot;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-229">patternsProximity=&quot;300&quot;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ac5d3-230">3</span><span class="sxs-lookup"><span data-stu-id="ac5d3-230">3</span></span></td>
<td align="left"><p><span data-ttu-id="ac5d3-231">Livello di probabilità</span><span class="sxs-lookup"><span data-stu-id="ac5d3-231">Confidence level</span></span></p>
<p><span data-ttu-id="ac5d3-p122">Impostare la proprietà recommendedConfidence su un valore che si pensi possa rappresentare la probabilità di trovare una corrispondenza accurata. Ciò potrebbe richiedere un tentativo con un set di dati rappresentativi per ottenere un risultato accurato. Come impostazione iniziale, impostare questo valore su 75.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p122">Set the recommendedConfidence property to a value you feel will represent the confidence of finding an accurate match. This will likely require testing with a representative data set to get an accurate result. As an initial setting, set this value to 75.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac5d3-235">recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-235">recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-236">L'XML ottenuto per questi primi tre elementi combinati sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-236">The resulting XML for these first three elements combined looks like this:</span></span></p>
<p><span data-ttu-id="ac5d3-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-237">&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-238">&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-239">&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-240">&lt;Any minMatches=&quot;1&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-240">&lt;Any minMatches=&quot;1&quot;&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-241">&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-242">&lt;/Any&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-242">&lt;/Any&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-243">&lt;/Pattern&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-243">&lt;/Pattern&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-244">&lt;/Entity&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-244">&lt;/Entity&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ac5d3-245">4</span><span class="sxs-lookup"><span data-stu-id="ac5d3-245">4</span></span></td>
<td align="left"><p><span data-ttu-id="ac5d3-246">Elemento Regex</span><span class="sxs-lookup"><span data-stu-id="ac5d3-246">Regex element</span></span></p>
<p><span data-ttu-id="ac5d3-247">Aggiungere un nuovo elemento &lt;Regex&gt; immediatamente sotto gli elementi &lt;Entity&gt; che definisce l'espressione regolare utilizzata per identificare gli indirizzi e-mail.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-247">Add a new &lt;Regex&gt; element immediately be below the &lt;Entity&gt; elements that defines the regular expression used to identify email addresses.</span></span></p></td>
<td align="left"><span data-ttu-id="ac5d3-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-248">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ac5d3-249">5</span><span class="sxs-lookup"><span data-stu-id="ac5d3-249">5</span></span></td>
<td align="left"><p><span data-ttu-id="ac5d3-250">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ac5d3-250">Keywords</span></span></p>
<p><span data-ttu-id="ac5d3-p123">Aggiungere un nuovo elemento &lt;Keyword&gt; sotto l'elemento &lt;Regex&gt; che definisce l'elenco di indirizzi e-mail correlati alle parole chiave. Verificare che il valore id dell'elemento &lt;Keyword&gt; corrisponda al valore &lt;Match idRef&gt; nell'elemento &lt;Entity&gt;&lt;Pattern&gt;. È possibile continuare ad aggiungere le proprie parole chiave se necessario.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p123">Add a new &lt;Keyword&gt; element below the &lt;Regex&gt; element that defines list of email address related keywords. Ensure that the id value for the &lt;Keyword&gt; element matches the &lt;Match idRef&gt; value in the &lt;Entity&gt;&lt;Pattern&gt; element. You may continue to add your own keywords if needed.</span></span></p>
<p><span data-ttu-id="ac5d3-p124">Le parole chiave non devono necessariamente essere incluse in un tipo di informazione riservata per la posta elettronica. Di seguito ne sono forniti degli esempi.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p124">Keywords are likely not necessary to include in an email sensitive information type. These are provided as an example.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac5d3-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-256">&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-257">&lt;Group&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-257">&lt;Group&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-258">&lt;Term&gt;email&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-258">&lt;Term&gt;email&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-259">&lt;Term&gt;email address&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-259">&lt;Term&gt;email address&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-260">&lt;Term&gt;contact&lt;/Term&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-260">&lt;Term&gt;contact&lt;/Term&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-261">&lt;/Group&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-261">&lt;/Group&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-262">&lt;/Keyword&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-262">&lt;/Keyword&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ac5d3-263">6</span><span class="sxs-lookup"><span data-stu-id="ac5d3-263">6</span></span></td>
<td align="left"><p><span data-ttu-id="ac5d3-264">Elemento LocalizedStrings</span><span class="sxs-lookup"><span data-stu-id="ac5d3-264">LocalizedStrings element</span></span></p>
<p><span data-ttu-id="ac5d3-265">Nell'elemento &lt;LocalizedStrings&gt;&lt;Resource&gt; verificare di disporre di un nome univoco che identifichi il tipo di informazione riservata.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-265">In the &lt;LocalizedStrings&gt;&lt;Resource&gt; element ensure that you have a unique name that identifies your sensitive information type.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac5d3-266">&lt;LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-266">&lt;LocalizedStrings&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-267">&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-268">&lt;Name default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Email Address&lt;/Name&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-269">&lt;Description default=&quot;true&quot; langcode=&quot;en-us&quot;&gt;Detects email addresses.&lt;/Description&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-270">&lt;/Resource&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-270">&lt;/Resource&gt;</span></span></p>
<p><span data-ttu-id="ac5d3-271">&lt;/LocalizedStrings&gt;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-271">&lt;/LocalizedStrings&gt;</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a><span data-ttu-id="ac5d3-272">Creare un nuovo tipo di informazione riservata con file XML e PowerShell di esempio — Numero cliente Contoso</span><span class="sxs-lookup"><span data-stu-id="ac5d3-272">Create a new sensitive information type with example PowerShell and XML file — Contoso customer number</span></span>

<span data-ttu-id="ac5d3-p125">Contoso utilizza un Numero cliente Contoso (CCN) per identificare ogni cliente nel proprio database dei clienti. Un CCN è costituito dalla seguente tassonomia:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p125">Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following taxonomy:</span></span>

-   <span data-ttu-id="ac5d3-p126">Due cifre che rappresentano l'anno di creazione del record. Contoso è stata fondata nel 2002; quindi, il primo valore possibile dovrebbe essere 02.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p126">Two digits to represent the year that the record was created. Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span>

-   <span data-ttu-id="ac5d3-p127">Tre cifre che rappresentano l'agenzia partner che ha creato il record. I valori possibili per l'agenzia sono compresi tra 000 e 999.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p127">Three digits to represent the partner agency that created the record. Possible agency values range from 000 to 999.</span></span>

-   <span data-ttu-id="ac5d3-p128">Un carattere alfabetico che rappresenta la linea di business. I valori possibili vanno dalla a alla z, con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p128">An alpha character to represent the line of business. Possible values are a-z and should be case insensitive.</span></span>

-   <span data-ttu-id="ac5d3-p129">Un numero di serie di quattro cifre. I possibili valori per il numero di serie sono compresi tra 0000 e 9999.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p129">A four-digit serial number. Possible serial number values range from 0000 to 9999.</span></span>

<span data-ttu-id="ac5d3-283">CCN di esempio:</span><span class="sxs-lookup"><span data-stu-id="ac5d3-283">Example CCNs:</span></span>

> <span data-ttu-id="ac5d3-284">15080P9562</span><span class="sxs-lookup"><span data-stu-id="ac5d3-284">15080P9562</span></span>
>
> <span data-ttu-id="ac5d3-285">14040O1119</span><span class="sxs-lookup"><span data-stu-id="ac5d3-285">14040O1119</span></span>
>
> <span data-ttu-id="ac5d3-286">15020J8317</span><span class="sxs-lookup"><span data-stu-id="ac5d3-286">15020J8317</span></span>
>
> <span data-ttu-id="ac5d3-287">14050E2330</span><span class="sxs-lookup"><span data-stu-id="ac5d3-287">14050E2330</span></span>
>
> <span data-ttu-id="ac5d3-288">16050E2166</span><span class="sxs-lookup"><span data-stu-id="ac5d3-288">16050E2166</span></span>
>
> <span data-ttu-id="ac5d3-289">17040O1118</span><span class="sxs-lookup"><span data-stu-id="ac5d3-289">17040O1118</span></span>

<span data-ttu-id="ac5d3-290">Contoso fa sempre riferimento ai clienti utilizzando un CCN nella corrispondenza interna/esterna, nei documenti e così via. Vuole creare un tipo di informazione riservata personalizzato che rilevi l'uso di CCN per poter applicare la protezione per l'utilizzo di questo modulo di dati personali.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-290">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, etc. They would like to create a custom sensitive information type to detect the use of CCN so that they may apply protection to the use of this form of personal data.</span></span>

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a><span data-ttu-id="ac5d3-291">Creare un nuovo tipo di informazione riservata per il numero cliente Contoso</span><span class="sxs-lookup"><span data-stu-id="ac5d3-291">Create a new sensitive information type for Contoso customer number</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ac5d3-292"><strong>Passaggio</strong></span><span class="sxs-lookup"><span data-stu-id="ac5d3-292"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="ac5d3-293"><strong>Azione </strong></span><span class="sxs-lookup"><span data-stu-id="ac5d3-293"><strong>Action </strong></span></span></th>
<th align="left"><span data-ttu-id="ac5d3-294"><strong>Risultato</strong></span><span class="sxs-lookup"><span data-stu-id="ac5d3-294"><strong>Result</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ac5d3-295">1</span><span class="sxs-lookup"><span data-stu-id="ac5d3-295">1</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-296">Contoso si avvale di PowerShell e Ricerca contenuto per trovare documenti che corrispondono a un set di CCN di esempio.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-296">Contoso uses PowerShell and Content Search to find documents that match an example set of CCNs.</span></span></td>
<td align="left">

<p><span data-ttu-id="ac5d3-297">#Connettersi al Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ac5d3-297">#Connect to Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="ac5d3-298">$adminUser = &quot;alland@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-298">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="ac5d3-299">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="ac5d3-299">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="ac5d3-300">#Creazione e avvio della ricerca per i dati campione</span><span class="sxs-lookup"><span data-stu-id="ac5d3-300">#Create &amp; start search for sample data</span></span></p>
<p><span data-ttu-id="ac5d3-301">$searchName = &quot;Sample Customer Information Search&quot;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-301">$searchName = &quot;Sample Customer Information Search&quot;</span></span></p>
<p><span data-ttu-id="ac5d3-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-302">$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</span></span></p>
<p><span data-ttu-id="ac5d3-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span><span class="sxs-lookup"><span data-stu-id="ac5d3-303">New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</span></span></p>
<p><span data-ttu-id="ac5d3-304">Start-ComplianceSearch -Identity $searchName</span><span class="sxs-lookup"><span data-stu-id="ac5d3-304">Start-ComplianceSearch -Identity $searchName</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ac5d3-305">2</span><span class="sxs-lookup"><span data-stu-id="ac5d3-305">2</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-p130">Contoso analizza i risultati. Ogni volta che è stato usato il CCN, è stata utilizzata una data in formato europeo ed è stata impiegata anche una delle parole chiave entro una prossimità di 300 caratteri.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-p130">Contoso analyzes the results. Every time the CCN was used, an EU formatted date was used and one of these keywords were also used within a proximity of 300 characters.</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-308">numero cliente, n. cliente, cliente #, cliente#, cliente Contoso</span><span class="sxs-lookup"><span data-stu-id="ac5d3-308">customer number, customer no, customer #, customer#, Contoso customer</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ac5d3-309">3</span><span class="sxs-lookup"><span data-stu-id="ac5d3-309">3</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-310">Contoso ha sviluppato il seguente schema Regular Expression (RegEx) per identificare il proprio CCN.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-310">Contoso developed the following Regular Expression (RegEx) pattern to identify their CCN.</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span><span class="sxs-lookup"><span data-stu-id="ac5d3-311">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ac5d3-312">4</span><span class="sxs-lookup"><span data-stu-id="ac5d3-312">4</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-313">Contoso ha sviluppato il seguente schema Regular Expression (RegEx) per identificare le date EU nei formati utilizzati dalle sue varie filiali.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-313">Contoso developed the following Regular Expression (RegEx) pattern to identify EU dates in the formats used by their various subsidiaries.</span></span></td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ac5d3-314">5</span><span class="sxs-lookup"><span data-stu-id="ac5d3-314">5</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-315">Contoso usa PowerShell per generare tre GUID univoci.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-315">Contoso uses PowerShell to generate three unique GUIDs.</span></span></td>
<td align="left"><p><span data-ttu-id="ac5d3-316">#Generazione di un GUID univoco per RulePack Id, Publisher Id ed Entity Id</span><span class="sxs-lookup"><span data-stu-id="ac5d3-316">#Generate a unique GUID for RulePack Id, Publisher Id, and Entity Id</span></span></p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ac5d3-317">6</span><span class="sxs-lookup"><span data-stu-id="ac5d3-317">6</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-318">Contoso definisce i seguenti parametri per la regola del tipo di elemento riservato.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-318">Contoso defines the following parameters for their sensitive item type rule.</span></span></td>
<td align="left"><p><span data-ttu-id="ac5d3-319">Nome: Numero cliente Contoso (CCN)</span><span class="sxs-lookup"><span data-stu-id="ac5d3-319">Name: Contoso Customer Number (CCN)</span></span></p>
<p><span data-ttu-id="ac5d3-320">Descrizione: Numero cliente Contoso (CCN) che cerca parole chiave aggiuntive e data in formato europeo</span><span class="sxs-lookup"><span data-stu-id="ac5d3-320">Description: Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ac5d3-321">7</span><span class="sxs-lookup"><span data-stu-id="ac5d3-321">7</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-322">Contoso crea un file XML per un nuovo tipo di informazione riservata per rilevare un Numero cliente Contoso (CCN) e lo salva in un file system locale come C:\Scripts\ContosoCCN.xml con codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-322">Contoso creates an XML file for a new sensitive information type to detect a Contoso Customer Number (CCN) and saves this to a local file system as C:\Scripts\ContosoCCN.xml in with UTF-8 encoding.</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-323">Vedere il file XML sotto questa tabella.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-323">See the XML file below this table.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ac5d3-324">8</span><span class="sxs-lookup"><span data-stu-id="ac5d3-324">8</span></span></td>
<td align="left"><span data-ttu-id="ac5d3-325">Contoso crea il tipo di informazione riservata personalizzato con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-325">Contoso creates the custom sensitive information type with the following PowerShell.</span></span></td>
<td align="left"><p><span data-ttu-id="ac5d3-326">#Connettersi al Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ac5d3-326">#Connect to Security &amp; Compliance Center</span></span></p>
<p><span data-ttu-id="ac5d3-327">$adminUser = &quot;alland@contoso.com&quot;</span><span class="sxs-lookup"><span data-stu-id="ac5d3-327">$adminUser = &quot;alland@contoso.com&quot;</span></span></p>
<p><span data-ttu-id="ac5d3-328">Connect-IPPSSession -UserPrincipalName $adminUser</span><span class="sxs-lookup"><span data-stu-id="ac5d3-328">Connect-IPPSSession -UserPrincipalName $adminUser</span></span></p>
<p><span data-ttu-id="ac5d3-329">#Creazione del nuovo tipo di informazione riservata</span><span class="sxs-lookup"><span data-stu-id="ac5d3-329">#Create new Sensitive Information Type</span></span></p>
<p><span data-ttu-id="ac5d3-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span><span class="sxs-lookup"><span data-stu-id="ac5d3-330">New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a><span data-ttu-id="ac5d3-331">File XML di esempio per il nuovo tipo di informazione riservata (passaggio 7)</span><span class="sxs-lookup"><span data-stu-id="ac5d3-331">Example XML file for the new sensitive information type (step 7)</span></span>
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
