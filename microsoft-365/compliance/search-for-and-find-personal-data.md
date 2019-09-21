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
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="d00c1-103">Cercare e trovare i dati personali</span><span class="sxs-lookup"><span data-stu-id="d00c1-103">Search for and find personal data</span></span>

<span data-ttu-id="d00c1-104">L'RGPD definisce i dati personali in modo molto generico come qualsiasi dato relativo a una persona fisica identificata o identificabile residente nell'Unione Europea.
</span><span class="sxs-lookup"><span data-stu-id="d00c1-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="d00c1-105">Articolo 4 - Definizioni</span><span class="sxs-lookup"><span data-stu-id="d00c1-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="d00c1-106">Il termine "dati personali" si riferisce a qualsiasi informazione relativa a una persona fisica identificata o identificabile ("soggetto dei dati"); una persona fisica identificabile è una persona che può essere identificata, direttamente o indirettamente, tramite dati specifici come un nome, un numero di identificazione, dati sulla posizione, un identificatore online o uno o più fattori specifici per l'identità fisica, psicologica, genetica, mentale, economica, culturale o sociale della persona fisica;
</span><span class="sxs-lookup"><span data-stu-id="d00c1-106">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="d00c1-107">In questo articolo viene illustrato come trovare i dati personali archiviati in SharePoint Online e OneDrive for Business (che include i siti per tutti i gruppi di Office 365 e Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="d00c1-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Office 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="d00c1-p101">L'individuazione dei dati personali soggetti all'RGPD si basa sull'utilizzo di tipi di informazioni riservate in Office 365. Queste definiscono il modo in cui il processo automatico riconosce tipi di informazione specifici come i numeri di previdenza sociale e di carta di credito. Al momento, tali informazioni non possono essere usate per trovare i dati nelle cassette postali di Exchange inattive. Tuttavia, i tipi di informazioni riservate possono essere usate con criteri di prevenzione della perdita dei dati per trovare dati personali nella posta elettronica in transito.</span><span class="sxs-lookup"><span data-stu-id="d00c1-p101">Finding personal data subject to GDPR relies on using sensitive information types in Office 365. These define how the automated process recognizes specific information types such as health service numbers and credit card numbers. At this time these cannot be used to find data in Exchange mailboxes at rest. However, sensitive information types can be used with data loss prevention policies to find personal data in mail while in transit.</span></span>

<span data-ttu-id="d00c1-112">Quindi, attualmente non è possibile usare Ricerca contenuto per trovare i dati personali archiviati nelle cassette postali di Exchange Online, ma è possibile utilizzare le tipologie di informazioni sensibili definite per l'RGPD per trovare e proteggere le informazioni personali quando vengono inviate tramite posta elettronica.
</span><span class="sxs-lookup"><span data-stu-id="d00c1-112">So, while you can’t currently use Content Search to find personal data at rest in Exchange Online mailboxes, you can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="d00c1-113">Usare Ricerca contenuto per trovare dati personali</span><span class="sxs-lookup"><span data-stu-id="d00c1-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="d00c1-p102">Microsoft consiglia un approccio in tre fasi per la ricerca di dati personali dell'utente in Office 365. Il resto di questo argomento fornisce informazioni su ognuno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d00c1-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table><span data-ttu-id="d00c1-116">
<thead>
<tr class="header">
<th align="left"><strong>Passaggio</strong></span><span class="sxs-lookup"><span data-stu-id="d00c1-116">Step</span></span></th>
<th align="left"><span data-ttu-id="d00c1-117"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="d00c1-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d00c1-118">1. Cercare le tipologie di informazioni riservate
</span><span class="sxs-lookup"><span data-stu-id="d00c1-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="d00c1-p103">Iniziare utilizzando tipi di informazioni riservate per trovare dati personali. Creare una query di Ricerca contenuto per ogni tipo di informazione riservata. Eseguire la query e analizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d00c1-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="d00c1-122">Se necessario, è possibile aggiungere parametri alla query per ridurre i falsi positivi:</span><span class="sxs-lookup"><span data-stu-id="d00c1-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="d00c1-123">Numero istanze</span><span class="sxs-lookup"><span data-stu-id="d00c1-123">Count range</span></span></li>
    <li><span data-ttu-id="d00c1-124">Intervallo di confidenza</span><span class="sxs-lookup"><span data-stu-id="d00c1-124">Confidence range</span></span></li>
    <li><span data-ttu-id="d00c1-125">Altre proprietà od operatori per query più complesse
</span><span class="sxs-lookup"><span data-stu-id="d00c1-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="d00c1-126">Se necessario, modificare una tipologia di informazione sensibile per ottenere risultati più accurati:
</span><span class="sxs-lookup"><span data-stu-id="d00c1-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="d00c1-127">Modificare il livello di confidenza direttamente nel file XML.
</span><span class="sxs-lookup"><span data-stu-id="d00c1-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="d00c1-128">Aggiungere parole chiave.</span><span class="sxs-lookup"><span data-stu-id="d00c1-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="d00c1-129">Modificare i requisiti di prossimità delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="d00c1-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d00c1-130">2. Usare Keyword Query Language (KQL) per trovare ulteriori dati personali nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="d00c1-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="d00c1-131">Per trovare i dati non inclusi nei tipi di informazioni riservate, usare il linguaggio di query KQL per lo sviluppo di query personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d00c1-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="d00c1-132">Verificare i risultati di queste ricerche e modificare la stringa di query KQL fino a ottenere il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="d00c1-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d00c1-133">3. Creare nuovi tipi di informazioni riservate personalizzati con le query KQL</span><span class="sxs-lookup"><span data-stu-id="d00c1-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="d00c1-p104">Dopo l'ottimizzazione delle query KQL per trovare i dati di destinazione, è possibile creare nuovi tipi di informazioni riservate personalizzati con queste query. Quindi, è possibile usare questi tipi di informazioni riservate personalizzati con Ricerca contenuto, nei criteri DLP e con altri strumenti e in altre query KQL.</span><span class="sxs-lookup"><span data-stu-id="d00c1-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="d00c1-136">Cercare le tipologie di informazioni sensibili con Ricerca contenuto
</span><span class="sxs-lookup"><span data-stu-id="d00c1-136">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="d00c1-137">Avviare la ricerca dei dati personali usando i tipi di informazioni riservate incluse in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d00c1-137">Begin searching for personal data by using the sensitive information types that are included with Office 365.</span></span> <span data-ttu-id="d00c1-138">Questi sono elencati sotto Classificazioni nel Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="d00c1-138">These are listed under Classification in the security center and compliance center.</span></span>

<span data-ttu-id="d00c1-139">Questo argomento include un elenco di alcuni tipi di informazioni riservate che si applicano ai cittadini dell'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="d00c1-139">This topic includes a list of some sensitive information types that apply to citizens in the European Union.</span></span> <span data-ttu-id="d00c1-140">Controllare il Centro sicurezza e conformità per le nuove aggiunte che semplificano la conformità all’RGDP.</span><span class="sxs-lookup"><span data-stu-id="d00c1-140">Check the security center or the compliance center for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="d00c1-141">Vedere anche l'articolo: [Elenco dei tipi di informazioni riservate e l'aspetto di ognuno di essi](https://support.office.com/it-IT/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span><span class="sxs-lookup"><span data-stu-id="d00c1-141">Also see this article: [List of sensitive information types and what each one looks for](https://support.office.com/it-IT/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span></span>

<span data-ttu-id="d00c1-p107">Le tipologie di informazioni sensibili permettono di riconoscere in modo automatico informazioni specifiche come i numeri di previdenza sociale e di carta di credito. Le tipologie di informazioni sensibili sono chiamate anche condizioni. Una tipologia di informazioni sensibili corrisponde a un modello identificato da un'espressione regolare o da una funzione. Inoltre, è possibile utilizzare altri elementi come parole chiave e checksum per identificare una tipologia di informazioni sensibili. In questa procedura di valutazione vengono usati anche il livello di confidenza e la prossimità.
</span><span class="sxs-lookup"><span data-stu-id="d00c1-p107">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="d00c1-147">Attualmente le tipologie di informazioni sensibili non sono utilizzabili per trovare i dati conservati nelle cassette postali.
</span><span class="sxs-lookup"><span data-stu-id="d00c1-147">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="d00c1-148">Utilizzo di Ricerca contenuto con le tipologie di informazioni sensibili
</span><span class="sxs-lookup"><span data-stu-id="d00c1-148">Using Content Search with sensitive information types</span></span>

<table><span data-ttu-id="d00c1-149">
<thead>
<tr class="header">
<th align="left"><strong>Passaggio</strong></span><span class="sxs-lookup"><span data-stu-id="d00c1-149">Step</span></span></th>
<th align="left"><span data-ttu-id="d00c1-150"><strong>Ulteriori informazioni</strong></span><span class="sxs-lookup"><span data-stu-id="d00c1-150"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="d00c1-151">Andare a Ricerca contenuto nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d00c1-151">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="d00c1-152">Nel riquadro a sinistra del Centro sicurezza e conformità, fare clic su **Ricerca e analisi** &gt; **Ricerca contenuto**.</span><span class="sxs-lookup"><span data-stu-id="d00c1-152">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="d00c1-153">Vedere <a href="https://support.office.com/it-IT/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Eseguire Ricerca contenuto nel Centro sicurezza e conformità di Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="d00c1-153">See <a href="https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d00c1-154">Creare un nuovo elemento di ricerca per ogni tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="d00c1-154">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="d00c1-155">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="d00c1-155">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="d00c1-156">SensitiveType:"&lt;tipologia&gt;"
</span><span class="sxs-lookup"><span data-stu-id="d00c1-156">SensitiveType:”&lt;type&gt;”</span></span></p>
</blockquote>
<p><span data-ttu-id="d00c1-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d00c1-157">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="d00c1-158">SensitiveType:&quot;Numero di passaporto francese&quot;</span><span class="sxs-lookup"><span data-stu-id="d00c1-158">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="d00c1-p108">Definire l'ambito di ricerca per SharePoint (include OneDrive for Business). Verificare che la sintassi sia esatta e non siano presenti spazi o errori di digitazione.</span><span class="sxs-lookup"><span data-stu-id="d00c1-p108">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="d00c1-161">Vedere <a href="https://support.office.com/it-IT/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Creare una query per individuare dati riservati memorizzati nei siti</a>.</span><span class="sxs-lookup"><span data-stu-id="d00c1-161">See <a href="https://support.office.com/it-IT/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d00c1-162">Esaminare i risultati per ogni ricerca</span><span class="sxs-lookup"><span data-stu-id="d00c1-162">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="d00c1-163">Cercare i tipi di problemi per determinare se la precisione della query viene rispettata:</span><span class="sxs-lookup"><span data-stu-id="d00c1-163">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="d00c1-164">Molti falsi positivi</span><span class="sxs-lookup"><span data-stu-id="d00c1-164">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="d00c1-165">Mancano istanze note dei dati
</span><span class="sxs-lookup"><span data-stu-id="d00c1-165">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="d00c1-166">Vedere <a href="https://support.office.com/it-IT/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Esportare i risultati di Ricerca contenuto dal Centro sicurezza e conformità di Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="d00c1-166">See <a href="https://support.office.com/en-us/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Export Content Search results from the Office 365 Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="d00c1-167">Nota: se si utilizza Mozilla Firefox o Chrome, è necessario prima scaricare i report utilizzando Internet Explorer o Edge per installare il componente aggiuntivo necessario.</span><span class="sxs-lookup"><span data-stu-id="d00c1-167">Note: if you’re using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="d00c1-168">Tipi di informazioni riservate per i dati dei cittadini dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="d00c1-168">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="d00c1-p109">Iniziare con queste tipologie di informazioni sensibili. Molte altre tipologie saranno presto disponibili per i dati personali nei paesi dell'Unione europea.
</span><span class="sxs-lookup"><span data-stu-id="d00c1-p109">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="d00c1-171">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="d00c1-171">Belgium National Number</span></span>
>
> <span data-ttu-id="d00c1-172">Numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="d00c1-172">Credit Card Number</span></span>
>
> <span data-ttu-id="d00c1-173">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="d00c1-173">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="d00c1-174">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="d00c1-174">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="d00c1-175">Numero carta d’identità (Repubblica Ceca)</span><span class="sxs-lookup"><span data-stu-id="d00c1-175">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="d00c1-176">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="d00c1-176">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="d00c1-177">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="d00c1-177">EU Debit Card Number</span></span>
>
> <span data-ttu-id="d00c1-178">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="d00c1-178">Finland National ID</span></span>
>
> <span data-ttu-id="d00c1-179">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="d00c1-179">Finland Passport Number</span></span>
>
> <span data-ttu-id="d00c1-180">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="d00c1-180">France Driver's License Number</span></span>
>
> <span data-ttu-id="d00c1-181">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="d00c1-181">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="d00c1-182">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="d00c1-182">France Passport Number</span></span>
>
> <span data-ttu-id="d00c1-183">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="d00c1-183">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="d00c1-184">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="d00c1-184">German Driver’s License Number</span></span>
>
> <span data-ttu-id="d00c1-185">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="d00c1-185">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="d00c1-186">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="d00c1-186">German Passport Number</span></span>
>
> <span data-ttu-id="d00c1-187">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="d00c1-187">Greece National ID Card</span></span>
>
> <span data-ttu-id="d00c1-188">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="d00c1-188">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="d00c1-189">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="d00c1-189">IP Address</span></span>
>
> <span data-ttu-id="d00c1-190">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="d00c1-190">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="d00c1-191">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="d00c1-191">Italy’s Driver’s License Number</span></span>
>
> <span data-ttu-id="d00c1-192">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="d00c1-192">Netherlands Citizen’s Service (BSN) Number</span></span>
>
> <span data-ttu-id="d00c1-193">Norvegia - Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="d00c1-193">Norway Identity Number</span></span>
>
> <span data-ttu-id="d00c1-194">Carta di identità - Polonia</span><span class="sxs-lookup"><span data-stu-id="d00c1-194">Poland Identity Card</span></span>
>
> <span data-ttu-id="d00c1-195">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="d00c1-195">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="d00c1-196">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="d00c1-196">Poland Passport</span></span>
>
> <span data-ttu-id="d00c1-197">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="d00c1-197">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="d00c1-198">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="d00c1-198">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="d00c1-199">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="d00c1-199">Sweden National ID</span></span>
>
> <span data-ttu-id="d00c1-200">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="d00c1-200">Sweden Passport Number</span></span>
>
> <span data-ttu-id="d00c1-p110">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="d00c1-p110">U.K. Driver’s License Number</span></span>
>
> <span data-ttu-id="d00c1-p111">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="d00c1-p111">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="d00c1-p112">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="d00c1-p112">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="d00c1-p113">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="d00c1-p113">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="d00c1-p114">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="d00c1-p114">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="d00c1-211">Aggiungere parametri a una query di un tipo di informazione riservata per perfezionare i risultati</span><span class="sxs-lookup"><span data-stu-id="d00c1-211">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="d00c1-212">È possibile aggiungere i parametri a una query di un tipo di informazioni riservate:</span><span class="sxs-lookup"><span data-stu-id="d00c1-212">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="d00c1-213">Numero istanze - Consente di definire il numero di occorrenze di informazioni riservato che un documento deve contenere prima di essere incluso nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="d00c1-213">Count range — define the number of occurrences of sensitive information a document needs to contain before it’s included in the query results.</span></span>

-   <span data-ttu-id="d00c1-214">Intervallo di confidenza - Indica il livello di confidenza secondo il quale la tipologia di informazione sensibile identificata rappresenta effettivamente una corrispondenza, ad esempio 85 (85%).
</span><span class="sxs-lookup"><span data-stu-id="d00c1-214">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="d00c1-215">Sintassi:</span><span class="sxs-lookup"><span data-stu-id="d00c1-215">Syntax:</span></span>

-   <span data-ttu-id="d00c1-216">SensitiveType:”\<tipologia\>|\<numero istanze\>|\<intervallo confidenza\>”
</span><span class="sxs-lookup"><span data-stu-id="d00c1-216">SensitiveType:”\<type\>|\<count range\>|\<confidence range\>”</span></span>

<span data-ttu-id="d00c1-217">Esempi:</span><span class="sxs-lookup"><span data-stu-id="d00c1-217">Examples:</span></span>

-   <span data-ttu-id="d00c1-218">SensitiveType:“Credit Card Number|5” (restituisce soltanto i documenti che contengono esattamente cinque numeri di carta di credito)</span><span class="sxs-lookup"><span data-stu-id="d00c1-218">SensitiveType:“Credit Card Number|5” (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="d00c1-p115">SensitiveType:“Credit Card Number|\*|85..” (l'intervallo di confidenza è pari almeno all'85%)</span><span class="sxs-lookup"><span data-stu-id="d00c1-p115">SensitiveType:“Credit Card Number|\*|85..” (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="d00c1-221">Nota: "SensitiveType" distingue tra maiuscole e minuscole, il resto della query no.</span><span class="sxs-lookup"><span data-stu-id="d00c1-221">Note: “SensitiveType” is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="d00c1-p116">È inoltre possibile usare le proprietà e gli operatori per illustrare il modo in cui è possibile perfezionare le query. Per ulteriori informazioni ed esempi, vedere [Creare una query per trovare i dati riservati archiviati nei siti](https://support.office.com/it-IT/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span><span class="sxs-lookup"><span data-stu-id="d00c1-p116">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://support.office.com/it-IT/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span></span>
