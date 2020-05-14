---
title: Cercare e trovare i dati personali
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
description: Informazioni su come cercare e trovare i dati personali soggetti al Regolamento generale sulla protezione dei dati (GDPR) in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0d29697a28221b5ff998f5ce923c143bf7a0804
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214580"
---
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="4a295-103">Cercare e trovare i dati personali</span><span class="sxs-lookup"><span data-stu-id="4a295-103">Search for and find personal data</span></span>

<span data-ttu-id="4a295-104">L'RGPD definisce i dati personali in modo molto generico come qualsiasi dato relativo a una persona fisica identificata o identificabile residente nell'Unione Europea.
</span><span class="sxs-lookup"><span data-stu-id="4a295-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="4a295-105">Articolo 4 - Definizioni</span><span class="sxs-lookup"><span data-stu-id="4a295-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="4a295-106">Con "dati personali" si intende qualsiasi informazione relativa a una persona fisica identificata o identificabile ("interessato"); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, in particolare in riferimento a un identificatore come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o a uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica;</span><span class="sxs-lookup"><span data-stu-id="4a295-106">'personal data' means any information relating to an identified or identifiable natural person ('data subject'); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="4a295-107">In questo articolo viene illustrato come trovare i dati personali archiviati in SharePoint Online e OneDrive for Business (che include i siti per tutti i gruppi di Microsoft 365 e Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="4a295-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Microsoft 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="4a295-108">La ricerca di dati personali soggetti al GDPR si basa sull'utilizzo di tipi di informazioni sensibili in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a295-108">Finding personal data subject to GDPR relies on using sensitive information types in Office 365.</span></span> <span data-ttu-id="4a295-109">Questi definiscono il modo in cui il processo automatizzato riconosce tipi specifici di informazioni come codici di servizi sanitari e numeri di carte di credito.</span><span class="sxs-lookup"><span data-stu-id="4a295-109">These define how the automated process recognizes specific information types such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="4a295-110">È possibile utilizzare i criteri di prevenzione della perdita di dati per trovare i dati personali nella posta durante il transito.</span><span class="sxs-lookup"><span data-stu-id="4a295-110">You can use data loss prevention policies to find personal data in mail while in transit.</span></span> <span data-ttu-id="4a295-111">È possibile utilizzare i tipi di informazioni sensibili curate per il GDPR per trovare e proteggere le informazioni personali inviate tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4a295-111">You can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span> <span data-ttu-id="4a295-112">Vedere inoltre [Gestire richieste dell'interessato per il GDPR con lo strumento dei casi DSR nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).</span><span class="sxs-lookup"><span data-stu-id="4a295-112">Also see [Managed GDPR data subject requests with the DSR case tool in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="4a295-113">Usare Ricerca contenuto per trovare dati personali</span><span class="sxs-lookup"><span data-stu-id="4a295-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="4a295-p102">Microsoft consiglia un approccio in tre fasi per la ricerca di dati personali dell'utente in Office 365. Il resto di questo argomento fornisce informazioni su ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="4a295-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a295-116"><strong>Fase</strong>
</span><span class="sxs-lookup"><span data-stu-id="4a295-116"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="4a295-117"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="4a295-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a295-118">1. Cercare le tipologie di informazioni riservate
</span><span class="sxs-lookup"><span data-stu-id="4a295-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a295-p103">Iniziare utilizzando tipi di informazioni riservate per trovare dati personali. Creare una query di Ricerca contenuto per ogni tipo di informazione riservata. Eseguire la query e analizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="4a295-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="4a295-122">Se necessario, è possibile aggiungere parametri alla query per ridurre i falsi positivi:</span><span class="sxs-lookup"><span data-stu-id="4a295-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="4a295-123">Numero istanze</span><span class="sxs-lookup"><span data-stu-id="4a295-123">Count range</span></span></li>
    <li><span data-ttu-id="4a295-124">Intervallo di confidenza</span><span class="sxs-lookup"><span data-stu-id="4a295-124">Confidence range</span></span></li>
    <li><span data-ttu-id="4a295-125">Altre proprietà od operatori per query più complesse
</span><span class="sxs-lookup"><span data-stu-id="4a295-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="4a295-126">Se necessario, modificare una tipologia di informazione sensibile per ottenere risultati più accurati:
</span><span class="sxs-lookup"><span data-stu-id="4a295-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="4a295-127">Modificare il livello di confidenza direttamente nel file XML.
</span><span class="sxs-lookup"><span data-stu-id="4a295-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="4a295-128">Aggiungere parole chiave.</span><span class="sxs-lookup"><span data-stu-id="4a295-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="4a295-129">Modificare i requisiti di prossimità delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="4a295-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a295-130">2. Usare Keyword Query Language (KQL) per trovare ulteriori dati personali nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="4a295-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a295-131">Per trovare i dati non inclusi nei tipi di informazioni riservate, usare il linguaggio di query KQL per lo sviluppo di query personalizzate.</span><span class="sxs-lookup"><span data-stu-id="4a295-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="4a295-132">Verificare i risultati di queste ricerche e modificare la stringa di query KQL fino a ottenere il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="4a295-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a295-133">3. Creare nuovi tipi di informazioni riservate personalizzati con le query KQL</span><span class="sxs-lookup"><span data-stu-id="4a295-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="4a295-p104">Dopo l'ottimizzazione delle query KQL per trovare i dati di destinazione, è possibile creare nuovi tipi di informazioni riservate personalizzati con queste query. Quindi, è possibile usare questi tipi di informazioni riservate personalizzati con Ricerca contenuto, nei criteri DLP e con altri strumenti e in altre query KQL.</span><span class="sxs-lookup"><span data-stu-id="4a295-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="4a295-136">Cercare le tipologie di informazioni sensibili con Ricerca contenuto
</span><span class="sxs-lookup"><span data-stu-id="4a295-136">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="4a295-137">Avviare la ricerca dei dati personali usando i tipi di informazioni riservate incluse in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a295-137">Begin searching for personal data by using the sensitive information types that are included with Office 365.</span></span> <span data-ttu-id="4a295-138">Questi sono elencati sotto Classificazioni nel Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="4a295-138">These are listed under Classification in the security center and compliance center.</span></span>

<span data-ttu-id="4a295-139">Questo argomento include un elenco di alcuni tipi di informazioni riservate che si applicano ai cittadini dell'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="4a295-139">This topic includes a list of some sensitive information types that apply to citizens in the European Union.</span></span> <span data-ttu-id="4a295-140">Controllare il Centro sicurezza e conformità per le nuove aggiunte che semplificano la conformità all’RGDP.</span><span class="sxs-lookup"><span data-stu-id="4a295-140">Check the security center or the compliance center for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="4a295-141">Vedere anche l'articolo: [Elenco dei tipi di informazioni riservate e l'aspetto di ognuno di essi](https://docs.microsoft.com/microsoft-365/compliance/content-search).</span><span class="sxs-lookup"><span data-stu-id="4a295-141">Also see this article: [List of sensitive information types and what each one looks for](https://docs.microsoft.com/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="4a295-p107">Le tipologie di informazioni sensibili permettono di riconoscere in modo automatico informazioni specifiche come i numeri di previdenza sociale e di carta di credito. Le tipologie di informazioni sensibili sono chiamate anche condizioni. Una tipologia di informazioni sensibili corrisponde a un modello identificato da un'espressione regolare o da una funzione. Inoltre, è possibile utilizzare altri elementi come parole chiave e checksum per identificare una tipologia di informazioni sensibili. In questa procedura di valutazione vengono usati anche il livello di confidenza e la prossimità.
</span><span class="sxs-lookup"><span data-stu-id="4a295-p107">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="4a295-147">Attualmente le tipologie di informazioni sensibili non sono utilizzabili per trovare i dati conservati nelle cassette postali.
</span><span class="sxs-lookup"><span data-stu-id="4a295-147">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="4a295-148">Utilizzo di Ricerca contenuto con le tipologie di informazioni sensibili
</span><span class="sxs-lookup"><span data-stu-id="4a295-148">Using Content Search with sensitive information types</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a295-149"><strong>Fase</strong>
</span><span class="sxs-lookup"><span data-stu-id="4a295-149"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="4a295-150"><strong>Ulteriori informazioni</strong></span><span class="sxs-lookup"><span data-stu-id="4a295-150"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="4a295-151">Andare a Ricerca contenuto nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="4a295-151">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a295-152">Nel riquadro a sinistra del Centro sicurezza e conformità, fare clic su **Ricerca e analisi** &gt; **Ricerca contenuto**.</span><span class="sxs-lookup"><span data-stu-id="4a295-152">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="4a295-153">Vedere <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Eseguire una ricerca contenuto nel Centro sicurezza e conformità</a>.</span><span class="sxs-lookup"><span data-stu-id="4a295-153">See <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a295-154">Creare un nuovo elemento di ricerca per ogni tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="4a295-154">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a295-155">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="4a295-155">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="4a295-156">SensitiveType:"&lt;tipologia&gt;"</span><span class="sxs-lookup"><span data-stu-id="4a295-156">SensitiveType:"&lt;type&gt;"</span></span></p>
</blockquote>
<p><span data-ttu-id="4a295-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4a295-157">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="4a295-158">SensitiveType:&quot;Numero di passaporto francese&quot;</span><span class="sxs-lookup"><span data-stu-id="4a295-158">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="4a295-p108">Definire l'ambito di ricerca per SharePoint (include OneDrive for Business). Verificare che la sintassi sia esatta e non siano presenti spazi o errori di digitazione.</span><span class="sxs-lookup"><span data-stu-id="4a295-p108">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="4a295-161">Vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites">Creare una query per individuare dati riservati memorizzati nei siti</a>.</span><span class="sxs-lookup"><span data-stu-id="4a295-161">See <a href="https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a295-162">Esaminare i risultati per ogni ricerca</span><span class="sxs-lookup"><span data-stu-id="4a295-162">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a295-163">Cercare i tipi di problemi per determinare se la precisione della query viene rispettata:</span><span class="sxs-lookup"><span data-stu-id="4a295-163">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="4a295-164">Molti falsi positivi</span><span class="sxs-lookup"><span data-stu-id="4a295-164">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="4a295-165">Mancano istanze note dei dati
</span><span class="sxs-lookup"><span data-stu-id="4a295-165">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="4a295-166">Vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Esportare i risultati di Ricerca contenuto dal Centro sicurezza e conformità</a>.</span><span class="sxs-lookup"><span data-stu-id="4a295-166">See <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Export Content Search results from the Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="4a295-167">Nota: se si utilizza Mozilla Firefox o Chrome, è necessario prima scaricare i report utilizzando Internet Explorer o Edge per installare il componente aggiuntivo necessario.</span><span class="sxs-lookup"><span data-stu-id="4a295-167">Note: if you're using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="4a295-168">Tipi di informazioni riservate per i dati dei cittadini dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="4a295-168">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="4a295-p109">Iniziare con queste tipologie di informazioni sensibili. Molte altre tipologie saranno presto disponibili per i dati personali nei paesi dell'Unione europea.
</span><span class="sxs-lookup"><span data-stu-id="4a295-p109">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="4a295-171">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="4a295-171">Belgium National Number</span></span>
>
> <span data-ttu-id="4a295-172">Numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="4a295-172">Credit Card Number</span></span>
>
> <span data-ttu-id="4a295-173">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="4a295-173">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="4a295-174">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="4a295-174">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="4a295-175">Numero carta d’identità (Repubblica Ceca)</span><span class="sxs-lookup"><span data-stu-id="4a295-175">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="4a295-176">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="4a295-176">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="4a295-177">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="4a295-177">EU Debit Card Number</span></span>
>
> <span data-ttu-id="4a295-178">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="4a295-178">Finland National ID</span></span>
>
> <span data-ttu-id="4a295-179">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="4a295-179">Finland Passport Number</span></span>
>
> <span data-ttu-id="4a295-180">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="4a295-180">France Driver's License Number</span></span>
>
> <span data-ttu-id="4a295-181">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="4a295-181">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="4a295-182">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="4a295-182">France Passport Number</span></span>
>
> <span data-ttu-id="4a295-183">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="4a295-183">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="4a295-184">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="4a295-184">German Driver's License Number</span></span>
>
> <span data-ttu-id="4a295-185">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="4a295-185">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="4a295-186">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="4a295-186">German Passport Number</span></span>
>
> <span data-ttu-id="4a295-187">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="4a295-187">Greece National ID Card</span></span>
>
> <span data-ttu-id="4a295-188">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="4a295-188">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="4a295-189">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="4a295-189">IP Address</span></span>
>
> <span data-ttu-id="4a295-190">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="4a295-190">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="4a295-191">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="4a295-191">Italy's Driver's License Number</span></span>
>
> <span data-ttu-id="4a295-192">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="4a295-192">Netherlands Citizen's Service (BSN) Number</span></span>
>
> <span data-ttu-id="4a295-193">Norvegia - Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="4a295-193">Norway Identity Number</span></span>
>
> <span data-ttu-id="4a295-194">Carta di identità - Polonia</span><span class="sxs-lookup"><span data-stu-id="4a295-194">Poland Identity Card</span></span>
>
> <span data-ttu-id="4a295-195">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="4a295-195">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="4a295-196">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="4a295-196">Poland Passport</span></span>
>
> <span data-ttu-id="4a295-197">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="4a295-197">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="4a295-198">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="4a295-198">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="4a295-199">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="4a295-199">Sweden National ID</span></span>
>
> <span data-ttu-id="4a295-200">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="4a295-200">Sweden Passport Number</span></span>
>
> <span data-ttu-id="4a295-p110">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="4a295-p110">U.K. Driver's License Number</span></span>
>
> <span data-ttu-id="4a295-p111">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="4a295-p111">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="4a295-p112">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="4a295-p112">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="4a295-p113">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="4a295-p113">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="4a295-p114">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="4a295-p114">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="4a295-211">Aggiungere parametri a una query di un tipo di informazione riservata per perfezionare i risultati</span><span class="sxs-lookup"><span data-stu-id="4a295-211">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="4a295-212">È possibile aggiungere i parametri a una query di un tipo di informazioni riservate:</span><span class="sxs-lookup"><span data-stu-id="4a295-212">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="4a295-213">Numero istanze - Consente di definire il numero di occorrenze di informazioni sensibili che un documento deve contenere prima di essere incluso nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="4a295-213">Count range — define the number of occurrences of sensitive information a document needs to contain before it's included in the query results.</span></span>

-   <span data-ttu-id="4a295-214">Intervallo di confidenza - Indica il livello di confidenza secondo il quale la tipologia di informazione sensibile identificata rappresenta effettivamente una corrispondenza, ad esempio 85 (85%).
</span><span class="sxs-lookup"><span data-stu-id="4a295-214">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="4a295-215">Sintassi:</span><span class="sxs-lookup"><span data-stu-id="4a295-215">Syntax:</span></span>

-   <span data-ttu-id="4a295-216">SensitiveType:"\<tipologia\>|\<numero istanze\>|\<intervallo confidenza\>"</span><span class="sxs-lookup"><span data-stu-id="4a295-216">SensitiveType:"\<type\>|\<count range\>|\<confidence range\>"</span></span>

<span data-ttu-id="4a295-217">Esempi:</span><span class="sxs-lookup"><span data-stu-id="4a295-217">Examples:</span></span>

-   <span data-ttu-id="4a295-218">SensitiveType:"Credit Card Number|5" (restituisce soltanto i documenti che contengono esattamente cinque numeri di carta di credito)</span><span class="sxs-lookup"><span data-stu-id="4a295-218">SensitiveType:"Credit Card Number|5" (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="4a295-219">SensitiveType:"Credit Card Number|\*|85.." (l'intervallo di confidenza è pari almeno all'85%)</span><span class="sxs-lookup"><span data-stu-id="4a295-219">SensitiveType:"Credit Card Number|\*|85.." (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="4a295-220">Nota: "SensitiveType" distingue tra maiuscole e minuscole, il resto della query no.</span><span class="sxs-lookup"><span data-stu-id="4a295-220">Note: "SensitiveType" is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="4a295-p115">È inoltre possibile usare le proprietà e gli operatori per illustrare il modo in cui è possibile perfezionare le query. Per ulteriori informazioni ed esempi, vedere [Creare una query per trovare i dati riservati archiviati nei siti](https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites).</span><span class="sxs-lookup"><span data-stu-id="4a295-p115">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites).</span></span>
