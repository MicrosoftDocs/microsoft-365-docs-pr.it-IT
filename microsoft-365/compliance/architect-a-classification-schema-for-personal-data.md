---
title: Progettare uno schema di classificazione per i dati personali
f1.keywords:
- NOCSH
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
ms.openlocfilehash: db61c5c26ed8484e99aa8f06310bdd3385cf2dce
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637136"
---
# <a name="architect-a-classification-schema-for-personal-data"></a><span data-ttu-id="089d7-103">Progettare uno schema di classificazione per i dati personali</span><span class="sxs-lookup"><span data-stu-id="089d7-103">Architect a classification schema for personal data</span></span>

<span data-ttu-id="089d7-p101">I precedenti articoli di questa serie si focalizzano sull'uso dei tipi di informazioni riservate per identificare i dati personali soggetti all'RGPD. I tipi di informazioni riservate sono una forma di classificazione. Potrebbero rappresentare tutta la classificazione necessaria all'utente. Tuttavia, molte organizzazioni implementano una strategia di governance dei dati più ampia mediante le etichette. Consultare questo argomento per decidere se si desidera implementare anche le etichette nell'ambito del piano RGPD. Se sì, in questo argomento sono disponibili informazioni dettagliate ed esempi.</span><span class="sxs-lookup"><span data-stu-id="089d7-p101">Previous articles in this series focus on using sensitive information types to identify personal data that is subject to GDPR. Sensitive information types are a form of classification. This might be all the classification you need. However, many organizations implement a broader data governance strategy using labels. Use this topic to decide if you also want to implement labels as part of your GDPR plan. If you do, this topic provides some guidance and examples.</span></span>

<span data-ttu-id="089d7-p102">Nota: definire uno schema di classificazione per un'organizzazione e configurare criteri, etichette e condizioni richiede una pianificazione attenta. È importante comprendere che non si tratta di una procedura IT. Accertarsi di collaborare con il proprio team legale e della conformità per sviluppare una classificazione e uno schema di etichette appropriati per i dati della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="089d7-p102">Note: Defining a classification schema for an organization and configuring policies, labels, and conditions requires careful planning and preparation. It's important to realize that this isn't an IT driven process. Be sure to work with your legal and compliance team to develop an appropriate classification and labeling schema for your organization's data.</span></span>

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a><span data-ttu-id="089d7-113">Decidere se utilizzare le etichette oltre ai tipi di dati riservati</span><span class="sxs-lookup"><span data-stu-id="089d7-113">Decide if you're using labels in addition to sensitive data types</span></span>

<span data-ttu-id="089d7-p103">È possibile adottare uno dei due approcci di classificazione in Microsoft 365 per le informazioni personali. Ciascuno di essi può essere utilizzato per la protezione GDPR. Se si decide di usare solo i tipi di informazioni riservate per la classificazione, è possibile ignorare il resto di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="089d7-p103">You can take one of two approaches for classification in Microsoft 365 for personal information. Either of these can be used for GDPR protection. If you decide to use only sensitive information types for classification, you can skip the rest of this topic.</span></span>

<span data-ttu-id="089d7-117">Scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="089d7-117">Choose one of the following options.</span></span>

### <a name="option-1-use-only-microsoft-365-sensitive-information-types"></a><span data-ttu-id="089d7-118">Opzione 1: usare solo tipi di informazioni riservate di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="089d7-118">Option 1: Use only Microsoft 365 sensitive information types</span></span>

- <span data-ttu-id="089d7-119">I tipi di informazioni riservate sono utili per identificare e proteggere i dati personali soggetti a RGPD e altri tipi di normative.</span><span class="sxs-lookup"><span data-stu-id="089d7-119">Sensitive information types work well to identify and protect personal data subject to GDPR and other types of regulations.</span></span>

- <span data-ttu-id="089d7-120">Sono più facili da usare se l'organizzazione non dispone o non intende implementare un piano di governance dei dati più ampio con le etichette.</span><span class="sxs-lookup"><span data-stu-id="089d7-120">These are simpler to use if your organization doesn't already have or plan to implement a broader data governance plan using labels.</span></span>

- <span data-ttu-id="089d7-121">Funzionano con le regole DLP (come le etichette di conservazione).</span><span class="sxs-lookup"><span data-stu-id="089d7-121">These work with DLP rules (so do retention labels).</span></span>

- <span data-ttu-id="089d7-122">I tipi di informazioni sensibili sono compatibili con Cloud App Security per consentire agli utenti di rilevare le informazioni riservate in altre app SaaS.</span><span class="sxs-lookup"><span data-stu-id="089d7-122">Sensitive information types work with Cloud App Security so you can detect sensitive information in other SaaS apps.</span></span>

### <a name="option-2-use-sensitive-information-types--retention-labels"></a><span data-ttu-id="089d7-123">Opzione 2: usare tipi di informazioni sensibili + etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="089d7-123">Option 2: Use sensitive information types + retention labels</span></span>

- <span data-ttu-id="089d7-124">I tipi di informazioni sensibili devono applicare automaticamente le etichette ai dati personali soggetti a GDPR, quindi rappresentano un prerequisito.</span><span class="sxs-lookup"><span data-stu-id="089d7-124">You'll need sensitive information types to automatically apply labels to personal data that is subject to GDPR, so these are a prerequisite.</span></span>

- <span data-ttu-id="089d7-125">L'uso delle etichette di conservazione consente di includere dati personali soggetti a GDPR in un piano di governance dei dati più ampio per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="089d7-125">Using retention labels allows you to include personal data that is subject to GDPR into a broader data governance plan for your organization.</span></span>

## <a name="develop-a-label-schema-that-includes-personal-data"></a><span data-ttu-id="089d7-126">Sviluppare uno schema di etichette che include dati personali</span><span class="sxs-lookup"><span data-stu-id="089d7-126">Develop a label schema that includes personal data</span></span>

<span data-ttu-id="089d7-p104">Prima di utilizzare funzioni tecniche per applicare etichette e protezione, è opportuno esaminare l'organizzazione per definire uno schema di classificazione. L'organizzazione dovrebbe già avere uno schema di classificazione che semplifica l'aggiunta di dati personali. Questo argomento include uno schema di classificazione di esempio. È possibile utilizzare questo esempio come punto di partenza, se necessario.</span><span class="sxs-lookup"><span data-stu-id="089d7-p104">Before using technical capabilities to apply labels and protection, first work across your organization to define a classification schema. Your organization might already have a classification schema, which makes it easier to add personal data. This topic includes an example classification schema. You can use this example as a starting point, if needed.</span></span>

### <a name="getting-started"></a><span data-ttu-id="089d7-131">Introduzione</span><span class="sxs-lookup"><span data-stu-id="089d7-131">Getting started</span></span>

<span data-ttu-id="089d7-p105">Iniziare decidendo la quantità e i nomi delle etichette da implementare. Eseguire questa operazione senza pensare alla tecnologia da usare e alla modalità di applicazione delle etichette. Applicare questo schema a livello globale nell'organizzazione, includendo i dati in locale e in altri servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="089d7-p105">Begin by deciding on the number and names of labels to implement. Do this activity without worrying about which technology to use and how labels will be applied. Apply this schema universally throughout your organization, including data that resides on premises and in other cloud services.</span></span>

### <a name="recommendations"></a><span data-ttu-id="089d7-135">Consigli</span><span class="sxs-lookup"><span data-stu-id="089d7-135">Recommendations</span></span> 

<span data-ttu-id="089d7-136">Durante la progettazione e l'implementazione di criteri, etichette e condizioni, seguire questi suggerimenti:</span><span class="sxs-lookup"><span data-stu-id="089d7-136">When designing and implementing policies, labels and conditions, consider following these recommendations:</span></span>

- <span data-ttu-id="089d7-p106">Utilizzare lo schema di classificazione esistente (se disponibile) &ndash; molte organizzazioni già utilizzano la classificazione dei dati in qualche modo. Esaminare attentamente lo schema di assegnazione delle etichette esistente e, se possibile, usarlo così com'è. La scelta sarà influenzata dall'utilizzo di etichette note agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="089d7-p106">Use existing classification schema (if any) &ndash; Many organizations already are using data classification in some form. Carefully evaluate the existing label schema and if possible use it as is. Using familiar labels that are recognizable to the end user will drive adoption.</span></span>

- <span data-ttu-id="089d7-p107">Iniziare con criteri ed etichette predefiniti &ndash; tutte le soluzioni sono dotate di un set di criteri ed etichette predefiniti. Esaminarli attentamente nell'ambito dei requisiti aziendali e legali dell'organizzazione e scegliere di usare quelli, anziché crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="089d7-p107">Start with default policies and labels &ndash; All solutions come with a set of predefined policies and labels. Carefully evaluate these against the organization's legal and business requirements and consider using them instead of creating new ones.</span></span>

- <span data-ttu-id="089d7-p108">Iniziare con poche etichette &ndash; potenzialmente non ci sono limiti alla quantità di etichette che è possibile creare. Tuttavia, un gran numero di etichette e etichette secondarie influirà in modo negativo sull'adozione. Un numero eccessivo di scelte spesso è sinonimo di nessuna scelta.</span><span class="sxs-lookup"><span data-stu-id="089d7-p108">Start small &ndash; There's virtually no limit to the number of labels that can be created. However, large numbers of labels and sub-labels will negatively impact the adoption. Too many choices often mean no choice at all.</span></span>

- <span data-ttu-id="089d7-145">Utilizzare scenari e casi d'uso &ndash; identificare casi d'uso comuni all'interno dell'organizzazione e scenari derivati da RGPD per verificare se la configurazione pianificata per la classificazione e l'assegnazione di etichette è efficace.</span><span class="sxs-lookup"><span data-stu-id="089d7-145">Use scenarios and use cases &ndash; Identify common use cases within the organization and use scenarios derived from the GDPR to verify if the envisioned label and classification configuration will work in practice.</span></span>

- <span data-ttu-id="089d7-p109">Per ogni richiesta di nuova etichetta, è opportuno chiedersi &ndash; tutti gli scenari o i casi d'uso necessitano realmente di una nuova etichetta o è possibile utilizzare quelle già disponibili? Mantenere il numero di etichette al minimo migliora l'adozione.</span><span class="sxs-lookup"><span data-stu-id="089d7-p109">Question every request for a new label &ndash; Does every scenario or use case really need a new label or can you use what you already have? Keeping the number of labels to a minimum improves adoption.</span></span>

- <span data-ttu-id="089d7-p110">Utilizzare etichette secondarie per i reparti chiave &ndash; alcuni reparti hanno esigenze specifiche che richiedono etichette specifiche. Definire queste etichette come secondarie rispetto a un'etichetta esistente e utilizzare criteri con ambito assegnati a gruppi di utenti, anziché a livello globale.</span><span class="sxs-lookup"><span data-stu-id="089d7-p110">Use sub-labels for key departments &ndash; Some departments will have specific needs that require specific labels. Define these labels as sub-labels to an existing label, and consider using scoped policies that are assigned to user groups instead of globally.</span></span>

- <span data-ttu-id="089d7-p111">Prendere in considerazione i criteri con ambito &ndash; criteri destinati a sottoinsiemi di utenti che impediscono un "sovraccarico di etichette". Un criterio con ambito consente di abilitare l'assegnazione di etichette (secondarie) specifiche per ruoli o reparti solo ai dipendenti che lavorano per un determinato reparto.</span><span class="sxs-lookup"><span data-stu-id="089d7-p111">Consider scoped policies &ndash; Policies targeted at subsets of users will prevent "label overload". A scoped policy lets you assign role or department-specific (sub-)labels to just employees that work for that specific department.</span></span>

- <span data-ttu-id="089d7-p112">Utilizzare nomi significativi per le etichette (si consiglia di non usare termini specifici, standard o acronimi) &ndash; Provare a usare nomi familiari agli utenti finali per migliorarne l'adozione. Anziché usare etichette come PII, PCI, HIPAA, LBI, MBI e HBI, scegliere nomi quali Non aziendale, Pubblico, Generale, Riservato ed Estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="089d7-p112">Use meaningful label names &ndash; We recommend that you don't use jargon, standards, or acronyms as label names. Try to use names that resonate with the end user to improve adoption. Instead of using labels like PII, PCI, HIPAA, LBI, MBI, and HBI, consider names like Non-Business, Public, General, Confidential, and Highly Confidential.</span></span>

### <a name="example-classification-schema"></a><span data-ttu-id="089d7-155">Schema di classificazione di esempio</span><span class="sxs-lookup"><span data-stu-id="089d7-155">Example classification schema</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="089d7-156"><strong>Nome etichetta</strong></span><span class="sxs-lookup"><span data-stu-id="089d7-156"><strong>Label name</strong></span></span></th>
<th align="left"><span data-ttu-id="089d7-157"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="089d7-157"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="089d7-158">Personale</span><span class="sxs-lookup"><span data-stu-id="089d7-158">Personal</span></span></td>
<td align="left"><span data-ttu-id="089d7-159">Dati non aziendali, solo per uso personale.</span><span class="sxs-lookup"><span data-stu-id="089d7-159">Non-business data, for personal use only.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="089d7-160">Pubblico</span><span class="sxs-lookup"><span data-stu-id="089d7-160">Public</span></span></td>
<td align="left"><span data-ttu-id="089d7-161">Dati aziendali appositamente preparati e approvati per l'utilizzo pubblico.</span><span class="sxs-lookup"><span data-stu-id="089d7-161">Business data that is specifically prepared and approved for public consumption.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="089d7-162">Dati della società</span><span class="sxs-lookup"><span data-stu-id="089d7-162">Customer data</span></span></td>
<td align="left"><span data-ttu-id="089d7-p113">Dati aziendali contenenti informazioni di identificazione personale (ad esempio; numeri di carte di credito, numeri di conto corrente e numeri di previdenza sociale).</span><span class="sxs-lookup"><span data-stu-id="089d7-p113">Business data that contains personal identifiable information. Examples are credit card numbers, bank account numbers, and social security numbers.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="089d7-165">Dati sulle risorse umane</span><span class="sxs-lookup"><span data-stu-id="089d7-165">HR data</span></span></td>
<td align="left"><span data-ttu-id="089d7-166">Dati sulle risorse umane sui dipendenti di Contoso, come i dati sulle retribuzioni e sul numero di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="089d7-166">Human Resource data about Contoso employees, such as employee number and salary data.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="089d7-167">Riservato</span><span class="sxs-lookup"><span data-stu-id="089d7-167">Confidential</span></span></td>
<td align="left"><span data-ttu-id="089d7-p114">Dati aziendali riservati che potrebbero causare danni all'azienda qualora fossero condivisi con persone non autorizzate (ad esempio: contratti, report sulla sicurezza, riepilogo delle previsioni e dati sul conto vendite).</span><span class="sxs-lookup"><span data-stu-id="089d7-p114">Sensitive business data that could cause damage to the business if shared with unauthorized people. Examples include contracts, security reports, forecast summaries, and sales account data.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="089d7-170">Estremamente riservato</span><span class="sxs-lookup"><span data-stu-id="089d7-170">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="089d7-p115">Dati aziendali estremamente riservati che potrebbero causare danni all'azienda qualora fossero condivisi con persone non autorizzate (ad esempio: informazioni su clienti e dipendenti, password, codice sorgente e report finanziari pre-annunciati.</span><span class="sxs-lookup"><span data-stu-id="089d7-p115">Very sensitive business data that would cause damage to the business if it was shared with unauthorized people. Examples include employee and customer information, passwords, source code, and pre-announced financial reports.</span></span></td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a><span data-ttu-id="089d7-173">Definire una tassonomia e criteri di ricerca per ogni etichetta</span><span class="sxs-lookup"><span data-stu-id="089d7-173">Define a taxonomy and search criteria for each label</span></span>

<span data-ttu-id="089d7-p116">Dopo aver sviluppato uno schema di classificazione per l'organizzazione, il passaggio successivo consiste nello sviluppo della tassonomia e dei criteri di ricerca per trovare tali dati. Per i dati personali, questa operazione è già stata completata identificando i tipi di informazioni riservate e personalizzando o creando nuovi tipi di informazioni riservate per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="089d7-p116">After developing a classification schema for your organization, the next step is to develop the taxonomy and search criteria for finding this data. For personal data, you've already completed this work by identifying sensitive information types and customizing or creating new sensitive information types for your environment.</span></span>

<span data-ttu-id="089d7-p117">La tabella seguente fornisce un esempio di schema, tassonomia e criteri di ricerca per un'organizzazione. Le etichette sono ordinate per livello di gravità dalla meno riservata alla più riservata per garantire che ai dati che corrispondono a più condizioni vengano assegnate le etichette corrette.</span><span class="sxs-lookup"><span data-stu-id="089d7-p117">The following table provides an example schema, taxonomy, and search criteria for an organization. The labels are ordered by sensitivity level from least sensitive to most sensitive to ensure that data that matches multiple label conditions is assigned the appropriate label.</span></span>

<span data-ttu-id="089d7-178">Nota: l'esempio di configurazione viene fornito a scopo puramente illustrativo e non è da considerare come una guida o una risorsa di riferimento.</span><span class="sxs-lookup"><span data-stu-id="089d7-178">Note: The configuration example is provided for illustration only and is not intended as deployment guidance or reference.</span></span>

<span data-ttu-id="089d7-179">Il punto importante è accertarsi che il lavoro investito nel classificare i dati personali per la conformità all'RGPD sia adatto agli obiettivi dell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="089d7-179">The important takeaway is to ensure that the work you invest to classify personal data for GDPR compliance fits together with the objectives for your entire organization.</span></span>

### <a name="example-schema-taxonomy-and-search-criteria"></a><span data-ttu-id="089d7-180">Esempio di schema, tassonomia e criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="089d7-180">Example schema, taxonomy, and search criteria</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="089d7-181"><strong>Etichetta</strong></span><span class="sxs-lookup"><span data-stu-id="089d7-181"><strong>Label</strong></span></span></th>
<th align="left"><span data-ttu-id="089d7-182"><strong>Tassonomia</strong></span><span class="sxs-lookup"><span data-stu-id="089d7-182"><strong>Taxonomy</strong></span></span></th>
<th align="left"><span data-ttu-id="089d7-183"><strong>Metodo</strong></span><span class="sxs-lookup"><span data-stu-id="089d7-183"><strong>Method</strong></span></span></th>
<th align="left"><span data-ttu-id="089d7-184"><strong>Sintassi di ricerca</strong></span><span class="sxs-lookup"><span data-stu-id="089d7-184"><strong>Search syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="089d7-185">Personale</span><span class="sxs-lookup"><span data-stu-id="089d7-185">Personal</span></span></td>
<td align="left"><span data-ttu-id="089d7-186">Documenti personali etichettati manualmente dall'utente finale.</span><span class="sxs-lookup"><span data-stu-id="089d7-186">Documents manually labeled personal by the end user.</span></span></td>
<td align="left"><span data-ttu-id="089d7-187">Manuale</span><span class="sxs-lookup"><span data-stu-id="089d7-187">Manual</span></span></td>
<td align="left"><span data-ttu-id="089d7-188">Documenti personali etichettati manualmente dall'utente finale.</span><span class="sxs-lookup"><span data-stu-id="089d7-188">Documents manually labeled personal by the end user.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="089d7-189">Pubblico</span><span class="sxs-lookup"><span data-stu-id="089d7-189">Public</span></span></td>
<td align="left"><span data-ttu-id="089d7-190">Documenti contenenti la frase Approvato per la pubblicazione ##/#### (senza distinzione tra maiuscole/minuscole), dove # rappresenta qualsiasi cifra.</span><span class="sxs-lookup"><span data-stu-id="089d7-190">Documents containing the case insensitive phrase Approved for Public Release ##/#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="089d7-191">KQL</span><span class="sxs-lookup"><span data-stu-id="089d7-191">KQL</span></span></p>
<p><span data-ttu-id="089d7-192">RegEx</span><span class="sxs-lookup"><span data-stu-id="089d7-192">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="089d7-193">KQL — Approvato per la pubblicazione\*</span><span class="sxs-lookup"><span data-stu-id="089d7-193">KQL — Approved for Public Release\*</span></span></p>
<p><span data-ttu-id="089d7-194">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="089d7-194">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="089d7-195">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="089d7-195">Customer data</span></span></td>
<td align="left"><span data-ttu-id="089d7-196">Tipi di informazioni riservate per i dati dei cittadini dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="089d7-196">Sensitive information types for EU citizen data.</span></span></td>
<td align="left"><span data-ttu-id="089d7-197">Tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="089d7-197">Sensitive information types</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="089d7-198">Risorse umane - Dati dipendenti</span><span class="sxs-lookup"><span data-stu-id="089d7-198">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="089d7-199">Documenti che includono l'id dipendente (con distinzione tra maiuscole/minuscole) nel formato CONTOSO-9#####, dove # rappresenta qualsiasi cifra.</span><span class="sxs-lookup"><span data-stu-id="089d7-199">Documents that include the case-sensitive employee id in the format CONTOSO-9##### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="089d7-200">KQL</span><span class="sxs-lookup"><span data-stu-id="089d7-200">KQL</span></span></p>
<p><span data-ttu-id="089d7-201">RegEx</span><span class="sxs-lookup"><span data-stu-id="089d7-201">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="089d7-202">KQL — CONTOSO-9\*</span><span class="sxs-lookup"><span data-stu-id="089d7-202">KQL — CONTOSO-9\*</span></span></p>
<p><span data-ttu-id="089d7-203">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="089d7-203">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="089d7-204">Risorse umane - Dati sugli stipendi</span><span class="sxs-lookup"><span data-stu-id="089d7-204">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="089d7-205">Documenti che includono la parola chiave (senza distinzione tra maiuscole/minuscole) Contoso AND un'altra parola chiave (senza distinzione tra maiuscole/minuscole), Stipendio OR Retribuzione</span><span class="sxs-lookup"><span data-stu-id="089d7-205">Documents that include the keyword (not case sensitive) Contoso AND either keyword (not case sensitive) Salary OR Compensation</span></span></td>
<td align="left"><p><span data-ttu-id="089d7-206">KQL</span><span class="sxs-lookup"><span data-stu-id="089d7-206">KQL</span></span></p>
<p><span data-ttu-id="089d7-207">RegEx</span><span class="sxs-lookup"><span data-stu-id="089d7-207">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="089d7-208">KQL — Contoso AND (Stipendio OR Retribuzione)</span><span class="sxs-lookup"><span data-stu-id="089d7-208">KQL — Contoso AND (Salary OR Compensation)</span></span></p>
<p><span data-ttu-id="089d7-209">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="089d7-209">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="089d7-210">Riservato</span><span class="sxs-lookup"><span data-stu-id="089d7-210">Confidential</span></span></td>
<td align="left"><span data-ttu-id="089d7-211">Documenti contenenti la frase (senza distinzione tra maiuscole/minuscole) Contoso - Riservato.</span><span class="sxs-lookup"><span data-stu-id="089d7-211">Documents containing the phrase (not case sensitive) Contoso Confidential.</span></span></td>
<td align="left"><p><span data-ttu-id="089d7-212">KQL</span><span class="sxs-lookup"><span data-stu-id="089d7-212">KQL</span></span></p>
<p><span data-ttu-id="089d7-213">RegEx</span><span class="sxs-lookup"><span data-stu-id="089d7-213">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="089d7-214">KQL — Contoso - Riservato</span><span class="sxs-lookup"><span data-stu-id="089d7-214">KQL — Contoso Confidential</span></span></p>
<p><span data-ttu-id="089d7-215">RegEx — (?i)(\bContoso - Riservato\b)</span><span class="sxs-lookup"><span data-stu-id="089d7-215">RegEx — (?i)(\bContoso Confidential\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="089d7-216">Estremamente riservato</span><span class="sxs-lookup"><span data-stu-id="089d7-216">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="089d7-217">Documenti che includono la frase (con distinzione tra maiuscle/minuscole) Contoso Secret o Secret-C####, dove # rappresenta qualsiasi cifra.</span><span class="sxs-lookup"><span data-stu-id="089d7-217">Documents that include either pharase (case sensitive) Contoso Secret or Secret-C#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="089d7-218">KQL</span><span class="sxs-lookup"><span data-stu-id="089d7-218">KQL</span></span></p>
<p><span data-ttu-id="089d7-219">RegEx</span><span class="sxs-lookup"><span data-stu-id="089d7-219">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="089d7-220">KQL — Contoso Secret OR Secret-C\*</span><span class="sxs-lookup"><span data-stu-id="089d7-220">KQL — Contoso Secret OR Secret-C\*</span></span></p>
<p><span data-ttu-id="089d7-221">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="089d7-221">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span></span></p></td>
</tr>
</tbody>
</table>
